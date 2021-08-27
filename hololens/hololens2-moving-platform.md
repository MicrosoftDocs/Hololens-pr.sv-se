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
ms.openlocfilehash: cd46e162971ea709d865b2ac998cc7a517d231ec
ms.sourcegitcommit: 18f6c00a57a6b4608dadcec418d1970455d8ee3a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/26/2021
ms.locfileid: "122989216"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Flytta plattformsläge på plattformar med låg dynamisk rörelseflyttning

I **Insider-versionen 20348.1411** har vi lagt till betastöd för spårning på plattformar med låg dynamisk rörelseflyttning på HoloLens 2. När du har installerat bygget och aktiverat Moving Platform Mode kommer du att kunna använda din HoloLens 2 i tidigare otillgängliga miljöer som stora skepp och stora djur. För närvarande är funktionen endast avsedd att aktivera dessa specifika plattformar som flyttas. Även om ingenting hindrar dig från att försöka använda funktionen i andra miljöer fokuserar funktionen på att lägga till stöd för dessa miljöer först.

> [!NOTE]
> Den här funktionen är för närvarande endast tillgänglig [via Windows Insiders](hololens-insider.md).

![Flytta plattformsexempel.](./images/mpm-compare.gif)

I den här artikeln beskrivs:

1. [Varför moving platform är nödvändigt](#why-moving-platform-mode-is-necessary)
1. [Aktivera flytta plattformsläge](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Varför det är nödvändigt att flytta plattformsläge

HoloLens måste kunna spåra din huvudposition med [6 frihetsgrader](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X, Y, Z, översättning och rullning, pitch, yaw rotation) för att kunna visa stabila hologram. För att göra det HoloLens två liknande typer av information från två separata källor:

1. Synliga ljuskameror – som spårar miljön, till exempel det fysiska rum som du använder HoloLens
1. Inertial Measurement Unit (IMU), – som består av en accelerometer, torrop och magnetometer som spårar din huvud rörelse och orientering i förhållande till jorden

Informationen från dessa två källor är sammansatt för att spåra din huvudposition med låg latens och tillräckligt hög frekvens för att återge jämna hologram.

Den här metoden förlitar sig dock på ett kritiskt antagande. miljön (spåras av kamerorna) förblir stationär i förhållande till jorden (mot vilken IMU kan göra mätningar). När så inte är fallet, som på en åsna i vattnet, kan informationen från båda källorna vara i konflikt med varandra och göra att spåraren går förlorad. Den här konflikten genererar felaktig positionsinformation och resulterar i simbilder eller till och med spårningsförlust.

När du flyttar plattformsläget åtgärdas det här problemet. När du aktiverar moving platform mode (Flytta plattformsläge) är det en ledtråd till vår spårare att vi inte kan förlita oss på våra sensorindata för att hålla helt överens med varandra hela tiden. I stället behöver vi förlita oss mer på visuell spårning och snabbt identifiera icke-inkonfigurerade inertiala rörelsedata och filtrera ut dem därefter innan vi kan använda IMU-indata.

## <a name="supported-environments-and-known-limitations"></a>Miljöer som stöds och kända begränsningar

Även om moving platform mode utvecklades för att hantera fall av inertiala och visuella datakonflikter på ett intelligent sätt, är det för närvarande begränsad till stora djur som upplever låg-dynamisk rörelse. Det innebär att det finns begränsningar och scenarier som inte stöds.

### <a name="known-limitations"></a>Kända begränsningar

- De enda miljöer som stöds för MPM (Moving Platform Mode) är stora detektorer som har låg-dynamisk rörelse. Med andra ord stöds inte många  vanliga miljöer/situationer än på grund av deras höga frekvens och höga accelerationsnivåer och [sn hos](https://en.wikipedia.org/wiki/Jerk_(physics)). Till exempel: plan, tränas, bilar, cyklar, buss, små lastbilar, hissar osv.
- Hologram kan göra något när MPM är aktiverat, särskilt när det är varmt vatten.
- Ingenting hindrar användare från att försöka använda MPM i miljöer som inte stöds, men användare kan uppleva oönskade sidoeffekter om enheten kan upprätthålla spårning i det utrymme som inte stöds. Med MPM kan användare till exempel se att det är möjligt att använda i en hiss när de byter golv, medan det tidigare var omöjligt. Även om MPM tillåter att enheten underhåller spårningen så hanterar den tyvärr inte karthantering just nu. Användare kommer att se att om golven ändras i en hiss kommer enheten att förvirra de övre och lägre golven och påverka kartkvaliteten negativt.

## <a name="prerequisites"></a>Förutsättningar

Stöd för betaversion för flytta plattformsläge kräver bara några förutsättningar:

1. Installera version 20348.1411 eller nyare genom att flasha den senaste [Insiders-versionen via ARC](hololens-insider.md#ffu-download-and-flash-directions) eller genom att registrera och [uppdatera din enhet.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Den här versionen är för närvarande endast tillgänglig på [Insider Dev Channel.](hololens-insider.md#start-receiving-insider-builds)

2. Aktivera [utvecklarläge och Enhetsportalen](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Aktivera flytta plattformsläge

Om du vill aktivera läget Moving Platform (Flytta [plattform) aktiverar du först Enhetsportalen](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Välj **överensstämmelse** för system på menyn till vänster

   ![Första avbildningen](.\images\moving-platform-1w.png)

2. Markera sidan **Moving Platform Mode (Flytta plattformsläge)** och markera kryssrutan Moving Platform Mode **(Flytta** plattformsläge)

    ![Andra bilden](.\images\moving-platform-2z.png)

3. När du uppmanas med en varning väljer du **OK**

   ![Tredje bilden](.\images\moving-platform-3w.png)

4. Starta om enheten, vilket kan göras antingen via Enhetsportalen **Power-menyn** längst upp till höger eller genom att ange följande röstkommando Starta om enheten &quot; och välj &quot; &quot; &quot; Ja.

   ![Fjärde bilden](.\images\moving-platform-4z.png)

Om du inte kan se alternativet Flytta plattformsläge i Enhetsportalen innebär det förmodligen att du ännu inte har rätt version. Se [avsnittet Förutsättningar.](#prerequisites)

## <a name="reporting-issues"></a>Rapportera problem

Som nämnts ovan är den här funktionen en betafunktion som endast är tillgänglig i utvecklarläge, vilket innebär att du kan träffa på problem. Om det händer kan vi undersöka och förbättra produkten.

1. Rapportera problemet [via](hololens-feedback.md) Feedbackhubben under kategorin **Hologrammets noggrannhet, stabilitet och tillförlitlighet** och inkludera:
    1. En beskrivning av problemet, inklusive förväntat beteende och erfarenhet av beteende
    1. En Mixed Reality [videoinspelning](holographic-photos-and-videos.md#capture-a-mixed-reality-video) av problemet
2.  Öppna ett supportfall på och dela url Feedbackhubben adressen så att vi kan kontakta oss om [https://aka.ms/hlsupport](https://aka.ms/hlsupport) vi har uppföljningsfrågor