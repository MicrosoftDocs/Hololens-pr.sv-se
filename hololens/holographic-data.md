---
title: Hitta och spara filer på HoloLens
description: Lär dig hur du använder Utforskaren på HoloLens för att öppna, visa och hantera filer på din enhet med mixad verklighet.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636188"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="a6dd2-104">Hitta, öppna och spara filer på HoloLens</span><span class="sxs-lookup"><span data-stu-id="a6dd2-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="a6dd2-105">Filer som du skapar HoloLens, inklusive foton och videor, sparas direkt på din HoloLens enhet.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="a6dd2-106">Visa och hantera dem på samma sätt som du hanterar filer på Windows 10:</span><span class="sxs-lookup"><span data-stu-id="a6dd2-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="a6dd2-107">Använda appen Utforskaren åtkomst till lokala mappar.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="a6dd2-108">I en applagring.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-108">Within an app's storage.</span></span>
- <span data-ttu-id="a6dd2-109">I en särskild mapp (till exempel video- eller musikbiblioteket).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="a6dd2-110">Använda en lagringstjänst som innehåller en app och filväljare (till exempel OneDrive).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="a6dd2-111">Använd en stationär dator som är ansluten till HoloLens med hjälp av en USB-kabel med stöd för MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="a6dd2-112">Visa filer på HoloLens med Utforskaren</span><span class="sxs-lookup"><span data-stu-id="a6dd2-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="a6dd2-113">Gäller för alla HoloLens 2 enheter och HoloLens (första generationen) från och med [Windows 10 april 2018-uppdateringen (RS4) för HoloLens](/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="a6dd2-114">Använd Utforskaren på HoloLens för att visa och hantera filer på enheten, inklusive 3D-objekt, dokument och bilder.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="a6dd2-115">Gå till **Starta**   >  **Alla appar**   >  **Utforskaren** att komma igång.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="a6dd2-116">Om det inte finns några filer i Utforskaren väljer du **Den här enheten** i det övre vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="a6dd2-117">Om du inte ser några filer i Utforskaren kan filtret Senaste vara aktivt (klockikonen är markerad i det vänstra fönstret).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="a6dd2-118">Du kan åtgärda detta genom att **välja ikonen** Detta enhetsdokument i den vänstra rutan (under klockikonen) eller öppna menyn och välja Den **här enheten.**</span><span class="sxs-lookup"><span data-stu-id="a6dd2-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="a6dd2-119">Hitta och visa dina foton och videor</span><span class="sxs-lookup"><span data-stu-id="a6dd2-119">Find and view your photos and videos</span></span>

<span data-ttu-id="a6dd2-120">[Med Mixed Reality Capture](holographic-photos-and-videos.md) kan du ta foton och videor med mixad verklighet HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="a6dd2-121">Dessa foton och videor sparas i enhetens mapp kamerarulle.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="a6dd2-122">Du kan komma åt foton och videor som tagits med HoloLens genom att:</span><span class="sxs-lookup"><span data-stu-id="a6dd2-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="a6dd2-123">åtkomst till kamerarullen direkt via [Photos appen](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="a6dd2-124">ladda upp foton och videor till molnlagring genom att synkronisera dina foton och videor till OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="a6dd2-125">med hjälp Inspelning av mixad verklighet sidan för [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="a6dd2-126">Appen Foton</span><span class="sxs-lookup"><span data-stu-id="a6dd2-126">Photos app</span></span>

