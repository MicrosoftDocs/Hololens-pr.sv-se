---
title: Använda HoloLens-klickaren
description: Den här artikeln beskriver hur du använder HoloLens-klickaren, inklusive klickkoppling, debitering och återställning.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378922"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>Använda HoloLens-klickaren (första gen)

Klickaren har utformats specifikt för HoloLens (första generationen) och ger dig ett annat sätt att interagera med hologram. Den levereras med HoloLens (1:a gen) i en separat ruta.

Använd den i stället för handgester för att välja, rulla, flytta och ändra storlek på appar.

## <a name="clicker-hardware-and-pairing"></a>Clicker-maskinvara och parkoppling

HoloLens-klickaren (1:a gen) har en fingerloop som gör det enklare att hålla och en indikatorlampa.

![The HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Lampor för klickerindikator

Det här är vad lamporna på klickaren betyder.

- **Blinkning av vitt**. Klickaren är i parkopplingsläge.
- **Snabbt blinkande vitt**. Parkopplingen lyckades.
- **Helvitt**. Klickaren laddas.
- **Blinkande gult**. Batteriet är lågt.
- **Solid gult** sken . Klickaren stötte på ett fel och du måste starta om den. När du trycker på parkopplingsknappen klickar du och håller ned i 15 sekunder.

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>Koppla klickaren med din HoloLens (första gen)

1. Använd bloom-gesten för att **gå till Start** och välj sedan **Inställningar**  >  **Enheter** och kontrollera att Bluetooth är på.
1. Tryck på och håll ned parkopplingsknappen på klickknappen tills statuslampan blinkar vit.
1. På parkopplingsskärmen väljer du **Klicka på**  >  **par.**

### <a name="charge-the-clicker"></a>Debitera klickaren

När klickarbatteriet är lågt blinkar batteriindikatorn gult. Anslut Micro USB-kabeln till en USB-strömförsörjning för att ladda enheten.

## <a name="use-the-clicker-with-hololens-1st-gen"></a>Använda klickern med HoloLens (första gen)

### <a name="hold-the-clicker"></a>Håll kvar klickern

För att sätta på klickern drar du loopen över din ring eller mitt finger så att Micro USB-porten står mot handleden. Vila din tumme i indraget.

![Så här håller du klickern](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Klickgester

Klickgester är små handledsrotationer, inte de större rörelser som används för HoloLens handgester. HoloLens känner igen dina gester och klick även om [](hololens1-basic-usage.md)klickaren är utanför gesterramen, så att du kan hålla klickaren på den position som är mest bekväm för dig.

- **Välj**. Om du vill välja ett hologram, en knapp eller ett annat element kan du titta på det och sedan klicka på det.

- **Klicka och håll ned**. Klicka och håll ned tummarna på knappen för att göra några av de saker som du skulle göra med tryck och håll ned, till exempel flytta eller ändra storlek på ett hologram.

- **Rulla .** Välj Rullningsverktyget i **appfältet.** Klicka och håll ned och rotera sedan klickaren uppåt, nedåt, vänster eller höger. Rulla snabbare genom att flytta din hand längre från mitten av rullningsverktyget.

- **Zooma**. I appfältet väljer du **Zoom Tool**. Klicka och håll ned och rotera sedan klickern uppåt för att zooma in eller ned för att zooma ut.

> [!TIP]
> Om du vill zooma in eller ut Microsoft Edge genom att titta på en sida och dubbelklicka.

## <a name="restart-or-recover-the-clicker"></a>Starta om eller återställa klickaren

Här är några saker att prova om HoloLens-klickaren inte svarar eller inte fungerar bra.

### <a name="restart-the-clicker"></a>Starta om klickaren

Använd penntipset för att trycka på och hålla ned parkopplingsknappen. Samtidigt klickar du och håller ned klickern i 15 sekunder. Om klickaren redan har kopplats ihop med hololens förblir den parkopplad när den har startats om.

Om klickaren inte aktiverar eller startar om kan du prova att debitera den med hjälp av HoloLens-programmet. Om batteriet är mycket lågt kan det ta några minuter innan den vita indikatorn tänds.

### <a name="re-pair-the-clicker"></a>Parkoppla klickaren på ett annat sätt

Välj **Inställningar**  >  **enheter** och välj klickaren. Välj **Ta** bort, vänta några sekunder och koppla sedan klickaren igen.

### <a name="recover-the-clicker"></a>Återställa klickaren

Om du inte åtgärdar problemet genom att starta om och koppla ihop klickaren igen kan verktyget Windows Device Recovery hjälpa dig att återställa det. Återställningsprocessen kan ta lite tid och installerar den senaste versionen av klickprogrammet. Om du vill använda verktyget behöver du en dator som kör Windows 10 eller senare som har minst 4 GB ledigt lagringsutrymme.

Så här återställer du klickern:

1. Ladda ned och installera [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) på datorn.
1. Anslut klickaren till datorn med hjälp av Micro USB-kabeln som medkom med HoloLens.
1. Kör windows-verktyget för enhetsåterställning och följ instruktionerna.

Om klickaren inte identifieras automatiskt väljer du **Min enhet** har inte identifierats och följer instruktionerna för att föra enheten i återställningsläge.
