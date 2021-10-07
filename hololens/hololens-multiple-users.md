---
title: Dela din HoloLens med flera personer
description: Du kan konfigurera HoloLens ska delas av flera Azure Active Directory eller av flera användare som använder ett enda konto.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600737"
---
# <a name="share-your-hololens-with-multiple-people"></a>Dela din HoloLens med flera personer

## <a name="overview"></a>Översikt

Företag investerar ofta i många HoloLens enheter. Hur du använder HoloLens är flexibelt över hela linjen, beroende på dina enskilda krav. Här är ett exempel på några upplevelser för flera användare:

- En vagnpark med HoloLens 2 enheter konfigureras via Windows Autopilot för HoloLens 2, med en konsekvent portfölj med företagsprogram på varje enhet. Du har skapat några olika profiler för helskärmsläge med olika Azure AD-grupper som mål. Varje användare loggar in på HoloLens FIDO2-nycklar och loggar in på sitt eget Azure AD-konto och får en skräddarsydd upplevelse.
- En oberoende programvaruleverantör (ISV) hyr ut HoloLens 2 enheter med D365 Remote Assist och deras affärsprogram (LOB) till en kunds företag. Dessa enheter är konfigurerade för informationsdatorer som endast innehåller deras LOB-app och Remote Assist, och delas mellan flera slutanvändare. WDAC används för att Inställningar program Microsoft Edge startar. I uthyrningen ingår ett USB-C-batteripaket som ger enheterna full laddning under flera skift.
- En slutanvändare på ett företag försöker göra justeringar i Bluetooth på enheten så att de kan ansluta en ny enhet, men principen Sidsynlighet Inställningar har aktiverats för att begränsa sidan Enheter från att visas. De har fortfarande åtkomst till andra sidor efter behov, till exempel Wi-Fi så att de kan använda Fjärrhjälp på flera platser med samma HoloLens.

## <a name="best-practices"></a>Bästa praxis

När du planerar att dela dina enheter finns det flera överväganden för att optimera din enhetsmiljö baserat på dina affärsbehov.

