---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – översikt
description: Lär dig hur du registrerar HoloLens 2 enheter med Dynamics 365-guider över ett företagsanslutet nätverk.
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637021"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="98da9-104">Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – översikt</span><span class="sxs-lookup"><span data-stu-id="98da9-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="98da9-105">Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Dynamics 365-guider (guider) till organisationen.</span><span class="sxs-lookup"><span data-stu-id="98da9-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="98da9-106">Den här guiden är utmärkt för både piloter och produktionsdistributioner och liknar [scenario B: Distribuera i](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) din organisations nätverksguide.</span><span class="sxs-lookup"><span data-stu-id="98da9-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="98da9-107">När du har testat konceptbeviset kan du använda den här guiden för att gå vidare med att integrera HoloLens i din organisation.</span><span class="sxs-lookup"><span data-stu-id="98da9-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="98da9-108">I den här guiden går vi in på hur du registrerar dina enheter i din befintliga enhetshantering, tillämpar licenser efter behov och kontrollerar att slutanvändarna kan använda en Dynamics 365-guide, samt hur du använder anpassade branschappar när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="98da9-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="98da9-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="98da9-109">Prerequisites</span></span>

<span data-ttu-id="98da9-110">Följande infrastruktur bör redan finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="98da9-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="98da9-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="98da9-111">Wi-Fi</span></span>
    - <span data-ttu-id="98da9-112">Internt företagsnätverk med åtkomst till interna resurser och begränsad åtkomst till Internet- eller molntjänster</span><span class="sxs-lookup"><span data-stu-id="98da9-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="98da9-113">Enhetsbaserad certifikatautentisering.</span><span class="sxs-lookup"><span data-stu-id="98da9-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="98da9-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment (Azure AD P1 subscription needed) (Azure AD P1-anslutning med mdm-automatisk registrering ([Azure AD P1-prenumeration krävs)](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="98da9-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="98da9-115">MDM (Intune) Hanterad</span><span class="sxs-lookup"><span data-stu-id="98da9-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="98da9-116">Ett eller flera program distribueras via MDM.</span><span class="sxs-lookup"><span data-stu-id="98da9-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="98da9-117">Nätverk</span><span class="sxs-lookup"><span data-stu-id="98da9-117">Network</span></span> 
    - <span data-ttu-id="98da9-118">Certifikat (SCEP eller PKCS)</span><span class="sxs-lookup"><span data-stu-id="98da9-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="98da9-119">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="98da9-119">Proxy configuration</span></span>
- <span data-ttu-id="98da9-120">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="98da9-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="98da9-121">En eller flera användare per enhet stöds.</span><span class="sxs-lookup"><span data-stu-id="98da9-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="98da9-122">Olika nivåer av enhetslåsningskonfigurationer som tillämpas baserat på specifika användningsfall, från Fullständigt öppen till Helskärmsläge för enskild app.</span><span class="sxs-lookup"><span data-stu-id="98da9-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="98da9-123">Guider licensiering och krav</span><span class="sxs-lookup"><span data-stu-id="98da9-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="98da9-124">Azure AD-konto</span><span class="sxs-lookup"><span data-stu-id="98da9-124">Azure AD account</span></span>
- <span data-ttu-id="98da9-125">Dynamics 365-guider för program PC och HoloLens</span><span class="sxs-lookup"><span data-stu-id="98da9-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="98da9-126">Prenumeration på Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="98da9-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="98da9-127">Microsoft Dataverse (ingår)</span><span class="sxs-lookup"><span data-stu-id="98da9-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="98da9-128">Power Apps (ingår)</span><span class="sxs-lookup"><span data-stu-id="98da9-128">Power Apps (included)</span></span>
- <span data-ttu-id="98da9-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="98da9-129">Power BI Desktop</span></span>
- <span data-ttu-id="98da9-130">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="98da9-130">Network Connectivity</span></span>

