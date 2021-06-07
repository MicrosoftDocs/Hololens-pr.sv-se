---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – översikt
description: Lär dig hur du registrerar HoloLens 2-enheter med Dynamics 365-guider över ett företagsanslutet nätverk.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Enhetshantering
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ee6c24f65e5990f1e84a71d86b24dd782cf9f4cc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378877"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="c4472-104">Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – översikt</span><span class="sxs-lookup"><span data-stu-id="c4472-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="c4472-105">Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Dynamics 365-guider (guider) till organisationen.</span><span class="sxs-lookup"><span data-stu-id="c4472-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="c4472-106">Den här guiden är utmärkt för både piloter och produktionsdistributioner och liknar [scenario B: Distribuera i](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) din organisations nätverksguide.</span><span class="sxs-lookup"><span data-stu-id="c4472-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="c4472-107">När du har testat konceptbeviset kan du använda den här guiden för att gå vidare med integreringen av HoloLens i din organisation.</span><span class="sxs-lookup"><span data-stu-id="c4472-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="c4472-108">I den här guiden går vi in på hur du registrerar dina enheter i din befintliga enhetshantering, tillämpar licenser efter behov och kontrollerar att slutanvändarna kan använda en Dynamics 365-guide, samt hur du använder anpassade branschappar när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="c4472-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c4472-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c4472-109">Prerequisites</span></span>

<span data-ttu-id="c4472-110">Följande infrastruktur bör redan finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="c4472-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="c4472-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c4472-111">Wi-Fi</span></span>
    - <span data-ttu-id="c4472-112">Internt företagsnätverk med åtkomst till interna resurser och begränsad åtkomst till Internet- eller molntjänster</span><span class="sxs-lookup"><span data-stu-id="c4472-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="c4472-113">Enhetsbaserad certifikatautentisering.</span><span class="sxs-lookup"><span data-stu-id="c4472-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="c4472-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment[(Azure AD P1 subscription needed) (Azure AD P1-prenumeration krävs)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="c4472-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="c4472-115">MDM (Intune) Hanterad</span><span class="sxs-lookup"><span data-stu-id="c4472-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="c4472-116">Ett eller flera program distribueras via MDM.</span><span class="sxs-lookup"><span data-stu-id="c4472-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="c4472-117">Nätverk</span><span class="sxs-lookup"><span data-stu-id="c4472-117">Network</span></span> 
    - <span data-ttu-id="c4472-118">Certifikat (SCEP eller PKCS)</span><span class="sxs-lookup"><span data-stu-id="c4472-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="c4472-119">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="c4472-119">Proxy configuration</span></span>
- <span data-ttu-id="c4472-120">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c4472-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="c4472-121">En eller flera användare per enhet stöds.</span><span class="sxs-lookup"><span data-stu-id="c4472-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="c4472-122">Olika nivåer av enhetslåsningskonfigurationer som tillämpas baserat på specifika användningsfall, från Fullständigt öppen till Helskärmsläge för enskild app.</span><span class="sxs-lookup"><span data-stu-id="c4472-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="c4472-123">Guider licensiering och krav</span><span class="sxs-lookup"><span data-stu-id="c4472-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="c4472-124">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="c4472-124">Azure AD account</span></span>
- <span data-ttu-id="c4472-125">Dynamics 365-guideprogram PC och HoloLens</span><span class="sxs-lookup"><span data-stu-id="c4472-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="c4472-126">Prenumeration på Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="c4472-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="c4472-127">Microsoft Dataverse (ingår)</span><span class="sxs-lookup"><span data-stu-id="c4472-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="c4472-128">Power Apps (ingår)</span><span class="sxs-lookup"><span data-stu-id="c4472-128">Power Apps (included)</span></span>
- <span data-ttu-id="c4472-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="c4472-129">Power BI Desktop</span></span>
- <span data-ttu-id="c4472-130">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="c4472-130">Network Connectivity</span></span>

<span data-ttu-id="c4472-131">[![Diagram över företagsanslutna nätverk, steg 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4472-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="c4472-132">[![Diagram över företagsanslutna nätverk, steg 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4472-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="c4472-133">I den här guiden kommer du att:</span><span class="sxs-lookup"><span data-stu-id="c4472-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="c4472-134">Förbereda</span><span class="sxs-lookup"><span data-stu-id="c4472-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c4472-135">Lär dig mer om information om infrastrukturen för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="c4472-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="c4472-136">Läs mer om Azure AD och konfigurera ett om du inte har det.</span><span class="sxs-lookup"><span data-stu-id="c4472-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="c4472-137">Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.</span><span class="sxs-lookup"><span data-stu-id="c4472-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="c4472-138">Läs mer om MDM och konfigurera med Intune om du inte redan har en klar.</span><span class="sxs-lookup"><span data-stu-id="c4472-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="c4472-139">Bekanta dig med certifikatbaserad Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c4472-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="c4472-140">Bekanta dig med Proxy.</span><span class="sxs-lookup"><span data-stu-id="c4472-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="c4472-141">Förstå hur du kan använda branschappar.</span><span class="sxs-lookup"><span data-stu-id="c4472-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="c4472-142">Läs mer om hur du kan använda guider för din organisation.</span><span class="sxs-lookup"><span data-stu-id="c4472-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="c4472-143">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="c4472-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c4472-144">Så här skapar du användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="c4472-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="c4472-145">Konfigurera automatisk registrering.</span><span class="sxs-lookup"><span data-stu-id="c4472-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="c4472-146">Så här ställer du Wi-Fi certifikat och profiler för Wi-Fi anslutning.</span><span class="sxs-lookup"><span data-stu-id="c4472-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="c4472-147">Ladda upp och tilldela LOB-appaket (Line of Business).</span><span class="sxs-lookup"><span data-stu-id="c4472-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="c4472-148">Konfigurera Dynamics 365-guider.</span><span class="sxs-lookup"><span data-stu-id="c4472-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="c4472-149">Så här konfigurerar du helskärmsläge (valfritt).</span><span class="sxs-lookup"><span data-stu-id="c4472-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="c4472-150">Så här konfigurerar du WDAC (valfritt).</span><span class="sxs-lookup"><span data-stu-id="c4472-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="c4472-151">Distribuera</span><span class="sxs-lookup"><span data-stu-id="c4472-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="c4472-152">Verifiera registrering via enhet och MDM.</span><span class="sxs-lookup"><span data-stu-id="c4472-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="c4472-153">Verifiera Wi-Fi certifikat.</span><span class="sxs-lookup"><span data-stu-id="c4472-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="c4472-154">Verifiera installationen av LOB-appen.</span><span class="sxs-lookup"><span data-stu-id="c4472-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="c4472-155">Verifiera guider via redigering och drift.</span><span class="sxs-lookup"><span data-stu-id="c4472-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="c4472-156">Underhåll</span><span class="sxs-lookup"><span data-stu-id="c4472-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c4472-157">Uppdatera HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c4472-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="c4472-158">Så här uppdaterar du guider (Store-appar).</span><span class="sxs-lookup"><span data-stu-id="c4472-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="c4472-159">Så här uppdaterar du LOB-appar.</span><span class="sxs-lookup"><span data-stu-id="c4472-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="c4472-160">Utvecklingsplan.</span><span class="sxs-lookup"><span data-stu-id="c4472-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="c4472-161">Skapa en supportplan.</span><span class="sxs-lookup"><span data-stu-id="c4472-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="c4472-162">Alternativ för enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="c4472-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="c4472-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c4472-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="c4472-164">Företagsansluten distribution – Förbereda</span><span class="sxs-lookup"><span data-stu-id="c4472-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
