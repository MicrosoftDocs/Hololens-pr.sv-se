---
title: Uppdatera HoloLens 2
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924119"
---
# <a name="update-hololens-2"></a><span data-ttu-id="09aa4-104">Uppdatera HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="09aa4-104">Update HoloLens 2</span></span>

<span data-ttu-id="09aa4-105">HoloLens använder Windows Update, precis som andra Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="09aa4-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="09aa4-106">HoloLens laddar automatiskt ned och installerar systemuppdateringar när den är ansluten till ström och ansluten till Internet, även när den är i vänteläge.</span><span class="sxs-lookup"><span data-stu-id="09aa4-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="09aa4-107">Den här artikeln går igenom HoloLens-verktyg för:</span><span class="sxs-lookup"><span data-stu-id="09aa4-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="09aa4-108">visa din aktuella operativsystemversion (build-nummer)</span><span class="sxs-lookup"><span data-stu-id="09aa4-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="09aa4-109">söka efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="09aa4-109">checking for updates</span></span>
- <span data-ttu-id="09aa4-110">uppdatera HoloLens manuellt</span><span class="sxs-lookup"><span data-stu-id="09aa4-110">manually updating HoloLens</span></span>
- <span data-ttu-id="09aa4-111">gå tillbaka till en äldre uppdatering</span><span class="sxs-lookup"><span data-stu-id="09aa4-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="09aa4-112">Kontrollera operativsystemversionen (build-nummer)</span><span class="sxs-lookup"><span data-stu-id="09aa4-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="09aa4-113">Du kan verifiera systemversionsnumret (build-nummer) genom att öppna appen Inställningar och välja **System**  >  **About (System om).**</span><span class="sxs-lookup"><span data-stu-id="09aa4-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="09aa4-114">Söka efter uppdateringar och uppdatera manuellt</span><span class="sxs-lookup"><span data-stu-id="09aa4-114">Check for updates and manually update</span></span>

<span data-ttu-id="09aa4-115">Du kan söka efter uppdateringar när som helst i inställningarna.</span><span class="sxs-lookup"><span data-stu-id="09aa4-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="09aa4-116">Så här ser du tillgängliga uppdateringar och söker efter nya uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="09aa4-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="09aa4-117">Öppna appen **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="09aa4-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="09aa4-118">Gå till **Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="09aa4-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="09aa4-119">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="09aa4-119">Select **Check for updates**.</span></span>

<span data-ttu-id="09aa4-120">Om en uppdatering är tillgänglig börjar den ladda ned den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="09aa4-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="09aa4-121">När nedladdningen är klar väljer du knappen **Starta om nu** för att utlösa installationen.</span><span class="sxs-lookup"><span data-stu-id="09aa4-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="09aa4-122">Om enheten är lägre än 40 % och den inte är ansluten kommer omstarten inte att starta om installationen av uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="09aa4-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="09aa4-123">När hololens installerar uppdateringen visas snurrande kugghjul och en förloppsindikator.</span><span class="sxs-lookup"><span data-stu-id="09aa4-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="09aa4-124">Stäng inte av hololens under den här tiden.</span><span class="sxs-lookup"><span data-stu-id="09aa4-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="09aa4-125">Den startas om automatiskt när installationen är klar.</span><span class="sxs-lookup"><span data-stu-id="09aa4-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="09aa4-126">HoloLens tillämpar en uppdatering i taget.</span><span class="sxs-lookup"><span data-stu-id="09aa4-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="09aa4-127">Om din HoloLens är mer än en version bakom den senaste kan du behöva gå igenom uppdateringsprocessen flera gånger för att få den helt uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="09aa4-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="09aa4-128">Gå tillbaka till en tidigare version</span><span class="sxs-lookup"><span data-stu-id="09aa4-128">Go back to a previous version</span></span>

<span data-ttu-id="09aa4-129">I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens-programvaran.</span><span class="sxs-lookup"><span data-stu-id="09aa4-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="09aa4-130">De rekommenderade stegen är:</span><span class="sxs-lookup"><span data-stu-id="09aa4-130">The recommended steps are:</span></span>

