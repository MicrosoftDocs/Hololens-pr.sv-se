---
title: Översikt över molnanslutna HoloLens 2 med Fjärrhjälp
description: Lär dig hur du registrerar HoloLens 2 enheter i ett molnanslutet nätverk med Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635134"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="4fb6a-104">Distributionsguide – Molnansluten HoloLens 2 med Fjärrhjälp – översikt</span><span class="sxs-lookup"><span data-stu-id="4fb6a-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="4fb6a-105">Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Fjärrhjälp till organisationen.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="4fb6a-106">Detta kommer att fungera som en modell för konceptbevisdistributioner till din organisation i en mängd olika HoloLens 2 användningsfall.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="4fb6a-107">Konfigurationen liknar scenario [A: Distribuera till enheter som ansluter till molnet.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="4fb6a-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="4fb6a-108">I guiden går vi in på hur du registrerar dina enheter i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Fjärrhjälp när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="4fb6a-109">För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="4fb6a-110">Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4fb6a-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4fb6a-111">Prerequisites</span></span>

<span data-ttu-id="4fb6a-112">Följande infrastruktur måste vara på plats för att distribuera HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="4fb6a-113">Om inte ingår att konfigurera Azure och Intune i den här guiden:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="4fb6a-114">Det här är en uppsättning som liknar [scenario A: Distribuera](/hololens/common-scenarios#scenario-a)till moln anslut-enheter , vilket är ett bra alternativ för många Proof of Concept-distributioner, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="4fb6a-115">Wi-Fi nätverk är vanligtvis helt öppna för Internet- och molntjänsterna</span><span class="sxs-lookup"><span data-stu-id="4fb6a-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="4fb6a-116">Azure AD Join med automatisk MDM-registrering – MDM (Intune) hanterad</span><span class="sxs-lookup"><span data-stu-id="4fb6a-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="4fb6a-117">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="4fb6a-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="4fb6a-118">En eller flera användare per enhet stöds.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Molnanslutet scenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="4fb6a-120">Läs mer om Remote Assist</span><span class="sxs-lookup"><span data-stu-id="4fb6a-120">Learn about Remote Assist</span></span>

<span data-ttu-id="4fb6a-121">Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="4fb6a-122">Genom att koppla samman personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare på Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="4fb6a-123">De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte&#39;på samma plats.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="4fb6a-124">Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikern&#39;:s fysiska utrymme så att de kan referera till schemat när de arbetar med huvudena och handsfree på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="4fb6a-125">Remote Assist– licensiering och krav</span><span class="sxs-lookup"><span data-stu-id="4fb6a-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="4fb6a-126">Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)</span><span class="sxs-lookup"><span data-stu-id="4fb6a-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="4fb6a-127">[Remote Assist-prenumeration](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="4fb6a-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="4fb6a-128">Dynamics 365 Remote Assist-användare</span><span class="sxs-lookup"><span data-stu-id="4fb6a-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="4fb6a-129">Remote Assist-licens</span><span class="sxs-lookup"><span data-stu-id="4fb6a-129">Remote Assist license</span></span>
- <span data-ttu-id="4fb6a-130">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="4fb6a-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="4fb6a-131">Microsoft Teams användare</span><span class="sxs-lookup"><span data-stu-id="4fb6a-131">Microsoft Teams user</span></span>

- <span data-ttu-id="4fb6a-132">Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="4fb6a-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="4fb6a-133">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="4fb6a-133">Network connectivity</span></span>

<span data-ttu-id="4fb6a-134">Om du planerar att implementera det [här scenariot mellan klientorganisationen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en licens för informationsbarriärer.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="4fb6a-135">Se [den här artikeln](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) för att avgöra om en Information Barrier-licens krävs.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="4fb6a-136">I den här guiden kommer du att:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-136">In this guide you will:</span></span>

<span data-ttu-id="4fb6a-137">Förbereda:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4fb6a-138">Lär dig mer om grundläggande infrastruktur för HoloLens 2 enheter.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="4fb6a-139">Läs mer om Azure AD och konfigurera ett om du inte&#39;inte har det.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="4fb6a-140">Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="4fb6a-141">Läs mer om MDM och konfigurera med Intune om du inte redan&#39;har en klar.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="4fb6a-142">Lär dig mer om nätverkskraven för Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="4fb6a-143">Valfritt: VPN för att ansluta till organisationsresurser</span><span class="sxs-lookup"><span data-stu-id="4fb6a-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="4fb6a-144">Konfigurera:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4fb6a-145">Skapa användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="4fb6a-146">Konfigurera automatisk registrering i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="4fb6a-147">Så här tilldelar du dina programlicenser.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="4fb6a-148">Distribuera:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4fb6a-149">Konfigurera din HoloLens 2 och verifiera registreringen.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="4fb6a-150">Kontrollera att du kan göra ett Remote Assist-anrop.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="4fb6a-151">Underhåll:</span><span class="sxs-lookup"><span data-stu-id="4fb6a-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4fb6a-152">Uppdatera Remote Assist med hjälp av Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="4fb6a-153">Skapa en supportplan.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="4fb6a-154">Utvecklingsplan.</span><span class="sxs-lookup"><span data-stu-id="4fb6a-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="4fb6a-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4fb6a-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4fb6a-156">Molnansluten distribution – Förbereda</span><span class="sxs-lookup"><span data-stu-id="4fb6a-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

