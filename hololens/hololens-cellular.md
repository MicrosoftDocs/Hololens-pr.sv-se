---
title: Ansluta till mobilnät och 5G
description: Ansluta till mobilnät från dina HoloLens-enheter med mixad verklighet.
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
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379999"
---
# <a name="connect-to-cellular-and-5g"></a>Ansluta till mobilnät och 5G

HoloLens 2 stöder två metoder för att ansluta till mobilnät och 5G-nätverk:

- Ett ad hoc WiFi-nätverk som tillhandahålls av mobilenheten, vilket vanligtvis kallas "hotspot"
- Begränsat stöd för USB-C-anslutna enheter

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

De flesta mobilanslutningsbehov kan uppfyllas med en hotspot. HoloLens 2 WiFi stöder 802.11ac, som kan ge de krav på bandbredd och svarstid som krävs för de vanligaste användningsfallen. WiFi är också kabelfritt och erbjuder kompatibilitet med det största antalet mobila enheter.

### <a name="connecting-to-a-hotspot"></a>Ansluta till en hotspot

1. Läs enhetens manuella information om hur du aktiverar dess hotspot-läge.
1. Aktivera hotspot-läge, ange ett namn för nätverket samt ett känt lösenord.
1. I HoloLens 2-nätverksinställningar letar du upp det WiFi-nätverk som skapades i steg 2 och ansluter det.

## <a name="usb-c-tethering"></a>USB-C-internetring

USB-C-internet internet kan ge kortare svarstider för avancerade arbetsbelastningar som behöver det. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)kan till exempel dra nytta av internet internet. Observera att Internet-anslutning kräver en kabel mellan den mobila enheten och HoloLens, och internetring stöds av ett begränsat antal enheter.

### <a name="usb-c-compatibility"></a>USB-C-kompatibilitet

Ett begränsat antal enheter som presenterar sig själva som ethernet-adapter kan användas med Windows Holographic version 2004 och senare.

Enheter som inte visas som ethernet-kort måste ha stöd för den allmänna Microsoft [RNDIS-drivrutinen.](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Men endast ett begränsat antal av dessa enheter är kompatibla med HoloLens 2. Kontakta enhetens tillverkare för information om huruvida den stöder den allmänna Microsoft RNDIS-drivrutinen.

Enheter som inte är RNDIS-kompatibla eller kräver att en drivrutin eller ett program installeras stöds inte.

Även om Microsoft inte har någon lista över kompatibla enheter finns det en community-diskussion om ämnet [här](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Ansluta till en internetansluten enhet

1. Läs enhetens handbok om hur du aktiverar datadelning via USB. Den här inställningen kallas ofta "USB-internetdelning", "Datadelning" eller "USB-modem".
1. Aktivera datadelning via USB.
1. Anslut enheten till HoloLens USB-C-port.
1. I HoloLens 2-nätverksinställningar visas enheten automatiskt som en Ethernet-anslutning.
