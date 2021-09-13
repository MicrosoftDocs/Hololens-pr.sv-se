---
title: Hantera användaridentitet och inloggning för HoloLens
description: Lär dig hur du hanterar användaridentitet, stöd för flera användare, säkerhet, företagsautentisering och inloggning för HoloLens enheter.
keywords: HoloLens, user, account, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033258"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Hantera användaridentitet och inloggning för HoloLens

> [!NOTE]
> Den här artikeln är en teknisk referens för IT-proffs och tekniker. Om du letar efter HoloLens konfigurerade instruktioner läser du " Konfigurera din[HoloLens (första gen)](hololens1-start.md)" eller " Konfigurera[din HoloLens 2](hololens2-start.md)".

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>Låt oss prata om att konfigurera användaridentitet för HoloLens 2

Precis som Windows enheter HoloLens alltid under en användarkontext. Det finns alltid en användaridentitet. HoloLens hanterar identitet på nästan samma sätt som en Windows 10 enhet. När du loggar in under installationen skapas en användarprofil HoloLens som lagrar appar och data. Samma konto tillhandahåller också enkel inloggning för appar, till exempel Edge eller Dynamics 365 Remote Assist, med hjälp av API:Windows Account Manager. 

HoloLens stöder flera typer av användaridentiteter. Du kan välja någon av dessa tre kontotyper, men vi rekommenderar starkt Azure AD eftersom det är bäst för att hantera enheter. Endast Azure AD-konton stöder flera användare. 

