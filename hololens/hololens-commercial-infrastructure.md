---
title: Riktlinjer för infrastruktur för HoloLens
description: Lär dig mer om riktlinjerna för infrastruktur för HoloLens-enheter, inklusive stöd för trådlösa nätverk, fjärrhjälp och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379997"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="d86d3-103">Konfigurera ditt nätverk för HoloLens</span><span class="sxs-lookup"><span data-stu-id="d86d3-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="d86d3-104">Den här delen av dokumentet kräver följande personer:</span><span class="sxs-lookup"><span data-stu-id="d86d3-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="d86d3-105">Nätverksadministratör med behörighet att göra ändringar i proxyn/brandväggen</span><span class="sxs-lookup"><span data-stu-id="d86d3-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="d86d3-106">Azure Active Directory administratör</span><span class="sxs-lookup"><span data-stu-id="d86d3-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="d86d3-107">Mobile Enhetshanteraren Admin</span><span class="sxs-lookup"><span data-stu-id="d86d3-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="d86d3-108">Infrastrukturkrav</span><span class="sxs-lookup"><span data-stu-id="d86d3-108">Infrastructure Requirements</span></span>

<span data-ttu-id="d86d3-109">HoloLens är i grunden en mobil Windows-enhet som är integrerad med Azure.</span><span class="sxs-lookup"><span data-stu-id="d86d3-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="d86d3-110">Det fungerar bäst i kommersiella miljöer med trådlös nätverkstillgänglighet (Wi-Fi) och åtkomst till Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="d86d3-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="d86d3-111">Viktiga molntjänster är:</span><span class="sxs-lookup"><span data-stu-id="d86d3-111">Critical cloud services include:</span></span>

- <span data-ttu-id="d86d3-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d86d3-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="d86d3-113">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="d86d3-113">Windows Update (WU)</span></span>

<span data-ttu-id="d86d3-114">Kommersiella kunder behöver enterprise mobility management (EMM) eller mdm-infrastruktur för hantering av mobila enheter för att hantera HoloLens-enheter i stor skala.</span><span class="sxs-lookup"><span data-stu-id="d86d3-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="d86d3-115">Den här guiden [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) som exempel, även om alla leverantörer med fullständigt stöd för Microsoft Policy kan stödja HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="d86d3-116">Fråga din leverantör av hantering av mobila enheter om de stöder HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d86d3-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="d86d3-117">HoloLens stöder en begränsad uppsättning frånkopplade molnupplevelser.</span><span class="sxs-lookup"><span data-stu-id="d86d3-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="d86d3-118">EAP-stöd för trådlösa nätverk</span><span class="sxs-lookup"><span data-stu-id="d86d3-118">Wireless network EAP support</span></span>

