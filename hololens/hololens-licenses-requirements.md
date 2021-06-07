---
title: Licenskrav
description: Håll dig uppdaterad med alla licenskrav och riktlinjer som du behöver för hantering av mobila enheter, HoloLens och Remote Assist.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380073"
---
# <a name="license-requirements"></a><span data-ttu-id="23ee8-103">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="23ee8-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="23ee8-104">Vägledning för MDM Enhetshantering licenser (Mobile Enhetshantering)</span><span class="sxs-lookup"><span data-stu-id="23ee8-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="23ee8-105">Om du planerar att hantera dina HoloLens-enheter behöver du Azure AD och en MDM.</span><span class="sxs-lookup"><span data-stu-id="23ee8-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="23ee8-106">Active Director (AD) kan inte användas för att hantera HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="23ee8-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="23ee8-107">Om du planerar att använda en annan MDM än Intune krävs [Azure Active Directory en](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) ny licens.</span><span class="sxs-lookup"><span data-stu-id="23ee8-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="23ee8-108">Om du planerar att använda Intune som MDM läser du upp listan [över paket som](https://docs.microsoft.com/intune/fundamentals/licenses) innehåller Intune-licenser.</span><span class="sxs-lookup"><span data-stu-id="23ee8-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="23ee8-109">**Observera att Azure AD ingår i de flesta av dessa paket.**</span><span class="sxs-lookup"><span data-stu-id="23ee8-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="23ee8-110">Identifiera de licenser som behövs för ditt scenario och dina produkter</span><span class="sxs-lookup"><span data-stu-id="23ee8-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="23ee8-111">Licenskrav för HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="23ee8-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="23ee8-112">Du kan behöva uppgradera din HoloLens-enhet (första generationen) till Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="23ee8-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="23ee8-113">(Se [HoloLens kommersiella funktioner för](holoLens-commercial-features.md#feature-comparison-between-editions) att avgöra om du behöver uppgradera).</span><span class="sxs-lookup"><span data-stu-id="23ee8-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="23ee8-114">I så fall måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="23ee8-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="23ee8-115">Hämta en XML-fil för HoloLens Enterprise-licens</span><span class="sxs-lookup"><span data-stu-id="23ee8-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="23ee8-116">Tillämpa XML-filen på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="23ee8-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="23ee8-117">Du kan göra detta via ett [etableringspaket eller](hololens-provisioning.md) via ditt [Mobila Enhetshanteraren](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="23ee8-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="23ee8-118">Licenskrav för Remote Assist</span><span class="sxs-lookup"><span data-stu-id="23ee8-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="23ee8-119">Kontrollera att du har nödvändig licensiering och enhet, vilket du kan läsa i [kravdokumentationen.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)</span><span class="sxs-lookup"><span data-stu-id="23ee8-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="23ee8-120">Remote Assist-licens</span><span class="sxs-lookup"><span data-stu-id="23ee8-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="23ee8-121">Eller prova en [Remote Assist-utvärderingsversion](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="23ee8-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="23ee8-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="23ee8-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="23ee8-123">Azure Active Directory-licens (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="23ee8-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="23ee8-124">Om du planerar att implementera **[det här scenariot mellan klientorganisationen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** kan du behöva en licens för informationsbarriärer.</span><span class="sxs-lookup"><span data-stu-id="23ee8-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="23ee8-125">Se den [här artikeln för](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) att avgöra om en Information Barrier-licens krävs.</span><span class="sxs-lookup"><span data-stu-id="23ee8-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="23ee8-126">Licenskrav för guider</span><span class="sxs-lookup"><span data-stu-id="23ee8-126">Guides License Requirements</span></span>

<span data-ttu-id="23ee8-127">Kolla in de [uppdaterade licens- och enhetskraven.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="23ee8-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="23ee8-128">Azure Active Directory-licens (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="23ee8-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="23ee8-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="23ee8-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="23ee8-130">Guider</span><span class="sxs-lookup"><span data-stu-id="23ee8-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
