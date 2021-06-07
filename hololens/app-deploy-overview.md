---
title: Översikt – Apphantering
description: Kom igång med en översikt över apphantering med mixad verklighet med hantering av mobila enheter, Microsoft Store för företag och etableringspaket.
keywords: HoloLens, user, account, app, application management,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378765"
---
# <a name="app-management-overview"></a><span data-ttu-id="1ed9a-104">Apphantering: Översikt</span><span class="sxs-lookup"><span data-stu-id="1ed9a-104">App Management: Overview</span></span>

<span data-ttu-id="1ed9a-105">Du kan distribuera appar på fyra olika sökvägar: **Mobile Enhetshantering (MDM),** **Microsoft Store för företag**, **Microsoft Store** eller genom att installera dem via **Etablera**.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="1ed9a-106">Mobile Enhetshantering (MDM)</span><span class="sxs-lookup"><span data-stu-id="1ed9a-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="1ed9a-107">En MDM-lösning gör det möjligt för IT-beslutsfattare och administratörer att automatiskt installera (push-installera) sina egna, verksamhetsbaserade appar eller köpa appar via butiken för en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="1ed9a-108">HoloLens-enheter fungerar bäst med Microsoft Endpoint Manager (Intune) för [programhantering.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="1ed9a-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="1ed9a-109">Intune erbjuder även användare mer begränsad kontroll över IT-hanterade appar via Företagsportal nedladdningsbara upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed9a-110">Följande anvisningar är för användare som vill hantera sina program med Intune.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="1ed9a-111">Microsoft rekommenderar att du använder Intune för program- och enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="1ed9a-112">Mobile Enhetshantering (MDM) gäller för:</span><span class="sxs-lookup"><span data-stu-id="1ed9a-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="1ed9a-113">MDM distribuerad + Företagsportal</span><span class="sxs-lookup"><span data-stu-id="1ed9a-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="1ed9a-114">Verksamhetsapplikationer (icke-offentliga) appar</span><span class="sxs-lookup"><span data-stu-id="1ed9a-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="1ed9a-115">Manuell installation av tillgängliga program via Företagsportal</span><span class="sxs-lookup"><span data-stu-id="1ed9a-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="1ed9a-116">Push-meddelanden för administratörer via MDM-princip</span><span class="sxs-lookup"><span data-stu-id="1ed9a-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="1ed9a-117">Automatisk uppdatering via MDM</span><span class="sxs-lookup"><span data-stu-id="1ed9a-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="1ed9a-118">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="1ed9a-118">Microsoft Store for Business</span></span>