- [Identitet och Autentisering](#identity-and-authentication)
- [Enhetshantering](#device-management)
- [Avancerad enhetshantering – helskärmsläge och WDAC](#advanced-device-management---kiosk-and-wdac)
- [Fysisk hantering](#physical-management)

### <a name="identity-and-authentication"></a>[Identitet och Autentisering](hololens-identity.md)

Om du planerar att ha flera konton på en enhet har du Azure AD-konton med alla autentiseringslägen. Dessa autentiseringsmetoder baseras på [Windows Hello](/windows-hardware/design/device-experiences/windows-hello), inklusive Iris- och FIDO2-nycklar.

- FIDO 2-säkerhetsnycklar är utmärkta om du har flera enheter, många användare eller ständigt använder nya enheter.
- Om du har 10 eller färre användare är Iris en snabb lösning för att logga in användare som tidigare har loggat in på samma enhet.

### <a name="device-management"></a>[Enhetshantering](hololens-csp-policy-overview.md)

Om enheter delas mellan användare vill du förmodligen använda enhetsbegränsningar. Genom att använda enhetshantering kan du ange att vissa principer antingen ska göra det möjligt för användarna att använda enheten, hantera uppdateringar eller begränsa vad enheten kan göra. Vi rekommenderar att du granskar våra [vanliga enhetsbegränsningar](hololens-common-device-restrictions.md)och ser om dessa rekommendationer verkar passa din organisation. När du vet vilka principer du vill använda kan du tillämpa dem via [Microsofts Endpoint Manager (MDM)](hololens-mdm-configure.md) eller etableringspaket.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Avancerad enhetshantering – [helskärmsläge](hololens-kiosk.md) och [WDAC](windows-defender-application-control-wdac.md)

I vissa fall kanske du vill begränsa vilka program som kan användas av slutanvändarna. Du kan begränsa vilka appar som användarna ser på Start-menyn med [helskärmsläge](hololens-kiosk.md). Helskärmsläge kan konfigureras för att presentera olika startmenyer baserat på användare, Azure-grupper eller särskilda användartyper. sådan besökare eller exklusive enhetsägare. Du kan välja flera appar eller bara en enda app. Helskärmsläge för flera appar stoppar inte en app från att starta en annan, så om butiken eller en annan app är tillgänglig kan användarna fortfarande starta en annan app.

Du kan också helt stoppa start av appar eller tjänster som [använder Windows Defender programkontroll (WDAC) för](windows-defender-application-control-wdac.md) att begränsa appar. WDAC skiljer sig från helskärmsläge, eftersom det inte ändrar användargränssnittet för HoloLens utan i stället inte tillåter att en blockerad app startas.

[Sidsynlighet Inställningar](settings-uri-list.md) ett annat sätt att lägga till begränsningar för en enhet. Om du behöver ge användare åtkomst till vissa sidor i Inställningar-appen, men det är inte allt du kan använda Page Inställningar Visibility för att begränsa åtkomsten. Detta är användbart, till exempel om användarna behöver ändra Wi-Fi, men du inte vill att de ska komma åt sidan Konton.

### <a name="physical-management"></a>Fysisk hantering

När du delar enheten mellan flera användare finns det vissa fysiska överväganden.

- Se till att enheter debiteras mellan skift.
- Om en enhet krävs för ett skift och behöver hantera flera skift bör du överväga att använda ett externt batteri i början av ett skift medan enheten fortfarande har betydande avgifter enligt de hanterande [värmeriktningarna](hololens2-charging.md#managing-heat).
- När du lagrar enheter ska de vara anslutna till ett nätverk. Det här är det bästa sättet att säkerställa uppdateringar av operativsystem och appar.
- Fundera över hur du planerar [att rensa enheten](hololens2-maintenance.md) mellan användare.
- För en enhet med en enda delad användare ska du inte placera PIN-koden/lösenordet på sidan av enheten om du använder en delad PIN-kod/ett lösenord för en enskild användare.
- För flera enheter med en enda delad användare använder du olika PIN-koder/lösenord.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Dela med flera personer, var och en med sitt eget konto

Enskilda Azure Active Directory (Azure AD) är det bästa och säkraste användningsfallet för identiteter för HoloLens 2 användare. När du använder egna Azure AD-konton kan flera användare behålla sina egna användarinställningar och användardata på enheten. Endast en användare kan loggas in i taget. När en användare loggar in HoloLens den tidigare användaren.

Om du vill kontrollera att flera personer kan använda sina egna konton på HoloLens, följer du dessa steg för att konfigurera det:

1. När du [ställer in enheten väljer du](hololens2-start.md)Mitt arbete eller min skola äger **den** och loggar in med ett Azure AD-konto.
1. När du är klar med konfigurationen kontrollerar du att kontoinställningarna (Inställningar >-konton) innehåller **Andra användare**.

> [!NOTE]
> Om enheten inte har ställts in med ett Azure AD-konto måste den antingen återställas [eller omgrupperas](hololens-recovery.md) och konfigureras korrekt.

Varje användare HoloLens följande steg för att använda den:

1. Om en annan användare har använt enheten väljer du något av följande alternativ:
   - Tryck på strömknappen en gång för att gå till vänteläge och tryck sedan på strömknappen igen för att återgå till låsskärmen
   - Välj användarpanelen från Start-menyn **eller** välj logga ut från Power-menyn **för** att logga ut den aktuella användaren.

1. Använd dina autentiseringsuppgifter för Azure AD-kontot för att logga in på enheten.  
    - Om det är första gången du använder enheten uppmanas [](hololens-calibration.md) du att kalibrera HoloLens dina ögon.
    - Om du tidigare använde enheten:
        - [Windows Holographic, version 20H2, version 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) eller senare, justeras skärmen sömlöst för kvalitet och en bekväm tittarupplevelse.
        - Tidigare versioner behöver manuell kalibrering för att justeras efter dina ögon.

> [!TIP]
> Om en användare inte har loggat in på en enhet än kan du prova någon av följande två metoder för snabbare inloggning:
>
> - **FIDO 2-säkerhetsnyckel: Din** FIDO2-säkerhetsnyckel identifieras automatiskt och användaren behöver inte ange sina autentiseringsuppgifter eller använda MFA. Det här är den snabbaste metoden för att logga in på en ny enhet.
> - **Webbautentisering:** När du loggar in på en ny enhet kan du välja länken Logga in från en annan enhet som genererar en kod på 9 tecken som du kan använda på [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) för att antingen logga **in** som användare på enheten eller ange ditt användarnamn och lösenord med hjälp av ett tangentbord.

Om du vill se en lista över enhetsanvändare eller ta bort en användare från enheten går **du till Inställningar**  >  **Konton**  >  **Övriga användare**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Dela med flera personer, alla med samma konto

Flera användare kan också dela en HoloLens enhet när du använder ett enda användarkonto. Även om det är HoloLens att användarna loggar in på enheten med sina enskilda identiteter (Azure AD-konton), är detta inte ett alternativ i vissa organisationer.

Det finns två delade enhetsmetoder:

- **Flera slutanvändare som delar 1 enhet** – en HoloLens tilldelas till ett anvisat utrymme där alla medarbetare kan använda enheten. Det kan till exempel vara ett rent rum eller en operationssvit.

- **Flera slutanvändare delar flera enheter –** HoloLens enheter finns i ett delat lagringsutrymme där anställda kan använda vilken enhet som helst. Exempel är en oljerigg eller en bilhandlare/ett verkstäder.

När en ny användare sätter på enheten för första gången samtidigt som samma konto är inloggad uppmanas användaren att snabbt kalibrera och anpassa visningsupplevelsen. Enheten lagrar kalibreringsinformationen för att automatiskt optimera kvaliteten och bekvämligheten för varje användares tittarupplevelse. Användarna behöver inte kalibrera enheten igen.
