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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977229"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insiderförhandsvisning för Microsoft HoloLens

Välkommen till de senaste Insider Preview-versionerna för HoloLens! Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för vår nästa större operativsystemsuppdatering för HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider – information

Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen. Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna. Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider våra byggen. Bli spänd och redo att blanda de här uppdateringarna i din verklighet.

| Funktion                 | Beskrivning                | Målanvändare | Skapa introducerat |
|-------------------------|----------------------------|--------------|------------------|
| CSP-ändringar på HoloLens | Nya CPP:er för att fråga efter data | IT-administratörer    | 20348.1403                 |

### <a name="csp-changes-on-hololens"></a>CSP-ändringar på HoloLens

- Introducerades i Windows Insider build, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens-enheten. Detta bör ungefär matcha det värde som visas på inställningsappens lagringssida. Nedan visas den specifika nod som innehåller den här informationen.

- ./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP rapporterar nu även SSID och BSSID för WiFi-nätverk som HoloLens är aktivt ansluten till. Nedan visas de specifika noder som innehåller den här informationen.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi*/BSSID

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

### <a name="fixes-and-improvements"></a>Korrigeringar och förbättringar:

- Ett känt [problem har åtgärdats för Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Åtgärdat [ett känt problem för Enhetsportalen med time out för filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Börja ta emot Insider-byggen
> [!NOTE]
> Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.
> - Röstkommandot "Starta om enheten" fungerar bra. 
> - Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.
>
> Det har uppstått en bugg i backend-delen som du kan ha stött på, vilket gör att du kommer igång igen.

På en HoloLens 2-enhet går du **till**  >  **Inställningar & Security**  >  **Windows Insider Program** och väljer **Kom igång.** Länka det konto som du använde för att registrera som Windows Insider.
Windows Insider flyttas nu till kanaler. Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.** Så här ser mappningen ut: Windows Insider förklaring av kanaler Mer information finns ![ i Introduktion Windows Insider ](images/WindowsInsiderChannels.png) [kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows-bloggar.
Välj sedan **Aktiv utveckling av Windows,** välj om du vill ta emot Dev **Channel** **eller Betakanal-versioner** och granska programvillkoren.
Välj **Bekräfta > starta om nu** för att slutföra. När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.
### <a name="update-error-0x80070490-work-around"></a>Uppdatera fel 0x80070490 för att komma runt
Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning. Det innebär att du flyttar din Insider-kanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.
#### <a name="stage-one---release-preview"></a>Steg ett – förhandsversion
1.  Inställningar, Uppdatera & säkerhet, Windows Insider Program och välj **Kanal för förhandsversion.**
2.  Settings, Update & Security, Windows Update, **Check for updates**. Efter uppdateringen fortsätter du till Fas två.
#### <a name="stage-two---dev-channel"></a>Steg två – Dev Channel
1. Inställningar, Uppdatera & säkerhet, Windows Insider Program, välj **Dev Channel**.
2. Settings, Update & Security, Windows Update, **Check for updates**.
## <a name="ffu-download-and-flash-directions"></a>FFU-nedladdning och flash-riktningar
Om du vill testa med en flyg signerad ffu måste du först låsa upp enheten innan du flashar den flyg signerade ffu.
1. På datorn:
    1. Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. På HoloLens – Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** sedan registrera dig, starta om enheten.
1. Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.
### <a name="provide-feedback-and-report-issues"></a>Ge feedback och rapportera problem
Använd appen [Feedbackhubben hololens](hololens-feedback.md) för att ge feedback och rapportera problem. Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.  Problem med den kinesiska och japanska versionen av HoloLens bör rapporteras på samma sätt.
> [!NOTE]
> Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben komma åt mappen Dokument (välj **Ja när** du tillfrågas).
## <a name="note-for-developers"></a>Obs! För utvecklare
Du är välkommen och uppmanas att prova att utveckla dina program med Insider-byggen av HoloLens.  Kom igång genom [att läsa HoloLens-utvecklardokumentationen.](https://developer.microsoft.com/windows/mixed-reality/development) Samma instruktioner fungerar med Insider-byggen av HoloLens.  Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens-utveckling.
## <a name="stop-receiving-insider-builds"></a>Sluta ta emot Insider-byggen
Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du avanmäla [](hololens-recovery.md) dig när din HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.
> [!CAUTION]
> Det finns ett känt problem där användare som avregistrerar sig från Insider Preview-versionerna efter att ha installerat om en ny version av förhandsversionen manuellt skulle uppleva en blå skärm. Därefter måste de återställa sin enhet manuellt. Fullständig information om om du skulle påverkas eller inte finns i mer information om det här [kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Så här kontrollerar du att hololens kör en produktionsbygge:
1. Gå till **Inställningar > System > Om** och leta reda på build-numret.
1. [Se den nya versionen för produktionsbyggnummer.](hololens-release-notes.md)
Så här avanmäler du dig från Insider-byggen:
1. På en HoloLens som kör en produktionsbygge går du **till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**
1. Följ instruktionerna för att avanmäla enheten.
