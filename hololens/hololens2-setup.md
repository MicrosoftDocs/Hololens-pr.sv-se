---
title: Förbereda en ny HoloLens 2
description: Lär dig att konfigurera och justera din HoloLens 2-enhet för första gången, inklusive hälso- och säkerhetstips och maskinvaruguider.
keywords: hololens, lights, fit, comfort, parts
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190420"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Gör din HoloLens 2 redo att användas

Procedurerna nedan hjälper dig att konfigurera en HoloLens 2 för första gången.

## <a name="charge-your-hololens"></a>Debitera din HoloLens

Anslut strömförsörjningen till laddningsporten med hjälp av USB-C-kabeln (ingår). Anslut strömförsörjningen till ett elaggregat. Strömförsörjningen och USB-C-till-C-kabeln som levereras med enheten är det bästa sättet att debitera din HoloLens 2. Nätaggregatet levererar 18 W ström (9V vid 2A). Med medföljande väggutrustning kan HoloLens 2 enheter ladda upp batteriet till full på mindre än 65 minuter när enheten är i vänteläge.

Debiteringshastigheten och hastigheten kan variera beroende på i vilken miljö enheten körs.

- När enheten laddas tänds batteriindikatorn för att ange den aktuella avgiftsnivån.  Det sista lampan tonas in och ut för att indikera aktiv laddning.
- När HoloLens är på visar batteriindikatorn batterinivån i steg.
- När bara en av de fem lamporna är på är batterinivån under 20 procent.
- Om batterinivån är kritiskt låg och du försöker slå på enheten blinkar en lampa en kort stund och går sedan ut.

