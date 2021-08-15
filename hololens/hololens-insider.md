---
title: Insiderförhandsvisning för Microsoft HoloLens
description: Lär dig hur du kommer igång med Insider-byggen och ge värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: df0cb555c8445ef4d8f8165996a33e0f8c1a38653b45514594f893e3c761f65a
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2021
ms.locfileid: "120364293"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insiderförhandsvisning för Microsoft HoloLens

Välkommen till de senaste Insider Preview-versionerna för HoloLens! Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för nästa stora uppdatering av operativsystemet för HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider – information

Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen. Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna. Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider-versionerna. Bli spänd och redo att blanda dessa uppdateringar i din verklighet.

| Funktion                 | Beskrivning                | Användare eller scenario | Build introducerades |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-ändringar för rapportering HoloLens information](#csp-changes-for-reporting-hololens-details) | Nya CP:er för att fråga efter data | IT-administratörer    | 20348.1403                 |
| [Princip för automatisk inloggning som styrs av CSP](#auto-login-policy-controlled-by-csp) | Används för att logga in ett konto automatiskt | IT-administratörer | 20348.1405 |
| [PFX-filstöd för Certificate Manager](#pfx-file-support-for-certificate-manager) | Lägga till PFX-certifikat via Inställningar användargränssnitt | Slutanvändare | 20348.1405 |
| [Visa avancerad diagnostikrapport i Inställningar på HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visa MDM-diagnostikloggar på enheten | Felsökning | 20348.1405 |
| [Aviseringar om offlinediagnostik](#offline-diagnostics-notifications) | Feedback om feedback för logginsamling | Felsökning | 20348.1405 |
| [Använd endast privata Store-appar för Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurera Store-appen så att den endast visar appar från organisationen | IT-administratör | 20348.1408 |
| [Förbättringar av logginsamling med låg lagring](#low-storage-log-collection-improvements) | Förbättringar av logginsamlingsscenarier i situationer med låg lagring. | IT-administratör | 20348.1412 |
| [Flytta plattformsläge](#moving-platform-mode) | Introducerar Moving Platform Mode-beta, som när den är konfigurerad möjliggör användning av HoloLens 2 på stora vattensnöring med låg-dynamisk rörelse. | Alla | 20348.1411 |
| [Korrigeringar och förbättringar](#fixes-and-improvements) | Korrigeringar och förbättringar för HoloLens. | Alla | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-ändringar för rapportering HoloLens information

- Introducerades i Windows Insider-versionen, 20348.1403

Följande CPS har uppdaterats med nya sätt att rapportera information från dina HoloLens enheter.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – kostnadsfri Storage

DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens enhet. Detta bör ungefär matcha det värde som visas Inställningar appens Storage sida. Nedan visas den specifika nod som innehåller den här informationen.

- ./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID och BSSID

DeviceStatus CSP rapporterar nu även SSID och BSSID för Wi-Fi nätverk som HoloLens är aktivt ansluten till. Nedan visas de specifika noder som innehåller den här informationen.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi/SSID*
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

Den här nya Principen AutoLogonUser styr om en användare loggas in automatiskt. Vissa kunder vill konfigurera enheter som är knutna till en identitet men inte vill ha någon inloggningsupplevelse. Imagine hämtar en enhet och använder fjärrhjälp direkt. Eller ha en fördel med att snabbt kunna distribuera HoloLens enheter och göra det möjligt för slutanvändarna att påskynda inloggningen.

När principen har angetts till ett värde som inte är tomt anges e-postadressen för användaren för automatisk inloggning. Den angivna användaren måste logga in på enheten minst en gång för att aktivera automatisk inloggning.

OMA-URI för nytt `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` principsträngvärde

- Automatisk inloggning är aktiverat för användare med samma e-postadress.

På en enhet där den här principen har konfigurerats måste användaren som anges i principen logga in minst en gång. Efterföljande omstarter av enheten efter den första inloggningen kommer att ha den angivna användaren automatiskt inloggad. Endast en användare för automatisk inloggning stöds. När den har aktiverats kan den automatiskt inloggade användaren inte logga ut manuellt. Om du vill logga in som en annan användare måste principen först inaktiveras.

> [!NOTE]
> - Vissa händelser, till exempel större OS-uppdateringar, kan kräva att den angivna användaren loggar in på enheten igen för att återuppta beteendet för automatisk inloggning. 
> - Automatisk inloggning stöds endast för MSA- och AAD-användare.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-filstöd för Certificate Manager

Introducerades i Windows Insider version 20348.1405. Vi har lagt till stöd för [Certifikathanteraren för att](certificate-manager.md) nu använda PFX-certifikat. När användarna navigerar **till Inställningar** Update & Security Certificates och väljer Installera ett certifikat har användargränssnittet nu stöd  >    >  för PFX-certifikatfilen. 
Användare kan importera .pfx-certifikat, med privat nyckel, till användararkivet eller datorarkivet.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visa avancerad diagnostikrapport i Inställningar på HoloLens

För hanterade enheter vid felsökning av beteende är det viktigt att bekräfta att en förväntad principkonfiguration tillämpas. Tidigare i den här nya funktionen var detta tvungen att göras av enheten via MDM eller nära enheten efter export av MDM-diagnostikloggar som samlats in via   ->  **Inställningar-konton** Åtkomst till arbete eller skola och välja  >   **Exportera** dina hanteringsloggar och visas på en närliggande dator.

Nu kan MDM-diagnostiken visas på enheten med hjälp av Edge-webbläsaren. Om du vill visa MDM-diagnostikrapporten enklare går du till sidan Åtkomst till arbete eller skola och väljer **Visa avancerad diagnostikrapport.** Detta genererar och öppnar rapporten i ett nytt Edge-fönster.

![Visa avancerad diagnostikrapport i Inställningar appen.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Aviseringar om offlinediagnostik

Detta är en uppdatering för en befintlig funktion som heter [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Tidigare fanns det ingen tydlig indikator för användarna att de utlöst diagnostikinsamlingen eller att den hade slutförts.
Nu har lagts Windows Insider-byggen finns det två former av feedback om offlinediagnostik. Den första är popup-meddelanden som visas för både när samlingen startar och slutförs. Dessa visas när användaren är inloggad och har visuella objekt.

![Popup-meddelande för insamling av loggar.](./images/logcollection1.jpg)

![Popup-meddelande när logginsamlingen är klar.](./images/logcollection2.jpg)
 
Eftersom användare ofta använder offlinediagnostik som reservlogginsamlingsmekanism för när de inte har åtkomst till en visning, inte kan logga in eller är kvar i OOBE, spelas även en ljudikon upp när loggar samlas in. Det här ljudet spelas upp utöver popup-meddelandet.

Den här nya funktionen aktiveras när enheten uppdateras och behöver inte aktiveras eller hanteras. Om den här nya feedbacken inte kan visas eller höras genereras fortfarande offlinediagnostik.

Vi hoppas att med den här nyare feedbacken blir det enklare att samla in diagnostikdata och snabbare kunna felsöka dina problem.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Använd endast privata Store-appar för Microsoft Store

Principen RequirePrivateStoreOnly har aktiverats för HoloLens. Med den här principen kan Microsoft Store konfigureras så att endast det privata arkivet som har konfigurerats för din organisation visas. Begränsa åtkomsten till endast de appar som du har gjort tillgängliga.

Läs mer om [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Förbättringar av logginsamling med låg lagring

I scenarier där en enhet verkar ha ont om diskutrymme när diagnostikloggar samlas in, skapas ytterligare en **rapport medStorageDiagnostics.zip** namn. Tröskelvärdet för låg lagring bestäms automatiskt av Windows [lagringsförekänning](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

### <a name="moving-platform-mode"></a>Flytta plattformsläge

Från och **med Insider-versionen 20348.1411** har vi lagt till betastöd för spårning på plattformar med låg dynamisk rörelseflyttning på HoloLens 2. När du har installerat bygget och aktiverat Moving Platform Mode kan du använda din HoloLens 2 i tidigare otillgängliga miljöer, till exempel stora skepp och stora laster. För närvarande är funktionen avsedd att endast aktivera dessa specifika rörliga plattformar. Inget hindrar dig från att försöka använda funktionen i andra miljöer, men funktionen fokuserar på att lägga till stöd för dessa miljöer först.

Mer information om vad som stöds och hur du aktiverar den här nya funktionen finns [på sidan om att flytta plattformen.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Korrigeringar och förbättringar

- Ett känt [problem har åtgärdats Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ett känt [problem har åtgärdats för Enhetsportalen med time out-fel vid filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Åtgärdar problem med rapportering av efterlevnadsegenskaper från HoloLens enheter. en omstart kan krävas för att rätt rapportering ska utlösas på Insider-byggen.  
- Ett [API för tilldelad](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) åtkomst har aktiverats så att appar nu kan avgöra om HoloLens körs i helskärmsläge för den användare som är inloggad i HoloLens.
- Uppdaterade den in-box-version av Remote Assist som installeras på nytt.

## <a name="start-receiving-insider-builds"></a>Börja ta emot Insider-byggen

> [!NOTE]
> Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.
> - Röstkommandot "Starta om enhet" fungerar bra. 
> - Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.
>
> Det har uppstått en bugg i backend-delen som du kan ha påträffat, vilket gör att du kommer igång igen.

På en HoloLens 2-enhet **går du till Inställningar**  >  **Update & Security**  >  **Windows Insider Program** och väljer **Kom igång.** Länka det konto som du använde för att registrera dig Windows Insider.

Windows insider flyttas nu till Kanaler. Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.** Så här ser mappningen ut:

![Windows Förklaring av insiderkanaler](images/WindowsInsiderChannels.png)

Mer information finns i Introduktion [till Windows Insider-kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows bloggar.
Välj sedan **Aktiv utveckling av Windows**, välj om du vill ta emot Dev **Channel** eller **Betakanal** byggen och granska programvillkoren.
Välj **Bekräfta > starta om nu** för att slutföra. När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.

### <a name="update-error-0x80070490-work-around"></a>Uppdatera fel 0x80070490 för att komma runt

Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning. Det innebär att du flyttar din insiderkanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.

#### <a name="stage-one---release-preview"></a>Steg ett – förhandsversion

1.  Inställningar, Update & Security, Windows Insider Program du Release Preview **Channel**.

2.  Inställningar, Update & Security, Windows Update, **Check for updates**. Efter uppdateringen fortsätter du till Steg två.

#### <a name="stage-two---dev-channel"></a>Steg två – Dev Channel

1. Inställningar, Update & Security, Windows Insider Program, välj Dev **Channel**.

2. Inställningar, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU-nedladdning och flash-riktningar

Om du vill testa med ett flyg signerat ffu måste du först flygupplåsa enheten innan du flashar den flyg signerade ffu.

1. På datorn:
    1. Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. På HoloLens – Flight Unlock: **Öppna Inställningar** Update &  >  **Security**  >  **Windows Insider Program** sedan registrera dig och starta om enheten.

1. Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.

### <a name="provide-feedback-and-report-issues"></a>Ge feedback och rapportera problem

Använd appen [Feedbackhubben på](hololens-feedback.md) ditt HoloLens för att ge feedback och rapportera problem. Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.  Problem med den kinesiska och japanska versionen HoloLens bör rapporteras på samma sätt.

> [!NOTE]
> Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben åtkomst till mappen Dokument (välj **Ja när** du tillfrågas).

## <a name="note-for-developers"></a>Obs! För utvecklare

Du är välkommen och uppmanas att prova att utveckla dina program med Insider-HoloLens.  Läs dokumentationen [HoloLens developer för](https://developer.microsoft.com/windows/mixed-reality/development) att komma igång. Samma instruktioner fungerar med Insider-HoloLens.  Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens utveckling.

## <a name="stop-receiving-insider-builds"></a>Sluta ta emot Insider-byggen

Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du välja bort när din [](hololens-recovery.md) HoloLens kör en produktionsversion, eller så kan du återställa enheten med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.

> [!CAUTION]
> Det finns ett känt problem där användare som avregistrerar sig från Insider Preview skapar efter att ha installerat om en ny förhandsversion manuellt skulle uppleva en blå skärm. Därefter måste de återställa sin enhet manuellt. Fullständig information om om du skulle påverkas eller inte finns i mer information om det [här kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Så här kontrollerar du HoloLens kör ett produktionsbygge:

1. Gå till **Inställningar > System > Om** och leta reda på build-numret.

1. [Se den nya versionen för produktions build-nummer.](hololens-release-notes.md)

Så här avanmäler du dig från Insider-byggen:

1. På en HoloLens som kör en produktionsbygge **går du till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**

1. Följ anvisningarna för att avanmäla enheten.
