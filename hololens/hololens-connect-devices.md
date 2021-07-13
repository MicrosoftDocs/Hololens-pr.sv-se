---
title: Anslut till Bluetooth USB-C-enheter
description: Kom igång med att ansluta Bluetooth USB-C-enheter och tillbehör från dina HoloLens enheter med mixad verklighet.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639105"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Anslut till Bluetooth USB-C-enheter

## <a name="pair-bluetooth-devices"></a>Koppla Bluetooth enheter

HoloLens 2 stöder följande klasser av Bluetooth enheter:

- [HID](/windows-hardware/drivers/hid/):
    - Mus
    - Tangentbord
- Enheter med ljudutdata (A2DP)

HoloLens 2 stöder följande Bluetooth API:er:
- [GATT-server](/windows/uwp/devices-sensors/gatt-server) och [klient](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Du kan behöva installera motsvarande tillhörande appar från Microsoft Store för att faktiskt använda HID- och GATT-enheterna.

HoloLens (första generationen) stöder följande klasser av Bluetooth enheter:

- Mus
- Tangentbord
- [HoloLens (första generationen)](hololens1-clicker.md)

> [!NOTE]
> Andra typer Bluetooth enheter, till exempel högtalare, headset, smartphones och spelpaddlar, kan anges som tillgängliga i HoloLens inställningar. Dessa enheter stöds dock inte på HoloLens (första generationen). Mer information finns i [HoloLens Inställningar visar enheter som tillgängliga, men enheterna fungerar inte.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Koppla ett Bluetooth tangentbord eller mus

1. Sätt på tangentbordet eller musen och gör det möjligt att identifiera det. Om du vill lära dig hur du gör det möjligt att identifiera enheten kan du leta efter information om enheten (eller dess dokumentation) eller gå till tillverkarens webbplats.

1. Använd bloom-gesten (HoloLens (första gen)) eller startgesten (HoloLens 2) för att gå **till Starta** och välj **sedan Inställningar**.

1. Välj **Enheter** och kontrollera att Bluetooth är på.  

1. När du ser enhetsnamnet väljer du **Parkoppla** och följer sedan anvisningarna.

## <a name="disable-bluetooth"></a>Inaktivera Bluetooth

Den här proceduren inaktiverar RF-komponenterna i Bluetooth radio och inaktiverar alla Bluetooth på Microsoft HoloLens.

1. Använd bloom-gesten (HoloLens (första gen)) eller startgesten (HoloLens 2) för att gå **till Starta** och välj **sedan Inställningar**  >  **Enheter**.

1. Flytta skjutreglaget för **Bluetooth** till **läget Av.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Anslut USB-C-enheter

HoloLens 2 stöder följande klasser av USB-C-enheter:

- Masslagringsenheter (till exempel tumenheter)
- Ethernet-kort (inklusive Ethernet plus laddning)
- Digitala USB-C-till-3.5mm-ljudadaptrar
- Digitala USB-C-ljudheadset (inklusive headsetadaptrar plus laddning)
- Externa USB-C-mikrofoner[(Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare)
- Kabelansluten mus
- Kabelanslutet tangentbord
- PDU-hubbar (USB A plus PD-debitering)


> [!NOTE]
> Som svar på kundfeedback har vi aktiverat begränsat stöd för mobil anslutning till internet direkt till HoloLens via USB-C. Mer Anslut finns i Anslut till mobilnät och [5G.](hololens-cellular.md)

### <a name="usb-c-external-microphone-support"></a>Stöd för extern USB-C-mikrofon

> [!IMPORTANT]
> Om du ansluter **en USB-mic konfigureras den inte automatiskt som indataenhet.** När användarna ansluter en uppsättning USB-C-telefoner ser de att hörtelefonens ljud automatiskt omdirigeras till mikrofonen, men HoloLens-operativsystemet prioriterar den interna mikrofonmatrisen ovanför andra indataenhet. **Följ stegen nedan om du vill använda en USB-C-mikrofon.**

> [!NOTE]
> Externa mikrofoner kan inte användas i versioner före [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare. 

Användare kan välja USB-C-anslutna externa mikrofoner med hjälp **av panelen** Ljudinställningar. USB-C-mikrofoner kan användas för att anropa, spela in osv.

Öppna appen **Inställningar** och välj   >  **Systemljud.**

![Ljud Inställningar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Om du vill använda externa **mikrofoner med Remote Assist** måste användarna klicka på hyperlänken "Hantera ljudenheter".
>
> Använd sedan listrutan för att ange den externa mikrofonen som Standard **eller** **Standard för kommunikation.** Om **du** väljer Standard används den externa mikrofonen överallt.
>
> Om **du väljer Kommunikationsstandard** innebär det att den externa mikrofonen kommer att användas i Remote Assist och andra kommunikationsappar, men HoloLens mic-matrisen kan fortfarande användas för andra uppgifter.

![Hantera ljudenheter](images/usbc-mic-2.png)

<br>

![Ange mikrofonstandard](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Vad gäller för Bluetooth mikrofonstöd?

Tyvärr stöds Bluetooth mikrofoner fortfarande inte på HoloLens 2.

### <a name="usb-c-hubs"></a>USB-C-hubbar

Vissa användare kan behöva ansluta flera enheter samtidigt. För användare som vill använda en [USB-C-mikrofon](#usb-c-external-microphone-support) tillsammans med en annan ansluten enhet kan USB-C-hubbar passa kundens behov. Microsoft har inte testat dessa enheter och vi kan inte heller rekommendera några specifika varumärken.

**Krav för USB-C-hubb och anslutna enheter:**

- Anslutna enheter får inte kräva att en drivrutin installeras.
- Det totala energisparet för alla anslutna enheter måste vara under 4,5 Watt.

## <a name="connect-to-miracast"></a>Anslut till Miracast

Följ dessa Miracast du använda:

1. Gör något av följande:  

   - Öppna **Start-menyn** och välj **ikonen** Visa.
   - Säg "Anslut" när du tittar på **Start-menyn.**  

1. I listan över enheter som visas väljer du en tillgänglig enhet.

1. Slutför parkopplingen för att börja projicera.
