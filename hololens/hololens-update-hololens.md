---
title: Uppdatera HoloLens
description: Lär dig hur du kontrollerar ditt HoloLens-versionsnummer, håller dig uppdaterad med enhetsuppdateringar, går med i Insiders-programmet och återställningsuppdateringar.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378822"
---
# <a name="update-hololens"></a><span data-ttu-id="2b0f3-104">Uppdatera HoloLens</span><span class="sxs-lookup"><span data-stu-id="2b0f3-104">Update HoloLens</span></span>

<span data-ttu-id="2b0f3-105">HoloLens använder Windows Update, precis som andra Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="2b0f3-106">HoloLens laddar automatiskt ned och installerar systemuppdateringar när den är ansluten till ström och ansluten till Internet, även när den är i vänteläge.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="2b0f3-107">Den här artikeln går igenom HoloLens-verktyg för:</span><span class="sxs-lookup"><span data-stu-id="2b0f3-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="2b0f3-108">visa din aktuella operativsystemversion (build-nummer)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="2b0f3-109">söka efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="2b0f3-109">checking for updates</span></span>
- <span data-ttu-id="2b0f3-110">uppdatera HoloLens manuellt</span><span class="sxs-lookup"><span data-stu-id="2b0f3-110">manually updating HoloLens</span></span>
- <span data-ttu-id="2b0f3-111">gå tillbaka till en äldre uppdatering</span><span class="sxs-lookup"><span data-stu-id="2b0f3-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="2b0f3-112">Kontrollera operativsystemversionen (build-nummer)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="2b0f3-113">Du kan verifiera systemversionsnumret (build-nummer) genom att öppna appen Inställningar och välja **System**  >  **About (System om).**</span><span class="sxs-lookup"><span data-stu-id="2b0f3-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="2b0f3-114">Söka efter uppdateringar och uppdatera manuellt</span><span class="sxs-lookup"><span data-stu-id="2b0f3-114">Check for updates and manually update</span></span>

<span data-ttu-id="2b0f3-115">Du kan söka efter uppdateringar när som helst i inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="2b0f3-116">Så här ser du tillgängliga uppdateringar och söker efter nya uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="2b0f3-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="2b0f3-117">Öppna appen **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="2b0f3-118">Gå till **Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="2b0f3-119">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-119">Select **Check for updates**.</span></span>

<span data-ttu-id="2b0f3-120">Om en uppdatering är tillgänglig börjar den ladda ned den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="2b0f3-121">När nedladdningen är klar väljer du knappen **Starta om nu** för att utlösa installationen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="2b0f3-122">Om enheten är lägre än 40 % och den inte är ansluten kommer omstarten inte att starta om installationen av uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="2b0f3-123">När hololens installerar uppdateringen visas snurrande kugghjul och en förloppsindikator.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="2b0f3-124">Stäng inte av hololens under den här tiden.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="2b0f3-125">Den startas om automatiskt när installationen är klar.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="2b0f3-126">HoloLens tillämpar en uppdatering i taget.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="2b0f3-127">Om din HoloLens är mer än en version bakom den senaste kan du behöva gå igenom uppdateringsprocessen flera gånger för att få den helt uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="2b0f3-128">Gå tillbaka till en tidigare version – HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="2b0f3-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="2b0f3-129">I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens-programvaran.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="2b0f3-130">Du kan göra detta med hjälp av Advanced Recovery Companion för att återställa din HoloLens till den tidigare versionen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0f3-131">Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="2b0f3-132">Följ dessa steg om du vill gå tillbaka till en tidigare version av HoloLens 2:</span><span class="sxs-lookup"><span data-stu-id="2b0f3-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="2b0f3-133">Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="2b0f3-134">På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="2b0f3-135">Ladda ned [den senaste HoloLens 2-versionen](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="2b0f3-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="2b0f3-136">När du är klar med dessa nedladdningar öppnar du **Hämtningsbara filer**  >  **i Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="2b0f3-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="2b0f3-137">Högerklicka på den komprimerade mappen som du precis har laddat ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2b0f3-138">Anslut din HoloLens till datorn med hjälp av en USB-A till USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="2b0f3-139">(Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2b0f3-140">Advanced Recovery Companion identifierar automatiskt din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="2b0f3-141">Välj **Microsoft HoloLens** panelen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="2b0f3-142">På nästa skärm väljer du **Manuellt paketval** och väljer sedan installationsfilen som finns i mappen som du packade upp i steg 4.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="2b0f3-143">(Leta efter en fil med filnamnstillägget .ffu.)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="2b0f3-144">Välj **Installera programvara** och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="2b0f3-145">Gå tillbaka till en tidigare version – HoloLens (första gen)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="2b0f3-146">I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens-programvaran.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="2b0f3-147">Du kan göra detta med hjälp av återställningsverktyget för Windows-enheter för att återställa din HoloLens till den tidigare versionen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0f3-148">Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="2b0f3-149">Följ dessa steg om du vill gå tillbaka till en tidigare version av HoloLens 1:</span><span class="sxs-lookup"><span data-stu-id="2b0f3-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="2b0f3-150">Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="2b0f3-151">Ladda ned Windows [Device Recovery Tool (WDRT) på datorn.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="2b0f3-152">Ladda ned [holoLens Anniversary Update-återställningspaketet](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="2b0f3-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="2b0f3-153">När hämtningarna är klara öppnar du  >  **Hämtningsbara filer i Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="2b0f3-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="2b0f3-154">Högerklicka på den komprimerade mappen som du precis laddade ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2b0f3-155">Anslut din HoloLens till datorn med hjälp av den mikro-USB-kabel som den medkom med.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="2b0f3-156">(Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2b0f3-157">WDRT identifierar automatiskt din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="2b0f3-158">Välj **Microsoft HoloLens** panelen.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="2b0f3-159">På nästa skärm väljer du **Manuellt paketval och** väljer installationsfilen i mappen som du packade upp i steg 4.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="2b0f3-160">(Leta efter en fil med filnamnstillägget .ffu.)</span><span class="sxs-lookup"><span data-stu-id="2b0f3-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="2b0f3-161">Välj **Installera programvara** och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0f3-162">Om WDRT inte identifierar hololens kan du prova att starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="2b0f3-163">Om det inte fungerar väljer du **Min enhet identifierades inte,** **Microsoft HoloLens** och följer sedan anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="2b0f3-164">Windows Insider Program på HoloLens</span><span class="sxs-lookup"><span data-stu-id="2b0f3-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="2b0f3-165">Vill du se de senaste funktionerna i HoloLens?</span><span class="sxs-lookup"><span data-stu-id="2b0f3-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="2b0f3-166">I så fall ansluter du till Windows Insider Program; du får tillgång till förhandsversioner av HoloLens-programuppdateringar innan de blir tillgängliga för allmänheten.</span><span class="sxs-lookup"><span data-stu-id="2b0f3-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="2b0f3-167">[Hämta Windows Insider förhandsgranskning för Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="2b0f3-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
