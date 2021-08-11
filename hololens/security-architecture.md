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
ms.openlocfilehash: fd6409f5087ef7d6e7ab90d6ef8dcb83e1c490746803ad869ef075dace24bae7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665530"
---
# <a name="security-overview-and-architecture"></a>Säkerhetsöversikt och arkitektur

Säkerhetsarkitekturen HoloLens 2 utformades och utformades från grunden för att vara fri från äldre säkerhetsproblem, samtidigt som man skapade en minimerad angreppsyta. Den här nya, innovativa arkitekturen erbjuder säkra lagringsplatser och avancerade säkerhetselement, med mekanismer som kan avskärma operativsystem från potentiella hot och sårbarheter.

HoloLens 2 kombinerar maskinvara, programvara, nätverk och tjänster för att leverera säkerhet från slutanvändare till slut, samtidigt som användaren får en optimal upplevelse. Med HoloLens 2 aktiveras nu en stor majoritet av säkerhetsfunktionerna automatiskt, vilket minimerar det arbete som krävs för att konfigurera operativsystemet korrekt.

Windows HoloLens 2 och operativsystemarkitekturen erbjuder dessa innovativa säkerhetsfunktioner:

  * **Tillståndsseparation och** isolering: Den här nya arkitekturen skyddar kritiska delar av HoloLens 2-operativsystemet från ändringar – till exempel de som krävs för att kärnoperativsystemet ska kunna starta i ett betrott tillstånd. Isoleringsteknik används för att begränsa ej betrodda appar i en sandbox-miljö, vilket säkerställer att de inte påverkar systemsäkerheten. Hela operativsystemet är indelade i säkra avsnitt, där varje avsnitt avskärmas av en kombination av olika säkerhetstekniker.
  
  * **Dataskydd:** Om en användares enhet förloras eller blir stulen HoloLens 2 obehöriga program från att läsa känslig information genom att förlita sig på BitLocker-kryptering av data. 
  
  * **Lösenordslös operativsystem:** Äldre lösenordsbaserade operativsystem kan oavsiktligt exponera användare för nätfiskehot och var ofta ansvariga för komprometterade konton. Windows Holographic for Business eliminerar användningen av lösenord för MSA- och Azure AD-inloggning och förstärker skyddet av användaridentiteter med Windows Hello™- och FIDO2-inloggning. 
  
    > [!NOTE]
    > Om du vill ha FIDO2-stöd måste enheten vara på Version 19041 eller senare. 

  * **Nätverkssäkerhet:** HoloLens 2 ger användaren ökad nätverkssäkerhet via förbättrade protokoll och standardinställningar.
