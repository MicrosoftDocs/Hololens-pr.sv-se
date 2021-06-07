---
title: Windows Defender programkontroll – WDAC
description: Översikt över vad Windows Defender Application Control är och hur du använder det för att hantera HoloLens-enheter med mixad verklighet.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378796"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="a22bf-103">Windows Defender programkontroll – WDAC</span><span class="sxs-lookup"><span data-stu-id="a22bf-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="a22bf-104">WDAC gör det möjligt för IT-administratörer att konfigurera sina enheter för att blockera start av appar på enheter.</span><span class="sxs-lookup"><span data-stu-id="a22bf-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="a22bf-105">Detta skiljer sig från metoder för enhetsbegränsning, till exempel helskärmsläge, där användaren får ett användargränssnitt som döljer apparna på enheten, men de kan fortfarande startas.</span><span class="sxs-lookup"><span data-stu-id="a22bf-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="a22bf-106">Medan WDAC implementeras visas apparna fortfarande i listan Alla appar, men WDAC hindrar dessa appar och processer från att kunna startas av enhetsanvändaren.</span><span class="sxs-lookup"><span data-stu-id="a22bf-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="a22bf-107">En enhet kan tilldelas mer än en WDAC-princip.</span><span class="sxs-lookup"><span data-stu-id="a22bf-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="a22bf-108">Om flera WDAC-principer har angetts i ett system gäller de mest restriktiva.</span><span class="sxs-lookup"><span data-stu-id="a22bf-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="a22bf-109">När slutanvändarna försöker starta en app som blockeras av WDAC får de på HoloLens inget meddelande om att de inte kan starta appen.</span><span class="sxs-lookup"><span data-stu-id="a22bf-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="a22bf-110">Följande är en guide för användare som lär sig hur de använder WDAC och Windows PowerShell för att tillåta eller blockera appar på [HoloLens 2-enheter med Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="a22bf-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="a22bf-111">När användare söker efter appar som Windows 10 på sin dator med hjälp av det första exempelsteget kan de behöva göra några försök att begränsa resultaten.</span><span class="sxs-lookup"><span data-stu-id="a22bf-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="a22bf-112">Om du inte känner till det fullständiga namnet på paketet kan du behöva köra Get-AppxPackage -name \* YourBestGuess några gånger \* för att hitta det.</span><span class="sxs-lookup"><span data-stu-id="a22bf-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="a22bf-113">När du har fått namnet kör du sedan "$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="a22bf-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="a22bf-114">Om du till exempel kör följande för Microsoft Edge returneras fler än ett resultat, men i listan kan du se att det fullständiga namn du behöver är Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="a22bf-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="a22bf-115">Paketfamiljenamn för appar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="a22bf-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="a22bf-116">I den guide som länkas ovan kan du manuellt redigera newPolicy.xml lägga till regler för program som endast är installerade på HoloLens med deras paketfamiljenamn.</span><span class="sxs-lookup"><span data-stu-id="a22bf-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="a22bf-117">Ibland kan det finnas appar som du kan använda som inte finns på den stationära dator som du vill lägga till i principen.</span><span class="sxs-lookup"><span data-stu-id="a22bf-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="a22bf-118">Här är en lista över vanliga och In-Box för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="a22bf-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="a22bf-119">Appnamn</span><span class="sxs-lookup"><span data-stu-id="a22bf-119">App Name</span></span>                   | <span data-ttu-id="a22bf-120">Paketfamiljenamn</span><span class="sxs-lookup"><span data-stu-id="a22bf-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="a22bf-121">3D-visningsprogram</span><span class="sxs-lookup"><span data-stu-id="a22bf-121">3D Viewer</span></span>                  | <span data-ttu-id="a22bf-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="a22bf-123">Appinstallationsprogram</span><span class="sxs-lookup"><span data-stu-id="a22bf-123">App Installer</span></span>              | <span data-ttu-id="a22bf-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a22bf-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="a22bf-125">Kalender</span><span class="sxs-lookup"><span data-stu-id="a22bf-125">Calendar</span></span>                   | <span data-ttu-id="a22bf-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="a22bf-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="a22bf-127">Camera</span></span>                     | <span data-ttu-id="a22bf-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="a22bf-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="a22bf-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="a22bf-129">Cortana</span></span>                    | <span data-ttu-id="a22bf-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="a22bf-131">Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="a22bf-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="a22bf-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="a22bf-133">Fjärrhjälp för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a22bf-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="a22bf-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="a22bf-135">Feedbackhubben</span><span class="sxs-lookup"><span data-stu-id="a22bf-135">Feedback Hub</span></span>               | <span data-ttu-id="a22bf-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="a22bf-137">Utforskaren</span><span class="sxs-lookup"><span data-stu-id="a22bf-137">File Explorer</span></span>              | <span data-ttu-id="a22bf-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="a22bf-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="a22bf-139">E-post</span><span class="sxs-lookup"><span data-stu-id="a22bf-139">Mail</span></span>                       | <span data-ttu-id="a22bf-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="a22bf-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a22bf-141">Microsoft Store</span></span>            | <span data-ttu-id="a22bf-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="a22bf-143">Filmer & TV</span><span class="sxs-lookup"><span data-stu-id="a22bf-143">Movies & TV</span></span>                | <span data-ttu-id="a22bf-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="a22bf-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a22bf-145">OneDrive</span></span>                   | <span data-ttu-id="a22bf-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="a22bf-147">Foton</span><span class="sxs-lookup"><span data-stu-id="a22bf-147">Photos</span></span>                     | <span data-ttu-id="a22bf-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="a22bf-149">Inställningar</span><span class="sxs-lookup"><span data-stu-id="a22bf-149">Settings</span></span>                   | <span data-ttu-id="a22bf-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="a22bf-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="a22bf-151">Tips</span><span class="sxs-lookup"><span data-stu-id="a22bf-151">Tips</span></span>                       | <span data-ttu-id="a22bf-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a22bf-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="a22bf-153">1 – Appinstallationsprogram blockerar endast Appinstallationsprogram appen och inte appar som har installerats från andra källor, till exempel Microsoft Store eller från din MDM-lösning.</span><span class="sxs-lookup"><span data-stu-id="a22bf-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="a22bf-154">Hitta ett paketfamiljenamn</span><span class="sxs-lookup"><span data-stu-id="a22bf-154">How to find a Package Family Name</span></span>

<span data-ttu-id="a22bf-155">Om en app inte finns med i listan kan en användare använda Enhetsportalen, ansluten till en HoloLens 2 som har installerat appen som vill blockeras, för att fastställa PackageRelativeID och därifrån hämta PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="a22bf-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="a22bf-156">Installera appen på din HoloLens 2-enhet.</span><span class="sxs-lookup"><span data-stu-id="a22bf-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="a22bf-157">Öppna Inställningar -> Uppdateringar & Security -> För utvecklare, aktivera **Utvecklarläge** och sedan **Enhetsportal.**</span><span class="sxs-lookup"><span data-stu-id="a22bf-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="a22bf-158">Mer information om instruktioner finns i konfigurera [och använda enhetsportalen här.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="a22bf-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="a22bf-159">När Enhetsportalen är ansluten går du till **Vyer** och sedan **Appar.**</span><span class="sxs-lookup"><span data-stu-id="a22bf-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="a22bf-160">I panelen Installerade appar använder du listrutan för att välja den installerade appen.</span><span class="sxs-lookup"><span data-stu-id="a22bf-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="a22bf-161">Leta upp PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="a22bf-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="a22bf-162">Kopiera apptecken före !. Dessa tecken blir PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="a22bf-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


