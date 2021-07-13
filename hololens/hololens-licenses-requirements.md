---
title: Licenskrav
description: Håll dig uppdaterad med alla licenskrav och riktlinjer som du behöver för hantering av mobila enheter, HoloLens och Fjärrhjälp.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640294"
---
# <a name="license-requirements"></a><span data-ttu-id="70832-103">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="70832-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="70832-104">HoloLens 2-enhet (hanterad)</span><span class="sxs-lookup"><span data-stu-id="70832-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="70832-105">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="70832-105">Azure AD Account</span></span>](/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="70832-106">Active Directory (AD) kan inte användas för att hantera HoloLens enheter.</span><span class="sxs-lookup"><span data-stu-id="70832-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="70832-107">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) eller någon annan MDM.</span><span class="sxs-lookup"><span data-stu-id="70832-107">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="70832-108">[Windows Autopilot för HoloLens 2](hololens2-autopilot.md)– förenklar etableringen för både IT-administratörer och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="70832-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="70832-109">IT-administratörer kan förkonfigurera HoloLens 2 principer, och vid första starten distribueras enheter i företagsklart tillstånd utan interaktion från slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="70832-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="70832-110">Windows Autopilot kräver [att Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) [och automatisk registrering](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) först konfigureras för Autopilot-flödet med låg pekfunktion och distribution av enheter.</span><span class="sxs-lookup"><span data-stu-id="70832-110">Windows Autopilot requires [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="70832-111">Användningsfall för företag:</span><span class="sxs-lookup"><span data-stu-id="70832-111">Business Use Case:</span></span> 

- <span data-ttu-id="70832-112">[Distributionsscenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) – konceptbevis eller pilotdistribution.</span><span class="sxs-lookup"><span data-stu-id="70832-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="70832-113">[Distributionsscenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) – distribution i stor skala.</span><span class="sxs-lookup"><span data-stu-id="70832-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="70832-114">HoloLens 2 Endast enhet (ej hanterad)</span><span class="sxs-lookup"><span data-stu-id="70832-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="70832-115">När du använder antingen ett Microsoft-konto (MSA) eller ett lokalt konto krävs inga ytterligare licenser för dessa konton.</span><span class="sxs-lookup"><span data-stu-id="70832-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="70832-116">Lokalt konto</span><span class="sxs-lookup"><span data-stu-id="70832-116">Local Account</span></span>](/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="70832-117">Det här kontot måste [etableras](hololens-provisioning.md#provisioning-package-hololens-wizard) i förväg med Windows Configuration Designer (WCD).</span><span class="sxs-lookup"><span data-stu-id="70832-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="70832-118">Microsoft-konto (MSA)</span><span class="sxs-lookup"><span data-stu-id="70832-118">Microsoft Account (MSA)</span></span>](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="70832-119">Flera användare stöds inte för en enhet som använder något av dessa konton.</span><span class="sxs-lookup"><span data-stu-id="70832-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="70832-120">Användningsfall för företag:</span><span class="sxs-lookup"><span data-stu-id="70832-120">Business Use Case:</span></span> 

- <span data-ttu-id="70832-121">[Distributionsscenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) – offline eller säker distribution.</span><span class="sxs-lookup"><span data-stu-id="70832-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="70832-122">Licensiering och krav för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="70832-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="70832-123">Fjärrhjälp för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="70832-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="70832-124">Administratör</span><span class="sxs-lookup"><span data-stu-id="70832-124">Admin</span></span>

- <span data-ttu-id="70832-125">Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)</span><span class="sxs-lookup"><span data-stu-id="70832-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="70832-126">[Remote Assist-prenumeration](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="70832-126">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="70832-127">Dynamics 365 Remote Assist-användare</span><span class="sxs-lookup"><span data-stu-id="70832-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="70832-128">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="70832-128">Azure AD account</span></span>

- <span data-ttu-id="70832-129">Remote Assist-licens</span><span class="sxs-lookup"><span data-stu-id="70832-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="70832-130">Microsoft Teams paketeras med Remote Assist</span><span class="sxs-lookup"><span data-stu-id="70832-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="70832-131">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="70832-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="70832-132">Microsoft Teams användare</span><span class="sxs-lookup"><span data-stu-id="70832-132">Microsoft Teams user</span></span>

- <span data-ttu-id="70832-133">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="70832-133">Azure AD account</span></span>

- <span data-ttu-id="70832-134">Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="70832-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="70832-135">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="70832-135">Network connectivity</span></span>

<span data-ttu-id="70832-136">Om du planerar att implementera det här [scenariot för flera klienter](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en informationsbarriärlicens.</span><span class="sxs-lookup"><span data-stu-id="70832-136">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="70832-137">Se [den här artikeln](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) för att avgöra om en Information Barrier-licens krävs.</span><span class="sxs-lookup"><span data-stu-id="70832-137">See [this article](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="70832-138">Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="70832-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="70832-139">Administratör</span><span class="sxs-lookup"><span data-stu-id="70832-139">Admin</span></span>

- <span data-ttu-id="70832-140">Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)</span><span class="sxs-lookup"><span data-stu-id="70832-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="70832-141">Prenumeration på Dynamics 365-guider [eller kostnadsfri utvärderingsversion](/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="70832-141">Dynamics 365 [Guides subscription or free trial](/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="70832-142">Skapare av guider</span><span class="sxs-lookup"><span data-stu-id="70832-142">Guides Author</span></span>

1. <span data-ttu-id="70832-143">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="70832-143">Azure AD account</span></span>
1. [<span data-ttu-id="70832-144">Licens för Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="70832-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="70832-145">Dynamics 365 Guides-programmet installerat på en dator eller HoloLens</span><span class="sxs-lookup"><span data-stu-id="70832-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="70832-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (används för att visa Analytics-instrumentpanelen)</span><span class="sxs-lookup"><span data-stu-id="70832-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="70832-147">Författarroll (för att skapa guider)</span><span class="sxs-lookup"><span data-stu-id="70832-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="70832-148">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="70832-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="70832-149">Användare av guider</span><span class="sxs-lookup"><span data-stu-id="70832-149">Guides User</span></span>

1. <span data-ttu-id="70832-150">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="70832-150">Azure AD account</span></span>
1. [<span data-ttu-id="70832-151">Licens för Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="70832-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="70832-152">Appen Dynamics 365 Guides installerad på en HoloLens</span><span class="sxs-lookup"><span data-stu-id="70832-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="70832-153">Operatörsroll (för testning eller användning av guider)</span><span class="sxs-lookup"><span data-stu-id="70832-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="70832-154">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="70832-154">Network Connectivity</span></span>
