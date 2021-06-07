---
title: Översikt över att konfigurera Enhetshantering och Enhetshantering
description: Lär dig hur du konfigurerar CPS, princip- och enhetshantering med mobiler Enhetshantering och etableringspaket.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378866"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="1fc47-103">Översikt över att konfigurera Enhetshantering och Enhetshantering</span><span class="sxs-lookup"><span data-stu-id="1fc47-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="1fc47-104">IT-administratörer kan definiera och implementera principinställningar på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1fc47-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="1fc47-105">Vilka konfigurationsinställningar du använder skiljer sig åt beroende på distributionsscenariot, och företagsenheter kommer att erbjuda IT det bredaste kontrollintervallet.</span><span class="sxs-lookup"><span data-stu-id="1fc47-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="1fc47-106">I Windows 10 är CSP:er (Configuration Service Providers) ett gränssnitt för att läsa, ange, ändra eller ta bort konfigurationsinställningar på enheten.</span><span class="sxs-lookup"><span data-stu-id="1fc47-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="1fc47-107">De här inställningarna mappar till registernycklar eller filer.</span><span class="sxs-lookup"><span data-stu-id="1fc47-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="1fc47-108">Vissa konfigurationstjänstleverantörer stöder WAP-formatet, vissa stöder SyncML och vissa stöder båda.</span><span class="sxs-lookup"><span data-stu-id="1fc47-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="1fc47-109">Mer information om hur du Windows 10 Holographic för enhetshantering finns i den fullständiga listan över [CP:er som stöds i HoloLens-enheter.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="1fc47-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="1fc47-110">IT-administratörer kan också hantera princip-CSP på enheter. Se den fullständiga listan över princip-CSP:er som [stöds av HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="1fc47-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="1fc47-111">Konfigurationsmetoder</span><span class="sxs-lookup"><span data-stu-id="1fc47-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="1fc47-112">Konfigurera med MDM</span><span class="sxs-lookup"><span data-stu-id="1fc47-112">Configure with MDM</span></span>

<span data-ttu-id="1fc47-113">CSP:er och principer kan enkelt hanteras på alla personliga enheter eller företagsenhet som registrerats i ett MDM-system.</span><span class="sxs-lookup"><span data-stu-id="1fc47-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="1fc47-114">När en enhet har registrerats i MDM-lösningen kan du hantera den enheten eller en uppsättning enheter med hjälp av enhetskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="1fc47-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="1fc47-115">Läs mer om hur du [hanterar dina HoloLens-enheter via MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1fc47-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="1fc47-116">Konfigurera med etableringspaket</span><span class="sxs-lookup"><span data-stu-id="1fc47-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="1fc47-117">HoloLens 2 stöder också inställning av en begränsad uppsättning CSP-konfigurationer för HoloLens 2-enheter via anpassade etableringspaket.</span><span class="sxs-lookup"><span data-stu-id="1fc47-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="1fc47-118">Etableringspaket används vanligtvis för icke-MDM-hanterade enheter och måste tillämpas manuellt på varje enhet.</span><span class="sxs-lookup"><span data-stu-id="1fc47-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="1fc47-119">Läs information om hur du skapar [anpassade etableringspaket för HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="1fc47-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="1fc47-120">Konfigurationer</span><span class="sxs-lookup"><span data-stu-id="1fc47-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="1fc47-121">Vanliga enhetsbegränsningar</span><span class="sxs-lookup"><span data-stu-id="1fc47-121">Common device restrictions</span></span>

<span data-ttu-id="1fc47-122">Vissa enhetsbegränsningar är så enkla och inaktiverar en funktion eller anslutning till enheten.</span><span class="sxs-lookup"><span data-stu-id="1fc47-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="1fc47-123">Mer information om dessa finns i vanliga [enhetsbegränsningar.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="1fc47-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="1fc47-124">Helskärmsläge</span><span class="sxs-lookup"><span data-stu-id="1fc47-124">Kiosk modes</span></span>

<span data-ttu-id="1fc47-125">Använd helskärmsläge för att styra vilka identiteter som har åtkomst till vilka appar som standard.</span><span class="sxs-lookup"><span data-stu-id="1fc47-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="1fc47-126">Helskärmsläge kan användas för en enda app eller flera appars användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="1fc47-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="1fc47-127">Kioskkonfigurationer sträcker sig från en enda app för alla som använder enheten till olika val av appar för olika grupper.</span><span class="sxs-lookup"><span data-stu-id="1fc47-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="1fc47-128">Helskärmsläge stoppar inte "tillåtna appar" från att starta andra appar och var inte avsett att någonsin.</span><span class="sxs-lookup"><span data-stu-id="1fc47-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="1fc47-129">Läs mer genom [att läsa om helskärmsläge och hur du använder dem.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="1fc47-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="1fc47-130">Sidsynlighet för inställningar</span><span class="sxs-lookup"><span data-stu-id="1fc47-130">Settings Page Visibility</span></span>

<span data-ttu-id="1fc47-131">Använd appprincipen Inställningar för att styra vilka identiteter som har åtkomst till inställningar som standard.</span><span class="sxs-lookup"><span data-stu-id="1fc47-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="1fc47-132">Med den här principen kan appen Inställningar konfigureras för att antingen endast visa de valda sidorna eller dölja alla valda sidor.</span><span class="sxs-lookup"><span data-stu-id="1fc47-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="1fc47-133">[Läs mer om hur du konfigurerar de tillgängliga sidorna.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="1fc47-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="1fc47-134">Den här funktionen är för närvarande endast tillgänglig [i Windows Insider skapar](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="1fc47-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="1fc47-135">Se till att enheter som du tänker använda den här funktionen för finns på version 19041.1349+.</span><span class="sxs-lookup"><span data-stu-id="1fc47-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="1fc47-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="1fc47-136">WDAC</span></span>

<span data-ttu-id="1fc47-137">Använd WDAC-konfigurationen för att kontrollera vilka appar/processer som tillåts/tillåts inte startas oavsett om systemet är i helskärmsläge eller inte.</span><span class="sxs-lookup"><span data-stu-id="1fc47-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="1fc47-138">Se vår översikt för WDAC.</span><span class="sxs-lookup"><span data-stu-id="1fc47-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
