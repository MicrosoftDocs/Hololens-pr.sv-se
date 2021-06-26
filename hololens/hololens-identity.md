---
title: Hantera användaridentitet och inloggning för HoloLens
description: Lär dig hur du hanterar användaridentitet, stöd för flera användare, säkerhet, företagsautentisering och inloggning för HoloLens-enheter.
keywords: HoloLens, user, account, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924425"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Hantera användaridentitet och inloggning för HoloLens

> [!NOTE]
> Den här artikeln är en teknisk referens för IT-proffs och tekniker. Om du letar efter anvisningar för HoloLens-set up (HoloLens-set up instructions) kan du läsa "[Setting up your HoloLens (1st gen)](hololens1-start.md)" (Konfigurera din HoloLens 2) eller " Setting up your[HoloLens 2 " (Konfigurera HoloLens 2).](hololens2-start.md)

Precis som andra Windows-enheter fungerar HoloLens alltid i användarkontext. Det finns alltid en användaridentitet. HoloLens behandlar identitet på nästan samma sätt som andra Windows 10 enheter gör. Den här artikeln är en djupgående referens för identitet på HoloLens och fokuserar på hur HoloLens skiljer sig från andra Windows 10 enheter.

HoloLens stöder flera typer av användaridentiteter. Du kan använda ett eller flera användarkonton för att logga in. Här är en översikt över identitetstyper och autentiseringsalternativ på HoloLens:

