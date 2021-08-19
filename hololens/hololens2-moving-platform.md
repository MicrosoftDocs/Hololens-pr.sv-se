---
title: HoloLens 2 Flytta plattformsläge
description: Använda HoloLens på rörliga plattformar
keywords: moving platforms, dynamic motion, hololens, moving platform mode
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9c37baa6fb63e9b049378799515ef107ed0ea7a8
ms.sourcegitcommit: 7b666c63a0367032a4a3f366b7f9029b2613e345
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2021
ms.locfileid: "122401213"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Flytta plattformsläge på plattformar med låg dynamisk rörelse

I **Insider-versionen 20348.1411** har vi lagt till betastöd för spårning på plattformar med låg dynamisk rörelseflyttning på HoloLens 2. När du har installerat bygget och aktiverat Moving Platform Mode kan du använda din HoloLens 2 i tidigare otillgängliga miljöer som stora skepp och stora skepp. För närvarande är funktionen avsedd att endast aktivera dessa specifika rörliga plattformar. Inget hindrar dig från att försöka använda funktionen i andra miljöer, men funktionen fokuserar på att lägga till stöd för dessa miljöer först.

> [!NOTE]
> Den här funktionen är för närvarande endast tillgänglig [via Windows Insiders](hololens-insider.md).

I den här artikeln beskrivs:

1. [Varför det är nödvändigt att flytta plattformen](#why-moving-platform-mode-is-necessary)
1. [Aktivera flytta plattformsläge](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Varför det är nödvändigt att flytta plattformsläge

HoloLens måste kunna spåra din huvudposition med [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) frihetsgrader (X, Y, Z översättning och roll, pitch, yaw rotation) för att kunna visa stabila hologram. För att göra det HoloLens två liknande typer av information från två separata källor:

1. Synliga ljuskameror – som spårar miljön, till exempel det fysiska rummet där du använder HoloLens
1. Inertial Measurement Unit (IMU), – som består av en accelerometer, ett accelerationsomfång och en magnetometer som spårar din huvud rörelse och orientering i förhållande till jorden

Informationen från dessa två källor är sammansatt för att spåra din huvudposition med låg latens och tillräckligt hög frekvens för att återge jämna hologram.

Den här metoden förlitar sig dock på ett kritiskt antagande. miljön (spåras av kamerorna) förblir stationär i förhållande till jorden (mot vilken IMU kan göra mätningar). När så inte är fallet, till exempel på en åsna i vatten, kan informationen från båda källorna vara i konflikt med varandra och göra att spåraren går förlorad. Den här konflikten genererar felaktig positionsinformation och resulterar i simtur mina hologram eller till och med spårning av förlust.

När du flyttar plattformsläget åtgärdas det här problemet. När du aktiverar flytta plattformsläge är det en ledtråd till vår spårare att vi inte kan förlita oss på våra sensorindata för att helt och hållet hålla med varandra hela tiden. I stället behöver vi förlita oss mer på visuell spårning och snabbt identifiera inkonfigurerade inertiala rörelsedata och filtrera ut dem på motsvarande sätt innan vi&#39;kunna använda IMU-indata.

## <a name="supported-environments-and-known-limitations"></a>Miljöer som stöds och kända begränsningar

Även om flytta plattformsläge utvecklades för att hantera fall av inertiala och visuella datakonflikter, är det för närvarande begränsad till stora havar med låg dynamisk rörelse. Det innebär att det finns begränsningar och scenarier som inte stöds.

### <a name="known-limitations"></a>Kända begränsningar

- De enda miljöer som stöds för MPM (Moving Platform Mode) är stora havsmiljöer med låg dynamisk rörelse. Med andra ord stöds inte många  vanliga miljöer/situationer ännu på grund av den höga frekvensen av rörelse och höga accelerations- och [accelerationsnivåer.](https://en.wikipedia.org/wiki/Jerk_(physics)) Till exempel: plan, träna, bilar, cyklar, buss, små lastbilar, hissar osv.
- Hologram kan uppstå något när MPM är aktiverat, särskilt när det är ont om vatten.
- Ingenting hindrar användare från att försöka använda MPM i miljöer som inte stöds, men användare kan uppleva oönskade sidoeffekter om enheten kan upprätthålla spårning i det utrymme som inte stöds. Med MPM kan användarna till exempel se att&#39;kan använda i en hiss när de byter golv, medan det tidigare var omöjligt. Även om MPM tillåter att enheten underhåller spårningen så hanterar den tyvärr inte karthantering just nu. Användarna kommer därför att se att ändrade golv i en hiss leder till att enheten förvirrar de övre och nedre golven och påverkar kartkvaliteten negativt.

## <a name="prerequisites"></a>Förutsättningar

Beta-stöd för flytta plattformsläge kräver bara några krav:

1. Installera version 20348.1411 eller nyare genom att flasha den senaste [Insiders-versionen via ARC](hololens-insider.md#ffu-download-and-flash-directions) eller genom att registrera och [uppdatera din enhet.](hololens-insider.md#start-receiving-insider-builds)
   - Obs! Den här versionen är för närvarande endast tillgänglig på [Insider Dev Channel.](hololens-insider.md#start-receiving-insider-builds)
2. Aktivera [utvecklarläge och Enhetsportalen](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Aktivera flytta plattformsläge

Om du vill aktivera läget Moving Platform (Flytta [plattform) aktiverar du först Enhetsportalen](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Välj **överensstämmelse** för system på menyn till vänster
2. Välj sidan **Moving Platform Mode (Flytta plattformsläge)** och markera kryssrutan Moving Platform Mode **(Flytta plattformsläge)**

   ![Första avbildningen](.\images\moving-platform-1x.png)
 
     ![Andra bilden](.\images\moving-platform-2x.png)

3. När du uppmanas med en varning väljer du **OK**

   ![Tredje avbildningen](.\images\moving-platform-3x.png)

4. Starta om enheten, vilket antingen kan göras via Enhetsportalen **Power-menyn** längst upp till höger eller genom att utfärda följande röstkommando Starta om enheten &quot; och välj &quot; &quot; &quot; Ja.

   ![Fjärde bilden](.\images\moving-platform-4x.png)

Om du inte kan se alternativet Flytta plattformsläge i Enhetsportalen innebär det troligen att du inte är i rätt version än. Se [avsnittet](#prerequisites) Förutsättningar.
