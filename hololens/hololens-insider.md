---
title: Insiderförhandsvisning för Microsoft HoloLens
description: Lär dig hur du kommer igång med Insider-byggen och ge värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924374"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="c00b3-103">Insiderförhandsvisning för Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="c00b3-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="c00b3-104">Välkommen till de senaste Insider Preview-versionerna för HoloLens!</span><span class="sxs-lookup"><span data-stu-id="c00b3-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="c00b3-105">Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för vår nästa större operativsystemsuppdatering för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c00b3-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="c00b3-106">Windows Insider – information</span><span class="sxs-lookup"><span data-stu-id="c00b3-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="c00b3-107">Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="c00b3-108">Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="c00b3-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="c00b3-109">Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider våra byggen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="c00b3-110">Bli spänd och redo att blanda de här uppdateringarna i din verklighet.</span><span class="sxs-lookup"><span data-stu-id="c00b3-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="c00b3-111">CSP-ändringar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="c00b3-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="c00b3-112">Introducerades i Windows Insider build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="c00b3-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="c00b3-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="c00b3-113">DevDetail CSP</span></span>

<span data-ttu-id="c00b3-114">DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens-enheten.</span><span class="sxs-lookup"><span data-stu-id="c00b3-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="c00b3-115">Detta bör ungefär matcha det värde som visas på inställningsappens lagringssida.</span><span class="sxs-lookup"><span data-stu-id="c00b3-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="c00b3-116">Nedan visas den specifika nod som innehåller den här informationen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="c00b3-117">./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)</span><span class="sxs-lookup"><span data-stu-id="c00b3-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="c00b3-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="c00b3-118">DeviceStatus CSP</span></span>

<span data-ttu-id="c00b3-119">DeviceStatus CSP rapporterar nu även SSID och BSSID för WiFi-nätverk som HoloLens är aktivt ansluten till.</span><span class="sxs-lookup"><span data-stu-id="c00b3-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="c00b3-120">Nedan visas de specifika noder som innehåller den här informationen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="c00b3-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="c00b3-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="c00b3-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi*/BSSID</span><span class="sxs-lookup"><span data-stu-id="c00b3-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="c00b3-123">Exempel på syncml-blob (för MDM-leverantörer) för att fråga efter NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c00b3-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="c00b3-124">Korrigeringar och förbättringar:</span><span class="sxs-lookup"><span data-stu-id="c00b3-124">Fixes and improvements:</span></span>