| Identitetstyp | Konton per enhet | Autentiseringsalternativ |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure-provider för webbidentifiering</li><li>Azure Authenticator App</li><li>Biometrisk (Iris) &ndash; HoloLens 2 endast<sup>2</sup> </li><li>FIDO2-säkerhetsnyckel</li><li>&ndash;PIN-kod HoloLens (1 gen) krävs för HoloLens 2</li><li>Lösenord</li></ul> |
| [Microsoft-konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrisk (Iris) &ndash; HoloLens 2 endast</li><li>&ndash;PIN-kod HoloLens (1 gen) krävs för HoloLens 2</li><li>Lösenord</li></ul> |
| [Lokalt konto](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Lösenord |

Molnanslutna konton (Azure AD och MSA) erbjuder fler funktioner eftersom de kan använda Azure-tjänster.  
> [!IMPORTANT]
> 1 – Azure AD Premium krävs inte för att logga in på enheten. Det krävs dock för andra funktioner i en molnbaserad low touch-distribution, till exempel automatisk registrering och Autopilot.

> [!NOTE]
> 2 – En HoloLens 2-enhet har stöd för upp till 64 Azure AD-konton, men endast 31 av dessa konton kan registreras i Iris-autentisering. Detta överensstämmer med andra alternativ för [biometrisk autentisering för Windows Hello för företag.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

> [!IMPORTANT]
> 3 – Ett lokalt konto kan bara konfigureras på en enhet via ett etableringspaket under [OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup). Det kan inte läggas till senare i inställningsappen. Om du vill använda ett lokalt konto på en enhet som redan har ställts in måste du omsnedstreck [eller återställa enheten.](hololens-recovery.md)

## <a name="setting-up-users"></a>Konfigurera användare

Det finns två sätt att konfigurera en ny användare på HoloLens. Det vanligaste sättet är HoloLens oobe (out-of-box experience). Om du Azure Active Directory kan [andra användare logga in efter OOBE med](#setting-up-multi-user-support-azure-ad-only) sina Autentiseringsuppgifter för Azure AD. HoloLens enheter som först konfigureras med ett MSA-konto eller lokalt konto under OOBE stöder inte flera användare. Se Konfigurera din [HoloLens (första gen)](hololens1-start.md) eller [HoloLens 2.](hololens2-start.md)

Om du använder ett företags- eller organisationskonto för att logga in HoloLens, HoloLens registreras i organisationens IT-infrastruktur. Med den här registreringen kan IT-administratören konfigurera Mobile Enhetshantering (MDM) för att skicka grupprinciper till HoloLens.

Precis Windows på andra enheter skapar inloggning under installationen en användarprofil på enheten. Användarprofilen lagrar appar och data. Samma konto tillhandahåller också enkel inloggning för appar, till exempel Edge eller Microsoft Store, med hjälp av Windows Account Manager-API:er.

Som standard, precis som för Windows 10 enheter, måste du logga in igen när HoloLens startar om eller återupptas från vänteläge. Du kan använda Inställningar för att ändra det här beteendet, eller så kan beteendet styras av en grupprincip.

### <a name="linked-accounts"></a>Länkade konton

Precis som i Desktop-versionen av Windows kan du länka andra webbkontoautentiseringsuppgifter till ditt HoloLens konto. Sådana länkar gör det enklare att komma åt resurser i eller inom appar (till exempel Store) eller att kombinera åtkomst till personliga och arbetsresurser. När du har ansluter ett konto till enheten kan du ge behörighet att använda enheten i appar så att du inte behöver logga in på varje app individuellt.

Länkningskonton separerar inte användardata som skapats på enheten, till exempel bilder eller nedladdningar.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Konfigurera stöd för flera användare (endast Azure AD)

HoloLens har stöd för flera användare från samma Azure AD-klientorganisation. Om du vill använda den här funktionen måste du använda ett konto som tillhör din organisation för att konfigurera enheten. Därefter kan andra användare från samma klientorganisation logga in på enheten från inloggningsskärmen eller genom att trycka på användarpanelen på startpanelen. Endast en användare kan loggas in i taget. När en användare loggar in HoloLens loggar ut den tidigare användaren. 

>[!IMPORTANT]
> Den första användaren på enheten anses vara enhetens ägare, förutom när det gäller Azure AD-anslutning. Läs [mer om enhetsägare.](security-adminless-os.md#device-owner)

Alla användare kan använda de appar som är installerade på enheten. Varje användare har dock sina egna appdata och inställningar. Om du tar bort en app från enheten tas den bort för alla användare.  

Enheter som har ställts in med Azure AD-konton tillåter inte inloggning på enheten med ett Microsoft-konto. Alla efterföljande konton som används måste vara Azure AD-konton från samma klientorganisation som enheten. Du kan fortfarande [logga in med ett Microsoft-konto till appar](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) som stöder det (till exempel Microsoft Store). Om du vill ändra från att använda Azure AD-konton till Microsoft-konton för att logga in på enheten måste [du omsluta enheten](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (första generationen)** började stödja flera Azure AD-användare i [april 2018-uppdateringen för Windows 10](/windows/mixed-reality/release-notes-april-2018) som en del av [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Flera användare visas på inloggningsskärmen

Tidigare visade inloggningsskärmen endast den senast inloggade användaren och startpunkten "Annan användare". Vi har fått feedback från kunder om att det inte räcker om flera användare har loggat in på enheten. De var fortfarande nödvändiga för att skriva in sitt användarnamn på nytt osv.

Introducerades [i Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)  när du väljer Annan användare som finns till höger om fältet PIN-kodspost. Inloggningsskärmen visar flera användare med tidigare loggat in på enheten. På så sätt kan användarna välja sin användarprofil och sedan logga in med sina Windows Hello autentiseringsuppgifter. En ny användare kan också läggas till på enheten från den här **sidan med andra** användare via knappen Lägg **till** konto.

I menyn **Andra användare** visar knappen Andra **användare** den senaste användaren som loggat in på enheten. Välj den här knappen för att återgå till inloggningsskärmen för den här användaren.

![Inloggningsskärmen är standard.](./images/multiusers1.jpg)

<br>

![Inloggningsskärmen för andra användare.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Ta bort användare

Du kan ta bort en användare från enheten genom att gå **till Inställningar**  >  **Konton**  >  **Andra personer**. Den här åtgärden återtar också utrymme genom att ta bort alla användarens appdata från enheten.  

## <a name="using-single-sign-on-within-an-app"></a>Använda enkel inloggning i en app

Som apputvecklare kan du dra nytta av länkade identiteter på HoloLens med hjälp av [API:erna för Windows Account Manager](/uwp/api/Windows.Security.Authentication.Web.Core), precis som på andra Windows-enheter. Vissa kodexempel för dessa API:er finns på GitHub: [Web account management sample](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Alla kontoavbrott som kan uppstå, till exempel att begära användarmedgivande för kontoinformation, tvåfaktorautentisering och så vidare, måste hanteras när appen begär en autentiseringstoken.

Om din app kräver en viss kontotyp som inte har länkats tidigare kan din app be systemet att uppmana användaren att lägga till en. Den här begäran utlöser fönstret kontoinställningar för att starta som ett modalt underkonto till din app. För 2D-appar återges det här fönstret direkt över mitten av din app. För Unity-appar tar den här begäran kort användaren ut från din holografiska app för att återge det underordnade fönstret. Information om hur du anpassar kommandona och åtgärderna i det här fönstret finns [i WebAccountCommand Class](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Företagsautentisering och annan autentisering

Om din app använder andra typer av autentisering, till exempel NTLM, Basic eller Kerberos, kan du använda [Windows-autentiseringsgränssnittet](/uwp/api/Windows.Security.Credentials.UI) för att samla in, bearbeta och lagra användarens autentiseringsuppgifter. Användarupplevelsen för att samla in dessa autentiseringsuppgifter liknar andra avbrott i molndrivna konton och visas som en underordnad app ovanpå din 2D-app eller pausar en Unity-app en kort stund för att visa användargränssnittet.

## <a name="deprecated-apis"></a>Inaktuella API:er

Ett sätt som utveckling för HoloLens skiljer sig från att utveckla för Desktop är att [ONLINEIDAuthenticator-API:et](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) inte stöds fullt ut. Även om API:et returnerar en token om det primära kontot är i gott anseende, så visar inte avbrott som de som beskrivs i den här artikeln något användargränssnitt för användaren och kan inte autentisera kontot korrekt.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Stöds Windows Hello for Business på HoloLens (första gen)?

Windows Hello for Business (som stöder användning av en PIN-kod för att logga in) stöds för HoloLens (första gen). Så här tillåter Windows Hello pin-kod för företag-inloggning HoloLens:

1. Enheten HoloLens måste hanteras [av MDM](hololens-enroll-mdm.md).
1. Du måste aktivera Windows Hello för företag för enheten. ([Se anvisningarna för Microsoft Intune.](/intune/windows-hello))
1. På HoloLens kan användaren sedan använda **inloggningsalternativen Inställningar** Lägg till  >  **PIN-kod** för att konfigurera en  >   PIN-kod.

> [!NOTE]
> Användare som loggar in med en Microsoft-konto kan också konfigurera en PIN-kod **Inställningar**  >  **inloggningsalternativen** Lägg  >  **till PIN-kod.** Den här PIN-koden [är associerad Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), i stället för Windows Hello för [företag](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Hur implementeras biometrisk Iris-autentisering HoloLens 2?

HoloLens 2 stöder Iris-autentisering. Iris är baserad på Windows Hello och stöds för användning av både Azure Active Directory- och Microsoft-konton. Iris implementeras på samma sätt som andra Windows Hello och uppnår [biometrisäkerhet PÅ 1/100 000.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)

Mer information [finns i biometriska krav Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) specifikationer. Läs mer om [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) och [Windows Hello för företag](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="where-is-iris-biometric-information-stored"></a>Var lagras biometrisk Iris-information?

Biometrisk Iris-information lagras lokalt på varje HoloLens [enligt Windows Hello specifikationer](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Den delas inte och skyddas av två lager med kryptering. Det är inte tillgängligt för andra användare, inte ens en administratör, eftersom det inte finns något administratörskonto på en HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Måste jag använda Iris-autentisering?
Nej, du kan hoppa över det här steget under installationen. 

![Konfigurera Iris.](./images/setup-iris.png)

HoloLens 2 innehåller många olika alternativ för autentisering, inklusive FIDO2-säkerhetsnycklar.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Kan Iris-information tas bort från HoloLens?
Ja, du kan ta bort den manuellt i Inställningar.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hur påverkar kontotypen inloggningsbeteendet?

Om du tillämpar principer för inloggning respekteras alltid principen. Om ingen princip för inloggning tillämpas är dessa standardbeteenden för varje kontotyp:

- **Azure AD:** frågar efter autentisering som standard och kan konfigureras **av Inställningar** inte längre fråga efter autentisering.
- **Microsoft-konto:** Låsbeteendet skiljer sig åt så att automatisk upplåsning tillåts, men inloggningsautentisering krävs fortfarande vid omstart.
- **Lokalt konto:** begär alltid autentisering i form av ett lösenord som inte kan konfigureras i **Inställningar**

> [!NOTE]
> Inaktivitet timers stöds inte för närvarande, vilket innebär att **principen AllowIdleReturnWithoutPassword** endast respekteras när enheten hamnar i StandBy.

## <a name="additional-resources"></a>Ytterligare resurser

Läs mycket mer om skydd och autentisering av [användaridentiteter på Windows 10 säkerhets- och identitetsdokumentation.](/windows/security/identity-protection/)

Lär dig mer om att konfigurera hybrididentitetsinfrastruktur genomgående i [dokumentationen om Azure Hybrid-identiteter.](/azure/active-directory/hybrid/)