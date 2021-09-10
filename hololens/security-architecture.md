---
title: HoloLens säkerhetsarkitektur
description: Säkerhetsarkitektur
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428967"
---
# <a name="security-overview-and-architecture"></a>Säkerhetsöversikt och arkitektur

Säkerhetsarkitekturen HoloLens 2 utformades och utformades från grunden för att vara fri från äldre säkerhetsproblem, samtidigt som man skapade en minimerad angreppsyta. Den här nya, innovativa arkitekturen erbjuder säkra lagringsplatser och avancerade säkerhetselement, med mekanismer som kan avskärma operativsystem från potentiella hot och sårbarheter.

HoloLens 2 kombinerar maskinvara, programvara, nätverk och tjänster för att leverera säkerhet från slutanvändare till slut, samtidigt som användaren får en optimal upplevelse. Med HoloLens 2 aktiveras en stor majoritet av säkerhetsfunktionerna automatiskt, vilket minimerar det arbete som krävs för att konfigurera operativsystemet korrekt.

Windows HoloLens 2 och operativsystemets arkitektur erbjuder dessa innovativa säkerhetsfunktioner:

  * Tillståndsseparation och isolering: Den här nya arkitekturen skyddar kritiska delar av HoloLens 2-operativsystemet från att ändras – till exempel de som krävs för att kärnoperativsystemet ska kunna starta i ett betrott tillstånd. Isoleringsteknik används för att begränsa ej betrodda appar i ett sandbox-område, så att de inte kan påverka systemsäkerheten. Hela operativsystemet är indelade i säkra avsnitt, där varje avsnitt är avskärmat av en kombination av olika säkerhetstekniker.
  
  * **Dataskydd:** Om en användares enhet blir stulen eller borttappad, förhindrar HoloLens 2 obehöriga program från att läsa känslig information genom att förlita sig på BitLocker-kryptering av data. 
  
  * **Lösenordslös operativsystem:** Äldre lösenordsbaserade operativsystem kan oavsiktligt exponera användare för nätfiskehot och var ofta ansvariga för komprometterade konton. Windows Holographic for Business eliminerar användningen av lösenord för MSA- och Azure AD-inloggning och förstärker skyddet av användaridentiteter med Windows Hello™- och FIDO2-inloggning. 
  
    > [!NOTE]
    > Om du vill ha FIDO2-stöd måste enheten vara på Version 19041 eller senare. 

  * **Nätverkssäkerhet:** HoloLens 2 ger användaren ökad nätverkssäkerhet via förbättrade protokoll och standardinställningar.
