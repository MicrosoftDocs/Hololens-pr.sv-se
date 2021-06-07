---
title: Ansluta till Bluetooth- och USB-C-enheter
description: Kom igång med att ansluta till Bluetooth- och USB-C-enheter och tillbehör från dina HoloLens Mixed Reality-enheter.
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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380083"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Ansluta till Bluetooth- och USB-C-enheter

## <a name="pair-bluetooth-devices"></a>Koppla Bluetooth-enheter

HoloLens 2 stöder följande klasser av Bluetooth-enheter:

- [HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):
    - Mus
    - Tangentbord
- Ljudutdataenheter (A2DP)

HoloLens 2 stöder följande Bluetooth-API:er:
- [GATT-server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) och [klient](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Du kan behöva installera motsvarande tillhörande appar från Microsoft Store att faktiskt använda HID- och GATT-enheterna.

HoloLens (1:a gen) stöder följande klasser av Bluetooth-enheter:

- Mus
- Tangentbord
- [HoloLens (1:a gen) clicker](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Andra typer av Bluetooth-enheter, till exempel högtalare, headset, smartphones och spelenheter, kan anges som tillgängliga i HoloLens-inställningarna. Dessa enheter stöds dock inte på HoloLens (första gen). Mer information finns i [HoloLens-inställningar visar enheter som tillgängliga, men enheterna fungerar inte.](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Parkoppla ett Bluetooth-tangentbord eller en mus

1. Sätt på tangentbordet eller musen och gör det enkelt att identifiera det. Om du vill lära dig hur du gör det möjligt att identifiera enheten kan du leta efter information om enheten (eller dess dokumentation) eller gå till tillverkarens webbplats.

1. Använd bloom-gesten (HoloLens (första gen)) eller startgesten (HoloLens 2) för att gå **till Starta** och välj **sedan Inställningar.**

1. Välj **Enheter** och kontrollera att Bluetooth är på.  

1. När du ser enhetsnamnet väljer du **Par** och följer sedan anvisningarna.

## <a name="disable-bluetooth"></a>Inaktivera Bluetooth

Den här proceduren inaktiverar RF-komponenterna i Bluetooth-radio och inaktiverar alla Bluetooth-funktioner på Microsoft HoloLens.

1. Använd bloom-gesten (HoloLens (första gen)) eller startgesten (HoloLens 2) för att gå **till Starta** och välj **sedan Inställningar**  >  **Enheter**.

1. Flytta skjutreglaget för **Bluetooth** till **läget Av.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Ansluta USB-C-enheter

HoloLens 2 stöder följande klasser av USB-C-enheter:

- Masslagringsenheter (till exempel tumenheter)
- Ethernet-kort (inklusive Ethernet plus laddning)
- USB-C-till-3.5mm digitala ljudadaptrar
- Digitala USB-C-ljudheadset (inklusive headsetadapters plus laddning)
- Externa USB-C-mikrofoner[(Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare)
- Kabelansluten mus
- Kabelanslutet tangentbord
- PDU-kombinationshubbbar (USB A plus PD-debitering)


> [!NOTE]
> Som svar på kundfeedback har vi aktiverat begränsat stöd för mobilanslutning via Internet direkt till HoloLens via USB-C. Mer information finns i Ansluta till mobilnät och [5G.](hololens-cellular.md)

### <a name="usb-c-external-microphone-support"></a>Stöd för extern USB-C-mikrofon

> [!IMPORTANT]
> När du ansluter **en USB-mikrofon konfigureras den inte automatiskt som indataenheten**. Vid anslutning av en uppsättning USB-C-mikrofoner ser användarna att hörtelefonens ljud automatiskt omdirigeras till mikrofonen, men HoloLens OS prioriterar den interna mikrofonmatrisen ovanför andra indataenhet. **Följ stegen nedan om du vill använda en USB-C-mikrofon.**

> [!NOTE]
> Externa mikrofoner kan inte användas i versioner före [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare. 

Användare kan välja USB-C-anslutna externa mikrofoner med hjälp av **panelen** Ljudinställningar. USB-C-mikrofoner kan användas för att anropa, spela in osv.

Öppna appen **Inställningar** och välj   >  **Systemljud.**

![Ljudinställningar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Om du vill använda externa **mikrofoner med Fjärrhjälp** måste användarna klicka på hyperlänken "Hantera ljudenheter".
>
> Använd sedan listrutan för att ange den externa mikrofonen som Standard **eller** **Standard för kommunikation.** Om **du** väljer Standard används den externa mikrofonen överallt.
>
> Om **du väljer Standard** för kommunikation innebär det att den externa mikrofonen kommer att användas i Remote Assist och andra kommunikationsappar, men HoloLens mic-matrisen kan fortfarande användas för andra uppgifter.

![Hantera ljudenheter](images/usbc-mic-2.png)

<br>

![Ange mikrofon som standard](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Vad gäller för stöd för Bluetooth-mikrofon?

Bluetooth-mikrofoner stöds tyvärr inte för närvarande på HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Felsöka USB-C-mikrofoner

Tänk på att vissa USB-C-mikrofoner rapporterar sig själva felaktigt som både *en mikrofon och* en talare. Det här är ett problem med mikrofonen och inte med HoloLens. När du ansluter en av dessa mikrofoner till HoloLens kan ljudet gå förlorat. Lyckligtvis finns det en enkel korrigering.  

I **Inställningar**  ->    ->  **Systemljud** anger du uttryckligen de inbyggda talarna **(Analog Feature Audio Driver)** som **Standardenhet**. HoloLens bör komma ihåg den här inställningen även om mikrofonen tas bort och återansluts senare.

![Felsöka USB-C-mikrofoner](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a>USB-C-hubbar

Vissa användare kan behöva ansluta flera enheter samtidigt. För användare som vill använda en [USB-C-mikrofon](#usb-c-external-microphone-support) tillsammans med en annan ansluten enhet kan USB-C-hubbar passa kundens behov. Microsoft har inte testat dessa enheter och vi kan inte heller rekommendera några specifika varumärken.

**Krav för USB-C-hubb och anslutna enheter:**

- Anslutna enheter får inte kräva att en drivrutin installeras.
- Det totala energisparet för alla anslutna enheter måste vara under 4,5 Watt.

## <a name="connect-to-miracast"></a>Ansluta till Miracast

Följ dessa steg om du vill använda Miracast:

1. Gör något av följande:  

   - Öppna **Start-menyn** och välj **ikonen** Visa.
   - Säg "Anslut" medan du tittar på **Start-menyn.**  

1. I listan över enheter som visas väljer du en tillgänglig enhet.

1. Slutför parkopplingen för att börja projicera.
