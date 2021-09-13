---
title: Använda din röst för att HoloLens
description: Lär dig Cortana kan hjälpa dig att göra alla typer av saker på HoloLens enheter med mixad verklighet, inklusive röstkommandon, diktering och holograminteraktioner.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036278"
---
# <a name="use-your-voice-to-operate-hololens"></a>Använda din röst för att HoloLens

Du kan använda din röst för att göra nästan vad som helst på HoloLens, till exempel ta ett snabbt foto eller öppna en app. Många röstkommandon är inbyggda i HoloLens, medan andra är tillgängliga via Cortana.

Den här artikeln lär dig hur du HoloLens och din holografiska värld med din röst och med Cortana.

> [!NOTE]
> Tal stöds endast på [vissa språk.](hololens2-language-support.md) Talspråket baseras på Windows visningsspråk, inte tangentbordsspråket.  
>  
> Du kan kontrollera Windows visningsspråk genom att **välja Inställningar**  >  **Tid och**  >  **Språk.**

## <a name="built-in-voice-commands"></a>Inbyggda röstkommandon

Kom runt HoloLens snabbare med dessa grundläggande kommandon. För att kunna använda dessa måste du aktivera Tal under den första körningen av enheten eller i **Inställningar**  >  **Privacy**  >  **Speech**. Du kan alltid kontrollera om tal är aktiverat genom att titta på statusen överst i Start-menyn. För bästa resultat av taligenkänning använder HoloLens 2 Microsofts molnbaserade tjänster. Du kan dock använda Inställningar för att inaktivera den här funktionen. Det gör du genom att Inställningar av Taligenkänning **online.** När du har ändrat den här inställningen bearbetar HoloLens 2 endast röstdata lokalt för att identifiera kommandon och diktering, Cortana inte är tillgänglig.

### <a name="general-speech-commands"></a>Allmänna talkommandon

Använd dessa kommandon i Windows Mixed Reality för att komma runt snabbare. Vissa kommandon använder blickmarkören, som du tar fram genom att säga "select".

> [!NOTE]
> Handbilder stöds inte på HoloLens (första gen).

| Säg detta | Gör så här: |
| - | - |
| "Välj" | Säg "select" (välj) för att öppna blickmarkören. Sätt sedan huvudet för att placera markören på det du vill markera och säg "välj" igen. |
| "Gå till Start" |  Öppna Start-menyn |
| "Stäng"  | Stäng Start-menyn |
| Säg "Go to Start" (Gå till start) för att öppna snabbåtgärder-menyn och säg sedan "Mixed reality home".  | Lämna en avancerad app |
| "Dölj hand ray" /"Visa hand ray" | Dölj och visa hand ray |
| "Vad kan jag säga?"  | Se tillgängliga talkommandon |

Från och med version 19041.x HoloLens 2 kan du också använda följande kommandon:

| Säg detta | Gör så här: |
| - | - |
| "Starta om enheten" | Öppna en dialogdialog för att bekräfta att du vill starta om enheten. Du kan säga "Ja" för att starta om. |
| "Stäng av enhet" | Öppna en dialogdialog för att bekräfta att du vill stänga av enheten. Du kan säga "Ja" för att bekräfta. |
| "Ljusstyrka upp/ned" | Öka eller minska skärmens ljusstyrka med 10 %. |
| "Volym upp/ned" | Öka eller minska volymen med 10 %. |
| "Vad är min IP-adress" | Öppna en dialogdialog som visar enhetens aktuella IP-adress i det lokala nätverket. |
| "Ta en bild" | Ta ett foto med mixad verklighet av det du för närvarande ser. |
| "Ta en video" | Börja spela in en video med mixad verklighet. | 
| "Stoppa inspelning" | Stoppar den aktuella videoinspelningen av mixad verklighet om en sådan pågår. |

### <a name="hologram-commands"></a>Hologramkommandon

Om du vill använda dessa kommandon kan du titta på ett 3D-objekt, ett hologram eller ett appfönster.

