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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036350"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Gör din HoloLens 2 redo att användas

Procedurerna nedan hjälper dig att konfigurera en HoloLens 2 för första gången.

## <a name="charge-your-hololens"></a>Debitera din HoloLens

Anslut strömkabeln till laddningsporten med hjälp av USB-C-kabeln (ingår). Anslut strömförsörjningen till ett elnät. Strömförsörjningen och USB-C-till-C-kabeln som följer med enheten är det bästa sättet att debitera HoloLens 2. Strömförsörjningen levererar 18 W ström (9V vid 2A). Med medföljande väggsett kan HoloLens 2 enheter ladda upp batteriet till full på mindre än 65 minuter när enheten är i vänteläge.

Debiteringshastigheten och hastigheten kan variera beroende på i vilken miljö enheten körs.

- När enheten laddas tänds batteriindikatorn för att ange den aktuella avgiftsnivån.  Det sista lampan tonas in och ut för att indikera aktiv debitering.
- När HoloLens är på visar batteriindikatorn batterinivån i steg.
- När bara ett av de fem lamporna är på är batterinivån under 20 procent.
- Om batterinivån är kritiskt låg och du försöker slå på enheten blinkar en lampa en kort stund och går sedan ut.

Fullständig [information om enhetsdeladd kan läsas här](hololens2-charging.md#charging-the-device) om mer information behövs. 

## <a name="adjust-fit"></a>Justera anpassning

Placera HoloLens 2 på huvudet. Om du har glasögon ska du lämna dem på.  Brow pad bör vara bra att känna dig bekväm med, och det bakre bandet ska stå i mitten av huvudet.

Om det behövs utökar du huvudbandet genom att slå på justeringshjulet och sedan släppa på omkostnaderna.

![HoloLens 2 anpassning och justeringar.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Koppla och koppla från overhead-ledningar

Overheadförsening krävs inte, men den kan göra HoloLens 2 mer bekväm under långa perioder av användning.

För att koppla från fronten av överlägget tar du bort den och drar den genom den indragbara slingan på brow pad. För att återansluta den, drar du ut loopen och drar tillbaka den igen.

Tryck på knappen under varje anslutningsflik för att koppla bort baksidan av overhead- och pull-kopplingen. Om du vill ansluta den igen, push-koppla tillbaka anslutningsflikarna till facken tills de klickar.

![koppla eller ta bort HoloLens 2 huvudhuvud.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Aktivera HoloLens 2

Om du vill aktivera HoloLens 2 trycker du på strömknappen.  Lysdioderna under strömknappen visar batterinivån.

> [!NOTE]
> Om du vill HoloLens 2 för första gången trycker du på och håller ned strömknappen i minst 4 sekunder efter att du har packat upp den. Nästa gång du startar HoloLens 2 startar den efter en kort tryckning på strömknappen.

### <a name="power-button-actions-for-different-power-transitions"></a>Strömknappsåtgärder för olika energiövergångar

| Gör så här: | Utför den här åtgärden | Det här HoloLens 2 |
| - | - | - |
| Så här aktiverar du | Tryck på en knapp. | Alla fem lamporna tänds och ändras sedan för att indikera batterinivån. Efter fyra sekunder spelas ett ljud upp. |
| För strömsparläge | Tryck på en knapp. | Alla fem lamporna tänds och tonas sedan bort en i taget. När lamporna har släcks spelas ett ljud upp och skärmen visar "Goodbye". |
| Att väcka från strömsparläge | Tryck på en knapp. | Alla fem lamporna tänds och ändras sedan för att indikera batterinivån. Ett ljud spelas upp direkt. |
| Så här stänger du av | Tryck och håll ned i 5 sekunder. |  Alla fem lamporna tänds och tonas sedan bort en i taget. När lamporna har släcks spelas ett ljud upp och skärmen visar "Goodbye". |
| Så här tvingar HoloLens att starta om om den inte svarar | Tryck och håll ned i 10 sekunder. | Alla fem lamporna tänds och tonas sedan bort en i taget. När lamporna har släckt. |

## <a name="hololens-behavior-reference"></a>HoloLens beteendereferens

Är du osäker på vad indikatorn HoloLens betyder? Vill du veta hur HoloLens beter sig vid debitering?  Här är lite hjälp!

### <a name="charging-behavior"></a>Debiteringsbeteende

| Enhetens tillstånd | Åtgärd | HoloLens 2 gör detta |
| - | - | - |
| OFF | Anslut USB-kabel | Enheten övergår till PÅ med indikatorbelysning som visar batterinivå och enheten börjar laddas.
| ON | Ta bort USB-kabel | Enheten slutar att ladda
| ON | Anslut USB-kabel | Enheten börjar ladda
| SÖMN | Anslut USB-kabel | Enheten börjar ladda
| SÖMN | Ta bort USB-kabel | Enheten slutar att ladda
| PÅ med USB-kabel ansluten | Stäng av enhet | Enheten övergår till PÅ med indikatorbelysning som visar batterinivå och enheten börjar laddas |

### <a name="lights-that-indicate-the-battery-level"></a>Lampor som indikerar batterinivån

| Antal lampor | Batterinivå |
| - | - |
| Fyra helljus, ett ljus som släcks in och ut | Mellan 100 % och 81 % (debiteras fullständigt) |
| Tre helljus, en ljuslyssning in och ut | Mellan 80 % och 61 % |
| Två helljus, en ljuslyssning in och ut | Mellan 60 % och 41 % |
| Ett fast ljus, ett ljust sken in och ut | Mellan 40 % och 21 % |
| En ljusning in och ut | Mellan 20 % och 5 % eller lägre (kritiskt batteri) |

### <a name="sleep-behavior"></a>Strömsparlägesbeteende

| Enhetens tillstånd | Åtgärd | HoloLens 2 gör detta |
| - | - | - |
| ON | Tryck på enkel strömknapp | Enheten övergår till SLEEP och stänger av alla indikatorbelysningar |
| ON | Ingen förflyttning på 3 minuter | Enheten övergår till SLEEP och inaktiverar alla indikatorbelysningar |
| SÖMN | Tryck på en strömknapp | Enheten övergår till PÅ och sätter på indikatorbelysning |

### <a name="lights-to-indicate-problems"></a>Lampor som indikerar problem

| När du gör detta | Lamporna gör detta | Det innebär att |
| - | - | - |
| Du trycker på strömknappen. | En lampa släcks fem gånger och stängs sedan av. | Den HoloLens batteri är kritiskt låg. Debitera din HoloLens. |
| Du trycker på strömknappen. | Alla fem lamporna blinkar fem gånger och stäng sedan av. |  HoloLens kan inte starta korrekt och är i ett feltillstånd. [Installera om operativsystemet för](hololens-recovery.md) att återställa enheten. |
| Du trycker på strömknappen. | 1:a, 3:e och 5:e lamporna blinkar kontinuerligt tillsammans. |  HoloLens kan ha ett maskinvarufel. Kontakta [supporten.](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb) |

## <a name="safety-and-comfort"></a>Säkerhet och bekvämlighet

### <a name="use-hololens-in-safe-surroundings"></a>Använda HoloLens i säkra miljöer

Använd dina HoloLens i ett säkert utrymme, utan hinder och utlösta hinder. Använd den inte när du behöver ett tydligt synfält eller inte kan ge dig fullständig uppmärksamhet, till exempel när du kör ett fordon eller utför andra potentiellt skadliga aktiviteter.

### <a name="stay-comfortable"></a>Håll dig bekväm

Håll dina första sessioner med HoloLens kort och var noga med att ta pauser. Om du upplever att du känner dig trygg ska du stanna upp och vila tills du känner dig bättre. Detta kan omfatta tillfälliga känslor av känslor, rörelseförlamning, känslor, disorientation, sjukdom, utmattning, ögonbelastning eller ögontorrhet.

Se [produktsäkerhetsvarningar och instruktioner.](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)

> [!div class="nextstepaction"]
> [Konfigurera din HoloLens 2](hololens2-start.md)
