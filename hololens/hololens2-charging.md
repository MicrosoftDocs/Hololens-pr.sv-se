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
# <a name="battery-and-charging"></a>Batteri och laddning

Den här sidan innehåller information om hur du laddar HoloLens 2 och använder externa batteripaket.

## <a name="included-charger"></a>Included Charger

Den ingår i HoloLens 2 ger upp till 9V @ 2A (18 W). När det är möjligt rekommenderar vi starkt att du debiterar med hjälp av den medföljande 50-500-500-500-100-100-1  

## <a name="specifications"></a>Specifikationer

HoloLens 2 kan debiteras av [USB-strömkällor](https://www.usb.org/usb-charger-pd) på upp till 27 watt. Om källan kan ange minst 10 Watts kan HoloLens-driftstiden utökas (eventuellt på obestämd tid för vissa arbetsbelastningar). 

> [!NOTE]
> Om du använder en USB-A till USB-C-laddningskabel begränsar du avgiften till 7,5 Watt. Drifttiden kommer fortfarande att utökas, men inte så länge som du använder USB-C till C.

När HoloLens är i vänteläge räcker 18 watt för att nå den maximala laddningstakten för det interna batteriet. När HoloLens används kan avgiftspriset minskas eftersom HoloLens prioriterar drift över debitering.

> [!IMPORTANT]
> Vi rekommenderar att HoloLens 2 debiteras till minst 5V/1,5A. 5V/1.5A bör inte användas. 

## <a name="external-battery-packs"></a>Externa batteripaket

Batteripaket som uppfyller specifikationerna ovan kan användas med HoloLens 2. Observera dock att vissa USB-C-batteripaket är anslutna och ger ström via samma USB-C-port. Det är viktigt att dessa batteripaket implementerar [TRY. SRC för](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) att säkerställa att de debiterar HoloLens i stället för att debitera från den. 

## <a name="managing-heat"></a>Hantera värme

Precis som med alla enheter genererar debitering av HoloLens värme. Ju snabbare avgiften är, desto mer värme genereras. Att starta en avgift på en lägre batterinivå genererar dessutom mer värme än att starta en laddning när batteriet mest är fullt. Kunder som behöver använda HoloLens under längre tidsperioder i heta miljöer kan använda följande metoder:

- Det är ok att ansluta HoloLens 2 till en extern strömkälla även när det interna batteriet är helt laddat.
- När ett externt batteri är slut fortsätter HoloLens att fungera med sitt interna batteri.    
- Om värme fortfarande är ett problem efter att du har följt stegen ovan bör du överväga att använda ett batteripaket som begränsar debiteringen till 1,5A. Observera att det här alternativet inte ger lika mycket drifttid eftersom det interna batteriet fortfarande tar slut långsamt.

## <a name="troubleshooting"></a>Felsökning


### <a name="hololens-charges-external-battery"></a>Externa HoloLens-avgifter
Om HoloLens 2 laddar ett externt batteri i stället för att debiteras av det, betyder det att batteriet inte implementerar [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Att byta till ett nyare batteripaket är det rekommenderade sättet att lösa det här problemet, men du kan också prova att byta till en USB-A-till-USB-C-kabel. Tänk på att detta begränsar debiteringshastigheten till 7,5 watt.
