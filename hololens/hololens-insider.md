---
title: Insiderförhandsvisning för Microsoft HoloLens
description: Lär dig hur du kommer igång med Insider-byggen och ger värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.
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
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378843"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insiderförhandsvisning för Microsoft HoloLens

Välkommen till de senaste Insider Preview-versionerna för HoloLens! Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider – Information

Vi är glada över att kunna börja använda nya funktioner i Windows Insiders igen. Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna. Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider våra byggen. Bli spänd och redo att blanda dessa uppdateringar i din verklighet. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>Ladda upp en kamera med OneDrive för arbete eller skola

*Introducerades i version 20346.1402*

Vi har lagt till en ny funktion i holoLens 2-inställningsappen, som gör att kunder automatiskt kan ladda upp foton och videor med mixad verklighet från enhetens mapp Pictures > Camera Roll till motsvarande OneDrive för arbets- eller skolmapp. Den här funktionen åtgärdar ett funktionsgap i [OneDrive-appen](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) på HoloLens 2, som endast stöder automatisk överföring av kamerarullning till en kunds personliga Microsoft-konto (och inte deras arbets- eller skolkonto).

**Så här fungerar det**

- Gå **till Inställningar > System > Mixed Reality Kamera för** att aktivera "Kamerauppladdning".
- Genom att ställa  in den här funktionen på Läget På placeras alla foton eller videor med mixad verklighet som har avbildats på enheten automatiskt i kö för uppladdning till mappen Bilder > Camera Roll för ditt OneDrive för arbets- eller skolkonto.
    >[!NOTE]
    >Foton och videor som har tagits innan du aktiverar den *här* funktionen kommer inte att köas för uppladdning och måste fortfarande laddas upp manuellt.
- Ett statusmeddelande på sidan Inställningar visar antalet filer som väntar på uppladdning (eller läser "OneDrive är uppdaterat" när alla väntande filer har laddats upp).
- Om du är orolig för bandbredden eller om du vill "pausa" uppladdningen av någon anledning kan du växla funktionen till **läget Av.** Om du tillfälligt inaktiverar funktionen ser du till att uppladdningskön fortsätter att öka när du lägger till nya filer i mappen Kamerarulle, men filerna laddas inte upp förrän du aktiverar funktionen på nytt.
- De senaste filerna laddas upp först (sist in, först ut).
- Om ditt OneDrive-konto har problem (till exempel  efter dina lösenordsändringar) visas knappen Åtgärda nu på sidan Inställningar.
- Det finns ingen maximal filstorlek, men observera att stora filer tar längre tid att ladda upp (särskilt om bandbredden för uppladdningen är begränsad). Om du "pausar" eller inaktiverar uppladdningen medan en stor fil laddas upp avbryts överföringen omedelbart. Uppladdningen startar om när du återaktivera funktionen. du kommer inte att förlora några filer, men den partiella uppladdningen kommer att tas bort.

**Kända problem och varningar**

- Den här inställningen har ingen inbyggd begränsning baserat på aktuell bandbreddsanvändning. Om du behöver maximera bandbredden för ett annat scenario kan du inaktivera inställningen manuellt. Uppladdningen pausas men funktionen fortsätter att övervaka nyligen tillagda filer i Kamerarullning. Återaktivera uppladdning när du är redo att fortsätta.
- Den här funktionen måste aktiveras för varje användarkonto på enheten och kan bara aktivt ladda upp filer för den användare som för närvarande är inloggad på enheten.
- Om du tar foton eller videor medan du tittar på uppladdningsantalet på sidan Inställningar i realtid kan det hända att antalet väntande filer inte ändras förrän den aktuella filen har laddats upp.
- Uppladdningen pausas om enheten förfaller eller är avstängd. För att säkerställa att dina väntande **uppladdningar** slutförs använder du aktivt enheten tills sidan Inställningar läser "OneDrive är uppdaterad" eller justerar inställningarna för & strömsparläge.

