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
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924358"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insiderförhandsvisning för Microsoft HoloLens

Välkommen till de senaste Insider Preview-versionerna för HoloLens! Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för nästa större operativsystemsuppdatering för HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insiders versionsanteckningar

Vi är glada över att alla våra senaste Insider-funktioner har blivit offentliga! Om du vill läsa om dessa kan du ta en titt på sidan [med information om versionen](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Börja ta emot Insider-byggen

> [!NOTE]
> Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.
>
> - Röstkommandot "Starta om enheten" fungerar bra.
> - Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.
>
> Det har uppstått en bugg i backend-delen som du kan ha stött på, vilket gör att du kommer igång igen.

På en HoloLens 2-enhet **går du till Inställningar**  >  **Update & Security**  >  **Windows Insider Program** och väljer **Kom igång.** Länka det konto som du använde för att registrera dig Windows Insider.

> [!NOTE]
> För att kunna registrera din enhet i Insider-byggen måste du aktivera valfri telemetri. Om du inte redan har gjort det öppnar du Inställningar-appen och väljer Sekretessdiagnostik & feedback och  ->   väljer **sedan Valfria diagnostikdata.**

Windows insider flyttas nu till kanaler. Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.** Så här ser mappningen ut:

![Windows Förklaring av insiderkanaler.](images/WindowsInsiderChannels.png)

Mer information finns i Introduktion [till Windows Insider-kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows Bloggar.
Välj sedan **Aktiv utveckling Windows**, välj om du vill ta emot Dev **Channel** eller **Betakanal-byggen** och granska programvillkoren.
Välj **Bekräfta > starta om nu** för att slutföra. När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.

### <a name="update-error-0x80070490-work-around"></a>Uppdatera fel 0x80070490 för att komma runt

Om du får ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning. Det innebär att du flyttar din Insider-kanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.

#### <a name="stage-one---release-preview"></a>Steg ett – förhandsversion

1. Inställningar, Update & Security, Windows Insider Program du **Release Preview Channel**.

2. Inställningar, Update & Security, Windows Update, **Check for updates**. Efter uppdateringen fortsätter du till Fas två.

#### <a name="stage-two---dev-channel"></a>Steg två – Dev Channel

1. Inställningar, Update & Security, Windows Insider Program, väljer du **Dev Channel**.

2. Inställningar, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU-nedladdning och flash-riktningar

Om du vill testa med en flyg signerad ffu måste du först flygupplåsa enheten innan du flashar den flyg signerade ffu.

1. På datorn:
    1. Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. På HoloLens – Flight Unlock: **Öppna Inställningar** Update &  >  **Security**  >  **Windows Insider Program** och registrera dig och starta om enheten.

1. Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.

### <a name="provide-feedback-and-report-issues"></a>Ge feedback och rapportera problem

Använd appen [Feedbackhubben på](hololens-feedback.md) din dator HoloLens ge feedback och rapportera problem. Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.  Problem med den kinesiska och japanska HoloLens bör rapporteras på samma sätt.

> [!NOTE]
> Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben åtkomst till mappen Dokument (välj **Ja när** du tillfrågas).

## <a name="note-for-developers"></a>Obs! För utvecklare

Du är välkommen och uppmanas att prova att utveckla dina program med Insider-HoloLens.  Kom igång [genom HoloLens utvecklardokumentationen.](https://developer.microsoft.com/windows/mixed-reality/development) Samma instruktioner fungerar med Insider-HoloLens.  Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens utveckling.

## <a name="stop-receiving-insider-builds"></a>Sluta ta emot Insider-byggen

Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du avanmäla dig [](hololens-recovery.md) när din HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.

> [!CAUTION]
> Det finns ett känt problem där användare som avregistrerar sig från Insider Preview-versionerna efter att ha installerat om en ny version av förhandsversionen manuellt skulle uppleva en blå skärm. Därefter måste de återställa sin enhet manuellt. Fullständig information om om du skulle påverkas eller inte finns i mer information om det här [kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Så här kontrollerar du HoloLens kör en produktionsbygge:

1. Gå till **Inställningar > System > Om** och leta reda på build-numret.

1. [Se den nya versionen för produktions build-nummer.](hololens-release-notes.md)

Så här avanmäler du dig från Insider-byggen:

1. På en HoloLens som kör en produktionsbygge går du **till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**

1. Följ instruktionerna för att avanmäla enheten.
