---
title: HoloLens BitLocker-kryptering
description: Lär dig hur du aktiverar BitLocker-enhetskryptering för att skydda filer som lagras HoloLens enheter med mixad verklighet.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635253"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="61837-103">HoloLens (första generationens) BitLocker-kryptering</span><span class="sxs-lookup"><span data-stu-id="61837-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="61837-104">HoloLens (första generationen) och HoloLens 2 stöder båda enhetskryptering med BitLocker, men BitLocker är alltid aktiverat på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="61837-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="61837-105">Den här artikeln hjälper dig att aktivera och hantera BitLocker på HoloLens (första gen).</span><span class="sxs-lookup"><span data-stu-id="61837-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="61837-106">På HoloLens (första generationen) kan du aktivera BitLocker-enhetskryptering manuellt eller med hjälp av hantering av mobila enheter (MDM).</span><span class="sxs-lookup"><span data-stu-id="61837-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="61837-107">Följ dessa anvisningar för att aktivera [BitLocker-enhetskryptering](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) för att skydda filer och information som lagras på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="61837-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="61837-108">Med enhetskryptering kan du skydda dina data med krypteringsmetoden AES-CBC 128, som motsvarar [EncryptionMethodByDriveType-metoden 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) i BitLocker-konfigurationstjänstprovidern (CSP).</span><span class="sxs-lookup"><span data-stu-id="61837-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="61837-109">Personal som har rätt krypteringsnyckel (till exempel ett lösenord) kan dekryptera den eller utföra en dataåterställning.</span><span class="sxs-lookup"><span data-stu-id="61837-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="61837-110">Aktivera enhetskryptering med MDM</span><span class="sxs-lookup"><span data-stu-id="61837-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="61837-111">Du kan använda MDM-providern (Mobile Enhetshantering) för att tillämpa en princip som kräver enhetskryptering.</span><span class="sxs-lookup"><span data-stu-id="61837-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="61837-112">Den princip som ska användas är [inställningen Säkerhet/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) i CSP-princip.</span><span class="sxs-lookup"><span data-stu-id="61837-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="61837-113">Se anvisningar för att aktivera enhetskryptering med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="61837-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="61837-114">För andra MDM-verktyg, se mdm-providerns dokumentation för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="61837-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="61837-115">Om MDM-providern kräver anpassad URI för enhetskryptering använder du följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="61837-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="61837-116">**Namn:** val av namn</span><span class="sxs-lookup"><span data-stu-id="61837-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="61837-117">**Beskrivning**: valfritt</span><span class="sxs-lookup"><span data-stu-id="61837-117">**Description**: optional</span></span>
- <span data-ttu-id="61837-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="61837-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="61837-119">**Datatyp:** heltal</span><span class="sxs-lookup"><span data-stu-id="61837-119">**Data type**: integer</span></span>
- <span data-ttu-id="61837-120">**Värde**: `1`</span><span class="sxs-lookup"><span data-stu-id="61837-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="61837-121">Aktivera enhetskryptering med ett etableringspaket</span><span class="sxs-lookup"><span data-stu-id="61837-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="61837-122">Konfigurationspaket är filer som skapas av Windows Configuration Designer-verktyget som tillämpar en angiven konfiguration på en enhet.</span><span class="sxs-lookup"><span data-stu-id="61837-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="61837-123">Skapa ett etableringspaket som uppgraderar Windows Holographic Edition och aktiverar kryptering</span><span class="sxs-lookup"><span data-stu-id="61837-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="61837-124">Skapa ett etableringspaket för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="61837-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="61837-125">Gå till **Körningsinställningar**  >    >  **Principer Säkerhet** och välj **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="61837-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Kräv inställningen enhetskryptering inställd på Ja](images/device-encryption.png)

