---
title: Översikt över molnanslutna HoloLens 2 med Remote Assist
description: Lär dig hur du registrerar HoloLens 2-enheter via ett molnanslutet nätverk med hjälp av Dynamics 365 Remote Assist.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923541"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="53ed4-104">Distributionsguide – Molnansluten HoloLens 2 med Remote Assist – översikt</span><span class="sxs-lookup"><span data-stu-id="53ed4-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="53ed4-105">Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Fjärrhjälp till organisationen.</span><span class="sxs-lookup"><span data-stu-id="53ed4-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="53ed4-106">Detta fungerar som en modell för proof-of-concept-distributioner till din organisation i en mängd olika HoloLens 2-användningsfall.</span><span class="sxs-lookup"><span data-stu-id="53ed4-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="53ed4-107">Konfigurationen liknar scenario [A: Distribuera till enheter som ansluter till molnet.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="53ed4-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="53ed4-108">I guiden går vi in på hur du registrerar dina enheter i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Fjärrhjälp när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="53ed4-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="53ed4-109">För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53ed4-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="53ed4-110">Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.</span><span class="sxs-lookup"><span data-stu-id="53ed4-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="53ed4-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="53ed4-111">Prerequisites</span></span>

<span data-ttu-id="53ed4-112">Följande infrastruktur bör finnas på plats för att distribuera HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53ed4-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="53ed4-113">Om inte ingår det att konfigurera Azure och Intune i den här guiden:</span><span class="sxs-lookup"><span data-stu-id="53ed4-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="53ed4-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="53ed4-114">Wi-Fi</span></span>
    - <span data-ttu-id="53ed4-115">Nätverk är vanligtvis öppna för Internet- och molntjänster</span><span class="sxs-lookup"><span data-stu-id="53ed4-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="53ed4-116">Azure Active Directory (Azure AD)-anslutning med automatisk MDM-registrering[(Azure AD P1-prenumeration krävs)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="53ed4-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="53ed4-117">MDM (Intune) Hanterad</span><span class="sxs-lookup"><span data-stu-id="53ed4-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="53ed4-118">Ett eller flera program distribueras via MDM.</span><span class="sxs-lookup"><span data-stu-id="53ed4-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="53ed4-119">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="53ed4-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="53ed4-120">En eller flera användare per enhet stöds.</span><span class="sxs-lookup"><span data-stu-id="53ed4-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Molnanslutet scenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="53ed4-122">Läs mer om Remote Assist</span><span class="sxs-lookup"><span data-stu-id="53ed4-122">Learn about Remote Assist</span></span>

<span data-ttu-id="53ed4-123">Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning.</span><span class="sxs-lookup"><span data-stu-id="53ed4-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="53ed4-124">Genom att koppla samman personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="53ed4-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="53ed4-125">De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte&#39;på samma plats.</span><span class="sxs-lookup"><span data-stu-id="53ed4-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="53ed4-126">Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikern&#39;:s fysiska utrymme så att de kan referera till schemat när de arbetar med heads-up och handsfree på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="53ed4-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="53ed4-127">Licensiering och krav för Remote Assist</span><span class="sxs-lookup"><span data-stu-id="53ed4-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="53ed4-128">Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)</span><span class="sxs-lookup"><span data-stu-id="53ed4-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="53ed4-129">[Remote Assist-prenumeration](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="53ed4-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="53ed4-130">Dynamics 365 Remote Assist-användare</span><span class="sxs-lookup"><span data-stu-id="53ed4-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="53ed4-131">Remote Assist-licens</span><span class="sxs-lookup"><span data-stu-id="53ed4-131">Remote Assist license</span></span>
- <span data-ttu-id="53ed4-132">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="53ed4-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="53ed4-133">Microsoft Teams-användare</span><span class="sxs-lookup"><span data-stu-id="53ed4-133">Microsoft Teams user</span></span>

- <span data-ttu-id="53ed4-134">Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="53ed4-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="53ed4-135">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="53ed4-135">Network connectivity</span></span>

<span data-ttu-id="53ed4-136">Om du planerar att implementera det här [scenariot för flera klienter](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en informationsbarriärlicens.</span><span class="sxs-lookup"><span data-stu-id="53ed4-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="53ed4-137">Se [den här artikeln](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) för att avgöra om en Information Barrier-licens krävs.</span><span class="sxs-lookup"><span data-stu-id="53ed4-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="53ed4-138">I den här guiden kommer du att:</span><span class="sxs-lookup"><span data-stu-id="53ed4-138">In this guide you will:</span></span>

<span data-ttu-id="53ed4-139">Förbereda:</span><span class="sxs-lookup"><span data-stu-id="53ed4-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="53ed4-140">Lär dig mer om grundläggande infrastruktur för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="53ed4-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="53ed4-141">Läs mer om Azure AD och konfigurera ett om du inte&#39;inte har det.</span><span class="sxs-lookup"><span data-stu-id="53ed4-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="53ed4-142">Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.</span><span class="sxs-lookup"><span data-stu-id="53ed4-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="53ed4-143">Läs mer om MDM och konfigurera med Intune om du inte redan&#39;har en klar.</span><span class="sxs-lookup"><span data-stu-id="53ed4-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="53ed4-144">Lär dig mer om nätverkskraven för Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="53ed4-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="53ed4-145">Valfritt: VPN för att ansluta till organisationsresurser</span><span class="sxs-lookup"><span data-stu-id="53ed4-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="53ed4-146">Konfigurera:</span><span class="sxs-lookup"><span data-stu-id="53ed4-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="53ed4-147">Så här skapar du användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="53ed4-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="53ed4-148">Konfigurera automatisk registrering i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="53ed4-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="53ed4-149">Så här tilldelar du dina programlicenser.</span><span class="sxs-lookup"><span data-stu-id="53ed4-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="53ed4-150">Distribuera:</span><span class="sxs-lookup"><span data-stu-id="53ed4-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="53ed4-151">Konfigurera HoloLens 2 och verifiera registreringen.</span><span class="sxs-lookup"><span data-stu-id="53ed4-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="53ed4-152">Kontrollera att du kan göra ett Remote Assist-anrop.</span><span class="sxs-lookup"><span data-stu-id="53ed4-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="53ed4-153">Underhåll:</span><span class="sxs-lookup"><span data-stu-id="53ed4-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="53ed4-154">Uppdatera Remote Assist med hjälp av Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="53ed4-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="53ed4-155">Skapa en supportplan.</span><span class="sxs-lookup"><span data-stu-id="53ed4-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="53ed4-156">Utvecklingsplan.</span><span class="sxs-lookup"><span data-stu-id="53ed4-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="53ed4-157">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="53ed4-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="53ed4-158">Molnansluten distribution – Förbereda</span><span class="sxs-lookup"><span data-stu-id="53ed4-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

