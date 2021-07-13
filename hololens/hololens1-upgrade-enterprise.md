---
title: Lås Windows Holographic for Business funktioner
description: När du uppgraderar till Windows Holographic for Business innehåller HoloLens extra funktioner som är utformade för företag.
ms.prod: hololens
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
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635202"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="9c66b-103">Lås Windows Holographic for Business funktioner</span><span class="sxs-lookup"><span data-stu-id="9c66b-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c66b-104">Den här sidan gäller endast HoloLens första generationen.</span><span class="sxs-lookup"><span data-stu-id="9c66b-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="9c66b-105">Microsoft HoloLens finns i Development *Edition*, som kör Windows Holographic (en utgåva av Windows 10 som är utformad för HoloLens) och i [Commercial Suite](hololens-commercial-features.md), som innehåller extra funktioner som är utformade för företag.</span><span class="sxs-lookup"><span data-stu-id="9c66b-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="9c66b-106">När du köper Commercial Suite får du en licens som uppgraderar Windows Holographic till Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="9c66b-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="9c66b-107">Du kan tillämpa den här licensen på enheten antingen med hjälp av organisationens [MDM-provider (hantering](#edition-upgrade-by-using-mdm) av mobila enheter) eller med [ett etableringspaket](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="9c66b-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="9c66b-108">I Windows 10 version 1803 kan du kontrollera att HoloLens har uppgraderats till Business Edition genom att **välja Inställningar**  >  **System**.</span><span class="sxs-lookup"><span data-stu-id="9c66b-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="9c66b-109">Uppgradering av utgåva med hjälp av MDM</span><span class="sxs-lookup"><span data-stu-id="9c66b-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="9c66b-110">Företagslicensen kan tillämpas av valfri MDM-provider som har stöd för [WindowsLicensing Configuration Service Provider (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)</span><span class="sxs-lookup"><span data-stu-id="9c66b-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="9c66b-111">Den senaste versionen av Microsoft MDM API stöder WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="9c66b-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="9c66b-112">Stegvisa instruktioner för att uppgradera HoloLens med hjälp av Microsoft Intune finns i Uppgradera enheter som kör [Windows Holographic till Windows Holographic for Business](/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="9c66b-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="9c66b-113">För andra MDM-leverantörer kan de specifika stegen för att konfigurera och distribuera principen variera.</span><span class="sxs-lookup"><span data-stu-id="9c66b-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="9c66b-114">Uppgradering av utgåva med hjälp av ett etableringspaket</span><span class="sxs-lookup"><span data-stu-id="9c66b-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="9c66b-115">Konfigurationspaket är filer som skapas av Windows Configuration Designer-verktyget som tillämpar en angiven konfiguration på en enhet.</span><span class="sxs-lookup"><span data-stu-id="9c66b-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="9c66b-116">Skapa ett etableringspaket som uppgraderar Windows Holographic Edition</span><span class="sxs-lookup"><span data-stu-id="9c66b-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="9c66b-117">Skapa ett etableringspaket för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9c66b-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="9c66b-118">Gå till KörningsinställningarUtgåvaUppgradera   >  och **välj EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="9c66b-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Uppgradera utgåva med licensinställning vald](images/icd1.png)

1. <span data-ttu-id="9c66b-120">Hitta XML-licensfilen som angavs när du köpte Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="9c66b-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c66b-121">Du kan konfigurera [ytterligare inställningar i konfigurationspaketet](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="9c66b-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="9c66b-122">Öppna menyn **File** (Arkiv) och välj **Save** (Spara).</span><span class="sxs-lookup"><span data-stu-id="9c66b-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="9c66b-123">Läs varningen om att projektfiler kan innehålla känslig information och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="9c66b-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9c66b-124">När du skapar ett etableringspaket kan du inkludera känslig information i projektfilerna och etableringspaketfilen (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="9c66b-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="9c66b-125">Även om du har möjlighet att kryptera .ppkg-filen krypteras inte projektfilerna.</span><span class="sxs-lookup"><span data-stu-id="9c66b-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="9c66b-126">Du bör lagra projektfilerna på en säker plats och ta bort projektfilerna när de inte längre behövs.</span><span class="sxs-lookup"><span data-stu-id="9c66b-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="9c66b-127">På menyn **Exportera** väljer du **Etableringspaket**.</span><span class="sxs-lookup"><span data-stu-id="9c66b-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="9c66b-128">Ändra **Ägare** till **IT-administratör**, vilket anger att prioriteten för det här etableringspaketet ska vara högre än andra som tillämpas på den här enheten från olika källor och välj **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="9c66b-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="9c66b-129">Ange ett värde för **Paketversion**.</span><span class="sxs-lookup"><span data-stu-id="9c66b-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9c66b-130">Du kan göra ändringar i befintliga paket och ändra versionsnumret för att uppdatera tidigare tillämpade paket.</span><span class="sxs-lookup"><span data-stu-id="9c66b-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="9c66b-131">På **Välj säkerhetsinformation för etableringspaketet** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="9c66b-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="9c66b-132">Välj **Nästa** för att ange den utdataplats där du vill att etableringspaketet ska gå när det har skapats.</span><span class="sxs-lookup"><span data-stu-id="9c66b-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="9c66b-133">Som standard Windows ICD projektmappen som utdataplats.</span><span class="sxs-lookup"><span data-stu-id="9c66b-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="9c66b-134">Du kan också välja Bläddra **för att** ändra standardplatsen för utdata.</span><span class="sxs-lookup"><span data-stu-id="9c66b-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="9c66b-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9c66b-135">Select **Next**.</span></span>

1. <span data-ttu-id="9c66b-136">Välj **Skapa** för att börja skapa paketet.</span><span class="sxs-lookup"><span data-stu-id="9c66b-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="9c66b-137">Byggsidan visar projektinformationen och förloppsfältet visar byggstatus.</span><span class="sxs-lookup"><span data-stu-id="9c66b-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="9c66b-138">När bygget är klart väljer du **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="9c66b-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="9c66b-139">Tillämpa etableringspaketet på HoloLens</span><span class="sxs-lookup"><span data-stu-id="9c66b-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="9c66b-140">Anslut enheten till en dator med hjälp av USB-kabeln.</span><span class="sxs-lookup"><span data-stu-id="9c66b-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="9c66b-141">Starta enheten, men fortsätt inte förbi sidan anpassa **för** den första installationen (den första sidan med den blå rutan).</span><span class="sxs-lookup"><span data-stu-id="9c66b-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="9c66b-142">På datorn visas HoloLens som en enhet i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="9c66b-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c66b-143">Om HoloLens-enheten körs Windows 10 version 1607 eller tidigare, öppnar du Utforskaren genom att kort  trycka på  och släppa knapparna Volym ned och Ström samtidigt på enheten.</span><span class="sxs-lookup"><span data-stu-id="9c66b-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="9c66b-144">I Utforskaren du och släpper etableringspaketet (.ppkg) till enhetens lagring.</span><span class="sxs-lookup"><span data-stu-id="9c66b-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="9c66b-145">Medan HoloLens fortfarande är på **anpassa-sidan,** trycker du kort och släpper **knapparna Volym ned** **och** Ström samtidigt igen.</span><span class="sxs-lookup"><span data-stu-id="9c66b-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="9c66b-146">HoloLens frågar om du litar på paketet och vill tillämpa det.</span><span class="sxs-lookup"><span data-stu-id="9c66b-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="9c66b-147">Bekräfta att du litar på paketet.</span><span class="sxs-lookup"><span data-stu-id="9c66b-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="9c66b-148">Du kommer att se om paketet har tillämpats korrekt eller inte.</span><span class="sxs-lookup"><span data-stu-id="9c66b-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="9c66b-149">Om det inte har tillämpats kan du åtgärda paketet och försöka igen.</span><span class="sxs-lookup"><span data-stu-id="9c66b-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="9c66b-150">Om det lyckas fortsätter du med enhetskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9c66b-150">If successful, proceed with device setup.</span></span>
