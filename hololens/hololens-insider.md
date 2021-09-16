---
title: Insiderförhandsvisning för Microsoft HoloLens
description: Lär dig hur du kommer igång med Insider-byggen och ge värdefull feedback för vår nästa större operativsystemsuppdatering för HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: e3b067987fb339bc070fcb64ed01c28dee21ec35
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833547"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insiderförhandsvisning för Microsoft HoloLens

Välkommen till de senaste Insider Preview-versionerna för HoloLens! Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insiders versionsanteckningar

Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen. Nya byggen kommer att gå till dev- och betakanalerna för att få de senaste uppdateringarna. Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider-versionerna. Bli spänd och redo att blanda de här uppdateringarna i din verklighet.

Den här handlar om den förbättrade felsöknings- och enhetsrapporterna, vissa fasta buggar i helskärmsläge och certifikatvisaren, den utökade hanterbarhetsytan och den ökade uppdateringstillförlitligheten. En ny funktion i den här funktionsuppdateringen som kommer till HoloLens är vårt moving platform-läge. Kolla in alla nya fantastiska funktioner för HoloLens 2!

| Funktion                 | Beskrivning                | Användare eller scenario | Skapa introducerat |
|-------------------------|----------------------------|--------------|------------------|
| [Flytta plattformsläge](#moving-platform-mode) | Introducerar Moving Platform Mode-beta, som när den konfigureras möjliggör användning av HoloLens 2 på stora djur som upplever låg-dynamisk rörelse. | Alla | 20348.1411 |
| [PFX-filstöd för Certificate Manager](#pfx-file-support-for-certificate-manager) | Lägga till PFX-certifikat via Inställningar användargränssnitt | Slutanvändare | 20348.1405 |
| [Visa avancerad diagnostikrapport i Inställningar på HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visa MDM-diagnostikloggar på enheten | Felsökning | 20348.1405 |
| [Aviseringar om offlinediagnostik](#offline-diagnostics-notifications) | Bra feedback för logginsamling | Felsökning | 20348.1405 |
| [Förbättringar av logginsamling med låg lagring](#low-storage-log-collection-improvements) | Förbättringar av logginsamlingsscenarier i situationer med låg lagring. | Felsökning | 20348.1412 |
| [CSP-ändringar för HoloLens information](#csp-changes-for-reporting-hololens-details) | Nya CPP:er för att fråga efter data | IT-administratörer    | 20348.1403                 |
| [Princip för automatisk inloggning som styrs av CSP](#auto-login-policy-controlled-by-csp) | Används för att logga in ett konto automatiskt | IT-administratörer | 20348.1405 |
| [Förbättrad identifiering av omstart av uppdateringar och meddelanden](#improved-update-restart-detection-and-notifications) | Nya aktiverade principer och UX för uppdateringar. | IT-administratörer | 20348.1405 |
| [Smart Försök igen för appuppdateringar](#smart-retry-for-app-updates) | Gör att IT-administratörer kan schemalägga återförsök för att uppdatera appar. | IT-administratörer | 20348.1405 |
| [Använd endast privata Store-appar för Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurera Store-appen så att den endast visar appar från organisationen | IT-administratör | 20348.1408 |
| [Använda WDAC- och LOB-appar](#use-wdac-and-lob-apps) | Gör att IT-administratörer kan använda sina egna appar och fortfarande använda WDAC för att blockera andra appar. | IT-administratörer | 20348.1405 |
| [Korrigeringar och förbättringar](#fixes-and-improvements) | Korrigeringar och förbättringar för HoloLens. | Alla | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Checklista för INSIDER-funktioner för IT-administratörer

✔️ Konfigurera den nya [CSP:en](#auto-login-policy-controlled-by-csp) om du vill ange att ett enda Azure AD-konto ska logga in automatiskt. <br>
✔️ Om du vill konfigurera dina appar så att de försöker uppdatera automatiskt efter att det inte gick att uppdatera anger du den nya [CSP:en för smart återförsök.](#smart-retry-for-app-updates) <br>
✔️ Om du vill ha mer kontroll över OS-uppdateringar kan du läsa dessa nyligen [aktiverade uppdateringsprinciper.](#improved-update-restart-detection-and-notifications) <br>
✔️ Ange den här principen om du behöver göra din organisations appar tillgängliga i företagsbutiken via Microsoft Store, men bara vill tillåta åtkomst till din organisations appar och inte hela [butiken.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Om du vill veta det lediga lagringsutrymmet, SSID eller BSSID för dina HoloLens-enheter kan du läsa dessa [rapporterings-CPP:er](#csp-changes-for-reporting-hololens-details). <br>
✔️ Om du vill använda WDAC för att blockera appar eller processer från att starta, men även behöver använda dina egna slarvappar, kan du nu tillåta LOB i [wdac-principen](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Flytta plattformsläge

Från och **med Insider-versionen 20348.1411** har vi lagt till betastöd för spårning på plattformar med låg dynamisk rörelseflyttning på HoloLens 2. När du har installerat bygget och aktiverat Moving Platform Mode kommer du att kunna använda din HoloLens 2 i tidigare otillgängliga miljöer, till exempel stora skepp och stora djur. För närvarande är funktionen endast avsedd att aktivera dessa specifika plattformar som flyttas. Även om ingenting hindrar dig från att försöka använda funktionen i andra miljöer fokuserar funktionen på att lägga till stöd för dessa miljöer först.

Mer information om vad som stöds och hur du aktiverar den här nya funktionen finns [på sidan om rörliga plattformar.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Översikt för att prova moving platform mode (Flytta plattformsläge)

1. [Aktivera utvecklarläge och enhetsportal.](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Aktivera flytt av plattformsläge via enhetsportalen](hololens2-moving-platform.md#enabling-moving-platform-mode).
1. Ta enheten till din stora rörliga plattform och observera hur stabila hologram är.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-filstöd för Certificate Manager

Introducerades i Windows Insider version 20348.1405. Vi har lagt till stöd för Certifikathanteraren [för att](certificate-manager.md) nu använda .pfx-certifikat. När användarna navigerar **till Inställningar** Update & Security Certificates och väljer Installera ett certifikat har användargränssnittet nu stöd för  >    >  PFX-certifikatfilen. 
Användare kan importera PFX-certifikat, med privat nyckel, till användararkivet eller datorarkivet.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Översikt för att testa PFX-filer i Certificate Manager

1. Förbered PFX-filen.
1. Kopiera filen till enheten via en USB-C-kabel.
1. Öppna appen Inställningar och navigera till [Certifikathanteraren](certificate-manager.md) och tillämpa certifikatet.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visa avancerad diagnostikrapport i Inställningar på HoloLens

För hanterade enheter vid felsökning av beteende är det viktigt att bekräfta att en förväntad principkonfiguration tillämpas. Tidigare var den här nya funktionen tvungen att visa den här informationen av enheten via MDM eller nära enheten efter export av MDM-diagnostikloggar som samlats in via **Inställningar** Accounts Access work or school (Åtkomst till arbets- eller skolkonton) och välj Exportera dina hanteringsloggar och visa dem på en närliggande  ->    >  dator. 

Nu kan MDM-diagnostiken visas på enheten med hjälp av Edge-webbläsaren. Om du vill visa MDM-diagnostikrapporten enklare går du till sidan Åtkomst till arbete eller skola och väljer **Visa avancerad diagnostikrapport.** Detta genererar och öppnar rapporten i ett nytt Edge-fönster.

![Visa avancerad diagnostikrapport i Inställningar app.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Översikt för att testa den avancerade diagnostikrapporten

1. Öppna inställningsappen.
1. Gå till sidan Konton och klicka på den nya länken Exportera **dina hanteringsloggar.**
1. Visa avancerad information om enhetens konfigurationer.

### <a name="offline-diagnostics-notifications"></a>Aviseringar om offlinediagnostik

Detta är en uppdatering för en befintlig funktion som heter [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Tidigare fanns det ingen tydlig indikator för användarna att de utlöst diagnostikinsamlingen eller att den hade slutförts.
Nu har lagts Windows Insider-byggen, finns det två typer av feedback för offlinediagnostik. Den första är popup-meddelanden som visas för både när samlingen startar och slutförs. Dessa visas när användaren är inloggad och har visuella objekt.

![Popup-meddelande för insamling av loggar.](./images/logcollection1.jpg)

![Popup-meddelande när logginsamlingen är klar.](./images/logcollection2.jpg)

Eftersom användare ofta använder offlinediagnostik som reservlogginsamlingsmekanism för när de inte har åtkomst till en visning, inte kan logga in eller är kvar i OOBE, spelas även en ljudikon upp när loggar samlas in. Det här ljudet spelas upp utöver popup-meddelandet.

Den här nya funktionen aktiveras när enheten uppdateras och behöver inte aktiveras eller hanteras. Om denna nya feedback inte kan visas eller höras genereras fortfarande offlinediagnostik.

Med den här nyare feedbacken hoppas vi att det är enklare att samla in diagnostikdata och att du snabbare ska kunna felsöka dina problem.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Översikt för att testa diagnostikmeddelandena

1. Lås upp enheten och använd den.
1. Tryck på **tangentkombinationen** **Ström och Volym** ned för att samla in [offlinediagnostik.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Visa popup-meddelandena och hör ljudikoner för när enheten startar och slutför insamlingen av loggar.

### <a name="low-storage-log-collection-improvements"></a>Förbättringar av logginsamling med låg lagring

I scenarier där en enhet verkar ha ont om diskutrymme när diagnostikloggar samlas in skapas ytterligare **en rapport medStorageDiagnostics.zip** namn. Tröskelvärdet för låg lagring bestäms automatiskt av Windows [lagrings sense](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Översikt för att testa de låga lagringsförbättringarna

1. Fyll upp enhetens lagringsutrymme.
1. Tryck på **tangentkombinationen** **Ström och Volym** ned för att samla in [offlinediagnostik.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Observera att det finns en ny fil i loggsamlingen som lagras i mappen Dokument i HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-ändringar för HoloLens information

- Introducerades i Windows Insider build, 20348.1403

Följande CPP:er har uppdaterats med nya sätt att rapportera information från dina HoloLens enheter.

#### <a name="devdetail-csp---free-storage"></a>CSP:t DevDetail – kostnadsfri Storage

DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens enhet. Detta bör ungefär matcha det värde som Inställningar på Storage appsidan. Nedan visas den specifika nod som innehåller den här informationen.

- ./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID och BSSID

DeviceStatus CSP rapporterar nu även SSID och BSSID för Wi-Fi nätverk som HoloLens är aktivt ansluten till. Nedan visas de specifika noder som innehåller den här informationen.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för* Wi-Fi/BSSID

Exempel på syncml-blob (för MDM-leverantörer) för att fråga efter NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Princip för automatisk inloggning som styrs av CSP

Den här nya AutoLogonUser-principen styr om en användare loggas in automatiskt. Vissa kunder vill konfigurera enheter som är knutna till en identitet men inte vill ha någon inloggningsupplevelse. Imagine hämtar en enhet och använder fjärrhjälp omedelbart. Eller ha en fördel med att snabbt kunna distribuera HoloLens enheter och göra det möjligt för slutanvändarna att påskynda inloggningen.

När principen har angetts till ett värde som inte är tomt anges e-postadressen för den användare som loggar in automatiskt. Den angivna användaren måste logga in på enheten minst en gång för att aktivera automatisk inloggning.

OMA-URI för nytt `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` principsträngvärde

- Automatisk inloggning är aktiverat för användare med samma e-postadress.

På en enhet där den här principen har konfigurerats måste användaren som anges i principen logga in minst en gång. Efterföljande omstarter av enheten efter den första inloggningen kommer den angivna användaren att loggas in automatiskt. Endast en användare för automatisk inloggning stöds. När den automatiskt inloggade användaren har aktiverats kan den inte logga ut manuellt. Om du vill logga in som en annan användare måste principen först inaktiveras.

> [!NOTE]
>
> - Vissa händelser, till exempel större OS-uppdateringar, kan kräva att den angivna användaren loggar in på enheten igen för att återuppta beteendet för automatisk inloggning.
> - Automatisk inloggning stöds endast för MSA- och AAD-användare.

#### <a name="overview-to-try-auto-logon-csp"></a>Översikt för att prova CSP för automatisk inloggning

1. Konfigurera den nya CSP:en till en önskad användare [med hjälp av en anpassad princip:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Tillämpa CSP:n på enheten via [etableringspaketet](hololens-provisioning.md) eller [MDM.](hololens-mdm-configure.md)
1. Logga in på det angivna kontot.
1. Starta om enheten och observera att användaren loggas in automatiskt.

### <a name="improved-update-restart-detection-and-notifications"></a>Förbättrad identifiering av omstart av uppdateringar och meddelanden

Mellan aktiva timmar och installationstidsprinciper är det möjligt att undvika att HoloLens av enheter när de används. Men det skulle också fördröja införandet av uppdateringar om omstarter inte sker för att slutföra installationen av en nödvändig uppdatering. Vi har nu lagt till principer för att tillåta IT att framtvinga tidsgränser och nödvändiga omstarter och se till att installationen av en uppdatering slutförs inom rimlig tid. Användarna kan meddelas innan omstarten initieras och de kan fördröja omstarten i enlighet med IT-principen.

Följande uppdateringsprinciper har lagts till:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Översikt för att prova nya uppdateringsmeddelanden

1. Konfigurera en av de nya uppdaterings-CPP:erna via [etableringspaket](hololens-provisioning.md) eller [MDM](hololens-mdm-configure.md) (se länklistan ovan och välj ett).
1. Använd enheten under den schemalagda tiden.
1. Observera att användaren meddelas om uppdateringen och att enheten måste startas \* om.

\* Resultatet kan variera beroende på uppdateringsprinciper som används.

### <a name="smart-retry-for-app-updates"></a>Smart Försök igen för appuppdateringar

Nu aktiverad för HoloLens är en ny princip som gör att IT-administratörer kan ange ett återkommande datum eller ett tidsdatum för att starta om appar vars uppdatering misslyckades på grund av att appen används och tillåter att uppdateringen tillämpas. Dessa kan ställas in baserat på några olika utlösare, till exempel en schemalagd tid eller inloggning. Mer information om hur du använder den här principvyn [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)finns i .

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Översikt för att prova Smart Retry för appuppdateringar

1. Konfigurera den nya funktionen för smarta återförsök.
1. Logga in i en onlinemiljö på en enhet som ännu inte har tagit emot din app och är korrekt konfigurerad för.
1. Gör så att enheten inte kan ladda ned appen genom att stänga av den eller koppla från den.
1. Ha enheten påslagen och ansluten till Internet under den utlösta tiden för att försöka ladda ned igen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Använd endast privata Store-appar för Microsoft Store

Principen RequirePrivateStoreOnly har aktiverats för HoloLens. Den här principen gör att Microsoft Store kan konfigureras för att endast visa det privata arkivet som konfigurerats för din organisation. Begränsa åtkomsten till endast de appar som du har gjort tillgängliga.

Läs mer om [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly).

#### <a name="overview-to-try-only-private-store-apps"></a>Översikt för att endast prova privata Store-appar

1. Konfigurera den nya principen för dina enheter via [MDM](hololens-mdm-configure.md).
1. Logga in på en enhet som har principen.
1. Öppna appen Microsoft Store och observera att du bara kan se din organisations appar.

### <a name="use-wdac-and-lob-apps"></a>Använda WDAC- och LOB-appar

Nu kan du använda WDAC för att blockera appar eller processer från att starta och fortsätta att använda dina egna appar. du kan nu tillåta dem i din WDAC-princip. När du använder den här principen måste du köra en extra kodrad i PowerShell när du skapar WDAC-principen. [Granska stegen här.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Översikt för att prova egna appar när du använder WDAC för att blockera andra

1. Samla in AUMID:er för din LOB-app och de appar som du vill blockera.
1. [Skapa en ny WDAC-princip](/mem/intune/configuration/custom-profile-hololens) genom att följa de nya stegen.
1. [Distribuera principen med MDM](hololens-mdm-configure.md) till din enhet.
1. Logga in på enheten och observera att du kan starta appen och blockera andra.

### <a name="fixes-and-improvements"></a>Korrigeringar och förbättringar

- Ett känt [problem har åtgärdats Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ett känt [problem har åtgärdats för Enhetsportalen med time out för filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Åtgärdar problem med rapportering av efterlevnadsegenskaper från HoloLens enheter. en omstart kan krävas för att rätt rapportering ska utlösas på Insider-byggen.  
- Ett [API för tilldelad](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) åtkomst har aktiverats så att appar nu kan avgöra om HoloLens körs i helskärmsläge för den användare som är inloggad i HoloLens.
- Uppdaterade den in-box-version av Remote Assist som installeras på nytt.
- Spelpadbearbetning för 2D-appar har inaktiverats i Insider-byggen. Genom att ta bort den kan appar nu använda Gamepad-API:erna direkt och ha åtkomst till hela uppsättningen kontroller och göra vad de vill. Utvecklare bör använda Gamepad-API:er för att använda Gamepad-indata. Här är ett exempel för [Gamepad-klass (Windows. Gaming.Input) – Windows UWP-program](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- Ett problem har åtgärdats som gjorde att OOBE avslutades efter den första användarin inloggningen i scenarier där AAD-gruppbaserade kioskkonfigurationer användes.
- Åtgärdat ett problem med att visa uppdateringsmeddelanden och dialogrutor för omstart av enheten.

## <a name="start-receiving-insider-builds"></a>Börja ta emot Insider-byggen

> [!NOTE]
> Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.
>
> - Röstkommandot "Starta om enhet" fungerar bra.
> - Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.
>
> Det har uppstått en bugg i backend-delen som du kan ha påträffat, vilket gör att du kommer igång igen.

På en HoloLens 2-enhet **går du till Inställningar** Update &  >  **Security**  >  **Windows Insider Program** och väljer Kom **igång.** Länka det konto som du använde för att registrera dig Windows Insider.

> [!NOTE]
> För att kunna registrera din enhet i Insider-byggen måste du aktivera valfri telemetri. Om du inte redan har gjort det öppnar du Inställningar-appen och väljer  ->  **Sekretessdiagnostik & feedback** och väljer sedan **Valfria diagnostikdata.**

Windows insider flyttas nu till Kanaler. Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.** Så här ser mappningen ut:

![Windows Förklaring av insiderkanaler.](images/WindowsInsiderChannels.png)

Mer information finns i Introduktion [till Windows Insider-kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows bloggar.
Välj sedan **Aktiv utveckling av Windows**, välj om du vill ta emot Dev **Channel** eller **Betakanal** byggen och granska programvillkoren.
Välj **Bekräfta > starta om nu** för att slutföra. När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.

### <a name="update-error-0x80070490-work-around"></a>Uppdatera fel 0x80070490 att komma runt

Om ett uppdateringsfel uppstår 0x80070490 uppdatering på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning. Det innebär att du flyttar din insiderkanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.

#### <a name="stage-one---release-preview"></a>Steg ett – förhandsversion

1. Inställningar, Update & Security, Windows Insider Program du **Release Preview Channel**.

2. Inställningar, Update & Security, Windows Update, Check **for updates**. Efter uppdateringen fortsätter du till Steg två.

#### <a name="stage-two---dev-channel"></a>Steg två – Dev Channel

1. Inställningar, Update & Security, Windows Insider Program, välj **Dev Channel**.

2. Inställningar, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU-nedladdning och flash-riktningar

Om du vill testa med ett flyg signerat ffu måste du först flygupplåsa enheten innan du flashar den flyg signerade ffu.

1. På datorn:
    1. Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. På HoloLens – Flight Unlock: **Öppna Inställningar** Update &  >  **Security**  >  **Windows Insider Program** sedan registrera dig och starta om enheten.

1. Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.

### <a name="provide-feedback-and-report-issues"></a>Ge feedback och rapportera problem

Använd appen [Feedbackhubben på](hololens-feedback.md) din dator HoloLens att ge feedback och rapportera problem. Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.  Problem med den kinesiska och japanska versionen HoloLens bör rapporteras på samma sätt.

> [!NOTE]
> Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben åtkomst till mappen Dokument (välj **Ja när** du tillfrågas).

## <a name="note-for-developers"></a>Obs! För utvecklare

Du är välkommen och uppmanas att prova att utveckla dina program med insider-HoloLens.  Läs dokumentationen [om HoloLens developer för](https://developer.microsoft.com/windows/mixed-reality/development) att komma igång. Samma instruktioner fungerar med Insider-HoloLens.  Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens utveckling.

## <a name="stop-receiving-insider-builds"></a>Sluta ta emot Insider-byggen

Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du välja bort när din [](hololens-recovery.md) HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.

> [!CAUTION]
> Det finns ett känt problem där användare som avregistrerar sig från Insider Preview skapar efter att ha installerat om en ny förhandsversion manuellt skulle uppleva en blå skärm. Därefter måste de återställa sin enhet manuellt. Fullständig information om om du skulle påverkas eller inte finns i mer information om det [här kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Så här kontrollerar du HoloLens kör ett produktionsbygge:

1. Gå till **Inställningar > System > Om** och leta reda på build-numret.

1. [Se den nya versionen för produktions build-nummer.](hololens-release-notes.md)

Så här avanmäler du dig från Insider-byggen:

1. På en HoloLens som kör en produktionsbygge **går du till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**

1. Följ anvisningarna för att avanmäla enheten.
