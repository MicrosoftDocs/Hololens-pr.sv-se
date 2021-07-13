---
title: Översikt över molnanslutna HoloLens 2 med Fjärrhjälp
description: Lär dig hur du registrerar HoloLens 2 enheter över ett molnanslutet nätverk med hjälp av Dynamics 365 Remote Assist.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Enhetshantering
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 26fd2def8ce1fa8f960ab930e209c74fb37e2e0a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639768"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="21462-104">Distributionsguide – Molnansluten HoloLens 2 med Remote Assist – översikt</span><span class="sxs-lookup"><span data-stu-id="21462-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="21462-105">Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Fjärrhjälp till organisationen.</span><span class="sxs-lookup"><span data-stu-id="21462-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="21462-106">Detta fungerar som en modell för konceptbevisdistributioner till din organisation i olika HoloLens 2 användningsfall.</span><span class="sxs-lookup"><span data-stu-id="21462-106">This will serve as a model for proof-of-concept deployments to your organization across various HoloLens 2 use cases.</span></span> <span data-ttu-id="21462-107">Konfigurationen liknar scenario [A: Distribuera till enheter som ansluter till molnet.](common-scenarios.md#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="21462-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](common-scenarios.md#scenario-a).</span></span> 

<span data-ttu-id="21462-108">I guiden går vi in på hur du registrerar dina enheter i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Remote Assist när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="21462-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="21462-109">För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="21462-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="21462-110">Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.</span><span class="sxs-lookup"><span data-stu-id="21462-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21462-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="21462-111">Prerequisites</span></span>

<span data-ttu-id="21462-112">Följande infrastruktur ska vara på plats för att distribuera HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="21462-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="21462-113">Om inte ingår det att konfigurera Azure och Intune i den här guiden:</span><span class="sxs-lookup"><span data-stu-id="21462-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="21462-114">Det här är en konfiguration som liknar [scenario A: Distribuera](/hololens/common-scenarios#scenario-a)till cloud connect-enheter, vilket är ett bra alternativ för många Proof of Concept-distributioner, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="21462-114">This is a setup similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="21462-115">Wi-Fi är vanligtvis helt öppna för Internet- och molntjänster</span><span class="sxs-lookup"><span data-stu-id="21462-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="21462-116">Azure AD Join med mdm-automatisk registrering – MDM-hanterad (Intune)</span><span class="sxs-lookup"><span data-stu-id="21462-116">Azure AD Join with MDM Auto Enrollment—MDM-managed (Intune)</span></span>
- <span data-ttu-id="21462-117">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="21462-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="21462-118">En eller flera användare per enhet stöds.</span><span class="sxs-lookup"><span data-stu-id="21462-118">Single or multiple users per device are supported.</span></span>

:::image type="content" alt-text="Molnanslutet scenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="21462-120">Läs mer om Remote Assist</span><span class="sxs-lookup"><span data-stu-id="21462-120">Learn about Remote Assist</span></span>

<span data-ttu-id="21462-121">Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning.</span><span class="sxs-lookup"><span data-stu-id="21462-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="21462-122">Genom att koppla samman personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare på Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21462-122">By connecting people in different roles and locations, a technician who uses Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="21462-123">De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte är på samma plats.</span><span class="sxs-lookup"><span data-stu-id="21462-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren't in the same location.</span></span> <span data-ttu-id="21462-124">Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikerns fysiska utrymme, så att de kan referera till schemat när de arbetar med huvuden och handsfree på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21462-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician's physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="21462-125">Licensiering och krav för Remote Assist</span><span class="sxs-lookup"><span data-stu-id="21462-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="21462-126">Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)</span><span class="sxs-lookup"><span data-stu-id="21462-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="21462-127">[Remote Assist-prenumeration](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="21462-127">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="21462-128">Dynamics 365 Remote Assist-användare</span><span class="sxs-lookup"><span data-stu-id="21462-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="21462-129">Remote Assist-licens</span><span class="sxs-lookup"><span data-stu-id="21462-129">Remote Assist license</span></span>
- <span data-ttu-id="21462-130">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="21462-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="21462-131">Microsoft Teams användare</span><span class="sxs-lookup"><span data-stu-id="21462-131">Microsoft Teams user</span></span>

- <span data-ttu-id="21462-132">Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="21462-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="21462-133">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="21462-133">Network connectivity</span></span>

<span data-ttu-id="21462-134">Om du planerar att implementera det här [scenariot för flera klienter](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en informationsbarriärlicens.</span><span class="sxs-lookup"><span data-stu-id="21462-134">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="21462-135">Information om huruvida en Information Barrier-licens krävs finns i Vendors and customers use full Dynamics 365 Remote Assist capabilities (Leverantörer och kunder använder fullständiga [Dynamics 365 Remote Assist-funktioner).](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)</span><span class="sxs-lookup"><span data-stu-id="21462-135">To determine if an Information Barrier License is required, see [Vendors and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="21462-136">I den här guiden kommer du att:</span><span class="sxs-lookup"><span data-stu-id="21462-136">In this guide you will:</span></span>

<span data-ttu-id="21462-137">Förbereda:</span><span class="sxs-lookup"><span data-stu-id="21462-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21462-138">Lär dig mer om grundläggande infrastruktur för HoloLens 2 enheter.</span><span class="sxs-lookup"><span data-stu-id="21462-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="21462-139">Läs mer om Azure AD och konfigurera ett om du inte&#39;inte har det.</span><span class="sxs-lookup"><span data-stu-id="21462-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="21462-140">Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.</span><span class="sxs-lookup"><span data-stu-id="21462-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="21462-141">Läs mer om MDM och konfigurera med Intune om du inte redan&#39;har en klar.</span><span class="sxs-lookup"><span data-stu-id="21462-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="21462-142">Lär dig mer om nätverkskraven för Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="21462-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="21462-143">Valfritt: VPN för att ansluta till organisationsresurser</span><span class="sxs-lookup"><span data-stu-id="21462-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="21462-144">Konfigurera:</span><span class="sxs-lookup"><span data-stu-id="21462-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21462-145">Så här skapar du användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="21462-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="21462-146">Konfigurera automatisk registrering i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21462-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="21462-147">Så här tilldelar du dina programlicenser.</span><span class="sxs-lookup"><span data-stu-id="21462-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="21462-148">Distribuera:</span><span class="sxs-lookup"><span data-stu-id="21462-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21462-149">Konfigurera din HoloLens 2 och verifiera registreringen.</span><span class="sxs-lookup"><span data-stu-id="21462-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="21462-150">Kontrollera att du kan göra ett Remote Assist-anrop.</span><span class="sxs-lookup"><span data-stu-id="21462-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="21462-151">Underhåll:</span><span class="sxs-lookup"><span data-stu-id="21462-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21462-152">Uppdatera Remote Assist med hjälp av Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="21462-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="21462-153">Skapa en supportplan.</span><span class="sxs-lookup"><span data-stu-id="21462-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="21462-154">Utvecklingsplan.</span><span class="sxs-lookup"><span data-stu-id="21462-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="21462-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="21462-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="21462-156">Molnansluten distribution – Förbereda</span><span class="sxs-lookup"><span data-stu-id="21462-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

