---
title: Starta om, återställa eller HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Använda Advanced Recovery Companion för att flasha en bild till HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635950"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="7fd94-104">Starta om, återställa eller återställa HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7fd94-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="7fd94-105">Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="7fd94-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="7fd94-106">Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="7fd94-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="7fd94-107">Använd kabeln [och USB Type-C-kabeln](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) som medkom med HoloLens 2 eftersom det är det bästa sättet att debitera enheten.</span><span class="sxs-lookup"><span data-stu-id="7fd94-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="7fd94-108">Nätaggregatet levererar 18 W ström (9V vid 2A).</span><span class="sxs-lookup"><span data-stu-id="7fd94-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="7fd94-109">Med medföljande väggutrustning kan HoloLens 2 enheter ladda upp batteriet till full på mindre än 65 minuter när enheten är i vänteläge.</span><span class="sxs-lookup"><span data-stu-id="7fd94-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="7fd94-110">Om tillbehören inte är tillgängliga kontrollerar du att de tillgängliga strömerna har stöd för minst 15 W ström.</span><span class="sxs-lookup"><span data-stu-id="7fd94-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="7fd94-111">Om möjligt bör du undvika att använda en dator för att debitera enheten via USB, vilket är långsamt.</span><span class="sxs-lookup"><span data-stu-id="7fd94-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="7fd94-112">Om enheten är korrekt startad och körs finns det tre sätt att kontrollera batteriladdningsnivån:</span><span class="sxs-lookup"><span data-stu-id="7fd94-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="7fd94-113">På huvudmenyn i HoloLens enhetens användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="7fd94-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="7fd94-114">Visa lysdioden nära strömknappen (för en avgift på 40 procent bör du se minst två solida lysdioder).</span><span class="sxs-lookup"><span data-stu-id="7fd94-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="7fd94-115">När enheten laddas tänds batteriindikatorn för att ange den aktuella avgiftsnivån.</span><span class="sxs-lookup"><span data-stu-id="7fd94-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="7fd94-116">Det sista lampan tonas in och ut för att indikera aktiv laddning.</span><span class="sxs-lookup"><span data-stu-id="7fd94-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="7fd94-117">När HoloLens är på visar batteriindikatorn batterinivån i fem steg.</span><span class="sxs-lookup"><span data-stu-id="7fd94-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="7fd94-118">När bara en av de fem lamporna är på är batterinivån under 20 procent.</span><span class="sxs-lookup"><span data-stu-id="7fd94-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="7fd94-119">Om batterinivån är kritiskt låg och du försöker slå på enheten blinkar en lampa en kort stund och går sedan ut.</span><span class="sxs-lookup"><span data-stu-id="7fd94-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="7fd94-120">På värddatorn öppnar du **Utforskaren** och letar efter din HoloLens 2-enhet till vänster under **Den här datorn**.</span><span class="sxs-lookup"><span data-stu-id="7fd94-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="7fd94-121">Högerklicka på enheten och välj **Egenskaper.**</span><span class="sxs-lookup"><span data-stu-id="7fd94-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="7fd94-122">En dialogruta visar batteriladdningsnivån.</span><span class="sxs-lookup"><span data-stu-id="7fd94-122">A dialog box will show the battery charge level.</span></span>

   ![En HoloLens 2-egenskapsskärm visar batteriändringsnivå](images/ResetRecovery2.png)