| Identitetstyp | Konton per enhet | Autentiseringsalternativ |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure-provider för webb autentiseringsuppgifter</li><li>Azure Authenticator-app</li><li>Biometric (Iris) &ndash; HoloLens 2 endast<sup>2</sup> </li><li>&ndash;PIN-kod (valfritt) för HoloLens (1:a gen), krävs för HoloLens 2</li><li>Lösenord</li></ul> |
| [Microsoft-konto (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrik &ndash; (Iris) Endast HoloLens 2</li><li>&ndash;PIN-kod (valfritt) för HoloLens (1:a gen), krävs för HoloLens 2</li><li>Lösenord</li></ul> |
| [Lokalt konto](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Lösenord |

Molnanslutna konton (Azure AD och MSA) erbjuder fler funktioner eftersom de kan använda Azure-tjänster.  
> [!IMPORTANT]
> 1 – Azure AD Premium krävs inte för att logga in på enheten. Det krävs dock för andra funktioner i en molnbaserad low touch-distribution, till exempel automatisk registrering och Autopilot.

> [!NOTE]
> 2 – Även om en HoloLens 2-enhet har stöd för upp till 64 Azure AD-konton kan endast 10 av dessa konton registreras i Iris-autentisering. Detta är justerat med andra [alternativ för biometrisk autentisering för Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

## <a name="setting-up-users"></a>Konfigurera användare

Det vanligaste sättet att konfigurera en ny användare är under OoBE (Out-of-Box Experience) för HoloLens. Under installationen uppmanar HoloLens en användare att logga in med det konto som han eller hon vill använda på enheten. Det här kontot kan vara en Microsoft-konto eller ett företagskonto som har konfigurerats i Azure. Se Konfigurera din [HoloLens (första gen) eller](hololens1-start.md) [HoloLens 2.](hololens2-start.md)

Precis som Windows på andra enheter skapar inloggning under installationen en användarprofil på enheten. Användarprofilen lagrar appar och data. Samma konto tillhandahåller också enkel inloggning för appar, till exempel Edge eller Microsoft Store, med hjälp av Api:er för Windows Account Manager.  

Om du använder ett företags- eller organisationskonto för att logga in på HoloLens registreras HoloLens i organisationens IT-infrastruktur. Med den här registreringen kan IT-administratören konfigurera Mobile Enhetshantering (MDM) för att skicka grupprinciper till din HoloLens.

Som standard, precis som Windows 10 andra enheter, måste du logga in igen när HoloLens startas om eller återupptas från vänteläge. Du kan använda appen Inställningar för att ändra det här beteendet, eller så kan beteendet styras av en grupprincip.

### <a name="linked-accounts"></a>Länkade konton

Precis som i Desktop-versionen av Windows kan du länka ytterligare autentiseringsuppgifter för webbkontot till ditt HoloLens-konto. Sådana länkar gör det enklare att komma åt resurser i eller inom appar (till exempel Store) eller kombinera åtkomst till personliga och arbetsresurser. När du har anslutt ett konto till enheten kan du bevilja behörighet att använda enheten i appar så att du inte behöver logga in i varje app individuellt.

Länkningskonton separerar inte användardata som skapats på enheten, till exempel bilder eller nedladdningar.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Konfigurera stöd för flera användare (endast Azure AD)

HoloLens stöder flera användare från samma Azure AD-klientorganisation. Om du vill använda den här funktionen måste du använda ett konto som tillhör din organisation för att konfigurera enheten. Därefter kan andra användare från samma klientorganisation logga in på enheten från inloggningsskärmen eller genom att trycka på användarpanelen på startpanelen. Endast en användare kan loggas in i taget. När en användare loggar in loggar HoloLens ut den tidigare användaren. Den första användaren på enheten betraktas som enhetens ägare, förutom när det gäller Azure AD-anslutning. Läs [mer om enhetsägare.](security-adminless-os.md#device-owner)

Alla användare kan använda de appar som är installerade på enheten. Varje användare har dock sina egna appdata och inställningar. Om du tar bort en app från enheten tas den bort för alla användare.  

Enheter som konfigureras med Azure AD-konton tillåter inte inloggning på enheten med ett Microsoft-konto. Alla efterföljande konton som används måste vara Azure AD-konton från samma klientorganisation som enheten. Du kan fortfarande [logga in med ett Microsoft-konto till appar](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) som stöder det (till exempel Microsoft Store). Om du vill ändra från att använda Azure AD-konton till Microsoft-konton för att logga in på enheten måste [du omsluta enheten](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (första generationen)** började stödja flera Azure [AD-användare i April 2018-uppdatering för Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) som en del av [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Flera användare visas på inloggningsskärmen

Tidigare visade inloggningsskärmen endast den senast inloggade användaren, samt en startpunkt för "Annan användare". Vi har fått feedback från kunder om att detta inte räcker om flera användare har loggat in på enheten. De var fortfarande nödvändiga för att skriva in användarnamnet igen.

Introducerades [i Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), när du väljer Annan användare som finns till höger om fältet PIN-kodspost, visar inloggningsskärmen flera användare med som tidigare har loggat in på enheten.  På så sätt kan användarna välja sin användarprofil och sedan logga in med sina Windows Hello autentiseringsuppgifter. En ny användare kan också läggas till på enheten från sidan Andra användare via knappen **Lägg till** konto.

I menyn Andra användare visar knappen Andra användare den senaste användaren som loggat in på enheten. Välj den här knappen för att återgå till inloggningsskärmen för den här användaren.

![Standard för inloggningsskärmen](./images/multiusers1.jpg)

<br>

![Inloggningsskärm för andra användare](./images/multiusers2.jpg)

## <a name="removing-users"></a>Ta bort användare

Du kan ta bort en användare från enheten genom att gå till **Inställningar**  >  **Konton**  >  **Andra personer.** Den här åtgärden återtar också utrymme genom att ta bort alla användarens appdata från enheten.  

## <a name="using-single-sign-on-within-an-app"></a>Använda enkel inloggning i en app

Som apputvecklare kan du dra nytta av länkade identiteter på HoloLens med hjälp av API:er för [Windows Account Manager,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)precis som på andra Windows-enheter. Vissa kodexempel för dessa API:er finns på GitHub: [Web account management sample](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Alla kontoavbrott som kan inträffa, till exempel att begära användarmedgivande för kontoinformation, tvåfaktorautentisering och så vidare, måste hanteras när appen begär en autentiseringstoken.

Om din app kräver en viss kontotyp som inte har länkats tidigare kan din app be systemet att uppmana användaren att lägga till en. Den här begäran utlöser fönstret kontoinställningar för att starta som ett modalt underkonto till din app. För 2D-appar återges det här fönstret direkt i mitten av din app. För Unity-appar tar den här begäran kort användaren bort från din holografiska app för att återge det underordnade fönstret. Information om hur du anpassar kommandona och åtgärderna i det här fönstret finns [i WebAccountCommand Class](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Företagsautentisering och annan autentisering

Om din app använder andra typer av autentisering, till exempel NTLM, Basic eller Kerberos, kan du använda [användargränssnittet](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) för Windows-autentiseringsuppgifter för att samla in, bearbeta och lagra användarens autentiseringsuppgifter. Användarupplevelsen för att samla in dessa autentiseringsuppgifter liknar andra molnbaserade kontoavbrott och visas som en underordnad app ovanpå din 2D-app eller pausar en Unity-app en kort stund för att visa användargränssnittet.

## <a name="deprecated-apis"></a>Inaktuella API:er

Ett sätt att utveckla för HoloLens skiljer sig från att utveckla för Desktop är att [API:et OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) inte stöds fullt ut. Även om API:et returnerar en token om det primära kontot är i gott stående, så visar avbrott som de som beskrivs i den här artikeln inte något användargränssnitt för användaren och kan inte autentisera kontot korrekt.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Stöds Windows Hello för företag hololens (första generationen)?

Windows Hello för företag (som stöder användning av en PIN-kod för att logga in) stöds för HoloLens (första generationen). Så här tillåter Windows Hello för företag INLOGGNING MED PIN-kod på HoloLens:

1. HoloLens-enheten måste [hanteras av MDM](hololens-enroll-mdm.md).
1. Du måste aktivera Windows Hello för företag för enheten. ([Se anvisningarna för Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. På HoloLens kan användaren sedan använda Inställningar **Inloggningsalternativ**  >  **Lägg till PIN-kod** för att konfigurera en  >   PIN-kod.

> [!NOTE]
> Användare som loggar in med en Microsoft-konto kan också konfigurera en PIN-kod i **Inställningar** Inloggningsalternativ  >  **Lägg till**  >  **PIN-kod.** Den här PIN-koden [är associerad Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), i stället för [Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Hur implementeras biometrisk Iris-autentisering på HoloLens 2?

HoloLens 2 stöder Iris-autentisering. Iris är baserad på Windows Hello och stöds för användning av både Azure Active Directory- och Microsoft-konton. Iris implementeras på samma sätt som andra Windows Hello och uppnår biometrisäkerhet PÅ 1/100 000.

Se [biometriska krav och specifikationer för Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) mer information. Läs mer om [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) och [Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hur påverkar kontotypen inloggningsbeteendet?

Om du tillämpar principer för inloggning respekteras alltid principen. Om ingen princip för inloggning tillämpas är dessa standardbeteenden för varje kontotyp:

- **Azure AD:** frågar efter autentisering som standard och kan konfigureras av **Inställningar för** att inte längre be om autentisering.
- **Microsoft-konto:** Låsbeteendet skiljer sig åt så att automatisk upplåsning tillåts, men inloggningsautentisering krävs fortfarande vid omstart.
- **Lokalt konto:** begär alltid autentisering i form av ett lösenord, som inte kan konfigureras i **Inställningar**

> [!NOTE]
> Inaktivitet timers stöds inte för närvarande, vilket innebär att **principen AllowIdleReturnWithoutPassword** endast respekteras när enheten hamnar i StandBy.

## <a name="additional-resources"></a>Ytterligare resurser

Läs mycket mer om skydd och autentisering av [användaridentiteter på Windows 10 säkerhets- och identitetsdokumentationen](https://docs.microsoft.com/windows/security/identity-protection/).

Lär dig mer om att konfigurera hybrididentitetsinfrastruktur genomgående i [dokumentationen om Azure Hybrid-identiteter.](https://docs.microsoft.com/azure/active-directory/hybrid/)
