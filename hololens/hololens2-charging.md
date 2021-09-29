---
title: HoloLens 2 batteri och laddning
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
ms.openlocfilehash: a0ae0ccade01d7df520cd6cb142a9b51e63a2b05
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2021
ms.locfileid: "129163989"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 batteri och laddning

Den här sidan innehåller information om hur du HoloLens 2 och använder externa batteripaket.

## <a name="charging-the-device"></a>Ladda enheten

Använd kabeln [och USB Type-C-kabeln](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) som medkom med HoloLens 2 eftersom det är det bästa sättet att ladda enheten. Den borstning som ingår i HoloLens 2 ger upp till 9V @ 2A (18 W). Tillsammans med den medföljande väggväggen kan HoloLens 2 enheter ladda upp batteriet till full på mindre än 65 minuter när enheten är i vänteläge. Om tillbehören inte är tillgängliga kontrollerar du att de tillgängliga tillbehören har stöd för minst 15 W ström.

> [!NOTE]
> Om möjligt bör du undvika att använda en dator för att debitera enheten via USB, vilket är långsamt.

## <a name="checking-the-battery-charge-level"></a>Kontrollera batteriladdningsnivån
Om enheten är korrekt startad och körs finns det tre sätt att kontrollera batteriladdningsnivån:

- På huvudmenyn i HoloLens enhetens användargränssnitt.
- Visa lysdioden nära strömknappen (för en avgift på 40 procent bör du se minst två solida lysdioder).
    - När enheten laddas tänds batteriindikatorn för att ange den aktuella avgiftsnivån.  Det sista lampan tonas in och ut för att indikera aktiv laddning.
    - När HoloLens är på visar batteriindikatorn batterinivån i fem steg.
    - När bara en av de fem lamporna är på är batterinivån under 20 procent.
    - Om batterinivån är kritiskt låg och du försöker slå på enheten blinkar en lampa en kort stund och går sedan ut.
- På värddatorn öppnar du **Utforskaren** och letar efter din HoloLens 2-enhet till vänster under **Den här datorn.** Högerklicka på enheten och välj **Egenskaper.** En dialogruta visar batteriladdningsnivån.

   ![En HoloLens 2-egenskapsskärm visar batteriändringsnivå.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternativa debiteringsspecifikationer

HoloLens 2 kan debiteras av [USB-strömkällor](https://www.usb.org/usb-charger-pd) på upp till 27 Watt. Om källan kan ange minst 10 Watt HoloLens kan drifttiden utökas (eventuellt på obestämd tid för vissa arbetsbelastningar). 

> [!NOTE]
> Om du använder en USB-A till USB-C-laddningskabel begränsar du avgiften till 7,5 Watt. Drifttiden kommer fortfarande att utökas, men inte så länge som du använder USB-C till C.

När HoloLens är i vänteläge räcker 18 Watt för att nå den maximala laddningstakten för det interna batteriet. När HoloLens används kan avgiftssatsen minskas eftersom HoloLens prioriterar drift över debitering.

> [!IMPORTANT]
> Vi rekommenderar att du HoloLens 2 till minst 5V/1,5A. 5V/1.5A bör inte användas. 

### <a name="external-battery-packs"></a>Externa batteripaket

Batteripaket som uppfyller specifikationerna ovan kan användas med HoloLens 2. Observera dock att vissa USB-C-batteripaket är anslutna och ger ström via samma USB-C-port. Det är viktigt att dessa batteripaket implementerar [TRY. SRC för](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) att säkerställa att de HoloLens i stället för att debitera från den. 

### <a name="managing-heat"></a>Hantera värme

Precis som med alla enheter genererar HoloLens genererar värme. Ju snabbare avgiften är, desto mer värme genereras. Att starta en avgift på en lägre batterinivå genererar dessutom mer värme än att starta en laddning när batteriet mest är fullt. Kunder som behöver använda HoloLens under längre tidsperioder i heta miljöer kan använda följande metoder:

- Det är ok att ansluta HoloLens 2 till en extern strömkälla även när det interna batteriet är helt laddat.
- När ett externt batteri är slut fortsätter HoloLens att fungera på det interna batteriet.    
- Om värme fortfarande är ett problem efter att du har följt stegen ovan bör du överväga att använda ett batteripaket som begränsar debiteringen till 1,5A. Observera att det här alternativet inte ger lika mycket drifttid eftersom det interna batteriet fortfarande tar slut långsamt.

## <a name="troubleshooting"></a>Felsökning


### <a name="hololens-charges-external-battery"></a>HoloLens Externa avgifter för batteri
Om HoloLens 2 laddar ett externt batteri i stället för att laddas av det, betyder det att batteriet inte implementerar [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Att byta till ett nyare batteripaket är det rekommenderade sättet att lösa det här problemet, men du kan också prova att byta till en USB-A-till-USB-C-kabel. Tänk på att detta begränsar debiteringshastigheten till 7,5 watt.
