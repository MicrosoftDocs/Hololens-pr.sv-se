---
title: Konfigurera HoloLens som helskärmsläge
description: Lär dig att konfigurera och använda en kioskkonfiguration för att låsa apparna på HoloLens-enheter.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378836"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Konfigurera HoloLens som helskärmsläge

Du kan konfigurera en HoloLens-enhet så att den fungerar som en fast enhet, även kallad helskärmsenhet, genom att konfigurera enheten så att den körs i helskärmsläge. Helskärmsläge begränsar de program (eller användare) som är tillgängliga på enheten. Helskärmsläge är en praktisk funktion som du kan använda för att dedikera en HoloLens-enhet till företagsappar eller för att använda HoloLens-enheten i en appdemo.

Den här artikeln innehåller information om aspekter av kioskkonfiguration som är specifika för HoloLens-enheter. Allmän information om de olika typerna av Windows-baserade helskärmsdatorer och hur du konfigurerar dem finns i Konfigurera helskärmsdatorer och [digitala skyltar på Windows-skrivbordsversionerna.](https://docs.microsoft.com/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Helskärmsläge avgör vilka appar som är tillgängliga när en användare loggar in på enheten. Helskärmsläge är dock inte en säkerhetsmetod. Det stoppar inte en "tillåten" app från att öppna en annan app som inte är tillåten. För att blockera appar eller processer från att öppnas använder du [CSP Windows Defender för programkontroll (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) för att skapa lämpliga principer.
>
> Läs mer om Microsoft-tjänster för att ge användarna en avancerad säkerhetsnivå som HoloLens 2 använder. Läs mer om tillståndsseparation och [isolering – Defender-skydd.](security-state-separation-isolation.md#defender-protections) Eller lär dig hur du använder WDAC och Windows PowerShell för att tillåta eller blockera appar på [HoloLens 2-enheter med Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Du kan använda helskärmsläge i antingen en enskild app eller en konfiguration med flera appar, och du kan använda en av tre processer för att konfigurera och distribuera helskärmskonfigurationen.

> [!IMPORTANT]  
> Om du tar bort konfigurationen för flera appar tas de användarlåsningsprofiler som skapades av funktionen för tilldelad åtkomst bort. Men alla principändringar återställs inte. Om du vill återställa dessa principer måste du återställa enheten till fabriksinställningarna.

## <a name="plan-the-kiosk-deployment"></a>Planera distributionen av helskärmsläge

När du planerar din kiosk måste du kunna besvara följande frågor. Här är några beslut att tänka på när du läser den här sidan och några överväganden för dessa frågor.
1. **Vem kommer att använda din informationsdator och [vilken typ av konto](hololens-identity.md) kommer de att använda?** Det här är ett beslut som du förmodligen redan har gjort och bör inte justeras för din kiosk, men det påverkar hur helskärmsläge tilldelas senare.
1. **Behöver du antingen ha olika helskärmsläge per användare/grupp eller en helskärm som inte är aktiverad för vissa?** I så fall bör du skapa helskärmsläge via XML. 
1. **Hur många appar kommer att finnas i helskärmsläge?** Om du har fler än en app behöver du en helskärmsläge för flera appar. 
1. **Vilka appar kommer att finnas i helskärmsläge?** Använd vår lista över AUMID:er nedan för att lägga till In-Box appar utöver dina egna.
1. **Hur planerar du att distribuera helskärmsläge?** Om du registrerar en enhet i MDM föreslår vi att du använder MDM för att distribuera helskärmsläge. Om du inte använder MDM är distribution med etableringspaket tillgängligt.  

### <a name="kiosk-mode-requirements"></a>Krav för helskärmsläge

Du kan konfigurera alla HoloLens 2-enheter att använda helskärmsläge.

> [!IMPORTANT]
> Helskärmsläge är endast tillgängligt om enheten har Windows Holographic for Business. Alla HoloLens 2-enheter levereras Windows Holographic for Business och det finns inga andra utgåvor. Alla HoloLens 2-enheter kan köra helskärmsläge från lådan.
>
> HoloLens-enheter (1:a gen) måste uppgraderas både vad gäller OS-version och OS-utgåva. Här finns mer information om hur du uppdaterar en HoloLens (första gen) till [Windows Holographic for Business](hololens1-upgrade-enterprise.md) utgåva. Om du vill uppdatera en HoloLens-enhet (första generationens) för att använda helskärmsläge måste du först se till att enheten kör Windows 10, version 1803 eller en senare version. Om du har använt verktyget Återställning av Windows-enhet för att återställa din HoloLens-enhet (första generationen) till standardbygget, eller om du har installerat de senaste uppdateringarna, är enheten redo att konfigureras.

> [!IMPORTANT]  
> För att skydda enheter som körs i helskärmsläge kan du överväga att lägga till enhetshanteringsprinciper som stänger av funktioner som USB-anslutning. Kontrollera även inställningarna för uppdateringsringen för att se till att automatiska uppdateringar inte sker under arbetstid.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Välja mellan helskärmsläge för en app eller helskärmsläge för flera appar

En helskärmsenhet med en app startar den angivna appen när användaren loggar in på enheten. Den Start-menyn är inaktiverad, liksom Cortana. En HoloLens 2-enhet svarar inte på [gesten Start.](hololens2-basic-usage.md#start-gesture) En HoloLens-enhet (första generationen) svarar inte på [bloom-gesten.](hololens1-basic-usage.md) Eftersom endast en app kan köras kan användaren inte placera andra appar.

En helskärmsenhet med flera appar visar Start-menyn när användaren loggar in på enheten. Konfigurationen för helskärmsläge avgör vilka appar som är tillgängliga på Start-menyn. Du kan använda helskärmsläge för flera appar för att ge användarna en lätt att förstå genom att bara presentera de saker som de behöver använda och ta bort de saker som de inte behöver använda.

I följande tabell visas funktionerna i de olika helskärmslägena.

| &nbsp; |Start-menyn |Snabbåtgärder-menyn |Kamera och video |Miracast |Cortana |Inbyggda röstkommandon |
| --- | --- | --- | --- | --- | --- | --- | 
|Helskärmsläge för en app |Inaktiverad |Inaktiverad |Inaktiverad |Inaktiverad   |Inaktiverad |Aktiverad<sup>1</sup> |
|Helskärmsläge för flera appar |Enabled |Aktiverad<sup>2</sup> |Tillgänglig<sup>2</sup> |Tillgänglig<sup>2</sup> |Tillgänglig<sup>2, 3</sup>  |Aktiverad<sup>1</sup> |

> <sup>1</sup> Röstkommandon som är relaterade till inaktiverade funktioner fungerar inte.  
> <sup>2</sup> Mer information om hur du konfigurerar dessa funktioner finns i [Välj kioskappar.](#plan-kiosk-apps)  
> <sup>3</sup> Även om Cortana är inaktiverat aktiveras de inbyggda röstkommandona.

I följande tabell visas funktionerna för användarstöd i de olika helskärmslägena.

| &nbsp; |Användartyper som stöds | Automatisk inloggning | Flera åtkomstnivåer |
| --- | --- | --- | --- |
|Helskärmsläge för en app |Hanterat tjänstkonto (MSA) i Azure Active Directory (Azure AD) eller lokalt konto |Ja |Inga |
|Helskärmsläge för flera appar |Azure AD-konto |Inga |Ja |

Exempel på hur du använder dessa funktioner finns i följande tabell.

|Använd en helskärmsläge för en app för: |Använd helskärmsläge för flera appar för: |
| --- | --- |
|En enhet som endast kör en Dynamics 365-guide för nya medarbetare. |En enhet som kör både guider och fjärrhjälp för ett antal anställda. |
|En enhet som bara kör en anpassad app. |En enhet som fungerar som helskärmsläge för de flesta användare (som bara kör en anpassad app), men som fungerar som en standardenhet för en viss grupp användare. |

### <a name="plan-kiosk-apps"></a>Planera kioskappar

Allmän information om hur du väljer helskärmsappar finns i [Riktlinjer för att välja en app för tilldelad åtkomst (helskärmsläge).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Om du använder Windows Enhetsportalen för att konfigurera en helskärmsläge för en app väljer du appen under installationen.  

Om du använder ett MDM-system (Mobile Enhetshantering) eller ett konfigurationspaket för att konfigurera helskärmsläge använder du [CSP (AssignedAccess Configuration Service Provider)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) för att ange program. CSP:n [använder PROGRAManvändarmodell-ID:n (AUMID) för](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) att identifiera program. I följande tabell visas AUMID:er för vissa in-box-program som du kan använda i en helskärmsläge för flera appar.

> [!IMPORTANT]
> Helskärmsläge avgör vilka appar som är tillgängliga när en användare loggar in på enheten. Helskärmsläge är dock inte en säkerhetsmetod. Det stoppar inte en "tillåten" app från att öppna en annan app som inte är tillåten. Eftersom vi inte begränsar det här beteendet kan appar fortfarande startas från Edge, Utforskaren och Microsoft Store appar. Om det finns specifika appar som du inte vill ska startas från en kiosk använder du [CSP Windows Defender (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) för att skapa lämpliga principer. 
> 
> Dessutom kan Mixed Reality Start inte anges som en helskärmsapp.

<a id="aumids"></a>

|Appnamn |AUMID |
| --- | --- |
|3D-visningsprogram |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Enhetsväljare på HoloLens (första generationen) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Enhetsväljare på HoloLens 2 |Microsoft.Windows.DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365-guider |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Fjärrhjälp för Dynamics 365 |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|&nbsp;Feedbackhubb |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Utforskaren |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|E-post |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Gamla Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Ny Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filmer & TV |Microsoft.Video \_ 8wekyb3d8bbwe \! Microsoft.Video |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Foton |Microsoft.Windows.Photos \_ 8wekyb3d8bbwe \! App |
|Gamla inställningar |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nya inställningar |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tips |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Om du vill aktivera foto eller videoinspelning måste du aktivera kameraappen som en kioskapp.  
> <sup>2</sup> Tänk på följande när du aktiverar kameraappen:
> - Snabbåtgärder-menyn innehåller knapparna Foto och Video.  
> - Du bör också aktivera en app (till exempel Foton, E-post eller OneDrive) som kan interagera med eller hämta bilder.  
>  
> <sup>3</sup> Även om du inte aktiverar Cortana som en kioskapp aktiveras inbyggda röstkommandon. Kommandon som är relaterade till inaktiverade funktioner har dock ingen effekt.  
> <sup>4</sup> Du kan inte aktivera Miracast direkt. Aktivera Miracast som en kioskapp genom att aktivera appen Kamera och appen Enhetsväljare.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planera helskärmsprofiler för användare eller grupper

När du antingen skapar XML-filen eller använder Intunes användargränssnitt för att konfigurera en helskärmsläge måste du överväga vem som ska använda helskärmsläge. En helskärmskonfiguration kan begränsas till antingen ett enskilt konto eller Azure AD-grupper. 

Normalt är helskärmsläge aktiverat för antingen en användare eller användargrupp. Men om du planerar att skriva egna XML-helskärmsläge kan du överväga global tilldelad åtkomst, där helskärmsläge tillämpas på enhetsnivå oavsett identitet. Om detta tilltalar dig kan [du läsa mer om globalt tilldelade åtkomst-kiosker.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Om du skapar en XML-fil:
-   Du har många som skapar flera helskärmsprofiler och tilldelar var och en till olika användare/grupper. Till exempel en kiosk för din Azure AD-grupp som har många appar och en besökare som har flera app-kiosker med en enda app.
-   Kioskkonfigurationen kallas för ett **profil-ID och** har ett GUID.
-   Du tilldelar profilen i konfigurationsavsnittet genom att ange användartypen och använda samma GUID för **DefaultProfile-ID:t.**
- En XML-fil kan skapas men fortfarande tillämpas på en enhet via MDM genom att skapa en anpassad OMA URI-enhetskonfigurationsprofil och tillämpa den på HoloLens-enhetsgrupp med hjälp av URI-värdet: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Om du skapar en helskärmsläge i Intune.
-   Varje enhet kan bara ta emot en profil för helskärmsläge, annars skapas en konflikt och inga helskärmskonfigurationer alls visas. 
    -   Andra typer av profiler och principer, till exempel enhetsbegränsningar som inte är relaterade till kioskkonfigurationsprofilen, står inte i konflikt med kioskkonfigurationsprofilen.
-   Helskärmsläge aktiveras för alla användare som är en del av inloggningstypen Användare. Detta anges med en användare eller En Azure AD-grupp. 
-   När konfigurationen för helskärmsläge har angetts och inloggningstypen Användare **(användare** som kan logga in i helskärmsläge) och Appar har valts, måste enhetskonfigurationen fortfarande tilldelas till en grupp. Tilldelade grupper avgör vilka enheter som får enhetskonfigurationen för helskärmsläge, men interagerar inte med om helskärmsläge är aktiverat eller inte. 
    - En fullständig diskussion om effekterna av att tilldela konfigurationsprofiler i Intune finns i Tilldela användar- och [enhetsprofiler i Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Välj en distributionsmetod

Du kan välja någon av följande metoder för att distribuera kioskkonfigurationer:

- [Microsoft Intune eller annan MDM-tjänst (hantering av mobila enheter)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Etableringspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Enhetsportalen](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Eftersom den här metoden kräver att Utvecklarläge är aktiverat på enheten rekommenderar vi att du endast använder det i demonstrationer.

I följande tabell visas funktionerna och fördelarna med var och en av distributionsmetoderna.

| &nbsp; |Distribuera med hjälp av Windows Enhetsportalen |Distribuera med hjälp av ett etableringspaket |Distribuera med hjälp av MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Distribuera helskärmsläge för en app   | Ja           | Ja                  | Ja  |
|Distribuera helskärmsläge för flera appar    | Inga            | Ja                  | Ja  |
|Distribuera endast till lokala enheter | Ja           | Ja                  | Inga   |
|Distribuera med hjälp av utvecklarläge |Obligatorisk       | Krävs inte            | Krävs inte   |
|Distribuera med Azure Active Directory (Azure AD)  | Krävs inte            | Krävs inte                   | Obligatorisk  |
|Distribuera automatiskt      | Inga            | Inga                   | Ja  |
|Distributionshastighet            | Snabb       | Snabb                 | Långsam |
|Distribuera i stor skala | Rekommenderas inte    | Rekommenderas        | Rekommenderas |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Använd Microsoft Intune eller annan MDM för att konfigurera en helskärmsläge för en app eller flera appar

Följ dessa steg om du vill konfigurera helskärmsläge Microsoft Intune ett annat MDM-system.

1. [Förbered för att registrera enheterna](#mdmenroll).
1. [Skapa en kioskkonfigurationsprofil](#mdmprofile).
1. Konfigurera helskärmsläge.
   - [Konfigurera inställningarna för en helskärmsläge för en app.](#mdmconfigsingle)
   - [Konfigurera inställningarna för helskärmsläge för flera appar.](#mdmconfigmulti)
1. [Tilldela kioskkonfigurationsprofilen till en grupp](#mdmassign).
1. Distribuera enheterna.
   - [Distribuera en helskärmsläge för en app.](#mdmsingledeploy)
   - [Distribuera en helskärmsläge för flera appar.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, steg 1 &ndash; Förbered för att registrera enheterna

Du kan konfigurera MDM-systemet så att HoloLens-enheter registreras automatiskt när användaren loggar in eller att användarna registrerar enheter manuellt. Enheterna måste också vara anslutna till din Azure AD-domän och tilldelas till lämpliga grupper.

Mer information om hur du registrerar enheterna finns i [Registrera HoloLens i MDM-](hololens-enroll-mdm.md) och [Intune-registreringsmetoder för Windows-enheter.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, steg 2 Skapa &ndash; en kioskkonfigurationsprofil

1. Öppna [Azure-portalen](https://portal.azure.com/) och logga in på ditt Intune-administratör konto.
1. Välj **Microsoft Intune**  >  **Enhetskonfiguration – Profiler** Skapa  >  **profil.**
1. Ange ett profilnamn.
1. Välj **Plattform**  >  **Windows 10 och senare** och välj sedan **Profiltyp**  > **Enhetsbegränsningar.**
1. Välj **Konfigurera**  >  **helskärmsläge** och välj sedan något av följande:
   - Om du vill skapa en helskärmsläge för en app väljer **du Helskärmsläge**  >  **Helskärmsläge helskärmsläge för enstaka app.**
   - Om du vill skapa en helskärmsläge för flera appar väljer **du Helskärmsläge** För flera appar i  >  **helskärmsläge.**
1. Börja konfigurera helskärmsläge genom att välja Lägg **till**.

Nästa steg varierar beroende på vilken typ av helskärmsläge du vill använda. Om du vill ha mer information väljer du något av följande alternativ:  

- [Helskärmsläge för en app](#mdmconfigsingle)
- [Helskärmsläge för flera appar](#mdmconfigmulti)

Mer information om hur du skapar en profil för helskärmskonfiguration finns i Windows 10 och Windows Holographic for Business enhetsinställningar som ska köras som en dedikerad [helskärmsenhet med Intune.](https://docs.microsoft.com/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, steg 3 (enskild app) &ndash;  Konfigurera inställningarna för en helskärmsläge för en app

I det här avsnittet sammanfattas de inställningar som en helskärmsläge för en app kräver. Mer information finns i följande artiklar:

- Information om hur du konfigurerar en profil för helskärmskonfiguration i Intune finns i Så här konfigurerar du [helskärmsläge med Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Mer information om tillgängliga inställningar för helskärmsläge för enskilda appar i Intune finns i [Helskärmsläge för appar med en enda helskärm](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Information om andra MDM-tjänster finns i leverantörens dokumentation. Om du måste använda en anpassad XML-konfiguration för att konfigurera en helskärmsläge i MDM-tjänsten skapar du en [XML-fil som definierar helskärmskonfigurationen](#ppkioskconfig).

1. Välj **Användarinloggningstyp** Lokalt användarkonto och ange sedan användarnamnet för det lokala  >  kontot (enheten) eller Microsoft-kontot (MSA) som kan logga in i helskärmsläge.
   > [!NOTE]  
   > Användarkontotyper med **Automatisk inloggning** stöds inte på Windows Holographic for Business.
1. Välj **Programtyp**  >  **Store-app** och välj sedan en app i listan.

Nästa steg är att [tilldela](#mdmassign) profilen till en grupp.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, steg 3 (flera appar) &ndash; Konfigurera inställningarna för helskärmsläge för flera appar

I det här avsnittet sammanfattas de inställningar som krävs för helskärmsläge för flera appar. Mer detaljerad information finns i följande artiklar:

- Information om hur du konfigurerar en profil för helskärmskonfiguration i Intune finns i Så här konfigurerar du [helskärmsläge med Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Mer information om tillgängliga inställningar för helskärmsläge för flera appar i Intune finns i [Helskärmsläge för flera appar](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Information om andra MDM-tjänster finns i leverantörens dokumentation. Om du behöver använda en anpassad XML-konfiguration för att konfigurera en helskärmsläge i MDM-tjänsten skapar du en [XML-fil som definierar kioskkonfigurationen](#ppkioskconfig). Om du använder en XML-fil måste du ta med [Start-layouten.](#start-layout-for-hololens)  
- Du kan också använda en anpassad Start-layout med Intune eller andra MDM-tjänster. Mer information finns i [Start layout file for MDM (Intune and others) (Starta layoutfilen för MDM (med flera)](#start-layout-file-for-mdm-intune-and-others).

1. Välj **Mål Windows 10 enheter i S-läge**  >  **Nej.**  
>[!NOTE]  
> S-läge stöds inte i Windows Holographic for Business.

1. Välj **Användarinloggning skriv** Azure AD-användare eller grupp eller Användarinloggningstyp  >     >  **HoloLens-besökare** och lägg sedan till en eller flera användargrupper eller konton.  

   Endast användare som tillhör de grupper eller konton som du anger i **Användarinloggningstyp kan** använda helskärmsupplevelsen.

1. Välj en eller flera appar med hjälp av följande alternativ:
   - Om du vill lägga till en uppladdad verksamhetsrad app väljer du **Lägg till Store-app** och sedan den app som du vill använda.
   - Om du vill lägga till en app genom att ange dess AUMID väljer du Lägg till efter **AUMID** och anger sedan APPENS AUMID. [Se listan över tillgängliga AUMID:er](#aumids)

Nästa steg är att [tilldela](#mdmassign) profilen till en grupp.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, steg 4 &ndash; Tilldela kioskkonfigurationsprofilen till en grupp

Använd sidan **Tilldelningar i** kioskkonfigurationsprofilen för att ange var du vill att helskärmskonfigurationen ska distribueras. I det enklaste fallet tilldelar du kioskkonfigurationsprofilen till en grupp som ska innehålla HoloLens-enheten när enheten registreras i MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, steg 5 (enskild app) &ndash; Distribuera en helskärmsläge för en app

När du använder ett MDM-system kan du registrera enheten i MDM under OOBE. När OOBE är klart är det enkelt att logga in på enheten.

Följ dessa steg under OOBE:

1. Logga in med det konto som du angav i kioskkonfigurationsprofilen.
1. Registrera enheten. Kontrollera att enheten har lagts till i gruppen som kioskkonfigurationsprofilen är tilldelad till.
1. Vänta tills OOBE har avslutats, att Store-appen har laddats ned och installerats och att principerna ska tillämpas. Starta sedan om enheten.

Nästa gång du loggar in på enheten bör helskärmsappen startas automatiskt.

Om du inte ser konfigurationen för helskärmsläge nu kontrollerar [du tilldelningsstatusen](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, steg 5 (flera appar) Distribuera &ndash; ett helskärmsläge för flera appar

När du använder ett MDM-system kan du ansluta enheten till din Azure AD-klientorganisation och registrera enheten i MDM under OOBE. Om det är lämpligt anger du registreringsinformationen för användarna så att de har den tillgänglig under OOBE-processen.

> [!NOTE]  
> Om du har tilldelat kioskkonfigurationsprofilen till en grupp som innehåller användare kontrollerar du att ett av dessa användarkonton är det första kontot att logga in på enheten.

Följ dessa steg under OOBE:

1. Logga in med det konto som tillhör gruppen **Användarinloggningstyp.**
1. Registrera enheten.
1. Vänta tills alla appar som ingår i kioskkonfigurationsprofilen har laddats ned och installerats. Vänta också på att principer tillämpas.  
1. När OOBE är klart kan du installera ytterligare appar från Microsoft Store eller genom separat inläsning. [Obligatoriska appar](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) för den grupp som enheten tillhör installeras automatiskt.
1. Starta om enheten när installationen är klar.

Nästa gång du loggar in på enheten med ett konto som tillhör inloggningstypen Användare **ska** helskärmsappen startas automatiskt.

Om du inte ser konfigurationen för helskärmsläge just nu kontrollerar [du tilldelningsstatusen](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Använd ett etableringspaket för att konfigurera en helskärmsläge för en app eller flera appar

Följ dessa steg om du vill konfigurera helskärmsläge med hjälp av ett etableringspaket.

1. [Skapa en XML-fil som definierar helskärmskonfigurationen,](#ppkioskconfig), inklusive [startlayouten](#start-layout-for-hololens).
2. [Lägg till XML-filen i ett etableringspaket.](#ppconfigadd)
3. [Tillämpa etableringspaketet på HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Konfigurationspaket, steg 1 Skapa en &ndash; XML-fil för helskärmskonfiguration

Följ [de allmänna anvisningarna för att skapa en XML-fil för helskärmskonfiguration för Windows-skrivbordet,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)förutom följande:

- Inkludera inte klassiska Windows-program (Win32). HoloLens stöder inte dessa program.
- Använd [platshållaren Start layout XML](#start-layout-for-hololens) for HoloLens (XML för startlayout för HoloLens).
- Valfritt: Lägga till gäståtkomst till kioskkonfigurationen

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Valfritt: Lägga till gäståtkomst till kioskkonfigurationen

I avsnittet [ **Konfigurationer** i XML-filen kan](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)du konfigurera en särskild grupp med namnet **Besökare** så att gäster kan använda helskärmsläge. När helskärmsläge har konfigurerats för att stödja **besökargruppen** läggs alternativet **"** Gäst " till på inloggningssidan. **Gästkontot** kräver inget lösenord och alla data som är associerade med kontot tas bort när kontot loggar ut.

Om du vill aktivera **gästkontot** lägger du till följande kodfragment i XML-koden för kioskkonfigurationen:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Aktivera besökarlogg automatiskt

På skapar [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare:
- Både konfigurationerna AAD och Icke-ADD stöder besökarkonton som aktiveras för automatisk inloggning i helskärmsläge.

##### <a name="non-aad-configuration"></a>Icke-AAD-konfiguration

1. Skapa ett etableringspaket som:
    1. Konfigurerar körningsinställningar/AssignedAccess för att tillåta besökarkonton.
    1. Du kan också registrera enheten i MDM (Körningsinställningar/Arbetsplats/Registreringar) så att den kan hanteras senare.
    1. Skapa inte ett lokalt konto
2. [Tillämpa etableringspaketet](https://docs.microsoft.com/hololens/hololens-provisioning).

##### <a name="aad-configuration"></a>AAD-konfiguration

AAD-anslutna enheter som konfigurerats för helskärmsläge kan logga in på ett besökarkonto med en enda knapptryckning från inloggningsskärmen. När du har loggat in på besökarkontot frågar enheten inte om inloggning igen förrän besökaren uttryckligen loggas ut från Start-menyn eller enheten startas om.

Besökarinloggning automatiskt kan hanteras via anpassad [OMA-URI-princip:](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)

- URI-värde: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Policy |Beskrivning |Konfigurationer 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Tillåter att en besökare automatiskt kan logga in på en kiosk. | 1 (Ja), 0 (Nej, standard.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Startlayout för platshållare för HoloLens

Om du använder ett [konfigurationspaket för](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) att konfigurera en helskärmsläge för flera appar kräver proceduren en Start-layout. Anpassning av startlayout stöds inte i Windows Holographic for Business. Därför måste du använda platshållaren Startlayout.

> [!NOTE]  
> Eftersom helskärmsläge för en app startar helskärmsappen när en användare loggar in, använder den inte en Start-menyn och behöver inte ha en Start-layout.

> [!NOTE]  
> Om du använder [MDM för](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) att konfigurera en helskärmsläge för flera appar kan du välja att använda en Start-layout. Mer information finns i [Platshållarstartlayoutfil för MDM (Intune med flera).](#start-layout-file-for-mdm-intune-and-others)

För startlayouten lägger du till följande **StartLayout-avsnitt** i XML-filen för kiosketablering:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Platshållarstartlayoutfil för MDM (Intune och andra)

Spara följande exempel som en XML-fil. Du kan använda den här filen när du konfigurerar helskärmsläge för flera appar i Microsoft Intune (eller i en annan MDM-tjänst som tillhandahåller en profil för helskärmsläge).

> [!NOTE]
> Om du måste använda en anpassad inställning och fullständig XML-konfiguration för att konfigurera en helskärmsläge i MDM-tjänsten använder du [instruktionerna för startlayout](#start-layout-for-hololens)för ett etableringspaket .

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Ords. package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package

1. Öppna [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Välj **Avancerad etablering,** ange ett namn för projektet och välj sedan **Nästa.**
1. Välj **Windows 10 Holographic** och välj sedan **Nästa.**
1. Välj **Slutför**. Arbetsytan för ditt paket öppnas.
1. Välj **Körningsinställningar**  >  **TilldeladeÅtkomst till**  >  **MultiAppAssignedAccessInställningar.**
1. I mittenfönstret väljer du Bläddra för **att hitta** och välja XML-filen för kioskkonfigurationen som du skapade.

   ![Skärmbild av fältet MultiAppAssignedAccessSettings i Windows Configuration Designer](./images/multiappassignedaccesssettings.png)

1. **Valfritt**. (Om du vill tillämpa konfigurationspaketet efter den första installationen av enheten och det redan finns en administratörsanvändare tillgänglig på kioskenheten kan du hoppa över det här steget.) Välj **Körningsinställningar** &gt;  &gt; **Konton Användare** och skapa sedan ett användarkonto. Ange ett användarnamn och lösenord och välj sedan **UserGroup**  >  **Administrators**.  
  
     Med det här kontot kan du visa etableringsstatus och loggar.  
1. **Valfritt**. (Om du redan har ett icke-administratörskonto på kioskenheten hoppar du över det här steget.) Välj **Körningsinställningar** &gt;  &gt; **Konton Användare** och skapa sedan ett lokalt användarkonto. Kontrollera att användarnamnet är samma som för det konto som du anger i xml-konfigurationsfilen. Välj **UserGroup**  >  **Standard Users**.
1. Välj **Arkiv**  >  **Spara.**
1. Välj **Exportera**  >  **etableringspaket och** välj sedan ÄGARE  >  **IT-administratör.** Detta anger prioriteten för det här etableringspaketet högre än att etablera paket som tillämpas på den här enheten från andra källor.
1. Välj **Nästa**.
1. På sidan **Säkerhet för etableringspaket** väljer du ett säkerhetsalternativ.
   > [!IMPORTANT]  
   > Om du väljer **Aktivera paketsignering** måste du också välja ett giltigt certifikat som ska användas för att signera paketet. Det gör du genom att **välja** Bläddra och välja det certifikat som du vill använda för att signera paketet.
   
   > [!CAUTION]  
   > Välj inte Aktivera **paketkryptering.** På HoloLens-enheter gör den här inställningen att etableringen misslyckas.
1. Välj **Nästa**.
1. Ange den utdataplats där du vill att etableringspaketet ska gå när det har skapats. Som standard använder Windows Configuration Designer projektmappen som utdataplats. Om du vill ändra utdataplatsen väljer du **Bläddra**. När du är klar väljer du **Nästa.**
1. Välj **Skapa** för att börja skapa paketet. Etableringspaketet tar inte lång tid att bygga. Byggsidan visar projektinformationen och förloppsfältet visar byggstatus.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Etableringspaket, steg 3 &ndash; Tillämpa etableringspaketet på HoloLens

Artikeln "Konfigurera HoloLens med hjälp av ett konfigurationspaket" innehåller detaljerade anvisningar för hur du tillämpar konfigurationspaketet under följande omständigheter:

- Du kan börja [med att tillämpa ett konfigurationspaket på HoloLens under installationen](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Du kan också [använda ett konfigurationspaket för HoloLens efter installationen.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Använd Windows Enhetsportalen för att konfigurera en helskärmsläge för en app

Följ dessa steg om du vill konfigurera helskärmsläge Windows Enhetsportalen med hjälp av Windows Enhetsportalen helskärmsläge.

1. [Konfigurera HoloLens-enheten så att den använder Windows Enhetsportalen](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Den Enhetsportalen är en webbserver på din HoloLens som du kan ansluta till från en webbläsare på datorn.

    > [!CAUTION]
    > När du ställer in HoloLens för att Enhetsportalen måste du aktivera Utvecklarläge på enheten. Utvecklarläge på en enhet som har Windows Holographic for Business kan du läsa in appar på sidan. Den här inställningen medför dock en risk att en användare kan installera appar som inte har certifierats av Microsoft Store. Administratörer kan blockera möjligheten att aktivera utvecklarläge med hjälp av inställningen **ApplicationManagement/AllowDeveloper Unlock** i [CSP-princip.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Läs mer om Utvecklarläge.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Anslut till HoloLens via [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) eller USB på en [dator.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Gör något av följande:
   - Om du ansluter till Windows Enhetsportalen första gången skapar du [ett användarnamn och lösenord](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Ange det användarnamn och lösenord som du tidigare konfigurerade.

    > [!TIP]
    > Om du ser ett certifikatfel i webbläsaren följer du dessa [felsökningssteg.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. I Windows Enhetsportalen **helskärmsläge**.

1. Välj **Aktivera helskärmsläge,** välj en app som ska köras när enheten startar och välj sedan **Spara.**

    ![Helskärmsläge](images/kiosk.png)
1. Starta om HoloLens. Om du fortfarande har Enhetsportalen sidan öppen kan du **välja** Starta om överst på sidan.

> [!NOTE]
> Helskärmsläge kan ställas in via Enhetsportalen:s REST API genom att göra en POST till /api/holographic/kioskmode/settings med en obligatorisk frågesträngsparameter ("kioskModeEnabled&quot; med värdet &quot;true&quot; eller &quot;false") och en valfri parameter ("startupApp" med ett värde för ett paketnamn). Tänk på att Enhetsportalen endast är avsett för utvecklare och inte ska aktiveras på enheter som inte är utvecklare. Den REST API kan komma att ändras i framtida uppdateringar/versioner.

## <a name="more-information"></a>Mer information

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Se hur du konfigurerar en kiosk med hjälp av ett konfigurationspaket.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Global tilldelad åtkomst – helskärmsläge
- Minskad identitetshantering för helskärmsläge genom att aktivera ny kioskmetod som tillämpar helskärmsläge på systemnivå.

Med den här nya funktionen kan IT-administratörer konfigurera en HoloLens 2-enhet för flera appar i helskärmsläge som gäller på systemnivå, saknar tillhörighet till någon identitet i systemet och gäller för alla som loggar in på enheten. Mer information om den här nya funktionen finns i dokumentationen om global tilldelad [HoloLens-åtkomst](hololens-global-assigned-access-kiosk.md) i helskärmsläge.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisk start av ett program i helskärmsläge för flera appar 
- Fokuserad upplevelse med automatisk appstart, vilket ytterligare ökar användargränssnitts- och appval som valts för helskärmslägesupplevelser.

Gäller endast helskärmsläge för flera appar och endast 1 app kan väljas för automatisk start med det markerade attributet nedan i Konfigurationen för tilldelad åtkomst. 

Programmet startas automatiskt när användaren loggar in. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Beteendeändringar i helskärmsläge för hantering av fel
Vid fel vid tillämpning av helskärmsläge visas följande:

- Före Windows Holographic visar version 20H2 – HoloLens alla program i Start-menyn.
- Windows Holographic, version 20H2 – om en enhet har en helskärmskonfiguration som är en kombination av både global tilldelad åtkomst och AAD-gruppmedlem tilldelad åtkomst, visas menyn "inget som visas på Start"-menyn om det inte går att fastställa AAD-gruppmedlemskap.

![Bild av vad helskärmsläge nu ser ut när det misslyckas.](images/hololens-kiosk-failure-behavior.png )


- Från och [med Windows Holographic, version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)söker helskärmsläge efter global tilldelad åtkomst innan en tom startmeny visas. Helskärmsupplevelsen går tillbaka till en global kioskkonfiguration (om sådan finns) vid fel i helskärmsläge för AAD-grupp.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cachelagra Azure AD-gruppmedlemskap för helskärmsläge offline

- Säkrare helskärmsläge genom att eliminera tillgängliga appar vid fel i helskärmsläge.
- Aktiverade helskärmsläge offline för användning med Azure AD-grupper i upp till 60 dagar.

Den här principen styr hur många dagar azure AD-gruppmedlemskapscache får användas för konfigurationer av tilldelad åtkomst som riktar in sig på Azure AD-grupper för inloggade användare. När det här principvärdet har angetts till ett värde som är större än 0 används cachen annars inte.  

Namn: URI-värdet AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min – 0 dagar  
Max – 60 dagar 

Steg för att använda den här principen korrekt: 
1. Skapa en enhetskonfigurationsprofil för helskärmsläge för Azure AD-grupper och tilldela den till HoloLens-enheter. 
1. Skapa en anpassad OMA URI-baserad enhetskonfiguration som anger det här principvärdet till önskat antal dagar (> 0) och tilldela det till HoloLens-enheter. 
    1. URI-värdet ska anges i textrutan OMA-URI som ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Värdet kan vara mellan min/max tillåtet.
1. Registrera HoloLens-enheter och kontrollera att båda konfigurationerna tillämpas på enheten. 
1. Låt Azure AD-användare 1 logga in när Internet är tillgängligt, när användaren loggar in och Azure AD-gruppmedlemskap har bekräftats, så skapas cacheminnet. 
1. Nu kan Azure AD-användare 1 ta HoloLens offline och använda det för helskärmsläge så länge principvärdet tillåter X antal dagar. 
1. Steg 4 och 5 kan upprepas för andra Azure AD-användare N. Nyckelpunkten här är att alla Azure AD-användare måste logga in på enheten via Internet så att vi minst en gång kan fastställa att de är medlemmar i Den Azure AD-grupp som helskärmskonfigurationen är riktad mot. 
 
> [!NOTE]
> Tills steg 4 utförs för en Azure AD-användare uppstår ett felbeteende som anges i "frånkopplade" miljöer. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML-kioskkodexempel för HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Helskärmsläge för flera appar som är riktade till en Azure AD-grupp. 
Den här helskärmsdatorn distribuerar en helskärm som för användare i Azure AD-gruppen har ett aktiverat helskärmsläge som innehåller de tre apparna: Inställningar, Fjärrhjälp och Feedbackhubben. Om du vill ändra det här exemplet så att det används omedelbart måste du ändra det GUID som är markerat nedan så att det matchar en egen Azure AD-grupp. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Flera appar i helskärmsläge för Azure AD-konto.
Den här helskärmsdatorn distribuerar en helskärmsläge för en enskild användare. Den har ett aktiverat helskärmsläge som innehåller de tre apparna: Inställningar, Fjärrhjälp och Feedbackhubben. Om du vill ändra det här exemplet så att det används omedelbart måste du ändra kontot som är markerat nedan så att det matchar ett eget Azure AD-konto. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