- <span data-ttu-id="d86d3-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="d86d3-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="d86d3-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="d86d3-120">PEAP-TLS</span></span>
- <span data-ttu-id="d86d3-121">TLS</span><span class="sxs-lookup"><span data-stu-id="d86d3-121">TLS</span></span>
- <span data-ttu-id="d86d3-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="d86d3-122">TTLS-CHAP</span></span>
- <span data-ttu-id="d86d3-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="d86d3-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="d86d3-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="d86d3-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="d86d3-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="d86d3-125">TTLS-PAP</span></span>
- <span data-ttu-id="d86d3-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="d86d3-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="d86d3-127">HoloLens-specifika nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="d86d3-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="d86d3-128">Kontrollera att den [här listan](hololens-offline.md) över slutpunkter tillåts i nätverksbrandväggen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="d86d3-129">Detta gör att HoloLens kan fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="d86d3-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="d86d3-130">Specifika nätverkskrav för fjärrhjälp</span><span class="sxs-lookup"><span data-stu-id="d86d3-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="d86d3-131">Den rekommenderade bandbredden för optimala prestanda för Remote Assist är 1,5 Mbit/s.</span><span class="sxs-lookup"><span data-stu-id="d86d3-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="d86d3-132">Mer information [finns i de detaljerade](https://docs.microsoft.com/MicrosoftTeams/prepare-network) nätverkskraven.</span><span class="sxs-lookup"><span data-stu-id="d86d3-132">See the [detailed network requirements](https://docs.microsoft.com/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="d86d3-133">**(Observera att om du inte har nätverkshastigheter på minst 1,5 Mbit/s fungerar Remote Assist fortfarande. Kvaliteten kan dock bli dålig).**</span><span class="sxs-lookup"><span data-stu-id="d86d3-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="d86d3-134">Kontrollera att dessa portar och URL:er tillåts i nätverksbrandväggen så att Microsoft Teams kan fungera.</span><span class="sxs-lookup"><span data-stu-id="d86d3-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="d86d3-135">Håll dig uppdaterad med den [senaste listan över portar.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="d86d3-135">Stay up to date with the [latest list of ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="d86d3-136">Läs mer om de specifika [nätverkskraven för Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="d86d3-136">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="d86d3-137">Läs mer om hur [du förbereder organisationens nätverk för Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="d86d3-137">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="d86d3-138">Särskilda nätverkskrav för guider</span><span class="sxs-lookup"><span data-stu-id="d86d3-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="d86d3-139">Guider kräver endast nätverksåtkomst för att ladda ned och använda appen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="d86d3-140">Azure Active Directory vägledning</span><span class="sxs-lookup"><span data-stu-id="d86d3-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="d86d3-141">Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="d86d3-142">Kontrollera att du har en Azure AD-licens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="d86d3-143">Mer information [finns i Licenskrav för HoloLens.](hololens-licenses-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="d86d3-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="d86d3-144">Om du planerar att använda automatisk registrering måste du konfigurera [Azure AD-registrering.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="d86d3-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="d86d3-145">Se till att företagets användare finns i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d86d3-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="d86d3-146">Se följande anvisningar [för att](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) lägga till användare.</span><span class="sxs-lookup"><span data-stu-id="d86d3-146">See the following [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="d86d3-147">Vi föreslår att användare som behöver liknande licenser läggs till i samma grupp.</span><span class="sxs-lookup"><span data-stu-id="d86d3-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="d86d3-148">Skapa en grupp</span><span class="sxs-lookup"><span data-stu-id="d86d3-148">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="d86d3-149">Lägga till användare i grupper</span><span class="sxs-lookup"><span data-stu-id="d86d3-149">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="d86d3-150">Kontrollera att företagets användare (eller användargrupp) har tilldelats nödvändiga licenser.</span><span class="sxs-lookup"><span data-stu-id="d86d3-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="d86d3-151">Om du behöver tilldela licenser följer du dessa [anvisningar.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="d86d3-151">If you need to assign licenses, follow these [directions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="d86d3-152">Gör bara det här steget om användarna förväntas registrera sina HoloLens/Mobile-enheter på dig (Det finns tre alternativ) De här stegen säkerställer att företagets användare (eller en grupp av användare) kan lägga till enheter.</span><span class="sxs-lookup"><span data-stu-id="d86d3-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="d86d3-153">**Alternativ 1:** Ge alla användare behörighet att ansluta enheter till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d86d3-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="d86d3-154">**Logga in på Azure Portal som administratör**  >  **Azure Active Directory**  >  **Enheter**  >  **Enhetsinställningar**  >
 **Ange Användare kan ansluta enheter till Azure AD till *Alla***</span><span class="sxs-lookup"><span data-stu-id="d86d3-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="d86d3-155">**Alternativ 2:** Ge valda användare/grupper behörighet att ansluta enheter till Azure AD Logga in på **Azure Portal** som administratör  >  **Azure Active Directory Enhetsinställningar** Ange Användare kan ansluta enheter till Azure  >    >    >
 **AD** 
 ![ till vald bild som visar konfiguration av Azure AD-anslutna enheter](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="d86d3-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="d86d3-156">**Alternativ 3:** Du kan blockera alla användare från att ansluta sina enheter till domänen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="d86d3-157">Det innebär att alla enheter måste registreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="d86d3-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="d86d3-158">Vägledning för Enhetshanteraren mobila enheter</span><span class="sxs-lookup"><span data-stu-id="d86d3-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="d86d3-159">Pågående enhetshantering</span><span class="sxs-lookup"><span data-stu-id="d86d3-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="d86d3-160">Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="d86d3-161">Pågående enhetshantering beror på din infrastruktur för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="d86d3-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="d86d3-162">De flesta har samma allmänna funktioner, men användargränssnittet kan variera mycket.</span><span class="sxs-lookup"><span data-stu-id="d86d3-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="d86d3-163">[Med CPS (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) kan du skapa och distribuera hanteringsinställningar för enheterna i nätverket.</span><span class="sxs-lookup"><span data-stu-id="d86d3-163">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="d86d3-164">Se listan [över HoloLens CPS](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) som referens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-164">See the [list of HoloLens CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="d86d3-165">[Efterlevnadsprinciper](https://docs.microsoft.com/intune/device-compliance-get-started) är regler och inställningar som enheter måste uppfylla för att vara kompatibla i företagets infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="d86d3-165">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="d86d3-166">Använd dessa principer med villkorlig åtkomst för att blockera åtkomst till företagsresurser för enheter som inte är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="d86d3-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="d86d3-167">Du kan till exempel skapa en princip som kräver att BitLocker är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="d86d3-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="d86d3-168">[Skapa en efterlevnadsprincip.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="d86d3-168">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="d86d3-169">Villkorlig åtkomst tillåter/nekar mobila enheter och mobilappar från att komma åt företagsresurser.</span><span class="sxs-lookup"><span data-stu-id="d86d3-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="d86d3-170">Två dokument som kan vara användbara är Plan your CA Deployment (Planera [din CA-distribution)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) [och Best Practices (Metodtips).](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="d86d3-170">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="d86d3-171">[Den här](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) artikeln handlar om Intunes hanteringsverktyg för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-171">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="d86d3-172">Skapa en enhetsprofil</span><span class="sxs-lookup"><span data-stu-id="d86d3-172">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="d86d3-173">Hantera uppdateringar</span><span class="sxs-lookup"><span data-stu-id="d86d3-173">Manage updates</span></span>

<span data-ttu-id="d86d3-174">Intune innehåller en funktion som kallas uppdateringsringar för Windows 10 enheter, inklusive HoloLens 2 och HoloLens v1 (med Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="d86d3-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="d86d3-175">Uppdateringsringar innehåller en grupp med inställningar som avgör hur och när uppdateringar installeras.</span><span class="sxs-lookup"><span data-stu-id="d86d3-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="d86d3-176">Du kan till exempel skapa en underhållsperiod för installation av uppdateringar, eller välja att datorn startas om när uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="d86d3-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="d86d3-177">Du kan också välja att pausa uppdateringar på obestämd tid tills du är redo att uppdatera.</span><span class="sxs-lookup"><span data-stu-id="d86d3-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="d86d3-178">Läs mer om [att konfigurera uppdateringsringar med Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="d86d3-178">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="d86d3-179">Programhantering</span><span class="sxs-lookup"><span data-stu-id="d86d3-179">Application management</span></span>

<span data-ttu-id="d86d3-180">Hantera HoloLens-program via:</span><span class="sxs-lookup"><span data-stu-id="d86d3-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="d86d3-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="d86d3-181">Microsoft Store</span></span>  
  <span data-ttu-id="d86d3-182">Den Microsoft Store är det bästa sättet att distribuera och använda program på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d86d3-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="d86d3-183">Det finns en bra uppsättning HoloLens-kärnprogram som redan finns i butiken, eller så kan [du publicera dina egna](https://docs.microsoft.com/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="d86d3-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="d86d3-184">Alla program i butiken är tillgängliga offentligt för alla, men om det inte är acceptabelt kan du kolla Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="d86d3-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="d86d3-185">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="d86d3-185">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="d86d3-186">Microsoft Store för företag and Education är en anpassad butik för din företagsmiljö.</span><span class="sxs-lookup"><span data-stu-id="d86d3-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="d86d3-187">Med den kan du använda Microsoft Store inbyggda Windows 10 hololens för att hitta, hämta, distribuera och hantera appar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="d86d3-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="d86d3-188">Du kan också distribuera appar som är specifika för din kommersiella miljö men inte för världen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="d86d3-189">Programdistribution och -hantering via Intune eller någon annan lösning för hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="d86d3-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="d86d3-190">De flesta lösningar för hantering av mobila enheter, inklusive Intune, är ett sätt att distribuera affärsprogram direkt till en uppsättning registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="d86d3-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="d86d3-191">Läs den här artikeln om [att installera Intune-appen.](https://docs.microsoft.com/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="d86d3-191">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="d86d3-192">_rekommenderas inte_ Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="d86d3-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="d86d3-193">Program kan också installeras på HoloLens direkt med hjälp av Windows Enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="d86d3-194">Detta rekommenderas inte eftersom utvecklarläget måste vara aktiverat för att använda enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="d86d3-195">Läs mer om [att installera appar på HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span><span class="sxs-lookup"><span data-stu-id="d86d3-195">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <a name="certificates"></a><span data-ttu-id="d86d3-196">Certifikat</span><span class="sxs-lookup"><span data-stu-id="d86d3-196">Certificates</span></span>

<span data-ttu-id="d86d3-197">Du kan distribuera certifikat via MDM-providern.</span><span class="sxs-lookup"><span data-stu-id="d86d3-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="d86d3-198">Om ditt företag kräver certifikat stöder Intune PKCS, PFX och SCEP.</span><span class="sxs-lookup"><span data-stu-id="d86d3-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="d86d3-199">Det är viktigt att förstå vilket certifikat som är rätt för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="d86d3-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="d86d3-200">Gå till dokumentationen [om certifikatkonfigurationer](https://docs.microsoft.com/intune/protect/certificates-configure) för att avgöra vilket certifikat som är bäst för dig.</span><span class="sxs-lookup"><span data-stu-id="d86d3-200">Please visit the [certificate configurations](https://docs.microsoft.com/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="d86d3-201">Om du planerar att använda certifikat för HoloLens-autentisering kan PFX eller SCEP vara rätt för dig.</span><span class="sxs-lookup"><span data-stu-id="d86d3-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="d86d3-202">Se följande steg för att använda [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="d86d3-202">See the following steps for using [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="d86d3-203">Uppgradera till Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="d86d3-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="d86d3-204">Windows Holographics for Business (commercial suite) är endast avsett för HoloLens 1:a gen-enheter.</span><span class="sxs-lookup"><span data-stu-id="d86d3-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="d86d3-205">Profilen tillämpas inte på HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="d86d3-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="d86d3-206">Anvisningar för hur du uppgraderar till den kommersiella sviten finns i dokumentationen [om holografiska](https://docs.microsoft.com/intune/configuration/holographic-upgrade) uppgraderingar.</span><span class="sxs-lookup"><span data-stu-id="d86d3-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="d86d3-207">Så här konfigurerar du helskärmsläge med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d86d3-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="d86d3-208">Synkronisera Microsoft Store till Intune (se följande [anvisningar).](https://docs.microsoft.com/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="d86d3-208">Sync Microsoft Store to Intune (See the following [instructions](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="d86d3-209">Kontrollera appinställningarna</span><span class="sxs-lookup"><span data-stu-id="d86d3-209">Check your app settings</span></span>
    1. <span data-ttu-id="d86d3-210">Logga in på ditt Microsoft Store Business-konto</span><span class="sxs-lookup"><span data-stu-id="d86d3-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="d86d3-211">**Hantera > Produkter och tjänster > Appar och programvara > Välj den app som du vill synkronisera > Private Store-tillgänglighet > Välj "Alla" eller "Specifika grupper"**</span><span class="sxs-lookup"><span data-stu-id="d86d3-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="d86d3-212">Om du inte ser den app som du vill använda måste du "hämta" appen genom att söka i Butiken efter din app.</span><span class="sxs-lookup"><span data-stu-id="d86d3-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="d86d3-213">Klicka på sökfältet i det övre högra hörnet > skriver in namnet på appen > klickar på **appen och > väljer "Hämta".**</span><span class="sxs-lookup"><span data-stu-id="d86d3-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="d86d3-214">Om du inte ser dina appar **i Intune > Client Apps > Apps** kan du behöva synkronisera dina [appar](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) igen.</span><span class="sxs-lookup"><span data-stu-id="d86d3-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="d86d3-215">Skapa en enhetsprofil för helskärmsläge</span><span class="sxs-lookup"><span data-stu-id="d86d3-215">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="d86d3-216">Du kan konfigurera olika användare så att de har olika funktioner för helskärmsläge genom att använda "Azure AD" som "Användarinloggningstyp".</span><span class="sxs-lookup"><span data-stu-id="d86d3-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="d86d3-217">Det här alternativet är dock endast tillgängligt i helskärmsläge för flera appar.</span><span class="sxs-lookup"><span data-stu-id="d86d3-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="d86d3-218">Helskärmsläge för flera appar fungerar bara med en app och flera appar.</span><span class="sxs-lookup"><span data-stu-id="d86d3-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Bild som visar konfiguration av helskärmsläge i Intune](images/aad-kioskmode.png)

<span data-ttu-id="d86d3-220">Information om andra MDM-tjänster finns i leverantörens dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d86d3-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="d86d3-221">Läs [HoloLens kioskinstruktioner](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) om du behöver använda en anpassad inställning och fullständig XML-konfiguration för att konfigurera en helskärm i MDM-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d86d3-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="d86d3-222">Certifikat och autentisering</span><span class="sxs-lookup"><span data-stu-id="d86d3-222">Certificates and Authentication</span></span>

<span data-ttu-id="d86d3-223">Certifikat kan distribueras via din MDM (se "certifikat" i [MDM-avsnittet](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="d86d3-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="d86d3-224">Certifikat kan också distribueras till HoloLens via paketetablering.</span><span class="sxs-lookup"><span data-stu-id="d86d3-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="d86d3-225">Mer information [finns i HoloLens-etablering.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="d86d3-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="d86d3-226">Ytterligare intune-snabblänkar</span><span class="sxs-lookup"><span data-stu-id="d86d3-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="d86d3-227">[Skapa profiler:](https://docs.microsoft.com/intune/configuration/device-profile-create) Med profiler kan du lägga till och konfigurera inställningar som ska skickas till enheterna i din organisation.</span><span class="sxs-lookup"><span data-stu-id="d86d3-227">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