## <a name="start-receiving-insider-builds"></a>Börja ta emot Insider-byggen
> [!NOTE]
> Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.
> - Röstkommandot "Starta om enhet" fungerar bra. 
> - Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.
>
> Det har uppstått en bugg i backend-delen som du kan ha påträffat, vilket gör att du kommer igång igen.

På en HoloLens 2-enhet går du till   >  **Inställningar uppdatera & Security**  >  **Windows Insider Program** och väljer **Kom igång.** Länka det konto som du använde för att registrera Windows Insider.
Windows Insider flyttas nu till Kanaler. Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.** Så här ser mappningen ut: Windows Insider förklaring av kanaler Mer information finns i ![ Introduktion till Windows Insider ](images/WindowsInsiderChannels.png) [kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows-bloggar.
Välj sedan **Aktiv utveckling av Windows,** välj om du vill ta emot Dev **Channel** **eller Betakanal** versioner och granska programvillkoren.
Välj **Bekräfta > starta om nu** för att slutföra. När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.
### <a name="update-error-0x80070490-work-around"></a>Uppdatera fel 0x80070490 för att komma runt
Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning. Det innebär att du flyttar din insiderkanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.
#### <a name="stage-one---release-preview"></a>Steg ett – förhandsversion
1.  Inställningar, Uppdatera & säkerhet, Windows Insider Program och välj **Kanal för förhandsversion.**
2.  Settings, Update & Security, Windows Update, **Check for updates**. Efter uppdateringen fortsätter du till Steg två.
#### <a name="stage-two---dev-channel"></a>Steg två – Dev Channel
1. Inställningar, Uppdatera & säkerhet, Windows Insider Program, välj **Dev Channel**.
2. Settings, Update & Security, Windows Update, **Check for updates**.
## <a name="ffu-download-and-flash-directions"></a>FFU-nedladdning och flash-riktningar
Om du vill testa med ett flyg signerat ffu måste du först flygupplåsa enheten innan du flashar den flyg signerade ffu.
1. På datorn:
    1. Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. På HoloLens – Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** sedan registrera dig och starta om enheten.
1. Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.
### <a name="provide-feedback-and-report-issues"></a>Ge feedback och rapportera problem
Använd appen [Feedbackhubben HoloLens](hololens-feedback.md) för att ge feedback och rapportera problem. Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.  Problem med den kinesiska och japanska versionen av HoloLens bör rapporteras på samma sätt.
> [!NOTE]
> Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben åtkomst till mappen Dokument (välj **Ja när** du tillfrågas).
## <a name="note-for-developers"></a>Obs! För utvecklare
Du är välkommen och uppmanas att prova att utveckla dina program med Insider-byggen av HoloLens.  Läs [HoloLens Developer-dokumentationen för att](https://developer.microsoft.com/windows/mixed-reality/development) komma igång. Samma instruktioner fungerar med Insider-byggen av HoloLens.  Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens-utveckling.
## <a name="stop-receiving-insider-builds"></a>Sluta ta emot Insider-byggen
Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du välja bort [](hololens-recovery.md) när din HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.
> [!CAUTION]
> Det finns ett känt problem där användare som avregistrerar sig från Insider Preview skapar efter att ha installerat om en ny förhandsversion manuellt skulle uppleva en blå skärm. Därefter måste de återställa sin enhet manuellt. Fullständig information om om du skulle påverkas eller inte finns i mer information om det [här kända problemet.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Så här kontrollerar du att HoloLens kör en produktionsbygge:
1. Gå till **Inställningar > System > Om** och leta reda på build-numret.
1. [Se den nya versionen för produktions build-nummer.](hololens-release-notes.md)
Så här avanmäler du dig från Insider-byggen:
1. På en HoloLens som kör ett produktionsbygge går du **till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**
1. Följ anvisningarna för att avanmäla enheten.
