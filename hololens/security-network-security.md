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
# <a name="network-security"></a><span data-ttu-id="d6acc-104">Nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="d6acc-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="d6acc-105">Nätverksprotokoll</span><span class="sxs-lookup"><span data-stu-id="d6acc-105">Network protocols</span></span>

<span data-ttu-id="d6acc-106">Inaktuella NetBIOS (Network Basic Input/Output System) användes ofta tidigare i LAN-scenarier – ofta för att tillhandahålla namnmatchning till en dator och delade mappar.</span><span class="sxs-lookup"><span data-stu-id="d6acc-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="d6acc-107">Men med tiden visade sig NetBIOS vara sårbart för flera attacker och dess relevans minskade till förmån för andra säkrare protokoll.</span><span class="sxs-lookup"><span data-stu-id="d6acc-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="d6acc-108">HoloLens 2 har eliminerat den NetBIOS-relaterade koden från operativsystemet för att ta bort det här säkerhetsproblemet.</span><span class="sxs-lookup"><span data-stu-id="d6acc-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="d6acc-109">TLS-Transport Layer Security protokoll utvecklas hela tiden.</span><span class="sxs-lookup"><span data-stu-id="d6acc-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="d6acc-110">För att hålla koll på de olika säkerhetskryphål som har upptäckts i det här området har databehandlingsbranschen uppgraderats till nyare och effektivare versioner.</span><span class="sxs-lookup"><span data-stu-id="d6acc-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="d6acc-111">På grund av den tid som krävs för att alla serverdistributioner ska införa de nya TLS-protokollversionerna kan en återställningsmekanism implementeras som gör att klienten och servrarna i olika standardprotokollversioner fortfarande kan kommunicera under övergångsperioden.</span><span class="sxs-lookup"><span data-stu-id="d6acc-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="d6acc-112">Säker anslutning</span><span class="sxs-lookup"><span data-stu-id="d6acc-112">Secure connectivity</span></span> 

<span data-ttu-id="d6acc-113">Den Windows Defender-brandväggen tillhandahåller viktiga funktioner för att skydda enhetsanslutningen.</span><span class="sxs-lookup"><span data-stu-id="d6acc-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="d6acc-114">Med HoloLens 2 är brandväggen alltid aktiverad och det finns inga sätt att inaktivera den programmässigt eller via användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="d6acc-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="d6acc-115">Fjärråtkomst och anslutningssekretess för mobila klienter kan garanteras via [UWP VPN-plugin-plattformen](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="d6acc-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="d6acc-116">VPN-leverantörer från tredje part kan skapa egna plugin-program med Hjälp av WinRT-API:er som körs i sandbox-miljön för AppContainer, vilket eliminerar den komplexitet och de problem som ofta är associerade med att skriva drivrutiner på systemnivå.</span><span class="sxs-lookup"><span data-stu-id="d6acc-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
