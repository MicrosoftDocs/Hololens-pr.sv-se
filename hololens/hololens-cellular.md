---
title: Anslut till mobilnät och 5G
description: Ansluta till mobilnät från dina HoloLens enheter med mixad verklighet.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635848"
---
# <a name="connect-to-cellular-and-5g"></a>Anslut till mobilnät och 5G

HoloLens 2 stöder två metoder för att ansluta till mobilnät och 5G-nätverk:

- Ett ad hoc WiFi-nätverk som tillhandahålls av mobilenheten, vilket vanligtvis kallas "hotspot"
- Begränsat stöd för USB-C-anslutna enheter

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

De flesta mobilanslutningsbehov kan uppfyllas med en hotspot. HoloLens 2 WiFi stöder 802.11ac, vilket kan ge de krav på bandbredd och svarstid som krävs för de vanligaste användningsfallen. WiFi är också kabelfritt och erbjuder kompatibilitet med det största antalet mobila enheter.

### <a name="connecting-to-a-hotspot"></a>Ansluta till en hotspot

1. Läs enhetens manuella information om hur du aktiverar dess hotspot-läge.
1. Aktivera hotspot-läge, ange ett namn för nätverket samt ett känt lösenord.
1. I HoloLens 2 Nätverksinställningar letar du upp det WiFi-nätverk som skapades i steg 2 och ansluter det.

## <a name="usb-c-tethering"></a>USB-C-internetring

USB-C-internet internet kan ge kortare svarstider för avancerade arbetsbelastningar som behöver det. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)kan till exempel dra nytta av internet internet. Observera att Internet-anslutning kräver en kabel mellan mobilenheten och HoloLens, och internet internetning stöds av ett begränsat antal enheter.

### <a name="usb-c-compatibility"></a>USB-C-kompatibilitet

Ett begränsat antal enheter som presenterar sig själva som ethernet-adapter kan användas med Windows Holographic version 2004 och senare.

Enheter som inte visas som ethernet-kort måste ha stöd för den allmänna Microsoft [RNDIS-drivrutinen.](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Men endast ett begränsat antal av dessa enheter är kompatibla med HoloLens 2. Kontakta enhetens tillverkare för information om huruvida den stöder den allmänna Microsoft RNDIS-drivrutinen.

Enheter som inte är RNDIS-kompatibla eller kräver att en drivrutin eller ett program installeras stöds inte.

Även om Microsoft inte har någon lista över kompatibla enheter finns det en community-diskussion om ämnet [här](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Ansluta till en internetansluten enhet

1. Läs enhetens handbok om hur du aktiverar datadelning via USB. Den här inställningen kallas ofta "USB-internetdelning", "Datadelning" eller "USB-modem".
1. Aktivera datadelning via USB.
1. Anslut enheten till den HoloLens USB-C-porten.
1. I HoloLens 2 Nätverksinställningar visas enheten automatiskt som en Ethernet-anslutning.
