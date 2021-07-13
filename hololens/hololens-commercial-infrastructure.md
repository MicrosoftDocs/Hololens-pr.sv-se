---
title: Riktlinjer för infrastruktur för HoloLens
description: Lär dig mer om riktlinjerna för infrastruktur HoloLens enheter, inklusive stöd för trådlösa nätverk, fjärrhjälp och hantering av mobila enheter.
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639292"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="f3135-103">Konfigurera ditt nätverk för HoloLens</span><span class="sxs-lookup"><span data-stu-id="f3135-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="f3135-104">Den här delen av dokumentet kräver följande personer:</span><span class="sxs-lookup"><span data-stu-id="f3135-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="f3135-105">Nätverksadministratör med behörighet att göra ändringar i proxyn/brandväggen</span><span class="sxs-lookup"><span data-stu-id="f3135-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="f3135-106">Azure Active Directory Admin</span><span class="sxs-lookup"><span data-stu-id="f3135-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="f3135-107">Mobile Enhetshanteraren Admin</span><span class="sxs-lookup"><span data-stu-id="f3135-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="f3135-108">Infrastrukturkrav</span><span class="sxs-lookup"><span data-stu-id="f3135-108">Infrastructure Requirements</span></span>

<span data-ttu-id="f3135-109">HoloLens är i grunden en mobil Windows som är integrerad med Azure.</span><span class="sxs-lookup"><span data-stu-id="f3135-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="f3135-110">Det fungerar bäst i kommersiella miljöer med trådlös nätverkstillgänglighet (Wi-Fi) och åtkomst till Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="f3135-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="f3135-111">Viktiga molntjänster är:</span><span class="sxs-lookup"><span data-stu-id="f3135-111">Critical cloud services include:</span></span>

- <span data-ttu-id="f3135-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="f3135-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="f3135-113">Windows Uppdatera (WU)</span><span class="sxs-lookup"><span data-stu-id="f3135-113">Windows Update (WU)</span></span>

<span data-ttu-id="f3135-114">Kommersiella kunder behöver enterprise mobility management (EMM) eller mdm-infrastruktur för hantering av mobila enheter för att hantera HoloLens enheter i stor skala.</span><span class="sxs-lookup"><span data-stu-id="f3135-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="f3135-115">Den här guiden [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) som exempel, även om alla leverantörer med fullständigt stöd för Microsoft Policy kan stödja HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f3135-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="f3135-116">Fråga din leverantör av hantering av mobila enheter om de stöder HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f3135-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="f3135-117">HoloLens stöder en begränsad uppsättning frånkopplade molnupplevelser.</span><span class="sxs-lookup"><span data-stu-id="f3135-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="f3135-118">EAP-stöd för trådlöst nätverk</span><span class="sxs-lookup"><span data-stu-id="f3135-118">Wireless network EAP support</span></span>

