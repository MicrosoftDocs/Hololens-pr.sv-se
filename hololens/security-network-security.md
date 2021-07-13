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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640499"
---
# <a name="network-security"></a><span data-ttu-id="35be0-104">Nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="35be0-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="35be0-105">Nätverksprotokoll</span><span class="sxs-lookup"><span data-stu-id="35be0-105">Network protocols</span></span>

<span data-ttu-id="35be0-106">Det inaktuella NetBIOS (Network Basic Input/Output System) användes ofta tidigare i LAN-scenarier – ofta för att tillhandahålla namnmatchning till en dator och delade mappar.</span><span class="sxs-lookup"><span data-stu-id="35be0-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="35be0-107">Men med tiden visade sig NetBIOS vara sårbart för flera attacker och dess relevans minskade till förmån för andra säkrare protokoll.</span><span class="sxs-lookup"><span data-stu-id="35be0-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="35be0-108">För att ta bort det här HoloLens 2 eliminerat den NetBIOS-relaterade koden från operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="35be0-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="35be0-109">TLS-protokoll (Transport Layer Security) utvecklas hela tiden.</span><span class="sxs-lookup"><span data-stu-id="35be0-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="35be0-110">För att hålla reda på de olika säkerhetsriskerna som har upptäckts i det här området har databehandlingsbranschen uppgraderats till nyare och effektivare versioner.</span><span class="sxs-lookup"><span data-stu-id="35be0-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="35be0-111">På grund av den tid som krävs för att alla serverdistributioner ska införa de nya TLS-protokollversionerna kan en återställningsmekanism implementeras som gör att klienten och servrarna på olika standardprotokollversioner fortfarande kan kommunicera under övergångsperioden.</span><span class="sxs-lookup"><span data-stu-id="35be0-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="35be0-112">Säker anslutning</span><span class="sxs-lookup"><span data-stu-id="35be0-112">Secure connectivity</span></span> 

<span data-ttu-id="35be0-113">I Windows Defender Firewall finns viktiga funktioner som skyddar enhetsanslutningen.</span><span class="sxs-lookup"><span data-stu-id="35be0-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="35be0-114">Med HoloLens 2 är brandväggen alltid aktiverad och det finns inga sätt att inaktivera den programmatiskt eller via användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="35be0-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="35be0-115">Fjärråtkomst och anslutningssekretess för mobila klienter kan garanteras via [UWP VPN-plugin-plattformen](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="35be0-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="35be0-116">VPN-leverantörer från tredje part kan skapa egna plugin-program med WinRT-API:er som körs i sandbox-miljön för AppContainer, vilket eliminerar den komplexitet och de problem som ofta är associerade med att skriva drivrutiner på systemnivå.</span><span class="sxs-lookup"><span data-stu-id="35be0-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
