---
title: Planera HoloLens 2-distribution i en kommersiell miljö
description: Lär dig mer om kärnbehoven för att distribuera och hantera HoloLens i företagsmiljöer, inklusive infrastruktur, Azure Active Directory och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961478"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="ff319-103">Planera HoloLens 2-distribution i en kommersiell miljö</span><span class="sxs-lookup"><span data-stu-id="ff319-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="ff319-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="ff319-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="ff319-105">Den här översikten är avsedd att hjälpa IT-proffs att förstå överväganden för att distribuera och Microsoft HoloLens 2 enheter inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="ff319-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="ff319-106">För slutanvändare av enheter kan du [gå till Grundläggande information för](hololens2-setup.md) att komma igång.</span><span class="sxs-lookup"><span data-stu-id="ff319-106">For device end users, see [The Basics](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="ff319-107">HoloLens 2 körs på Windows 10 Holographic som ger organisationer robusta, flexibla, inbyggda tekniker för hantering av mobila enheter och appar.</span><span class="sxs-lookup"><span data-stu-id="ff319-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="ff319-108">Windows 10 Holographic har stöd för livscykelhantering från hela enheten så att företag kan kontrollera sina enheter, data och appar.</span><span class="sxs-lookup"><span data-stu-id="ff319-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="ff319-109">HoloLens 2 kan enkelt införlivas i standardlivscykeln, från enhetsregistrering, konfiguration och programhantering till underhåll och tillbakatagning med hjälp av en omfattande lösning för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="ff319-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="ff319-110">Följande steg kan hjälpa dig genom processen för HoloLens 2-implementering i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ff319-110">The following steps can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Steg 1](images/1green.png)| <br/> <span data-ttu-id="ff319-112">**[Vanliga distributionsscenarier:](hololens-requirements.md)** Förstå distributionsscenarier och utforska de kärnkomponenter som behövs för att distribuera HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="ff319-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Steg 2](images/2green.png)| <br/> <span data-ttu-id="ff319-114">**[Förbered:](#prepare)** Bekanta dig med de grundläggande infrastrukturerna som behövs för HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ff319-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Steg 3](images/3green.png) | <br/> <span data-ttu-id="ff319-116">**[Konfigurera](#configure)**: Lär dig hur du konfigurerar viktiga komponenter för en molnbaserad distribution.</span><span class="sxs-lookup"><span data-stu-id="ff319-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Steg 4](images/4green.png) | <br/> <span data-ttu-id="ff319-118">**[Distribuera:](#deploy)** Upptäck hur du distribuerar dina enheter och distribuerar dina program på ett säkert och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="ff319-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Steg 5](images/5green.png) | <br/> <span data-ttu-id="ff319-120">**[Underhåll:](#maintain)** Ta reda på vad som behövs för att korrekt upprätthålla statusen för dina HoloLens 2-enheter och säkerställa efterlevnad med företagets policy.</span><span class="sxs-lookup"><span data-stu-id="ff319-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

## <a name="prepare"></a><span data-ttu-id="ff319-121">Förbereda</span><span class="sxs-lookup"><span data-stu-id="ff319-121">Prepare</span></span>

<span data-ttu-id="ff319-122">Lär dig mer om viktiga infrastrukturtjänster som krävs för att stödja en fullständig uppsättning HoloLens 2-funktioner.</span><span class="sxs-lookup"><span data-stu-id="ff319-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="ff319-123">Komponent</span><span class="sxs-lookup"><span data-stu-id="ff319-123">Component</span></span> | <span data-ttu-id="ff319-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff319-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ff319-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff319-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="ff319-126">Tillhandahåller identitets- och åtkomsthantering för HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ff319-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="ff319-127">Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="ff319-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="ff319-128">Hanterar HoloLens 2-enheter som är anslutna till din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="ff319-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="ff319-129">Wi-Fi-nätverk</span><span class="sxs-lookup"><span data-stu-id="ff319-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="ff319-130">Wi-Fi är tillgänglig och enheter kan anslutas till Internet</span><span class="sxs-lookup"><span data-stu-id="ff319-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="ff319-131">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="ff319-131">Configure</span></span>

<span data-ttu-id="ff319-132">Använd Intune och Autopilot som low-touch-lösningar för att registrera och konfigurera HoloLens 2 till din organisations Azure AD-klientorganisation och MDM.</span><span class="sxs-lookup"><span data-stu-id="ff319-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="ff319-133">Komponent</span><span class="sxs-lookup"><span data-stu-id="ff319-133">Component</span></span> | <span data-ttu-id="ff319-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff319-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ff319-135">Automatisk registrering</span><span class="sxs-lookup"><span data-stu-id="ff319-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="ff319-136">Efter den första inloggningen registreras enheter automatiskt med Azure AD och registreras i MDM</span><span class="sxs-lookup"><span data-stu-id="ff319-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="ff319-137">Programlicenser</span><span class="sxs-lookup"><span data-stu-id="ff319-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="ff319-138">Kan tillämpas på antingen användare, användargrupper eller enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="ff319-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="ff319-139">Azure-användare och -grupper</span><span class="sxs-lookup"><span data-stu-id="ff319-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="ff319-140">Hjälper till att tilldela konfigurationer och licenser för HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ff319-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="ff319-141">Distribuera</span><span class="sxs-lookup"><span data-stu-id="ff319-141">Deploy</span></span>

<span data-ttu-id="ff319-142">Distribuera dina HoloLens 2-enheter och verifiera deras konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ff319-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="ff319-143">Komponent</span><span class="sxs-lookup"><span data-stu-id="ff319-143">Component</span></span> | <span data-ttu-id="ff319-144">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff319-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ff319-145">Registreringsverifiering</span><span class="sxs-lookup"><span data-stu-id="ff319-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="ff319-146">Kontrollera att enheten har anslutits till Azure AD från Inställningar eller Azure Portal</span><span class="sxs-lookup"><span data-stu-id="ff319-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="ff319-147">Certifikatverifiering</span><span class="sxs-lookup"><span data-stu-id="ff319-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="ff319-148">Kontrollera inställningarna och kontrollera att de har distribuerats korrekt</span><span class="sxs-lookup"><span data-stu-id="ff319-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="ff319-149">Verifiera appinstallationer</span><span class="sxs-lookup"><span data-stu-id="ff319-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="ff319-150">Bekräfta att appen finns och arbetar med hololens 2</span><span class="sxs-lookup"><span data-stu-id="ff319-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="ff319-151">Underhåll</span><span class="sxs-lookup"><span data-stu-id="ff319-151">Maintain</span></span>

<span data-ttu-id="ff319-152">Använd Windows Update för företag tillsammans med DITT MDM-system eller Microsoft Store för att hålla din flotta av HoloLens 2 och appar uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="ff319-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="ff319-153">Komponent</span><span class="sxs-lookup"><span data-stu-id="ff319-153">Component</span></span> | <span data-ttu-id="ff319-154">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff319-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ff319-155">Uppdatera HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ff319-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="ff319-156">Konfigurera uppdateringar efter behov via Windows Updates for Business</span><span class="sxs-lookup"><span data-stu-id="ff319-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="ff319-157">Uppdatera appar</span><span class="sxs-lookup"><span data-stu-id="ff319-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="ff319-158">Konfigurera via DITT MDM-system eller Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ff319-158">Configure through your MDM system or the Microsoft Store</span></span>
