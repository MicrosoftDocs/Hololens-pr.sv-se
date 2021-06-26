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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924187"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="2cb7d-103">Ansluta till Bluetooth- och USB-C-enheter</span><span class="sxs-lookup"><span data-stu-id="2cb7d-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="2cb7d-104">Koppla Bluetooth-enheter</span><span class="sxs-lookup"><span data-stu-id="2cb7d-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="2cb7d-105">HoloLens 2 stöder följande klasser av Bluetooth-enheter:</span><span class="sxs-lookup"><span data-stu-id="2cb7d-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="2cb7d-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="2cb7d-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="2cb7d-107">Mus</span><span class="sxs-lookup"><span data-stu-id="2cb7d-107">Mouse</span></span>
    - <span data-ttu-id="2cb7d-108">Tangentbord</span><span class="sxs-lookup"><span data-stu-id="2cb7d-108">Keyboard</span></span>
- <span data-ttu-id="2cb7d-109">Enheter med ljudutdata (A2DP)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="2cb7d-110">HoloLens 2 stöder följande Bluetooth-API:er:</span><span class="sxs-lookup"><span data-stu-id="2cb7d-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="2cb7d-111">[GATT-server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) och [klient](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="2cb7d-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="2cb7d-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="2cb7d-113">Du kan behöva installera motsvarande tillhörande appar från Microsoft Store att faktiskt använda HID- och GATT-enheterna.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="2cb7d-114">HoloLens (1:a gen) stöder följande klasser av Bluetooth-enheter:</span><span class="sxs-lookup"><span data-stu-id="2cb7d-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="2cb7d-115">Mus</span><span class="sxs-lookup"><span data-stu-id="2cb7d-115">Mouse</span></span>
- <span data-ttu-id="2cb7d-116">Tangentbord</span><span class="sxs-lookup"><span data-stu-id="2cb7d-116">Keyboard</span></span>
- [<span data-ttu-id="2cb7d-117">HoloLens (1:a gen) clicker</span><span class="sxs-lookup"><span data-stu-id="2cb7d-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="2cb7d-118">Andra typer av Bluetooth-enheter, till exempel högtalare, headset, smartphones och spelenheter, kan listas som tillgängliga i HoloLens-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="2cb7d-119">Dessa enheter stöds dock inte på HoloLens (första generationen).</span><span class="sxs-lookup"><span data-stu-id="2cb7d-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="2cb7d-120">Mer information finns i [HoloLens-inställningar visar enheter som tillgängliga, men enheterna fungerar inte.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="2cb7d-121">Koppla ett Bluetooth-tangentbord eller en mus</span><span class="sxs-lookup"><span data-stu-id="2cb7d-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="2cb7d-122">Sätt på tangentbordet eller musen och gör det enkelt att identifiera det.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="2cb7d-123">Om du vill lära dig hur du gör det möjligt att identifiera enheten kan du leta efter information om enheten (eller dess dokumentation) eller gå till tillverkarens webbplats.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="2cb7d-124">Använd bloom-gesten (HoloLens (första gen)) eller startgesten (HoloLens 2) för att gå **till Starta** och välj **sedan Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="2cb7d-125">Välj **Enheter** och kontrollera att Bluetooth är på.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="2cb7d-126">När du ser enhetsnamnet väljer du **Par** och följer sedan anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="2cb7d-127">Inaktivera Bluetooth</span><span class="sxs-lookup"><span data-stu-id="2cb7d-127">Disable Bluetooth</span></span>

<span data-ttu-id="2cb7d-128">Den här proceduren inaktiverar RF-komponenterna i Bluetooth-radio och inaktiverar alla Bluetooth-funktioner på Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="2cb7d-129">Använd bloom-gesten (HoloLens (första gen)) eller startgesten (HoloLens 2) för att gå **till Starta** och välj **sedan Inställningar**  >  **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="2cb7d-130">Flytta skjutreglaget för **Bluetooth** till **läget Av.**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="2cb7d-131">HoloLens 2: Ansluta USB-C-enheter</span><span class="sxs-lookup"><span data-stu-id="2cb7d-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="2cb7d-132">HoloLens 2 stöder följande klasser av USB-C-enheter:</span><span class="sxs-lookup"><span data-stu-id="2cb7d-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="2cb7d-133">Masslagringsenheter (till exempel tumenheter)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="2cb7d-134">Ethernet-kort (inklusive Ethernet plus laddning)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="2cb7d-135">Usb-C-till-3.5mm digitala ljudadaptrar</span><span class="sxs-lookup"><span data-stu-id="2cb7d-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="2cb7d-136">Digitala USB-C-ljudheadset (inklusive headsetadapters plus laddning)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="2cb7d-137">Externa USB-C-mikrofoner[(Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="2cb7d-138">Kabelansluten mus</span><span class="sxs-lookup"><span data-stu-id="2cb7d-138">Wired mouse</span></span>
- <span data-ttu-id="2cb7d-139">Kabelanslutet tangentbord</span><span class="sxs-lookup"><span data-stu-id="2cb7d-139">Wired keyboard</span></span>
- <span data-ttu-id="2cb7d-140">PDU-kombinationshubbbar (USB A plus PD-debitering)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="2cb7d-141">Som svar på kundfeedback har vi aktiverat begränsat stöd för mobilanslutning via Internet direkt till HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="2cb7d-142">Mer information finns i Ansluta till mobilnät och [5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="2cb7d-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="2cb7d-143">Stöd för extern USB-C-mikrofon</span><span class="sxs-lookup"><span data-stu-id="2cb7d-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cb7d-144">När du ansluter **en USB-mikrofon konfigureras den inte automatiskt som indataenheten**.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="2cb7d-145">Vid anslutning av en uppsättning USB-C-mikrofoner ser användarna att hörtelefonens ljud automatiskt omdirigeras till mikrofonen, men HoloLens OS prioriterar den interna mikrofonmatrisen ovanför andra indataenhet.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="2cb7d-146">**Följ stegen nedan om du vill använda en USB-C-mikrofon.**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="2cb7d-147">Externa mikrofoner kan inte användas i versioner före [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="2cb7d-148">Användare kan välja USB-C-anslutna externa mikrofoner med hjälp av **panelen** Ljudinställningar.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="2cb7d-149">USB-C-mikrofoner kan användas för att anropa, spela in osv.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="2cb7d-150">Öppna appen **Inställningar** och välj   >  **Systemljud.**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Ljudinställningar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="2cb7d-152">Om du vill använda externa **mikrofoner med Fjärrhjälp** måste användarna klicka på hyperlänken "Hantera ljudenheter".</span><span class="sxs-lookup"><span data-stu-id="2cb7d-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="2cb7d-153">Använd sedan listrutan för att ange den externa mikrofonen som Standard **eller** **Standard för kommunikation.**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="2cb7d-154">Om **du** väljer Standard används den externa mikrofonen överallt.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="2cb7d-155">Om **du väljer Standard** för kommunikation innebär det att den externa mikrofonen kommer att användas i Remote Assist och andra kommunikationsappar, men HoloLens mic-matrisen kan fortfarande användas för andra uppgifter.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Hantera ljudenheter](images/usbc-mic-2.png)

<br>

![Ange mikrofon som standard](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="2cb7d-158">Vad gäller för stöd för Bluetooth-mikrofon?</span><span class="sxs-lookup"><span data-stu-id="2cb7d-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="2cb7d-159">Bluetooth-mikrofoner stöds tyvärr inte för närvarande på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="2cb7d-160">USB-C-hubbar</span><span class="sxs-lookup"><span data-stu-id="2cb7d-160">USB-C Hubs</span></span>

<span data-ttu-id="2cb7d-161">Vissa användare kan behöva ansluta flera enheter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="2cb7d-162">För användare som vill använda en [USB-C-mikrofon](#usb-c-external-microphone-support) tillsammans med en annan ansluten enhet kan USB-C-hubbar passa kundens behov.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="2cb7d-163">Microsoft har inte testat dessa enheter och vi kan inte heller rekommendera några specifika varumärken.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="2cb7d-164">**Krav för USB-C-hubb och anslutna enheter:**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="2cb7d-165">Anslutna enheter får inte kräva att en drivrutin installeras.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="2cb7d-166">Det totala energisparet för alla anslutna enheter måste vara under 4,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="2cb7d-167">Ansluta till Miracast</span><span class="sxs-lookup"><span data-stu-id="2cb7d-167">Connect to Miracast</span></span>

<span data-ttu-id="2cb7d-168">Följ dessa steg om du vill använda Miracast:</span><span class="sxs-lookup"><span data-stu-id="2cb7d-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="2cb7d-169">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2cb7d-169">Do one of the following:</span></span>  

   - <span data-ttu-id="2cb7d-170">Öppna **Start-menyn** och välj **ikonen** Visa.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="2cb7d-171">Säg "Anslut" medan du tittar på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="2cb7d-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="2cb7d-172">I listan över enheter som visas väljer du en tillgänglig enhet.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="2cb7d-173">Slutför parkopplingen för att börja projicera.</span><span class="sxs-lookup"><span data-stu-id="2cb7d-173">Complete the pairing to begin projecting.</span></span>
