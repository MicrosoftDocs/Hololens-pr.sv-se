---
title: Uppdatera HoloLens 2
description: Lär dig hur du kontrollerar HoloLens versionsnummer, håller dig uppdaterad med enhetsuppdateringar, ansluter till Insiders-programmet och återställ uppdateringar.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427342"
---
# <a name="update-hololens-2"></a>Uppdatera HoloLens 2

## <a name="overview"></a>Översikt

Vi arbetar alltid med nya funktioner, felkorrigeringar och säkerhetsuppdateringar. Du meddelas när de här uppdateringarna är klara.

Baserat på dina önskemål kommer HoloLens automatiskt att ladda ned och installera systemuppdateringar när den är ansluten till ström, ansluten till Internet och även i vänteläge.

Se till att HoloLens alltid är uppdaterad genom att lämna den ansluten med den ström som medkom med den. Du vill också att HoloLens ska vara ansluten till Internet. På så sätt hämtas och installeras systemuppdateringar automatiskt. 

Med Windows Update-tjänsten styr du flera aspekter av uppdateringsprocessen, till exempel vilka enheter som får vilka uppdateringar vid vilken tidpunkt. Den här kontrollen är användbar eftersom du kan distribuera uppdateringar till en delmängd HoloLens enheter för testning. Distribuera sedan uppdateringar till de återstående uppdateringarna. Eller så kan du definiera olika uppdateringsscheman för olika typer av uppdateringar.

## <a name="types-of-updates"></a>Typer av uppdateringar

Du HoloLens hantera två typer av uppdateringar automatiskt. 

- Funktionsuppdateringar: släpps två gånger per år.
- Kvalitetsuppdateringar: innehåller viktiga säkerhetsuppdateringar. De släpps varje månad eller efter behov.

Använd **Uppdatera** / **AllowAutoUpdate** för att hantera genomsökning, nedladdning och installation av uppdateringar. 

## <a name="scheduling-updates"></a>Schemaläggning av uppdateringar

Du kan också ange ett uppdateringsschema. Det kan vara en viss dag, eller varje dag, vid en viss tidpunkt. Till exempel kl. 17:00 eller utanför aktiva timmar.

Slutligen några ord om hur du planerar din uppdateringsstrategi. Vi stöder upp skjuta upp uppdateringar. Därför kan du bestämma hur lång tid det tar att vänta efter att Microsoft har släppt en uppdatering för att installera uppdateringen på enheter.

Ibland gillar ett företag att prova alla nya funktioner först för att se till att allt fungerar, och de är bekanta med de nya uppdateringarna så att supportteamet är förberedda. När de har bekräftat att allt är bra distribuerar de uppdateringarna till hela företaget. Genom att associera delmängder av dina enheter med olika upplåsningsprinciper, så kallade uppdateringsringar, kan du samordna en strategi för uppdateringsutrullning för din organisation.

## <a name="hololens-update-tools"></a>HoloLens uppdateringsverktyg

I det här avsnittet får du HoloLens verktyg för:

- söka efter uppdateringar
- uppdatera HoloLens
- visa din aktuella operativsystemversion (build-nummer)
- att gå tillbaka till en äldre uppdatering

### <a name="check-for-updates-and-manually-update"></a>Sök efter uppdateringar och uppdatera manuellt

Du kan söka efter uppdateringar när som helst i inställningarna.  Så här ser du tillgängliga uppdateringar och söker efter nya uppdateringar:

1. Öppna appen **Inställningar**.
1. Gå till **Uppdatera & Security** Windows  >  **Update**.
1. Välj **Sök efter uppdateringar**.

Om en uppdatering är tillgänglig börjar den ladda ned den nya versionen. När nedladdningen är klar väljer du knappen **Starta om nu** för att utlösa installationen. Om enheten är lägre än 40 % och den inte är ansluten kommer omstarten inte att starta om installationen av uppdateringen.

När HoloLens installerar uppdateringen visas snurrande kugghjul och en förloppsindikator. Stäng inte av HoloLens under den här tiden. Den startas om automatiskt när installationen är klar.

HoloLens en uppdatering i taget.  Om din HoloLens är mer än en version bakom den senaste, kan du behöva gå igenom uppdateringsprocessen flera gånger för att få den helt uppdaterad.

### <a name="check-your-operating-system-version-build-number"></a>Kontrollera din version av operativsystemet (build-nummer)

Du kan verifiera systemversionsnumret (versionsnumret) genom att **öppna Inställningar** och välja System About   >  **(System Om).**

### <a name="go-back-to-a-previous-version"></a>Gå tillbaka till en tidigare version

I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens programvara. De rekommenderade stegen är:

1. Kontakta supporten för att se om de kan åtgärda problemet.
    1. Se till **att Valfri** **eller Fullständig** telemetri är aktiverat – detta gör buggen mer användbar och enklare för tekniker att diagnostisera.
    1. [File Feedback är](hololens-feedback.md) så beskrivande som möjligt. Anteckna rubriken eller använd delningsfunktionen så att du kan dela din bugg med supporten.
    1. Kontakta [supporten.](https://aka.ms/hlsupport) Om problemet måste lösas genom att gå tillbaka till en tidigare version kan de tillhandahålla FFU för att flasha enheten.

1. Om det inte fungerar återställer eller [omstreckar du HoloLens 2 med Advanced Recovery Companion](hololens-recovery.md).
    1. På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.
    1. Kontrollera att du inte har några telefoner eller enheter Windows anslutna till datorn.
    1. Välj vilken version du vill flasha till:
        1. Du kan ladda ned [den senaste versionen HoloLens 2.](https://aka.ms/hololens2download)
        1. Du kan använda standardbygget som ARC är värd för. (Om du väljer det här alternativet hoppar du över nästa steg.)
        1. Du kan använda ett byggstöd som du har.
    1. När du är klar med dessa nedladdningar öppnar **du Utforskaren**  >  **Hämtningsbara filer.** Högerklicka på den komprimerade mappen som du laddade ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.
    1. Anslut din HoloLens datorn med hjälp av en USB-A-till-USB-C-kabel. (Även om du har använt andra kablar för att ansluta HoloLens fungerar den här bäst.)
    1. Advanced Recovery Companion identifierar automatiskt HoloLens. Välj **Microsoft HoloLens** panelen.
    1. På nästa skärm väljer du **Manuellt paketval** och väljer sedan installationsfilen som finns i mappen som du packade upp i steg 4. (Leta efter en fil med `.ffu` tillägget.)
    1. Välj **Installera programvara** och följ instruktionerna.

> [!NOTE]
> När du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.

Om du vill fortsätta att använda den installerade versionen kan du även pausa uppdateringar [manuellt.](hololens-updates.md#pause-updates-via-device) Detta ger teknikteamet tid att åtgärda problemet.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program på HoloLens

Vill du se de senaste funktionerna i HoloLens?  I så fall ansluter du till Windows Insider Program; du får åtkomst till förhandsversioner av HoloLens programuppdateringar innan de blir tillgängliga för allmänheten.

[Hämta Windows Insider-förhandsgranskning för Microsoft HoloLens](hololens-insider.md).