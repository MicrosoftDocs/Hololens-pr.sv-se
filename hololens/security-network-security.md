---
title: Nätverkssäkerhet
description: nätverkssäkerhet
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, network, network security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380031"
---
# <a name="network-security"></a>Nätverkssäkerhet

## <a name="network-protocols"></a>Nätverksprotokoll

Inaktuella NetBIOS (Network Basic Input/Output System) användes ofta tidigare i LAN-scenarier – ofta för att tillhandahålla namnmatchning till en dator och delade mappar. Men med tiden visade sig NetBIOS vara sårbart för flera attacker och dess relevans minskade till förmån för andra säkrare protokoll. HoloLens 2 har eliminerat den NetBIOS-relaterade koden från operativsystemet för att ta bort det här säkerhetsproblemet.

TLS-Transport Layer Security protokoll utvecklas hela tiden. För att hålla koll på de olika säkerhetskryphål som har upptäckts i det här området har databehandlingsbranschen uppgraderats till nyare och effektivare versioner. På grund av den tid som krävs för att alla serverdistributioner ska införa de nya TLS-protokollversionerna kan en återställningsmekanism implementeras som gör att klienten och servrarna i olika standardprotokollversioner fortfarande kan kommunicera under övergångsperioden.

## <a name="secure-connectivity"></a>Säker anslutning 

Den Windows Defender-brandväggen tillhandahåller viktiga funktioner för att skydda enhetsanslutningen. Med HoloLens 2 är brandväggen alltid aktiverad och det finns inga sätt att inaktivera den programmässigt eller via användargränssnittet.

Fjärråtkomst och anslutningssekretess för mobila klienter kan garanteras via [UWP VPN-plugin-plattformen](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041). VPN-leverantörer från tredje part kan skapa egna plugin-program med Hjälp av WinRT-API:er som körs i sandbox-miljön för AppContainer, vilket eliminerar den komplexitet och de problem som ofta är associerade med att skriva drivrutiner på systemnivå.
