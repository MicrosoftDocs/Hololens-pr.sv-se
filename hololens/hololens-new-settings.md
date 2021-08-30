---
title: Introduktion till den nya Inställningar appen
description: Läs mer om den nya Inställningar appen
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, inställningar, appväljare, volym
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189672"
---
# <a name="new-settings-app"></a>Ny Inställningar app

Med [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)introducerar vi en ny version av Inställningar appen. Den nya Inställningar-appen innehåller nya funktioner och utökade inställningar för HoloLens 2 inom följande områden: Ljud, Power &-strömsparläge, Network & Internet, Appar, konton, Hjälpmedel med mera.

> [!NOTE]
> Eftersom den nya Inställningar-appen skiljer sig från den äldre Inställningar-appen, kommer alla Inställningar fönster som du tidigare placerat i din miljö att tas bort vid uppdateringen.

![Ny Inställningar app-startsida.](images/new-settings-app.png)

**Nya funktioner och inställningar**
- Inställningar sökning: sök efter inställningar Inställningar startsidan med nyckelord eller inställningens namn.
- System > [Color-kalibrering](hololens2-display.md#how-to-use-display-color-calibration)
    - Välj en alternativ färgprofil för din HoloLens 2-skärm.
- System > Sound:
  - Enheter för indata- och utdataljud: välj enheter för indata- och utdataljud oberoende av varandra (till exempel lyssna på ljud via Bluetooth-mikrofon eller använd en USB-C-mikrofon för ljudindata).
    > [!NOTE]
    > Bluetooth mikrofoner stöds inte av HoloLens 2.
  - Appvolym: justera volymen för varje app oberoende av varandra. Se [volymkontrollen per app.](holographic-home.md#per-app-volume-control)
- System > Power & strömsparläge: Välj när enheten ska förströms för ström efter en tids inaktivitet.
- System > batteri: aktivera batterisparfunktion manuellt eller ange ett tröskelvärde för batteri vid vilken tidpunkt batterisparfunktion aktiveras automatiskt.
- Enheter > USB: du kan inaktivera USB-anslutningar som standard.
- Nätverk & Internet:
  - USB-C Ethernet-kort visas nu i Network & Internet.
  - Inställningar för USB-C Ethernet-adaptern är nu tillgängliga, inklusive dess IP-adress.
  - Nu kan du aktivera flygplansläge på HoloLens 2.
- Appar: du kan återställa de standardappar som används för fil- och länktyper. Mer information finns i [Standardappväljaren](holographic-home.md#default-app-picker).
- Konton > Andra användare: enhetsägare kan lägga till användare, uppgradera standardanvändare till enhetsägare, nedgradera enhetsägare till standardanvändare och ta bort användare.
- Hjälpmedel: ändra textstorlek och vissa visuella effekter.

**Kända problem**
- Tidigare placerade Inställningar-fönster tas bort (se anteckningen ovan).
- Du kan inte längre byta namn på enheten med Inställningar appen. IT-administratörer kan byta namn på enheter med hjälp av Windows Autopilot för HoloLens 2-enhetsnamnmallen eller MDM [](hololens2-autopilot.md) [DevDetail CSP Ext/Microsoft/DNSComputerName-noden.](/windows/client-management/mdm/devdetail-csp)
- Ethernet-sidan visar alltid en virtuell Ethernet-enhet ("UsbNcm").
- Batterianvändningen för den nya Microsoft Edge kanske inte är korrekt på grund av dess natur som ett Win32-skrivbordsprogram som stöds av ett UWP-kortskikt (ingen korrigering förväntas snart).

