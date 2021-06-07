---
title: Installera lokaliserade versioner av HoloLens
description: Lär dig hur du installerar de lokaliserade versionerna av HoloLens (första gen), inklusive kinesiska och japanska versioner.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378934"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="5120b-103">Installera lokaliserade versioner av HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="5120b-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="5120b-104">För att kunna växla till den kinesiska eller japanska versionen av HoloLens måste du använda Windows Device Recovery Tool (WDRT) för att ladda ned versionen för språket på en dator och sedan installera den på din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5120b-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5120b-105">Med WDRT för att installera de kinesiska eller japanska versionerna av HoloLens tas befintliga data, till exempel personliga filer och inställningar, bort från HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5120b-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="5120b-106">Ladda ned och installera Windows [Device Recovery Tool (WDRT) på datorn.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="5120b-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="5120b-107">Ladda ned paketet för det språk du vill ha till datorn: [Förenklad kinesiska](https://aka.ms/hololensdownload-ch) eller [japanska.](https://aka.ms/hololensdownload-jp)</span><span class="sxs-lookup"><span data-stu-id="5120b-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="5120b-108">När nedladdningen är klar väljer **du Utforskaren**  >  **Nedladdningar.**</span><span class="sxs-lookup"><span data-stu-id="5120b-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="5120b-109">Högerklicka på den zippade mappen som du precis laddade ned och välj **Extrahera alla**  >  **extrahera** för att packa upp den.</span><span class="sxs-lookup"><span data-stu-id="5120b-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="5120b-110">Anslut HoloLens till datorn med hjälp av den mikro-USB-kabel som den levererades med.</span><span class="sxs-lookup"><span data-stu-id="5120b-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="5120b-111">(Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)</span><span class="sxs-lookup"><span data-stu-id="5120b-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="5120b-112">När verktyget automatiskt identifierar hololens väljer du Microsoft HoloLens panelen.</span><span class="sxs-lookup"><span data-stu-id="5120b-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="5120b-113">På nästa skärm väljer du **Manuellt paketval** och väljer installationsfilen som finns i mappen som   du packade upp i steg 4.</span><span class="sxs-lookup"><span data-stu-id="5120b-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="5120b-114">(Leta efter en fil med filnamnstillägget ".ffu".)</span><span class="sxs-lookup"><span data-stu-id="5120b-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="5120b-115">Välj **Installera programvara** och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="5120b-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="5120b-116">När versionen har installerats startar HoloLens-installationen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5120b-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="5120b-117">Sätt på enheten och följ installationsanvisningarna.</span><span class="sxs-lookup"><span data-stu-id="5120b-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="5120b-118">När du är klar med installationen går du till Inställningar Uppdatera & Security Windows Insider Program och kontrollerar att du är konfigurerad för att ta emot de senaste  >    >  förhandsversionerna.</span><span class="sxs-lookup"><span data-stu-id="5120b-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="5120b-119">Precis som de engelska förhandsversionerna Windows Insider Program de kinesiska och japanska versionerna av HoloLens uppdaterade med de senaste förhandsversionerna.</span><span class="sxs-lookup"><span data-stu-id="5120b-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="5120b-120">Du kan inte använda appen Inställningar för att ändra systemspråket mellan engelska, japanska och kinesiska.</span><span class="sxs-lookup"><span data-stu-id="5120b-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="5120b-121">Att flasha en ny version är det enda sätt som stöds för att ändra enhetens systemspråk.</span><span class="sxs-lookup"><span data-stu-id="5120b-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="5120b-122">Även om du kan använda Pinyin-tangentbordet på skärmen för att ange förenklad kinesiska eller japanska text, stöds inte användning av ett Bluetooth-maskinvarutangentbord för att skriva förenklad kinesiska eller japanska text för närvarande.</span><span class="sxs-lookup"><span data-stu-id="5120b-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="5120b-123">På kinesiska eller japanska HoloLens kan du dock fortsätta att använda ett Bluetooth-tangentbord för att skriva på engelska (om du vill växla ett maskinvarutangentbord för att skriva på engelska trycker du på ~-tangenten).</span><span class="sxs-lookup"><span data-stu-id="5120b-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
