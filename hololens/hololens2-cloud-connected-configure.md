---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Konfigurera
description: Lär dig att konfigurera konfigurationer för att registrera HoloLens över ett molnanslutet nätverk i stor skala med Remote Assist.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635151"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="85c48-104">Konfigurera – Molnansluten guide</span><span class="sxs-lookup"><span data-stu-id="85c48-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="85c48-105">I det här avsnittet av guiden går&#39;igenom hur du ställer in automatisk registrering för din klientorganisation och hur du tillämpar licenser för både Intune och Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="85c48-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="85c48-106">Azure-användare och -grupper</span><span class="sxs-lookup"><span data-stu-id="85c48-106">Azure Users and Groups</span></span>

<span data-ttu-id="85c48-107">Azure och Intune med det tillägget använder användare och grupper för att tilldela konfigurationer och licenser.</span><span class="sxs-lookup"><span data-stu-id="85c48-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="85c48-108">För att verifiera det här distributionsflödet och kunna göra ett Remote Assist-anrop från en användare till en annan&#39;du två användarkonton.</span><span class="sxs-lookup"><span data-stu-id="85c48-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="85c48-109">Vi kan skapa en enskild användargrupp för att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="85c48-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="85c48-110">Vi kan ansluta båda användarna till samma grupp och tillämpa en licens för Intune och Remote Assist för den gruppen.</span><span class="sxs-lookup"><span data-stu-id="85c48-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="85c48-111">Om du inte&#39;har åtkomst till två Azure AD-konton i en användargrupp kan du använda; här är snabbstartsguiderna för:</span><span class="sxs-lookup"><span data-stu-id="85c48-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="85c48-112">Så här skapar du en användare</span><span class="sxs-lookup"><span data-stu-id="85c48-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="85c48-113">Så här skapar du en grupp</span><span class="sxs-lookup"><span data-stu-id="85c48-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="85c48-114">[Lägg till användare i en grupp](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Lägg till skapade användare för att skapa grupp</span><span class="sxs-lookup"><span data-stu-id="85c48-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="85c48-115">[Konfigurera Azure AD så att en användargrupp kan ansluta till enheter](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Se till att den nya användargruppen har behörighet att registrera enheter i Azure AD</span><span class="sxs-lookup"><span data-stu-id="85c48-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="85c48-116">Automatisk registrering på HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="85c48-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="85c48-117">För att få en smidig och smidig upplevelse är det enkelt att konfigurera Azure Active Directory Join (AADJ) och automatisk registrering i Intune för HoloLens 2 enheter.</span><span class="sxs-lookup"><span data-stu-id="85c48-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="85c48-118">Detta gör att användare kan ange sina autentiseringsuppgifter för organisationens inloggningsuppgifter under OOBE och automatiskt registrera sig med Azure AD och registrera enheten i MDM.</span><span class="sxs-lookup"><span data-stu-id="85c48-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="85c48-119">Med hjälp [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kan vi välja tjänster och navigera på några sidor tills vi kan välja Hämta en Premium utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="85c48-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="85c48-120">Du kanske märker att det Azure Active Directory Premium 1 och 2. För automatisk registrering räcker det med P1.</span><span class="sxs-lookup"><span data-stu-id="85c48-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="85c48-121">Vi kan välja Intune och välja användaromfånget för automatisk registrering och välja den grupp som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="85c48-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="85c48-122">Fullständig information och anvisningar finns i guiden om [hur du aktiverar automatisk registrering för Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="85c48-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="85c48-123">Programlicenser</span><span class="sxs-lookup"><span data-stu-id="85c48-123">Application Licenses</span></span>

<span data-ttu-id="85c48-124">Med en programlicens kan en användare antingen installera företagsinköpta appar eller uppgradera från en kostnadsfri utvärderingsversion till den fullständiga versionen av en app.</span><span class="sxs-lookup"><span data-stu-id="85c48-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="85c48-125">Programlicenser kan tillämpas på antingen användare, användargrupper eller enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="85c48-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="85c48-126">Du&#39;behöver Remote Assist-licenser för användare i din organisation för att kunna använda Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="85c48-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="85c48-127">I den här guiden tilldelar vi Remote Assist-licenser till användargruppen som vi skapade ovan i [Azure-användare och -grupper.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="85c48-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="85c48-128">Licenskraven kan vara olika beroende på om användaren kommer att göra remote Assist-anropet från en enhet eller vara en fjärransluten medarbetare från Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85c48-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="85c48-129">Kryssrutorna Fjärrhjälp och Teams markeras som standard.</span><span class="sxs-lookup"><span data-stu-id="85c48-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="85c48-130">I den här guiden rekommenderar vi att du lämnar standardrutorna markerade.</span><span class="sxs-lookup"><span data-stu-id="85c48-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="85c48-131">Läs mer om de olika [licens- och produktkraven per roll.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)</span><span class="sxs-lookup"><span data-stu-id="85c48-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="85c48-132">Det finns några olika typer av Remote Assist-licenser, så se till att få rätt för dina behov.</span><span class="sxs-lookup"><span data-stu-id="85c48-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="85c48-133">Du&#39;måste skaffa [licensen](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span><span class="sxs-lookup"><span data-stu-id="85c48-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="85c48-134">[Tillämpa dina](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) licenser på gruppen.</span><span class="sxs-lookup"><span data-stu-id="85c48-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="85c48-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="85c48-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="85c48-136">Molnansluten distribution – Distribuera</span><span class="sxs-lookup"><span data-stu-id="85c48-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)