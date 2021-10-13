---
title: Samla in och använda diagnostikinformation från HoloLens enheter
description: Lär dig hur du samlar in, använder och behåller diagnostikinformation från HoloLens enheter.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924409"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Samla in och använda diagnostikinformation från HoloLens enheter

HoloLens användare och administratörer kan välja mellan fyra olika metoder för att samla in diagnostikinformation från HoloLens:

- Feedbackhubben app
- CSP för diagnostiklogg
- Inställningar app
- Offlinediagnostik

> [!IMPORTANT]  
> Diagnostikloggar för enheter innehåller personligt identifierbar information (PII), till exempel om vilka processer eller program som användaren startar under typiska åtgärder. När flera användare delar en HoloLens-enhet (till exempel om användarna loggar in på samma enhet med hjälp av olika Microsoft Azure Active Directory-konton (Azure AD) kan diagnostikloggarna innehålla PII-information som gäller för flera användare. Mer information finns i [Microsofts sekretesspolicy.](https://privacy.microsoft.com/privacystatement)

I följande tabell jämförs olika insamlingsmetoder. Metodnamnen länkar till mer detaljerad information i avsnitten som följer tabellen.

|Metod |Förutsättningar |Dataplatser |Dataåtkomst och -användning |Datakvarhållning |
| --- | --- | --- | --- | --- |
|[Feedbackhubben](#feedback-hub) |Nätverk och Internetanslutning<br /><br />Feedbackhubben app<br /><br />Behörighet att ladda upp filer till Microsoft-molnet |Microsoft-moln<br /><br />HoloLens enhet (valfritt) |Användaren begär hjälp, godkänner användningsvillkoren och laddar upp data<br /><br />Microsoft-anställda ser data i enlighet med användningsvillkoren |Data i molnet bevaras under den period som definieras av Nästa generations sekretess (NGP). Sedan tas data bort automatiskt.<br /><br />Data på enheten kan när som helst tas bort av en användare som har behörighet **som enhetsägare** **eller** administratör. |
|[Inställningar Felsökaren](#settings-troubleshooter) |Inställningar app |HoloLens-enhet<br /><br />Ansluten dator (valfritt) |Användaren lagrar data och endast användaren kommer åt data (såvida inte användaren specifikt delar data med en annan användare). |Data sparas på enheten tills användaren tar bort dem.* |
|[CSP för diagnostiklogg](#diagnosticlog-csp) |Nätverksanslutning<br /><br />MDM-miljö som stöder CSP:n DiagnosticLog |Administratören konfigurerar lagringsplatser |I den hanterade miljön samtycker användaren implicit till administratörsåtkomst till data.<br /><br />Administratören konfigurerar åtkomstroller och behörigheter. | Data lagras i molnlagringen och administratören konfigurerar kvarhållningsprincipen. |
|[Offlinediagnostik](#offline-diagnostics) |Enhetskonfiguration:<ul><li>Påslagen och ansluten till datorn</li><li>Ström- och volymknappar fungerar</li></ul> |HoloLens-enhet<br /><br />Ansluten dator |Användaren lagrar data och endast användaren kommer åt data (såvida inte användaren specifikt delar data med en annan användare). |Data sparas på enheten tills användaren tar bort dem. |

* Slutanvändaren ansvarar för att dela loggarna på ett ansvarsfullt sätt med någon annan. De här filerna är främst användbara när du kontaktar kundtjänst och support.  

## <a name="feedback-hub"></a>Feedbackhubben

En HoloLens kan använda Microsoft Feedbackhubben-skrivbordsappen för att skicka diagnostikinformation till Microsoft Support. Mer information och fullständiga instruktioner finns i [Ge oss feedback.](hololens-feedback.md)  

> [!NOTE]  
> **Kommersiella användare eller företagsanvändare:** Om du använder Feedbackhubben-appen för att rapportera ett problem som rör MDM, etablering eller någon annan aspekt av enhetshantering ändrar du appkategorin till **Kategorin**  >  **Företagshanteringsenhet.**

>[!IMPORTANT]
> För att tillhandahålla bästa möjliga data för att åtgärda problem rekommenderar vi starkt att du ställer in enhetens telemetri på **Valfri**. Du kan ange det här värdet under OoBE (Out-of-Box Experience) eller med hjälp av Inställningar appen.  Om du vill göra detta med Inställningar väljer du **Starta > Inställningar > Sekretess > Appdiagnostik > På**.

### <a name="prerequisites"></a>Förutsättningar

- Enheten är ansluten till ett nätverk.
- Appen Feedbackhubben är tillgänglig på användarens stationära dator och användaren kan ladda upp filer till Microsoft-molnet.

### <a name="data-locations-access-and-retention"></a>Dataplatser, åtkomst och kvarhållning

Genom att godkänna användningsvillkoren för Feedbackhubben samtycker användaren uttryckligen till lagring och användning av data (enligt definitionen i det avtalet).

I Feedbackhubben finns två platser där användaren kan lagra diagnostikinformation:

- **Microsoft-molnet**. Data som användaren laddar upp med hjälp av Feedbackhubben-appen lagras under det antal dagar som är konsekvent med kraven för nästa generations sekretess (NGP). Microsoft-anställda kan använda ett NGP-kompatibelt visningsprogram för att komma åt informationen under den här perioden.

   > [!NOTE]  
   > Dessa krav gäller för data i alla Feedbackhubben kategorier.

- **Enheten HoloLens**. När du skapar en rapport Feedbackhubben kan användaren välja Spara en lokal kopia av diagnostik och bifogade filer som skapats när **de ger feedback.** Om användaren väljer det här alternativet Feedbackhubben en kopia av diagnostikinformationen på den HoloLens enheten. Den här informationen är fortfarande tillgänglig för användaren (eller någon som använder det kontot för att logga in på HoloLens). Om du vill ta bort den här informationen måste en **användare ha enhetsägare** **eller administratörsbehörighet** på enheten. En användare som har rätt behörigheter kan logga in på Feedbackhubben, **välja Inställningar**  >  **Visa diagnostikloggar** och ta bort informationen.

## <a name="settings-troubleshooter"></a>Inställningar Felsökaren

En HoloLens kan använda appen **Inställningar** på enheten för att felsöka problem och samla in diagnostikinformation. Det gör du genom att följa dessa steg:

1. Öppna appen Inställningar och välj sidan **Felsök &**  >  **uppdateringssäkerhet.**
1. Välj lämpligt område och välj **Starta.**
1. Återskapa problemet.
1. När du har återskapat problemet återgår du till Inställningar och väljer **sedan Stoppa**.

En användare kan också konfigurera beteendet  för återställningsdiagnostik från Inställningar appen. Gå till **sidan Sekretess -> felsökning för** att konfigurera den här inställningen.
> [!NOTE]
> Om MDM-principen har konfigurerats för enheten kan användaren inte åsidosätta det beteendet.

### <a name="os-update-troubleshooter"></a>Felsökare för os-uppdatering

På versioner [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare:
- Förutom de tidigare felsökarna i Inställningar-appen har en ny felsökare lagts till med det nya Inställningar för OS-uppdateringar. Gå till **Inställningar -> Update & Security -> Troubleshoot -> Windows Update** och välj **Starta**. På så sätt kan du samla in spårningar samtidigt som du återskapar problemet med OS-uppdateringar för att få bättre hjälp med felsökning med DIN IT eller support.

### <a name="prerequisites"></a>Förutsättningar

- Appen **Inställningar** installeras på enheten och är tillgänglig för användaren.

### <a name="data-locations-access-and-retention"></a>Dataplatser, åtkomst och kvarhållning

Eftersom användaren startar datainsamlingen godkänner användaren implicit lagringen av diagnostikinformationen. Endast användaren, eller vem som helst som användaren delar data med, kan komma åt data.

Diagnostikinformationen lagras på enheten. Om enheten är ansluten till användarens dator finns informationen även på datorn i följande fil:

> Den här \\ \<*HoloLens device name*> \\ datorns interna Storage \\ Documents \\ Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> I den här sökvägen och namnet representerar namnet på HoloLens och representerar datum och tid \<*HoloLens device name*> \<*ddmmyyhhmmss*> då filen skapades.

Diagnostikinformationen finns kvar på dessa platser tills användaren tar bort den.

### <a name="view-diagnostic-report"></a>Visa diagnostikrapport

Om du vill visa MDM-diagnostik på HoloLens 2 väljer du din WiFi-ikon och går **sedan till Inställningar** Åtkomst till arbets- eller skolkonton och väljer Exportera dina  ->    >   **hanteringsloggar.** HoloLens skickar loggfilerna till ditt konto och visar deras plats på din stationära dator.

## <a name="diagnosticlog-csp"></a>CSP för diagnostiklogg

I en MDM-miljö (Mobile Enhetshantering) kan IT-administratören använda [CSP:n DiagnosticLog](/windows/client-management/mdm/diagnosticlog-csp) för att konfigurera diagnostikinställningar på registrerade HoloLens enheter. IT-administratören kan konfigurera dessa inställningar för att samla in loggar från registrerade enheter.

Mer information:
- [Samla in diagnostik från en Windows enhet](/mem/intune/remote-actions/collect-diagnostics)
- [Offentlig förhandsversion av Intune – Windows 10 enhetsdiagnostik](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Förutsättningar

- Enheten är ansluten till ett nätverk.
- Enheten har registrerats i en MDM-miljö som stöder CSP:n DiagnosticLog.

### <a name="data-locations-access-and-retention"></a>Dataplatser, åtkomst och kvarhållning

Eftersom enheten är en del av den hanterade miljön samtycker användaren implicit till administrativ åtkomst till diagnostikinformation.

IT-administratören använder CSP:en DiagnosticLog för att konfigurera principer för datalagring, kvarhållning och åtkomst, inklusive de principer som styr följande:

- Molninfrastrukturen som lagrar diagnostikinformationen.
- Kvarhållningsperioden för diagnostikinformationen.
- Behörigheter som styr åtkomsten till diagnostikinformationen.

## <a name="offline-diagnostics"></a>Offlinediagnostik

I situationer där enheten inte kan samla in diagnostik via Feedbackhubben eller Inställningar-felsökaren kan du samla in diagnostik manuellt. Ett scenario där detta är nödvändigt är när enheten inte kan ansluta till Wi-Fi eller om du inte kan komma åt andra metoder som nämns ovan. Diagnostiken samlar in kraschdumpar och loggar från enheten som hjälper en Microsoft-supporttekniker att isolera problem.

Detta fungerar när enheten visas i ett Utforskaren när den har anslutits till en dator via en USB-kabel.

> [!NOTE]
> Generering och hantering av offlinediagnostik styrs på olika sätt beroende på operativsystemversion. Tidigare styrdes den av telemetriinställningen, men styrs nu direkt via MDM-principen. Om den är inaktiverad via antingen inställning eller MDM-princip kan diagnostikloggar inte samlas in med den här mekanismen.

Beteende före [Windows Holographic, version 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Offlinediagnostik aktiveras endast när användaren antingen går via OOBE eller [System\AllowTelemetry-principvärdet](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) är inställt på Fullständig (Grundläggande är standardvärdet på HoloLens). 
- Om du vill inaktivera offlinediagnostik **går Inställningar till sidan > Sekretess** och väljer **Grundläggande** i **Diagnostikdata.** I byggen där offlinediagnostik är beroende av telemetriinställningen påverkar det bara om några loggar samlas in eller inte. Det påverkar inte vilka filer som samlas in.
- Om enheten är låst visas inte loggar.

På versioner [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) och senare:
- När Återställningsdiagnostik är aktiverat styrs av en specifik MDM-princip med motsvarande inställning [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Om enheten är låst visas inte loggar.

Titta på den här videon om du vill veta mer.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Följ dessa steg för att samla in diagnostik:

1.  Anslut enheten med en USB-kabel till datorn.

2.  I Utforskaren datorn navigerar du till **"This PC \<hololens-device> \Internal Storage"**(Den här datorn \Intern Storage).

3.  Om **mappen Internal Storage** inte visas väntar enheten på att en användare ska logga in. Logga in eller strömförser enheten genom att hålla strömknappen nere i 10 sekunder.

4.  Tryck på och släpp omedelbart **knapparna Power + Volume Down** tillsammans.

5.  Vänta en minut tills enheten förbereder zip-arkiven. (En tillfällig fil med namnet HololensDiagnostics.temp kan bli synlig medan enheten genererar ZIP-arkiven. Kom inte åt eller spara filen. När processen är klar ersätts den av zip-arkiven.)

6.  Uppdatera Utforskaren och navigera till **mappen \Documents.**

7.  Kopiera ZIP-diagnostikfilerna och dela dem med Microsofts supportteam.

> [!NOTE]
> Vissa AV ZIP-diagnostikfilerna kan innehålla PII.

### <a name="offline-diagnostics-notifications"></a>Aviseringar om offlinediagnostik

- Introducerades [i Windows Holographic, version 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Detta är en uppdatering för en befintlig funktion som heter [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Tidigare fanns det ingen tydlig indikator för användarna att de utlöst diagnostikinsamlingen eller att den hade slutförts.
Det finns nu två Windows feedback för offlinediagnostik som nu har lagts till i Windows Insider-byggen. Den första är popup-meddelanden som visas för både när samlingen startar och slutförs. Dessa visas när användaren är inloggad och har visuella objekt.

![Popup-meddelande för insamling av loggar.](./images/logcollection1.jpg)

![Popup-meddelande när logginsamlingen är klar.](./images/logcollection2.jpg)

Eftersom användare ofta använder offlinediagnostik som reservlogginsamlingsmekanism för när de inte har åtkomst till en visning, inte kan logga in eller är kvar i OOBE, spelas även en ljudikon upp när loggar samlas in. Det här ljudet spelas upp utöver popup-meddelandet.

Den här nya funktionen aktiveras när enheten uppdateras och behöver inte aktiveras eller hanteras. Om denna nya feedback inte kan visas eller höras genereras fortfarande offlinediagnostik.

Med den här nyare feedbacken hoppas vi att det är enklare att samla in diagnostikdata och att du snabbare ska kunna felsöka dina problem.

### <a name="low-storage-log-collection-improvements"></a>Förbättringar av logginsamling med låg lagring

- Introducerades [i Windows Holographic, version 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

I scenarier där en enhet verkar ha ont om diskutrymme när diagnostikloggar samlas in, skapas ytterligare **en rapport medStorageDiagnostics.zip** namn. Tröskelvärdet för låg lagring bestäms automatiskt av Windows [lagrings sense](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visa avancerad diagnostikrapport i Inställningar på HoloLens

- Introducerades [i Windows Holographic, version 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

För hanterade enheter vid felsökning av beteende är det viktigt att bekräfta att en förväntad principkonfiguration tillämpas. Tidigare i den här nya funktionen behövde detta göras av enheten via MDM eller nära enheten efter export av MDM-diagnostikloggar som samlats in via **Inställningar** Accounts Access work or school och välja Exportera dina hanteringsloggar och visa dem på en närliggande  ->    >  dator. 

Nu kan MDM-diagnostiken visas på enheten med hjälp av Edge-webbläsaren. Om du vill visa MDM-diagnostikrapporten enklare går du till sidan Åtkomst till arbete eller skola och väljer **Visa avancerad diagnostikrapport.** Detta genererar och öppnar rapporten i ett nytt Edge-fönster.

![Visa avancerad diagnostikrapport i Inställningar app.](./images/view-advanced-diagnostic-report.jpg)
