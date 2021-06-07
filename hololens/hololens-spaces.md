---
title: Mappa fysiska utrymmen med HoloLens
description: HoloLens lär sig hur ett utrymme ser ut över tid. Användare kan underlätta den här processen genom att flytta HoloLens på vissa sätt genom utrymmet.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, spatial mapping, HoloLens, surface rekonstruktion, mesh, head tracking, mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380059"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="6d427-105">Mappa fysiska utrymmen med HoloLens</span><span class="sxs-lookup"><span data-stu-id="6d427-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="6d427-106">HoloLens blandar hologram med din fysiska värld.</span><span class="sxs-lookup"><span data-stu-id="6d427-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="6d427-107">För att göra det måste HoloLens lära sig mer om den fysiska världen omkring dig och komma ihåg var du placerar hologram i det utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="6d427-108">Med tiden bygger HoloLens upp en *rumslig karta* över den miljö som den har sett.</span><span class="sxs-lookup"><span data-stu-id="6d427-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="6d427-109">HoloLens uppdaterar kartan när miljön ändras.</span><span class="sxs-lookup"><span data-stu-id="6d427-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="6d427-110">Så länge du är inloggad och enheten är aktiverad skapar och uppdaterar HoloLens dina rumsliga kartor.</span><span class="sxs-lookup"><span data-stu-id="6d427-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="6d427-111">Om du håller i eller bär enheten med kamerorna riktade mot ett utrymme försöker HoloLens mappa området.</span><span class="sxs-lookup"><span data-stu-id="6d427-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="6d427-112">Även om HoloLens lär sig ett utrymme naturligt över tid, finns det sätt på vilka du kan hjälpa HoloLens att mappa ditt utrymme snabbare och effektivare.</span><span class="sxs-lookup"><span data-stu-id="6d427-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="6d427-113">Om holoLens inte kan mappa ditt utrymme eller om kalibreringen är slut kan HoloLens gå in i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="6d427-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="6d427-114">I begränsat läge kan du inte placera hologram i din miljö.</span><span class="sxs-lookup"><span data-stu-id="6d427-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="6d427-115">Den här artikeln förklarar hur HoloLens mappar utrymmen, hur du förbättrar rumslig mappning och hur du hanterar rumsliga data som HoloLens samlar in.</span><span class="sxs-lookup"><span data-stu-id="6d427-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="6d427-116">Välja och konfigurera och ditt utrymme</span><span class="sxs-lookup"><span data-stu-id="6d427-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="6d427-117">Funktioner i din miljö kan göra det svårt för HoloLens att tolka ett utrymme.</span><span class="sxs-lookup"><span data-stu-id="6d427-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="6d427-118">Ljusnivåer, material i utrymmet, objektens layout och mycket annat kan påverka hur HoloLens mappar ett område.</span><span class="sxs-lookup"><span data-stu-id="6d427-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="6d427-119">HoloLens fungerar bäst i vissa typer av miljöer.</span><span class="sxs-lookup"><span data-stu-id="6d427-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="6d427-120">Om du vill skapa den bästa rumsliga kartan väljer du ett rum som har tillräckligt med ljus och mycket utrymme.</span><span class="sxs-lookup"><span data-stu-id="6d427-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="6d427-121">Undvik mörka utrymmen och rum som har mycket mörka, ljusbruna eller genomskinliga ytor (till exempel speglingar eller pråliga ytor).</span><span class="sxs-lookup"><span data-stu-id="6d427-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="6d427-122">HoloLens är optimerat för inomhusanvändning.</span><span class="sxs-lookup"><span data-stu-id="6d427-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="6d427-123">Rumslig mappning fungerar också Wi-Fi är aktiverat, även om det inte behöver vara anslutet till ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="6d427-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="6d427-124">HoloLens kan Wi-Fi åtkomstpunkter även om det inte är anslutet eller autentiserat.</span><span class="sxs-lookup"><span data-stu-id="6d427-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="6d427-125">HoloLens-funktionen ändras inte om åtkomstpunkterna endast är Internetanslutna eller intranät/lokala.</span><span class="sxs-lookup"><span data-stu-id="6d427-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="6d427-126">Använd endast HoloLens på säkra platser utan problem.</span><span class="sxs-lookup"><span data-stu-id="6d427-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="6d427-127">[Mer om säkerhet](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="6d427-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="6d427-128">Mappa ditt utrymme</span><span class="sxs-lookup"><span data-stu-id="6d427-128">Mapping your space</span></span>

<span data-ttu-id="6d427-129">Nu är du redo att börja mappa reservreserven.</span><span class="sxs-lookup"><span data-stu-id="6d427-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="6d427-130">När HoloLens börjar mappa din miljö ser du en nätgrafik som sprids över utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="6d427-131">I mixed reality-hemmet kan du utlösa kartan som ska visas genom att välja på en mappad yta.</span><span class="sxs-lookup"><span data-stu-id="6d427-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="6d427-132">Här följer riktlinjer för att skapa en bra rumslig karta.</span><span class="sxs-lookup"><span data-stu-id="6d427-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="6d427-133">Förstå scenarierna för området</span><span class="sxs-lookup"><span data-stu-id="6d427-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="6d427-134">Det är viktigt att ägna mest tid åt att använda HoloLens, så att kartan är relevant och fullständig.</span><span class="sxs-lookup"><span data-stu-id="6d427-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="6d427-135">Om ett användarscenario för HoloLens till exempel innebär att flytta från punkt A till punkt B går du den vägen två till tre gånger och tittar i alla riktningar när du flyttar.</span><span class="sxs-lookup"><span data-stu-id="6d427-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="6d427-136">Gå långsamt runt i utrymmet</span><span class="sxs-lookup"><span data-stu-id="6d427-136">Walk slowly around the space</span></span>

<span data-ttu-id="6d427-137">Om du går för snabbt runt i området är det troligt att HoloLens missar mappningsområden.</span><span class="sxs-lookup"><span data-stu-id="6d427-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="6d427-138">Gå långsamt runt i utrymmet och stoppa var 5–8:e fot för att titta runt i din miljö.</span><span class="sxs-lookup"><span data-stu-id="6d427-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="6d427-139">Smidiga rörelser hjälper även HoloLens-kartan mer effektivt.</span><span class="sxs-lookup"><span data-stu-id="6d427-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="6d427-140">Titta i alla riktningar</span><span class="sxs-lookup"><span data-stu-id="6d427-140">Look in all directions</span></span>

<span data-ttu-id="6d427-141">När du tittar runt när du mappar utrymmet får HoloLens mer data om var punkter är relativa till varandra.</span><span class="sxs-lookup"><span data-stu-id="6d427-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="6d427-142">Om du till exempel inte letar upp kanske HoloLens inte vet var taket i ett rum finns.</span><span class="sxs-lookup"><span data-stu-id="6d427-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="6d427-143">Glöm inte att titta nedåt på marken när du mappar utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="6d427-144">Täcka viktiga områden flera gånger</span><span class="sxs-lookup"><span data-stu-id="6d427-144">Cover key areas multiple times</span></span>

<span data-ttu-id="6d427-145">Om du går igenom ett område flera gånger blir det till hjälp att hämta funktioner som du kan ha missat i den första genomgången.</span><span class="sxs-lookup"><span data-stu-id="6d427-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="6d427-146">Om du vill skapa en perfekt karta kan du prova att gå igenom ett område två till tre gånger.</span><span class="sxs-lookup"><span data-stu-id="6d427-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="6d427-147">Om möjligt, när du upprepar dessa rörelser, kan du ägna tid åt att gå genom ett område i en riktning och sedan vända dig om och gå tillbaka som du kom.</span><span class="sxs-lookup"><span data-stu-id="6d427-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="6d427-148">Ta dig tid att mappa området</span><span class="sxs-lookup"><span data-stu-id="6d427-148">Take your time mapping the area</span></span>

<span data-ttu-id="6d427-149">Det kan ta mellan 15 och 20 minuter för HoloLens att fullständigt mappa och anpassa sig till sin omgivning.</span><span class="sxs-lookup"><span data-stu-id="6d427-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="6d427-150">Om du har ett utrymme där du planerar att använda en HoloLens ofta kan du förhindra problem senare om du tar den tiden för att mappa utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="6d427-151">Möjliga fel i den rumsliga kartan</span><span class="sxs-lookup"><span data-stu-id="6d427-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="6d427-152">Fel i data för rumslig mappning finns i några kategorier:</span><span class="sxs-lookup"><span data-stu-id="6d427-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="6d427-153">*Hål:* Verkliga ytor saknas i rumsliga mappningsdata.</span><span class="sxs-lookup"><span data-stu-id="6d427-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="6d427-154">*Grafer:* Det finns ytor i de rumsliga mappningsdata som inte finns i den verkliga världen.</span><span class="sxs-lookup"><span data-stu-id="6d427-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="6d427-155">*Maskhål:* HoloLens "förlorar" en del av den rumsliga kartan genom att tro att den finns i en annan del av kartan än den faktiskt är.</span><span class="sxs-lookup"><span data-stu-id="6d427-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="6d427-156">*Bias:* Ytor i rumsliga mappningsdata justeras felaktigt med verkliga ytor, antingen push-in eller dras ut.</span><span class="sxs-lookup"><span data-stu-id="6d427-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="6d427-157">Om du ser något av dessa fel kan du använda [FeedbackHub för](hololens-feedback.md) att skicka feedback.</span><span class="sxs-lookup"><span data-stu-id="6d427-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="6d427-158">Säkerhet och lagring för rumsliga data</span><span class="sxs-lookup"><span data-stu-id="6d427-158">Security and storage for spatial data</span></span>

<span data-ttu-id="6d427-159">Windows 10 version 1803-uppdatering för Microsoft HoloLens och senare lagrar mappningsdata i en lokal databas (på enheten).</span><span class="sxs-lookup"><span data-stu-id="6d427-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="6d427-160">HoloLens-användare kan inte komma åt map-databasen direkt, även om enheten är ansluten till en dator eller när du använder Utforskaren appen.</span><span class="sxs-lookup"><span data-stu-id="6d427-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="6d427-161">När BitLocker är aktiverat på HoloLens krypteras även lagrade kartdata tillsammans med hela volymen.</span><span class="sxs-lookup"><span data-stu-id="6d427-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="6d427-162">Ta bort kartdata och kända utrymmen från HoloLens</span><span class="sxs-lookup"><span data-stu-id="6d427-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="6d427-163">Det finns två alternativ för att ta bort kartdata **i Inställningar > System > Hologram:**</span><span class="sxs-lookup"><span data-stu-id="6d427-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="6d427-164">Om du vill ta bort hologram i närheten väljer du **Ta bort hologram i närheten.**</span><span class="sxs-lookup"><span data-stu-id="6d427-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="6d427-165">Det här kommandot rensar kartdata och fäst hologram för det aktuella utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="6d427-166">Om du fortsätter att använda enheten i samma utrymme skapas och lagras ett helt nytt kartavsnitt som ersätter den borttagna informationen.</span><span class="sxs-lookup"><span data-stu-id="6d427-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6d427-167">Hologram i närheten är hologram som är fästa inom samma kartavsnitt i det aktuella utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="6d427-168">Du kan till exempel använda det här alternativet för att rensa arbetsrelaterade kartdata utan att påverka hemrelaterade kartdata.</span><span class="sxs-lookup"><span data-stu-id="6d427-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="6d427-169">Om du vill ta bort alla hologram väljer du **Ta bort alla hologram.**</span><span class="sxs-lookup"><span data-stu-id="6d427-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="6d427-170">Det här kommandot rensar alla kartdata som lagras på enheten samt alla ankare hologram.</span><span class="sxs-lookup"><span data-stu-id="6d427-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="6d427-171">Du måste uttryckligen placera hologram.</span><span class="sxs-lookup"><span data-stu-id="6d427-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="6d427-172">Du kommer inte att kunna identifiera hologrammen som placerats tidigare på nya sätt.</span><span class="sxs-lookup"><span data-stu-id="6d427-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="6d427-173">När du har tagit bort närliggande eller alla hologram börjar HoloLens genast skanna och mappa det aktuella utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="6d427-174">Wi-Fi data i rumsliga kartor</span><span class="sxs-lookup"><span data-stu-id="6d427-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="6d427-175">HoloLens lagrar Wi-Fi egenskaper för att korrelera hologramplatser och kartavsnitt som lagras i HoloLens-databasen med kända utrymmen.</span><span class="sxs-lookup"><span data-stu-id="6d427-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="6d427-176">Information om Wi-Fi egenskaper är inte tillgänglig för användare och skickas inte till Microsoft med hjälp av molnet eller med telemetri.</span><span class="sxs-lookup"><span data-stu-id="6d427-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="6d427-177">Så länge Wi-Fi är aktiverat korrelerar HoloLens kartdata med närliggande Wi-Fi åtkomstpunkter.</span><span class="sxs-lookup"><span data-stu-id="6d427-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="6d427-178">Det finns ingen skillnad i beteendet om ett nätverk är anslutet eller bara har identifierats i närheten.</span><span class="sxs-lookup"><span data-stu-id="6d427-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="6d427-179">Om Wi-Fi är inaktiverat söker HoloLens fortfarande igenom utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6d427-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="6d427-180">HoloLens måste dock söka efter mer av kartdata i blankstegsdatabasen och kan behöva mer tid för att hitta hologram.</span><span class="sxs-lookup"><span data-stu-id="6d427-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="6d427-181">Utan Wi-Fi information måste HoloLens jämföra aktiva genomsökningar med alla hologramankare och kartavsnitt som lagras på enheten för att hitta rätt del av kartan.</span><span class="sxs-lookup"><span data-stu-id="6d427-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d427-182">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6d427-182">Related topics</span></span>

- [<span data-ttu-id="6d427-183">Design av rumslig mappning</span><span class="sxs-lookup"><span data-stu-id="6d427-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
