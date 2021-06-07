---
title: Översikt över molnanslutna HoloLens 2 med Remote Assist
description: Lär dig hur du registrerar HoloLens 2-enheter i ett molnanslutet nätverk med Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378721"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="37b0a-104">Distributionsguide – Molnansluten HoloLens 2 med Remote Assist – översikt</span><span class="sxs-lookup"><span data-stu-id="37b0a-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="37b0a-105">Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter till organisationen med det övergripande målet att ansluta dessa enheters moln till din organisation med Dynamics 365 Remote Assist redo att användas.</span><span class="sxs-lookup"><span data-stu-id="37b0a-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="37b0a-106">Tänk på att detta fungerar som en modell för proof-of-concept-distributioner till din organisation i olika HoloLens 2-användningsfall.</span><span class="sxs-lookup"><span data-stu-id="37b0a-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="37b0a-107">I guiden går vi in på hur du registrerar dina enheter i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Fjärrhjälp när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="37b0a-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="37b0a-108">För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="37b0a-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="37b0a-109">[![Molnanslutet scenario ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="37b0a-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="37b0a-110">I den här guiden</span><span class="sxs-lookup"><span data-stu-id="37b0a-110">In this Guide</span></span>

<span data-ttu-id="37b0a-111">Den här guiden har det specifika målet att konfigurera Remote Assist i din organisation på dina HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="37b0a-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="37b0a-112">Vi kommer att gå in på de behov som krävs för att uppnå det målet.</span><span class="sxs-lookup"><span data-stu-id="37b0a-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="37b0a-113">För att bibehålla fokus på det här målet är vissa förberedelser och konfigurationer förvalda för att optimera för den här distributionen eller för att minska de objekt som behövs för att konfigurera.</span><span class="sxs-lookup"><span data-stu-id="37b0a-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="37b0a-114">Du informeras om de här alternativen och kan anpassa distributionen utifrån dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="37b0a-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="37b0a-115">Det här är en uppsättning som liknar [scenario A: Distribuera](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)till moln anslut-enheter , vilket är ett bra alternativ för många Proof of Concept-distributioner, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="37b0a-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="37b0a-116">Wi-Fi nätverk är vanligtvis helt öppna för Internet- och molntjänsterna</span><span class="sxs-lookup"><span data-stu-id="37b0a-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="37b0a-117">Azure AD Join med automatisk MDM-registrering – MDM (Intune) hanterad</span><span class="sxs-lookup"><span data-stu-id="37b0a-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="37b0a-118">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="37b0a-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="37b0a-119">En eller flera användare per enhet stöds</span><span class="sxs-lookup"><span data-stu-id="37b0a-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="37b0a-120">Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Helt öppen till Helskärmsläge för enskilda appar</span><span class="sxs-lookup"><span data-stu-id="37b0a-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="37b0a-121">Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.</span><span class="sxs-lookup"><span data-stu-id="37b0a-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="37b0a-122">Läs mer om Remote Assist</span><span class="sxs-lookup"><span data-stu-id="37b0a-122">Learn about Remote Assist</span></span>

<span data-ttu-id="37b0a-123">Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning.</span><span class="sxs-lookup"><span data-stu-id="37b0a-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="37b0a-124">Genom att koppla samman personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37b0a-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="37b0a-125">De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte&#39;på samma plats.</span><span class="sxs-lookup"><span data-stu-id="37b0a-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="37b0a-126">Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikern&#39;:s fysiska utrymme så att de kan referera till schemat när de arbetar med huvudena och handsfree på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="37b0a-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="37b0a-127">I den här guiden kommer du att:</span><span class="sxs-lookup"><span data-stu-id="37b0a-127">In this guide you will:</span></span>

<span data-ttu-id="37b0a-128">Förbereda:</span><span class="sxs-lookup"><span data-stu-id="37b0a-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="37b0a-129">Lär dig mer om information om infrastrukturen för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="37b0a-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="37b0a-130">Läs mer om Azure AD och konfigurera ett om du inte&#39;inte har det.</span><span class="sxs-lookup"><span data-stu-id="37b0a-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="37b0a-131">Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.</span><span class="sxs-lookup"><span data-stu-id="37b0a-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="37b0a-132">Läs mer om MDM och konfigurera med Intune om du inte redan&#39;har en klar.</span><span class="sxs-lookup"><span data-stu-id="37b0a-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="37b0a-133">Lär dig mer om nätverkskraven för Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="37b0a-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="37b0a-134">Valfritt: VPN för att ansluta till organisationsresurser</span><span class="sxs-lookup"><span data-stu-id="37b0a-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="37b0a-135">Konfigurera:</span><span class="sxs-lookup"><span data-stu-id="37b0a-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="37b0a-136">Skapa användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="37b0a-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="37b0a-137">Konfigurera automatisk registrering i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="37b0a-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="37b0a-138">Så här tilldelar du dina programlicenser.</span><span class="sxs-lookup"><span data-stu-id="37b0a-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="37b0a-139">Distribuera:</span><span class="sxs-lookup"><span data-stu-id="37b0a-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="37b0a-140">Konfigurera din HoloLens 2 och verifiera registreringen.</span><span class="sxs-lookup"><span data-stu-id="37b0a-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="37b0a-141">Kontrollera att du kan göra ett Remote Assist-anrop.</span><span class="sxs-lookup"><span data-stu-id="37b0a-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="37b0a-142">Underhåll:</span><span class="sxs-lookup"><span data-stu-id="37b0a-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="37b0a-143">Uppdatera Remote Assist med hjälp av Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="37b0a-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="37b0a-144">Skapa en supportplan.</span><span class="sxs-lookup"><span data-stu-id="37b0a-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="37b0a-145">Utvecklingsplan.</span><span class="sxs-lookup"><span data-stu-id="37b0a-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="37b0a-146">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="37b0a-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="37b0a-147">Molnansluten distribution – Förbereda</span><span class="sxs-lookup"><span data-stu-id="37b0a-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