<span data-ttu-id="7fd94-124">Observera LED-utseendet och enhetsuppräkningen på värddatorn om enheten inte kan starta på startmenyn.</span><span class="sxs-lookup"><span data-stu-id="7fd94-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="7fd94-125">Följ sedan [felsökningsguiden](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="7fd94-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="7fd94-126">Om enhetens tillstånd inte matchar något av tillstånden som anges [](hololens-recovery.md#hard-reset-procedure) i felsökningsguiden utför du proceduren för hårdåterställning med enheten som är ansluten till strömförsörjningen, inte till din värddator.</span><span class="sxs-lookup"><span data-stu-id="7fd94-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="7fd94-127">Vänta minst en timme på att enheten ska debiteras.</span><span class="sxs-lookup"><span data-stu-id="7fd94-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="7fd94-128">Återställa enheten</span><span class="sxs-lookup"><span data-stu-id="7fd94-128">Reset the device</span></span>

<span data-ttu-id="7fd94-129">Under vissa omständigheter kan du behöva återställa enheten manuellt utan att använda användargränssnittet för programvaran.</span><span class="sxs-lookup"><span data-stu-id="7fd94-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="7fd94-130">Standardprocedur</span><span class="sxs-lookup"><span data-stu-id="7fd94-130">Standard procedure</span></span>

1. <span data-ttu-id="7fd94-131">Koppla från Type-C-kabeln för att koppla bort enheten från strömförsörjningen eller värddatorn.</span><span class="sxs-lookup"><span data-stu-id="7fd94-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="7fd94-132">Tryck och håll ned **strömknappen** i 15 sekunder.</span><span class="sxs-lookup"><span data-stu-id="7fd94-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="7fd94-133">Alla lysdioder ska vara avstängda.</span><span class="sxs-lookup"><span data-stu-id="7fd94-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="7fd94-134">Vänta 2–3 sekunder och tryck sedan kort på **strömknappen.**</span><span class="sxs-lookup"><span data-stu-id="7fd94-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="7fd94-135">Lysdioderna nära strömknappen tänds och enheten börjar starta.</span><span class="sxs-lookup"><span data-stu-id="7fd94-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="7fd94-136">Anslut enheten till värddatorn och öppna sedan Enhetshanteraren.</span><span class="sxs-lookup"><span data-stu-id="7fd94-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="7fd94-137">(För Windows 10 trycker du **Windows** tangenten och sedan **på X** och väljer **sedan Enhetshanteraren**.) Kontrollera att enheten räknas upp korrekt enligt *Microsoft HoloLens* som visas i följande bild:</span><span class="sxs-lookup"><span data-stu-id="7fd94-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="7fd94-139">Procedur för hård återställning</span><span class="sxs-lookup"><span data-stu-id="7fd94-139">Hard-reset procedure</span></span>

<span data-ttu-id="7fd94-140">Om standardåterställningen inte fungerade använder du proceduren för hård återställning:</span><span class="sxs-lookup"><span data-stu-id="7fd94-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="7fd94-141">Koppla från Type-C-kabeln för att koppla bort enheten från strömförsörjningen eller värddatorn.</span><span class="sxs-lookup"><span data-stu-id="7fd94-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="7fd94-142">Håll ned **strömknapparna**  +  **för volymen** i 15 sekunder.</span><span class="sxs-lookup"><span data-stu-id="7fd94-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="7fd94-143">Enheten startas om automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7fd94-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="7fd94-144">Anslut till värddatorn.</span><span class="sxs-lookup"><span data-stu-id="7fd94-144">Connect the device to the host PC.</span></span>


5. <span data-ttu-id="7fd94-145">Öppna Enhetshanteraren (för Windows 10 trycker **du Windows** tangenten och sedan **på X-tangenten** och väljer sedan **Enhetshanteraren**).</span><span class="sxs-lookup"><span data-stu-id="7fd94-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="7fd94-146">Kontrollera att enheten räknas upp korrekt enligt *Microsoft HoloLens* som visas i följande bild:</span><span class="sxs-lookup"><span data-stu-id="7fd94-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery device maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="7fd94-148">Rensa omstreck på enheten</span><span class="sxs-lookup"><span data-stu-id="7fd94-148">Clean-reflash the device</span></span>

<span data-ttu-id="7fd94-149">I svåra situationer kan du behöva "rensa flash"-HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7fd94-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="7fd94-150">Observera att clean-reflash inte förväntas påverka följande problem:</span><span class="sxs-lookup"><span data-stu-id="7fd94-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="7fd94-151">Visa färguniformitet</span><span class="sxs-lookup"><span data-stu-id="7fd94-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="7fd94-152">Starta med ljud men inga visningsutdata</span><span class="sxs-lookup"><span data-stu-id="7fd94-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="7fd94-153">1-3-5-LED-mönster</span><span class="sxs-lookup"><span data-stu-id="7fd94-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="7fd94-154">Överhettning</span><span class="sxs-lookup"><span data-stu-id="7fd94-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="7fd94-155">OS-krascher (som skiljer sig från programkrasch)</span><span class="sxs-lookup"><span data-stu-id="7fd94-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="7fd94-156">Det finns två sätt att omsnedstrecka enheten.</span><span class="sxs-lookup"><span data-stu-id="7fd94-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="7fd94-157">För båda måste du först installera [Advanced Recovery Companion från Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="7fd94-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="7fd94-158">Om du omskär enheten raderas alla personliga data, appar och inställningar, inklusive information om TPM-återställning.</span><span class="sxs-lookup"><span data-stu-id="7fd94-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="7fd94-159">Som standard är Advanced Recovery Companion inställt på att ladda ned [](hololens-release-notes.md#) den senaste versionen av funktionen. Läs vår viktig information här om du vill veta mer om den senaste versionen av funktionen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="7fd94-160">Om du vill hämta det senaste paketet HoloLens 2 Full Flash Update (FFU) för att omsnedstrecka enheten via Advanced Recovery Companion klickar du här för att ladda ned den senaste [månatliga HoloLens 2-avbildningen](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="7fd94-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="7fd94-161">Den här versionen är den senaste allmänt tillgängliga versionen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="7fd94-162">Innan du startar omstrecksproceduren kontrollerar du att appen är installerad och körs Windows 10 datorn och redo att identifiera enheten.</span><span class="sxs-lookup"><span data-stu-id="7fd94-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="7fd94-163">Se också till att HoloLens debiteras till minst 40 %.</span><span class="sxs-lookup"><span data-stu-id="7fd94-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 skärmdump med ett rent omstreck](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="7fd94-165">Normal procedur</span><span class="sxs-lookup"><span data-stu-id="7fd94-165">Normal procedure</span></span>

1. <span data-ttu-id="7fd94-166">När HoloLens körs ansluter du den till den Windows 10 datorn där du tidigare öppnade appen Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="7fd94-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="7fd94-167">Enheten identifieras automatiskt och användargränssnittet för appen Advanced Recovery startar uppdateringsprocessen:</span><span class="sxs-lookup"><span data-stu-id="7fd94-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 rensade omstreck första skärmen](images/ARC2.png)

