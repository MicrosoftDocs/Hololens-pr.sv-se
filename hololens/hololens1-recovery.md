---
title: Starta om, återställa eller återställa HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Hur du använder Windows Device Recovery-verktyget för att flasha en bild HoloLens första gen.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635236"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="386e7-104">Starta om, återställa eller HoloLens (första gen)</span><span class="sxs-lookup"><span data-stu-id="386e7-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="386e7-105">Om du har problem med din HoloLens kan du prova en omstart eller återställning eller till och med omsnedstrecka enheten med hjälp av enhetsåterställning.</span><span class="sxs-lookup"><span data-stu-id="386e7-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="386e7-106">Den här artikeln vägleder dig genom de rekommenderade återställningsstegen i rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="386e7-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="386e7-107">Om du vill återställa en HoloLens 2 kan du se Återställa [en HoloLens 2](hololens-recovery.md)eftersom processen skiljer sig åt.</span><span class="sxs-lookup"><span data-stu-id="386e7-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="386e7-108">Den här artikeln fokuserar på HoloLens enhet och programvara.</span><span class="sxs-lookup"><span data-stu-id="386e7-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="386e7-109">Om dina hologram inte ser bra ut kan du läsa HoloLens miljööverväganden för information om faktorer som förbättrar hologramkvaliteten. **[](hololens-environment-considerations.md)**</span><span class="sxs-lookup"><span data-stu-id="386e7-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="386e7-110">Starta om</span><span class="sxs-lookup"><span data-stu-id="386e7-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="386e7-111">Gör en säker omstart med hjälp av Cortana</span><span class="sxs-lookup"><span data-stu-id="386e7-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="386e7-112">Det säkraste sättet att starta om HoloLens är att använda Cortana, vilket vanligtvis är det första du försöker när du får problem med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="386e7-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="386e7-113">Cortana är inte tillgängligt på alla enheter.</span><span class="sxs-lookup"><span data-stu-id="386e7-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="386e7-114">Cortana är tillgängligt på alla HoloLens (första generationens) enheter.</span><span class="sxs-lookup"><span data-stu-id="386e7-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="386e7-115">Cortana finns på HoloLens 2 enheter på versioner före Windows Holograpic, version 2004.</span><span class="sxs-lookup"><span data-stu-id="386e7-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="386e7-116">Aktivera din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="386e7-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="386e7-117">Kontrollera att en användare är inloggad och att enheten inte väntar på ett lösenord för att låsa upp den.</span><span class="sxs-lookup"><span data-stu-id="386e7-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="386e7-118">Säg "Hej Cortana, starta om" eller "Hej Cortana starta om".</span><span class="sxs-lookup"><span data-stu-id="386e7-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="386e7-119">Cortana svarar och uppmanar dig att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="386e7-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="386e7-120">Vänta tills ett ljud spelas upp efter frågan och säg sedan "Ja".</span><span class="sxs-lookup"><span data-stu-id="386e7-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="386e7-121">Enheten startas om.</span><span class="sxs-lookup"><span data-stu-id="386e7-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="386e7-122">Använda strömknappen för att göra en säker omstart</span><span class="sxs-lookup"><span data-stu-id="386e7-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="386e7-123">Om du fortfarande inte kan starta om enheten kan  du prova att starta om den med strömknappen:</span><span class="sxs-lookup"><span data-stu-id="386e7-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="386e7-124">Tryck på och håll **ned strömknappen** i 5 sekunder.</span><span class="sxs-lookup"><span data-stu-id="386e7-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="386e7-125">Efter 1 sekund kommer alla fem lysdioderna att lysa och sedan långsamt stänga av en i ordning från höger till vänster.</span><span class="sxs-lookup"><span data-stu-id="386e7-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="386e7-126">Efter 5 sekunder är alla lysdioder avstängda, vilket indikerar att avstängningen lyckades.</span><span class="sxs-lookup"><span data-stu-id="386e7-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="386e7-127">Sluta trycka på knappen omedelbart efter att alla lysdioder har stängts av.</span><span class="sxs-lookup"><span data-stu-id="386e7-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="386e7-128">Vänta 1 minut tills avstängningen är klar.</span><span class="sxs-lookup"><span data-stu-id="386e7-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="386e7-129">Avstängningen kan fortfarande pågår även efter att skärmarna har stängts av.</span><span class="sxs-lookup"><span data-stu-id="386e7-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="386e7-130">Sätt på enheten igen genom att trycka på och hålla ned **strömknappen** i 1 sekund.</span><span class="sxs-lookup"><span data-stu-id="386e7-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="386e7-131">Göra en säker omstart med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="386e7-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="386e7-132">För den här HoloLens måste konfigureras som en utvecklarenhet.</span><span class="sxs-lookup"><span data-stu-id="386e7-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="386e7-133">Läs mer på [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="386e7-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="386e7-134">Om den föregående proceduren inte fungerade kan du prova att starta om enheten med hjälp av [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="386e7-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="386e7-135">I det övre högra hörnet hittar du alternativet att starta om eller stänga av enheten.</span><span class="sxs-lookup"><span data-stu-id="386e7-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="386e7-136">Göra en osäker framtvingade omstart</span><span class="sxs-lookup"><span data-stu-id="386e7-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="386e7-137">Om de föregående metoderna inte startade om HoloLens fram en omstart.</span><span class="sxs-lookup"><span data-stu-id="386e7-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="386e7-138">Den här metoden motsvarar att ta bort och installera om batteriet.</span><span class="sxs-lookup"><span data-stu-id="386e7-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="386e7-139">Det är riskabelt eftersom det kan göra att enheten är i ett skadat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="386e7-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="386e7-140">Om det händer måste du flasha HoloLens.</span><span class="sxs-lookup"><span data-stu-id="386e7-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="386e7-141">Det här är en potentiellt skadlig metod och bör endast användas om de tidigare citerade metoderna inte fungerade.</span><span class="sxs-lookup"><span data-stu-id="386e7-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="386e7-142">Tryck på och håll **ned strömknappen** i minst 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="386e7-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="386e7-143">Det är okej att hålla ned knappen i mer än 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="386e7-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="386e7-144">Det är säkert att ignorera all LED-aktivitet.</span><span class="sxs-lookup"><span data-stu-id="386e7-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="386e7-145">Släpp knappen och vänta i 2–3 sekunder.</span><span class="sxs-lookup"><span data-stu-id="386e7-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="386e7-146">Tryck och håll ned **strömknappen** i 1 sekund.</span><span class="sxs-lookup"><span data-stu-id="386e7-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="386e7-147">Om du fortfarande har  problem trycker du på strömknappen i 4 sekunder tills alla batteriindikatorer tonas ut och skärmen slutar att visa hologram.</span><span class="sxs-lookup"><span data-stu-id="386e7-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="386e7-148">Vänta 1 minut och tryck sedan på **strömknappen** igen för att aktivera enheten.</span><span class="sxs-lookup"><span data-stu-id="386e7-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="386e7-149">Gå tillbaka till en tidigare version – HoloLens (första gen)</span><span class="sxs-lookup"><span data-stu-id="386e7-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="386e7-150">I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens programvara.</span><span class="sxs-lookup"><span data-stu-id="386e7-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="386e7-151">Du kan göra detta med hjälp av Windows Device Recovery Tool för att återställa HoloLens till den tidigare versionen.</span><span class="sxs-lookup"><span data-stu-id="386e7-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="386e7-152">När du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.</span><span class="sxs-lookup"><span data-stu-id="386e7-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="386e7-153">Om du vill gå tillbaka till en tidigare version HoloLens 1 följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="386e7-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="386e7-154">Kontrollera att du inte har några telefoner eller enheter Windows anslutna till datorn.</span><span class="sxs-lookup"><span data-stu-id="386e7-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="386e7-155">På datorn laddar du ned [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="386e7-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="386e7-156">Ladda ned [HoloLens Anniversary Update-återställningspaketet](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="386e7-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="386e7-157">När hämtningen är klar öppnar du **Filutforskaren**  >  **Hämtar**.</span><span class="sxs-lookup"><span data-stu-id="386e7-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="386e7-158">Högerklicka på den komprimerade mappen som du precis laddade ned och välj **Extrahera alla**  >  **extrahera** för att packa upp den.</span><span class="sxs-lookup"><span data-stu-id="386e7-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="386e7-159">Anslut din HoloLens datorn med hjälp av den mikro-USB-kabel som den medkom med.</span><span class="sxs-lookup"><span data-stu-id="386e7-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="386e7-160">(Även om du har använt andra kablar för att ansluta HoloLens fungerar den här bäst.)</span><span class="sxs-lookup"><span data-stu-id="386e7-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="386e7-161">WDRT identifierar automatiskt HoloLens.</span><span class="sxs-lookup"><span data-stu-id="386e7-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="386e7-162">Välj **Microsoft HoloLens** panelen.</span><span class="sxs-lookup"><span data-stu-id="386e7-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="386e7-163">På nästa skärm väljer du **Manuellt paketval och** väljer installationsfilen som finns i mappen som du packade upp i steg 4.</span><span class="sxs-lookup"><span data-stu-id="386e7-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="386e7-164">(Leta efter en fil med filnamnstillägget .ffu.)</span><span class="sxs-lookup"><span data-stu-id="386e7-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="386e7-165">Välj **Installera programvara** och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="386e7-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="386e7-166">Om WDRT inte identifierar dina HoloLens provar du att starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="386e7-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="386e7-167">Om det inte fungerar väljer du **Min enhet har inte identifierats,** väljer **Microsoft HoloLens** och följer sedan anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="386e7-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="386e7-168">Återställa till fabriksinställningarna</span><span class="sxs-lookup"><span data-stu-id="386e7-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="386e7-169">Batteriet behöver minst en 40-procentig avgift för att återställas.</span><span class="sxs-lookup"><span data-stu-id="386e7-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="386e7-170">Om ditt HoloLens fortfarande har problem kan du försöka återställa det till fabrikstillstånd.</span><span class="sxs-lookup"><span data-stu-id="386e7-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="386e7-171">Det här steget behåller versionen av Windows Holographic-programvara som är installerad på den och returnerar allt annat till fabriksinställningarna.</span><span class="sxs-lookup"><span data-stu-id="386e7-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="386e7-172">Om du återställer enheten raderas alla personliga data, appar och inställningar, inklusive information om TPM-återställning.</span><span class="sxs-lookup"><span data-stu-id="386e7-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="386e7-173">Återställning installerar endast den senaste installerade versionen av Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="386e7-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="386e7-174">Du måste göra om alla initieringssteg (kalibrera, ansluta till Wi-Fi, skapa ett användarkonto, ladda ned appar och så vidare).</span><span class="sxs-lookup"><span data-stu-id="386e7-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="386e7-175">Öppna appen Inställningar och välj sedan **Uppdatera**  >  **återställning.**</span><span class="sxs-lookup"><span data-stu-id="386e7-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="386e7-176">Välj alternativet **Återställ enhet** och läs bekräftelsemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="386e7-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="386e7-177">Bekräfta återställningen.</span><span class="sxs-lookup"><span data-stu-id="386e7-177">Confirm the reset.</span></span> <span data-ttu-id="386e7-178">Enheten startar om och visar en uppsättning snurrande kugghjul och en förloppsstapel.</span><span class="sxs-lookup"><span data-stu-id="386e7-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="386e7-179">Vänta ungefär 30 minuter på att den här processen ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="386e7-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="386e7-180">När det är klart startas enheten om till "out-of-the-box"-upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="386e7-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="386e7-181">Installera om operativsystemet</span><span class="sxs-lookup"><span data-stu-id="386e7-181">Reinstall the operating system</span></span>

<span data-ttu-id="386e7-182">Om enheten fortfarande har problem efter omstart och återställning kan du använda ett återställningsverktyg på datorn för att installera om HoloLens operativsystem och inbyggd programvara.</span><span class="sxs-lookup"><span data-stu-id="386e7-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="386e7-183">De data HoloLens behöver för återställningen paketeras i en fullständig Flash-uppdatering (FFU), som liknar en ISO-, WIM- eller VHD-fil.</span><span class="sxs-lookup"><span data-stu-id="386e7-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="386e7-184">Läs mer om FFU-bildfilformat.</span><span class="sxs-lookup"><span data-stu-id="386e7-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="386e7-185">Du kan installera ett nytt operativsystem på din HoloLens (första generationen) med hjälp av Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="386e7-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="386e7-186">Innan du använder verktyget bör du se om det löser problemet genom HoloLens starta om eller återställa datorn.</span><span class="sxs-lookup"><span data-stu-id="386e7-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="386e7-187">Återställningsprocessen kan ta en stund.</span><span class="sxs-lookup"><span data-stu-id="386e7-187">The recovery process may take a while.</span></span> <span data-ttu-id="386e7-188">När det är klart installeras den senaste versionen Windows Holographic-programvara.</span><span class="sxs-lookup"><span data-stu-id="386e7-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="386e7-189">Om du vill använda verktyget behöver du en dator Windows 10 eller senare med minst 4 GB ledigt lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="386e7-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="386e7-190">Du kan inte köra det här verktyget på en virtuell dator.</span><span class="sxs-lookup"><span data-stu-id="386e7-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="386e7-191">Återställa HoloLens</span><span class="sxs-lookup"><span data-stu-id="386e7-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="386e7-192">Ladda ned och installera [Windows Device Recovery-verktyget](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) på datorn.</span><span class="sxs-lookup"><span data-stu-id="386e7-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="386e7-193">Anslut till HoloLens (1:a gen) till datorn med hjälp av Micro USB-kabeln som medkom med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="386e7-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="386e7-194">Öppna verktyget Windows Device Recovery och följ anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="386e7-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="386e7-195">Om HoloLens (1:a gen) inte identifieras automatiskt väljer du **Min enhet identifierades inte.**</span><span class="sxs-lookup"><span data-stu-id="386e7-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="386e7-196">Följ sedan anvisningarna för att föra enheten i återställningsläge.</span><span class="sxs-lookup"><span data-stu-id="386e7-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="386e7-197">Manuellt flashläge</span><span class="sxs-lookup"><span data-stu-id="386e7-197">Manual flashing mode</span></span>

<span data-ttu-id="386e7-198">Om enheten inte identifieras följer du dessa steg för att föra den i flashläge:</span><span class="sxs-lookup"><span data-stu-id="386e7-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="386e7-199">Koppla från enheten från valfri strömkälla.</span><span class="sxs-lookup"><span data-stu-id="386e7-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="386e7-200">Om enheten är på håller du ned **strömknappen** tills den stängs av helt.</span><span class="sxs-lookup"><span data-stu-id="386e7-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="386e7-201">Håll volymen **uppåt och** tryck en kort stund **på strömknappen.**</span><span class="sxs-lookup"><span data-stu-id="386e7-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="386e7-202">Enheten bör endast starta och visa den mittersta lysdioden.</span><span class="sxs-lookup"><span data-stu-id="386e7-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="386e7-203">Anslut enheten till datorn.</span><span class="sxs-lookup"><span data-stu-id="386e7-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="386e7-204">Öppna Windows Device Recovery.</span><span class="sxs-lookup"><span data-stu-id="386e7-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="386e7-205">Välj **Min enhet har inte identifierats** och välj **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="386e7-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="386e7-206">Följ instruktionerna för att återställa enheten.</span><span class="sxs-lookup"><span data-stu-id="386e7-206">Follow the instructions to recover your device.</span></span>