<span data-ttu-id="98da9-131">[![Diagram över företagsanslutna nätverk, steg 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="98da9-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="98da9-132">[![Diagram över företagsanslutna nätverk, steg 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="98da9-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="98da9-133">I den här guiden kommer du att:</span><span class="sxs-lookup"><span data-stu-id="98da9-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="98da9-134">Förbereda</span><span class="sxs-lookup"><span data-stu-id="98da9-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="98da9-135">Lär dig mer om grundläggande infrastruktur för HoloLens 2 enheter.</span><span class="sxs-lookup"><span data-stu-id="98da9-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="98da9-136">Läs mer om Azure AD och konfigurera ett om du inte har det.</span><span class="sxs-lookup"><span data-stu-id="98da9-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="98da9-137">Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.</span><span class="sxs-lookup"><span data-stu-id="98da9-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="98da9-138">Läs mer om MDM och konfigurera med Intune om du inte redan har en klar.</span><span class="sxs-lookup"><span data-stu-id="98da9-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="98da9-139">Bekanta dig med certifikatbaserad Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="98da9-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="98da9-140">Bekanta dig med Proxy.</span><span class="sxs-lookup"><span data-stu-id="98da9-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="98da9-141">Förstå hur du kan använda branschappar.</span><span class="sxs-lookup"><span data-stu-id="98da9-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="98da9-142">Läs mer om hur du kan använda guider för din organisation.</span><span class="sxs-lookup"><span data-stu-id="98da9-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="98da9-143">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="98da9-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="98da9-144">Så här skapar du användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="98da9-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="98da9-145">Konfigurera automatisk registrering.</span><span class="sxs-lookup"><span data-stu-id="98da9-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="98da9-146">Så här ställer du Wi-Fi certifikat och profiler för Wi-Fi anslutning.</span><span class="sxs-lookup"><span data-stu-id="98da9-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="98da9-147">Upload och tilldela affärs appaket (LOB).</span><span class="sxs-lookup"><span data-stu-id="98da9-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="98da9-148">Konfigurera Dynamics 365-guider.</span><span class="sxs-lookup"><span data-stu-id="98da9-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="98da9-149">Så här konfigurerar du helskärmsläge (valfritt).</span><span class="sxs-lookup"><span data-stu-id="98da9-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="98da9-150">Så här konfigurerar du WDAC (valfritt).</span><span class="sxs-lookup"><span data-stu-id="98da9-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="98da9-151">Distribuera</span><span class="sxs-lookup"><span data-stu-id="98da9-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="98da9-152">Verifiera registrering via enhet och MDM.</span><span class="sxs-lookup"><span data-stu-id="98da9-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="98da9-153">Verifiera Wi-Fi certifikat.</span><span class="sxs-lookup"><span data-stu-id="98da9-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="98da9-154">Verifiera installationen av LOB-appen.</span><span class="sxs-lookup"><span data-stu-id="98da9-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="98da9-155">Verifiera guider via redigering och drift.</span><span class="sxs-lookup"><span data-stu-id="98da9-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="98da9-156">Underhåll</span><span class="sxs-lookup"><span data-stu-id="98da9-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="98da9-157">Uppdatera HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="98da9-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="98da9-158">Så här uppdaterar du guider (Store-appar).</span><span class="sxs-lookup"><span data-stu-id="98da9-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="98da9-159">Så här uppdaterar du LOB-appar.</span><span class="sxs-lookup"><span data-stu-id="98da9-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="98da9-160">Utvecklingsplan.</span><span class="sxs-lookup"><span data-stu-id="98da9-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="98da9-161">Skapa en supportplan.</span><span class="sxs-lookup"><span data-stu-id="98da9-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="98da9-162">Alternativ för enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="98da9-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="98da9-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="98da9-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="98da9-164">Företagsansluten distribution – Förbereda</span><span class="sxs-lookup"><span data-stu-id="98da9-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
