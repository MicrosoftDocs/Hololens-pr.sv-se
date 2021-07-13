---
title: HoloLens Felsökning av enhet
description: Håll dig uppdaterad om de vanligaste lösningarna för att HoloLens enhetsproblem och felsökningstekniker.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problem, bugg, felsöka, åtgärda, hjälp, support, HoloLens, emulator
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635457"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="df33b-104">Felsökning av enhet</span><span class="sxs-lookup"><span data-stu-id="df33b-104">Device Troubleshooting</span></span>

<span data-ttu-id="df33b-105">Den här artikeln beskriver hur du löser flera vanliga HoloLens problem.</span><span class="sxs-lookup"><span data-stu-id="df33b-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="df33b-106">Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="df33b-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="df33b-107">Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="df33b-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="df33b-108">**Kända problem**</span><span class="sxs-lookup"><span data-stu-id="df33b-108">**Known Issues**</span></span>
- [<span data-ttu-id="df33b-109">Remote Assist-videon låser sig efter 20 minuter</span><span class="sxs-lookup"><span data-stu-id="df33b-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="df33b-110">Automatisk inloggning frågar efter inloggning</span><span class="sxs-lookup"><span data-stu-id="df33b-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="df33b-111">Microsoft Edge kan inte starta</span><span class="sxs-lookup"><span data-stu-id="df33b-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="df33b-112">Tangentbordet växlar inte till specialtecken</span><span class="sxs-lookup"><span data-stu-id="df33b-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="df33b-113">Det visas inget fel när låsta filer laddas ned</span><span class="sxs-lookup"><span data-stu-id="df33b-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="df33b-114">Enhetsportalen-filuppladdning/nedladdningstidsuppladdning</span><span class="sxs-lookup"><span data-stu-id="df33b-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="df33b-115">Blå skärm efter avregistrerad från Insider-förhandsgranskning på en enhet som flashats med en Insider-version</span><span class="sxs-lookup"><span data-stu-id="df33b-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="df33b-116">OneDrive laddar inte upp bilder automatiskt</span><span class="sxs-lookup"><span data-stu-id="df33b-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="df33b-117">**Allmänt**</span><span class="sxs-lookup"><span data-stu-id="df33b-117">**General**</span></span>
- [<span data-ttu-id="df33b-118">HoloLens svarar inte eller startar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="df33b-119">Fel om "lågt diskutrymme"</span><span class="sxs-lookup"><span data-stu-id="df33b-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="df33b-120">Kalibreringen misslyckas</span><span class="sxs-lookup"><span data-stu-id="df33b-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="df33b-121">Det går inte att logga in eftersom HoloLens tidigare har ställts in för någon annan</span><span class="sxs-lookup"><span data-stu-id="df33b-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="df33b-122">Unity fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="df33b-123">Windows Enhetsportalen fungerar inte korrekt</span><span class="sxs-lookup"><span data-stu-id="df33b-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="df33b-124">Den HoloLens Emulator fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="df33b-125">**Indata**</span><span class="sxs-lookup"><span data-stu-id="df33b-125">**Input**</span></span>
- [<span data-ttu-id="df33b-126">Röstkommandon fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="df33b-127">Handindata fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="df33b-128">**Anslutningsmöjligheter**</span><span class="sxs-lookup"><span data-stu-id="df33b-128">**Connectivity**</span></span>
- [<span data-ttu-id="df33b-129">Det går inte att ansluta till Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="df33b-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="df33b-130">**Externa enheter**</span><span class="sxs-lookup"><span data-stu-id="df33b-130">**External Devices**</span></span> 
- [<span data-ttu-id="df33b-131">Bluetooth-enheter inte parkopplas</span><span class="sxs-lookup"><span data-stu-id="df33b-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="df33b-132">USB-C-mikrofonen fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="df33b-133">Enheter som anges som tillgängliga Inställningar inte fungerar</span><span class="sxs-lookup"><span data-stu-id="df33b-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="df33b-134">Remote Assist-videon låser sig efter 20 minuter</span><span class="sxs-lookup"><span data-stu-id="df33b-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="df33b-135">Det finns en nyare version av Remote Assist som har en korrigering av det här problemet.</span><span class="sxs-lookup"><span data-stu-id="df33b-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="df33b-136">Uppdatera [Remote Assist till den](holographic-store-apps.md#update-apps) senaste versionen för att undvika det här problemet.</span><span class="sxs-lookup"><span data-stu-id="df33b-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="df33b-137">På grund av allvarlighetsgraden för det här kända problemet pausade vi tillfälligt tillgängligheten för Windows Holographic, version 21H1.</span><span class="sxs-lookup"><span data-stu-id="df33b-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="df33b-138">21H1-versionen är nu tillgänglig igen, så enheter kan återigen uppdateras till den senaste versionen 21H1.</span><span class="sxs-lookup"><span data-stu-id="df33b-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="df33b-139">I den senaste versionen [Windows Holographic, version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)har vissa användare av Remote Assist haft videofrysningar under samtal över 20 minuter.</span><span class="sxs-lookup"><span data-stu-id="df33b-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="df33b-140">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="df33b-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="df33b-141">Provisoriska lösningar</span><span class="sxs-lookup"><span data-stu-id="df33b-141">Workarounds</span></span>

<span data-ttu-id="df33b-142">Om du inte kan uppdatera Remote Assist till en nyare version kan du prova följande.</span><span class="sxs-lookup"><span data-stu-id="df33b-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="df33b-143">Starta om mellan anrop</span><span class="sxs-lookup"><span data-stu-id="df33b-143">Restart in between calls</span></span>

<span data-ttu-id="df33b-144">Om dina anrop tar mer än 20 minuter och det här problemet uppstår kan du prova att starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="df33b-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="df33b-145">Om du startar om enheten mellan Remote Assist-anrop uppdateras enheten och den förs tillbaka till ett bra tillstånd.</span><span class="sxs-lookup"><span data-stu-id="df33b-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="df33b-146">Om du snabbt vill starta [om Windows Holographic öppnar du version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) startmenyn och väljer användarikonen och väljer sedan **Starta om.**</span><span class="sxs-lookup"><span data-stu-id="df33b-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="df33b-147">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="df33b-148">Automatisk inloggning frågar efter inloggning</span><span class="sxs-lookup"><span data-stu-id="df33b-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="df33b-149">En HoloLens 2-enhet kan konfigureras för att automatiskt logga in via  ->    ->  **Inställningar-konton Inloggningsalternativ** -> och under  Obligatoriskt anger du värdet till **Aldrig**.</span><span class="sxs-lookup"><span data-stu-id="df33b-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="df33b-150">Vissa användare kan behöva logga in på enheten igen när de uppdaterar en enhet med en mycket stor uppdatering, till exempel en funktionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="df33b-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="df33b-151">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="df33b-151">This is a **known issue**.</span></span>

<span data-ttu-id="df33b-152">Exempel på när detta kan inträffa:</span><span class="sxs-lookup"><span data-stu-id="df33b-152">Example of when this could occur:</span></span>

- <span data-ttu-id="df33b-153">Uppdatera en enhet från Windows Holographic, version 2004 (Build 19041.xxxx) till Windows Holographic, version 21H1 (Build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="df33b-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="df33b-154">Uppdatera en enhet för att ta en stor uppdatering av samma större version, t.ex. Windows Holographic, version 2004 till Windows Holographic, version 20H2</span><span class="sxs-lookup"><span data-stu-id="df33b-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="df33b-155">Uppdatera en enhet från en fabriksavbildning till den senaste avbildningen</span><span class="sxs-lookup"><span data-stu-id="df33b-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="df33b-156">Detta bör inte inträffa under:</span><span class="sxs-lookup"><span data-stu-id="df33b-156">This should not occur during:</span></span>

- <span data-ttu-id="df33b-157">Enheter som tar en månatlig serviceuppdatering</span><span class="sxs-lookup"><span data-stu-id="df33b-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="df33b-158">Metoder för att komma runt:</span><span class="sxs-lookup"><span data-stu-id="df33b-158">Work around methods:</span></span>

- <span data-ttu-id="df33b-159">Inloggningsmetoder som PIN-kod, lösenord, Iris, webbautentisering eller FIDO2-nycklar.</span><span class="sxs-lookup"><span data-stu-id="df33b-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="df33b-160">Om enhetens PIN-kod inte kan sparas och andra autentiseringsmetoder inte är tillgängliga kan en användare använda [manuellt omsnedstrecksläge.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="df33b-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="df33b-161">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="df33b-162">Microsoft Edge kan inte starta</span><span class="sxs-lookup"><span data-stu-id="df33b-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="df33b-163">Det här problemet skapades ursprungligen med leveransversionen Microsoft Edge i åtanke.</span><span class="sxs-lookup"><span data-stu-id="df33b-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="df33b-164">Det här problemet kan lösas i den [nya Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="df33b-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="df33b-165">Om den inte är det kan du skicka feedback.</span><span class="sxs-lookup"><span data-stu-id="df33b-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="df33b-166">Några kunder har rapporterat ett problem där Microsoft Edge inte kan starta.</span><span class="sxs-lookup"><span data-stu-id="df33b-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="df33b-167">För dessa kunder kvarstår problemet genom omstart och kan inte lösas med Windows eller programuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="df33b-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="df33b-168">Om det här problemet uppstår och du har bekräftat att Windows är uppdaterat kan du skicka en bugg från [Feedbackhubben-appen](hololens-updates.md#manually-check-for-updates)med följande kategori och underkategori: Installera och uppdatera > Ladda ned, installera och konfigurera Windows Update. [](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="df33b-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="df33b-169">Det finns inga kända lösningar eftersom vi inte har kunnat rotorsaken till problemet hittills.</span><span class="sxs-lookup"><span data-stu-id="df33b-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="df33b-170">Att lämna in en bugg via Feedbackhubben hjälper vår undersökning!</span><span class="sxs-lookup"><span data-stu-id="df33b-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="df33b-171">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="df33b-171">This is a **known issue**.</span></span>

[<span data-ttu-id="df33b-172">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="df33b-173">Tangentbordet växlar inte till specialtecken</span><span class="sxs-lookup"><span data-stu-id="df33b-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="df33b-174">Det uppstår ett problem under OOBE, där när användaren har valt ett arbets- eller skolkonto och anger sitt lösenord och försöker växla till specialtecken på tangentbordet genom att trycka på knappen &123 ändras inte till specialtecken.</span><span class="sxs-lookup"><span data-stu-id="df33b-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="df33b-175">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="df33b-175">This is a **known issue**.</span></span>

<span data-ttu-id="df33b-176">Work-arounds:</span><span class="sxs-lookup"><span data-stu-id="df33b-176">Work-arounds:</span></span>
-   <span data-ttu-id="df33b-177">Stäng tangentbordet och öppna det igen genom att trycka på textfältet.</span><span class="sxs-lookup"><span data-stu-id="df33b-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="df33b-178">Ange ditt lösenord felaktigt.</span><span class="sxs-lookup"><span data-stu-id="df33b-178">Incorrectly enter your password.</span></span> <span data-ttu-id="df33b-179">När tangentbordet har återstartats nästa gång fungerar det som förväntat.</span><span class="sxs-lookup"><span data-stu-id="df33b-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="df33b-180">Webbautentisering, stäng tangentbordet och välj **Logga in från en annan enhet.**</span><span class="sxs-lookup"><span data-stu-id="df33b-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="df33b-181">Om du bara anger siffror kan en användare trycka på och hålla ned vissa tangenter för att öppna en expanderad meny.</span><span class="sxs-lookup"><span data-stu-id="df33b-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="df33b-182">Använda ett USB-tangentbord.</span><span class="sxs-lookup"><span data-stu-id="df33b-182">Using a USB keyboard.</span></span>

<span data-ttu-id="df33b-183">Detta påverkar inte:</span><span class="sxs-lookup"><span data-stu-id="df33b-183">This does not affect:</span></span>
- <span data-ttu-id="df33b-184">Användare som väljer att använda ett personligt konto.</span><span class="sxs-lookup"><span data-stu-id="df33b-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="df33b-185">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="df33b-186">Det går inte att ladda ned låsta filer</span><span class="sxs-lookup"><span data-stu-id="df33b-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="df33b-187">Det här är **ett känt** problem som åtgärdas i Windows Insider-versionen, version 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="df33b-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="df33b-188">I tidigare versioner av Windows Holographic skulle resultatet bli en HTTP-felsida när du försöker ladda ned en låst fil.</span><span class="sxs-lookup"><span data-stu-id="df33b-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="df33b-189">I Windows Holographic version 21H1-uppdateringen resulterar försök att ladda ned en låst fil i att inget visas – filen laddas inte ned och det uppstår inget fel.</span><span class="sxs-lookup"><span data-stu-id="df33b-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="df33b-190">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="df33b-191">Enhetsportalen-filuppladdning/nedladdningstidsuppladdning</span><span class="sxs-lookup"><span data-stu-id="df33b-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="df33b-192">Det här är **ett känt** problem som åtgärdas i Windows Insider-versionen, version 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="df33b-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="df33b-193">Om du tidigare har inaktiverat SSL-anslutning som en del av lösningen rekommenderar vi starkt att du återaktivera den.</span><span class="sxs-lookup"><span data-stu-id="df33b-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="df33b-194">Vissa kunder har upptäckt att åtgärden kanske låser sig när de försöker ladda upp eller ladda ned filer och sedan tar slut eller aldrig slutförs.</span><span class="sxs-lookup"><span data-stu-id="df33b-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="df33b-195">Detta är separat[](#downloading-locked-files-doesnt-error) från det kända problemet "fillås" – detta påverkar versioner av Windows Holographic, versionerna 2004, 20H2 och 21H1 på marknaden.</span><span class="sxs-lookup"><span data-stu-id="df33b-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="df33b-196">Problemet har orsakats av en bugg i Enhetsportalen hantering av vissa begäranden och används mest konsekvent när https används, vilket är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="df33b-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="df33b-197">Lösning</span><span class="sxs-lookup"><span data-stu-id="df33b-197">Workaround</span></span>

<span data-ttu-id="df33b-198">Den här lösningen, som gäller Wi-Fi och UsbNcm, är att inaktivera alternativet "krävs" under "SSL-anslutning".</span><span class="sxs-lookup"><span data-stu-id="df33b-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="df33b-199">Det gör du genom att Enhetsportalen, **System** och välja **sidan** Inställningar.</span><span class="sxs-lookup"><span data-stu-id="df33b-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="df33b-200">I avsnittet **Enhetssäkerhet** letar du upp **SSL-anslutning** och avmarkerar för att inaktivera **Nödvändig**.</span><span class="sxs-lookup"><span data-stu-id="df33b-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="df33b-201">Användaren bör sedan gå till http://, inte https:// (IP-adress) och funktioner som filuppladdning och nedladdning fungerar.</span><span class="sxs-lookup"><span data-stu-id="df33b-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="df33b-202">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="df33b-203">Blå skärm efter avregistrerad från Insider-förhandsgranskning på en enhet som flashats med en Insider-version</span><span class="sxs-lookup"><span data-stu-id="df33b-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="df33b-204">Det här är ett problem som påverkar användare som är i en Insider-förhandsversion, omsnedstreckade sina HoloLens 2 med en ny insiderförhandsvisning och sedan avregistrerade från Insider-programmet.</span><span class="sxs-lookup"><span data-stu-id="df33b-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="df33b-205">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="df33b-205">This is a **known issue**.</span></span>

<span data-ttu-id="df33b-206">Detta påverkar inte:</span><span class="sxs-lookup"><span data-stu-id="df33b-206">This does not affect:</span></span>
- <span data-ttu-id="df33b-207">Användare som inte är registrerade i Windows Insider</span><span class="sxs-lookup"><span data-stu-id="df33b-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="df33b-208">Insiders:</span><span class="sxs-lookup"><span data-stu-id="df33b-208">Insiders:</span></span>
    - <span data-ttu-id="df33b-209">Om en enhet har registrerats sedan Insider-versioner var version 18362.x</span><span class="sxs-lookup"><span data-stu-id="df33b-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="df33b-210">Om de flashade en Insider-signerad version av 19041.x och förblir registrerade i Insider-programmet</span><span class="sxs-lookup"><span data-stu-id="df33b-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="df33b-211">Work-around:</span><span class="sxs-lookup"><span data-stu-id="df33b-211">Work-around:</span></span> 
- <span data-ttu-id="df33b-212">Undvik problemet</span><span class="sxs-lookup"><span data-stu-id="df33b-212">Avoid the issue</span></span> 
    - <span data-ttu-id="df33b-213">Flasha en icke-insider-version.</span><span class="sxs-lookup"><span data-stu-id="df33b-213">Flash a non-insider build.</span></span> <span data-ttu-id="df33b-214">En av de regelbundna månatliga uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="df33b-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="df33b-215">Håll dig i Insider Preview</span><span class="sxs-lookup"><span data-stu-id="df33b-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="df33b-216">Omstrecka enheten</span><span class="sxs-lookup"><span data-stu-id="df33b-216">Reflash the device</span></span>

    1. <span data-ttu-id="df33b-217">Försätt [HoloLens 2 i flashläge manuellt](hololens-recovery.md) genom att stänga av helt och hållet utan att ansluta.</span><span class="sxs-lookup"><span data-stu-id="df33b-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="df33b-218">Håll sedan volymen uppåt och tryck på strömknappen.</span><span class="sxs-lookup"><span data-stu-id="df33b-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="df33b-219">Anslut till datorn och öppna Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="df33b-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="df33b-220">Flasha HoloLens 2 till standardbygget.</span><span class="sxs-lookup"><span data-stu-id="df33b-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="df33b-221">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="df33b-222">OneDrive laddar inte upp bilder automatiskt</span><span class="sxs-lookup"><span data-stu-id="df33b-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="df33b-223">Appen OneDrive för HoloLens stöder inte automatisk kamerauppladdning för arbets- eller skolkonton.</span><span class="sxs-lookup"><span data-stu-id="df33b-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="df33b-224">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="df33b-224">This is a **known issue**.</span></span>

<span data-ttu-id="df33b-225">Workarounds:</span><span class="sxs-lookup"><span data-stu-id="df33b-225">Workarounds:</span></span>

- <span data-ttu-id="df33b-226">Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton.</span><span class="sxs-lookup"><span data-stu-id="df33b-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="df33b-227">Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (appen OneDrive stöder dubbel inloggning).</span><span class="sxs-lookup"><span data-stu-id="df33b-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="df33b-228">Från din Microsoft-konto profil i OneDrive du aktivera automatisk överföring av kamerarulle i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="df33b-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="df33b-229">Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive appen.</span><span class="sxs-lookup"><span data-stu-id="df33b-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="df33b-230">Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive appen.</span><span class="sxs-lookup"><span data-stu-id="df33b-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="df33b-231">Välj knappen **+** och välj **Upload**.</span><span class="sxs-lookup"><span data-stu-id="df33b-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="df33b-232">Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > Kamerarulle**.</span><span class="sxs-lookup"><span data-stu-id="df33b-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="df33b-233">Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.</span><span class="sxs-lookup"><span data-stu-id="df33b-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="df33b-234">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="df33b-235">HoloLens svarar inte eller startar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="df33b-236">Om ditt HoloLens inte startar:</span><span class="sxs-lookup"><span data-stu-id="df33b-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="df33b-237">Om lysdioderna bredvid strömknappen inte tänds, eller om bara en led blinkar en kort stund, kan du behöva [ladda HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="df33b-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="df33b-238">Om lysdioderna tänds när du trycker på strömknappen men du inte kan se något på skärmarna, gör du en [hård återställning av enheten.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="df33b-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="df33b-239">Om ditt HoloLens låst eller inte svarar:</span><span class="sxs-lookup"><span data-stu-id="df33b-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="df33b-240">Stäng av HoloLens genom att trycka på strömknappen tills alla fem lysdioderna stänger av sig själva eller i 15 sekunder om lysdioderna inte svarar.</span><span class="sxs-lookup"><span data-stu-id="df33b-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="df33b-241">Starta din HoloLens genom att trycka på strömknappen igen.</span><span class="sxs-lookup"><span data-stu-id="df33b-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="df33b-242">Om de här stegen inte fungerar kan du försöka återställa [din HoloLens 2-HoloLens](hololens-recovery.md) [(första generationens) enhet.](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="df33b-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="df33b-243">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="df33b-244">Fel om "lågt diskutrymme"</span><span class="sxs-lookup"><span data-stu-id="df33b-244">"Low Disk Space" error</span></span>

<span data-ttu-id="df33b-245">Du måste frigöra lagringsutrymme genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="df33b-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="df33b-246">Ta bort vissa blanksteg som inte används.</span><span class="sxs-lookup"><span data-stu-id="df33b-246">Delete some unused spaces.</span></span> <span data-ttu-id="df33b-247">Gå till **Inställningar**  >    >  **systemutrymmen,** välj ett utrymme som du inte längre behöver och välj sedan Ta **bort.**</span><span class="sxs-lookup"><span data-stu-id="df33b-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="df33b-248">Ta bort några av hologrammen som du har placerat.</span><span class="sxs-lookup"><span data-stu-id="df33b-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="df33b-249">Ta bort några bilder och videor från Photos appen.</span><span class="sxs-lookup"><span data-stu-id="df33b-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="df33b-250">Avinstallera några appar från din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="df33b-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="df33b-251">I listan **Alla appar** trycker du på och håller ned den app som du vill avinstallera och väljer sedan **Avinstallera.**</span><span class="sxs-lookup"><span data-stu-id="df33b-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="df33b-252">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="df33b-253">Kalibreringen misslyckas</span><span class="sxs-lookup"><span data-stu-id="df33b-253">Calibration fails</span></span>

<span data-ttu-id="df33b-254">Kalibrering bör fungera för de flesta, men det finns fall där kalibreringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="df33b-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="df33b-255">Några möjliga orsaker till kalibreringsfel är:</span><span class="sxs-lookup"><span data-stu-id="df33b-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="df33b-256">Bli störande och inte följa kalibreringsmålen</span><span class="sxs-lookup"><span data-stu-id="df33b-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="df33b-257">Enhetens visor eller enhetsvisorn är inte korrekt placerad på rätt sätt</span><span class="sxs-lookup"><span data-stu-id="df33b-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="df33b-258">Dirty or scratched glass</span><span class="sxs-lookup"><span data-stu-id="df33b-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="df33b-259">Vissa typer av kontaktlinser och glasögon (färgade kontaktobjektiv, vissa toric kontaktobjektiv, IR-blockeringsglasögon, vissa glasögon med höga glasögon, solglasögon eller liknande)</span><span class="sxs-lookup"><span data-stu-id="df33b-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="df33b-260">Mer uttalad snedstreckstillägg</span><span class="sxs-lookup"><span data-stu-id="df33b-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="df33b-261">Behåring eller tjockt glasögonramar om de blockerar enheten från att se dina ögon</span><span class="sxs-lookup"><span data-stu-id="df33b-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="df33b-262">Vissa ögonoperationer, ögontillstånd eller ögonoperationer, till exempel smala ögon, långa ögonfransar, amblyopia, nystagmus, vissa fall av LASIK eller andra ögonoperationer</span><span class="sxs-lookup"><span data-stu-id="df33b-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="df33b-263">Om kalibreringen misslyckas försöker du:</span><span class="sxs-lookup"><span data-stu-id="df33b-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="df33b-264">Rensa enhetsvisorn</span><span class="sxs-lookup"><span data-stu-id="df33b-264">Cleaning your device visor</span></span>
- <span data-ttu-id="df33b-265">Rensa glasögon</span><span class="sxs-lookup"><span data-stu-id="df33b-265">Cleaning your glasses</span></span>
- <span data-ttu-id="df33b-266">Push-pusha enhetsvisor-programmet så nära dina ögon som möjligt</span><span class="sxs-lookup"><span data-stu-id="df33b-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="df33b-267">Flytta objekt i ditt visor-program från vägen (till exempel hår)</span><span class="sxs-lookup"><span data-stu-id="df33b-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="df33b-268">Tänd en lampa i rummet eller flytta ut direkt från rummet</span><span class="sxs-lookup"><span data-stu-id="df33b-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="df33b-269">Om du har följt alla riktlinjer och kalibreringen fortfarande inte fungerar kan du inaktivera kalibreringsuppmaning i Inställningar.</span><span class="sxs-lookup"><span data-stu-id="df33b-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="df33b-270">Meddela oss också genom att skicka feedback i [Feedbackhubben](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="df33b-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="df33b-271">Se även relaterad information för felsökning [av bildfärg eller ljusstyrka.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="df33b-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="df33b-272">Ipd-inställningen gäller inte för HoloLens 2, eftersom ögonpositionerna beräknas av systemet.</span><span class="sxs-lookup"><span data-stu-id="df33b-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="df33b-273">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="df33b-274">Det går inte att logga in eftersom HoloLens tidigare har ställts in för någon annan</span><span class="sxs-lookup"><span data-stu-id="df33b-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="df33b-275">Du kan [placera enheten i **flashläge och använda** Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) för att återställa enheten.</span><span class="sxs-lookup"><span data-stu-id="df33b-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="df33b-276">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="df33b-277">Unity fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-277">Unity isn't working</span></span>

- <span data-ttu-id="df33b-278">Se [Installera verktygen för](/windows/mixed-reality/install-the-tools) den senaste versionen av Unity som rekommenderas för HoloLens utveckling.</span><span class="sxs-lookup"><span data-stu-id="df33b-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="df33b-279">Kända problem med Unity HoloLens Technical Preview dokumenteras i de HoloLens [Unity-forumen](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="df33b-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="df33b-280">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="df33b-281">Windows Enhetsportalen fungerar inte korrekt</span><span class="sxs-lookup"><span data-stu-id="df33b-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="df33b-282">Funktionen Förhandsgranskning i Mixed Reality kan uppvisa flera sekunders svarstid.</span><span class="sxs-lookup"><span data-stu-id="df33b-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="df33b-283">På sidan Virtuella indata fungerar inte kontrollerna Gester och Rullning under avsnittet Virtuella gester.</span><span class="sxs-lookup"><span data-stu-id="df33b-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="df33b-284">Att använda dem har ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="df33b-284">Using them will have no effect.</span></span> <span data-ttu-id="df33b-285">Det virtuella tangentbordet på den virtuella indatasidan fungerar korrekt.</span><span class="sxs-lookup"><span data-stu-id="df33b-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="df33b-286">När du har aktiverat Developer Mode Inställningar kan det ta några sekunder innan växlingen aktiveras så att Enhetsportalen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="df33b-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="df33b-287">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="df33b-288">Den HoloLens Emulator fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="df33b-289">Information om HoloLens finns i vår utvecklardokumentation.</span><span class="sxs-lookup"><span data-stu-id="df33b-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="df33b-290">Läs mer om [att felsöka HoloLens emulatorn](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="df33b-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="df33b-291">Alla appar i Microsoft Store är inte kompatibla med emulatorn.</span><span class="sxs-lookup"><span data-stu-id="df33b-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="df33b-292">Till exempel är Young Conker och Fragment inte spelbara i emulatorn.</span><span class="sxs-lookup"><span data-stu-id="df33b-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="df33b-293">Du kan inte använda pc-webbkameran i Emulator.</span><span class="sxs-lookup"><span data-stu-id="df33b-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="df33b-294">Funktionen Liveförhandsgranskning i Windows Enhetsportalen fungerar inte med emulatorn.</span><span class="sxs-lookup"><span data-stu-id="df33b-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="df33b-295">Du kan fortfarande samla Mixed Reality videor och bilder.</span><span class="sxs-lookup"><span data-stu-id="df33b-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="df33b-296">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="df33b-297">Röstkommandon fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-297">Voice commands aren't working</span></span>

<span data-ttu-id="df33b-298">Om Cortana svarar på dina röstkommandon kontrollerar du att Cortana är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="df33b-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="df33b-299">I listan Alla appar väljer du **notebook-Cortana**  >    >  **notebook-Inställningar**  >   för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="df33b-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="df33b-300">Mer information om vad du kan säga finns i [Använda din röst med HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="df33b-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="df33b-301">På HoloLens (första generationen) går det inte att konfigurera inbyggd taligenkänning.</span><span class="sxs-lookup"><span data-stu-id="df33b-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="df33b-302">Den är alltid aktiverad.</span><span class="sxs-lookup"><span data-stu-id="df33b-302">It is always turned on.</span></span> <span data-ttu-id="df33b-303">På HoloLens 2 kan du välja om du vill aktivera både taligenkänning och Cortana under enhetskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="df33b-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="df33b-304">Om din HoloLens 2 inte svarar på din röst kontrollerar du att Taligenkänning är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="df33b-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="df33b-305">Gå till **Starta**  >  **Inställningar**  >    >  **Sekretesstal** och aktivera **Taligenkänning.**</span><span class="sxs-lookup"><span data-stu-id="df33b-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="df33b-306">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="df33b-307">Handindata fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-307">Hand input isn't working</span></span>

<span data-ttu-id="df33b-308">För att HoloLens ska kunna se dina händer måste du hålla dem inom gestens ram.</span><span class="sxs-lookup"><span data-stu-id="df33b-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="df33b-309">Startsidan Mixed Reality feedback som meddelar dig när dina händer spåras.</span><span class="sxs-lookup"><span data-stu-id="df33b-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="df33b-310">Feedbacken är annorlunda i olika versioner av HoloLens:</span><span class="sxs-lookup"><span data-stu-id="df33b-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="df33b-311">På HoloLens (1:a gen) ändras blickmarkören från en punkt till en ring</span><span class="sxs-lookup"><span data-stu-id="df33b-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="df33b-312">På HoloLens 2 visas en handmarkör när din hand är nära en pektavla och en handröta visas när pekarna är längre bort</span><span class="sxs-lookup"><span data-stu-id="df33b-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="df33b-313">Många integrerande appar följer indatamönster som liknar Mixed Reality Home.</span><span class="sxs-lookup"><span data-stu-id="df33b-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="df33b-314">Läs mer om att använda [handindata HoloLens (första generationen)](hololens1-basic-usage.md#use-hololens-with-your-hands) och [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)</span><span class="sxs-lookup"><span data-stu-id="df33b-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="df33b-315">Observera att vissa typer av handsken inte fungerar med handspårning om du bär handskydd.</span><span class="sxs-lookup"><span data-stu-id="df33b-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="df33b-316">Ett vanligt exempel är svarta handskes, som tenderar att absorbera IR-ljus och inte hämtas av djupkameran.</span><span class="sxs-lookup"><span data-stu-id="df33b-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="df33b-317">Om ditt arbete omfattar skyddshandske rekommenderar vi att du provar en ljusare färg, till exempel blå eller grå.</span><span class="sxs-lookup"><span data-stu-id="df33b-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="df33b-318">Ett annat exempel är stora baggy gloves, som tenderar att dölja formen på din hand.</span><span class="sxs-lookup"><span data-stu-id="df33b-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="df33b-319">Vi rekommenderar att du använder så väl formpassning som möjligt för bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="df33b-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="df33b-320">Om ditt visir har fingeravtryck eller utsmetning använder du mikrofiberrensningsmeden som HoloLens för att rensa visorn.</span><span class="sxs-lookup"><span data-stu-id="df33b-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="df33b-321">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="df33b-322">Det går inte att ansluta till Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="df33b-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="df33b-323">Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:</span><span class="sxs-lookup"><span data-stu-id="df33b-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="df33b-324">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="df33b-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="df33b-325">Kontrollera genom att använda gesten Start och välj sedan **Inställningar**  >  **Internet &amp;**  >  **Wi-Fi för nätverk.**</span><span class="sxs-lookup"><span data-stu-id="df33b-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="df33b-326">Om Wi-Fi är på kan du prova att stänga av den och sedan aktivera igen.</span><span class="sxs-lookup"><span data-stu-id="df33b-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="df33b-327">Flytta datorn närmare routern eller åtkomstpunkten.</span><span class="sxs-lookup"><span data-stu-id="df33b-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="df33b-328">Starta om Wi-Fi router och starta [sedan om HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="df33b-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="df33b-329">Försök att ansluta igen.</span><span class="sxs-lookup"><span data-stu-id="df33b-329">Try connecting again.</span></span>
- <span data-ttu-id="df33b-330">Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran.</span><span class="sxs-lookup"><span data-stu-id="df33b-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="df33b-331">Du hittar den här informationen på tillverkarens webbplats.</span><span class="sxs-lookup"><span data-stu-id="df33b-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="df33b-332">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="df33b-333">Bluetooth-enheter parkopplas inte</span><span class="sxs-lookup"><span data-stu-id="df33b-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="df33b-334">Om du har problem med [att koppla Bluetooth enhet](hololens-connect-devices.md)kan du prova följande:</span><span class="sxs-lookup"><span data-stu-id="df33b-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="df33b-335">Gå till **Inställningar**  >  **Enheter** och kontrollera att Bluetooth är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="df33b-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="df33b-336">Om den är det inaktiverar du den och sätter på den igen.</span><span class="sxs-lookup"><span data-stu-id="df33b-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="df33b-337">Kontrollera att din Bluetooth är helt debiterad eller har nya batterier.</span><span class="sxs-lookup"><span data-stu-id="df33b-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="df33b-338">Om du fortfarande inte kan ansluta startar [du om HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="df33b-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="df33b-339">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="df33b-340">USB-C-mikrofonen fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="df33b-341">Tänk på att vissa USB-C-mikrofoner felaktigt rapporterar sig själva som både *en mikrofon och* en talare.</span><span class="sxs-lookup"><span data-stu-id="df33b-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="df33b-342">Det här är ett problem med mikrofonen och inte med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="df33b-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="df33b-343">När någon av dessa mikrofoner ansluts till HoloLens kan ljudet gå förlorat.</span><span class="sxs-lookup"><span data-stu-id="df33b-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="df33b-344">Lyckligtvis finns det en enkel korrigering.</span><span class="sxs-lookup"><span data-stu-id="df33b-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="df33b-345">I **Inställningar**  ->    ->  **systemljud** anger du uttryckligen de inbyggda talarna **(Analog Feature Audio Driver)** som **standardenhet**.</span><span class="sxs-lookup"><span data-stu-id="df33b-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="df33b-346">HoloLens den här inställningen även om mikrofonen tas bort och återansluts senare.</span><span class="sxs-lookup"><span data-stu-id="df33b-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Felsöka USB-C-mikrofoner](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="df33b-348">Enheter som anges som tillgängliga Inställningar fungerar inte</span><span class="sxs-lookup"><span data-stu-id="df33b-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="df33b-349">HoloLens (första generationen) stöder inte Bluetooth ljudprofiler.</span><span class="sxs-lookup"><span data-stu-id="df33b-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="df33b-350">Bluetooth ljudenheter, till exempel högtalare och headset, kan visas som tillgängliga i HoloLens-inställningar, men de stöds inte.</span><span class="sxs-lookup"><span data-stu-id="df33b-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="df33b-351">HoloLens 2 stöder Bluetooth A2DP-ljudprofilen för stereouppspelning.</span><span class="sxs-lookup"><span data-stu-id="df33b-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="df33b-352">Profilen Bluetooth Hands Free som aktiverar mikrofoninfångning från en Bluetooth kringutrustning stöds inte på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="df33b-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="df33b-353">Om du har problem med att Bluetooth en enhet kontrollerar du att det är en enhet som stöds.</span><span class="sxs-lookup"><span data-stu-id="df33b-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="df33b-354">Enheter som stöds är följande:</span><span class="sxs-lookup"><span data-stu-id="df33b-354">Supported devices include the following:</span></span>

- <span data-ttu-id="df33b-355">QWERTY på engelska Bluetooth tangentbord (du kan använda dem var som helst där du använder det holografiska tangentbordet).</span><span class="sxs-lookup"><span data-stu-id="df33b-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="df33b-356">Bluetooth mice.</span><span class="sxs-lookup"><span data-stu-id="df33b-356">Bluetooth mice.</span></span>
- <span data-ttu-id="df33b-357">Klicka [HoloLens .](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="df33b-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="df33b-358">Du kan koppla ihop Bluetooth HID- och GATT-enheter med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="df33b-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="df33b-359">Du kan dock behöva installera motsvarande tillhörande appar från Microsoft Store för att faktiskt använda enheterna.</span><span class="sxs-lookup"><span data-stu-id="df33b-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="df33b-360">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="df33b-360">Back to list</span></span>](#list)
