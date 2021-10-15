---
title: Uppdatera HoloLens 2
description: Lär dig hur du kontrollerar HoloLens versionsnummer, håller dig uppdaterad med enhetsuppdateringar, ansluter till Insiders-programmet och återställ uppdateringar.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034271"
---
# <a name="update-hololens-2"></a>Uppdatera HoloLens 2

## <a name="overview"></a>Översikt

Vi arbetar alltid med nya funktioner, felkorrigeringar och säkerhetsuppdateringar. Du meddelas när de här uppdateringarna är klara.

Baserat på dina inställningar kommer HoloLens automatiskt att ladda ned och installera systemuppdateringar när den är ansluten till ström, ansluten till Internet och även i vänteläge.

Se till att HoloLens alltid uppdateras genom att lämna den ansluten med den ström som medkom med den. Du vill också att HoloLens är ansluten till Internet. På så sätt hämtas och installeras systemuppdateringar automatiskt. 

Med Windows Update-tjänsten styr du flera aspekter av uppdateringsprocessen, till exempel vilka enheter som får vilka uppdateringar vid vilken tidpunkt. Den här kontrollen är användbar eftersom du kan distribuera uppdateringar till en delmängd HoloLens enheter för testning. Distribuera sedan uppdateringar till de återstående. Eller så kan du definiera olika uppdateringsscheman för olika typer av uppdateringar.

## <a name="types-of-updates"></a>Typer av uppdateringar

Du HoloLens hantera två typer av uppdateringar automatiskt.

- Funktionsuppdateringar: släpps två gånger per år.
- Kvalitetsuppdateringar: innehåller kritiska säkerhetsuppdateringar. De släpps varje månad eller efter behov.

Använd **Uppdatera** / **AllowAutoUpdate** för att hantera genomsökning, hämtning och installation av uppdateringar. 

## <a name="scheduling-updates"></a>Schemaläggningsuppdateringar

Du kan också ange ett uppdateringsschema. Det kan ske en viss dag, eller varje dag, vid en viss tidpunkt. Till exempel kl. 17.00 eller utanför aktiva timmar.

Slutligen några ord om hur du planerar din uppdateringsstrategi. Vi stöder upp skjuta upp uppdateringar, så att du kan bestämma hur lång tid du ska vänta efter att Microsoft har släppt en uppdatering för att installera uppdateringen på enheter.

Ibland vill ett företag prova alla nya funktioner först för att se till att allt fungerar, och de är bekanta med de nya uppdateringarna så att supportteamet är förberett. När de har bekräftat att allt är bra distribuerar de uppdateringarna till hela företaget. Genom att associera delmängder av dina enheter med olika upplåsningsprinciper, så kallade uppdateringsringar, kan du samordna en strategi för uppdateringsutgivning för din organisation.

## <a name="hololens-update-tools"></a>HoloLens uppdateringsverktyg

I det här avsnittet får du HoloLens verktyg för:

- söka efter uppdateringar
- uppdatera HoloLens
- visa din aktuella operativsystemversion (build-nummer)
- gå tillbaka till en äldre uppdatering

### <a name="check-for-updates-and-manually-update"></a>Söka efter uppdateringar och uppdatera manuellt

Du kan söka efter uppdateringar när som helst i inställningarna.  Så här ser du tillgängliga uppdateringar och söker efter nya uppdateringar:

1. Öppna appen **Inställningar**.
1. Gå till **Update & Security** Windows  >  **Update**.
1. Välj **Sök efter uppdateringar**.

Om en uppdatering är tillgänglig börjar den ladda ned den nya versionen. När nedladdningen är klar väljer du knappen **Starta om nu** för att utlösa installationen. Om enheten är lägre än 40 % och den inte är ansluten kommer omstarten inte att starta om installationen av uppdateringen.

När HoloLens installerar uppdateringen visas snurrande kugghjul och en förloppsindikator. Stäng inte av HoloLens under den här tiden. Den startas om automatiskt när installationen är klar.

HoloLens en uppdatering i taget.  Om din HoloLens är mer än en version bakom den senaste kan du behöva gå igenom uppdateringsprocessen flera gånger för att få den helt uppdaterad.

### <a name="check-your-operating-system-version-build-number"></a>Kontrollera operativsystemversionen (build-nummer)

Du kan verifiera systemversionsnumret (build-nummer) genom **att Inställningar** och välja System About   >  **(System om).**

### <a name="go-back-to-a-previous-version"></a>Gå tillbaka till en tidigare version

I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens programvara. De rekommenderade stegen är:

1. Kontakta supporten för att se om de kan åtgärda problemet.
    1. Se till **att Valfri** **eller Fullständig** telemetri är aktiverat – detta gör buggen mer användbar och enklare för tekniker att diagnostisera.
    1. I [Filfeedback](hololens-feedback.md) ska du vara så beskrivande som möjligt. Anteckna rubriken eller använd delningsfunktionen så att du kan dela din bugg med supporten.
    1. Kontakta [supporten.](https://aka.ms/hlsupport) Om problemet måste lösas genom att gå tillbaka till en tidigare version kan de tillhandahålla FFU för att flasha enheten.

1. Om det inte fungerar [omstreckar du ditt HoloLens 2 med Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.

Om du vill fortsätta använda den installerade versionen kan du även pausa uppdateringar [manuellt.](hololens-updates.md#pause-updates-via-device) Detta ger teknikteamet tid att åtgärda problemet.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program på HoloLens

Vill du se de senaste funktionerna i HoloLens?  I så fall ansluter du till Windows Insider Program; du får tillgång till förhandsversioner av HoloLens programuppdateringar innan de blir tillgängliga för allmänheten.

[Hämta Windows Insider-förhandsgranskning för Microsoft HoloLens](hololens-insider.md).