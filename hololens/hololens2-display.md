---
title: felsökning HoloLens 2-visning
description: Förväntningar för HoloLens 2 visas. Vägledning för att konfigurera visning för bästa avbildningskvalitet.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, kalibrering, bekvämlighet, visuella objekt, kvalitet, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036443"
---
# <a name="hololens-2-display-troubleshooting"></a>felsökning HoloLens 2-visning

## <a name="overview"></a>Översikt
Skärmen HoloLens 2 är en kombination av vågguider och ljusprojektorer. Användarna tittar igenom vågguiderna – objektiven i visorn – när de bär headset. De ljusprojektorer som finns i höljet ovanför glödlampan. HoloLens 2 använderlaserbelysning för att lysa upp skärmen.

## <a name="troubleshooting"></a>Felsökning

Vidta följande steg för att säkerställa högsta visuella kvalitet på hologram som visas i skärmarna:

* **Öka skärmens ljusstyrka.** Hologram ser bäst ut när skärmen är på den bästa nivån. När du använder HoloLens är ljusstyrkan på vänster sida av visor-programmet nära ditttempel.
* **Håll ögonen på visorn.** Swinga ner visor-programmet till den position som är närmast dina ögon.
* **Skift-visorn är nere.** Försök att flytta brow pad på din nos, vilket leder till att visor-programmet närmar sig din näsa.
* **[Köra ögonkalibrering.](hololens-calibration.md#calibrating-your-hololens-2)** Skärmen använder ditt interpupillary distance (IPD) och blick för att optimera bilder på skärmen. Om du inte kör ögonkalibrering kan bildkvaliteten bli sämre. Om du vill köra ögonkalibrering går du **till Inställningar**  >  **System**  >  **Kalibreringskörning**  >  **för ögonavsening.**
* **Kör kalibrering av visningsfärg**. På [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare kan  du välja en alternativ färgprofil för din HoloLens 2-skärm. Detta kan hjälpa färger att se mer exakta ut, särskilt på lägre nivåer av skärmens ljusstyrka. Kalibrering av visningsfärg  finns i Inställningar appen på sidan **System > Kalibrering.**

    > [!NOTE]
    > Eftersom den här inställningen sparar en ny färgprofil i den inbyggda programvaran för visning är det en inställning per enhet (och inte unik för varje användarkonto).

### <a name="how-to-use-display-color-calibration"></a>Så här använder du kalibrering av visningsfärg
1. Starta appen **Inställningar** och gå till **System > Kalibrering.**
1. Under **Kalibrering av visningsfärg** väljer du knappen **Kör kalibrering av visningsfärg.**
1. Kalibreringsupplevelsen för bildskärmsfärg startar och uppmuntrar dig att se till att ditt visor-program är på rätt plats.
1. När du har gått igenom dialogrutorna för instruktioner blir skärmen automatiskt nedtonad till 30 % ljusstyrka.
    > [!TIP]
    > Om du har problem med att se den nedtonade scenen i din miljö kan du manuellt justera ljusstyrkan på HoloLens 2 med hjälp av ljusstyrka-knapparna till vänster på enheten.
1. Välj knappar 1–6 för att omedelbart prova varje färgprofil och hitta en som ser bäst ut för dina ögon (detta innebär vanligtvis den profil som hjälper scenen att se mest neutral ut, med gråskalningsmönster och hudtoner som ser ut som förväntat.)

    ![Visa kalibreringsscen för färg.](images/color-cal-ui.png)
    
6. När du är nöjd med den valda profilen väljer du knappen **Spara & Avsluta**
1. Om du föredrar att inte göra ändringar väljer du **knappen Avbryt & Avsluta** så återställs dina ändringar

> [!TIP]
> Här är några användbara tips att tänka på när du använder inställningen för kalibrering av bildskärmsfärg:
> - Du kan köra kalibrering av bildskärmsfärg från Inställningar när du vill
> - Om någon på enheten tidigare har använt inställningen för att ändra färgprofiler visas datum/tid för den senaste ändringen på Inställningar sidan
> - När du kör kalibreringen av bildskärmsfärgen markeras den färgprofil som sparades tidigare och Profil 0 visas inte (eftersom Profil 0 representerar visningens ursprungliga färgprofil)
> - Om du vill återgå till visningens ursprungliga färgprofil kan du göra det från Inställningar (se hur du återställer [färgprofilen](#how-to-reset-color-profile))

### <a name="how-to-reset-color-profile"></a>Återställa färgprofilen

Om du är missnöjd med den anpassade färgprofilen som sparats HoloLens 2 kan du återställa enhetens ursprungliga färgprofil:
1. Starta appen **Inställningar** och gå till **System > Kalibrering.**
1. Under **kalibrering av visningsfärg** väljer du **knappen Återställ till standardfärgprofil.**
1. När dialogrutan öppnas väljer du **Starta om** om du är redo att starta om HoloLens 2 och tillämpa ändringarna.

### <a name="top-display-color-calibration-known-issues"></a>Kända problem med kalibrering av de främsta bildskärmsfärgerna

- På Inställningar visas statussträngen som anger när färgprofilen senast ändrades tills du läser in sidan på Inställningar 
    - **Lösning:** Välj Inställningar sida och välj sedan sidan Kalibrering igen.
- Om din HoloLens 2 för strömsparläge medan visningsfärgen körs återupptas den senare till mixed reality-hemmet och din skärms ljusstyrkanivå är fortfarande nedtonad.
- Du kan behöva prova att trycka på ljusstyrkan på vänster sida av enheten upp/ned några gånger innan de fungerar som förväntat.
- Lokaliseringen är inte klar för alla marknader

## <a name="faq"></a>Vanliga frågor

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Vilka mönster blinkar ibland i de nedre hörnen på skärmen?

Ibland visar HoloLens 2 olika mönster längst ned till vänster och höger på skärmen. Exemplen visas nedan (animerade GIF-filer). Det här mönstret är en del av normal drift av HoloLens 2-enheten för att kalibrera skärmen för optimal upplevelse.

![Dubbelriktat mönster.](./images/DAT-Biphase-Fiducial.gif) ![GEO-mönster](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Varför kan jag inte ta ett korrekt foto av min HoloLens 2-skärm?

Skärmen HoloLens 2 är utformad för att ses av det mänskliga ögat. Enheten har ett aktivt färgkorrigeringssystem som anpassar sig efter användarens ögon. Jämfört med det mänskliga ögat ser kamerorna miljöer på olika sätt och nedan är några faktorer som kan påverka eventuella inkonsekvenser mellan vad en kamera fångar och vad en användare ser.

* **Ögonposition.** Skärmen HoloLens 2 är utformad specifikt för användarens ögonposition. I HoloLens 2 används ögonspårningsteknik för att anpassa sig till användarens ögonposition. En kamera som är felpositionerad med några millimeter kan leda till att bilden förvrängs. Korrekt placering med en kamera är svårt och måste matcha den exakta platsen och ögonhjälpen som enheten utför färgkorrigering för.
* **Ögonförflyttning.** Skärmen anpassas efter användarens ögon för att justera färger. Vad som visas på skärmen kan variera beroende på om användaren tittar på mitten, kanten eller hörnet på skärmen. En enda bildinbildning kan i bästa fall bara visa hur skärmen ser ut för axeln som matchar en ögonriktning.
* **Asynlig visning.** Skärmen HoloLens 2 är utformad för att visas med båda ögonen. Hjärnan anpassar sig till att se två bilder och kombinerar dem. Bilder av endast en visning ignorerar informationen från den andra visningen.
* **Kameraexponeringstid.** Kamerans exponeringstid måste vara en exakt multipel av 1/120 sekund. Den HoloLens bildfrekvens är 120 Hz. På grund av sättet som HoloLens 2 ritar bilder räcker det inte heller att skapa en enda bildruta för att matcha en människas visuella upplevelse. Om enheten rör sig alls – till och med mikroflyttningar – projektiverar systemet om bilden på skärmen för att stabilisera hologrammen. Att samla in flera bildrutor samtidigt som HoloLens från att flyttas kräver vanligtvis en labbinstallation.
* **Kamerans storlek.** Kamerans storlek måste vara minst 3 mm för att kunna ta en korrekt bild. Mobiltelefonkameror med små slyor integrerar ljus från ett mindre område än det mänskliga ögat. Enheten tillämpar färgkorrigering för mönster som observerats av större ljus. Med små dräkter blir enhetlighetsmönstren bättre och förblir synliga trots att systemet har tillämpat färgkorrigeringar.
* **Kameraingångens elev.** Kamerans ingångselev bör vara minst 3 mm imeter för att få en korrekt bild. Annars fångar kameran några mönster med hög frekvens som inte är synliga för ögat. Positionen för ingångsande elev måste vara framför kameran och placerad vid ögonrelevensavståndet för att undvika att införa avvikelser och andra variationer i den avbildade bilden.
* **Kameraposition.** Kameror som uppfyller kraven för att visa HoloLens 2-skärmen är större och det är svårt att placera kameran tillräckligt nära HoloLens 2-skärmen för att observera den färg korrigerade bilden. Om kameran är på fel plats kan färgkorrigeringen påverka insamlingen av HoloLens 2 visas.
* **Bildkorrigering.** Vanliga digitalkameror och smartphonekameror använder en TRC-kurva (Tone Reproduce Curve) som ökar kontrasten och färgen för att ge ett bättre resultat. När den tillämpas på HoloLens 2-skärm förstärker den här tonkurvan icke-uniformiteter.

Det är dock fortfarande möjligt för specialiserade industriella kameror att samla in representativa bilder från HoloLens 2-skärmen. Tyvärr kommer smartphone-, konsument- och professionella kameror inte att ta bilder som matchar vad en användare ser på HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Vad gör ögonavbildning för att visa bildkvalitet?

Den HoloLens 2 visar aktivt färg korrigerar bilder baserat på användarens ögons position. [Ögonigenkänning](hololens-calibration.md) ger två viktiga indata: (1) användarens interpupillary distance (IPD) och (2) riktningen som varje ögon söker. Utan ögonavfärgning har systemet som standard en nominell ögonposition utan ögonförflyttning. Skillnaden mellan aktiv färgkorrigering och ingen korrigering beror på användarens själv. Användare som har samma IPD som systemstandarden ser till exempel färre förbättringar av färgkorrigeringen. Användare som har en mycket smalare eller bredare IPD än systemstandarden ser fler ändringar i visningsbilden.

Observera att en ny funktion i [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) automatiskt [identifierar ögonpositionen](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Vilka skillnader visas mellan HoloLens (första generationen) och HoloLens 2?

Bland de främsta begärandena som kunder gav Microsoft efter HoloLens 1 var (1) ökade visningsområdet och (2) ökade ljusstyrkan. Teknikutvecklingen gjorde det möjligt för Microsoft att skapa vågguider som dubblerat synfältets område och producerar ljusprojektorer med en skärm som är upp till tre gånger ljusare. Maskinvaran anger baslinjen för en trea kompromisser för bildvisningens kvalitet: (1) visningsfält, (2) ljusstyrka och (3) färgunialitet. Fortsatt teknikutveckling möjliggör förbättringar inom alla områden utan att offra ett annat område. Under tiden anger den befintliga tekniken de gränser som är tillgängliga för dessa kompromisser.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Vilka förbättringar kommer som kommer att förbättra HoloLens 2 avbildningskvalitet?

Vi har många pågående undersökningar för att förbättra avbildningskvaliteten, men följande områden förväntas komma i kommande uppdateringar:

* **Automatisk ögonposition.** Den här funktionen gör att procedurerna för ögonprocedurer kan ske i bakgrunden. Användarna behöver inte längre köra ögonavfärgning för att aktiv färgkorrigering ska fungera. Det fungerar i stället bara.
* **Förbättringar av färgkontens.** Den här uppdateringen fokuserar på färgvärden för mörkare färger (till exempel mörkgrå). Just nu får nedtonade färger en röd ton. Det här problemet inträffar också när hela skärmen är nedtonad – hela skärmen hämtar röda färger. Det här problemet beror på för mycket aktivitet i den röda färgkanalen för dessa mörkare färger. Vi har kännetecknat de här dimerfärgerna och arbetar med att erbjuda en procedur för kalibrering av användare. Resultatet blir mer färgnoggrannhet över ljusstyrkans spektrum. Det ändrar inte utseendet på vita bakgrunder med full ljusstyrka. Vi fortsätter att rekommendera användning av designmönster för mörkt läge i appar.
* **Läsläge.** Det är möjligt för apputvecklare att kompromissa med visningsfältet för att uppnå högre angular-upplösning. Apputvecklare kan åsidosätta projektionsmatrisen så att innehållet återges på skärmens ritningsupplösning. Den här funktionen resulterar i 30 % minskning av synfältet och en motsvarande ökning i angular-upplösning. Vi håller på att införa den här funktionen för [Mixed Reality Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). När det är tillgängligt fungerar läsläget på alla HoloLens 2 OS– det är inte beroende av en OS-uppdatering.

Uppdateringar av operativsystemet levereras automatiskt. Du kan också testa tidiga versioner av programvaruförbättringar via insiderförhandsvisningsprogrammet.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Vilken vägledning är tillgänglig för utvecklare för att tillämpa designprinciper för mörkt läge?

Användarna får bästa möjliga upplevelse när de undviker vita bakgrunder. Mörkt läge är en designprincip som används av appar för att använda svarta eller mörkfärgade bakgrunder. Systeminställningarna har som standard mörkt läge och kan justeras genom att gå till **Inställningar**  >    >  **systemfärg**.

Utvecklare rekommenderas att följa designvägledningen för mörkt läge:

* [Riktlinjer för utvecklardesign för HoloLens visas](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Rekommenderade teckenstorlekar](/windows/mixed-reality/typography#recommended-font-size)

När ett hologram kräver en vit bakgrund bör du hålla storleken på hologrammet mindre än det fullständiga visningsfältet på skärmen. Den här storleken gör att användarna kan placera hologrammet i mitten av skärmen.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Hur rensar du en HoloLens 2-skärm?

Använd mikrofiber för att rensa bort visor-programmet. För att rensa visor-programmet använder du 70 % isopropylsprent för att enkelt ta en miljö och sedan rensa visorn. Läs den fullständiga vägledningen i [HoloLens 2 cleaning FAQ](hololens2-maintenance.md).
