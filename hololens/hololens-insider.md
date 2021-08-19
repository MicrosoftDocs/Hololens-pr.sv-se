---
title: Insiderförhandsvisning för Microsoft HoloLens
description: Lär dig hur du kommer igång med Insider-byggen och ge värdefull feedback för vår nästa större operativsystemsuppdatering för HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 19035c53fec64ec19243ab5edc79bf77acbf400a
ms.sourcegitcommit: d99de8d5afbe2585fdb5396bd0165ac74734b281
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2021
ms.locfileid: "122277162"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insiderförhandsvisning för Microsoft HoloLens

Välkommen till de senaste Insider Preview-versionerna för HoloLens! Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insiders versionsanteckningar

Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen. Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna. Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider-versionerna. Bli spänd och redo att blanda dessa uppdateringar i din verklighet.

Den här handlar om den förbättrade felsöknings- och enhetsrapporterna, vissa fasta buggar i helskärmsläge och certifikatvisaren, den utökade hanterbarhetsytan och den ökade uppdateringstillförlitligheten. En ny funktion i den här funktionsuppdateringen som kommer till HoloLens är vårt moving platform-läge. Kolla in alla nya fantastiska funktioner för HoloLens 2!

| Funktion                 | Beskrivning                | Användare eller scenario | Build introducerades |
|-------------------------|----------------------------|--------------|------------------|
| [Flytta plattformsläge](#moving-platform-mode) | Introducerar Moving Platform Mode-beta, som när den konfigureras möjliggör användning av HoloLens 2 på stora djur som upplever låg-dynamisk rörelse. | Alla | 20348.1411 |
| [PFX-filstöd för Certificate Manager](#pfx-file-support-for-certificate-manager) | Lägga till PFX-certifikat via Inställningar användargränssnitt | Slutanvändare | 20348.1405 |
| [Visa avancerad diagnostikrapport i Inställningar på HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visa MDM-diagnostikloggar på enheten | Felsökning | 20348.1405 |
| [Aviseringar om offlinediagnostik](#offline-diagnostics-notifications) | Bra feedback för logginsamling | Felsökning | 20348.1405 |
| [Förbättringar av logginsamling med låg lagring](#low-storage-log-collection-improvements) | Förbättringar av logginsamlingsscenarier i situationer med låg lagring. | Felsökning | 20348.1412 |
| [CSP-ändringar för HoloLens information](#csp-changes-for-reporting-hololens-details) | Nya CPP:er för att fråga efter data | IT-administratörer    | 20348.1403                 |
| [Princip för automatisk inloggning som styrs av CSP](#auto-login-policy-controlled-by-csp) | Används för att logga in ett konto automatiskt | IT-administratörer | 20348.1405 |
| [Förbättrad identifiering av omstart av uppdateringar och meddelanden](#improved-update-restart-detection-and-notifications) | Nya aktiverade - och UX-funktioner för uppdateringar. | IT-administratörer | 20348.1405 |
| [Smart Försök igen för appuppdateringar](#smart-retry-for-app-updates) | Gör att IT-administratörer kan schemalägga återförsök för att uppdatera appar. | IT-administratörer | 20348.1405 |
| [Använd endast privata Store-appar för Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurera Store-appen så att den endast visar appar från organisationen | IT-administratör | 20348.1408 |
| [Korrigeringar och förbättringar](#fixes-and-improvements) | Korrigeringar och förbättringar för HoloLens. | Alla | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Checklista för INSIDER-funktioner för IT-administratörer

✔️ Konfigurera den nya [CSP:en](#auto-login-policy-controlled-by-csp) om du vill ange att ett enda Azure AD-konto ska logga in automatiskt. <br>
✔️ Om du vill konfigurera dina appar så att de automatiskt försöker uppdatera efter att det inte gick att uppdatera, anger du den nya [CSP:en för smart återförsök.](#smart-retry-for-app-updates) <br>
✔️ Om du vill ha mer kontroll över OS-uppdateringar kan du läsa dessa nyligen [aktiverade uppdateringsprinciper.](#improved-update-restart-detection-and-notifications) <br>
✔️ Ange den här principen om du behöver göra din organisations appar tillgängliga i företagsbutiken via Microsoft Store, men bara vill tillåta åtkomst till din organisations appar och inte hela [butiken.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Om du vill veta det lediga lagringsutrymmet, SSID eller BSSID för dina HoloLens enheter kan du läsa dessa [rapporterings-CPP:er.](#csp-changes-for-reporting-hololens-details)

### <a name="moving-platform-mode"></a>Flytta plattformsläge

Från och **med Insider-versionen 20348.1411** har vi lagt till betastöd för spårning på plattformar med låg dynamisk rörelseflyttning på HoloLens 2. När du har installerat bygget och aktiverat Moving Platform Mode kan du använda din HoloLens 2 i tidigare otillgängliga miljöer, till exempel stora skepp och stora djur. För närvarande är funktionen endast avsedd att aktivera dessa specifika plattformar som flyttas. Även om ingenting hindrar dig från att försöka använda funktionen i andra miljöer fokuserar funktionen på att lägga till stöd för dessa miljöer först.

Mer information om vad som stöds och hur du aktiverar den här nya funktionen finns [på sidan om att flytta plattformen.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-filstöd för Certificate Manager

Introducerades i Windows Insider version 20348.1405. Vi har lagt till stöd för [Certifikathanteraren för att](certificate-manager.md) nu använda .pfx-certifikat. När användarna navigerar **till Inställningar** Update & Security Certificates (Uppdatera &) och väljer Install a certificate (Installera ett certifikat) stöder användargränssnittet  >    >  nu PFX-certifikatfilen. 
Användare kan importera PFX-certifikat, med privat nyckel, till användararkivet eller datorarkivet.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visa avancerad diagnostikrapport i Inställningar på HoloLens

För hanterade enheter vid felsökning av beteende är det viktigt att bekräfta att en förväntad principkonfiguration tillämpas. Tidigare i den här nya funktionen behövde detta göras av enheten via MDM eller nära enheten efter export av MDM-diagnostikloggar som samlats in via **Inställningar** Accounts Access work  ->    >  **or school**(Åtkomst till Inställningar-konton för arbete eller skola) och välja **Exportera** dina hanteringsloggar och visa dem på en närliggande dator.

Nu kan MDM-diagnostiken visas på enheten med hjälp av Edge-webbläsaren. Om du vill visa MDM-diagnostikrapporten enklare går du till sidan Åtkomst till arbete eller skola och väljer **Visa avancerad diagnostikrapport.** Detta genererar och öppnar rapporten i ett nytt Edge-fönster.

![Visa avancerad diagnostikrapport i Inställningar app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Aviseringar om offlinediagnostik

Detta är en uppdatering för en befintlig funktion som heter [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Tidigare fanns det ingen tydlig indikator för användarna att de utlöst diagnostikinsamlingen eller att den hade slutförts.
Det finns nu två Windows feedback om offlinediagnostik som läggs till i Windows Insider-byggen. Den första är popup-meddelanden som visas för både när samlingen startar och slutförs. Dessa visas när användaren är inloggad och har visuella objekt.

![Popup-meddelande för insamling av loggar.](./images/logcollection1.jpg)

![Popup-meddelande när logginsamlingen är klar.](./images/logcollection2.jpg)

Eftersom användare ofta använder offlinediagnostik som reservlogginsamlingsmekanism för när de inte har åtkomst till en visning, inte kan logga in eller är kvar i OOBE, spelas även en ljudikon upp när loggar samlas in. Det här ljudet spelas upp utöver popup-meddelandet.

Den här nya funktionen aktiveras när enheten uppdateras och behöver inte aktiveras eller hanteras. Om denna nya feedback inte kan visas eller höras genereras fortfarande offlinediagnostik.

Med den här nyare feedbacken hoppas vi att det är enklare att samla in diagnostikdata och att du snabbare ska kunna felsöka dina problem.

### <a name="low-storage-log-collection-improvements"></a>Förbättringar av logginsamling med låg lagring

I scenarier där en enhet verkar ha ont om diskutrymme när diagnostikloggar samlas in, skapas ytterligare **en rapport medStorageDiagnostics.zip** namn. Tröskelvärdet för låg lagring bestäms automatiskt av Windows [lagrings sense](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-ändringar för HoloLens information

- Introducerades i Windows Insider build, 20348.1403

Följande CPP:er har uppdaterats med nya sätt att rapportera information från dina HoloLens enheter.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – kostnadsfri Storage

DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens enhet. Detta bör ungefär matcha det värde som Inställningar på Storage appsidan. Nedan visas den specifika nod som innehåller den här informationen.

- ./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID och BSSID

DeviceStatus CSP rapporterar nu även SSID och BSSID för Wi-Fi nätverk som HoloLens är aktivt ansluten till. Nedan visas de specifika noder som innehåller den här informationen.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/BSSID

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

Den här nya AutoLogonUser-principen styr om en användare loggas in automatiskt. Vissa kunder vill konfigurera enheter som är knutna till en identitet men inte vill ha någon inloggningsupplevelse. Imagine att hämta en enhet och använda fjärrhjälp omedelbart. Eller ha en fördel med att snabbt kunna distribuera HoloLens enheter och göra det möjligt för slutanvändarna att påskynda inloggningen.

När principen har angetts till ett värde som inte är tomt anges e-postadressen för den användare som loggar in automatiskt. Den angivna användaren måste logga in på enheten minst en gång för att aktivera automatisk inloggning.

OMA-URI för nytt `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` principsträngvärde

- Automatisk inloggning är aktiverat för användare med samma e-postadress.

På en enhet där den här principen har konfigurerats måste användaren som anges i principen logga in minst en gång. Efterföljande omstarter av enheten efter den första inloggningen kommer den angivna användaren att loggas in automatiskt. Endast en användare för automatisk inloggning stöds. När den automatiskt inloggade användaren har aktiverats kan den inte logga ut manuellt. Om du vill logga in som en annan användare måste principen först inaktiveras.

> [!NOTE]
>
> - Vissa händelser, till exempel större OS-uppdateringar, kan kräva att den angivna användaren loggar in på enheten igen för att återuppta beteendet för automatisk inloggning.
> - Automatisk inloggning stöds endast för MSA- och AAD-användare.

### <a name="improved-update-restart-detection-and-notifications"></a>Förbättrad identifiering av omstart av uppdateringar och meddelanden

Mellan aktiva timmar och installationstidsprinciper är det möjligt att undvika att starta HoloLens enheter när de används. Men det skulle också fördröja införandet av uppdateringar om omstarter inte sker för att slutföra installationen av en nödvändig uppdatering. Vi har nu lagt till principer för att tillåta IT att framtvinga tidsgränser och nödvändiga omstarter och se till att installationen av en uppdatering slutförs inom rimlig tid. Användarna kan meddelas innan omstarten initieras och de kan fördröja omstarten i enlighet med IT-principen.

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

### <a name="smart-retry-for-app-updates"></a>Smart Försök igen för appuppdateringar

Nu aktiverad för HoloLens är en ny princip som gör att IT-administratörer kan ange ett återkommande datum eller ett tidsdatum för att starta om appar vars uppdatering misslyckades på grund av att appen används och tillåter att uppdateringen tillämpas. Dessa kan ställas in baserat på några olika utlösare, till exempel en schemalagd tid eller inloggning. Mer information om hur du använder den här principen finns i [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Använd endast privata Store-appar för Microsoft Store

Principen RequirePrivateStoreOnly har aktiverats för HoloLens. Den här principen gör att Microsoft Store kan konfigureras för att endast visa det privata arkivet som konfigurerats för din organisation. Begränsa åtkomsten till endast de appar som du har gjort tillgängliga.

Läs mer om [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Korrigeringar och förbättringar

- Ett känt [problem har åtgärdats för Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Åtgärdat [ett känt problem för Enhetsportalen med time out för filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Åtgärdar problem med rapportering av efterlevnadsegenskaper från HoloLens enheter. en omstart kan krävas för att rätt rapportering ska utlösas i Insider-byggen.  
- Ett [API för tilldelad](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) åtkomst har aktiverats så att appar nu kan avgöra om en HoloLens körs i helskärmsläge för den användare som är inloggad i HoloLens.
- Uppdaterade den in-box-versionen av Remote Assist som är installerad på nytt.

## <a name="start-receiving-insider-builds"></a>Börja ta emot Insider-byggen

> [!NOTE]
> Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.
>
> - Röstkommandot "Starta om enheten" fungerar bra.
> - Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.
>
> Vi har en bugg i backend-delen som du kan ha stött på och det kommer att få dig att komma igång igen.

På en HoloLens 2-enhet **går du till Inställningar** Update &  >  **Security**  >  **Windows Insider Program** och väljer Kom **igång.** Länka det konto som du använde för att registrera dig Windows Insider.

Windows insider flyttas nu till kanaler. Snabbringen blir **Dev Channel,**  den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.**  Så här ser mappningen ut:

![Windows Förklaring av insiderkanaler](images/WindowsInsiderChannels.png)

Mer information finns i [Introduktion till Windows Insider-kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows Bloggar.
Välj sedan **Aktiv utveckling av Windows**, välj om du vill ta emot Dev **Channel** **eller Betakanal-byggen** och granska programvillkoren.
Välj **Bekräfta > starta om nu** för att slutföra. När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.

### <a name="update-error-0x80070490-work-around"></a>Uppdatera fel 0x80070490 för att komma runt

Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning. Det innebär att du flyttar din Insider-kanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.

#### <a name="stage-one---release-preview"></a>Steg ett – förhandsversion

1. Inställningar, Update & Security, Windows Insider Program, välj Release **Preview Channel**.

2. Inställningar, Update & Security, Windows Update, **Check for updates**. Efter uppdateringen fortsätter du till Fas två.

#### <a name="stage-two---dev-channel"></a>Steg två – Dev Channel

1. Inställningar, Update & Security, Windows Insider Program, väljer **du Dev Channel**.

2. Inställningar, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU-nedladdning och flash-riktningar

Om du vill testa med en flyg signerad ffu måste du först flygupplåsa enheten innan du flashar den flyg signerade ffu.

1. På datorn:
    1. Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. På HoloLens – Flight Unlock: **Öppna Inställningar** Update &  >  **Security**  >  **Windows Insider Program** sedan registrera dig och starta om enheten.

1. Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.

### <a name="provide-feedback-and-report-issues"></a>Ge feedback och rapportera problem

Använd appen [Feedbackhubben på](hololens-feedback.md) din dator HoloLens ge feedback och rapportera problem. Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår så att våra tekniker snabbt kan felsöka och lösa problemet.  Problem med den kinesiska och japanska versionen HoloLens bör rapporteras på samma sätt.

> [!NOTE]
> Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben åtkomst till mappen Dokument (välj **Ja när** du tillfrågas).

## <a name="note-for-developers"></a>Obs! För utvecklare

Du är välkommen och uppmanas att prova att utveckla dina program med Insider-HoloLens.  Kom igång [genom HoloLens utvecklardokumentationen.](https://developer.microsoft.com/windows/mixed-reality/development) Samma instruktioner fungerar med Insider-HoloLens.  Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens utveckling.

## <a name="stop-receiving-insider-builds"></a>Sluta ta emot Insider-byggen

Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du avanmäla dig [](hololens-recovery.md) när din HoloLens kör en produktionsversion eller så kan du återställa enheten med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.

> [!CAUTION]
> Det finns ett känt problem där användare som avregistrerar sig från Insider Preview skapar efter att ha installerat om en ny version av förhandsversionen manuellt skulle uppleva en blå skärm. Därefter måste de återställa sin enhet manuellt. Fullständig information om om du skulle påverkas eller inte finns i mer information om det här [kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Så här kontrollerar du HoloLens kör en produktionsbygge:

1. Gå till **Inställningar > System > Om** och leta reda på build-numret.

1. [Se den nya versionen för produktions build-nummer.](hololens-release-notes.md)

Så här avanmäler du dig från Insider-byggen:

1. På en HoloLens som kör en produktionsbygge går du **till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**

1. Följ instruktionerna för att avanmäla enheten.
