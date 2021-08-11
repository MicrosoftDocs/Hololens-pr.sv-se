---
title: Mappa fysiska utrymmen med HoloLens
description: HoloLens lär sig hur ett utrymme ser ut över tid. Användare kan underlätta processen genom att flytta HoloLens på vissa sätt genom utrymmet.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, spatial mapping, HoloLens, surface rekonstruering, nät, huvudspårning, mappning
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: d1eef6bdf463aa400504af7b35a0fd2b8e2b44499d6ff7b93e70a2dd5952ef88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662867"
---
# <a name="map-physical-spaces-with-hololens"></a>Mappa fysiska utrymmen med HoloLens

HoloLens blandar hologram med din fysiska värld. För att göra det HoloLens lära sig mer om den fysiska världen omkring dig och komma ihåg var du placerar hologram i det utrymmet.

Med tiden bygger HoloLens en *rumslig karta över* miljön som den har sett.  HoloLens uppdaterar kartan när miljön ändras. Så länge du är inloggad och enheten är aktiverad kan du HoloLens och uppdaterar dina rumsliga kartor. Om du håller eller bär enheten med kamerorna riktade mot ett HoloLens försöker mappa området. Även HoloLens lär sig ett utrymme naturligt över tid, finns det sätt på vilka du kan hjälpa HoloLens att mappa ditt utrymme snabbare och effektivare.  

> [!NOTE]
> Om ditt HoloLens inte kan mappa ditt utrymme eller om kalibreringen är slut kan HoloLens in i begränsat läge. I begränsat läge kan du inte placera hologram i din miljö.

Den här artikeln förklarar HoloLens mappar utrymmen, hur du förbättrar rumslig mappning och hur du hanterar de rumsliga data som HoloLens samlar in.

## <a name="choosing-and-setting-up-and-your-space"></a>Välja och konfigurera och ditt utrymme

Funktioner i din miljö kan göra det svårt för HoloLens att tolka ett utrymme. Ljusnivåer, material i utrymmet, objektens layout och mycket annat kan påverka hur HoloLens mappar ett område.

HoloLens fungerar bäst i vissa typer av miljöer. Om du vill skapa den bästa rumsliga kartan väljer du ett rum som har tillräckligt med ljus och mycket utrymme. Undvik mörka utrymmen och rum som har mycket mörka, ljusbruna eller genomskinliga ytor (till exempel speglingar eller pråliga ytor).

HoloLens är optimerad för inomhusanvändning. Rumslig mappning fungerar också Wi-Fi är aktiverat, även om det inte behöver vara anslutet till ett nätverk. HoloLens kan hämta Wi-Fi åtkomstpunkter även om den inte är ansluten eller autentiserad. HoloLens funktioner ändras inte om åtkomstpunkterna endast är Internetanslutna eller intranät/lokala.

