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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977229"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="293b1-103">Insiderförhandsvisning för Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="293b1-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="293b1-104">Välkommen till de senaste Insider Preview-versionerna för HoloLens!</span><span class="sxs-lookup"><span data-stu-id="293b1-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="293b1-105">Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för vår nästa större operativsystemsuppdatering för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="293b1-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="293b1-106">Windows Insider – information</span><span class="sxs-lookup"><span data-stu-id="293b1-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="293b1-107">Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen.</span><span class="sxs-lookup"><span data-stu-id="293b1-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="293b1-108">Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="293b1-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="293b1-109">Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider våra byggen.</span><span class="sxs-lookup"><span data-stu-id="293b1-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="293b1-110">Bli spänd och redo att blanda de här uppdateringarna i din verklighet.</span><span class="sxs-lookup"><span data-stu-id="293b1-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="293b1-111">Funktion</span><span class="sxs-lookup"><span data-stu-id="293b1-111">Feature</span></span>                 | <span data-ttu-id="293b1-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="293b1-112">Description</span></span>                | <span data-ttu-id="293b1-113">Målanvändare</span><span class="sxs-lookup"><span data-stu-id="293b1-113">Target Users</span></span> | <span data-ttu-id="293b1-114">Skapa introducerat</span><span class="sxs-lookup"><span data-stu-id="293b1-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="293b1-115">CSP-ändringar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="293b1-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="293b1-116">Nya CPP:er för att fråga efter data</span><span class="sxs-lookup"><span data-stu-id="293b1-116">New CSPs for to query data</span></span> | <span data-ttu-id="293b1-117">IT-administratörer</span><span class="sxs-lookup"><span data-stu-id="293b1-117">IT Admins</span></span>    | <span data-ttu-id="293b1-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="293b1-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="293b1-119">CSP-ändringar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="293b1-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="293b1-120">Introducerades i Windows Insider build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="293b1-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="293b1-121">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="293b1-121">DevDetail CSP</span></span>

<span data-ttu-id="293b1-122">DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens-enheten.</span><span class="sxs-lookup"><span data-stu-id="293b1-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="293b1-123">Detta bör ungefär matcha det värde som visas på inställningsappens lagringssida.</span><span class="sxs-lookup"><span data-stu-id="293b1-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="293b1-124">Nedan visas den specifika nod som innehåller den här informationen.</span><span class="sxs-lookup"><span data-stu-id="293b1-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="293b1-125">./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)</span><span class="sxs-lookup"><span data-stu-id="293b1-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="293b1-126">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="293b1-126">DeviceStatus CSP</span></span>

<span data-ttu-id="293b1-127">DeviceStatus CSP rapporterar nu även SSID och BSSID för WiFi-nätverk som HoloLens är aktivt ansluten till.</span><span class="sxs-lookup"><span data-stu-id="293b1-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="293b1-128">Nedan visas de specifika noder som innehåller den här informationen.</span><span class="sxs-lookup"><span data-stu-id="293b1-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="293b1-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="293b1-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="293b1-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi*/BSSID</span><span class="sxs-lookup"><span data-stu-id="293b1-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="293b1-131">Exempel på syncml-blob (för MDM-leverantörer) för att fråga efter NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="293b1-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="293b1-132">Korrigeringar och förbättringar:</span><span class="sxs-lookup"><span data-stu-id="293b1-132">Fixes and improvements:</span></span>

