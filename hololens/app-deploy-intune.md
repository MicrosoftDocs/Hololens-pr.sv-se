---
title: Intune och Företagsportal
description: Lär dig att konfigurera, tilldela och skapa en bekväm användarupplevelse med Intune, hantering av mobila enheter och företagsportalen.
keywords: intune, apphantering, app, företagsportal, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378868"
---
# <a name="intune--company-portal"></a><span data-ttu-id="0b741-104">Intune-& Företagsportal</span><span class="sxs-lookup"><span data-stu-id="0b741-104">Intune & Company Portal</span></span>

<span data-ttu-id="0b741-105">Med Mobile Enhetshantering (MDM) kan du använda dina egna anpassade appar via [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) för att distribuera den direkt till dina HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="0b741-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="0b741-106">Microsoft Intune är en molnbaserad tjänst som fokuserar på hantering av mobilenheter (MDM) och hantering av mobilprogram (MAM).</span><span class="sxs-lookup"><span data-stu-id="0b741-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="0b741-107">Intune ingår i Microsofts [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) och gör det möjligt för användarna att vara produktiva samtidigt som organisationens data skyddas.</span><span class="sxs-lookup"><span data-stu-id="0b741-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="0b741-108">Mer information om Intune finns i [Vad är Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="0b741-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="0b741-109">Installation</span><span class="sxs-lookup"><span data-stu-id="0b741-109">Setup</span></span>

1. <span data-ttu-id="0b741-110">Ladda upp en app till en verksamhetsrad eller ladda upp en anpassad app till din Intune-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0b741-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="0b741-111">Se även: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="0b741-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="0b741-112">[Tilldela din app till en grupp](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="0b741-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="0b741-113">Baserat på vilken tilldelningstyp du väljer kan appen levereras automatiskt eller vara tillgänglig för att enkelt hämtas om du har ett urval av appar.</span><span class="sxs-lookup"><span data-stu-id="0b741-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="0b741-114">När du skapar ditt appx-paket ska du se till att ta med arkitekturen för de enheter som du distribuerar till.</span><span class="sxs-lookup"><span data-stu-id="0b741-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="0b741-115">HoloLens 2 är ARM64 och HoloLens (1st Gen) är x86.</span><span class="sxs-lookup"><span data-stu-id="0b741-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="0b741-116">Du kan inkludera båda i ett enda appx-paket om du planerar att ha en miljö med blandade enheter.</span><span class="sxs-lookup"><span data-stu-id="0b741-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="0b741-117">Tilldelningstyper</span><span class="sxs-lookup"><span data-stu-id="0b741-117">Assignment types</span></span>

<span data-ttu-id="0b741-118">Om du vill att din app ska installeras automatiskt på enheten efter registreringen bör du **välja Krävs** för dessa grupper.</span><span class="sxs-lookup"><span data-stu-id="0b741-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="0b741-119">Om du vill göra appen tillgänglig för nedladdning till enheter som registrerats via företagsportalen väljer du **Tillgänglig för registrerade enheter.**</span><span class="sxs-lookup"><span data-stu-id="0b741-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="0b741-120">End-User Experience</span><span class="sxs-lookup"><span data-stu-id="0b741-120">End-User Experience</span></span>

<span data-ttu-id="0b741-121">När du har ställt in konfigurationen i Intune är du redo för slutanvändarna att ta emot dina valda appar.</span><span class="sxs-lookup"><span data-stu-id="0b741-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="0b741-122">Följ dessa steg för att hämta dina appar automatiskt:</span><span class="sxs-lookup"><span data-stu-id="0b741-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="0b741-123">Registrera din enhet med din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0b741-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="0b741-124">När din enhet har slutfört registreringen bör du få appen på enheten.</span><span class="sxs-lookup"><span data-stu-id="0b741-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="0b741-125">Om du inte ser appen direkt går du till Inställningar Konton Arbets- eller skolkontoinformation och bläddrar ned för att se  >    >    >   information om status för installerad app.</span><span class="sxs-lookup"><span data-stu-id="0b741-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="0b741-126">Så här kommer du till appar via Företagsportal:</span><span class="sxs-lookup"><span data-stu-id="0b741-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="0b741-127">Öppna **Start-menyn** och välj **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="0b741-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="0b741-128">Sök efter **Företagsportal** och ladda ned appen.</span><span class="sxs-lookup"><span data-stu-id="0b741-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="0b741-129">Logga in på ditt konto.</span><span class="sxs-lookup"><span data-stu-id="0b741-129">Sign into your account.</span></span>
4. <span data-ttu-id="0b741-130">Välj den app som du vill ta emot och ladda ned den.</span><span class="sxs-lookup"><span data-stu-id="0b741-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="0b741-131">Läs mer om [automatisk installation av Företagsportal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) och distribuera och hantera appar i [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="0b741-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
