---
title: Vanliga frågor och svar om HoloLens-enheter och hologram
description: Har du en snabb fråga om HoloLens eller interagerar du med hologram?  Den här artikeln innehåller ett snabbt svar och fler resurser.
keywords: hololens, faq, known issue, help
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924034"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="d6882-105">Felsökning av hologram och interaktioner</span><span class="sxs-lookup"><span data-stu-id="d6882-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="d6882-106">Den här artikeln felsöker problem med att placera hologram, arbeta med utrymmen och rapportera problem med hologram.</span><span class="sxs-lookup"><span data-stu-id="d6882-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="d6882-107">När du har problem bör du se till att:</span><span class="sxs-lookup"><span data-stu-id="d6882-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="d6882-108">Prova [att starta om den](hololens-restart-recover.md) för att se om det åtgärdar något.</span><span class="sxs-lookup"><span data-stu-id="d6882-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="d6882-109">Innan du felsöker ska du se till att HoloLens [debiteras](hololens2-charging.md) (debiteras i minst en timme).</span><span class="sxs-lookup"><span data-stu-id="d6882-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="d6882-110">Använd feedbackappen för att skicka information om problemet till oss.</span><span class="sxs-lookup"><span data-stu-id="d6882-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="d6882-111">Du hittar feedbackappen på [ **Start-menyn**](holographic-home.md).</span><span class="sxs-lookup"><span data-stu-id="d6882-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="d6882-112">Tips om hur du använder HoloLens finns i [Justera anpassning.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="d6882-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="d6882-113">Det går inte att skapa nya blanksteg</span><span class="sxs-lookup"><span data-stu-id="d6882-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="d6882-114">Blanksteg kan inte identifieras eller läsas in</span><span class="sxs-lookup"><span data-stu-id="d6882-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="d6882-115">Hur gör jag för att ta bort alla blanksteg?</span><span class="sxs-lookup"><span data-stu-id="d6882-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="d6882-116">Hologram ser inte rätt ut eller flyttas runt</span><span class="sxs-lookup"><span data-stu-id="d6882-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="d6882-117">Meddelandet "Hitta ditt utrymme"</span><span class="sxs-lookup"><span data-stu-id="d6882-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="d6882-118">Förväntade hologram visas inte i mitt utrymme</span><span class="sxs-lookup"><span data-stu-id="d6882-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="d6882-119">Det går inte att placera hologram eller se hologram som placerats tidigare</span><span class="sxs-lookup"><span data-stu-id="d6882-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="d6882-120">Hologram försvinner eller är inkapslade i andra hologram eller objekt</span><span class="sxs-lookup"><span data-stu-id="d6882-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="d6882-121">Hologram visas på andra sidan av en vägg</span><span class="sxs-lookup"><span data-stu-id="d6882-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="d6882-122">När du har placerat ett hologram på en vägg verkar det flyta</span><span class="sxs-lookup"><span data-stu-id="d6882-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="d6882-123">Appar visas för nära efter att de har flyttats</span><span class="sxs-lookup"><span data-stu-id="d6882-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="d6882-124">Rapportera problem med instabila eller inexakta hologram</span><span class="sxs-lookup"><span data-stu-id="d6882-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="d6882-125">Det går inte att skapa nya blanksteg</span><span class="sxs-lookup"><span data-stu-id="d6882-125">New spaces can't be created</span></span>

<span data-ttu-id="d6882-126">Det mest sannolika problemet är att du börjar få ont om lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="d6882-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="d6882-127">[Frigör diskutrymme och](hololens-troubleshooting.md#low-disk-space-error) försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="d6882-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="d6882-128">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="d6882-129">Blanksteg kan inte identifieras eller läsas in</span><span class="sxs-lookup"><span data-stu-id="d6882-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="d6882-130">Om hololens inte kan identifiera och läsa in det utrymme som du använder automatiskt kontrollerar du följande faktorer:</span><span class="sxs-lookup"><span data-stu-id="d6882-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="d6882-131">Kontrollera att du är ansluten till Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6882-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="d6882-132">Se till att det finns gott om ljus i rummet</span><span class="sxs-lookup"><span data-stu-id="d6882-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="d6882-133">Se till att det inte har skett några större förändringar i miljön.</span><span class="sxs-lookup"><span data-stu-id="d6882-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="d6882-134">Du kan också läsa in ett utrymme manuellt eller hantera dina utrymmen genom att gå **till**  >  **Inställningar**  >  **Systemutrymmen**.</span><span class="sxs-lookup"><span data-stu-id="d6882-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="d6882-135">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="d6882-136">Hur gör jag för att ta bort alla blanksteg?</span><span class="sxs-lookup"><span data-stu-id="d6882-136">How do I delete all spaces?</span></span>

<span data-ttu-id="d6882-137">*Kommer snart*</span><span class="sxs-lookup"><span data-stu-id="d6882-137">*Coming soon*</span></span>

[<span data-ttu-id="d6882-138">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="d6882-139">Hologram ser inte rätt ut eller flyttas runt</span><span class="sxs-lookup"><span data-stu-id="d6882-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="d6882-140">Om dina hologram inte ser rätt ut (till exempel om de är jitteriga eller skakiga, eller om du ser svarta korrigeringar ovanpå dem) kan du prova någon av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d6882-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="d6882-141">[Rensa enhetsvisorn och](hololens1-hardware.md#care-and-cleaning) se till att inget blockerar sensorerna.</span><span class="sxs-lookup"><span data-stu-id="d6882-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="d6882-142">Se till att du är i ett välbelyst rum som inte har så mycket direkt belysning.</span><span class="sxs-lookup"><span data-stu-id="d6882-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="d6882-143">Prova att gå runt och titta på din miljö så att HoloLens kan genomsöka dem mer fullständigt.</span><span class="sxs-lookup"><span data-stu-id="d6882-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="d6882-144">Om du har placerat många hologram kan du prova att ta bort några.</span><span class="sxs-lookup"><span data-stu-id="d6882-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="d6882-145">Om du fortfarande har problem kan du prova att köra kalibreringsappen.</span><span class="sxs-lookup"><span data-stu-id="d6882-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="d6882-146">Den här appen kalibrerar HoloLens så att du kan hålla dina hologram så bra som möjligt.</span><span class="sxs-lookup"><span data-stu-id="d6882-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="d6882-147">Det gör du genom att gå **till**  >  **Inställningar**  >  **Systemverktyg.**</span><span class="sxs-lookup"><span data-stu-id="d6882-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="d6882-148">Under **Kalibrering** väljer du **Öppna kalibrering**.</span><span class="sxs-lookup"><span data-stu-id="d6882-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="d6882-149">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="d6882-150">Meddelandet "Hitta ditt utrymme"</span><span class="sxs-lookup"><span data-stu-id="d6882-150">"Finding your space" message</span></span>

<span data-ttu-id="d6882-151">När HoloLens lär sig eller läser in ett utrymme kan du se ett kort meddelande som säger "Hitta ditt utrymme".</span><span class="sxs-lookup"><span data-stu-id="d6882-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="d6882-152">Om det här meddelandet visas i mer än några sekunder visas ett annat meddelande under Start-menyn där det står "Letar fortfarande efter ditt utrymme".</span><span class="sxs-lookup"><span data-stu-id="d6882-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="d6882-153">Dessa meddelanden innebär att HoloLens har problem med att mappa ditt utrymme.</span><span class="sxs-lookup"><span data-stu-id="d6882-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="d6882-154">När detta inträffar kan du öppna appar, men du kan inte placera hologram i din miljö.</span><span class="sxs-lookup"><span data-stu-id="d6882-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="d6882-155">Om du ser dessa meddelanden ofta kan du prova en eller flera av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d6882-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="d6882-156">Se till att du är i ett välbelyst rum som inte har så mycket direkt belysning.</span><span class="sxs-lookup"><span data-stu-id="d6882-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="d6882-157">Kontrollera att enhetsvisorn är ren.</span><span class="sxs-lookup"><span data-stu-id="d6882-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="d6882-158">[Lär dig hur du rensar din visor.](hololens1-hardware.md#care-and-cleaning)</span><span class="sxs-lookup"><span data-stu-id="d6882-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="d6882-159">Kontrollera att du har en stark Wi-Fi signal.</span><span class="sxs-lookup"><span data-stu-id="d6882-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="d6882-160">Om du anger en ny miljö som inte Wi-Fi eller en svag Wi-Fi signal kan HoloLens inte hitta ditt utrymme.</span><span class="sxs-lookup"><span data-stu-id="d6882-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="d6882-161">Kontrollera din Wi-Fi genom att gå till **Inställningar**  >  **&amp; Nätverkets**  >  **Internet-Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="d6882-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="d6882-162">Försök att flytta långsammare.</span><span class="sxs-lookup"><span data-stu-id="d6882-162">Try moving more slowly.</span></span>

[<span data-ttu-id="d6882-163">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="d6882-164">Förväntade hologram visas inte i mitt utrymme</span><span class="sxs-lookup"><span data-stu-id="d6882-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="d6882-165">Om du inte ser hologrammen som du har placerat, eller om du ser några som du inte förväntar dig, kan du prova en eller flera av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d6882-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="d6882-166">Tänd några lampor.</span><span class="sxs-lookup"><span data-stu-id="d6882-166">Turn on some lights.</span></span> <span data-ttu-id="d6882-167">HoloLens fungerar bäst i välbelysta utrymmen.</span><span class="sxs-lookup"><span data-stu-id="d6882-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="d6882-168">Ta bort hologram som du inte behöver genom att gå till **Inställningar**  >  **System**  >  **Hologram**  >  **Ta bort hologram i närheten.**</span><span class="sxs-lookup"><span data-stu-id="d6882-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="d6882-169">Om det behövs kan du också välja **Ta bort alla hologram**.</span><span class="sxs-lookup"><span data-stu-id="d6882-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d6882-170">Om layouten eller belysningen i utrymmet ändras avsevärt kan enheten ha problem med att identifiera ditt utrymme och visa dina hologram.</span><span class="sxs-lookup"><span data-stu-id="d6882-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="d6882-171">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="d6882-172">Det går inte att placera hologram eller se hologram som placerats tidigare</span><span class="sxs-lookup"><span data-stu-id="d6882-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="d6882-173">Om HoloLens inte kan mappa eller läsa in ditt utrymme går det in i begränsat läge och du kan inte placera hologram eller se hologram som du har placerat.</span><span class="sxs-lookup"><span data-stu-id="d6882-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="d6882-174">Här är några saker du kan prova:</span><span class="sxs-lookup"><span data-stu-id="d6882-174">Here are some things to try:</span></span>

- <span data-ttu-id="d6882-175">Se till att det finns tillräckligt med ljus i din miljö så att HoloLens kan se och mappa utrymmet.</span><span class="sxs-lookup"><span data-stu-id="d6882-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="d6882-176">Ställ dig mellan en och tre meter från den plats där du försöker placera hologrammet.</span><span class="sxs-lookup"><span data-stu-id="d6882-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="d6882-177">Placera inte hologram på svarta eller reflerande ytor.</span><span class="sxs-lookup"><span data-stu-id="d6882-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="d6882-178">Kontrollera att du är ansluten till ett Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="d6882-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="d6882-179">Om du inte är ansluten till Wi-Fi kan HoloLens inte identifiera och läsa in ett känt utrymme.</span><span class="sxs-lookup"><span data-stu-id="d6882-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="d6882-180">Gå igenom rum så att HoloLens kan genomsöka din miljö igen.</span><span class="sxs-lookup"><span data-stu-id="d6882-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="d6882-181">Om du vill se vad som redan genomsökts trycker du i luften för att visa kartnätsbilden.</span><span class="sxs-lookup"><span data-stu-id="d6882-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="d6882-182">Om du behöver skapa ett nytt utrymme ansluter du till Wi-Fi och startar sedan om HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d6882-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="d6882-183">Om du vill se om rätt utrymme är aktivt eller om du vill läsa in ett utrymme manuellt går du **till**  >  **Inställningar**  >  **Systemutrymmen**.</span><span class="sxs-lookup"><span data-stu-id="d6882-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="d6882-184">Om rätt utrymme läses in och du fortfarande har problem kan utrymmet vara skadat.</span><span class="sxs-lookup"><span data-stu-id="d6882-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="d6882-185">Åtgärda problemet genom att markera utrymmet och sedan välja Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="d6882-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="d6882-186">När du har tagit bort utrymmet börjar HoloLens mappa din miljö och skapa ett nytt utrymme.</span><span class="sxs-lookup"><span data-stu-id="d6882-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="d6882-187">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="d6882-188">Hologram försvinner eller är inkapslade i andra hologram eller objekt</span><span class="sxs-lookup"><span data-stu-id="d6882-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="d6882-189">Om du är för nära ett hologram försvinner det tillfälligt för &mdash; att återställa hologrammet. Du behöver bara flytta från det.</span><span class="sxs-lookup"><span data-stu-id="d6882-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="d6882-190">Om du har placerat flera hologram nära varandra kan vissa försvinna.</span><span class="sxs-lookup"><span data-stu-id="d6882-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="d6882-191">Prova att ta bort några.</span><span class="sxs-lookup"><span data-stu-id="d6882-191">Try removing a few.</span></span>

<span data-ttu-id="d6882-192">Hologram kan också blockeras eller vara omslutna av andra hologram eller av objekt som väggar.</span><span class="sxs-lookup"><span data-stu-id="d6882-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="d6882-193">Om detta inträffar kan du prova någon av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d6882-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="d6882-194">Om hologrammet är inkapslade i ett annat hologram flyttar du det inkapslade hologrammet till en annan plats.</span><span class="sxs-lookup"><span data-stu-id="d6882-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="d6882-195">Det gör du genom att **välja Justera** och sedan trycka och hålla kvar för att placera den.</span><span class="sxs-lookup"><span data-stu-id="d6882-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="d6882-196">Om hologrammet är omslutet på en vägg väljer du Justera **och** går sedan mot väggen tills hologrammet visas.</span><span class="sxs-lookup"><span data-stu-id="d6882-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="d6882-197">Tryck och håll ned och dra hologrammet framåt och från väggen.</span><span class="sxs-lookup"><span data-stu-id="d6882-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="d6882-198">Om du inte kan flytta hologrammet med hjälp av gester kan du använda rösten för att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="d6882-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="d6882-199">Titta på hologrammet och säg "Ta bort".</span><span class="sxs-lookup"><span data-stu-id="d6882-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="d6882-200">Öppna sedan hologrammet och placera det på en ny plats.</span><span class="sxs-lookup"><span data-stu-id="d6882-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="d6882-201">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="d6882-202">Hologram visas på andra sidan av en vägg</span><span class="sxs-lookup"><span data-stu-id="d6882-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="d6882-203">Om du är mycket nära en vägg, eller om HoloLens inte har skannat väggen ännu, kan du se hologram som finns i nästa rum.</span><span class="sxs-lookup"><span data-stu-id="d6882-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="d6882-204">Om du vill genomsöka vägg ska du stå mellan en och tre meter från väggen och titta på den.</span><span class="sxs-lookup"><span data-stu-id="d6882-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="d6882-205">Ett svart eller reflektivt objekt (till exempel en svartoffa eller ett kylskåp av metall) nära väggen kan orsaka problem när HoloLens försöker genomsöka väggen.</span><span class="sxs-lookup"><span data-stu-id="d6882-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="d6882-206">Om det finns ett sådant objekt genomsöker du den andra sidan av väggen.</span><span class="sxs-lookup"><span data-stu-id="d6882-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="d6882-207">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="d6882-208">När du har placerat ett hologram på en vägg verkar det flyta</span><span class="sxs-lookup"><span data-stu-id="d6882-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="d6882-209">Ett hologram som du placerar på en vägg verkar vanligtvis vara en tum eller så från väggen.</span><span class="sxs-lookup"><span data-stu-id="d6882-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="d6882-210">Om det verkar vara längre bort kan du prova en eller flera av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d6882-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="d6882-211">När du placerar ett hologram på en vägg ska du stå mellan en och tre meter från väggen och ansiktet mot väggen direkt på.</span><span class="sxs-lookup"><span data-stu-id="d6882-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="d6882-212">Tryck i luften på väggen för att visa kartnätsgrafiken.</span><span class="sxs-lookup"><span data-stu-id="d6882-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="d6882-213">Se till att näten är justerade mot väggen.</span><span class="sxs-lookup"><span data-stu-id="d6882-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="d6882-214">Om den inte gör det tar du bort hologrammet, genomsökar vägg igen och försöker sedan igen.</span><span class="sxs-lookup"><span data-stu-id="d6882-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="d6882-215">Om problemet kvarstår kör du kalibreringsappen.</span><span class="sxs-lookup"><span data-stu-id="d6882-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="d6882-216">Du hittar den i **Inställningar**  >    >  **SystemVerktyg**.</span><span class="sxs-lookup"><span data-stu-id="d6882-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="d6882-217">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="d6882-218">Appar visas för nära efter att de har flyttats</span><span class="sxs-lookup"><span data-stu-id="d6882-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="d6882-219">Prova att gå runt och titta på det område där du placerar appen så att HoloLens genomsöker området från olika vinklar.</span><span class="sxs-lookup"><span data-stu-id="d6882-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="d6882-220">[Att rensa enhetsvisor-programmet](hololens1-hardware.md#care-and-cleaning) kan också vara till hjälp.</span><span class="sxs-lookup"><span data-stu-id="d6882-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="d6882-221">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="d6882-222">Rapportera problem med instabila eller inexakta hologram</span><span class="sxs-lookup"><span data-stu-id="d6882-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="d6882-223">Spela in och [Inspelning av mixad verklighet video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) om problemet.</span><span class="sxs-lookup"><span data-stu-id="d6882-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="d6882-224">Den här videon kan senare laddas upp via Feedbackhubben som en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="d6882-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="d6882-225">Aktivera fullständig telemetri via appen **Inställningar** – > sekretessdiagnostik & feedback och under Valfria  ->   **diagnostikdata** ser du till att växlingsknappen är inställd på **På**</span><span class="sxs-lookup"><span data-stu-id="d6882-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="d6882-226">Hämta de senaste korrigeringarna för hologramskalning och stabilitet genom att uppdatera till det senaste [Windows Holographic OS(20H2 eller senare)](hololens-release-notes.md#windows-holographic-version-20h2).</span><span class="sxs-lookup"><span data-stu-id="d6882-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="d6882-227">När du har uppdaterat utför du följande:</span><span class="sxs-lookup"><span data-stu-id="d6882-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="d6882-228">Ta bort alla Hologram via **inställningsappen** -> **System**  ->  **Holograms** -> sedan Ta bort alla **hologram** och börja med en ny karta.</span><span class="sxs-lookup"><span data-stu-id="d6882-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="d6882-229">Skapa en ny karta över ditt utrymme genom att använda HoloLens och gå runt i rummet och titta på alla områden och ytor i utrymmet.</span><span class="sxs-lookup"><span data-stu-id="d6882-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="d6882-230">Gör detta i 2–3 minuter.</span><span class="sxs-lookup"><span data-stu-id="d6882-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="d6882-231">Utför IPD-kalibrering.</span><span class="sxs-lookup"><span data-stu-id="d6882-231">Perform IPD calibration.</span></span> <span data-ttu-id="d6882-232">Gå till **Inställningar**  >    >  **Systemverktyg**.</span><span class="sxs-lookup"><span data-stu-id="d6882-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="d6882-233">Under **Kalibrering** väljer du **Öppna kalibrering.**</span><span class="sxs-lookup"><span data-stu-id="d6882-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="d6882-234">Testa scenariot på ett annat sätt och se om det fortfarande finns kvar.</span><span class="sxs-lookup"><span data-stu-id="d6882-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="d6882-235">Om uppdateringen inte åtgärdar problemet kan du skicka en [Feedbackhubben problemet](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="d6882-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="d6882-236">När du har fyllt i  feedback kan du använda knappen Dela för att skapa en enkel delningslänk som kan skickas när du kontaktar supporten.</span><span class="sxs-lookup"><span data-stu-id="d6882-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="d6882-237">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="d6882-237">Back to list</span></span>](#list)