- <span data-ttu-id="c00b3-125">Ett känt [problem har åtgärdats för Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="c00b3-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="c00b3-126">Åtgärdat [ett känt problem för Enhetsportalen med time out för filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="c00b3-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="c00b3-127">Börja ta emot Insider-byggen</span><span class="sxs-lookup"><span data-stu-id="c00b3-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="c00b3-128">Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="c00b3-129">Röstkommandot "Starta om enheten" fungerar bra.</span><span class="sxs-lookup"><span data-stu-id="c00b3-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="c00b3-130">Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="c00b3-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="c00b3-131">Det har uppstått en bugg i backend-delen som du kan ha stött på, vilket gör att du kommer igång igen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="c00b3-132">På en HoloLens 2-enhet går du **till**  >  **Inställningar & Security**  >  **Windows Insider Program** och väljer **Kom igång.**</span><span class="sxs-lookup"><span data-stu-id="c00b3-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="c00b3-133">Länka det konto som du använde för att registrera som Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="c00b3-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="c00b3-134">Windows Insider flyttas nu till kanaler.</span><span class="sxs-lookup"><span data-stu-id="c00b3-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="c00b3-135">Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.**</span><span class="sxs-lookup"><span data-stu-id="c00b3-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="c00b3-136">Så här ser mappningen ut: Windows Insider förklaring av kanaler Mer information finns ![ i Introduktion Windows Insider ](images/WindowsInsiderChannels.png) [kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows-bloggar.</span><span class="sxs-lookup"><span data-stu-id="c00b3-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="c00b3-137">Välj sedan **Aktiv utveckling av Windows,** välj om du vill ta emot Dev **Channel** **eller Betakanal-versioner** och granska programvillkoren.</span><span class="sxs-lookup"><span data-stu-id="c00b3-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="c00b3-138">Välj **Bekräfta > starta om nu** för att slutföra.</span><span class="sxs-lookup"><span data-stu-id="c00b3-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="c00b3-139">När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="c00b3-140">Uppdatera fel 0x80070490 för att komma runt</span><span class="sxs-lookup"><span data-stu-id="c00b3-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="c00b3-141">Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning.</span><span class="sxs-lookup"><span data-stu-id="c00b3-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="c00b3-142">Det innebär att du flyttar din Insider-kanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="c00b3-143">Steg ett – förhandsversion</span><span class="sxs-lookup"><span data-stu-id="c00b3-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="c00b3-144">Inställningar, Uppdatera & säkerhet, Windows Insider Program och välj **Kanal för förhandsversion.**</span><span class="sxs-lookup"><span data-stu-id="c00b3-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="c00b3-145">Settings, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="c00b3-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="c00b3-146">Efter uppdateringen fortsätter du till Fas två.</span><span class="sxs-lookup"><span data-stu-id="c00b3-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="c00b3-147">Steg två – Dev Channel</span><span class="sxs-lookup"><span data-stu-id="c00b3-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="c00b3-148">Inställningar, Uppdatera & säkerhet, Windows Insider Program, välj **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="c00b3-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="c00b3-149">Settings, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="c00b3-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="c00b3-150">FFU-nedladdning och flash-riktningar</span><span class="sxs-lookup"><span data-stu-id="c00b3-150">FFU download and flash directions</span></span>
<span data-ttu-id="c00b3-151">Om du vill testa med en flyg signerad ffu måste du först låsa upp enheten innan du flashar den flyg signerade ffu.</span><span class="sxs-lookup"><span data-stu-id="c00b3-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="c00b3-152">På datorn:</span><span class="sxs-lookup"><span data-stu-id="c00b3-152">On PC:</span></span>
    1. <span data-ttu-id="c00b3-153">Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="c00b3-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="c00b3-154">Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="c00b3-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="c00b3-155">På HoloLens – Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** sedan registrera dig, starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="c00b3-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="c00b3-156">Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.</span><span class="sxs-lookup"><span data-stu-id="c00b3-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="c00b3-157">Ge feedback och rapportera problem</span><span class="sxs-lookup"><span data-stu-id="c00b3-157">Provide feedback and report issues</span></span>
<span data-ttu-id="c00b3-158">Använd appen [Feedbackhubben hololens](hololens-feedback.md) för att ge feedback och rapportera problem.</span><span class="sxs-lookup"><span data-stu-id="c00b3-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="c00b3-159">Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="c00b3-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="c00b3-160">Problem med den kinesiska och japanska versionen av HoloLens bör rapporteras på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="c00b3-161">Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben komma åt mappen Dokument (välj **Ja när** du tillfrågas).</span><span class="sxs-lookup"><span data-stu-id="c00b3-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="c00b3-162">Obs! För utvecklare</span><span class="sxs-lookup"><span data-stu-id="c00b3-162">Note for developers</span></span>
<span data-ttu-id="c00b3-163">Du är välkommen och uppmanas att prova att utveckla dina program med Insider-byggen av HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c00b3-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="c00b3-164">Kom igång genom [att läsa HoloLens-utvecklardokumentationen.](https://developer.microsoft.com/windows/mixed-reality/development)</span><span class="sxs-lookup"><span data-stu-id="c00b3-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="c00b3-165">Samma instruktioner fungerar med Insider-byggen av HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c00b3-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="c00b3-166">Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens-utveckling.</span><span class="sxs-lookup"><span data-stu-id="c00b3-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="c00b3-167">Sluta ta emot Insider-byggen</span><span class="sxs-lookup"><span data-stu-id="c00b3-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="c00b3-168">Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du avanmäla [](hololens-recovery.md) dig när din HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="c00b3-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="c00b3-169">Det finns ett känt problem där användare som avregistrerar sig från Insider Preview-versionerna efter att ha installerat om en ny version av förhandsversionen manuellt skulle uppleva en blå skärm.</span><span class="sxs-lookup"><span data-stu-id="c00b3-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="c00b3-170">Därefter måste de återställa sin enhet manuellt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="c00b3-171">Fullständig information om om du skulle påverkas eller inte finns i mer information om det här [kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="c00b3-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="c00b3-172">Så här kontrollerar du att hololens kör en produktionsbygge:</span><span class="sxs-lookup"><span data-stu-id="c00b3-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="c00b3-173">Gå till **Inställningar > System > Om** och leta reda på build-numret.</span><span class="sxs-lookup"><span data-stu-id="c00b3-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="c00b3-174">[Se den nya versionen för produktionsbyggnummer.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="c00b3-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="c00b3-175">Så här avanmäler du dig från Insider-byggen:</span><span class="sxs-lookup"><span data-stu-id="c00b3-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="c00b3-176">På en HoloLens som kör en produktionsbygge går du **till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**</span><span class="sxs-lookup"><span data-stu-id="c00b3-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="c00b3-177">Följ instruktionerna för att avanmäla enheten.</span><span class="sxs-lookup"><span data-stu-id="c00b3-177">Follow the instructions to opt out your device.</span></span>
