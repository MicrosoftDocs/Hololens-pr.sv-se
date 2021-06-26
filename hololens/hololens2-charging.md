---
title: HoloLens 2-batteri och laddning
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
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923592"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="8f585-103">HoloLens 2-batteri och laddning</span><span class="sxs-lookup"><span data-stu-id="8f585-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="8f585-104">Den här sidan innehåller information om hur du laddar HoloLens 2 och använder externa batteripaket.</span><span class="sxs-lookup"><span data-stu-id="8f585-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="8f585-105">Ladda enheten</span><span class="sxs-lookup"><span data-stu-id="8f585-105">Charging the device</span></span>

<span data-ttu-id="8f585-106">Använd kabeln [och USB Type-C-kabeln](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) som medkom med HoloLens 2 eftersom det är det bästa sättet att debitera enheten.</span><span class="sxs-lookup"><span data-stu-id="8f585-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="8f585-107">Den ingår i HoloLens 2 ger upp till 9V @ 2A (18 W).</span><span class="sxs-lookup"><span data-stu-id="8f585-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="8f585-108">Tillsammans med den medföljande väggväggen kan HoloLens 2-enheter ladda upp batteriet till full på mindre än 65 minuter när enheten är i vänteläge.</span><span class="sxs-lookup"><span data-stu-id="8f585-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="8f585-109">Om tillbehören inte är tillgängliga kontrollerar du att de tillgängliga strömerna har stöd för minst 15 W ström.</span><span class="sxs-lookup"><span data-stu-id="8f585-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="8f585-110">Om möjligt bör du undvika att använda en dator för att debitera enheten via USB, vilket är långsamt.</span><span class="sxs-lookup"><span data-stu-id="8f585-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="8f585-111">Kontrollera batteriladdningsnivån</span><span class="sxs-lookup"><span data-stu-id="8f585-111">Checking the battery charge level</span></span>
<span data-ttu-id="8f585-112">Om enheten är korrekt startad och körs finns det tre sätt att kontrollera batteriladdningsnivån:</span><span class="sxs-lookup"><span data-stu-id="8f585-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="8f585-113">Från huvudmenyn i HoloLens-enhetens användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="8f585-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="8f585-114">Visa lysdioden nära strömknappen (för en avgift på 40 procent bör du se minst två solida lysdioder).</span><span class="sxs-lookup"><span data-stu-id="8f585-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="8f585-115">När enheten laddas tänds batteriindikatorn för att ange den aktuella avgiftsnivån.</span><span class="sxs-lookup"><span data-stu-id="8f585-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="8f585-116">Det sista lampan tonas in och ut för att indikera aktiv laddning.</span><span class="sxs-lookup"><span data-stu-id="8f585-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="8f585-117">När HoloLens är på visar batteriindikatorn batterinivån i fem steg.</span><span class="sxs-lookup"><span data-stu-id="8f585-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="8f585-118">När bara en av de fem lamporna är på är batterinivån under 20 procent.</span><span class="sxs-lookup"><span data-stu-id="8f585-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="8f585-119">Om batterinivån är kritiskt låg och du försöker slå på enheten blinkar en lampa en kort stund och går sedan ut.</span><span class="sxs-lookup"><span data-stu-id="8f585-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="8f585-120">På värddatorn öppnar du **Utforskaren** letar efter din HoloLens 2-enhet till vänster under **Den här datorn**.</span><span class="sxs-lookup"><span data-stu-id="8f585-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="8f585-121">Högerklicka på enheten och välj **Egenskaper.**</span><span class="sxs-lookup"><span data-stu-id="8f585-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="8f585-122">En dialogruta visar batteriladdningsnivån.</span><span class="sxs-lookup"><span data-stu-id="8f585-122">A dialog box will show the battery charge level.</span></span>

   ![En HoloLens 2-egenskapsskärm visar batteriändringsnivå](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="8f585-124">Alternativa debiteringsspecifikationer</span><span class="sxs-lookup"><span data-stu-id="8f585-124">Alternative charging specifications</span></span>

<span data-ttu-id="8f585-125">HoloLens 2 kan debiteras av [USB-strömkällor](https://www.usb.org/usb-charger-pd) på upp till 27 watt.</span><span class="sxs-lookup"><span data-stu-id="8f585-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="8f585-126">Om källan kan ange minst 10 Watts kan HoloLens-driftstiden utökas (eventuellt på obestämd tid för vissa arbetsbelastningar).</span><span class="sxs-lookup"><span data-stu-id="8f585-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="8f585-127">Om du använder en USB-A till USB-C-laddningskabel begränsar du avgiften till 7,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="8f585-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="8f585-128">Drifttiden kommer fortfarande att utökas, men inte så länge som du använder USB-C till C.</span><span class="sxs-lookup"><span data-stu-id="8f585-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="8f585-129">När HoloLens är i vänteläge räcker 18 Watt för att nå den maximala laddningstakten för det interna batteriet.</span><span class="sxs-lookup"><span data-stu-id="8f585-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="8f585-130">När HoloLens används kan avgiftspriset minskas eftersom HoloLens prioriterar driften över debitering.</span><span class="sxs-lookup"><span data-stu-id="8f585-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f585-131">Vi rekommenderar att HoloLens 2 debiteras till minst 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="8f585-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="8f585-132">5V/1.5A bör inte användas.</span><span class="sxs-lookup"><span data-stu-id="8f585-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="8f585-133">Externa batteripaket</span><span class="sxs-lookup"><span data-stu-id="8f585-133">External Battery Packs</span></span>

<span data-ttu-id="8f585-134">Batteripaket som uppfyller specifikationerna ovan kan användas med HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8f585-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="8f585-135">Observera dock att vissa USB-C-batteripaket är anslutna och ger ström via samma USB-C-port.</span><span class="sxs-lookup"><span data-stu-id="8f585-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="8f585-136">Det är viktigt att dessa batteripaket implementerar [TRY. SRC för](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) att säkerställa att de debiterar HoloLens i stället för att debitera från den.</span><span class="sxs-lookup"><span data-stu-id="8f585-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="8f585-137">Hantera värme</span><span class="sxs-lookup"><span data-stu-id="8f585-137">Managing Heat</span></span>

<span data-ttu-id="8f585-138">Precis som med alla enheter genererar debitering av HoloLens värme.</span><span class="sxs-lookup"><span data-stu-id="8f585-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="8f585-139">Ju snabbare avgiften är, desto mer värme genereras.</span><span class="sxs-lookup"><span data-stu-id="8f585-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="8f585-140">Att starta en avgift på en lägre batterinivå genererar dessutom mer värme än att starta en laddning när batteriet mest är fullt.</span><span class="sxs-lookup"><span data-stu-id="8f585-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="8f585-141">Kunder som behöver använda HoloLens under längre tidsperioder i heta miljöer kan använda följande metoder:</span><span class="sxs-lookup"><span data-stu-id="8f585-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="8f585-142">Det är ok att ansluta HoloLens 2 till en extern strömkälla även när det interna batteriet är helt laddat.</span><span class="sxs-lookup"><span data-stu-id="8f585-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="8f585-143">När ett externt batteri är slut fortsätter HoloLens att fungera med sitt interna batteri.</span><span class="sxs-lookup"><span data-stu-id="8f585-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="8f585-144">Om värme fortfarande är ett problem efter att du har följt stegen ovan bör du överväga att använda ett batteripaket som begränsar debiteringen till 1,5A.</span><span class="sxs-lookup"><span data-stu-id="8f585-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="8f585-145">Observera att det här alternativet inte ger lika mycket drifttid eftersom det interna batteriet fortfarande tar slut långsamt.</span><span class="sxs-lookup"><span data-stu-id="8f585-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8f585-146">Felsökning</span><span class="sxs-lookup"><span data-stu-id="8f585-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="8f585-147">Externa HoloLens-avgifter</span><span class="sxs-lookup"><span data-stu-id="8f585-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="8f585-148">Om HoloLens 2 laddar ett externt batteri i stället för att debiteras av det, betyder det att batteriet inte implementerar [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="8f585-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="8f585-149">Att byta till ett nyare batteripaket är det rekommenderade sättet att lösa det här problemet, men du kan också prova att byta till en USB-A-till-USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="8f585-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="8f585-150">Tänk på att detta begränsar debiteringshastigheten till 7,5 watt.</span><span class="sxs-lookup"><span data-stu-id="8f585-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