- <span data-ttu-id="f3135-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="f3135-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="f3135-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="f3135-120">PEAP-TLS</span></span>
- <span data-ttu-id="f3135-121">TLS</span><span class="sxs-lookup"><span data-stu-id="f3135-121">TLS</span></span>
- <span data-ttu-id="f3135-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="f3135-122">TTLS-CHAP</span></span>
- <span data-ttu-id="f3135-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="f3135-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="f3135-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="f3135-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="f3135-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="f3135-125">TTLS-PAP</span></span>
- <span data-ttu-id="f3135-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="f3135-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="f3135-127">HoloLens Specifika nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="f3135-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="f3135-128">Kontrollera att den [här listan](hololens-offline.md) över slutpunkter tillåts i nätverksbrandväggen.</span><span class="sxs-lookup"><span data-stu-id="f3135-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="f3135-129">Detta gör att HoloLens fungerar korrekt.</span><span class="sxs-lookup"><span data-stu-id="f3135-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="f3135-130">Specifika nätverkskrav för Fjärrhjälp</span><span class="sxs-lookup"><span data-stu-id="f3135-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="f3135-131">Den rekommenderade bandbredden för optimala prestanda för Remote Assist är 1,5 Mbit/s.</span><span class="sxs-lookup"><span data-stu-id="f3135-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="f3135-132">Mer information [finns i de detaljerade](/MicrosoftTeams/prepare-network) nätverkskraven.</span><span class="sxs-lookup"><span data-stu-id="f3135-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="f3135-133">**(Observera att om du inte har nätverkshastigheter på minst 1,5 Mbit/s kommer Remote Assist fortfarande att fungera. Kvaliteten kan dock bli dålig).**</span><span class="sxs-lookup"><span data-stu-id="f3135-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="f3135-134">Kontrollera att dessa portar och URL:er är tillåtna i nätverksbrandväggen för att Microsoft Teams ska fungera.</span><span class="sxs-lookup"><span data-stu-id="f3135-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="f3135-135">Håll dig uppdaterad med den [senaste listan med portar.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="f3135-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="f3135-136">Läs mer om de specifika [nätverkskraven för Fjärrhjälp](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="f3135-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="f3135-137">Läs mer om hur [du förbereder organisationens nätverk för Microsoft Teams](/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="f3135-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="f3135-138">Guidespecifika nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="f3135-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="f3135-139">Guider kräver endast nätverksåtkomst för att ladda ned och använda appen.</span><span class="sxs-lookup"><span data-stu-id="f3135-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="f3135-140">Azure Active Directory Vägledning</span><span class="sxs-lookup"><span data-stu-id="f3135-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="f3135-141">Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f3135-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="f3135-142">Kontrollera att du har en Azure AD-licens.</span><span class="sxs-lookup"><span data-stu-id="f3135-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="f3135-143">Läs [HoloLens licenskrav för](hololens-licenses-requirements.md) ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="f3135-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="f3135-144">Om du planerar att använda automatisk registrering måste du konfigurera [Azure AD-registrering.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="f3135-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="f3135-145">Se till att företagets användare finns i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f3135-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="f3135-146">Se följande anvisningar [för att](/azure/active-directory/fundamentals/add-users-azure-active-directory) lägga till användare.</span><span class="sxs-lookup"><span data-stu-id="f3135-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="f3135-147">Vi föreslår att användare som behöver liknande licenser läggs till i samma grupp.</span><span class="sxs-lookup"><span data-stu-id="f3135-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="f3135-148">Skapa en grupp</span><span class="sxs-lookup"><span data-stu-id="f3135-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="f3135-149">Lägga till användare i grupper</span><span class="sxs-lookup"><span data-stu-id="f3135-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="f3135-150">Se till att företagets användare (eller användargrupp) tilldelas nödvändiga licenser.</span><span class="sxs-lookup"><span data-stu-id="f3135-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="f3135-151">Om du behöver tilldela licenser följer du dessa [anvisningar.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="f3135-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="f3135-152">Gör bara det här steget om användarna förväntas registrera sina HoloLens/Mobila enheter på dig (Det finns tre alternativ) Dessa steg säkerställer att företagets användare (eller en grupp användare) kan lägga till enheter.</span><span class="sxs-lookup"><span data-stu-id="f3135-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="f3135-153">**Alternativ 1:** Ge alla användare behörighet att ansluta enheter till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f3135-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="f3135-154">**Logga in på Azure Portal som administratör**  >  **Azure Active Directory**  >  **Enheter**  >  **Enhets-Inställningar**  >
 **Ange Användare kan ansluta enheter till Azure AD till *Alla***</span><span class="sxs-lookup"><span data-stu-id="f3135-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="f3135-155">**Alternativ 2:** Ge valda användare/grupper behörighet att ansluta enheter till Azure AD Logga **in** på Azure Portal som administratör Azure Active Directory Enheter Enhet Inställningar Ange användare kan ansluta enheter till Azure AD till vald avbildning som visar konfiguration av  >    >    >    >
 \*\*\*\* 
 ![ Azure AD-anslutna enheter](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="f3135-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="f3135-156">**Alternativ 3:** Du kan blockera alla användare från att ansluta sina enheter till domänen.</span><span class="sxs-lookup"><span data-stu-id="f3135-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="f3135-157">Det innebär att alla enheter måste registreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="f3135-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="f3135-158">Vägledning för Enhetshanteraren mobildata</span><span class="sxs-lookup"><span data-stu-id="f3135-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="f3135-159">Pågående enhetshantering</span><span class="sxs-lookup"><span data-stu-id="f3135-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="f3135-160">Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f3135-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="f3135-161">Pågående enhetshantering beror på din infrastruktur för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="f3135-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="f3135-162">De flesta har samma allmänna funktioner, men användargränssnittet kan variera mycket.</span><span class="sxs-lookup"><span data-stu-id="f3135-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="f3135-163">[Med CSP:er (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) kan du skapa och distribuera hanteringsinställningar för enheterna i nätverket.</span><span class="sxs-lookup"><span data-stu-id="f3135-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="f3135-164">Se listan [över HoloLens för](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) referens.</span><span class="sxs-lookup"><span data-stu-id="f3135-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="f3135-165">[Efterlevnadsprinciper](/intune/device-compliance-get-started) är regler och inställningar som enheter måste uppfylla för att vara kompatibla i företagets infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="f3135-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="f3135-166">Använd dessa principer med villkorlig åtkomst för att blockera åtkomst till företagsresurser för enheter som inte är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="f3135-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="f3135-167">Du kan till exempel skapa en princip som kräver att BitLocker är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="f3135-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="f3135-168">[Skapa en efterlevnadsprincip.](/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="f3135-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="f3135-169">Villkorlig åtkomst tillåter/nekar mobila enheter och mobila program från att komma åt företagsresurser.</span><span class="sxs-lookup"><span data-stu-id="f3135-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="f3135-170">Två dokument som kan vara användbara är Plan your CA Deployment (Planera [distributionen av certifikatutfärdaren)](/azure/active-directory/conditional-access/plan-conditional-access) [och Best Practices (Metodtips).](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="f3135-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="f3135-171">[Den här](/intune/fundamentals/windows-holographic-for-business) artikeln beskriver Intunes hanteringsverktyg för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f3135-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="f3135-172">Skapa en enhetsprofil</span><span class="sxs-lookup"><span data-stu-id="f3135-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="f3135-173">Hantera uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f3135-173">Manage updates</span></span>

<span data-ttu-id="f3135-174">Intune innehåller en funktion som kallas uppdateringsringar för Windows 10 enheter, inklusive HoloLens 2 och HoloLens v1 (med Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="f3135-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="f3135-175">Uppdateringsringar innehåller en grupp inställningar som avgör hur och när uppdateringar installeras.</span><span class="sxs-lookup"><span data-stu-id="f3135-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="f3135-176">Du kan till exempel skapa en underhållsperiod för installation av uppdateringar, eller välja att datorn startas om när uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="f3135-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="f3135-177">Du kan också välja att pausa uppdateringar på obestämd tid tills du är redo att uppdatera.</span><span class="sxs-lookup"><span data-stu-id="f3135-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="f3135-178">Läs mer om [att konfigurera uppdateringsringar med Intune](/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="f3135-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="f3135-179">Programhantering</span><span class="sxs-lookup"><span data-stu-id="f3135-179">Application management</span></span>

<span data-ttu-id="f3135-180">Hantera HoloLens program via:</span><span class="sxs-lookup"><span data-stu-id="f3135-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="f3135-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f3135-181">Microsoft Store</span></span>  
  <span data-ttu-id="f3135-182">Den Microsoft Store är det bästa sättet att distribuera och använda program på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f3135-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="f3135-183">Det finns en bra uppsättning grundläggande HoloLens program som redan finns i butiken eller så kan [du publicera dina egna](/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="f3135-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="f3135-184">Alla program i butiken är tillgängliga offentligt för alla, men om det inte är acceptabelt kan du kolla Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="f3135-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="f3135-185">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="f3135-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="f3135-186">Microsoft Store för företag and Education är en anpassad butik för din företagsmiljö.</span><span class="sxs-lookup"><span data-stu-id="f3135-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="f3135-187">Du kan använda de Microsoft Store inbyggda Windows 10 och HoloLens för att hitta, hämta, distribuera och hantera appar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f3135-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="f3135-188">Du kan också distribuera appar som är specifika för din kommersiella miljö men inte för världen.</span><span class="sxs-lookup"><span data-stu-id="f3135-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="f3135-189">Programdistribution och -hantering via Intune eller någon annan lösning för hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="f3135-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="f3135-190">De flesta lösningar för hantering av mobila enheter, inklusive Intune, är ett sätt att distribuera affärsprogram direkt till en uppsättning registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="f3135-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="f3135-191">Se den här artikeln för [installation av Intune-appen.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="f3135-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="f3135-192">_rekommenderas inte_ Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="f3135-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="f3135-193">Program kan också installeras på HoloLens direkt med hjälp av Windows Enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="f3135-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="f3135-194">Detta rekommenderas inte eftersom utvecklarläget måste vara aktiverat för att använda enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="f3135-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="f3135-195">Läs mer om [att installera appar på HoloLens](hololens-install-apps.md).</span><span class="sxs-lookup"><span data-stu-id="f3135-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="f3135-196">Certifikat</span><span class="sxs-lookup"><span data-stu-id="f3135-196">Certificates</span></span>

<span data-ttu-id="f3135-197">Du kan distribuera certifikat via MDM-providern.</span><span class="sxs-lookup"><span data-stu-id="f3135-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="f3135-198">Om ditt företag kräver certifikat stöder Intune PKCS, PFX och SCEP.</span><span class="sxs-lookup"><span data-stu-id="f3135-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="f3135-199">Det är viktigt att förstå vilket certifikat som är rätt för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="f3135-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="f3135-200">Gå till dokumentationen [om certifikatkonfigurationer](/intune/protect/certificates-configure) för att avgöra vilket certifikat som är bäst för dig.</span><span class="sxs-lookup"><span data-stu-id="f3135-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="f3135-201">Om du planerar att använda certifikat för HoloLens autentisering kan PFX eller SCEP vara rätt för dig.</span><span class="sxs-lookup"><span data-stu-id="f3135-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="f3135-202">Se följande steg för att använda [SCEP](/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="f3135-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="f3135-203">Uppgradera till Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="f3135-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="f3135-204">Windows Holographics for Business (commercial suite) är endast avsett för HoloLens första generationens enheter.</span><span class="sxs-lookup"><span data-stu-id="f3135-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="f3135-205">Profilen tillämpas inte på HoloLens 2 enheter.</span><span class="sxs-lookup"><span data-stu-id="f3135-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="f3135-206">Anvisningar för hur du uppgraderar till den kommersiella sviten finns i dokumentationen [om holografiska](/intune/configuration/holographic-upgrade) uppgraderingar.</span><span class="sxs-lookup"><span data-stu-id="f3135-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="f3135-207">Så här konfigurerar du helskärmsläge med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f3135-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="f3135-208">Synkronisera Microsoft Store till Intune (se följande [instruktioner).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="f3135-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="f3135-209">Kontrollera appinställningarna</span><span class="sxs-lookup"><span data-stu-id="f3135-209">Check your app settings</span></span>
    1. <span data-ttu-id="f3135-210">Logga in på Microsoft Store företagskonto</span><span class="sxs-lookup"><span data-stu-id="f3135-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="f3135-211">**Hantera > Produkter och tjänster > Appar och programvara > Välj den app som du vill synkronisera > Private Store-tillgänglighet > Välj "Alla" eller "Specifika grupper"**</span><span class="sxs-lookup"><span data-stu-id="f3135-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="f3135-212">Om du inte ser den app som du vill använda måste du "hämta" appen genom att söka i Butiken efter din app.</span><span class="sxs-lookup"><span data-stu-id="f3135-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="f3135-213">Klicka på sökfältet i det övre högra hörnet > skriver in namnet på appen > klickar på **appen och > väljer "Hämta".**</span><span class="sxs-lookup"><span data-stu-id="f3135-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="f3135-214">Om du inte ser dina appar **i Intune > Client Apps > Apps** kan du behöva synkronisera dina [appar](/intune/apps/windows-store-for-business#synchronize-apps) igen.</span><span class="sxs-lookup"><span data-stu-id="f3135-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="f3135-215">Skapa en enhetsprofil för helskärmsläge</span><span class="sxs-lookup"><span data-stu-id="f3135-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="f3135-216">Du kan konfigurera olika användare så att de har olika funktioner för helskärmsläge genom att använda "Azure AD" som "Användarinloggningstyp".</span><span class="sxs-lookup"><span data-stu-id="f3135-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="f3135-217">Det här alternativet är dock endast tillgängligt i helskärmsläge för flera appar.</span><span class="sxs-lookup"><span data-stu-id="f3135-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="f3135-218">Helskärmsläge för flera appar fungerar bara med en app och flera appar.</span><span class="sxs-lookup"><span data-stu-id="f3135-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Bild som visar konfiguration av helskärmsläge i Intune](images/aad-kioskmode.png)

<span data-ttu-id="f3135-220">Information om andra MDM-tjänster finns i leverantörens dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f3135-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="f3135-221">Läs anvisningarna [HoloLens helskärmsläge](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) om du behöver använda en anpassad inställning och fullständig XML-konfiguration för att konfigurera en helskärm i MDM-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f3135-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="f3135-222">Certifikat och autentisering</span><span class="sxs-lookup"><span data-stu-id="f3135-222">Certificates and Authentication</span></span>

<span data-ttu-id="f3135-223">Certifikat kan distribueras via din MDM (se "certifikat" i [MDM-avsnittet](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="f3135-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="f3135-224">Certifikat kan också distribueras till HoloLens via paketetablering.</span><span class="sxs-lookup"><span data-stu-id="f3135-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="f3135-225">Mer [information HoloLens finns](hololens-provisioning.md) i HoloLens etablering.</span><span class="sxs-lookup"><span data-stu-id="f3135-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="f3135-226">Ytterligare intune-snabblänkar</span><span class="sxs-lookup"><span data-stu-id="f3135-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="f3135-227">[Skapa profiler:](/intune/configuration/device-profile-create) Med profiler kan du lägga till och konfigurera inställningar som ska skickas till enheterna i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f3135-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

