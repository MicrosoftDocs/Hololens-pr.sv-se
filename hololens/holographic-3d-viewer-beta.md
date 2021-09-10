---
title: Använda 3D-visningsprogram Beta på HoloLens (första generationen)
description: Beskriver de typer av filer och funktioner som 3D-visningsprogram Beta på HoloLens (första generationen) stöder och hur du använder och felsöker appen.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428926"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Använda 3D-visningsprogram Beta på HoloLens (första generationen)

3D-visningsprogram Beta kan du visa 3D-modeller på HoloLens (första generationen). Du kan öppna  och visa .fbx-filer som stöds från Microsoft Edge, OneDrive och andra appar.

>[!NOTE]
>Den här artikeln gäller för den integrerande Unity **3D-visningsprogram Beta-appen,** som stöder .fbx-filer och endast är tillgänglig på HoloLens (första generationen). Den förinstallerade **appen 3D-visningsprogram** på HoloLens 2 har stöd för att öppna anpassade 3D-modeller i Mixed Reality (mer information finns i Översikt över tillgångskrav. [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)

>[!IMPORTANT]
>Även 3D-visningsprogram Beta kan finnas kvar i Microsoft Store för HoloLens (första generationen), är den inte längre i aktiv utveckling och stöds inte längre.

Om du har problem med att öppna en 3D-modell i 3D-visningsprogram Beta, eller om vissa funktioner i 3D-modellen inte stöds, kan du gå till [Innehållsspecifikationer som stöds](#supported-content-specifications) nedan.

Om du vill skapa eller optimera 3D-modeller för användning med 3D-visningsprogram Beta kan du se [Optimera 3D-modeller för 3D-visningsprogram Beta](#optimizing-3d-models-for-3d-viewer-beta) nedan.

Det finns två sätt att öppna en 3D-modell på HoloLens. Se [Visa FBX-filer på HoloLens](#viewing-fbx-files-on-hololens) nedan för mer information.

Om du har problem med att läsa de här ämnena kan du läsa [Felsökning](#troubleshooting) nedan.

## <a name="supported-content-specifications"></a>Innehållsspecifikationer som stöds

### <a name="file-format"></a>Filformat

- FBX-format
- Högsta FBX-version 2015.1.0

### <a name="file-size"></a>Filstorlek

- Minst 5 kB
- Maximalt 500 MB

### <a name="geometry"></a>Geometri

- Endast polygonala modeller. Inga indelningsytor eller NURB
- Högerhänt koordinatsystem
- Shear i transformeringsmatriser stöds inte

### <a name="textures"></a>Bakgrunder

- Strukturkartor måste bäddas in i FBX-filen
- Bildformat som stöds
  - JPEG- och PNG-bilder
  - BMP-bilder (24-bitars RGB true-color)
  - TGA-bilder (24-bitars RGB och 32-bitars RGBQ true-color)
- Maximal upplösning på 2 048 x 2 048
- Maximalt en mappning, en normal karta och en reflektionskubkarta per nät
- Alfakanal i sporadiska strukturer gör att bildpunkter tas bort om de är lägre än 50 %

### <a name="animation"></a>Animering

- Animering av skalning/rotation/översättning på enskilda objekt
- Skeletal (trederad) animering med hudning
  - Maximalt 4 påverkan per hörn

### <a name="materials"></a>Material

- Det finns stöd för materialen Sådd och Prems, med justerbara parametrar
- Materialegenskaper som stöds för Properties
  - Main Texture (RGB + Alpha Test)
  - Color (RGB)
  - Omgivande färg (RGB)
- Materialegenskaper som stöds för Prem
  - Main Texture (RGB + Alpha Test)
  - Color (RGB)
  - Omgivande färg (RGB)
  - Specular Color (RGB)
  - Storhet
  - Reflektionsförmåga
- Anpassat material stöds inte
- Maximalt ett material per nät
- Högst ett materialskikt
- Högst 8 material per fil

### <a name="file-and-model-limitations"></a>Fil- och modellbegränsningar

Det finns hårda gränser för storleken på filer, samt antalet modeller, hörn och nät som kan öppnas samtidigt i 3D-visningsprogram Beta:

- Maximal filstorlek på 500 MB per modell
- Hörn: 600 000 kombinerat på alla öppna modeller
- Nät: 1 600 kombinerat på alla öppna modeller
- Högst 40 modeller öppna samtidigt

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optimera 3D-modeller för 3D-visningsprogram Beta

### <a name="special-considerations"></a>Särskilda överväganden

- Undvik svarta material eller svarta områden i strukturkartor. Hologram av ljus, vilket gör HoloLens svart (avsaknad av ljus) som transparent.
- Innan du exporterar till FBX från ditt verktyg ska du se till att all geometri är synlig och olåst och att inga skikt som innehåller geometri är inaktiverade eller mallade. Synligheten respekteras inte.
- Undvik mycket stora översättningsförskjutningar mellan noder (till exempel 100 000 enheter). Detta kan göra att modellen jitter när den flyttas/skalas/roteras.

### <a name="performance-optimization"></a>Prestandaoptimering

Ha prestanda i åtanke när du skapar innehåll och verifierar i 3D-visningsprogram Beta-appen på HoloLens under redigeringsprocessen för bästa resultat. 3D-visningsprogram Beta återger innehåll i realtid och prestandan omfattas HoloLens maskinvarufunktioner.  

Det finns många variabler i en 3D-modell som kan påverka prestanda. 3D-visningsprogram Beta visar en varning om belastning om det finns fler än 150 000 hörn eller fler än 400 nät. Animeringar kan påverka prestanda för andra öppna modeller. Det finns också hårda gränser för det totala antalet modeller, hörn och nät som kan öppnas samtidigt i 3D-visningsprogram Beta (se Fil- och [modellbegränsningar).](#file-and-model-limitations)  

Om 3D-modellen inte fungerar bra på grund av modellens komplexitet bör du tänka på följande:

- Minska antalet polygoner
- Minska antalet snor i animerad animering
- Undvika självocklusion

Dubbelsidig rendering stöds i 3D-visningsprogram Beta, även om det är inaktiverat som standard av prestandaskäl. Detta kan aktiveras via knappen **Dubbelsidig** på **sidan** Information. Undvik behovet av dubbelsidig rendering i ditt innehåll för bästa prestanda.

### <a name="validating-your-3d-model"></a>Verifiera din 3D-modell

Verifiera din modell genom att öppna den 3D-visningsprogram Beta på HoloLens. Välj knappen **Information** för att visa modellens egenskaper och varningar om innehåll som inte stöds (om det finns).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Återgivning av 3D-modeller med verkliga dimensioner

Som standard visar 3D-visningsprogram Beta 3D-modeller i en bekväm storlek och position i förhållande till användaren. Men om det är viktigt att återge en 3D-modell med verkliga mått (till exempel vid utvärdering av modeller i ett rum) kan innehållsskaparen ange en flagga i filens metadata för att förhindra storleksändring av modellen av både programmet och användaren.

För att förhindra skalning av modellen lägger du till ett booleskt anpassat attribut till alla objekt i scenen med Microsoft_DisableScale och anger det till true. 3D-visningsprogram Beta respekterar sedan FbxSystemUnit-informationen som finns i FBX-filen. Skala in 3D-visningsprogram Beta är 1 mätare per FBX-enhet.

## <a name="viewing-fbx-files-on-hololens"></a>Visa FBX-filer på HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Öppna en FBX-fil från Microsoft Edge

FBX-filer kan öppnas direkt från en webbplats med hjälp Microsoft Edge på HoloLens.

1. I Microsoft Edge du till webbsidan som innehåller FBX-filen som du vill visa.
1. Välj filen för att ladda ned den.
1. När nedladdningen är klar väljer du knappen **Öppna** i Microsoft Edge för att öppna filen i 3D-visningsprogram Beta.

Den nedladdade filen kan nås och öppnas igen senare med hjälp av Nedladdningar i Microsoft Edge. Om du vill spara en 3D-modell och säkerställa fortsatt åtkomst laddar du ned filen på datorn och sparar den till ditt OneDrive konto. Filen kan sedan öppnas från appen OneDrive på HoloLens.

> [!NOTE]
> Vissa webbplatser med nedladdningsbara FBX-modeller tillhandahåller dem i komprimerat ZIP-format. 3D-visningsprogram Beta kan inte öppna ZIP-filer direkt. Använd i stället datorn för att extrahera FBX-filen och spara den på ditt OneDrive konto. Filen kan sedan öppnas från appen OneDrive på HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Öppna en FBX-fil från OneDrive

FBX-filer kan öppnas från OneDrive med hjälp av OneDrive på HoloLens. Kontrollera att du har installerat OneDrive med Microsoft Store på HoloLens och att du redan har laddat upp FBX-filen till OneDrive på datorn.

Väl i OneDrive kan FBX-filer öppnas på HoloLens med 3D-visningsprogram Beta på något av två sätt:

- Starta OneDrive på HoloLens och välj FBX-filen för att öppna den i 3D-visningsprogram Beta.
- Starta 3D-visningsprogram Beta, tryck i luften för att visa verktygsfältet och välj **Öppna fil.** OneDrive startar så att du kan välja en FBX-fil.

## <a name="troubleshooting"></a>Felsökning

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Jag ser en varning när jag öppnar en 3D-modell

En varning visas om du försöker öppna en 3D-modell som innehåller funktioner som inte stöds av 3D-visningsprogram Beta, eller om modellen är för komplex och prestanda kan påverkas. 3D-visningsprogram Beta läser fortfarande in 3D-modellen, men prestanda eller visuell återgivning kan komprometteras.

Mer information finns i [Innehållsspecifikationer som stöds](#supported-content-specifications) och [Optimera 3D-modeller för 3D-visningsprogram Beta.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Jag ser en varning och 3D-modellen läses inte in

Ett felmeddelande visas när 3D-visningsprogram Beta inte kan läsa in en 3D-modell på grund av komplexitet eller filstorlek, eller om FBX-filen är skadad eller ogiltig. Du får också ett felmeddelande om du har nått gränsen för det totala antalet modeller, hörn eller nät som kan vara öppna samtidigt.  

Mer information finns i [Innehållsspecifikationer som stöds och](#supported-content-specifications) [Fil- och modellbegränsningar.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Min 3D-modell läses in, men visas inte som förväntat

Om din 3D-modell inte ser ut som förväntat i 3D-visningsprogram Beta trycker du i luften för att visa verktygsfältet och väljer sedan **Information.** Aspekter av filen som inte stöds av 3D-visningsprogram Beta markeras som varningar.

Det vanligaste problemet du kan se är att det saknas struktur, troligen eftersom de inte är inbäddade i FBX-filen. I det här fallet visas modellen som vit. Det här problemet kan åtgärdas i skapandeprocessen genom att exportera från ditt skapandeverktyg till FBX med alternativet bädda in struktur valt.

Mer information finns i [Innehållsspecifikationer som stöds](#supported-content-specifications) och [Optimera 3D-modeller för 3D-visningsprogram Beta.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Jag upplever att prestandan sjunker när jag visar min 3D-modell

Prestanda vid inläsning och visning av en 3D-modell kan påverkas av modellens komplexitet, antalet modeller som öppnas samtidigt eller antalet modeller med aktiva animeringar.

Mer information finns i Optimera [3D-modeller för 3D-visningsprogram beta-](#optimizing-3d-models-for-3d-viewer-beta) och [fil- och modellbegränsningar.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>När jag öppnar en FBX-HoloLens öppnas den inte i 3D-visningsprogram Beta

3D-visningsprogram Beta associeras automatiskt med filnamnstillägget .fbx när det installeras.

Om du försöker öppna en FBX-fil och ser en dialogruta som leder dig till Microsoft Store har du för närvarande inte någon app som är associerad med filnamnstillägget .fbx på HoloLens.

Kontrollera att 3D-visningsprogram Beta är installerat. Om den inte är installerad laddar du ned den från Microsoft Store på HoloLens.

Om 3D-visningsprogram Beta redan är installerat startar du 3D-visningsprogram Beta och försöker sedan öppna filen igen. Om problemet kvarstår avinstallerar och installerar du om 3D-visningsprogram Beta. Detta associerar filnamnstillägget .fbx med 3D-visningsprogram Beta.

Om försök att öppna en FBX-fil öppnar en annan app än 3D-visningsprogram Beta, installerades förmodligen appen efter 3D-visningsprogram Beta och har tagit över associationen med filnamnstillägget .fbx. Om du föredrar 3D-visningsprogram Beta ska associeras med filnamnstillägget .fbx avinstallerar du och 3D-visningsprogram Beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Knappen Öppna fil i 3D-visningsprogram Beta startar inte en app

Knappen **Öppna fil** öppnar appen som är associerad med filväljarfunktionen på HoloLens. Om OneDrive har installerats **ska knappen Öppna** fil starta OneDrive. Men om det för närvarande inte finns någon app som är associerad med filväljarfunktionen installerad på HoloLens dirigeras du till Microsoft Store.

Om knappen **Öppna fil** startar en annan app än OneDrive, installerades förmodligen den appen efter OneDrive och har tagit över associationen med filväljarfunktionen. Om du föredrar OneDrive starta när du väljer **knappen** Öppna fil i 3D-visningsprogram Beta avinstallerar du och installerar OneDrive.

Om knappen **Öppna** fil inte är aktiv är det möjligt att du har nått gränsen för modeller som kan vara öppna i 3D-visningsprogram Beta på en gång. Om du har 40 modeller öppna i 3D-visningsprogram Beta måste du stänga några innan du kan öppna ytterligare modeller.

## <a name="additional-resources"></a>Ytterligare resurser

- [Supportforum](http://forums.hololens.com/categories/3d-viewer-beta) – endast för arkivering. Det här forumet är inte längre aktivt.
- [Meddelanden från tredje part](https://www.microsoft.com/{lang-locale}/legal/products)
