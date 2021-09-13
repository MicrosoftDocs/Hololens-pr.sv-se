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
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036595"
---
# <a name="network-security"></a>Nätverkssäkerhet

## <a name="network-protocols"></a>Nätverksprotokoll

Inaktuella NetBIOS (Network Basic Input/Output System) användes ofta tidigare i LAN-scenarier – ofta för att tillhandahålla namnmatchning till en dator och delade mappar. Men med tiden visade sig NetBIOS vara sårbart för flera attacker och dess relevans minskade till förmån för andra säkrare protokoll. Om du vill ta bort det här HoloLens 2 eliminerat den NetBIOS-relaterade koden från operativsystemet.

TLS-Transport Layer Security protokoll utvecklas hela tiden. För att hålla koll på de olika säkerhetskryphål som har upptäckts i det här området har databehandlingsbranschen uppgraderats till nyare och effektivare versioner. På grund av den tid som krävs för att alla serverdistributioner ska införa de nya TLS-protokollversionerna kan en återställningsmekanism implementeras som gör att klienten och servrarna i olika standardprotokollversioner fortfarande kan kommunicera under övergångsperioden.

## <a name="secure-connectivity"></a>Säker anslutning 

I Windows Defender Firewall finns viktiga funktioner för att skydda enhetsanslutningen. Med HoloLens 2 är brandväggen alltid aktiverad och det finns inga sätt att inaktivera den programmatiskt eller via användargränssnittet.

Fjärråtkomst och anslutningssekretess för mobila klienter kan garanteras via [UWP VPN-plugin-plattformen](/uwp/api/Windows.Networking.Vpn?view=winrt-19041). VPN-leverantörer från tredje part kan skapa egna plugin-program med WinRT-API:er som körs i sandbox-miljön för AppContainer, vilket eliminerar den komplexitet och de problem som ofta är associerade med att skriva drivrutiner på systemnivå.