3. <span data-ttu-id="7fd94-169">Välj enheten HoloLens 2 i appen Advanced Recovery Companion och följ instruktionerna för att slutföra omstrecket.</span><span class="sxs-lookup"><span data-stu-id="7fd94-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="7fd94-170">Manuell procedur</span><span class="sxs-lookup"><span data-stu-id="7fd94-170">Manual procedure</span></span>

<span data-ttu-id="7fd94-171">Om HoloLens 2 inte startar korrekt eller om Advanced Recovery Companion inte kan identifiera enheten kan du behöva föra in enheten i återställningsläge:</span><span class="sxs-lookup"><span data-stu-id="7fd94-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="7fd94-172">Koppla från Type-C-kabeln för att koppla bort enheten från strömförsörjningen eller värddatorn.</span><span class="sxs-lookup"><span data-stu-id="7fd94-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="7fd94-173">Tryck och håll ned **strömknappen** i 15 sekunder.</span><span class="sxs-lookup"><span data-stu-id="7fd94-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="7fd94-174">Alla lysdioder bör stängas av.</span><span class="sxs-lookup"><span data-stu-id="7fd94-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="7fd94-175">När du trycker **på knappen för** att öka volymen trycker du på och släpper **strömknappen** för att starta enheten.</span><span class="sxs-lookup"><span data-stu-id="7fd94-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="7fd94-176">Vänta i 15 sekunder och släpp sedan **knappen volym** upp.</span><span class="sxs-lookup"><span data-stu-id="7fd94-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="7fd94-177">Endast den mittersta leden av de fem lysdioderna tänds.</span><span class="sxs-lookup"><span data-stu-id="7fd94-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="7fd94-178">Anslut enheten till värddatorn och öppna Enhetshanteraren.</span><span class="sxs-lookup"><span data-stu-id="7fd94-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="7fd94-179">(För Windows 10 trycker **Windows** tangenten och sedan **på X** och väljer sedan **Enhetshanteraren**.) Kontrollera att enheten räknas upp korrekt enligt Microsoft HoloLens som visas i följande bild:</span><span class="sxs-lookup"><span data-stu-id="7fd94-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="7fd94-181">Enheten identifieras automatiskt och användargränssnittet för appen Advanced Recovery startar uppdateringsprocessen:</span><span class="sxs-lookup"><span data-stu-id="7fd94-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 rensade omstrecksskärm](images/ARC2.png)