Använd endast HoloLens på säkra platser utan problem. [Mer om säkerhet](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Mappa ditt utrymme

Nu är du redo att börja mappa reservreserven.  När HoloLens börjar mappa din miljö ser du en nätgrafik som sprider sig över utrymmet.  I mixed reality-hemmet kan du utlösa kartan som ska visas genom att välja på en mappad yta.

Här följer riktlinjer för att skapa en bra rumslig karta.

### <a name="understand-the-scenarios-for-the-area"></a>Förstå scenarierna för området

Det är viktigt att ägna mest tid åt att använda HoloLens, så att kartan är relevant och fullständig. Om ett användarscenario för en HoloLens innebär att flytta från punkt A till punkt B går du den vägen två till tre gånger och tittar i alla riktningar när du flyttar.  

### <a name="walk-slowly-around-the-space"></a>Gå långsamt runt i utrymmet

Om du går för snabbt runt i området är det troligt att HoloLens kommer att missa mappningsområden. Gå långsamt runt i utrymmet och stoppa var 5–8:e fot för att titta runt i din miljö.  

Smidiga rörelser hjälper också HoloLens mappningen mer effektivt.

### <a name="look-in-all-directions"></a>Titta i alla riktningar

När du tittar runt när du mappar utrymmet får HoloLens mer data om var punkter är relativa till varandra.  

Om du till exempel inte letar upp HoloLens kanske inte vet var taket i ett rum är.  

Glöm inte att titta nedåt på marken när du mappar utrymmet.

### <a name="cover-key-areas-multiple-times"></a>Täcka viktiga områden flera gånger

Om du går igenom ett område flera gånger blir det till hjälp att hämta funktioner som du kan ha missat i den första genomgången. Om du vill skapa en perfekt karta kan du prova att gå igenom ett område två till tre gånger.

Om möjligt, när du upprepar dessa rörelser, kan du ägna tid åt att gå genom ett område i en riktning och sedan vända dig om och gå tillbaka som du kom.

### <a name="take-your-time-mapping-the-area"></a>Ta dig tid att mappa området

Det kan ta mellan 15 och 20 minuter för HoloLens att helt mappa och anpassa sig till dess omgivning. Om du har ett utrymme där du planerar att använda en HoloLens ofta, kan det förhindra problem senare om du tar den tiden för att mappa utrymmet.  

## <a name="possible-errors-in-the-spatial-map"></a>Möjliga fel i den rumsliga kartan

Fel i data för rumslig mappning finns i några kategorier:

- *Hål:* Verkliga ytor saknas i rumsliga mappningsdata.
- *Grafer:* Det finns ytor i de rumsliga mappningsdata som inte finns i den verkliga världen.
- *Maskhål:* HoloLens "förlorar" en del av den rumsliga kartan genom att tro att den finns i en annan del av kartan än den faktiskt är.
- *Bias:* Ytor i rumsliga mappningsdata justeras felaktigt med verkliga ytor, antingen push-in eller dras ut.

Om du ser något av dessa fel kan du använda [FeedbackHub för](hololens-feedback.md) att skicka feedback.

## <a name="security-and-storage-for-spatial-data"></a>Säkerhet och lagring för rumsliga data

Windows 10 version 1803 för Microsoft HoloLens och senare lagrar mappningsdata i en lokal databas (på enheten).

HoloLens kan inte komma åt kartdatabasen direkt, även när enheten är ansluten till en dator eller när du använder Utforskaren appen. När BitLocker är aktiverat HoloLens krypteras även lagrade kartdata tillsammans med hela volymen.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Ta bort kartdata och kända blanksteg från HoloLens

Det finns två alternativ för att ta bort kartdata **i Inställningar > System > Hologram**:

- Om du vill ta bort hologram i närheten väljer du **Ta bort hologram i närheten.** Det här kommandot rensar kartdata och fäst hologram för det aktuella utrymmet. Om du fortsätter att använda enheten i samma utrymme skapas och lagras ett helt nytt kartavsnitt som ersätter den borttagna informationen.

   > [!NOTE]
   > Hologram i närheten är hologram som är fästa inom samma kartavsnitt i det aktuella utrymmet.

   Du kan till exempel använda det här alternativet för att rensa arbetsrelaterade kartdata utan att påverka hemrelaterade kartdata.

- Om du vill ta bort alla hologram väljer du **Ta bort alla hologram.** Det här kommandot rensar alla kartdata som lagras på enheten samt alla ankare hologram. Du måste uttryckligen placera hologram. Du kommer inte att kunna identifiera hologrammen som placerats tidigare.

> [!NOTE]
> När du har tagit bort närliggande eller alla hologram börjar HoloLens att skanna och mappa det aktuella utrymmet.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi data i rumsliga kartor

HoloLens lagrar Wi-Fi egenskaper för att korrelera hologramplatser och kartavsnitt som lagras i den HoloLens databasen med kända utrymmen. Information om Wi-Fi egenskaper är inte tillgänglig för användare och skickas inte till Microsoft med hjälp av molnet eller med telemetri.

Så länge Wi-Fi är aktiverat korrelerar HoloLens kartdata med närliggande Wi-Fi åtkomstpunkter. Det finns ingen skillnad i beteendet om ett nätverk är anslutet eller bara har identifierats i närheten. Om Wi-Fi är inaktiverad HoloLens fortfarande utrymmet. Men HoloLens måste söka efter mer av kartdata i blankstegsdatabasen och kan behöva mer tid för att hitta hologram. Utan Wi-Fi information måste HoloLens jämföra aktiva genomsökningar med alla hologramankare och kartavsnitt som lagras på enheten för att hitta rätt del av kartan.

## <a name="related-topics"></a>Relaterade ämnen

- [Design av rumslig mappning](/windows/mixed-reality/spatial-mapping)
