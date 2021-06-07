---
title: Introduktion till den nya inställningsappen
description: Läs mer om den nya inställningsappen
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, settings, app picker, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380138"
---
# <a name="new-settings-app"></a>Ny inställningsapp

Med [Windows Holographic, version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)introducerar vi en ny version av appen Inställningar. Den nya appen Inställningar innehåller nya funktioner och utökade inställningar för HoloLens 2 inom följande områden: Ljud, Power &-strömsparläge, Network & Internet, Appar, konton, Hjälpmedel med mera.

> [!NOTE]
> Eftersom den nya appen Inställningar skiljer sig från den äldre inställningsappen tas eventuella inställningsfönster som du tidigare placerat runt din miljö bort vid uppdateringen.

![Startsida för appen Nya inställningar](images/new-settings-app.png)

**Nya funktioner och inställningar**
- Inställningssökning: Sök efter inställningar från startsidan inställningar med nyckelord eller inställningens namn.
- System > [Color-kalibrering](hololens2-display.md#how-to-use-display-color-calibration)
    - Välj en alternativ färgprofil för holoLens 2-visningen.
- System > Sound:
  - Enheter för indata- och utdataljud: Välj dina indata- och utdataljudenheter oberoende av varandra (till exempel lyssna på ljud via Bluetooth-ljud eller använd en USB-C-mikrofon för ljudindata).
    > [!NOTE]
    > Bluetooth-mikrofoner stöds inte av HoloLens 2.
  - Appvolym: justera volymen för varje app oberoende av varandra. Se [volymkontrollen per app.](holographic-home.md#per-app-volume-control)
- System > ström & sparläge: Välj när enheten ska förströms i strömsparläge efter en tids inaktivitet.
- System > Batteri: aktivera batterisparfunktion manuellt eller ange ett tröskelvärde för batteri vid vilket tidpunkt batterisparfunktion aktiveras automatiskt.
- Enheter > USB: du kan inaktivera USB-anslutningar som standard.
- Nätverk & Internet:
  - USB-C Ethernet-kort visas nu i Network & Internet.
  - Inställningar för USB-C Ethernet-adapter är nu tillgängliga, inklusive dess IP-adress.
  - Nu kan du aktivera flygplansläge på HoloLens 2.
- Appar: du kan återställa de standardappar som används för fil- och länktyper. Mer information finns i [Standardappväljaren](holographic-home.md#default-app-picker).
- Konton > Andra användare: enhetsägare kan lägga till användare, uppgradera standardanvändare till enhetsägare, nedgradera enhetsägare till standardanvändare och ta bort användare.
- Hjälpmedel: ändra textstorlek och vissa visuella effekter.

**Kända problem**
- Tidigare placerade inställningsfönster tas bort (se anteckningen ovan).
- Du kan inte längre byta namn på enheten med appen Inställningar. IT-administratörer kan byta namn på enheter med [hjälp av enhetsnamnmallen Windows Autopilot för HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) eller [CSP-noden](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) MDM DevDetail Ext/Microsoft/DNSComputerName.
- Ethernet-sidan visar en virtuell Ethernet-enhet ("UsbNcm") hela tiden.
- Batterianvändningen för den nya Microsoft Edge kanske inte är korrekt, på grund av dess natur som ett Win32-skrivbordsprogram som stöds av ett UWP-adapterlager (ingen korrigering förväntas snart).