6. <span data-ttu-id="7fd94-183">Välj enheten HoloLens 2 i appen Advanced Recovery Companion och följ sedan anvisningarna för att slutföra omstrecket.</span><span class="sxs-lookup"><span data-stu-id="7fd94-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="7fd94-184">Felsöka Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="7fd94-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="7fd94-185">Se till att enheten debiteras till 40 % eller mer innan du försöker flasha.</span><span class="sxs-lookup"><span data-stu-id="7fd94-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="7fd94-186">Kontrollera att enheten är upplåst.</span><span class="sxs-lookup"><span data-stu-id="7fd94-186">Check your device is unlocked.</span></span>

1. <span data-ttu-id="7fd94-187">Kontrollera att enheten är ansluten direkt till värddatorn, inte en hubb.</span><span class="sxs-lookup"><span data-stu-id="7fd94-187">Check your device is plugged directly into the host PC, not a hub.</span></span>

1. <span data-ttu-id="7fd94-188">Om enheten inte visas som en HoloLens/HoloLens Recovery-enhet under Drivrutiner för universella seriebussdrivrutiner kontrollerar du:</span><span class="sxs-lookup"><span data-stu-id="7fd94-188">If your device is not showing as a HoloLens/HoloLens Recovery device under Universal Serial Bus Drivers, check:</span></span>
    1. <span data-ttu-id="7fd94-189">**Portar**, som en Qualcomm HS-USB-enhet</span><span class="sxs-lookup"><span data-stu-id="7fd94-189">**Ports**, as a Qualcomm HS-USB device</span></span>
    1.   <span data-ttu-id="7fd94-190">**Andra enheter**, som en QUSB_BULK enhet – värddatorn saknar nödvändiga drivrutiner för att identifiera HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7fd94-190">**Other Devices**, as a QUSB_BULK device - your host PC is missing the necessary drivers to detect your HoloLens.</span></span> <span data-ttu-id="7fd94-191">Högerklicka och välj Uppdatera drivrutin och sök efter drivrutiner online eller [markera Valfria uppdateringar i Windows uppdatera inställningarna.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)</span><span class="sxs-lookup"><span data-stu-id="7fd94-191">Right click and select Update Driver and search for drivers online or [check Optional Updates in your Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span></span> <span data-ttu-id="7fd94-192">När drivrutinen har laddats ned ska ARC kunna identifiera den.</span><span class="sxs-lookup"><span data-stu-id="7fd94-192">After the driver is downloaded, ARC should be able to detect it.</span></span>
 
1. <span data-ttu-id="7fd94-193">Om ARC inte identifierar din enhet ser du till att du kan ansluta till enheten via Utforskaren på datorn.</span><span class="sxs-lookup"><span data-stu-id="7fd94-193">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="7fd94-194">Om du inte kan;</span><span class="sxs-lookup"><span data-stu-id="7fd94-194">If you cannot;</span></span>

    1.  <span data-ttu-id="7fd94-195">Det är möjligt att enheten har USB-principer som inaktiverar anslutningen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-195">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="7fd94-196">I så fall kan [du prova manuellt flashläge](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="7fd94-196">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="7fd94-197">Om det inte finns några principer kan du prova en annan USB-kabel.</span><span class="sxs-lookup"><span data-stu-id="7fd94-197">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="7fd94-198">Kontrollera att enheten inte visar ett [1-3-5-LED-mönster.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="7fd94-198">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="7fd94-199">Ladda ned ARC utan att använda App Store</span><span class="sxs-lookup"><span data-stu-id="7fd94-199">Download ARC without using the app store</span></span>

