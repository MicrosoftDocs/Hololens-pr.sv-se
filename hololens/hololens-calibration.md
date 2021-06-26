---
title: Förbättra visuell kvalitet och bekvämlighet
description: Lär dig hur du kalibrerar interpupillary distance (IPD) för att förbättra kvaliteten på dina visuella objekt på HoloLens-enheter.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: kalibrering, bekvämlighet, visuella objekt, kvalitet, ipd, HoloLens, Windows Mixed Reality, VR-headset
ms.openlocfilehash: 62d83aa5c6032d15b26fbc7938859bdaf74151f4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924153"
---
# <a name="improve-visual-quality-and-comfort"></a>Förbättra visuell kvalitet och bekvämlighet

Både HoloLens 2 och HoloLens (första generationen) fungerar bättre när de kalibreras mot dina unika ögon.

Båda enheterna måste kalibreras för bästa möjliga hologramvisning, men de använder olika kalibreringstekniker och tekniker.  Hoppa till [HoloLens 2-kalibrering](#calibrating-your-hololens-2) [eller HoloLens(1:a gen) kalibrering](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>Kalibrera hololens 2

HoloLens 2 använder ögonspårningsteknik för att förbättra upplevelsen av att se och interagera med den virtuella miljön. Genom att kalibrera HoloLens 2 ser du till att den kan spåra dina ögon (och ögonen på alla andra som använder enheten). Det hjälper också med användarkomfort, hologramjustering och handspårning. Efter kalibreringen visas hologram korrekt även när visor-programmet skiftar på huvudet.

HoloLens 2 uppmanar en användare att kalibrera enheten under följande omständigheter:

- Användaren använder enheten för första gången
- Användaren valde tidigare bort kalibreringsprocessen
- Kalibreringsprocessen lyckades inte den senaste gången användaren använde enheten
- Användaren har tagit bort sina kalibreringsprofiler
- Enheten tas bort och sätts på igen och alla ovanstående omständigheter gäller 


![Kalibreringsuppmaning för justering till ögon.](./images/07-et-adjust-for-your-eyes.png)

Under den här processen tittar du på en uppsättning mål (gems). Det går bra om du blinkar under kalibreringen, men försök att fokusera på gemsarna i stället för andra objekt i rummet.  Genom att fokusera på gems kan HoloLens lära sig om din ögonposition för att återge din holografiska värld.

![Kalibreringsuppmaning som uppmanar användaren att hålla huvudet still och följa punkterna med ögonen.](./images/07-et-hold-head-still.png)

![Kalibreringsuppmaning med gem-exempel.](./images/08-et-gems.png)

![Justering av kalibreringsuppmaning.](./images/09-et-adjusting.png)

Om kalibreringen lyckades visas en skärm med lyckat resultat.  Om inte, läs mer om [att diagnostisera kalibreringsfel.](hololens2-display.md#troubleshooting)

![Kalibreringsuppmaning lyckades.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Kalibrering vid delning av en enhet eller session

Flera användare kan dela en HoloLens 2-enhet utan att varje person behöver gå igenom enhetskonfigurationen. När en ny användare sätter enheten på huvudet för första gången uppmanar HoloLens 2 automatiskt användaren att kalibrera visuella objekt. När en användare som tidigare har kalibrerat visuella objekt placerar enheten på huvudet justeras skärmen sömlöst för kvalitet och en bekväm visningsupplevelse.  

### <a name="manually-starting-the-calibration-process"></a>Starta kalibreringsprocessen manuellt

1. Använd startgesten för att öppna [ **Start-menyn**](hololens2-basic-usage.md#start-gesture).
1. Om appen Inställningar inte är fäst på **Start väljer** du **Alla appar.**
1. Välj **Inställningar** och välj sedan System **Kalibrering av**  >  **ögonavseningar**  >    >  **Run eye kalibrering.**

   ![Inställningsappen som visar alternativet Run eye-kalibrering](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Stöd för automatisk ögonposition

I HoloLens 2 möjliggör ögonpositioner korrekt hologramplacering, bekväm visningsupplevelse och förbättrad visningskvalitet. Ögonpositioner beräknas internt som en del av ögonspårningsberäkningen. Detta kräver dock att varje användare går igenom kalibrering av ögonspårning, även om upplevelsen kanske inte kräver synindata.

**Auto Eye Position (AEP)** möjliggör dessa scenarier med ett interaktionsfritt sätt att beräkna ögonpositioner för användaren. Automatisk ögonposition börjar arbeta i bakgrunden automatiskt från den tidpunkt då användaren sätter på enheten. Om användaren inte har en tidigare kalibrering av ögonspårning börjar Auto Eye Position tillhandahålla användarens ögonpositioner till visningssystemet efter en bearbetningstid på 20–30 sekunder. Användardata bevaras inte på enheten och den här processen upprepas om användaren tar bort och sätter på enheten igen eller om enheten startas om eller aktiveras från strömsparläge.

Det finns några systembeteendeändringar med funktionen För automatisk ögonposition när en okalibrerad användare placerar på enheten. I det här sammanhanget refererar en ocalibrerad användare till någon som inte har gått igenom processen för ögonspårningsavbildning på enheten tidigare.

| Aktivt program | Tidigare beteende | Beteende från Windows Holographic, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Icke-blickaktiverad app eller Holographic Shell |Dialogrutan med kalibrering av ögonspårning visas. | Ingen uppmaning visas. |
| Blickaktiverad app | Dialogrutan med kalibrering av ögonspårning visas. | Mätningsuppmaning för ögonspårning visas bara när programmet kommer åt blickströmmen. |

Om användaren övergår från ett icke-blickaktiverad program till ett program som använder blickdata visas kalibreringsuppmaning. 

Alla andra systembeteenden liknar när den aktuella användaren inte har en aktiv kalibrering av ögonspårning. Startgesten med en hand aktiveras till exempel inte. Det kommer inte att ske några ändringar i Out-Of-Box-Experience för den inledande installationen.

För upplevelser som kräver ögonögondata eller exakt hologrampositionering rekommenderar vi att okalibrerade användare kör kalibrering av ögonspårning. Du kan komma åt den via kalibreringsuppmaningen för ögonspårning eller genom att starta appen Inställningar från Start-menyn och sedan välja **System > Kalibrering > Eye Kalibrering > Kör ögonav60.**

#### <a name="deferred-calibration-prompt"></a>Uppskjuten kalibreringsfråga

Med Auto Eye Position (Automatisk ögonposition) skjutas dialogrutan Kalibrering av ögonspårning upp tills ett program begär Ögonögontidsdata. Detta säkerställer att användaren inte uppmanas att göra det när det aktiva programmet inte kräver blick. Om programmet kräver blickdata och den aktuella användaren inte kalibreras visas en kalibreringsfråga för användaren. Det här beteendet kan användas för att visa kalibreringsuppmaning för ögonspårning vid en lämplig tidpunkt för upplevelsen. Den här metoden rekommenderas av följande skäl

1.  Dialogrutan Mätning av ögonspårning ger användaren information om varför ögonspårning behövs.
2.  Visar användaren ett sätt att neka att få ögonen kalibrerade.

Om användaren väljer att starta kalibrering av ögonspårning bör fokus återgå till det ursprungliga programmet när kalibreringen är klar. 

### <a name="calibration-data-and-security"></a>Kalibreringsdata och säkerhet

Kalibreringsinformation lagras lokalt på enheten och är inte associerad med någon kontoinformation. Det finns inget register över vem som har använt enheten utan kalibrering. Det innebär att nya användare uppmanas att kalibrera visuella objekt när de använder enheten för första gången och användare som avanmält sig från kalibrering tidigare eller om kalibreringen misslyckades.

Enheten kan lagra upp till 50 kalibreringsprofiler lokalt. När det här numret har nåtts tar enheten automatiskt bort den äldsta oanvända profilen.

Kalibreringsinformation kan alltid tas bort från enheten i **Inställningar Privacy**  >    >  **Eye-spårare**.  

### <a name="disable-calibration"></a>Inaktivera kalibrering

Du kan också inaktivera kalibreringsuppmaning genom att följa dessa steg:

1. Välj **Inställningar**  >  **System**  >  **Kalibrering**.
1. Stäng av **När en ny person använder denna HoloLens ber du automatiskt om att köra ögonavrummet.**

> [!IMPORTANT]
> Den här inställningen kan påverka hologramåtergivningens kvalitet och bekvämlighet negativt.  När du inaktiverar den här inställningen fungerar funktioner som är beroende av ögonspårning (till exempel textrullning) inte längre i avancerade program.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2-ögonspårningsteknik

Enheten använder sin ögonspårningsteknik för att förbättra visningskvaliteten och för att säkerställa att alla hologram är korrekt placerade och bekväma att visa i 3D. Eftersom den använder ögonen som landmärken kan enheten justera sig för varje användare och finjustera sina visuella objekt när headset skiftar något under hela användningen.  Alla justeringar sker i farten utan manuell justering.
> [!NOTE]
> Inställningen av IPD gäller inte för Hololens 2, eftersom ögonpositionerna beräknas av systemet.

HoloLens-program använder ögonspårning för att spåra var du letar i realtid. Det här är den viktigaste funktionen som utvecklare kan använda för att möjliggöra en helt ny kontextnivå, mänsklig förståelse och interaktioner inom den holografiska upplevelsen. Utvecklare behöver inte göra något för att använda den här funktionen.

## <a name="calibrating-your-hololens-1st-gen"></a>Kalibrera hololens (första gen)

HoloLens (1:a gen) justerar hologramvisningen enligt [ditt interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Om IPD:t inte är korrekt kan hologram verka instabila eller på ett felaktigt avstånd. Du kan förbättra kvaliteten på dina visuella objekt genom att bättra enheten till interpupillary distance (IPD).

När du ställer in din HoloLens-enhet (första generationens) uppmanas den att kalibrera dina visuella objekt när Cortana presenterar sig själv. Vi rekommenderar att du slutför kalibreringssteget under den här konfigurationsfasen. Du kan dock hoppa över det genom att vänta tills Cortana frågar dig och sedan säger "Hoppa över".

Under kalibreringsprocessen ber HoloLens dig att justera ditt finger med en serie med sex mål per ögon. HoloLens använder den här processen för att ange IPD:t korrekt för dina ögon.

![IPD-skärm för fingerjustering i det andra steget](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Starta kalibreringsprocessen manuellt

Om du behöver uppdatera kalibreringen eller om en ny användare behöver justera den kan du köra kalibreringsappen manuellt när som helst. Kalibreringsappen installeras som standard. Du kan komma åt den antingen via **Start-menyn** eller appen Inställningar.

Följ dessa steg **om** du vill använda Start-menyn för att köra kalibreringsappen:

1. Använd [bloom-gesten](hololens1-basic-usage.md) för att öppna **Start-menyn.**
1. Om du vill visa alla appar väljer du **+** .
1. Välj **Kalibrering.**

![Åtkomst till kalibreringsappen från gränssnittet](./images/calibration-shell.png)

![Kalibreringsappen visas som en live-kub efter att ha startats](./images/calibration-livecube-200px.png)

Följ dessa steg om du vill använda appen Inställningar för att köra kalibreringsappen:

1. Använd [bloom-gesten](hololens1-basic-usage.md) för att öppna **Start-menyn.**
1. Om **Inställningar** inte är fäst på Start **väljer du** för att visa alla **+** appar.
1. Välj **inställningar**.
1. Välj   >  **SystemVerktyg Öppna**  >  **Kalibrering**.

![Starta kalibreringsappen från inställningsappen](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Integrerande headset

Vissa integrerande headset ger möjlighet att anpassa IPD-inställningen. Om du vill ändra IPD för ditt headset öppnar du appen Inställningar och väljer **Mixed reality**  >  **Headset display** och flyttar sedan skjutreglaget. Du ser ändringarna i realtid i ditt headset. Om du känner till din IPD, kanske från ett besök i optomettten, kan du även ange den direkt.

Du kan också justera den här inställningen på datorn genom att välja **Inställningar**  >  **Mixed reality** Headset  >  **display**.

Om ditt headset inte stöder IPD-anpassning inaktiveras den här inställningen.