<span data-ttu-id="1ed9a-119">Med [Microsoft Store för företag](app-deploy-store-business.md) IT-beslutsfattare och administratörer i företag att hitta, skaffa, hantera och distribuera kostnadsfria och betalda appar.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="1ed9a-120">IT-administratörer kan hantera Microsoft Store-appar och privata verksamhetsapplikationer i ett lager, samt tilldela och återanvända licenser efter behov.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="1ed9a-121">Mer information finns i [Krav för att använda Microsoft Store för företag](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="1ed9a-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="1ed9a-122">Följande Microsoft Store för företag gäller för:</span><span class="sxs-lookup"><span data-stu-id="1ed9a-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="1ed9a-123">Offentliga appar eller verksamhetsapplikationer</span><span class="sxs-lookup"><span data-stu-id="1ed9a-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="1ed9a-124">Automatisk installation av nödvändiga program via MDM-association</span><span class="sxs-lookup"><span data-stu-id="1ed9a-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="1ed9a-125">Användaren laddar ned appar manuellt</span><span class="sxs-lookup"><span data-stu-id="1ed9a-125">User manually downloads apps</span></span>
* <span data-ttu-id="1ed9a-126">Automatisk uppdatering</span><span class="sxs-lookup"><span data-stu-id="1ed9a-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="1ed9a-127">Microsoft Store-appar</span><span class="sxs-lookup"><span data-stu-id="1ed9a-127">Microsoft Store apps</span></span>

<span data-ttu-id="1ed9a-128">Med Microsoft Store it-beslutsfattare och administratörer i företag att hitta, skaffa, hantera och distribuera offentliga appar.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="1ed9a-129">Den Microsoft Store här Microsoft Store gäller för:</span><span class="sxs-lookup"><span data-stu-id="1ed9a-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="1ed9a-130">Endast offentliga appar</span><span class="sxs-lookup"><span data-stu-id="1ed9a-130">Public apps only</span></span>
* <span data-ttu-id="1ed9a-131">Användaren laddar ned appar manuellt</span><span class="sxs-lookup"><span data-stu-id="1ed9a-131">User manually downloads apps</span></span>
* <span data-ttu-id="1ed9a-132">Uppdatera automatiskt om du är ansluten till Internet</span><span class="sxs-lookup"><span data-stu-id="1ed9a-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="1ed9a-133">Mer information finns i [Holographic Store-appar.](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="1ed9a-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="1ed9a-134">Installera via etableringspaket</span><span class="sxs-lookup"><span data-stu-id="1ed9a-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="1ed9a-135">[Med etableringspaket](app-deploy-provisioning-package.md) kan du installera anpassade appar eller branschapplikationer, så att IT-proffs och administratörer snabbt kan installera appar på en lokal enhet via USB.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="1ed9a-136">Den här installationen kan göras utan internetanslutning och för alla identitetstyper.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="1ed9a-137">Installation via etableringspaket gäller för:</span><span class="sxs-lookup"><span data-stu-id="1ed9a-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="1ed9a-138">Verksamhets-/egenutvecklade (icke-offentliga) appar</span><span class="sxs-lookup"><span data-stu-id="1ed9a-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="1ed9a-139">Offentliga appar (om offlineinstallationsprogram är tillgängligt)</span><span class="sxs-lookup"><span data-stu-id="1ed9a-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="1ed9a-140">Endast USB-sidladdning</span><span class="sxs-lookup"><span data-stu-id="1ed9a-140">USB side-loading only</span></span>
* <span data-ttu-id="1ed9a-141">Ingen automatisk uppdatering (kräver manuella uppdateringar via etableringspaket)</span><span class="sxs-lookup"><span data-stu-id="1ed9a-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="1ed9a-142">Installera appar på HoloLens 2 via Appinstallationsprogram</span><span class="sxs-lookup"><span data-stu-id="1ed9a-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="1ed9a-143">Med hjälp [Appinstallationsprogram](app-deploy-app-installer.md) användare en upplevelse som är enkel för att installera appar på lokala enheter eller dela en app med någon annan som inte är bekant med andra appinstallationsmetoder på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="1ed9a-144">Detta kan göras utan att du behöver aktivera utvecklarläge eller använda Enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="1ed9a-145">Det här är en enkel metod för att distribuera en helt skapad app.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="1ed9a-146">Oavsett om du bara vill degradera din app till en annan användare med en HoloLens eller om du vill distribuera din app fungerar den här metoden enkelt.</span><span class="sxs-lookup"><span data-stu-id="1ed9a-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="1ed9a-147">Installation via Appinstallationsprogram gäller för:</span><span class="sxs-lookup"><span data-stu-id="1ed9a-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="1ed9a-148">Verksamhets-/egenutvecklade (icke-offentliga) appar</span><span class="sxs-lookup"><span data-stu-id="1ed9a-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="1ed9a-149">Endast sidobelastning</span><span class="sxs-lookup"><span data-stu-id="1ed9a-149">Side-load only</span></span>
* <span data-ttu-id="1ed9a-150">Kräver inte utvecklarläge eller enhetsportal</span><span class="sxs-lookup"><span data-stu-id="1ed9a-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="1ed9a-151">Enkelt för slutanvändare att installera</span><span class="sxs-lookup"><span data-stu-id="1ed9a-151">Easy for end user to install</span></span>
