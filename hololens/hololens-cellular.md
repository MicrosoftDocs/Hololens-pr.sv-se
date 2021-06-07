---
title: Ansluta till mobilnät och 5G
description: Ansluta till mobilnät från dina HoloLens-enheter med mixad verklighet.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379999"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="9356d-103">Ansluta till mobilnät och 5G</span><span class="sxs-lookup"><span data-stu-id="9356d-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="9356d-104">HoloLens 2 stöder två metoder för att ansluta till mobilnät och 5G-nätverk:</span><span class="sxs-lookup"><span data-stu-id="9356d-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="9356d-105">Ett ad hoc WiFi-nätverk som tillhandahålls av mobilenheten, vilket vanligtvis kallas "hotspot"</span><span class="sxs-lookup"><span data-stu-id="9356d-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="9356d-106">Begränsat stöd för USB-C-anslutna enheter</span><span class="sxs-lookup"><span data-stu-id="9356d-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="9356d-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="9356d-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="9356d-108">De flesta mobilanslutningsbehov kan uppfyllas med en hotspot.</span><span class="sxs-lookup"><span data-stu-id="9356d-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="9356d-109">HoloLens 2 WiFi stöder 802.11ac, som kan ge de krav på bandbredd och svarstid som krävs för de vanligaste användningsfallen.</span><span class="sxs-lookup"><span data-stu-id="9356d-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="9356d-110">WiFi är också kabelfritt och erbjuder kompatibilitet med det största antalet mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="9356d-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="9356d-111">Ansluta till en hotspot</span><span class="sxs-lookup"><span data-stu-id="9356d-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="9356d-112">Läs enhetens manuella information om hur du aktiverar dess hotspot-läge.</span><span class="sxs-lookup"><span data-stu-id="9356d-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="9356d-113">Aktivera hotspot-läge, ange ett namn för nätverket samt ett känt lösenord.</span><span class="sxs-lookup"><span data-stu-id="9356d-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="9356d-114">I HoloLens 2-nätverksinställningar letar du upp det WiFi-nätverk som skapades i steg 2 och ansluter det.</span><span class="sxs-lookup"><span data-stu-id="9356d-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="9356d-115">USB-C-internetring</span><span class="sxs-lookup"><span data-stu-id="9356d-115">USB-C Tethering</span></span>

<span data-ttu-id="9356d-116">USB-C-internet internet kan ge kortare svarstider för avancerade arbetsbelastningar som behöver det.</span><span class="sxs-lookup"><span data-stu-id="9356d-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="9356d-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)kan till exempel dra nytta av internet internet.</span><span class="sxs-lookup"><span data-stu-id="9356d-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="9356d-118">Observera att Internet-anslutning kräver en kabel mellan den mobila enheten och HoloLens, och internetring stöds av ett begränsat antal enheter.</span><span class="sxs-lookup"><span data-stu-id="9356d-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="9356d-119">USB-C-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="9356d-119">USB-C compatibility</span></span>

<span data-ttu-id="9356d-120">Ett begränsat antal enheter som presenterar sig själva som ethernet-adapter kan användas med Windows Holographic version 2004 och senare.</span><span class="sxs-lookup"><span data-stu-id="9356d-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="9356d-121">Enheter som inte visas som ethernet-kort måste ha stöd för den allmänna Microsoft [RNDIS-drivrutinen.](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-)</span><span class="sxs-lookup"><span data-stu-id="9356d-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="9356d-122">Men endast ett begränsat antal av dessa enheter är kompatibla med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9356d-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="9356d-123">Kontakta enhetens tillverkare för information om huruvida den stöder den allmänna Microsoft RNDIS-drivrutinen.</span><span class="sxs-lookup"><span data-stu-id="9356d-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="9356d-124">Enheter som inte är RNDIS-kompatibla eller kräver att en drivrutin eller ett program installeras stöds inte.</span><span class="sxs-lookup"><span data-stu-id="9356d-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="9356d-125">Även om Microsoft inte har någon lista över kompatibla enheter finns det en community-diskussion om ämnet [här](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="9356d-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="9356d-126">Ansluta till en internetansluten enhet</span><span class="sxs-lookup"><span data-stu-id="9356d-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="9356d-127">Läs enhetens handbok om hur du aktiverar datadelning via USB.</span><span class="sxs-lookup"><span data-stu-id="9356d-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="9356d-128">Den här inställningen kallas ofta "USB-internetdelning", "Datadelning" eller "USB-modem".</span><span class="sxs-lookup"><span data-stu-id="9356d-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="9356d-129">Aktivera datadelning via USB.</span><span class="sxs-lookup"><span data-stu-id="9356d-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="9356d-130">Anslut enheten till HoloLens USB-C-port.</span><span class="sxs-lookup"><span data-stu-id="9356d-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="9356d-131">I HoloLens 2-nätverksinställningar visas enheten automatiskt som en Ethernet-anslutning.</span><span class="sxs-lookup"><span data-stu-id="9356d-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