1. <span data-ttu-id="09aa4-131">Kontakta supporten för att se om de kan åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="09aa4-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="09aa4-132">Se till **att Valfri** **eller Fullständig** telemetri är aktiverat – detta gör buggen mer användbar och enklare för tekniker att diagnostisera.</span><span class="sxs-lookup"><span data-stu-id="09aa4-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="09aa4-133">[Filfeedback](hololens-feedback.md) är så beskrivande som möjligt.</span><span class="sxs-lookup"><span data-stu-id="09aa4-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="09aa4-134">Anteckna rubriken eller använd delningsfunktionen så att du kan dela din bugg med supporten.</span><span class="sxs-lookup"><span data-stu-id="09aa4-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="09aa4-135">Kontakta [supporten.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="09aa4-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="09aa4-136">Om problemet är ett problem som måste lösas genom att gå tillbaka till en tidigare version kan de tillhandahålla FFU för att flasha enheten.</span><span class="sxs-lookup"><span data-stu-id="09aa4-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="09aa4-137">Om det inte fungerar återställer eller [omstreckar du HoloLens 2 med Advanced Recovery Companion](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="09aa4-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="09aa4-138">På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="09aa4-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="09aa4-139">Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.</span><span class="sxs-lookup"><span data-stu-id="09aa4-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="09aa4-140">Välj vilken version du vill flasha till:</span><span class="sxs-lookup"><span data-stu-id="09aa4-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="09aa4-141">Du kan ladda ned [den senaste HoloLens 2-versionen](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="09aa4-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="09aa4-142">Du kan använda standardbygget som ARC är värd för.</span><span class="sxs-lookup"><span data-stu-id="09aa4-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="09aa4-143">(Om du väljer det här alternativet hoppar du över nästa steg.)</span><span class="sxs-lookup"><span data-stu-id="09aa4-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="09aa4-144">Du kan använda ett byggstöd som du har tillgång till.</span><span class="sxs-lookup"><span data-stu-id="09aa4-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="09aa4-145">När du är klar med dessa hämtningar öppnar **du Utforskaren**  >  **hämtningsbara filer.**</span><span class="sxs-lookup"><span data-stu-id="09aa4-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="09aa4-146">Högerklicka på den komprimerade mappen som du precis har laddat ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.</span><span class="sxs-lookup"><span data-stu-id="09aa4-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="09aa4-147">Anslut din HoloLens till datorn med hjälp av en USB-A till USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="09aa4-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="09aa4-148">(Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)</span><span class="sxs-lookup"><span data-stu-id="09aa4-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="09aa4-149">Advanced Recovery Companion identifierar automatiskt din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="09aa4-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="09aa4-150">Välj **Microsoft HoloLens** panelen.</span><span class="sxs-lookup"><span data-stu-id="09aa4-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="09aa4-151">På nästa skärm väljer du **Manuellt paketval** och väljer sedan installationsfilen som finns i mappen som du packade upp i steg 4.</span><span class="sxs-lookup"><span data-stu-id="09aa4-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="09aa4-152">(Leta efter en fil med filnamnstillägget .ffu.)</span><span class="sxs-lookup"><span data-stu-id="09aa4-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="09aa4-153">Välj **Installera programvara** och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="09aa4-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="09aa4-154">Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.</span><span class="sxs-lookup"><span data-stu-id="09aa4-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="09aa4-155">Om du vill fortsätta använda den installerade versionen kan du också pausa uppdateringar [manuellt.](hololens-updates.md#pause-updates-via-device)</span><span class="sxs-lookup"><span data-stu-id="09aa4-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="09aa4-156">Detta ger teknikteamet tid att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="09aa4-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="09aa4-157">Windows Insider Program på HoloLens</span><span class="sxs-lookup"><span data-stu-id="09aa4-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="09aa4-158">Vill du se de senaste funktionerna i HoloLens?</span><span class="sxs-lookup"><span data-stu-id="09aa4-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="09aa4-159">I så fall ansluter du till Windows Insider Program; du får tillgång till förhandsversioner av HoloLens-programuppdateringar innan de blir tillgängliga för allmänheten.</span><span class="sxs-lookup"><span data-stu-id="09aa4-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="09aa4-160">[Hämta Windows Insider förhandsgranskning för Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="09aa4-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
