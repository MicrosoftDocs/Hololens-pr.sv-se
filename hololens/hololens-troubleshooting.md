---
title: Felsökning
description: Håll dig uppdaterad om de vanligaste lösningarna på HoloLens-enhetsproblem och felsökningstekniker.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problem, bugg, felsöka, åtgärda, hjälp, support, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378823"
---
# <a name="troubleshoot-common-issues"></a>Felsök vanliga problem

Den här artikeln beskriver hur du löser flera vanliga HoloLens-problem.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Min HoloLens svarar inte eller startar inte

Om hololens inte startar:

- Om lysdioderna bredvid strömknappen inte tänds eller bara en lysdiod blinkar en kort stund kan du behöva debitera [HoloLens.](hololens-recovery.md#charge-the-device)
- Om lysdioderna tänds när du trycker på strömknappen men du inte kan se något på skärmarna kan du förinställa [enheten.](hololens-recovery.md#hard-reset-procedure)

Om hololens blir låst eller inte svarar:

- Stäng av HoloLens genom att trycka på strömknappen tills alla fem lysdioderna stänger av sig själva eller i 15 sekunder om lysdioderna inte svarar. Starta HoloLens genom att trycka på strömknappen igen.

Om de här stegen inte fungerar kan du försöka återställa [din HoloLens 2-enhet](hololens-recovery.md) eller [HoloLens-enhet (första generationen).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Hologram ser inte bra ut

Om dina hologram är instabila, hoppiga eller inte ser rätt ut kan du prova:

- Rensa ditt enhetsvisor- och sensorfält framför HoloLens.
- Öka lampan i rummet.
- Gå runt och titta på din miljö så att HoloLens kan genomsöka dem mer fullständigt.
- Att kalibrera HoloLens för dina ögon. Gå till **Inställningar**  >    >  **Systemverktyg**. Under **Kalibrering** väljer du **Öppna kalibrering.**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Rapportera problem där Hologram är instabila eller inte ser rätt ut
 
1. Spela in och [Inspelning av mixad verklighet video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) om problemet. Den här videon kan senare laddas upp via Feedbackhubben som en bifogad fil.  
1. Aktivera fullständig telemetri via appen **Inställningar** – > sekretessdiagnostik & feedback och under Valfria  ->   **diagnostikdata** ser du till att växlingsknappen är inställd på **På**
1. Hämta de senaste korrigeringarna för hologramskalning och stabilitet genom att uppdatera till det senaste [Windows Holographic OS(20H2 eller senare)](hololens-release-notes.md#windows-holographic-version-20h2). När du har uppdaterat utför du följande:
    1. Ta bort alla hologram via **appen** Inställningar -> **System**  ->  **Holograms** -> sedan Ta bort alla **hologram** och börja med en ny karta.
    1. Skapa en ny karta över ditt utrymme genom att använda HoloLens och gå runt i rummet och titta på alla områden och ytor i utrymmet. Gör detta i 2–3 minuter.
    1. Utför IPD-kalibrering. Gå till **Inställningar**  >    >  **Systemverktyg**. Under **Kalibrering** väljer du **Öppna kalibrering.**
    1. Testa scenariot på ett annat sätt och se om det fortfarande finns kvar.
1. Om uppdateringen inte åtgärdar problemet kan du skicka en [Feedbackhubben problemet](hololens-feedback.md). När du har fyllt i  feedback kan du använda knappen Dela för att skapa en enkel delningslänk som kan skickas när du kontaktar supporten.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens svarar inte på handindata

För att säkerställa att HoloLens kan se dina händer måste du hålla dem inom gesterramen.  Startsidan Mixed Reality feedback som meddelar dig när dina händer spåras.  Feedbacken är annorlunda i olika versioner av HoloLens:
- På HoloLens (1:a gen) ändras blickmarkören från en punkt till en ring
- På HoloLens 2 visas en markör med fingertryck när din hand är nära en pektavla och en handröta visas när pekbilderna är längre bort

Många integrerande appar följer indatamönster som liknar Mixed Reality Start.  Läs mer om att använda handindata [på HoloLens (första gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) och [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Observera att vissa typer av handske inte fungerar med handspårning om du använder handske.  Ett vanligt exempel är svarta handskes, som tenderar att absorbera IR-ljus och inte hämtas av djupkameran.  Om ditt arbete omfattar handskes rekommenderar vi att du provar en ljusare färg, till exempel blå eller grå.  Ett annat exempel är stora baggy gloves, som tenderar att dölja formen på din hand. Vi rekommenderar att du använder så välformspassning som möjligt för bästa resultat.

Om ditt visir har fingeravtryck eller smet kan du använda mikrofiberrensningen som medkom med HoloLens för att rensa visor-programmet.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens svarar inte på mina röstkommandon

Om Cortana inte svarar på dina röstkommandon kontrollerar du att Cortana är aktiverat. I listan Alla appar **Cortana-menyn**  >  **Notebook-inställningar**  >    >  **för att** göra ändringar. Mer information om vad du kan säga finns i [Använda din röst med HoloLens](hololens-cortana.md).

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Jag kan inte placera hologram eller se hologram som jag tidigare har placerat

Om HoloLens inte kan mappa eller läsa in ditt utrymme går det in i begränsat läge och du kan inte placera hologram eller se hologram som du har placerat. Här är några saker du kan prova:

- Se till att det finns tillräckligt med ljus i din miljö så att HoloLens kan se och mappa utrymmet.
- Kontrollera att du är ansluten till ett Wi-Fi nätverk. Om du inte är ansluten till Wi-Fi kan HoloLens inte identifiera och läsa in ett känt utrymme.
- Om du behöver skapa ett nytt utrymme ansluter du till Wi-Fi och startar sedan om HoloLens.
- Om du vill se om rätt utrymme är aktivt eller om du vill läsa in ett blanksteg manuellt går du **till**  >  **Inställningar**  >  **Systemutrymmen**.
- Om rätt utrymme läses in och du fortfarande har problem kan utrymmet vara skadat. Åtgärda problemet genom att välja blanksteg och sedan ta **bort**. När du har tagit bort utrymmet börjar HoloLens mappa din miljö och skapa ett nytt utrymme.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Min HoloLens kan inte se vilket utrymme jag är i

Om HoloLens inte kan identifiera och läsa in det utrymme som du är i automatiskt kontrollerar du följande faktorer:

- Kontrollera att du är ansluten till Wi-Fi
- Kontrollera att det finns gott om ljus i rummet
- Se till att det inte har skett några större förändringar i miljön.

Du kan också läsa in ett utrymme manuellt eller hantera dina utrymmen genom att gå **till**  >  **Inställningar**  >  **Systemutrymmen**.

## <a name="im-getting-a-low-disk-space-error"></a>Jag får ett felmeddelande om "lite diskutrymme"

Du måste frigöra lagringsutrymme genom att göra något av följande:

- Ta bort vissa blanksteg som inte används. Gå till **Inställningar**  >    >  **Systemutrymmen**, välj ett utrymme som du inte längre behöver och välj sedan **Ta bort.**
- Ta bort några av de hologram som du har placerat.
- Ta bort några bilder och videor från appen Foton.
- Avinstallera några appar från HoloLens. I listan **Alla appar** trycker du på och håller ned den app som du vill avinstallera och väljer sedan **Avinstallera.**

## <a name="my-hololens-cant-create-a-new-space"></a>Min HoloLens kan inte skapa ett nytt utrymme

Det mest sannolika problemet är att du har ont om lagringsutrymme. Prova något av de [tidigare tipsen](#im-getting-a-low-disk-space-error) för att frigöra diskutrymme.

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens-emulatorn fungerar inte

Information om HoloLens-emulatorn finns i vår utvecklardokumentation.  Läs mer om felsökning [av HoloLens-emulatorn](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
