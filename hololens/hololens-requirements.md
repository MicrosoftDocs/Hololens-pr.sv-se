---
title: Vanliga distributionsscenarier
description: Läs mer om att distribuera och hantera HoloLens i företagsmiljöer, inklusive infrastruktur, Azure Active Directory och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639836"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="b782e-103">Vanliga distributionsscenarier</span><span class="sxs-lookup"><span data-stu-id="b782e-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="b782e-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="b782e-104">Overview</span></span>

<span data-ttu-id="b782e-105">Den här sidan innehåller en översikt över övergripande arkitektur för tre vanliga scenarier när du distribuerar och hanterar Microsoft HoloLens 2 enheter i företaget.</span><span class="sxs-lookup"><span data-stu-id="b782e-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="b782e-106">Ofta bestäms hur du hanterar dina enheter och får åtkomst till organisationens resurser huvudsakligen av faktorer som redan finns på plats.</span><span class="sxs-lookup"><span data-stu-id="b782e-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="b782e-107">Baserat på din befintliga infrastruktur uppmanar vi dig att granska det vanliga enhetshanteringsformatet (MDM) i följande scenarier och läser sedan [Planera HoloLens 2-distributioner](hololens-core-components.md) i en kommersiell miljö för att avgöra vilket scenario som passar dina behov.</span><span class="sxs-lookup"><span data-stu-id="b782e-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="b782e-108">Det finns också tre motsvarande guider som kan användas under distributionen.</span><span class="sxs-lookup"><span data-stu-id="b782e-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="b782e-109">Distributionsguide för molnansluten miljö</span><span class="sxs-lookup"><span data-stu-id="b782e-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="b782e-110">Distributionsguide för molnansluten miljö (externa klienter)</span><span class="sxs-lookup"><span data-stu-id="b782e-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="b782e-111">Distributionsguide för företagsnätverk</span><span class="sxs-lookup"><span data-stu-id="b782e-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="b782e-112">Distributionsguide för säker offlinemiljö</span><span class="sxs-lookup"><span data-stu-id="b782e-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="b782e-113">Scenario A: Distribuera till molnanslutna enheter</span><span class="sxs-lookup"><span data-stu-id="b782e-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="b782e-114">Det här scenariot är jämförbart med distribution av hanterade mobila enheter inom ett företag.</span><span class="sxs-lookup"><span data-stu-id="b782e-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="b782e-115">HoloLens 2 distribueras för användning främst i miljöer utanför ett företagsnätverk.</span><span class="sxs-lookup"><span data-stu-id="b782e-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="b782e-116">Företagsresurser används inte och kan begränsas via VPN.</span><span class="sxs-lookup"><span data-stu-id="b782e-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="b782e-117">Grundläggande vanliga konfigurationer</span><span class="sxs-lookup"><span data-stu-id="b782e-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="b782e-118">Wi-Fi nätverk är vanligtvis helt öppna för Internet- och molntjänsterna.</span><span class="sxs-lookup"><span data-stu-id="b782e-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="b782e-119">Azure AD Join med Mdm Enhetshantering (Mobile Enhetshantering) – Automatisk registrering – MDM (Intune) hanterad</span><span class="sxs-lookup"><span data-stu-id="b782e-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="b782e-120">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b782e-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="b782e-121">En eller flera användare per enhet stöds</span><span class="sxs-lookup"><span data-stu-id="b782e-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="b782e-122">Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Helt öppen till Helskärmsläge för enskilda appar.</span><span class="sxs-lookup"><span data-stu-id="b782e-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="b782e-123">Ett eller flera program distribueras via MDM</span><span class="sxs-lookup"><span data-stu-id="b782e-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="b782e-124">Vanliga utmaningar</span><span class="sxs-lookup"><span data-stu-id="b782e-124">Common Challenges</span></span>
   * <span data-ttu-id="b782e-125">Avgöra vilka MDM-konfigurationer som ska gälla för HoloLens 2 baserat på scenariokrav.</span><span class="sxs-lookup"><span data-stu-id="b782e-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="b782e-126">[![Scenario Ett diagram ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b782e-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="b782e-127">Motsvarande molnanslutna guide beskriver hur du registrerar HoloLens 2 i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Remote Assist när enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="b782e-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="b782e-128">Använd guiden för externa klienter för att distribuera enheter till en fjärrplats för kortsiktig eller långsiktig extern användning.</span><span class="sxs-lookup"><span data-stu-id="b782e-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b782e-129">Distributionsguide för molnansluten miljö</span><span class="sxs-lookup"><span data-stu-id="b782e-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="b782e-130">Distributionsguide för molnansluten miljö (externa klienter)</span><span class="sxs-lookup"><span data-stu-id="b782e-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="b782e-131">Scenario B: Distribuera i organisationens nätverk</span><span class="sxs-lookup"><span data-stu-id="b782e-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="b782e-132">Det här scenariot är identiskt med en klassisk distribution för Windows 10 datorer.</span><span class="sxs-lookup"><span data-stu-id="b782e-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="b782e-133">HoloLens 2 distribueras främst för användning i företagsnätverket med åtkomst till interna företagsresurser.</span><span class="sxs-lookup"><span data-stu-id="b782e-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="b782e-134">Internet- och molntjänster kan vara begränsade.</span><span class="sxs-lookup"><span data-stu-id="b782e-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="b782e-135">Grundläggande vanliga konfigurationer</span><span class="sxs-lookup"><span data-stu-id="b782e-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="b782e-136">Wi-Fi är ett internt företagsnätverk med åtkomst till interna resurser och begränsad åtkomst till Internet eller molntjänster.</span><span class="sxs-lookup"><span data-stu-id="b782e-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="b782e-137">Azure AD Join med automatisk MDM-registrering</span><span class="sxs-lookup"><span data-stu-id="b782e-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="b782e-138">MDM (Intune) Hanterad</span><span class="sxs-lookup"><span data-stu-id="b782e-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="b782e-139">Användare loggar in med sitt eget företagskonto (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b782e-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="b782e-140">En eller flera användare per enhet stöds</span><span class="sxs-lookup"><span data-stu-id="b782e-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="b782e-141">Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Helt öppen till Helskärmsläge för enskilda appar.</span><span class="sxs-lookup"><span data-stu-id="b782e-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="b782e-142">Ett eller flera program distribueras via MDM</span><span class="sxs-lookup"><span data-stu-id="b782e-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="b782e-143">Vanliga utmaningar</span><span class="sxs-lookup"><span data-stu-id="b782e-143">Common Challenges</span></span>
   * <span data-ttu-id="b782e-144">HoloLens 2 stöder inte lokal AD-anslutning eller SCCM.</span><span class="sxs-lookup"><span data-stu-id="b782e-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="b782e-145">Endast Azure AD-anslutning med MDM.</span><span class="sxs-lookup"><span data-stu-id="b782e-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="b782e-146">Många företag distribuerar i dag fortfarande Windows 10-datorer i det här scenariot som lokala AD-anslutna enheter som hanteras av System Center Configuration Manager (SCCM) och kanske inte har infrastrukturen distribuerad/konfigurerad för att hantera interna Windows 10-enheter via molnbaserade MDM-lösningar.</span><span class="sxs-lookup"><span data-stu-id="b782e-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="b782e-147">Eftersom HoloLens 2 är en molnbaserad enhet är den starkt beroende av Internet- och molnanslutna tjänster för användarautentisering, OS-uppdateringar, MDM-hantering och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b782e-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="b782e-148">När du ansluter till ett företagsnätverk kommer proxy-/brandväggsregler troligen att behöva justeras för att aktivera åtkomst för HoloLens 2 och de program som körs på det.</span><span class="sxs-lookup"><span data-stu-id="b782e-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="b782e-149">Företagsanslutning Wi-Fi kräver vanligtvis certifikat för att autentisera enheten eller användaren i nätverket.</span><span class="sxs-lookup"><span data-stu-id="b782e-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="b782e-150">Det kan vara svårt att konfigurera den infrastruktur eller de inställningar som krävs för att Windows 10 till enheter via MDM.</span><span class="sxs-lookup"><span data-stu-id="b782e-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="b782e-151">[![Scenario B1-diagram ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b782e-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="b782e-152">[![Scenario B2-diagram ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b782e-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="b782e-153">Motsvarande företagsnätverksguide instruerar dig att registrera HoloLens 2 i din befintliga enhetshantering, tillämpa licenser efter behov och verifiera att slutanvändarna kan använda en Dynamics 365-guide, samt använda anpassade branschappar efter att enheten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="b782e-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b782e-154">Distributionsguide för företagsnätverk</span><span class="sxs-lookup"><span data-stu-id="b782e-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="b782e-155">Scenario C: Distribuera i säker offlinemiljö</span><span class="sxs-lookup"><span data-stu-id="b782e-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="b782e-156">Det här är en typisk distribution för mycket säkra eller konfidentiella platser.</span><span class="sxs-lookup"><span data-stu-id="b782e-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="b782e-157">HoloLens 2 distribueras för användning främst offline utan nätverks- eller Internetåtkomst.</span><span class="sxs-lookup"><span data-stu-id="b782e-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="b782e-158">Grundläggande vanliga konfigurationer</span><span class="sxs-lookup"><span data-stu-id="b782e-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="b782e-159">Wi-Fi är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="b782e-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="b782e-160">Ethernet via USB kan aktiveras för LAN-anslutning om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b782e-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="b782e-161">Inte hanterad.</span><span class="sxs-lookup"><span data-stu-id="b782e-161">Not Managed.</span></span>
   * <span data-ttu-id="b782e-162">Lokalt användarkonto för enhets inloggning.</span><span class="sxs-lookup"><span data-stu-id="b782e-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="b782e-163">HoloLens 2 stöder endast ett lokalt konto.</span><span class="sxs-lookup"><span data-stu-id="b782e-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="b782e-164">Olika nivåer av enhetslåsningskonfigurationer tillämpas via Etableringspaket baserat på specifika användningsfall.</span><span class="sxs-lookup"><span data-stu-id="b782e-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="b782e-165">Dessa konfigurationer är vanligtvis begränsade på grund av säkra miljökrav.</span><span class="sxs-lookup"><span data-stu-id="b782e-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="b782e-166">Ett eller flera program distribueras via etableringspaket</span><span class="sxs-lookup"><span data-stu-id="b782e-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="b782e-167">Vanliga utmaningar</span><span class="sxs-lookup"><span data-stu-id="b782e-167">Common Challenges</span></span>
   * <span data-ttu-id="b782e-168">Det finns en begränsad uppsättning konfigurationer tillgängliga via konfigurationspaket</span><span class="sxs-lookup"><span data-stu-id="b782e-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="b782e-169">Molntjänster kan inte användas, vilket begränsar HoloLens 2 funktioner.</span><span class="sxs-lookup"><span data-stu-id="b782e-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="b782e-170">Högre administrativa kostnader eftersom enheterna måste konfigureras, konfigureras och uppdateras manuellt.</span><span class="sxs-lookup"><span data-stu-id="b782e-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="b782e-171">[![Säkerhetsdiagram 1 ](images/deployment-guides-revised-scenario-c-01.png) för offline](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b782e-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="b782e-172">Motsvarande offline-säkerhetsguide innehåller anvisningar för att tillämpa ett exempel på etableringspaket som låser en HoloLens 2 för användning i säkra miljöer.</span><span class="sxs-lookup"><span data-stu-id="b782e-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b782e-173">Distributionsguide för säker offlinemiljö</span><span class="sxs-lookup"><span data-stu-id="b782e-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