| Säg detta | Gör så här: |
| - | - |
| "Större" | Gör den större |
| "Mindre" | Gör den mindre |
| "Face me" | Sätt den så att du ser dig |
| "Flytta det här" | Flytta den (följ din blick) |
| "Stäng" | Stäng den |
| "Följ mig" /"Sluta följa" | Få den att följa dig när du flyttar |

### <a name="see-it-say-it"></a>Se det, säg det

Många knappar och andra element HoloLens också svara på din röst– till exempel Följ **mig** och **Stäng** i appfältet eller **bakåtknappen** i Edge. Om du vill ta reda på om en knapp är röstaktiverad kan du vila blickmarkören **,** **pekmarkören** eller en **hand ray** på den en stund. Om knappen är röstaktiverad visas ett rösttips.

### <a name="dictation-mode"></a>Dikteringsläge

Är du inte så bra på att skriva? Växla till dikteringsläge när som helst när det holografiska tangentbordet är aktivt. Kom igång genom att välja mikrofonknappen eller säga "Starta diktering". Om du vill sluta diktera väljer du knappen igen eller säger "Sluta diktera". Om du vill ta bort det du nyss dikterade säger du "Ta bort det". 

> [!NOTE]
> Om du vill använda dikteringsläge måste du ha en Internetanslutning.

HoloLens använder explicit skiljetecken, vilket innebär att du säger namnet på skiljetecken som du vill använda. Du kan till exempel säga "Hej **kommatecken** vad har du för **frågetecken."**

Här är de skiljeteckensnyckelord som du kan använda:

- Punkt, kommatecken, frågetecken, utropstecken/utropstecken
- Ny rad/nytt stycke
- Semikolon, kolon
- Öppna citattecken, stäng offerter
- Hashtag, smiley/smiley face, frowny, winky
- Dollar, procent

Ibland kan det vara bra att stava ut saker som e-postadresser. Om du till exempel vill diktera skulle du säga example@outlook.com "E X A M P L E at outlook dot com".

## <a name="do-more-with-cortana"></a>Gör mer med Cortana

Cortana kan hjälpa dig att göra alla typer av saker på din HoloLens, men beroende på vilken version av Windows Holographic du använder kan funktionerna vara olika. Du kan lära dig mer om de uppdaterade funktionerna i den senaste versionen av Cortana här: Cortana i den kommande [Windows 10-versionen: fokuserar](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)på din produktivitet med förbättrad säkerhet och sekretess. 

![Hey Cortana!](images/cortana-on-hololens.png)

Här är några saker du kan prova att säga (kom ihåg att säga "Hej Cortana" först).

**Hej, Cortana...**

- Vad kan jag säga?
- Starta <*appnamn*>.
- Hur mycket är klockan?
- Visa mig de senaste NBA-poängen.
- Tell me a joke.

Om du använder *version 18362.x eller tidigare* kan du också använda följande kommandon:

**Hej, Cortana...**

- Öka volymen.
- Minska ljusstyrkan.
- Stäng av.
- Starta om.
- Gå och lägga sig.
- Mute.
- Flytta <*appnamn*> här (titta på den plats som du vill att appen ska flyttas till).
- Gå till Start.
- Ta en bild.
- Starta inspelningen. (Börjar spela in en video.)
- Stoppa inspelningen. (Stoppar inspelning av en video.)
- Hur mycket batteri har jag kvar?

Vissa Cortana funktioner som du är van vid från Windows på din dator eller telefon (till exempel påminnelser och meddelanden) stöds inte i Microsoft HoloLens och Cortana-upplevelsen kan variera från en region till en annan.

### <a name="turn-cortana-off"></a>Stäng Cortana av

Cortana är första gången du använder HoloLens när du aktiverar tal. Du kan inaktivera henne Cortana inställningarna. I listan **Alla appar** väljer du **Cortana**  >  **Inställningar**. Stäng sedan av Cortana kan ge dig förslag, idéer, påminnelser, aviseringar med mera.

Om Cortana inte svarar på "Hej Cortana" kontrollerar du att tal är aktiverat på Start och går till Cortana inställningar och kontrollerar att hon är på.