- <span data-ttu-id="293b1-133">Ett känt [problem har åtgärdats för Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="293b1-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="293b1-134">Åtgärdat [ett känt problem för Enhetsportalen med time out för filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="293b1-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="293b1-135">Börja ta emot Insider-byggen</span><span class="sxs-lookup"><span data-stu-id="293b1-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="293b1-136">Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="293b1-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="293b1-137">Röstkommandot "Starta om enheten" fungerar bra.</span><span class="sxs-lookup"><span data-stu-id="293b1-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="293b1-138">Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="293b1-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="293b1-139">Det har uppstått en bugg i backend-delen som du kan ha stött på, vilket gör att du kommer igång igen.</span><span class="sxs-lookup"><span data-stu-id="293b1-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="293b1-140">På en HoloLens 2-enhet går du **till**  >  **Inställningar & Security**  >  **Windows Insider Program** och väljer **Kom igång.**</span><span class="sxs-lookup"><span data-stu-id="293b1-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="293b1-141">Länka det konto som du använde för att registrera som Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="293b1-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="293b1-142">Windows Insider flyttas nu till kanaler.</span><span class="sxs-lookup"><span data-stu-id="293b1-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="293b1-143">Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.**</span><span class="sxs-lookup"><span data-stu-id="293b1-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="293b1-144">Så här ser mappningen ut: Windows Insider förklaring av kanaler Mer information finns ![ i Introduktion Windows Insider ](images/WindowsInsiderChannels.png) [kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows-bloggar.</span><span class="sxs-lookup"><span data-stu-id="293b1-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="293b1-145">Välj sedan **Aktiv utveckling av Windows,** välj om du vill ta emot Dev **Channel** **eller Betakanal-versioner** och granska programvillkoren.</span><span class="sxs-lookup"><span data-stu-id="293b1-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="293b1-146">Välj **Bekräfta > starta om nu** för att slutföra.</span><span class="sxs-lookup"><span data-stu-id="293b1-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="293b1-147">När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="293b1-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="293b1-148">Uppdatera fel 0x80070490 för att komma runt</span><span class="sxs-lookup"><span data-stu-id="293b1-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="293b1-149">Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning.</span><span class="sxs-lookup"><span data-stu-id="293b1-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="293b1-150">Det innebär att du flyttar din Insider-kanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.</span><span class="sxs-lookup"><span data-stu-id="293b1-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="293b1-151">Steg ett – förhandsversion</span><span class="sxs-lookup"><span data-stu-id="293b1-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="293b1-152">Inställningar, Uppdatera & säkerhet, Windows Insider Program och välj **Kanal för förhandsversion.**</span><span class="sxs-lookup"><span data-stu-id="293b1-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="293b1-153">Settings, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="293b1-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="293b1-154">Efter uppdateringen fortsätter du till Fas två.</span><span class="sxs-lookup"><span data-stu-id="293b1-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="293b1-155">Steg två – Dev Channel</span><span class="sxs-lookup"><span data-stu-id="293b1-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="293b1-156">Inställningar, Uppdatera & säkerhet, Windows Insider Program, välj **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="293b1-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="293b1-157">Settings, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="293b1-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="293b1-158">FFU-nedladdning och flash-riktningar</span><span class="sxs-lookup"><span data-stu-id="293b1-158">FFU download and flash directions</span></span>
<span data-ttu-id="293b1-159">Om du vill testa med en flyg signerad ffu måste du först låsa upp enheten innan du flashar den flyg signerade ffu.</span><span class="sxs-lookup"><span data-stu-id="293b1-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="293b1-160">På datorn:</span><span class="sxs-lookup"><span data-stu-id="293b1-160">On PC:</span></span>
    1. <span data-ttu-id="293b1-161">Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="293b1-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="293b1-162">Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="293b1-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="293b1-163">På HoloLens – Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** sedan registrera dig, starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="293b1-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="293b1-164">Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.</span><span class="sxs-lookup"><span data-stu-id="293b1-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="293b1-165">Ge feedback och rapportera problem</span><span class="sxs-lookup"><span data-stu-id="293b1-165">Provide feedback and report issues</span></span>
<span data-ttu-id="293b1-166">Använd appen [Feedbackhubben hololens](hololens-feedback.md) för att ge feedback och rapportera problem.</span><span class="sxs-lookup"><span data-stu-id="293b1-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="293b1-167">Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="293b1-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="293b1-168">Problem med den kinesiska och japanska versionen av HoloLens bör rapporteras på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="293b1-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="293b1-169">Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben komma åt mappen Dokument (välj **Ja när** du tillfrågas).</span><span class="sxs-lookup"><span data-stu-id="293b1-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="293b1-170">Obs! För utvecklare</span><span class="sxs-lookup"><span data-stu-id="293b1-170">Note for developers</span></span>
<span data-ttu-id="293b1-171">Du är välkommen och uppmanas att prova att utveckla dina program med Insider-byggen av HoloLens.</span><span class="sxs-lookup"><span data-stu-id="293b1-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="293b1-172">Kom igång genom [att läsa HoloLens-utvecklardokumentationen.](https://developer.microsoft.com/windows/mixed-reality/development)</span><span class="sxs-lookup"><span data-stu-id="293b1-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="293b1-173">Samma instruktioner fungerar med Insider-byggen av HoloLens.</span><span class="sxs-lookup"><span data-stu-id="293b1-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="293b1-174">Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens-utveckling.</span><span class="sxs-lookup"><span data-stu-id="293b1-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="293b1-175">Sluta ta emot Insider-byggen</span><span class="sxs-lookup"><span data-stu-id="293b1-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="293b1-176">Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du avanmäla [](hololens-recovery.md) dig när din HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="293b1-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="293b1-177">Det finns ett känt problem där användare som avregistrerar sig från Insider Preview-versionerna efter att ha installerat om en ny version av förhandsversionen manuellt skulle uppleva en blå skärm.</span><span class="sxs-lookup"><span data-stu-id="293b1-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="293b1-178">Därefter måste de återställa sin enhet manuellt.</span><span class="sxs-lookup"><span data-stu-id="293b1-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="293b1-179">Fullständig information om om du skulle påverkas eller inte finns i mer information om det här [kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="293b1-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="293b1-180">Så här kontrollerar du att hololens kör en produktionsbygge:</span><span class="sxs-lookup"><span data-stu-id="293b1-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="293b1-181">Gå till **Inställningar > System > Om** och leta reda på build-numret.</span><span class="sxs-lookup"><span data-stu-id="293b1-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="293b1-182">[Se den nya versionen för produktionsbyggnummer.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="293b1-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="293b1-183">Så här avanmäler du dig från Insider-byggen:</span><span class="sxs-lookup"><span data-stu-id="293b1-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="293b1-184">På en HoloLens som kör en produktionsbygge går du **till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**</span><span class="sxs-lookup"><span data-stu-id="293b1-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="293b1-185">Följ instruktionerna för att avanmäla enheten.</span><span class="sxs-lookup"><span data-stu-id="293b1-185">Follow the instructions to opt out your device.</span></span>
