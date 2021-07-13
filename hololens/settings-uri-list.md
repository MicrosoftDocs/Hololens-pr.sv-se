---
title: Synlighet för Inställningar sida
description: Håll dig uppdaterad med vår lista över URI:er som stöds för PageVisibilityList och Guide på HoloLens enheter med mixad verklighet.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, tilldelad åtkomst, helskärmsläge, inställningssida
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639241"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="bad86-104">Synlighet för Inställningar sida</span><span class="sxs-lookup"><span data-stu-id="bad86-104">Page Settings Visibility</span></span>

<span data-ttu-id="bad86-105">En av de hanterbara funktionerna för HoloLens-enheter använder [principen Inställningar/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) för att begränsa de sidor som visas i Inställningar appen.</span><span class="sxs-lookup"><span data-stu-id="bad86-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="bad86-106">PageVisibilityList är en princip som gör det möjligt för IT-administratörer att antingen förhindra att specifika sidor i System Inställningar-appen visas eller är tillgängliga, eller att göra det för alla sidor utom de som anges.</span><span class="sxs-lookup"><span data-stu-id="bad86-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="bad86-107">Den här funktionen är endast tillgänglig i [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) eller senare för HoloLens 2 enheter.</span><span class="sxs-lookup"><span data-stu-id="bad86-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="bad86-108">Se till att de enheter som du tänker använda för uppdateras.</span><span class="sxs-lookup"><span data-stu-id="bad86-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="bad86-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="bad86-109">Examples</span></span>
<span data-ttu-id="bad86-110">Sidor identifieras med en förkortad version av de publicerade URI:erna, vilket är URI:n minus prefixet "ms-settings:".</span><span class="sxs-lookup"><span data-stu-id="bad86-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="bad86-111">I följande exempel visas en princip som endast tillåter åtkomst till about- och bluetooth-sidor, som har URI:erna "network-wifi" respektive "bluetooth":</span><span class="sxs-lookup"><span data-stu-id="bad86-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="bad86-112">I följande exempel visas en princip som skulle dölja sidan Återställning av operativsystem:</span><span class="sxs-lookup"><span data-stu-id="bad86-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="bad86-113">Distribuera den här principen via Intune</span><span class="sxs-lookup"><span data-stu-id="bad86-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="bad86-114">Det här är de konfigurationsvärden som kommer att tillhandahållas till Intune:</span><span class="sxs-lookup"><span data-stu-id="bad86-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="bad86-115">**Namn:** Ett visningsnamn som administratören föredrar för profilen.</span><span class="sxs-lookup"><span data-stu-id="bad86-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="bad86-116">**OMA-URI:** Inställningssidans fullständigt kvalificerade URI, inklusive dess [omfång](/windows/client-management/mdm/policy-configuration-service-provider).</span><span class="sxs-lookup"><span data-stu-id="bad86-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="bad86-117">De här exemplen på den här sidan använder `./Device` omfånget .</span><span class="sxs-lookup"><span data-stu-id="bad86-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="bad86-118">**Värde:** Ett strängvärde som anger om du vill dölja eller endast *visa* de angivna sidorna.</span><span class="sxs-lookup"><span data-stu-id="bad86-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="bad86-119">Möjliga värden är `hide:<pagename>` och `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="bad86-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="bad86-120">Flera sidor kan anges genom att avgränsa dem med semikolon, och en lista över vanliga sidor finns nedan.</span><span class="sxs-lookup"><span data-stu-id="bad86-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="bad86-121">Skapa en **anpassad princip.**</span><span class="sxs-lookup"><span data-stu-id="bad86-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="bad86-122">När du ställer in **OMA-URI anger** du den fullständigt begränsade URI:en.</span><span class="sxs-lookup"><span data-stu-id="bad86-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="bad86-123">Till exempel: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="bad86-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="bad86-124">När du väljer dataväljer du: **Sträng**</span><span class="sxs-lookup"><span data-stu-id="bad86-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="bad86-125">Använd **vägledningen ovan** när du anger Värde.</span><span class="sxs-lookup"><span data-stu-id="bad86-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="bad86-126">Till exempel: **`showonly:network-wifi;network-proxy;bluetooth`** eller **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="bad86-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="bad86-127">Se till att tilldela den anpassade enhetskonfigurationen till en grupp som enheten är avsedd att finnas i.</span><span class="sxs-lookup"><span data-stu-id="bad86-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="bad86-128">Om det här steget inte utförs push-skickas principen men tillämpas inte.</span><span class="sxs-lookup"><span data-stu-id="bad86-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="bad86-129">Se [HoloLens MDM-konfiguration](hololens-mdm-configure.md) för mer information om Intune-grupper och enhetskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="bad86-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="bad86-130">Distribuera den här principen via ett etableringspaket</span><span class="sxs-lookup"><span data-stu-id="bad86-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="bad86-131">Det här är de konfigurationsvärden som anges i Windows Configuration Designer:</span><span class="sxs-lookup"><span data-stu-id="bad86-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="bad86-132">**Värde:** Ett strängvärde som anger om du vill dölja eller endast *visa* de angivna sidorna.</span><span class="sxs-lookup"><span data-stu-id="bad86-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="bad86-133">Möjliga värden är `hide:<pagename>` och `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="bad86-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="bad86-134">Flera sidor kan anges genom att avgränsa dem med semikolon, och en lista över vanliga sidor finns nedan.</span><span class="sxs-lookup"><span data-stu-id="bad86-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="bad86-135">När du skapar paketet i Windows Configuration Designer går du till **Principer > Inställningar > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="bad86-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="bad86-136">Ange strängen: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="bad86-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="bad86-137">Exportera ditt etableringspaket.</span><span class="sxs-lookup"><span data-stu-id="bad86-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="bad86-138">Tillämpa paketet på din enhet.</span><span class="sxs-lookup"><span data-stu-id="bad86-138">Apply the package to your device.</span></span>
<span data-ttu-id="bad86-139">Fullständig information om hur du skapar och tillämpar ett etableringspaket finns [på HoloLens etableringssidan.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="bad86-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="bad86-140">Oavsett vilken metod som valts bör enheten nu ta emot ändringarna och användarna kommer att se följande Inställningar app.</span><span class="sxs-lookup"><span data-stu-id="bad86-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Skärmbild av aktiva timmar som ändras i Inställningar appen](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="bad86-142">Om du vill konfigurera Inställningar-appsidorna så att de visar eller döljer ditt eget val av sidor kan du ta en titt på de Inställningar URI:er som finns HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bad86-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="bad86-143">Inställningar Uris</span><span class="sxs-lookup"><span data-stu-id="bad86-143">Settings URIs</span></span>

<span data-ttu-id="bad86-144">HoloLens enheter Windows 10 enheter har olika val av sidor i Inställningar appen.</span><span class="sxs-lookup"><span data-stu-id="bad86-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="bad86-145">På den här sidan hittar du bara de inställningar som finns på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bad86-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="bad86-146">Konton</span><span class="sxs-lookup"><span data-stu-id="bad86-146">Accounts</span></span>
| <span data-ttu-id="bad86-147">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-147">Settings page</span></span>           | <span data-ttu-id="bad86-148">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="bad86-149">Åtkomst till arbete eller skola</span><span class="sxs-lookup"><span data-stu-id="bad86-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="bad86-150">Iris-registrering</span><span class="sxs-lookup"><span data-stu-id="bad86-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="bad86-151">Inloggningsalternativ</span><span class="sxs-lookup"><span data-stu-id="bad86-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="bad86-152">Appar</span><span class="sxs-lookup"><span data-stu-id="bad86-152">Apps</span></span>
| <span data-ttu-id="bad86-153">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-153">Settings page</span></span> | <span data-ttu-id="bad86-154">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="bad86-155">Appar & funktioner <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="bad86-156">Appar & funktioner > Avancerade alternativ <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="bad86-157">Appar & funktioner > Offline Kartor <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="bad86-158">Appar & funktioner > Offline Kartor > Hämta kartor <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="bad86-159">Enheter</span><span class="sxs-lookup"><span data-stu-id="bad86-159">Devices</span></span>
| <span data-ttu-id="bad86-160">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-160">Settings page</span></span> | <span data-ttu-id="bad86-161">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="bad86-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="bad86-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="bad86-163">Mus <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="bad86-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="bad86-165">Sekretess</span><span class="sxs-lookup"><span data-stu-id="bad86-165">Privacy</span></span>
| <span data-ttu-id="bad86-166">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-166">Settings page</span></span>            | <span data-ttu-id="bad86-167">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="bad86-168">Kontoinformation</span><span class="sxs-lookup"><span data-stu-id="bad86-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="bad86-169">Appdiagnostik</span><span class="sxs-lookup"><span data-stu-id="bad86-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="bad86-170">Bakgrundsappar</span><span class="sxs-lookup"><span data-stu-id="bad86-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="bad86-171">Kalender</span><span class="sxs-lookup"><span data-stu-id="bad86-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="bad86-172">Samtalshistorik</span><span class="sxs-lookup"><span data-stu-id="bad86-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="bad86-173">Kamera</span><span class="sxs-lookup"><span data-stu-id="bad86-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="bad86-174">Kontakter</span><span class="sxs-lookup"><span data-stu-id="bad86-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="bad86-175">Feedback & diagnostik</span><span class="sxs-lookup"><span data-stu-id="bad86-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="bad86-176">Dokument</span><span class="sxs-lookup"><span data-stu-id="bad86-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="bad86-177">E-post</span><span class="sxs-lookup"><span data-stu-id="bad86-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="bad86-178">Filsystem</span><span class="sxs-lookup"><span data-stu-id="bad86-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="bad86-179">Allmänt <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="bad86-180">Ink& skriva anpassning <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="bad86-181">Location</span><span class="sxs-lookup"><span data-stu-id="bad86-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="bad86-182">Meddelandefunktion</span><span class="sxs-lookup"><span data-stu-id="bad86-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="bad86-183">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="bad86-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="bad86-184">Rörelse <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="bad86-185">Meddelanden</span><span class="sxs-lookup"><span data-stu-id="bad86-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="bad86-186">Andra enheter</span><span class="sxs-lookup"><span data-stu-id="bad86-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="bad86-187">Bilder</span><span class="sxs-lookup"><span data-stu-id="bad86-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="bad86-188">Radioapparater</span><span class="sxs-lookup"><span data-stu-id="bad86-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="bad86-189">Skärmbild av <sup>kantlinjer 2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="bad86-190">Skärmbilder och appar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="bad86-191">Speech</span><span class="sxs-lookup"><span data-stu-id="bad86-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="bad86-192">Uppgifter</span><span class="sxs-lookup"><span data-stu-id="bad86-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="bad86-193">Användarförflyttningar</span><span class="sxs-lookup"><span data-stu-id="bad86-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="bad86-194">Video</span><span class="sxs-lookup"><span data-stu-id="bad86-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="bad86-195">Röstaktivering</span><span class="sxs-lookup"><span data-stu-id="bad86-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="bad86-196">Nätverk och Internet</span><span class="sxs-lookup"><span data-stu-id="bad86-196">Network & Internet</span></span>
| <span data-ttu-id="bad86-197">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-197">Settings page</span></span> | <span data-ttu-id="bad86-198">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="bad86-199">Flygplansläge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="bad86-200">Proxy</span><span class="sxs-lookup"><span data-stu-id="bad86-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="bad86-201">VPN</span><span class="sxs-lookup"><span data-stu-id="bad86-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="bad86-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="bad86-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="bad86-203">System</span><span class="sxs-lookup"><span data-stu-id="bad86-203">System</span></span>
| <span data-ttu-id="bad86-204">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-204">Settings page</span></span>      | <span data-ttu-id="bad86-205">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="bad86-206">Batteri <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="bad86-207">Batteri <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="bad86-208">Färger</span><span class="sxs-lookup"><span data-stu-id="bad86-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="bad86-209">Hologram <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="bad86-210">Kalibrering <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="bad86-211">Meddelanden & åtgärder</span><span class="sxs-lookup"><span data-stu-id="bad86-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="bad86-212">Delade upplevelser</span><span class="sxs-lookup"><span data-stu-id="bad86-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="bad86-213">Ljud <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="bad86-214">Ljud > appvolym och enhetsinställning <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="bad86-215">Ljud > Hantera ljudenheter <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="bad86-216">Storage</span><span class="sxs-lookup"><span data-stu-id="bad86-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="bad86-217">Storage > Konfigurera Storage Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="bad86-218">Tids & språk</span><span class="sxs-lookup"><span data-stu-id="bad86-218">Time & Language</span></span>
| <span data-ttu-id="bad86-219">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-219">Settings page</span></span> | <span data-ttu-id="bad86-220">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="bad86-221">Datum & tid <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="bad86-222">Tangentbord <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="bad86-223">Språk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="bad86-224">Språk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="bad86-225">Språk</span><span class="sxs-lookup"><span data-stu-id="bad86-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="bad86-226">Region</span><span class="sxs-lookup"><span data-stu-id="bad86-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="bad86-227">Uppdatera & Security</span><span class="sxs-lookup"><span data-stu-id="bad86-227">Update & Security</span></span>
| <span data-ttu-id="bad86-228">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="bad86-228">Settings page</span></span>                         | <span data-ttu-id="bad86-229">URI</span><span class="sxs-lookup"><span data-stu-id="bad86-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="bad86-230">Avancerade alternativ</span><span class="sxs-lookup"><span data-stu-id="bad86-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="bad86-231">Återställa & Recovery <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bad86-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="bad86-232">Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="bad86-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="bad86-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="bad86-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="bad86-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="bad86-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="bad86-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="bad86-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="bad86-236">Windows Uppdatera – Söker efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="bad86-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="bad86-237"><sup>1</sup> – För versioner före Windows Holographic, version 21H1, tar följande två  URI:er faktiskt inte dig till sidorna Avancerade alternativ **eller** Alternativ. De blockerar eller visar bara huvudsidan Windows Update.</span><span class="sxs-lookup"><span data-stu-id="bad86-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="bad86-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="bad86-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="bad86-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="bad86-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="bad86-240"><sup>2</sup> – Tillgängligt i Windows Holographic 21H1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="bad86-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="bad86-241">En fullständig lista över Windows 10 Inställningar-URI:er finns i dokumentationen [om startinställningar.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="bad86-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