Fullständig [information om enhetsladdning kan läsas här](hololens2-charging.md#charging-the-device) om mer information behövs. 

## <a name="adjust-fit"></a>Justera anpassning

Placera HoloLens 2 på huvudet. Om du har glasögon ska du lämna dem på.  Brow pad bör vara bra för din andning och det bakre bandet bör finnas i mitten av huvudet.

Om det behövs utökar du huvudbandet genom att rotera justeringshjulet och sedan släppa på overhead-hjulet.

![HoloLens 2 anpassning och justeringar.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Koppla och koppla från overhead-ledningar

Overhead-et krävs inte, men det kan göra att HoloLens 2 blir bekvämare under långa perioder.

Koppla bort den främre delen av överlägget genom att ta bort den och dra den genom den indragbara slingan på brow pad. För att återansluta den, drar du ut loopen och drar tillbaka bandet.

Om du vill koppla från baksidan av overhead-et trycker du på knappen under varje anslutningsflik och drar i rätt tid. Om du vill återansluta den, push-koppla tillbaka anslutningsflikarna till facken tills de klickar.

![koppla eller ta bort HoloLens 2-huvudet.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Aktivera HoloLens 2

Om du vill aktivera HoloLens 2 trycker du på strömknappen.  Lysdioderna under strömknappen visar batterinivån.

> [!NOTE]
> Om du vill HoloLens 2 för första gången trycker du på och håller ned strömknappen i minst 4 sekunder för att aktivera den efter att du har avmarkerat den. Nästa gång du startar HoloLens 2 startar den efter en kort tryckning på strömknappen.

### <a name="power-button-actions-for-different-power-transitions"></a>Strömknappsåtgärder för olika energiövergångar

| Gör så här: | Utför den här åtgärden | Det HoloLens 2 gör detta |
| - | - | - |
| Så här aktiverar du | Tryck på en knapp. | Alla fem lamporna tänds och ändras sedan för att indikera batterinivån. Efter fyra sekunder spelas ett ljud upp. |
| För strömsparläge | Tryck på en knapp. | Alla fem lamporna tänds och tonas sedan bort en i taget. När lamporna har släcks spelas ett ljud upp och skärmen visar "Hej då". |
| Att väcka från strömsparläge | Tryck på en knapp. | Alla fem lamporna tänds och ändras sedan för att indikera batterinivån. Ett ljud spelas upp direkt. |
| Så här stänger du av | Tryck och håll ned i 5 sekunder. |  Alla fem lamporna tänds och tonas sedan bort en i taget. När lamporna har släcks spelas ett ljud upp och skärmen visar "Hej då". |
| Så här tvingar HoloLens att starta om om den inte svarar | Tryck och håll ned i 10 sekunder. | Alla fem lamporna tänds och tonas sedan bort en i taget. När lamporna har släcks. |

## <a name="hololens-behavior-reference"></a>HoloLens beteendereferens

Är du osäker på vad indikatorn på HoloLens betyder? Vill du veta hur HoloLens bör bete sig vid debitering?  Här är lite hjälp!

### <a name="charging-behavior"></a>Debiteringsbeteende

| Enhetens tillstånd | Åtgärd | HoloLens 2 gör detta |
| - | - | - |
| OFF | Anslut USB-kabel | Enheten övergår till PÅ med indikatorbelysning som visar batterinivå och enheten börjar laddas.
| ON | Ta bort USB-kabel | Enheten slutar att laddas
| ON | Anslut USB-kabel | Enheten börjar laddas
| SÖMN | Anslut USB-kabel | Enheten börjar laddas
| SÖMN | Ta bort USB-kabel | Enheten slutar att laddas
| PÅ med USB-kabel ansluten | Stäng av enhet | Enheten övergår till PÅ med indikatorbelysning som visar batterinivå och enheten börjar laddas |

### <a name="lights-that-indicate-the-battery-level"></a>Lampor som indikerar batterinivån

| Antal lampor | Batterinivå |
| - | - |
| Fyra helljus, ett ljus som släcks och släcks | Mellan 100 % och 81 % (fullständigt debiterat) |
| Tre helljus, ett ljus som släcks och släcks | Mellan 80 % och 61 % |
| Två solid lights, en ljus fading in och ut | Mellan 60 % och 41 % |
| Ett fast ljus, ett ljus som tonar in och ut | Mellan 40 % och 21 % |
| En ljusning in och ut | Mellan 20 % och 5 % eller lägre (kritiskt batteri) |

### <a name="sleep-behavior"></a>Vilolägesbeteende

| Enhetens tillstånd | Åtgärd | HoloLens 2 gör detta |
| - | - | - |
| ON | Tryck på enkel strömknapp | Enheten övergår till SLEEP och inaktiverar alla indikatorbelysningar |
| ON | Ingen rörelse på 3 minuter | Enheten övergår till SLEEP och inaktiverar alla indikatorbelysningar |
| SÖMN | Enkel strömknapp Tryck på | Enheten övergår till PÅ och sätter på indikatorbelysning |

### <a name="lights-to-indicate-problems"></a>Lampor som indikerar problem

| När du gör detta | Lamporna gör detta | Det innebär att |
| - | - | - |
| Du trycker på strömknappen. | En lampa är fem gånger och stängs sedan av. | Den HoloLens är extremt låg. Debitera din HoloLens. |
| Du trycker på strömknappen. | Alla fem lamporna blinkar fem gånger och stäng sedan av. |  HoloLens startar inte korrekt och är i ett feltillstånd. [Installera om operativsystemet](hololens-recovery.md) för att återställa enheten. |
| Du trycker på strömknappen. | 1:a, 3:e och 5:e lamporna blinkar tillsammans kontinuerligt. |  HoloLens kan ha ett maskinvarufel. Kontakta [supporten.](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb) |

## <a name="safety-and-comfort"></a>Säkerhet och bekvämlighet

### <a name="use-hololens-in-safe-surroundings"></a>Använda HoloLens i säkra miljöer

Använd dina HoloLens i ett säkert utrymme, utan hinder och utlösta hinder. Använd den inte när du behöver ett tydligt synfält eller inte kan ge dig fullständig uppmärksamhet, till exempel när du använder ett fordon eller utför andra potentiellt farliga aktiviteter.

### <a name="stay-comfortable"></a>Håll dig bekväm

Håll dina första sessioner med HoloLens kort och var noga med att ta pauser. Om du upplever att du känner dig trygg ska du stanna upp och vila tills du känner dig bättre. Detta kan omfatta tillfälliga känslor av känslor, rörelsegrop, känslor, desorientering, känslor, förlamning, ögonbelastning eller ögontorrhet.

Se [produktsäkerhetsvarningar och anvisningar.](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)

> [!div class="nextstepaction"]
> [Konfigurera din HoloLens 2](hololens2-start.md)
