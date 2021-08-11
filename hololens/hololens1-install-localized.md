---
title: Installera lokaliserade versioner av HoloLens
description: Lär dig hur du installerar de lokaliserade versionerna av HoloLens (första generationen), inklusive kinesiska och japanska versioner.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661823"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installera lokaliserade versioner av HoloLens (första generationen)

För att växla till den kinesiska eller japanska versionen av HoloLens måste du använda Windows Device Recovery Tool (WDRT) för att ladda ned versionen för språket på en dator och sedan installera den på din HoloLens.

> [!IMPORTANT]
> Med WDRT för att installera de kinesiska eller japanska versionerna av HoloLens tas befintliga data, till exempel personliga filer och inställningar, bort från hololens. 

1. Ladda ned och installera Windows [Device Recovery Tool (WDRT) på datorn.](https://support.microsoft.com/help/12379)
1. Ladda ned paketet för det språk som du vill använda på datorn: [förenklad kinesiska](https://aka.ms/hololensdownload-ch) eller [japanska.](https://aka.ms/hololensdownload-jp)
1. När nedladdningen är klar väljer **du Utforskaren**  >  **hämtar**. Högerklicka på den komprimerade mappen som du precis har laddat ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.
1. Anslut din HoloLens till datorn med hjälp av den mikro-USB-kabel som den levererades med. (Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)
1. När verktyget automatiskt identifierar din HoloLens väljer du Microsoft HoloLens panelen.
1. På nästa skärm väljer du **Manuellt paketval** och väljer installationsfilen som finns i mappen som   du packade upp i steg 4. (Leta efter en fil med filnamnstillägget ".ffu".) 
1. Välj **Installera programvara** och följ instruktionerna. 
1. När versionen har installerats startar HoloLens-installationen automatiskt. Sätt på enheten och följ installationsanvisningarna. 

När du är klar med installationen går du till Inställningar Uppdatera & Security Windows Insider Program och kontrollerar att du är konfigurerad att ta emot de senaste  >    >  förhandsversionerna. Precis som de engelska förhandsversionsversionerna Windows Insider Program de kinesiska och japanska versionerna av HoloLens uppdaterade med de senaste förhandsversionerna.

> [!NOTE]
>  
> - Du kan inte använda appen Inställningar för att ändra systemspråket mellan engelska, japanska och kinesiska. Att flasha en ny version är det enda sätt som stöds för att ändra enhetens systemspråk.
> - Du kan använda Pinyin-tangentbordet på skärmen för att ange förenklad kinesiska eller japanska text, men det går inte att använda ett Bluetooth-maskinvarutangentbord för att skriva förenklad kinesiska eller japanska text för närvarande.  På kinesiska eller japanska HoloLens kan du dock fortsätta att använda ett Bluetooth-tangentbord för att skriva på engelska (om du vill växla ett maskinvarutangentbord för att skriva på engelska trycker du på ~-tangenten).
