---
title: Etableringspaket
description: Lär dig mer om apppaketering, etablering, distribution och distribution av företagsapp för HoloLens-enheter.
keywords: app, app deployment, enterprise app deployment, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378797"
---
# <a name="provisioning-package"></a><span data-ttu-id="73f03-104">Etableringspaket</span><span class="sxs-lookup"><span data-stu-id="73f03-104">Provisioning Package</span></span>

<span data-ttu-id="73f03-105">Konfigurationspaket kan användas för att förbereda och konfigurera enheter i en miljö utan åtkomst till slutpunktshantering.</span><span class="sxs-lookup"><span data-stu-id="73f03-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="73f03-106">De kan också distribueras till en enhet oavsett användarens identitet, registreringsstatus, under Oobe (Out of Box Experience) eller genom att använda ett konfigurationspaket under [installationen.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="73f03-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="73f03-107">Överväganden för etableringspaket:</span><span class="sxs-lookup"><span data-stu-id="73f03-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="73f03-108">Icke-offentliga appar</span><span class="sxs-lookup"><span data-stu-id="73f03-108">Non-Public apps</span></span>
* <span data-ttu-id="73f03-109">Endast USB-sidobelastning</span><span class="sxs-lookup"><span data-stu-id="73f03-109">USB side-load only</span></span>
* <span data-ttu-id="73f03-110">Ingen automatisk uppdatering (kräver manuella uppdateringar via PPKG:er)</span><span class="sxs-lookup"><span data-stu-id="73f03-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="73f03-111">Appar som installeras via ett etableringspaket måste signeras av ett certifikat i det lokala datorarkivet.</span><span class="sxs-lookup"><span data-stu-id="73f03-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="73f03-112">Etableringspaket kan bara installera certifikat till enhetens (den lokala datorns) arkiv, och därför kan en app och ett certifikat installeras via samma etableringspaket.</span><span class="sxs-lookup"><span data-stu-id="73f03-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="73f03-113">Om du distribuerar certifikatet från MDM eller installerar via [Certifikathanteraren](certificate-manager.md)distribuerar du certifikatet till det lokala datorarkivet för att signera appar som installerats på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="73f03-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="73f03-114">Om du vill lära dig grunderna för att skapa ett etableringspaket för HoloLens-enheter kan du gå [till HoloLens-etablering.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="73f03-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="73f03-115">Om du vill distribuera en app måste du börja med avancerad etablering.</span><span class="sxs-lookup"><span data-stu-id="73f03-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="73f03-116">HoloLens (första generationen) har begränsat stöd för installation av appar **(UniversalAppInstall)** med hjälp av ett etableringspaket.</span><span class="sxs-lookup"><span data-stu-id="73f03-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="73f03-117">HoloLens-enheter (första generationen) stöder endast installation av en app via PPKG under OOBE och endast med användarkontextinstallationer.</span><span class="sxs-lookup"><span data-stu-id="73f03-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="73f03-118">Installation</span><span class="sxs-lookup"><span data-stu-id="73f03-118">Setup</span></span>

<span data-ttu-id="73f03-119">I [Windows Configuration Designer gör](https://www.microsoft.com/store/productId/9NBLGGH4TX22) du följande fyra steg.</span><span class="sxs-lookup"><span data-stu-id="73f03-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="73f03-120">Ange ApplicationManagement/AllowAllTrustedApps till "Ja".</span><span class="sxs-lookup"><span data-stu-id="73f03-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="73f03-121">Se: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="73f03-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="73f03-122">Gå till **UniversalAppInstall**  >  **UserContextAppLicense** och ange **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="73f03-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="73f03-123">Se [UniversalAppInstallera](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="73f03-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="73f03-124">Se även: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="73f03-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="73f03-125">Du kan använda Enhetsportalen på en enhet som du redan har installerat appen på.</span><span class="sxs-lookup"><span data-stu-id="73f03-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="73f03-126">Besök sidan Appar och titta på raden PackageRelativeID, all information före "!" Är **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="73f03-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="73f03-127">Du ser då att du har ett nytt avsnitt, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="73f03-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="73f03-128">Använd det här området för att ladda upp ditt appx-paket.</span><span class="sxs-lookup"><span data-stu-id="73f03-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="73f03-129">Beroende på om du har köpt din app eller skapat en egen LOB-app måste du ladda upp licensfilen eller säkerhetscertifikatet.</span><span class="sxs-lookup"><span data-stu-id="73f03-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="73f03-130">För licensfil: navigera till **UniversalAppInstallera**  >  **användareContextAppLicence** och bläddra till platsen för din licens och ladda upp den.</span><span class="sxs-lookup"><span data-stu-id="73f03-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="73f03-131">För säkerhetsfilen går du till Certifikat **och väljer** det certifikat som ska installeras tillsammans med ditt .appx-paket.</span><span class="sxs-lookup"><span data-stu-id="73f03-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="73f03-132">Se till att spara projektet på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="73f03-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="73f03-133">Exportera **den** sedan som ett **etableringspaket**.</span><span class="sxs-lookup"><span data-stu-id="73f03-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="73f03-134">Se även: [Tillämpa ditt etableringspaket på HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="73f03-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
