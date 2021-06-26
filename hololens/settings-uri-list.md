---
title: Synlighet för sidinställningar
description: Håll dig uppdaterad med vår lista över URI:er som stöds för PageVisibilityList och Guide på HoloLens-enheter med mixad verklighet.
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
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924340"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="e7cb2-104">Synlighet för sidinställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-104">Page Settings Visibility</span></span>

<span data-ttu-id="e7cb2-105">En av de hanterbara funktionerna för HoloLens-enheter använder principen [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) för att begränsa de sidor som visas i appen Inställningar.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="e7cb2-106">PageVisibilityList är en princip som gör det möjligt för IT-administratörer att antingen förhindra att specifika sidor i appen Systeminställningar visas eller är tillgängliga, eller att göra det för alla sidor utom de som anges.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="e7cb2-107">Den här funktionen är endast tillgänglig i [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) eller senare för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="e7cb2-108">Se till att de enheter som du tänker använda för uppdateras.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="e7cb2-109">I följande exempel visas en princip som endast tillåter åtkomst till about- och bluetooth-sidor, som har URI:en "ms-settings:network-wifi" respektive "ms-settings:bluetooth":</span><span class="sxs-lookup"><span data-stu-id="e7cb2-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="e7cb2-110">Så här anger du detta via ett etableringspaket:</span><span class="sxs-lookup"><span data-stu-id="e7cb2-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="e7cb2-111">När du skapar paketet i Windows Configuration Designer går du till **Principer > Inställningar > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="e7cb2-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="e7cb2-112">Ange strängen: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="e7cb2-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="e7cb2-113">Exportera ditt etableringspaket.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="e7cb2-114">Tillämpa paketet på din enhet.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-114">Apply the package to your device.</span></span>
<span data-ttu-id="e7cb2-115">Fullständig information om hur du skapar och tillämpar ett etableringspaket finns på den [här sidan.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e7cb2-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="e7cb2-116">Detta kan göras via Intune med OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="e7cb2-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="e7cb2-117">Skapa en **anpassad princip.**</span><span class="sxs-lookup"><span data-stu-id="e7cb2-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="e7cb2-118">Använd strängen när du anger OMA-URI: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="e7cb2-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="e7cb2-119">När du väljer dataväljer du: **Sträng**</span><span class="sxs-lookup"><span data-stu-id="e7cb2-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="e7cb2-120">När du skriver värdet använder du: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="e7cb2-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="e7cb2-121">Se till att tilldela den anpassade enhetskonfigurationen till en grupp som enheten är avsedd att finnas i.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="e7cb2-122">Mer information [om Intune-grupper och](hololens-mdm-configure.md) enhetskonfigurationer finns i HoloLens MDM-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="e7cb2-123">Oavsett vilken metod som valts bör enheten nu ta emot ändringarna och användarna kommer att se följande inställningsapp.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Skärmbild av aktiva timmar som ändras i inställningsappen](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="e7cb2-125">Om du vill konfigurera inställningsappsidorna så att de visar eller döljer dina egna val av sidor kan du ta en titt på inställnings-URI:er som är tillgängliga på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="e7cb2-126">URI:er för inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-126">Settings URIs</span></span>

<span data-ttu-id="e7cb2-127">HoloLens-enheter Windows 10 enheter har olika val av sidor i appen Inställningar.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="e7cb2-128">På den här sidan hittar du bara de inställningar som finns på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="e7cb2-129">Konton</span><span class="sxs-lookup"><span data-stu-id="e7cb2-129">Accounts</span></span>
| <span data-ttu-id="e7cb2-130">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-130">Settings page</span></span>           | <span data-ttu-id="e7cb2-131">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="e7cb2-132">Åtkomst till arbete eller skola</span><span class="sxs-lookup"><span data-stu-id="e7cb2-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="e7cb2-133">Iris-registrering</span><span class="sxs-lookup"><span data-stu-id="e7cb2-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="e7cb2-134">Inloggningsalternativ</span><span class="sxs-lookup"><span data-stu-id="e7cb2-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="e7cb2-135">Appar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-135">Apps</span></span>
| <span data-ttu-id="e7cb2-136">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-136">Settings page</span></span> | <span data-ttu-id="e7cb2-137">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="e7cb2-138">Appar & funktioner<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="e7cb2-139">Appar & funktioner > Avancerade alternativ <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="e7cb2-140">Appar & funktioner > Offline Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="e7cb2-141">Appar & funktioner > offlinekartor > Hämta kartor <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="e7cb2-142">Enheter</span><span class="sxs-lookup"><span data-stu-id="e7cb2-142">Devices</span></span>
| <span data-ttu-id="e7cb2-143">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-143">Settings page</span></span> | <span data-ttu-id="e7cb2-144">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="e7cb2-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e7cb2-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="e7cb2-146">Mus <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="e7cb2-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="e7cb2-148">Sekretess</span><span class="sxs-lookup"><span data-stu-id="e7cb2-148">Privacy</span></span>
| <span data-ttu-id="e7cb2-149">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-149">Settings page</span></span>            | <span data-ttu-id="e7cb2-150">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="e7cb2-151">Kontoinformation</span><span class="sxs-lookup"><span data-stu-id="e7cb2-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="e7cb2-152">Appdiagnostik</span><span class="sxs-lookup"><span data-stu-id="e7cb2-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="e7cb2-153">Bakgrundsappar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="e7cb2-154">Kalender</span><span class="sxs-lookup"><span data-stu-id="e7cb2-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="e7cb2-155">Samtalshistorik</span><span class="sxs-lookup"><span data-stu-id="e7cb2-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="e7cb2-156">Kamera</span><span class="sxs-lookup"><span data-stu-id="e7cb2-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="e7cb2-157">Kontakter</span><span class="sxs-lookup"><span data-stu-id="e7cb2-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="e7cb2-158">Feedback & diagnostik</span><span class="sxs-lookup"><span data-stu-id="e7cb2-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="e7cb2-159">Dokument</span><span class="sxs-lookup"><span data-stu-id="e7cb2-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="e7cb2-160">E-post</span><span class="sxs-lookup"><span data-stu-id="e7cb2-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="e7cb2-161">Filsystem</span><span class="sxs-lookup"><span data-stu-id="e7cb2-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="e7cb2-162">Allmänt <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="e7cb2-163">Ink& skriva anpassning <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="e7cb2-164">Location</span><span class="sxs-lookup"><span data-stu-id="e7cb2-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="e7cb2-165">Meddelandefunktion</span><span class="sxs-lookup"><span data-stu-id="e7cb2-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="e7cb2-166">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="e7cb2-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="e7cb2-167">Rörelse <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="e7cb2-168">Meddelanden</span><span class="sxs-lookup"><span data-stu-id="e7cb2-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="e7cb2-169">Andra enheter</span><span class="sxs-lookup"><span data-stu-id="e7cb2-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="e7cb2-170">Bilder</span><span class="sxs-lookup"><span data-stu-id="e7cb2-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="e7cb2-171">Radioapparater</span><span class="sxs-lookup"><span data-stu-id="e7cb2-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="e7cb2-172">Skärmbild av <sup>kantlinjer 2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="e7cb2-173">Skärmbilder och appar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="e7cb2-174">Speech</span><span class="sxs-lookup"><span data-stu-id="e7cb2-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="e7cb2-175">Uppgifter</span><span class="sxs-lookup"><span data-stu-id="e7cb2-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="e7cb2-176">Användarförflyttningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="e7cb2-177">Video</span><span class="sxs-lookup"><span data-stu-id="e7cb2-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="e7cb2-178">Röstaktivering</span><span class="sxs-lookup"><span data-stu-id="e7cb2-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="e7cb2-179">Nätverk och Internet</span><span class="sxs-lookup"><span data-stu-id="e7cb2-179">Network & Internet</span></span>
| <span data-ttu-id="e7cb2-180">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-180">Settings page</span></span> | <span data-ttu-id="e7cb2-181">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="e7cb2-182">Flygplansläge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="e7cb2-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="e7cb2-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="e7cb2-184">VPN</span><span class="sxs-lookup"><span data-stu-id="e7cb2-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="e7cb2-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e7cb2-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="e7cb2-186">System</span><span class="sxs-lookup"><span data-stu-id="e7cb2-186">System</span></span>
| <span data-ttu-id="e7cb2-187">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-187">Settings page</span></span>      | <span data-ttu-id="e7cb2-188">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="e7cb2-189">Batteri <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="e7cb2-190">Batteri <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="e7cb2-191">Färger</span><span class="sxs-lookup"><span data-stu-id="e7cb2-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="e7cb2-192">Hologram <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="e7cb2-193">Kalibrering <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="e7cb2-194">Meddelanden & åtgärder</span><span class="sxs-lookup"><span data-stu-id="e7cb2-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="e7cb2-195">Delade upplevelser</span><span class="sxs-lookup"><span data-stu-id="e7cb2-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="e7cb2-196">Ljud <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="e7cb2-197">Ljud > appvolym och enhetsinställning <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="e7cb2-198">Ljud > Hantera ljudenheter <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="e7cb2-199">Storage</span><span class="sxs-lookup"><span data-stu-id="e7cb2-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="e7cb2-200">Storage > Configure Storage Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="e7cb2-201">Tid & språk</span><span class="sxs-lookup"><span data-stu-id="e7cb2-201">Time & Language</span></span>
| <span data-ttu-id="e7cb2-202">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-202">Settings page</span></span> | <span data-ttu-id="e7cb2-203">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="e7cb2-204">Datum & tid <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="e7cb2-205">Tangentbord <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="e7cb2-206">Språk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="e7cb2-207">Språk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="e7cb2-208">Språk</span><span class="sxs-lookup"><span data-stu-id="e7cb2-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="e7cb2-209">Region</span><span class="sxs-lookup"><span data-stu-id="e7cb2-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="e7cb2-210">Uppdatera & security</span><span class="sxs-lookup"><span data-stu-id="e7cb2-210">Update & Security</span></span>
| <span data-ttu-id="e7cb2-211">Sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-211">Settings page</span></span>                         | <span data-ttu-id="e7cb2-212">URI</span><span class="sxs-lookup"><span data-stu-id="e7cb2-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="e7cb2-213">Avancerade alternativ</span><span class="sxs-lookup"><span data-stu-id="e7cb2-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="e7cb2-214">Återställa & Recovery <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7cb2-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="e7cb2-215">Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="e7cb2-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="e7cb2-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e7cb2-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="e7cb2-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="e7cb2-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="e7cb2-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="e7cb2-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="e7cb2-219">Windows Update – Söker efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="e7cb2-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="e7cb2-220"><sup>1</sup> – För versioner före Windows Holographic version 21H1 tar inte följande  två URI:er dig till sidorna Avancerade alternativ **eller** Alternativ. De blockerar eller visar bara huvudsidan Windows Update sidan.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="e7cb2-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="e7cb2-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="e7cb2-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="e7cb2-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="e7cb2-223"><sup>2</sup> – Tillgängligt i Windows Holographic 21H1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="e7cb2-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="e7cb2-224">En fullständig lista över URI Windows 10 inställningar finns i dokumentationen om [startinställningar.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="e7cb2-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
