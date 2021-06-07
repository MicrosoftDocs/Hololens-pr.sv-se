---
title: Vanliga scenarier – Säker HoloLens 2 offline
description: Lär dig hur du ställer in ett scenario för säker distribution offline och appdistribution med etablering för HoloLens-enheter.
keywords: HoloLens, management, offline, offline secure
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378724"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="0336b-104">Vanliga scenarier – Säker HoloLens 2 offline</span><span class="sxs-lookup"><span data-stu-id="0336b-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="0336b-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0336b-105">Overview</span></span>

<span data-ttu-id="0336b-106">Den här guiden innehåller vägledning för att tillämpa ett exempel på etableringspaket som låser en HoloLens 2 för användning i säkra miljöer med följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="0336b-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="0336b-107">Inaktivera WiFi.</span><span class="sxs-lookup"><span data-stu-id="0336b-107">Disable WiFi.</span></span>
-   <span data-ttu-id="0336b-108">Inaktivera BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="0336b-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="0336b-109">Inaktivera mikrofoner.</span><span class="sxs-lookup"><span data-stu-id="0336b-109">Disable Microphones.</span></span>
-   <span data-ttu-id="0336b-110">Förhindrar tillägg eller borttagning av etableringspaket.</span><span class="sxs-lookup"><span data-stu-id="0336b-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="0336b-111">Ingen användare kan aktivera någon av ovanstående begränsade komponenter.</span><span class="sxs-lookup"><span data-stu-id="0336b-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="0336b-112">[![Scenario för offline-säkerhet ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0336b-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="0336b-113">Förbereda</span><span class="sxs-lookup"><span data-stu-id="0336b-113">Prepare</span></span>

<span data-ttu-id="0336b-114">Windows 10 datorinstallation</span><span class="sxs-lookup"><span data-stu-id="0336b-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="0336b-115">[Ladda ned den senaste HoloLens 2 OS-filen](https://aka.ms/hololens2download) direkt till en dator.</span><span class="sxs-lookup"><span data-stu-id="0336b-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="0336b-116">Stöd för den här konfigurationen ingår i Build 19041.1117 och högre.</span><span class="sxs-lookup"><span data-stu-id="0336b-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="0336b-117">Ladda ned/installera arc-verktyget (Advanced Recovery Companion) [från Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) till datorn</span><span class="sxs-lookup"><span data-stu-id="0336b-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="0336b-118">Ladda ned/installera det [senaste WCD-verktyget (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) från Microsoft Store till datorn.</span><span class="sxs-lookup"><span data-stu-id="0336b-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="0336b-119">[Ladda ned OfflineSecureHL2_Sample mappen med projektfilerna för](https://aka.ms/HoloLensDocs-SecureOfflineSample) att skapa PPKG.</span><span class="sxs-lookup"><span data-stu-id="0336b-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="0336b-120">Förbered ditt [verksamhets offlineprogram för PPKG-distribution.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="0336b-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="0336b-121">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="0336b-121">Configure</span></span>

<span data-ttu-id="0336b-122">Skapa ett paket för säker konfigurationsetablering</span><span class="sxs-lookup"><span data-stu-id="0336b-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="0336b-123">Starta WCD-verktyget på datorn.</span><span class="sxs-lookup"><span data-stu-id="0336b-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="0336b-124">Välj File -> Open project (Arkiv **-> Open project).**</span><span class="sxs-lookup"><span data-stu-id="0336b-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="0336b-125">Navigera till platsen för den tidigare sparade OfflineSecureHL2_Sample mapp och välj: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="0336b-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="0336b-126">Projektet bör öppnas och du bör nu ha en lista över tillgängliga anpassningar:</span><span class="sxs-lookup"><span data-stu-id="0336b-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0336b-127">![Skärmbild av konfigurationspaketet som är öppet i WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="0336b-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="0336b-128">Konfigurationer som anges i det här konfigurationspaketet:</span><span class="sxs-lookup"><span data-stu-id="0336b-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="0336b-129">Objekt</span><span class="sxs-lookup"><span data-stu-id="0336b-129">Item</span></span>                                                |     <span data-ttu-id="0336b-130">Inställning</span><span class="sxs-lookup"><span data-stu-id="0336b-130">Setting</span></span>                       |     <span data-ttu-id="0336b-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0336b-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="0336b-132">Konton/användare</span><span class="sxs-lookup"><span data-stu-id="0336b-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="0336b-133">Lokalt användarnamn och & lösenord</span><span class="sxs-lookup"><span data-stu-id="0336b-133">Local User Name & Password</span></span>    |     <span data-ttu-id="0336b-134">För dessa offlineenheter måste ett enda användarnamn och lösenord anges och delas av alla användare av enheten.</span><span class="sxs-lookup"><span data-stu-id="0336b-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="0336b-135">First Experience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="0336b-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="0336b-136">Sant</span><span class="sxs-lookup"><span data-stu-id="0336b-136">True</span></span>                          |     <span data-ttu-id="0336b-137">Hoppar över kalibrering endast under den första enhetskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="0336b-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="0336b-138">First Experience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="0336b-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="0336b-139">Sant</span><span class="sxs-lookup"><span data-stu-id="0336b-139">True</span></span>                          |     <span data-ttu-id="0336b-140">Hoppar över enhetsträning under den inledande enhetskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="0336b-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="0336b-141">Första upplevelsen/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="0336b-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="0336b-142">Sant</span><span class="sxs-lookup"><span data-stu-id="0336b-142">True</span></span>                          |     <span data-ttu-id="0336b-143">Hoppar Wi-Fi konfigurationen under den inledande enhetskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="0336b-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="0336b-144">Principer/Anslutning/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="0336b-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="0336b-145">Inga</span><span class="sxs-lookup"><span data-stu-id="0336b-145">No</span></span>                            |     <span data-ttu-id="0336b-146">Inaktiverar Bluetooth</span><span class="sxs-lookup"><span data-stu-id="0336b-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="0336b-147">Principer/erfarenhet/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="0336b-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="0336b-148">Inga</span><span class="sxs-lookup"><span data-stu-id="0336b-148">No</span></span>                            |     <span data-ttu-id="0336b-149">Inaktiverar Cortana (för att eliminera potentiella problem eftersom mikrofonerna är inaktiverade)</span><span class="sxs-lookup"><span data-stu-id="0336b-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="0336b-150">Principer/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="0336b-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="0336b-151">Ja</span><span class="sxs-lookup"><span data-stu-id="0336b-151">Yes</span></span>                           |     <span data-ttu-id="0336b-152">Inaktiverar mikrofon</span><span class="sxs-lookup"><span data-stu-id="0336b-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="0336b-153">Principer/Sekretess/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="0336b-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="0336b-154">Framtrigt neka</span><span class="sxs-lookup"><span data-stu-id="0336b-154">Force deny</span></span>                    |     <span data-ttu-id="0336b-155">Förhindrar att appar försöker komma åt platsdata (för att eliminera potentiella problem eftersom Platsspårning är inaktiverat)</span><span class="sxs-lookup"><span data-stu-id="0336b-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="0336b-156">Principer/Sekretess/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="0336b-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="0336b-157">Framtrigt neka</span><span class="sxs-lookup"><span data-stu-id="0336b-157">Force deny</span></span>                    |     <span data-ttu-id="0336b-158">Förhindrar att appar försöker komma åt mikrofoner (för att eliminera potentiella problem eftersom mikrofonerna är inaktiverade)</span><span class="sxs-lookup"><span data-stu-id="0336b-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="0336b-159">Principer/Säkerhet/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="0336b-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="0336b-160">Inga</span><span class="sxs-lookup"><span data-stu-id="0336b-160">No</span></span>                            |     <span data-ttu-id="0336b-161">Förhindrar att alla lägger till etableringspaket som kan försöka åsidosätta låsta principer.</span><span class="sxs-lookup"><span data-stu-id="0336b-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="0336b-162">Principer/Säkerhet/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="0336b-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="0336b-163">Inga</span><span class="sxs-lookup"><span data-stu-id="0336b-163">No</span></span>                            |     <span data-ttu-id="0336b-164">Förhindrar att någon tar bort det låsta etableringspaketet.</span><span class="sxs-lookup"><span data-stu-id="0336b-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="0336b-165">Principer/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="0336b-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="0336b-166">Inga</span><span class="sxs-lookup"><span data-stu-id="0336b-166">No</span></span>                            |     <span data-ttu-id="0336b-167">Förhindrar att enheten försöker spåra platsdata.</span><span class="sxs-lookup"><span data-stu-id="0336b-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="0336b-168">Principer/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="0336b-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="0336b-169">Inga</span><span class="sxs-lookup"><span data-stu-id="0336b-169">No</span></span>                            |     <span data-ttu-id="0336b-170">Inaktiverar Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0336b-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="0336b-171">Under Körningsinställningar väljer du **Konton/Användare/Användarnamn: Holo/Lösenord.**</span><span class="sxs-lookup"><span data-stu-id="0336b-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="0336b-172">Anteckna lösenordet och återställ om du vill.</span><span class="sxs-lookup"><span data-stu-id="0336b-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="0336b-173">Gå till UniversalAppInstall/UserContextApp och [konfigurera den LOB-app](app-deploy-provisioning-package.md) som du ska distribuera till dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="0336b-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0336b-174">![Skärmbild av var du lägger till din app i WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="0336b-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="0336b-175">När du är klar väljer du knappen "Exportera" och följer alla uppmaningar tills ditt etableringspaket har skapats.</span><span class="sxs-lookup"><span data-stu-id="0336b-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0336b-176">![Skärmbild av knappen Exportera för det här paketet i WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="0336b-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="0336b-177">Distribuera</span><span class="sxs-lookup"><span data-stu-id="0336b-177">Deploy</span></span>

1. <span data-ttu-id="0336b-178">Anslut HL2 till din Windows 10 via USB-kabel.</span><span class="sxs-lookup"><span data-stu-id="0336b-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="0336b-179">Starta ARC-verktyget och välj **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="0336b-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 , inledande skärm med rent omstreck](images/ARC2.png)

1. <span data-ttu-id="0336b-181">På nästa skärm väljer du **Manuellt paketval.**</span><span class="sxs-lookup"><span data-stu-id="0336b-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC-informationsskärmen](images/arc_device_info.png)

1. <span data-ttu-id="0336b-183">Gå till den tidigare nedladdade .ffu-filen och välj **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="0336b-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="0336b-184">På sidan Varning väljer du **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="0336b-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC-varningsskärm](images/arc_warning.png)

1. <span data-ttu-id="0336b-186">Vänta tills ARC-verktyget har slutfört HoloLens 2 OS-installationen.</span><span class="sxs-lookup"><span data-stu-id="0336b-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="0336b-187">När enheten har slutfört installationen och startar igen går du från datorn till Utforskaren och kopierar den tidigare sparade PPKG-filen till enhetsmappen.</span><span class="sxs-lookup"><span data-stu-id="0336b-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0336b-188">![PPKG-fil på datorn i Utforskaren fönster.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="0336b-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="0336b-189">På HoloLens 2 trycker du på följande knappkombination för  att köra etableringspaketet: Tryck på Volym ned och **Strömknapp** på samma gång.</span><span class="sxs-lookup"><span data-stu-id="0336b-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="0336b-190">Du uppmanas att tillämpa etableringspaketet och välja **Bekräfta**</span><span class="sxs-lookup"><span data-stu-id="0336b-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="0336b-191">När etableringspaketet är klart väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="0336b-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="0336b-192">Du bör sedan uppmanas att logga in på enheten med det delade lokala kontot och lösenordet.</span><span class="sxs-lookup"><span data-stu-id="0336b-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="0336b-193">Underhåll</span><span class="sxs-lookup"><span data-stu-id="0336b-193">Maintain</span></span>

<span data-ttu-id="0336b-194">Med den här konfigurationen rekommenderar vi att du startar om processen ovan och omstreckar enheten med ARC-verktyget och tillämpar ett nytt PPKG för att göra uppdateringar av operativsystemet och/eller program.</span><span class="sxs-lookup"><span data-stu-id="0336b-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