1. <span data-ttu-id="61837-127">Leta reda på XML-licensfilen som angavs när du köpte Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="61837-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="61837-128">Bläddra till och välj XML-licensfilen som angavs när du köpte Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="61837-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="61837-129">Du kan konfigurera [ytterligare inställningar i konfigurationspaketet](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="61837-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="61837-130">Klicka på **Spara** på **Arkiv**-menyn.</span><span class="sxs-lookup"><span data-stu-id="61837-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="61837-131">Läs varningen som förklarar att projektfiler kan innehålla känslig information och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="61837-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="61837-132">När du skapar ett etableringspaket kan du inkludera känslig information i projektfilerna och etableringspaketfilen (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="61837-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="61837-133">Även om du har möjlighet att kryptera .ppkg-filen krypteras inte projektfilerna.</span><span class="sxs-lookup"><span data-stu-id="61837-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="61837-134">Du bör lagra projektfilerna på en säker plats och ta bort projektfilerna när de inte längre behövs.</span><span class="sxs-lookup"><span data-stu-id="61837-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="61837-135">På menyn **Exportera** klickar du på **Etableringspaket**.</span><span class="sxs-lookup"><span data-stu-id="61837-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="61837-136">Ändra **Ägare** till **IT-administratör**, vilket anger högre prioritet för det här etableringspaketet än de etableringspaket som tillämpas på den här enheten från andra källor och välj **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="61837-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="61837-137">Ange ett värde för **Paketversion**.</span><span class="sxs-lookup"><span data-stu-id="61837-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="61837-138">Du kan göra ändringar i befintliga paket och ändra versionsnumret för att uppdatera tidigare tillämpade paket.</span><span class="sxs-lookup"><span data-stu-id="61837-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="61837-139">På sidan **Välj säkerhetsinformation för etableringspaketet klickar** du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="61837-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="61837-140">Klicka **på** Nästa för att ange den utdataplats där du vill att etableringspaketet ska gå när det har skapats.</span><span class="sxs-lookup"><span data-stu-id="61837-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="61837-141">Som standard Windows ICD projektmappen som utdataplats.</span><span class="sxs-lookup"><span data-stu-id="61837-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="61837-142">Du kan också klicka på Bläddra för att ändra standardplatsen för utdata.</span><span class="sxs-lookup"><span data-stu-id="61837-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="61837-143">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="61837-143">Click **Next**.</span></span>
1. <span data-ttu-id="61837-144">Klicka **på Skapa** för att börja skapa paketet.</span><span class="sxs-lookup"><span data-stu-id="61837-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="61837-145">Projektinformationen visas på byggsidan och förloppsfältet anger byggstatus.</span><span class="sxs-lookup"><span data-stu-id="61837-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="61837-146">När bygget är klart klickar du på **Slutför.**</span><span class="sxs-lookup"><span data-stu-id="61837-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="61837-147">Tillämpa etableringspaketet på HoloLens</span><span class="sxs-lookup"><span data-stu-id="61837-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="61837-148">Anslut enheten via USB till en dator och starta enheten, men  fortsätt inte förbi anpassa-sidan för den första installationsupplevelsen (den första sidan med den blå rutan).</span><span class="sxs-lookup"><span data-stu-id="61837-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="61837-149">Tryck kort på och släpp knapparna **Volym ned** **och Ström** samtidigt.</span><span class="sxs-lookup"><span data-stu-id="61837-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="61837-150">HoloLens visas som en enhet i Utforskaren på datorn.</span><span class="sxs-lookup"><span data-stu-id="61837-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="61837-151">I Utforskaren du och släpper etableringspaketet (.ppkg) till enhetens lagring.</span><span class="sxs-lookup"><span data-stu-id="61837-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="61837-152">Tryck kort och släpp knapparna **Volym ned** och **Ström** samtidigt på **anpassa-sidan.**</span><span class="sxs-lookup"><span data-stu-id="61837-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="61837-153">Enheten frågar dig om du litar på paketet och vill tillämpa det.</span><span class="sxs-lookup"><span data-stu-id="61837-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="61837-154">Bekräfta att du litar på paketet.</span><span class="sxs-lookup"><span data-stu-id="61837-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="61837-155">Du ser om paketet har tillämpats korrekt eller inte.</span><span class="sxs-lookup"><span data-stu-id="61837-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="61837-156">Om det misslyckades kan du åtgärda paketet och försöka igen.</span><span class="sxs-lookup"><span data-stu-id="61837-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="61837-157">Om det lyckades fortsätter du med enhetskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="61837-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="61837-158">Om enheten köptes före augusti 2016 måste du logga in på enheten med en Microsoft-konto, hämta den senaste OS-uppdateringen och sedan återställa operativsystemet för att tillämpa etableringspaketet.</span><span class="sxs-lookup"><span data-stu-id="61837-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="61837-159">Verifiera enhetskryptering</span><span class="sxs-lookup"><span data-stu-id="61837-159">Verify device encryption</span></span>

<span data-ttu-id="61837-160">Krypteringen är tyst på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="61837-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="61837-161">Så här kontrollerar du enhetens krypteringsstatus:</span><span class="sxs-lookup"><span data-stu-id="61837-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="61837-162">På HoloLens du till **Inställningar**  >  **System**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="61837-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="61837-163">**BitLocker** **aktiveras** om enheten är krypterad.</span><span class="sxs-lookup"><span data-stu-id="61837-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Om skärmen som visar Att BitLocker är aktiverat](images/about-encryption.png)