<span data-ttu-id="a6dd2-127">Appen Photos är en av standardapparna på **Start-menyn** och levereras inbyggt med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="a6dd2-128">Läs mer om [hur du använder Photos för att visa innehåll.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="a6dd2-129">Du kan också installera [OneDrive appen](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) från Microsoft Store synkronisera foton till andra enheter.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="a6dd2-130">OneDrive app</span><span class="sxs-lookup"><span data-stu-id="a6dd2-130">OneDrive app</span></span>

<span data-ttu-id="a6dd2-131">[OneDrive](https://onedrive.live.com/) kan du komma åt, hantera och dela dina foton och videor med valfri enhet och med alla användare.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="a6dd2-132">Om du vill komma åt foton och videor som HoloLens på [OneDrive du appen från](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="a6dd2-133">När du har laddat ned OneDrive appen och **Inställningar**  >  **kamerauppladdning** och aktiverar **Kamerauppladdning.**</span><span class="sxs-lookup"><span data-stu-id="a6dd2-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="a6dd2-134">Anslut till en dator</span><span class="sxs-lookup"><span data-stu-id="a6dd2-134">Connect to a PC</span></span>

<span data-ttu-id="a6dd2-135">Om din HoloLens kör uppdateringen från Windows 10 april [2018](/windows/mixed-reality/release-notes-april-2018) eller senare kan du ansluta din HoloLens till en Windows 10-dator med hjälp av en USB-kabel för att bläddra bland foton och videor på enheten med hjälp av MTP (media transfer protocol).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="a6dd2-136">Du måste se till att enheten är upplåst för att bläddra i filer om du har en PIN-kod eller ett lösenord som har ställts in på enheten.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="a6dd2-137">Om du har aktiverat [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal)kan du använda den för att bläddra, hämta och hantera foton och videor som lagras på enheten.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="a6dd2-138">Komma åt filer i en app</span><span class="sxs-lookup"><span data-stu-id="a6dd2-138">Access files within an app</span></span>

<span data-ttu-id="a6dd2-139">Om ett program sparar filer på enheten kan du använda programmet för att komma åt dem.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="a6dd2-140">Begära filer från en annan app</span><span class="sxs-lookup"><span data-stu-id="a6dd2-140">Requesting files from another app</span></span>

<span data-ttu-id="a6dd2-141">Ett program kan begära att spara en fil eller öppna en fil från en annan app med hjälp av [filväljare](/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="a6dd2-142">Kända mappar</span><span class="sxs-lookup"><span data-stu-id="a6dd2-142">Known folders</span></span>

<span data-ttu-id="a6dd2-143">HoloLens har stöd för ett antal [kända mappar som](/windows/mixed-reality/app-model#known-folders) appar kan begära åtkomstbehörighet till.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="a6dd2-144">Visa HoloLens filer på datorn</span><span class="sxs-lookup"><span data-stu-id="a6dd2-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="a6dd2-145">På samma sätt som med andra mobila enheter ansluter du HoloLens till din stationära dator med hjälp av MTP (Media Transfer Protocol) och öppnar Utforskaren på datorn för att få åtkomst till dina HoloLens bibliotek för enkel överföring.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="a6dd2-146">Så här ser HoloLens-filer Utforskaren på datorn:</span><span class="sxs-lookup"><span data-stu-id="a6dd2-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="a6dd2-147">Logga in på HoloLens och anslut den sedan till datorn med hjälp av USB-kabeln som medförde HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="a6dd2-148">Välj **Öppna enhet för att visa filer Utforskaren** eller öppna Utforskaren på datorn och navigera till enheten.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="a6dd2-149">Om du vill se information HoloLens högerklickar du på enhetsnamnet i Utforskaren på datorn och väljer **egenskaper.**</span><span class="sxs-lookup"><span data-stu-id="a6dd2-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6dd2-150">HoloLens (första generationen) stöder inte anslutning till externa hårddiskar eller SD-kort.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="a6dd2-151">Synkronisera till molnet</span><span class="sxs-lookup"><span data-stu-id="a6dd2-151">Sync to the cloud</span></span>

<span data-ttu-id="a6dd2-152">Om du vill synkronisera foton och andra filer HoloLens till molnet installerar och installerar du OneDrive på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="a6dd2-153">Du kommer OneDrive genom att söka efter den i Microsoft Store på din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="a6dd2-154">HoloLens inte filer och data i appen, så det är en bra idé att spara viktiga saker i OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="a6dd2-155">På så sätt säkerhetskopieras din information om du återställer enheten eller avinstallerar en app.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
