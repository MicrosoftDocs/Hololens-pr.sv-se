---
title: Batteri och laddning
description: Så här debiterar du HoloLens och använder externa batteripaket.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380136"
---
# <a name="battery-and-charging"></a><span data-ttu-id="adf54-103">Batteri och laddning</span><span class="sxs-lookup"><span data-stu-id="adf54-103">Battery and Charging</span></span>

<span data-ttu-id="adf54-104">Den här sidan innehåller information om hur du laddar HoloLens 2 och använder externa batteripaket.</span><span class="sxs-lookup"><span data-stu-id="adf54-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="adf54-105">Included Charger</span><span class="sxs-lookup"><span data-stu-id="adf54-105">Included Charger</span></span>

<span data-ttu-id="adf54-106">Den ingår i HoloLens 2 ger upp till 9V @ 2A (18 W).</span><span class="sxs-lookup"><span data-stu-id="adf54-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="adf54-107">När det är möjligt rekommenderar vi starkt att du debiterar med hjälp av den medföljande 50-500-500-500-100-100-1</span><span class="sxs-lookup"><span data-stu-id="adf54-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="adf54-108">Specifikationer</span><span class="sxs-lookup"><span data-stu-id="adf54-108">Specifications</span></span>

<span data-ttu-id="adf54-109">HoloLens 2 kan debiteras av [USB-strömkällor](https://www.usb.org/usb-charger-pd) på upp till 27 watt.</span><span class="sxs-lookup"><span data-stu-id="adf54-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="adf54-110">Om källan kan ange minst 10 Watts kan HoloLens-driftstiden utökas (eventuellt på obestämd tid för vissa arbetsbelastningar).</span><span class="sxs-lookup"><span data-stu-id="adf54-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="adf54-111">Om du använder en USB-A till USB-C-laddningskabel begränsar du avgiften till 7,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="adf54-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="adf54-112">Drifttiden kommer fortfarande att utökas, men inte så länge som du använder USB-C till C.</span><span class="sxs-lookup"><span data-stu-id="adf54-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="adf54-113">När HoloLens är i vänteläge räcker 18 watt för att nå den maximala laddningstakten för det interna batteriet.</span><span class="sxs-lookup"><span data-stu-id="adf54-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="adf54-114">När HoloLens används kan avgiftspriset minskas eftersom HoloLens prioriterar drift över debitering.</span><span class="sxs-lookup"><span data-stu-id="adf54-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adf54-115">Vi rekommenderar att HoloLens 2 debiteras till minst 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="adf54-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="adf54-116">5V/1.5A bör inte användas.</span><span class="sxs-lookup"><span data-stu-id="adf54-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="adf54-117">Externa batteripaket</span><span class="sxs-lookup"><span data-stu-id="adf54-117">External Battery Packs</span></span>

<span data-ttu-id="adf54-118">Batteripaket som uppfyller specifikationerna ovan kan användas med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="adf54-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="adf54-119">Observera dock att vissa USB-C-batteripaket är anslutna och ger ström via samma USB-C-port.</span><span class="sxs-lookup"><span data-stu-id="adf54-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="adf54-120">Det är viktigt att dessa batteripaket implementerar [TRY. SRC för](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) att säkerställa att de debiterar HoloLens i stället för att debitera från den.</span><span class="sxs-lookup"><span data-stu-id="adf54-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="adf54-121">Hantera värme</span><span class="sxs-lookup"><span data-stu-id="adf54-121">Managing Heat</span></span>

<span data-ttu-id="adf54-122">Precis som med alla enheter genererar debitering av HoloLens värme.</span><span class="sxs-lookup"><span data-stu-id="adf54-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="adf54-123">Ju snabbare avgiften är, desto mer värme genereras.</span><span class="sxs-lookup"><span data-stu-id="adf54-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="adf54-124">Att starta en avgift på en lägre batterinivå genererar dessutom mer värme än att starta en laddning när batteriet mest är fullt.</span><span class="sxs-lookup"><span data-stu-id="adf54-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="adf54-125">Kunder som behöver använda HoloLens under längre tidsperioder i heta miljöer kan använda följande metoder:</span><span class="sxs-lookup"><span data-stu-id="adf54-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="adf54-126">Det är ok att ansluta HoloLens 2 till en extern strömkälla även när det interna batteriet är helt laddat.</span><span class="sxs-lookup"><span data-stu-id="adf54-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="adf54-127">När ett externt batteri är slut fortsätter HoloLens att fungera med sitt interna batteri.</span><span class="sxs-lookup"><span data-stu-id="adf54-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="adf54-128">Om värme fortfarande är ett problem efter att du har följt stegen ovan bör du överväga att använda ett batteripaket som begränsar debiteringen till 1,5A.</span><span class="sxs-lookup"><span data-stu-id="adf54-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="adf54-129">Observera att det här alternativet inte ger lika mycket drifttid eftersom det interna batteriet fortfarande tar slut långsamt.</span><span class="sxs-lookup"><span data-stu-id="adf54-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="adf54-130">Felsökning</span><span class="sxs-lookup"><span data-stu-id="adf54-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="adf54-131">Externa HoloLens-avgifter</span><span class="sxs-lookup"><span data-stu-id="adf54-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="adf54-132">Om HoloLens 2 laddar ett externt batteri i stället för att debiteras av det, betyder det att batteriet inte implementerar [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="adf54-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="adf54-133">Att byta till ett nyare batteripaket är det rekommenderade sättet att lösa det här problemet, men du kan också prova att byta till en USB-A-till-USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="adf54-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="adf54-134">Tänk på att detta begränsar debiteringshastigheten till 7,5 watt.</span><span class="sxs-lookup"><span data-stu-id="adf54-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
