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
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640176"
---
# <a name="new-settings-app"></a>Ny Inställningar app

Med [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)introducerar vi en ny version av Inställningar appen. Den nya Inställningar-appen innehåller nya funktioner och utökade inställningar för HoloLens 2 inom följande områden: Ljud, Strömsparläge, Network & & Internet, appar, konton, Hjälpmedel med mera.

> [!NOTE]
> Eftersom den nya Inställningar-appen skiljer sig från den äldre Inställningar-appen, kommer alla Inställningar fönster som du tidigare placerat runt din miljö att tas bort vid uppdateringen.

![Startsida Inställningar ny app](images/new-settings-app.png)

**Nya funktioner och inställningar**
- Inställningar sökning: sök efter inställningar Inställningar startsidan med nyckelord eller inställningens namn.
- System > [Color-kalibrering](hololens2-display.md#how-to-use-display-color-calibration)
    - Välj en alternativ färgprofil för din HoloLens 2-skärm.
- System > Sound:
  - Enheter för indata- och utdataljud: Välj dina enheter för indata- och utdataljud oberoende av varandra (till exempel lyssna på ljud via Bluetooth eller använd en USB-C-mikrofon för ljudindata).
    > [!NOTE]
    > Bluetooth mikrofoner stöds inte av HoloLens 2.
  - Appvolym: justera volymen för varje app oberoende av varandra. Se [volymkontrollen per app.](holographic-home.md#per-app-volume-control)
- System > ström & sparläge: Välj när enheten ska förströms i strömsparläge efter en tids inaktivitet.
- System > Batteri: aktivera batterisparfunktion manuellt eller ange ett tröskelvärde för batteri vid vilket tidpunkt batterisparfunktion aktiveras automatiskt.
- Enheter > USB: du kan inaktivera USB-anslutningar som standard.
- Nätverk & Internet:
  - USB-C Ethernet-kort visas nu i Network & Internet.
  - Inställningar för USB-C Ethernet-adapter är nu tillgängliga, inklusive dess IP-adress.
  - Du kan nu aktivera flygplansläge på HoloLens 2.
- Appar: du kan återställa de standardappar som används för fil- och länktyper. Mer information finns i [Standardappväljaren](holographic-home.md#default-app-picker).
- Konton > Andra användare: enhetsägare kan lägga till användare, uppgradera standardanvändare till enhetsägare, nedgradera enhetsägare till standardanvändare och ta bort användare.
- Hjälpmedel: ändra textstorlek och vissa visuella effekter.

**Kända problem**
- Tidigare placerade Inställningar-fönster tas bort (se anmärkning ovan).
- Du kan inte längre byta namn på enheten med Inställningar appen. IT-administratörer kan byta namn på enheter med hjälp av Windows Autopilot för HoloLens 2-enhetsnamnmallen eller mdM [](hololens2-autopilot.md) [DevDetail CSP Ext/Microsoft/DNSComputerName-noden.](/windows/client-management/mdm/devdetail-csp)
- Ethernet-sidan visar en virtuell Ethernet-enhet ("UsbNcm") hela tiden.
- Batterianvändningen för den nya Microsoft Edge kanske inte är korrekt, på grund av dess natur som ett Win32-skrivbordsprogram som stöds av ett UWP-adapterlager (ingen korrigering förväntas snart).

