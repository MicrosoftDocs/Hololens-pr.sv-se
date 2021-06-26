---
title: Felsökning av HoloLens-enhet
description: Håll dig uppdaterad om de vanligaste lösningarna på problem med HoloLens-enheter och felsökningstekniker.
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
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924629"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="94b52-104">Felsökning av enhet</span><span class="sxs-lookup"><span data-stu-id="94b52-104">Device Troubleshooting</span></span>

<span data-ttu-id="94b52-105">Den här artikeln beskriver hur du löser flera vanliga HoloLens-problem.</span><span class="sxs-lookup"><span data-stu-id="94b52-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="94b52-106">Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="94b52-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="94b52-107">Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="94b52-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="94b52-108">**Kända problem**</span><span class="sxs-lookup"><span data-stu-id="94b52-108">**Known Issues**</span></span>
- [<span data-ttu-id="94b52-109">Remote Assist-videon låser sig efter 20 minuter</span><span class="sxs-lookup"><span data-stu-id="94b52-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="94b52-110">Automatisk inloggning frågar efter inloggning</span><span class="sxs-lookup"><span data-stu-id="94b52-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="94b52-111">Microsoft Edge kan inte starta</span><span class="sxs-lookup"><span data-stu-id="94b52-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="94b52-112">Tangentbordet växlar inte till specialtecken</span><span class="sxs-lookup"><span data-stu-id="94b52-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="94b52-113">Det visas inget fel när låsta filer laddas ned</span><span class="sxs-lookup"><span data-stu-id="94b52-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="94b52-114">Enhetsportalen-filuppladdning/nedladdningstidsuppladdning</span><span class="sxs-lookup"><span data-stu-id="94b52-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="94b52-115">Blå skärm efter avregistrerad från Insider-förhandsgranskning på en enhet som flashats med en Insider-version</span><span class="sxs-lookup"><span data-stu-id="94b52-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="94b52-116">OneDrive laddar inte upp bilder automatiskt</span><span class="sxs-lookup"><span data-stu-id="94b52-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="94b52-117">**Allmänt**</span><span class="sxs-lookup"><span data-stu-id="94b52-117">**General**</span></span>
- [<span data-ttu-id="94b52-118">HoloLens svarar inte eller startar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="94b52-119">Fel om "lågt diskutrymme"</span><span class="sxs-lookup"><span data-stu-id="94b52-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="94b52-120">Kalibreringen misslyckas</span><span class="sxs-lookup"><span data-stu-id="94b52-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="94b52-121">Det går inte att logga in eftersom min HoloLens tidigare har ställts in för någon annan</span><span class="sxs-lookup"><span data-stu-id="94b52-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="94b52-122">Unity fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="94b52-123">Windows Enhetsportalen fungerar inte korrekt</span><span class="sxs-lookup"><span data-stu-id="94b52-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="94b52-124">HoloLens-emulatorn fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="94b52-125">**Indata**</span><span class="sxs-lookup"><span data-stu-id="94b52-125">**Input**</span></span>
- [<span data-ttu-id="94b52-126">Röstkommandon fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="94b52-127">Handinmatningen fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="94b52-128">**Anslutningsmöjligheter**</span><span class="sxs-lookup"><span data-stu-id="94b52-128">**Connectivity**</span></span>
- [<span data-ttu-id="94b52-129">Det går inte att ansluta till Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="94b52-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="94b52-130">**Externa enheter**</span><span class="sxs-lookup"><span data-stu-id="94b52-130">**External Devices**</span></span> 
- [<span data-ttu-id="94b52-131">Bluetooth-enheter parkopplas inte</span><span class="sxs-lookup"><span data-stu-id="94b52-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="94b52-132">USB-C-mikrofonen fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="94b52-133">Enheter som anges som tillgängliga i Inställningar fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="94b52-134">Remote Assist-videon låser sig efter 20 minuter</span><span class="sxs-lookup"><span data-stu-id="94b52-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="94b52-135">På grund av det här kända problemets allvarlighetsgrad har vi för närvarande pausat tillgängligheten för Windows Holographic, version 21H1.</span><span class="sxs-lookup"><span data-stu-id="94b52-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="94b52-136">Om du fortfarande vill uppdatera dina enheter till 21H1 kan du läsa anvisningarna i vår version längst [upp på sidan.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="94b52-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="94b52-137">I den senaste versionen av [Windows Holographic, version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)har vissa användare av Remote Assist haft videofrysning under samtal över 20 minuter.</span><span class="sxs-lookup"><span data-stu-id="94b52-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="94b52-138">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="94b52-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="94b52-139">Provisoriska lösningar</span><span class="sxs-lookup"><span data-stu-id="94b52-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="94b52-140">Starta om mellan anrop</span><span class="sxs-lookup"><span data-stu-id="94b52-140">Restart in between calls</span></span>

<span data-ttu-id="94b52-141">Om dina anrop tar mer än 20 minuter och det här problemet uppstår kan du prova att starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="94b52-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="94b52-142">Om du startar om enheten mellan Remote Assist-anrop uppdateras enheten och den förs tillbaka till ett bra tillstånd.</span><span class="sxs-lookup"><span data-stu-id="94b52-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="94b52-143">Om du snabbt vill starta om en enhet i [Windows Holographic öppnar du version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) startmenyn och väljer användarikonen och väljer sedan **Starta om.**</span><span class="sxs-lookup"><span data-stu-id="94b52-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="94b52-144">Återgå till en äldre version</span><span class="sxs-lookup"><span data-stu-id="94b52-144">Revert to an older build</span></span>

<span data-ttu-id="94b52-145">Vissa kunder har upptäckt att det här problemet inte längre uppstår när de återgår till en tidigare version av operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="94b52-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="94b52-146">Om du har upptäckt att dina enheter har det här problemet kan du prova följande steg:</span><span class="sxs-lookup"><span data-stu-id="94b52-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="94b52-147">Workarounds:</span><span class="sxs-lookup"><span data-stu-id="94b52-147">Workarounds:</span></span>

- <span data-ttu-id="94b52-148">Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton.</span><span class="sxs-lookup"><span data-stu-id="94b52-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="94b52-149">Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning).</span><span class="sxs-lookup"><span data-stu-id="94b52-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="94b52-150">Från din Microsoft-konto i OneDrive kan du aktivera automatisk överföring av kamerarulle i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="94b52-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="94b52-151">Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive-appen.</span><span class="sxs-lookup"><span data-stu-id="94b52-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="94b52-152">Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive-appen.</span><span class="sxs-lookup"><span data-stu-id="94b52-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="94b52-153">Välj knappen **+** och välj Ladda **upp.**</span><span class="sxs-lookup"><span data-stu-id="94b52-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="94b52-154">Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > camera roll**.</span><span class="sxs-lookup"><span data-stu-id="94b52-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="94b52-155">Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.</span><span class="sxs-lookup"><span data-stu-id="94b52-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="94b52-156">Ladda ned versionen för Windows Holographic, version 20H2 – maj 2021 Update</span><span class="sxs-lookup"><span data-stu-id="94b52-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="94b52-157">Följ [instruktionerna för att återgå till en tidigare os-version](hololens-update-hololens.md#go-back-to-a-previous-version)</span><span class="sxs-lookup"><span data-stu-id="94b52-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="94b52-158">Pausa [antingen OS-uppdateringar på enheten manuellt](hololens-updates.md#pause-updates-via-device) eller för många enheter [med uppsnackning via MDM.](hololens-updates.md#configure-an-update-deferral-policy)</span><span class="sxs-lookup"><span data-stu-id="94b52-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="94b52-159">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="94b52-160">Automatisk inloggning frågar efter inloggning</span><span class="sxs-lookup"><span data-stu-id="94b52-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="94b52-161">En HoloLens 2-enhet kan konfigureras för att automatiskt logga in **via** Inställningskonton  ->    ->  **Inloggningsalternativ** -> och under  Obligatoriskt anger du **värdet till Aldrig**.</span><span class="sxs-lookup"><span data-stu-id="94b52-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="94b52-162">Vissa användare kan behöva logga in på enheten igen när de uppdaterar en enhet med en mycket stor uppdatering, till exempel en funktionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="94b52-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="94b52-163">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="94b52-163">This is a **known issue**.</span></span>

<span data-ttu-id="94b52-164">Exempel på när detta kan inträffa:</span><span class="sxs-lookup"><span data-stu-id="94b52-164">Example of when this could occur:</span></span>

- <span data-ttu-id="94b52-165">Uppdatera en enhet från Windows Holographic version 2004 (Build 19041.xxxx) till Windows Holographic, version 21H1 (Build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="94b52-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="94b52-166">Uppdatera en enhet för att ta en stor uppdatering av samma större version, t.ex. Windows Holographic, version 2004 till Windows Holographic, version 20H2</span><span class="sxs-lookup"><span data-stu-id="94b52-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="94b52-167">Uppdatera en enhet från en fabriksavbildning till den senaste avbildningen</span><span class="sxs-lookup"><span data-stu-id="94b52-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="94b52-168">Detta bör inte inträffa under:</span><span class="sxs-lookup"><span data-stu-id="94b52-168">This should not occur during:</span></span>

- <span data-ttu-id="94b52-169">Enheter som tar en månatlig serviceuppdatering</span><span class="sxs-lookup"><span data-stu-id="94b52-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="94b52-170">Metoder för att komma runt:</span><span class="sxs-lookup"><span data-stu-id="94b52-170">Work around methods:</span></span>

- <span data-ttu-id="94b52-171">Inloggningsmetoder som PIN-kod, lösenord, Iris, webbautentisering eller FIDO2-nycklar.</span><span class="sxs-lookup"><span data-stu-id="94b52-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="94b52-172">Om enhetens PIN-kod inte kan sparas och andra autentiseringsmetoder inte är tillgängliga kan en användare använda [manuellt omsnedstrecksläge.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="94b52-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="94b52-173">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="94b52-174">Microsoft Edge kan inte starta</span><span class="sxs-lookup"><span data-stu-id="94b52-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="94b52-175">Det här problemet skapades ursprungligen med leveransversionen Microsoft Edge i åtanke.</span><span class="sxs-lookup"><span data-stu-id="94b52-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="94b52-176">Det här problemet kan lösas i den [nya Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="94b52-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="94b52-177">Om den inte är det kan du skicka feedback.</span><span class="sxs-lookup"><span data-stu-id="94b52-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="94b52-178">Några kunder har rapporterat ett problem där Microsoft Edge inte kan starta.</span><span class="sxs-lookup"><span data-stu-id="94b52-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="94b52-179">För dessa kunder kvarstår problemet genom omstart och kan inte lösas med Windows- eller programuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="94b52-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="94b52-180">Om det här problemet uppstår och du har bekräftat att Windows är uppdaterat kan du skicka in en bugg från [Feedbackhubben-appen](hololens-updates.md#manually-check-for-updates)med följande kategori och underkategori: Installera och uppdatera > Ladda ned, installera och konfigurera Windows Update. [](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="94b52-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="94b52-181">Det finns inga kända lösningar eftersom vi inte har kunnat rotorsaken till problemet hittills.</span><span class="sxs-lookup"><span data-stu-id="94b52-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="94b52-182">Att lämna in en bugg via Feedbackhubben hjälper vår undersökning!</span><span class="sxs-lookup"><span data-stu-id="94b52-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="94b52-183">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="94b52-183">This is a **known issue**.</span></span>

[<span data-ttu-id="94b52-184">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="94b52-185">Tangentbordet växlar inte till specialtecken</span><span class="sxs-lookup"><span data-stu-id="94b52-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="94b52-186">Det uppstår ett problem under OOBE, där när användaren har valt ett arbets- eller skolkonto och anger sitt lösenord och försöker växla till specialtecken på tangentbordet genom att trycka på knappen &123 ändras inte till specialtecken.</span><span class="sxs-lookup"><span data-stu-id="94b52-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="94b52-187">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="94b52-187">This is a **known issue**.</span></span>

<span data-ttu-id="94b52-188">Work-arounds:</span><span class="sxs-lookup"><span data-stu-id="94b52-188">Work-arounds:</span></span>
-   <span data-ttu-id="94b52-189">Stäng tangentbordet och öppna det igen genom att trycka på textfältet.</span><span class="sxs-lookup"><span data-stu-id="94b52-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="94b52-190">Ange ditt lösenord felaktigt.</span><span class="sxs-lookup"><span data-stu-id="94b52-190">Incorrectly enter your password.</span></span> <span data-ttu-id="94b52-191">När tangentbordet har återstartats nästa gång fungerar det som förväntat.</span><span class="sxs-lookup"><span data-stu-id="94b52-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="94b52-192">Webbautentisering, stäng tangentbordet och välj **Logga in från en annan enhet.**</span><span class="sxs-lookup"><span data-stu-id="94b52-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="94b52-193">Om du bara anger siffror kan en användare trycka på och hålla ned vissa tangenter för att öppna en expanderad meny.</span><span class="sxs-lookup"><span data-stu-id="94b52-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="94b52-194">Använda ett USB-tangentbord.</span><span class="sxs-lookup"><span data-stu-id="94b52-194">Using a USB keyboard.</span></span>

<span data-ttu-id="94b52-195">Detta påverkar inte:</span><span class="sxs-lookup"><span data-stu-id="94b52-195">This does not affect:</span></span>
- <span data-ttu-id="94b52-196">Användare som väljer att använda ett personligt konto.</span><span class="sxs-lookup"><span data-stu-id="94b52-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="94b52-197">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="94b52-198">Det går inte att ladda ned låsta filer</span><span class="sxs-lookup"><span data-stu-id="94b52-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="94b52-199">! Obs! Det här **är ett känt** problem som har åtgärdats Windows Insider version 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="94b52-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="94b52-200">I tidigare versioner av Windows Holographic skulle resultatet bli en HTTP-felsida när du försöker ladda ned en låst fil.</span><span class="sxs-lookup"><span data-stu-id="94b52-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="94b52-201">I Windows Holographic version 21H1 Update, som försöker ladda ned en låst fil, resulterar det i att inget synligt händer – filen laddas inte ned och det uppstår inget fel.</span><span class="sxs-lookup"><span data-stu-id="94b52-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="94b52-202">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="94b52-203">Enhetsportalen-filuppladdning/nedladdningstidsuppladdning</span><span class="sxs-lookup"><span data-stu-id="94b52-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="94b52-204">! Obs! Det här **är ett känt** problem som åtgärdas i Windows Insider version 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="94b52-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="94b52-205">Om du tidigare har inaktiverat SSL-anslutning som en del av lösningen rekommenderar vi starkt att du återaktivera den.</span><span class="sxs-lookup"><span data-stu-id="94b52-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="94b52-206">Vissa kunder har upptäckt att åtgärden kan se ut att stanna upp när de försöker ladda upp eller ladda ned filer och sedan ta slut eller aldrig slutföras.</span><span class="sxs-lookup"><span data-stu-id="94b52-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="94b52-207">Detta är separat[](#downloading-locked-files-doesnt-error) från det kända problemet "fillås" – detta påverkar Windows Holographic- versionerna 2004, 20H2 och 21H1 på marknaden.</span><span class="sxs-lookup"><span data-stu-id="94b52-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="94b52-208">Problemet har orsakats av en bugg i Enhetsportalen hantering av vissa begäranden och används mest konsekvent när https används, vilket är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="94b52-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="94b52-209">Lösning</span><span class="sxs-lookup"><span data-stu-id="94b52-209">Workaround</span></span>

<span data-ttu-id="94b52-210">Den här lösningen, som gäller Wi-Fi och UsbNcm, är att inaktivera alternativet "krävs" under "SSL-anslutning".</span><span class="sxs-lookup"><span data-stu-id="94b52-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="94b52-211">Det gör du genom att Enhetsportalen, **System** och välja **sidan** Inställningar.</span><span class="sxs-lookup"><span data-stu-id="94b52-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="94b52-212">I avsnittet **Enhetssäkerhet** letar du upp **SSL-anslutning** och avmarkerar för att inaktivera **Nödvändig**.</span><span class="sxs-lookup"><span data-stu-id="94b52-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="94b52-213">Användaren bör sedan gå till http://, inte https:// (IP-adress) och funktioner som filuppladdning och nedladdning fungerar.</span><span class="sxs-lookup"><span data-stu-id="94b52-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="94b52-214">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="94b52-215">Blå skärm efter avregistrerad insiderförhandsvisning på en enhet som flashats med en Insider-version</span><span class="sxs-lookup"><span data-stu-id="94b52-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="94b52-216">Det här är ett problem som påverkar användare som är i en Insider-förhandsversion, omsnedstreckade sina HoloLens 2 med en ny insiderförhandsvisning och sedan avregistrerade från Insider-programmet.</span><span class="sxs-lookup"><span data-stu-id="94b52-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="94b52-217">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="94b52-217">This is a **known issue**.</span></span>

<span data-ttu-id="94b52-218">Detta påverkar inte:</span><span class="sxs-lookup"><span data-stu-id="94b52-218">This does not affect:</span></span>
- <span data-ttu-id="94b52-219">Användare som inte har registrerats i Windows Insider</span><span class="sxs-lookup"><span data-stu-id="94b52-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="94b52-220">Insiders:</span><span class="sxs-lookup"><span data-stu-id="94b52-220">Insiders:</span></span>
    - <span data-ttu-id="94b52-221">Om en enhet har registrerats sedan Insider-versioner var version 18362.x</span><span class="sxs-lookup"><span data-stu-id="94b52-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="94b52-222">Om de flashade ett Insider-signerat 19041.x-bygge och förblir registrerade i Insider-programmet</span><span class="sxs-lookup"><span data-stu-id="94b52-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="94b52-223">Runt om:</span><span class="sxs-lookup"><span data-stu-id="94b52-223">Work-around:</span></span> 
- <span data-ttu-id="94b52-224">Undvik problemet</span><span class="sxs-lookup"><span data-stu-id="94b52-224">Avoid the issue</span></span> 
    - <span data-ttu-id="94b52-225">Flasha en icke-insider-version.</span><span class="sxs-lookup"><span data-stu-id="94b52-225">Flash a non-insider build.</span></span> <span data-ttu-id="94b52-226">En av de regelbundna månatliga uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="94b52-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="94b52-227">Håll dig i insiderförhandsvisning</span><span class="sxs-lookup"><span data-stu-id="94b52-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="94b52-228">Omstrecka enheten</span><span class="sxs-lookup"><span data-stu-id="94b52-228">Reflash the device</span></span>

    1. <span data-ttu-id="94b52-229">Försätt [HoloLens 2 i flashläge manuellt](hololens-recovery.md) genom att stänga av helt och hållet utan att ansluta.</span><span class="sxs-lookup"><span data-stu-id="94b52-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="94b52-230">Håll sedan volymen uppåt och tryck på strömknappen.</span><span class="sxs-lookup"><span data-stu-id="94b52-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="94b52-231">Anslut till datorn och öppna Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="94b52-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="94b52-232">Flasha HoloLens 2 till standardbygget.</span><span class="sxs-lookup"><span data-stu-id="94b52-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="94b52-233">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="94b52-234">OneDrive laddar inte upp bilder automatiskt</span><span class="sxs-lookup"><span data-stu-id="94b52-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="94b52-235">OneDrive-appen för HoloLens stöder inte automatisk kamerauppladdning för arbets- eller skolkonton.</span><span class="sxs-lookup"><span data-stu-id="94b52-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="94b52-236">Det här är **ett känt problem.**</span><span class="sxs-lookup"><span data-stu-id="94b52-236">This is a **known issue**.</span></span>

<span data-ttu-id="94b52-237">Workarounds:</span><span class="sxs-lookup"><span data-stu-id="94b52-237">Workarounds:</span></span>

- <span data-ttu-id="94b52-238">Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton.</span><span class="sxs-lookup"><span data-stu-id="94b52-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="94b52-239">Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning).</span><span class="sxs-lookup"><span data-stu-id="94b52-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="94b52-240">Från din Microsoft-konto i OneDrive kan du aktivera automatisk överföring av kamerarulle i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="94b52-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="94b52-241">Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive-appen.</span><span class="sxs-lookup"><span data-stu-id="94b52-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="94b52-242">Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive-appen.</span><span class="sxs-lookup"><span data-stu-id="94b52-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="94b52-243">Välj knappen **+** och välj Ladda **upp.**</span><span class="sxs-lookup"><span data-stu-id="94b52-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="94b52-244">Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > camera roll**.</span><span class="sxs-lookup"><span data-stu-id="94b52-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="94b52-245">Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.</span><span class="sxs-lookup"><span data-stu-id="94b52-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="94b52-246">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="94b52-247">HoloLens svarar inte eller startar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="94b52-248">Om hololens inte startar:</span><span class="sxs-lookup"><span data-stu-id="94b52-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="94b52-249">Om lysdioderna bredvid strömknappen inte tänds eller bara en lysdiod blinkar en kort stund kan du behöva debitera [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="94b52-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="94b52-250">Om lysdioderna tänds när du trycker på strömknappen men du inte kan se något på skärmarna, gör du en hård [återställning av enheten.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="94b52-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="94b52-251">Om hololens blir låst eller inte svarar:</span><span class="sxs-lookup"><span data-stu-id="94b52-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="94b52-252">Stäng av HoloLens genom att trycka på strömknappen tills alla fem lysdioderna stänger av sig själva eller i 15 sekunder om lysdioderna inte svarar.</span><span class="sxs-lookup"><span data-stu-id="94b52-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="94b52-253">Starta HoloLens genom att trycka på strömknappen igen.</span><span class="sxs-lookup"><span data-stu-id="94b52-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="94b52-254">Om de här stegen inte fungerar kan du försöka återställa [din HoloLens 2-enhet](hololens-recovery.md) eller [HoloLens-enhet (första generationen).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="94b52-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="94b52-255">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="94b52-256">Fel om "lågt diskutrymme"</span><span class="sxs-lookup"><span data-stu-id="94b52-256">"Low Disk Space" error</span></span>

<span data-ttu-id="94b52-257">Du måste frigöra lagringsutrymme genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="94b52-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="94b52-258">Ta bort vissa blanksteg som inte används.</span><span class="sxs-lookup"><span data-stu-id="94b52-258">Delete some unused spaces.</span></span> <span data-ttu-id="94b52-259">Gå till **Inställningar**  >    >  **Systemutrymmen**, välj ett utrymme som du inte längre behöver och välj sedan Ta **bort.**</span><span class="sxs-lookup"><span data-stu-id="94b52-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="94b52-260">Ta bort några av de hologram som du har placerat.</span><span class="sxs-lookup"><span data-stu-id="94b52-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="94b52-261">Ta bort några bilder och videor från appen Foton.</span><span class="sxs-lookup"><span data-stu-id="94b52-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="94b52-262">Avinstallera några appar från hololens.</span><span class="sxs-lookup"><span data-stu-id="94b52-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="94b52-263">I listan **Alla appar** trycker du på och håller ned den app som du vill avinstallera och väljer sedan **Avinstallera.**</span><span class="sxs-lookup"><span data-stu-id="94b52-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="94b52-264">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="94b52-265">Kalibreringen misslyckas</span><span class="sxs-lookup"><span data-stu-id="94b52-265">Calibration fails</span></span>

<span data-ttu-id="94b52-266">Kalibrering bör fungera för de flesta, men det finns fall där kalibreringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="94b52-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="94b52-267">Några potentiella orsaker till kalibreringsfel är:</span><span class="sxs-lookup"><span data-stu-id="94b52-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="94b52-268">Bli störande och inte följa kalibreringsmålen</span><span class="sxs-lookup"><span data-stu-id="94b52-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="94b52-269">Dirty or scratched device visor or device visor not positioned properly</span><span class="sxs-lookup"><span data-stu-id="94b52-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="94b52-270">Dirty eller scratched glass</span><span class="sxs-lookup"><span data-stu-id="94b52-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="94b52-271">Vissa typer av kontaktlinser och glasögon (färgade kontaktlinser, några toric kontaktlinser, IR-blockeringsglasögon, några glasögon med höga glasögon, solglasögon eller liknande)</span><span class="sxs-lookup"><span data-stu-id="94b52-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="94b52-272">Mer uttalad snedstreck och vissa ögonfragnstillägg</span><span class="sxs-lookup"><span data-stu-id="94b52-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="94b52-273">Behåring eller tjocka glasögonramar om de blockerar enheten från att se dina ögon</span><span class="sxs-lookup"><span data-stu-id="94b52-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="94b52-274">Vissa ögonlyssna, ögontillstånd eller ögonoperationer som smala ögon, långa ögonfransar, amblyopia, nystagmus, vissa fall av LASIK eller andra ögonoperationer</span><span class="sxs-lookup"><span data-stu-id="94b52-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="94b52-275">Om kalibreringen misslyckas försöker du:</span><span class="sxs-lookup"><span data-stu-id="94b52-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="94b52-276">Rensa enhetsvisor-programmet</span><span class="sxs-lookup"><span data-stu-id="94b52-276">Cleaning your device visor</span></span>
- <span data-ttu-id="94b52-277">Rensa glasögonen</span><span class="sxs-lookup"><span data-stu-id="94b52-277">Cleaning your glasses</span></span>
- <span data-ttu-id="94b52-278">Push-pusha enhetsvisor-programmet så nära dina ögon som möjligt</span><span class="sxs-lookup"><span data-stu-id="94b52-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="94b52-279">Flytta objekt i ditt visor-program från vägen (till exempel hår)</span><span class="sxs-lookup"><span data-stu-id="94b52-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="94b52-280">Aktivera en lampa i rummet eller flytta ut direkt från rummet</span><span class="sxs-lookup"><span data-stu-id="94b52-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="94b52-281">Om du har följt alla riktlinjer och kalibreringen fortfarande misslyckas kan du inaktivera kalibreringsuppmaning i Inställningar.</span><span class="sxs-lookup"><span data-stu-id="94b52-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="94b52-282">Meddela oss också genom att skicka feedback i [Feedbackhubben](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="94b52-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="94b52-283">Se även relaterad information för felsökning [av bildfärg eller ljusstyrka.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="94b52-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="94b52-284">Inställningen IPD gäller inte för HoloLens 2, eftersom ögonpositioner beräknas av systemet.</span><span class="sxs-lookup"><span data-stu-id="94b52-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="94b52-285">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="94b52-286">Det går inte att logga in eftersom min HoloLens tidigare har ställts in för någon annan</span><span class="sxs-lookup"><span data-stu-id="94b52-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="94b52-287">Du kan [placera enheten i **flashläge och använda** Advanced Recovery Companion för](hololens-recovery.md#clean-reflash-the-device) att återställa enheten.</span><span class="sxs-lookup"><span data-stu-id="94b52-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="94b52-288">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="94b52-289">Unity fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-289">Unity isn't working</span></span>

- <span data-ttu-id="94b52-290">Se [Installera verktygen för](/windows/mixed-reality/install-the-tools) den senaste versionen av Unity som rekommenderas för HoloLens-utveckling.</span><span class="sxs-lookup"><span data-stu-id="94b52-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="94b52-291">Kända problem med Unity HoloLens Technical Preview finns dokumenterade i [HoloLens Unity-forumen](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="94b52-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="94b52-292">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="94b52-293">Windows Enhetsportalen fungerar inte korrekt</span><span class="sxs-lookup"><span data-stu-id="94b52-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="94b52-294">Funktionen Förhandsgranskning i Mixed Reality kan uppvisa flera sekunders svarstid.</span><span class="sxs-lookup"><span data-stu-id="94b52-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="94b52-295">På sidan Virtuella indata fungerar inte gester- och rullningskontrollerna i avsnittet Virtuella gester.</span><span class="sxs-lookup"><span data-stu-id="94b52-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="94b52-296">Att använda dem har ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="94b52-296">Using them will have no effect.</span></span> <span data-ttu-id="94b52-297">Det virtuella tangentbordet på den virtuella indatasidan fungerar korrekt.</span><span class="sxs-lookup"><span data-stu-id="94b52-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="94b52-298">När du har aktiverat Utvecklarläge i Inställningar kan det ta några sekunder innan växeln aktiveras för Enhetsportalen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="94b52-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="94b52-299">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="94b52-300">Emulator</span><span class="sxs-lookup"><span data-stu-id="94b52-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="94b52-301">HoloLens-emulatorn fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="94b52-302">Information om HoloLens-emulatorn finns i vår utvecklardokumentation.</span><span class="sxs-lookup"><span data-stu-id="94b52-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="94b52-303">Läs mer om felsökning [av HoloLens-emulatorn](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="94b52-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="94b52-304">Alla appar i Microsoft Store är inte kompatibla med emulatorn.</span><span class="sxs-lookup"><span data-stu-id="94b52-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="94b52-305">Till exempel är Young Conker och Fragment inte spelbara i emulatorn.</span><span class="sxs-lookup"><span data-stu-id="94b52-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="94b52-306">Du kan inte använda pc-webbkameran i emulatorn.</span><span class="sxs-lookup"><span data-stu-id="94b52-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="94b52-307">Funktionen Liveförhandsgranskning i Windows Enhetsportalen fungerar inte med emulatorn.</span><span class="sxs-lookup"><span data-stu-id="94b52-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="94b52-308">Du kan fortfarande samla Mixed Reality videor och bilder.</span><span class="sxs-lookup"><span data-stu-id="94b52-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="94b52-309">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="94b52-310">Jag kan inte hitta eller använda tangentbordet för att skriva i HoloLens 2-emulatorn</span><span class="sxs-lookup"><span data-stu-id="94b52-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="94b52-311">*Kommer snart*</span><span class="sxs-lookup"><span data-stu-id="94b52-311">*Coming soon*</span></span>

[<span data-ttu-id="94b52-312">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="94b52-313">Röstkommandon fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-313">Voice commands aren't working</span></span>

<span data-ttu-id="94b52-314">Om Cortana inte svarar på dina röstkommandon kontrollerar du att Cortana är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="94b52-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="94b52-315">I listan Alla appar Cortana-menyn Notebook Settings  >    >  **(Notebook-inställningar för**  >  **Cortana-menyn)** för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="94b52-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="94b52-316">Mer information om vad du kan säga finns i [Använda din röst med HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="94b52-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="94b52-317">På HoloLens (första generationen) kan inte inbyggd taligenkänning konfigureras.</span><span class="sxs-lookup"><span data-stu-id="94b52-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="94b52-318">Den är alltid aktiverad.</span><span class="sxs-lookup"><span data-stu-id="94b52-318">It is always turned on.</span></span> <span data-ttu-id="94b52-319">På HoloLens 2 kan du välja om du vill aktivera både taligenkänning och Cortana under enhetskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="94b52-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="94b52-320">Om HoloLens 2 inte svarar på din röst kontrollerar du att Taligenkänning är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="94b52-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="94b52-321">Gå till  >  **Startinställningar**  >    >  **Sekretesstal** och aktivera **Taligenkänning.**</span><span class="sxs-lookup"><span data-stu-id="94b52-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="94b52-322">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="94b52-323">Handindata fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-323">Hand input isn't working</span></span>

<span data-ttu-id="94b52-324">För att säkerställa att HoloLens kan se dina händer måste du hålla dem inom gestens ram.</span><span class="sxs-lookup"><span data-stu-id="94b52-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="94b52-325">Startsidan Mixed Reality feedback som meddelar dig när dina händer spåras.</span><span class="sxs-lookup"><span data-stu-id="94b52-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="94b52-326">Feedbacken är annorlunda i olika versioner av HoloLens:</span><span class="sxs-lookup"><span data-stu-id="94b52-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="94b52-327">På HoloLens (1:a gen) ändras blickmarkören från en punkt till en ring</span><span class="sxs-lookup"><span data-stu-id="94b52-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="94b52-328">På HoloLens 2 visas en handmarkör när din hand är nära en pektavla och en handröta visas när pekarna är längre bort</span><span class="sxs-lookup"><span data-stu-id="94b52-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="94b52-329">Många integrerande appar följer indatamönster som liknar Mixed Reality Home.</span><span class="sxs-lookup"><span data-stu-id="94b52-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="94b52-330">Läs mer om att använda handindata [på HoloLens (första generationen)](hololens1-basic-usage.md#use-hololens-with-your-hands) och [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)</span><span class="sxs-lookup"><span data-stu-id="94b52-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="94b52-331">Observera att vissa typer av handsken inte fungerar med handspårning om du bär handskydd.</span><span class="sxs-lookup"><span data-stu-id="94b52-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="94b52-332">Ett vanligt exempel är svarta handskes, som tenderar att absorbera IR-ljus och inte hämtas av djupkameran.</span><span class="sxs-lookup"><span data-stu-id="94b52-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="94b52-333">Om ditt arbete omfattar skyddshandske rekommenderar vi att du provar en ljusare färg, till exempel blå eller grå.</span><span class="sxs-lookup"><span data-stu-id="94b52-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="94b52-334">Ett annat exempel är stora baggy gloves, som tenderar att dölja formen på din hand.</span><span class="sxs-lookup"><span data-stu-id="94b52-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="94b52-335">Vi rekommenderar att du använder så väl formpassning som möjligt för bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="94b52-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="94b52-336">Om ditt visir har fingeravtryck eller utsmetning använder du mikrofiberrensningen som medkom med HoloLens för att rensa visorn.</span><span class="sxs-lookup"><span data-stu-id="94b52-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="94b52-337">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="94b52-338">Det går inte att ansluta till Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="94b52-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="94b52-339">Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:</span><span class="sxs-lookup"><span data-stu-id="94b52-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="94b52-340">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="94b52-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="94b52-341">Kontrollera genom att använda gesten Start och sedan välja **Inställningar**  >  **&amp; Nätverkets**  >  **Internet-Wi-Fi.**</span><span class="sxs-lookup"><span data-stu-id="94b52-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="94b52-342">Om Wi-Fi är på kan du prova att stänga av den och sedan aktivera igen.</span><span class="sxs-lookup"><span data-stu-id="94b52-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="94b52-343">Flytta datorn närmare routern eller åtkomstpunkten.</span><span class="sxs-lookup"><span data-stu-id="94b52-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="94b52-344">Starta om Wi-Fi router och starta [sedan om HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="94b52-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="94b52-345">Försök att ansluta igen.</span><span class="sxs-lookup"><span data-stu-id="94b52-345">Try connecting again.</span></span>
- <span data-ttu-id="94b52-346">Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran.</span><span class="sxs-lookup"><span data-stu-id="94b52-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="94b52-347">Du hittar den här informationen på tillverkarens webbplats.</span><span class="sxs-lookup"><span data-stu-id="94b52-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="94b52-348">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="94b52-349">Bluetooth-enheter parkopplas inte</span><span class="sxs-lookup"><span data-stu-id="94b52-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="94b52-350">Om du har problem med att [koppla en Bluetooth-enhet](hololens-connect-devices.md)kan du prova följande:</span><span class="sxs-lookup"><span data-stu-id="94b52-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="94b52-351">Gå till  >  **Inställningar Enheter** och kontrollera att Bluetooth är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="94b52-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="94b52-352">Om den är det inaktiverar du den och sätter på den igen.</span><span class="sxs-lookup"><span data-stu-id="94b52-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="94b52-353">Kontrollera att Bluetooth-enheten är helt debiterad eller har nya batterier.</span><span class="sxs-lookup"><span data-stu-id="94b52-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="94b52-354">Om du fortfarande inte kan ansluta startar [du om HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="94b52-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="94b52-355">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="94b52-356">USB-C-mikrofonen fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="94b52-357">Tänk på att vissa USB-C-mikrofoner felaktigt rapporterar sig själva som både *en mikrofon och* en talare.</span><span class="sxs-lookup"><span data-stu-id="94b52-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="94b52-358">Det här är ett problem med mikrofonen och inte med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94b52-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="94b52-359">När någon av dessa mikrofoner ansluts till HoloLens kan ljudet gå förlorat.</span><span class="sxs-lookup"><span data-stu-id="94b52-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="94b52-360">Lyckligtvis finns det en enkel korrigering.</span><span class="sxs-lookup"><span data-stu-id="94b52-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="94b52-361">I **Inställningar**  ->    ->  **Systemljud** anger du uttryckligen de inbyggda talarna **(Analog Feature Audio Driver)** som **Standardenhet**.</span><span class="sxs-lookup"><span data-stu-id="94b52-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="94b52-362">HoloLens bör komma ihåg den här inställningen även om mikrofonen tas bort och återansluts senare.</span><span class="sxs-lookup"><span data-stu-id="94b52-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Felsöka USB-C-mikrofoner](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="94b52-364">Enheter som anges som tillgängliga i Inställningarna fungerar inte</span><span class="sxs-lookup"><span data-stu-id="94b52-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="94b52-365">HoloLens (första generationen) stöder inte Bluetooth-ljudprofiler.</span><span class="sxs-lookup"><span data-stu-id="94b52-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="94b52-366">Bluetooth-ljudenheter, till exempel högtalare och headset, kan visas som tillgängliga i HoloLens-inställningar, men de stöds inte.</span><span class="sxs-lookup"><span data-stu-id="94b52-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="94b52-367">HoloLens 2 stöder Bluetooth A2DP-ljudprofilen för stereouppspelning.</span><span class="sxs-lookup"><span data-stu-id="94b52-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="94b52-368">Profilen Bluetooth Hands Free som aktiverar mikrofoninfångning från bluetooth-kringutrustning stöds inte på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="94b52-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="94b52-369">Om du har problem med att använda en Bluetooth-enhet kontrollerar du att det är en enhet som stöds.</span><span class="sxs-lookup"><span data-stu-id="94b52-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="94b52-370">Enheter som stöds är följande:</span><span class="sxs-lookup"><span data-stu-id="94b52-370">Supported devices include the following:</span></span>

- <span data-ttu-id="94b52-371">QWERTY Bluetooth-tangentbord på engelska (du kan använda dem var som helst där du använder det holografiska tangentbordet).</span><span class="sxs-lookup"><span data-stu-id="94b52-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="94b52-372">Bluetooth-mice.</span><span class="sxs-lookup"><span data-stu-id="94b52-372">Bluetooth mice.</span></span>
- <span data-ttu-id="94b52-373">[HoloLens-klickaren](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="94b52-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="94b52-374">Du kan koppla ihop andra Bluetooth HID- och GATT-enheter med din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94b52-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="94b52-375">Du kan dock behöva installera motsvarande tillhörande appar från Microsoft Store för att faktiskt använda enheterna.</span><span class="sxs-lookup"><span data-stu-id="94b52-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="94b52-376">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="94b52-376">Back to list</span></span>](#list)
