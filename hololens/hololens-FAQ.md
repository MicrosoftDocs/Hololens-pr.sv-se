---
title: Vanliga frågor och svar om HoloLens-enheter och hologram
description: Har du en snabb fråga om HoloLens eller interagerar du med hologram?  Den här artikeln innehåller ett snabbt svar och fler resurser.
keywords: hololens, faq, known issue, help
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924034"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Felsökning av hologram och interaktioner

Den här artikeln felsöker problem med att placera hologram, arbeta med utrymmen och rapportera problem med hologram.

När du har problem bör du se till att:
- Prova [att starta om den](hololens-restart-recover.md) för att se om det åtgärdar något.
- Innan du felsöker ska du se till att HoloLens [debiteras](hololens2-charging.md) (debiteras i minst en timme). 


Använd feedbackappen för att skicka information om problemet till oss. Du hittar feedbackappen på [ **Start-menyn**](holographic-home.md). 

Tips om hur du använder HoloLens finns i [Justera anpassning.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Det går inte att skapa nya blanksteg](#new-spaces-cant-be-created)
- [Blanksteg kan inte identifieras eller läsas in](#spaces-cant-be-identified-or-loaded)
- [Hur gör jag för att ta bort alla blanksteg?](#how-do-i-delete-all-spaces)
- [Hologram ser inte rätt ut eller flyttas runt](#holograms-dont-look-right-or-are-moving-around)
- [Meddelandet "Hitta ditt utrymme"](#finding-your-space-message)
- [Förväntade hologram visas inte i mitt utrymme](#expected-holograms-arent-showing-in-my-space)
- [Det går inte att placera hologram eller se hologram som placerats tidigare](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologram försvinner eller är inkapslade i andra hologram eller objekt](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologram visas på andra sidan av en vägg](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [När du har placerat ett hologram på en vägg verkar det flyta](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Appar visas för nära efter att de har flyttats](#apps-appear-too-close-after-moving-them)
- [Rapportera problem med instabila eller inexakta hologram](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Det går inte att skapa nya blanksteg

Det mest sannolika problemet är att du börjar få ont om lagringsutrymme. [Frigör diskutrymme och](hololens-troubleshooting.md#low-disk-space-error) försök sedan igen.

[Tillbaka till listan](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Blanksteg kan inte identifieras eller läsas in

Om hololens inte kan identifiera och läsa in det utrymme som du använder automatiskt kontrollerar du följande faktorer:

- Kontrollera att du är ansluten till Wi-Fi
- Se till att det finns gott om ljus i rummet
- Se till att det inte har skett några större förändringar i miljön.

Du kan också läsa in ett utrymme manuellt eller hantera dina utrymmen genom att gå **till**  >  **Inställningar**  >  **Systemutrymmen**.

[Tillbaka till listan](#list)

## <a name="how-do-i-delete-all-spaces"></a>Hur gör jag för att ta bort alla blanksteg?

*Kommer snart*

[Tillbaka till listan](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologram ser inte rätt ut eller flyttas runt

Om dina hologram inte ser rätt ut (till exempel om de är jitteriga eller skakiga, eller om du ser svarta korrigeringar ovanpå dem) kan du prova någon av följande korrigeringar:

- [Rensa enhetsvisorn och](hololens1-hardware.md#care-and-cleaning) se till att inget blockerar sensorerna.
- Se till att du är i ett välbelyst rum som inte har så mycket direkt belysning.
- Prova att gå runt och titta på din miljö så att HoloLens kan genomsöka dem mer fullständigt.
- Om du har placerat många hologram kan du prova att ta bort några.

Om du fortfarande har problem kan du prova att köra kalibreringsappen. Den här appen kalibrerar HoloLens så att du kan hålla dina hologram så bra som möjligt. Det gör du genom att gå **till**  >  **Inställningar**  >  **Systemverktyg.** Under **Kalibrering** väljer du **Öppna kalibrering**.

[Tillbaka till listan](#list)

## <a name="finding-your-space-message"></a>Meddelandet "Hitta ditt utrymme"

När HoloLens lär sig eller läser in ett utrymme kan du se ett kort meddelande som säger "Hitta ditt utrymme". Om det här meddelandet visas i mer än några sekunder visas ett annat meddelande under Start-menyn där det står "Letar fortfarande efter ditt utrymme".

Dessa meddelanden innebär att HoloLens har problem med att mappa ditt utrymme. När detta inträffar kan du öppna appar, men du kan inte placera hologram i din miljö.

Om du ser dessa meddelanden ofta kan du prova en eller flera av följande korrigeringar:

- Se till att du är i ett välbelyst rum som inte har så mycket direkt belysning.
- Kontrollera att enhetsvisorn är ren. [Lär dig hur du rensar din visor.](hololens1-hardware.md#care-and-cleaning)
- Kontrollera att du har en stark Wi-Fi signal. Om du anger en ny miljö som inte Wi-Fi eller en svag Wi-Fi signal kan HoloLens inte hitta ditt utrymme. Kontrollera din Wi-Fi genom att gå till **Inställningar**  >  **&amp; Nätverkets**  >  **Internet-Wi-Fi**.
- Försök att flytta långsammare.

[Tillbaka till listan](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Förväntade hologram visas inte i mitt utrymme

Om du inte ser hologrammen som du har placerat, eller om du ser några som du inte förväntar dig, kan du prova en eller flera av följande korrigeringar:

- Tänd några lampor. HoloLens fungerar bäst i välbelysta utrymmen.
- Ta bort hologram som du inte behöver genom att gå till **Inställningar**  >  **System**  >  **Hologram**  >  **Ta bort hologram i närheten.** Om det behövs kan du också välja **Ta bort alla hologram**.

  > [!NOTE]
  > Om layouten eller belysningen i utrymmet ändras avsevärt kan enheten ha problem med att identifiera ditt utrymme och visa dina hologram.

[Tillbaka till listan](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Det går inte att placera hologram eller se hologram som placerats tidigare

Om HoloLens inte kan mappa eller läsa in ditt utrymme går det in i begränsat läge och du kan inte placera hologram eller se hologram som du har placerat. Här är några saker du kan prova:

- Se till att det finns tillräckligt med ljus i din miljö så att HoloLens kan se och mappa utrymmet.
- Ställ dig mellan en och tre meter från den plats där du försöker placera hologrammet.
- Placera inte hologram på svarta eller reflerande ytor.
- Kontrollera att du är ansluten till ett Wi-Fi nätverk. Om du inte är ansluten till Wi-Fi kan HoloLens inte identifiera och läsa in ett känt utrymme.
- Gå igenom rum så att HoloLens kan genomsöka din miljö igen. Om du vill se vad som redan genomsökts trycker du i luften för att visa kartnätsbilden.
- Om du behöver skapa ett nytt utrymme ansluter du till Wi-Fi och startar sedan om HoloLens.
- Om du vill se om rätt utrymme är aktivt eller om du vill läsa in ett utrymme manuellt går du **till**  >  **Inställningar**  >  **Systemutrymmen**.
- Om rätt utrymme läses in och du fortfarande har problem kan utrymmet vara skadat. Åtgärda problemet genom att markera utrymmet och sedan välja Ta **bort**. När du har tagit bort utrymmet börjar HoloLens mappa din miljö och skapa ett nytt utrymme.

[Tillbaka till listan](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologram försvinner eller är inkapslade i andra hologram eller objekt

Om du är för nära ett hologram försvinner det tillfälligt för &mdash; att återställa hologrammet. Du behöver bara flytta från det. Om du har placerat flera hologram nära varandra kan vissa försvinna. Prova att ta bort några.

Hologram kan också blockeras eller vara omslutna av andra hologram eller av objekt som väggar. Om detta inträffar kan du prova någon av följande korrigeringar:

- Om hologrammet är inkapslade i ett annat hologram flyttar du det inkapslade hologrammet till en annan plats. Det gör du genom att **välja Justera** och sedan trycka och hålla kvar för att placera den.
- Om hologrammet är omslutet på en vägg väljer du Justera **och** går sedan mot väggen tills hologrammet visas. Tryck och håll ned och dra hologrammet framåt och från väggen.
- Om du inte kan flytta hologrammet med hjälp av gester kan du använda rösten för att ta bort det. Titta på hologrammet och säg "Ta bort". Öppna sedan hologrammet och placera det på en ny plats.

[Tillbaka till listan](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologram visas på andra sidan av en vägg

Om du är mycket nära en vägg, eller om HoloLens inte har skannat väggen ännu, kan du se hologram som finns i nästa rum. Om du vill genomsöka vägg ska du stå mellan en och tre meter från väggen och titta på den.

Ett svart eller reflektivt objekt (till exempel en svartoffa eller ett kylskåp av metall) nära väggen kan orsaka problem när HoloLens försöker genomsöka väggen. Om det finns ett sådant objekt genomsöker du den andra sidan av väggen.

[Tillbaka till listan](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>När du har placerat ett hologram på en vägg verkar det flyta

Ett hologram som du placerar på en vägg verkar vanligtvis vara en tum eller så från väggen. Om det verkar vara längre bort kan du prova en eller flera av följande korrigeringar:

- När du placerar ett hologram på en vägg ska du stå mellan en och tre meter från väggen och ansiktet mot väggen direkt på.
- Tryck i luften på väggen för att visa kartnätsgrafiken. Se till att näten är justerade mot väggen. Om den inte gör det tar du bort hologrammet, genomsökar vägg igen och försöker sedan igen.
- Om problemet kvarstår kör du kalibreringsappen. Du hittar den i **Inställningar**  >    >  **SystemVerktyg**.

[Tillbaka till listan](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Appar visas för nära efter att de har flyttats

Prova att gå runt och titta på det område där du placerar appen så att HoloLens genomsöker området från olika vinklar. [Att rensa enhetsvisor-programmet](hololens1-hardware.md#care-and-cleaning) kan också vara till hjälp.

[Tillbaka till listan](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Rapportera problem med instabila eller inexakta hologram
 
1. Spela in och [Inspelning av mixad verklighet video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) om problemet. Den här videon kan senare laddas upp via Feedbackhubben som en bifogad fil.  
1. Aktivera fullständig telemetri via appen **Inställningar** – > sekretessdiagnostik & feedback och under Valfria  ->   **diagnostikdata** ser du till att växlingsknappen är inställd på **På**
1. Hämta de senaste korrigeringarna för hologramskalning och stabilitet genom att uppdatera till det senaste [Windows Holographic OS(20H2 eller senare)](hololens-release-notes.md#windows-holographic-version-20h2). När du har uppdaterat utför du följande:
    1. Ta bort alla Hologram via **inställningsappen** -> **System**  ->  **Holograms** -> sedan Ta bort alla **hologram** och börja med en ny karta.
    1. Skapa en ny karta över ditt utrymme genom att använda HoloLens och gå runt i rummet och titta på alla områden och ytor i utrymmet. Gör detta i 2–3 minuter.
    1. Utför IPD-kalibrering. Gå till **Inställningar**  >    >  **Systemverktyg**. Under **Kalibrering** väljer du **Öppna kalibrering.**
    1. Testa scenariot på ett annat sätt och se om det fortfarande finns kvar.
1. Om uppdateringen inte åtgärdar problemet kan du skicka en [Feedbackhubben problemet](hololens-feedback.md). När du har fyllt i  feedback kan du använda knappen Dela för att skapa en enkel delningslänk som kan skickas när du kontaktar supporten.

[Tillbaka till listan](#list)