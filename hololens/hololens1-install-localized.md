---
title: Installera lokaliserade versioner av HoloLens
description: Lär dig hur du installerar lokaliserade versioner av HoloLens (första generationen), inklusive kinesiska och japanska versioner.
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
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427733"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installera lokaliserade versioner av HoloLens (första gen)

För att kunna växla till den kinesiska eller japanska versionen av HoloLens måste du använda Windows Device Recovery Tool (WDRT) för att ladda ned versionen för språket på en dator och sedan installera den på din HoloLens.

> [!IMPORTANT]
> Med WDRT för att installera kinesiska eller japanska versioner av HoloLens befintliga data, till exempel personliga filer och inställningar, från HoloLens. 

1. Ladda ned och installera verktyget Windows [(WDRT) på datorn.](https://support.microsoft.com/help/12379)
1. Ladda ned paketet för det språk du vill ha till datorn: [Förenklad kinesiska](https://aka.ms/hololensdownload-ch) eller [japanska.](https://aka.ms/hololensdownload-jp)
1. När nedladdningen är klar väljer **du Utforskaren**  >  **Hämtningsbara filer.** Högerklicka på den komprimerade mappen som du precis laddade ned och välj **Extrahera alla**  >  **extrahera** för att packa upp den.
1. Anslut din HoloLens datorn med hjälp av den mikro-USB-kabel som den levererade med. (Även om du har använt andra kablar för att ansluta HoloLens fungerar den här bäst.)
1. När verktyget automatiskt identifierar HoloLens väljer du Microsoft HoloLens panelen.
1. På nästa skärm väljer du **Manuellt paketval** och väljer installationsfilen som finns i mappen som   du packade upp i steg 4. (Leta efter en fil som har filnamnstillägget ".ffu".) 
1. Välj **Installera programvara** och följ instruktionerna. 
1. När bygget har installerats HoloLens installationen automatiskt. Sätt på enheten och följ installationsanvisningarna. 

När du är klar med installationen går du **till Inställningar** Update & Security Windows Insider Program och kontrollerar att du är konfigurerad att ta emot de senaste  >    >  förhandsversionerna. Precis som de engelska förhandsversionerna Windows Insider Program de kinesiska och japanska versionerna av HoloLens uppdaterade med de senaste förhandsversionerna.

> [!NOTE]
>  
> - Du kan inte använda Inställningar för att ändra systemspråket mellan engelska, japanska och kinesiska. Att flasha en ny version är det enda sätt som stöds för att ändra enhetens systemspråk.
> - Du kan använda Pinyin-tangentbordet på skärmen för att ange förenklad kinesiska eller japanska text, men det går inte att använda ett Bluetooth-maskinvarutangentbord för att skriva förenklad kinesiska eller japanska text för närvarande.  Men på kinesiska eller japanska HoloLens kan du fortsätta att använda ett Bluetooth-tangentbord för att skriva på engelska (om du vill växla ett maskinvarutangentbord för att skriva på engelska trycker du på ~-tangenten).