<span data-ttu-id="7fd94-200">Om IT-miljön förhindrar användning av Windows Store-appen eller begränsar åtkomsten till butiken, kan IT-administratören göra den här appen tillgänglig via en "offline"-distributionssökväg.</span><span class="sxs-lookup"><span data-stu-id="7fd94-200">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="7fd94-201">IT-administratörer kan också distribuera den här appen via System Center Configuration Manager (SCCM) eller Intune.</span><span class="sxs-lookup"><span data-stu-id="7fd94-201">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="7fd94-202">Den här guiden fokuserar på Advanced Recovery Companion, men processen kan även användas för andra "offline"-appar.</span><span class="sxs-lookup"><span data-stu-id="7fd94-202">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="7fd94-203">Följ dessa steg för att aktivera distributionssökvägen:</span><span class="sxs-lookup"><span data-stu-id="7fd94-203">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="7fd94-204">Gå till [Microsoft Store för företag](https://businessstore.microsoft.com) och logga in med en Azure Active Directory identitet.</span><span class="sxs-lookup"><span data-stu-id="7fd94-204">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="7fd94-205">Gå till **Hantera – Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="7fd94-205">Go to **Manage – Settings**.</span></span> <span data-ttu-id="7fd94-206">Aktivera Visa **offlineappar** under **Shoppingupplevelse.**</span><span class="sxs-lookup"><span data-stu-id="7fd94-206">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="7fd94-207">Gå till **butiken för min grupp** och sök efter Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="7fd94-207">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="7fd94-208">Ändra **Licenstyp till** \**_offline_*_, och välj _\* Hantera\*\*.</span><span class="sxs-lookup"><span data-stu-id="7fd94-208">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="7fd94-209">Under **Ladda ned paketet för offlineanvändning** väljer du den andra blå **nedladdningsknappen.**</span><span class="sxs-lookup"><span data-stu-id="7fd94-209">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="7fd94-210">Kontrollera att filnamnstillägget är *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="7fd94-210">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="7fd94-211">I det här skedet, om skrivbordsdatorn har Internetåtkomst, dubbelklickar du på paketet för att installera appen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-211">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="7fd94-212">Om måldatorn inte har någon Internetanslutning följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="7fd94-212">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="7fd94-213">Välj den okodade licensen och välj sedan **Generera licens.**</span><span class="sxs-lookup"><span data-stu-id="7fd94-213">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="7fd94-214">Under **Nödvändiga ramverk väljer** du Ladda **ned**.</span><span class="sxs-lookup"><span data-stu-id="7fd94-214">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="7fd94-215">Använd DISM för att tillämpa paketet med beroendet och licensen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-215">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="7fd94-216">Kör följande kommando från en administratörs kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="7fd94-216">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="7fd94-217">Versionsnumret i det här kodexe exemplet kanske inte matchar den tillgängliga versionen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-217">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="7fd94-218">Du kan också ha valt en annan nedladdningsplats än i exemplet.</span><span class="sxs-lookup"><span data-stu-id="7fd94-218">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="7fd94-219">Gör eventuella ändringar i kommandot efter behov.</span><span class="sxs-lookup"><span data-stu-id="7fd94-219">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="7fd94-220">När du planerar att använda Advanced Recovery Companion för att installera en FFU offline kan det vara användbart att ladda ned flash-avbildningen.</span><span class="sxs-lookup"><span data-stu-id="7fd94-220">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="7fd94-221">[**Ladda ned den aktuella avbildningen för HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="7fd94-221">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="7fd94-222">Andra resurser:</span><span class="sxs-lookup"><span data-stu-id="7fd94-222">Other resources:</span></span>
- [<span data-ttu-id="7fd94-223">Distribuera offlineappar</span><span class="sxs-lookup"><span data-stu-id="7fd94-223">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="7fd94-224">DISM-appaket (.appx eller .appxbundle) för kommandoradsalternativ</span><span class="sxs-lookup"><span data-stu-id="7fd94-224">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
