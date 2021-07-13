---
title: Insiderförhandsvisning för Microsoft HoloLens
description: Lär dig hur du kommer igång med Insider-byggen och ge värdefull feedback för vår nästa större uppdatering av operativsystemet för HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636131"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="1697f-103">Insiderförhandsvisning för Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="1697f-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="1697f-104">Välkommen till de senaste Insider Preview-versionerna för HoloLens!</span><span class="sxs-lookup"><span data-stu-id="1697f-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="1697f-105">Det är enkelt att [komma igång och](hololens-insider.md#start-receiving-insider-builds) ge värdefull feedback för nästa större operativsystemuppdatering för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1697f-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="1697f-106">Windows Insiders versionsanteckningar</span><span class="sxs-lookup"><span data-stu-id="1697f-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="1697f-107">Vi är glada över att kunna börja använda nya funktioner för Windows Insiders igen.</span><span class="sxs-lookup"><span data-stu-id="1697f-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="1697f-108">Nya byggen kommer att gå vidare till dev- och betakanalerna för att få de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="1697f-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="1697f-109">Vi kommer att fortsätta att uppdatera den här sidan när vi lägger till fler funktioner och uppdateringar Windows Insider-versionerna.</span><span class="sxs-lookup"><span data-stu-id="1697f-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="1697f-110">Bli spänd och redo att blanda de här uppdateringarna i din verklighet.</span><span class="sxs-lookup"><span data-stu-id="1697f-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="1697f-111">Funktion</span><span class="sxs-lookup"><span data-stu-id="1697f-111">Feature</span></span>                 | <span data-ttu-id="1697f-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1697f-112">Description</span></span>                | <span data-ttu-id="1697f-113">Användare eller scenario</span><span class="sxs-lookup"><span data-stu-id="1697f-113">User or Scenario</span></span> | <span data-ttu-id="1697f-114">Skapa introducerat</span><span class="sxs-lookup"><span data-stu-id="1697f-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="1697f-115">CSP-ändringar för HoloLens information</span><span class="sxs-lookup"><span data-stu-id="1697f-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="1697f-116">Nya CPP:er för att fråga efter data</span><span class="sxs-lookup"><span data-stu-id="1697f-116">New CSPs for to query data</span></span> | <span data-ttu-id="1697f-117">IT-administratörer</span><span class="sxs-lookup"><span data-stu-id="1697f-117">IT Admins</span></span>    | <span data-ttu-id="1697f-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="1697f-118">20348.1403</span></span>                 |
| [<span data-ttu-id="1697f-119">Princip för automatisk inloggning som styrs av CSP</span><span class="sxs-lookup"><span data-stu-id="1697f-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="1697f-120">Används för att logga in ett konto automatiskt</span><span class="sxs-lookup"><span data-stu-id="1697f-120">Used to log in an account automatically</span></span> | <span data-ttu-id="1697f-121">IT-administratörer</span><span class="sxs-lookup"><span data-stu-id="1697f-121">IT Admins</span></span> | <span data-ttu-id="1697f-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="1697f-122">20348.1405</span></span> |
| [<span data-ttu-id="1697f-123">PFX-filstöd för Certificate Manager</span><span class="sxs-lookup"><span data-stu-id="1697f-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="1697f-124">Lägga till PFX-certifikat via Inställningar användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="1697f-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="1697f-125">Slutanvändare</span><span class="sxs-lookup"><span data-stu-id="1697f-125">End User</span></span> | <span data-ttu-id="1697f-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="1697f-126">20348.1405</span></span> |
| [<span data-ttu-id="1697f-127">Visa avancerad diagnostikrapport i Inställningar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="1697f-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="1697f-128">Visa MDM-diagnostikloggar på enheten</span><span class="sxs-lookup"><span data-stu-id="1697f-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="1697f-129">Felsökning</span><span class="sxs-lookup"><span data-stu-id="1697f-129">Troubleshooting</span></span> | <span data-ttu-id="1697f-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="1697f-130">20348.1405</span></span> |
| [<span data-ttu-id="1697f-131">Aviseringar om offlinediagnostik</span><span class="sxs-lookup"><span data-stu-id="1697f-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="1697f-132">Feedback om logginsamling</span><span class="sxs-lookup"><span data-stu-id="1697f-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="1697f-133">Felsökning</span><span class="sxs-lookup"><span data-stu-id="1697f-133">Troubleshooting</span></span> | <span data-ttu-id="1697f-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="1697f-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="1697f-135">CSP-ändringar för HoloLens information</span><span class="sxs-lookup"><span data-stu-id="1697f-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="1697f-136">Introducerades i Windows Insider build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="1697f-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="1697f-137">Följande CPS har uppdaterats med nya sätt att rapportera information från dina HoloLens enheter.</span><span class="sxs-lookup"><span data-stu-id="1697f-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="1697f-138">CSP:t DevDetail – kostnadsfri Storage</span><span class="sxs-lookup"><span data-stu-id="1697f-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="1697f-139">DevDetail CSP rapporterar nu även ledigt lagringsutrymme på HoloLens enhet.</span><span class="sxs-lookup"><span data-stu-id="1697f-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="1697f-140">Detta bör ungefär matcha det värde som visas Inställningar appens Storage sida.</span><span class="sxs-lookup"><span data-stu-id="1697f-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="1697f-141">Nedan visas den specifika nod som innehåller den här informationen.</span><span class="sxs-lookup"><span data-stu-id="1697f-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="1697f-142">./DevDetail/Ext/Microsoft/FreeStorage (endast GET-åtgärd)</span><span class="sxs-lookup"><span data-stu-id="1697f-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="1697f-143">DeviceStatus CSP – SSID och BSSID</span><span class="sxs-lookup"><span data-stu-id="1697f-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="1697f-144">DeviceStatus CSP rapporterar nu även SSID och BSSID för Wi-Fi nätverk som HoloLens är aktivt ansluten till.</span><span class="sxs-lookup"><span data-stu-id="1697f-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="1697f-145">Nedan visas de specifika noder som innehåller den här informationen.</span><span class="sxs-lookup"><span data-stu-id="1697f-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="1697f-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="1697f-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="1697f-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adress för Wi-Fi*/BSSID</span><span class="sxs-lookup"><span data-stu-id="1697f-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="1697f-148">Exempel på syncml-blob (för MDM-leverantörer) för att fråga efter NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="1697f-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="1697f-149">Princip för automatisk inloggning som styrs av CSP</span><span class="sxs-lookup"><span data-stu-id="1697f-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="1697f-150">Den här nya AutoLogonUser-principen styr om en användare loggas in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1697f-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="1697f-151">Vissa kunder vill konfigurera enheter som är knutna till en identitet men inte vill ha någon inloggningsupplevelse.</span><span class="sxs-lookup"><span data-stu-id="1697f-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="1697f-152">Imagine att hämta en enhet och använda fjärrhjälp omedelbart.</span><span class="sxs-lookup"><span data-stu-id="1697f-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="1697f-153">Eller ha en fördel med att snabbt kunna distribuera HoloLens enheter och göra det möjligt för slutanvändarna att påskynda inloggningen.</span><span class="sxs-lookup"><span data-stu-id="1697f-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="1697f-154">När principen har angetts till ett värde som inte är tomt anges e-postadressen för den användare som loggar in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1697f-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="1697f-155">Den angivna användaren måste logga in på enheten minst en gång för att aktivera automatisk inloggning.</span><span class="sxs-lookup"><span data-stu-id="1697f-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="1697f-156">OMA-URI för nytt `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` principsträngvärde</span><span class="sxs-lookup"><span data-stu-id="1697f-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="1697f-157">Automatisk inloggning är aktiverat för användare med samma e-postadress.</span><span class="sxs-lookup"><span data-stu-id="1697f-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="1697f-158">På en enhet där den här principen har konfigurerats måste användaren som anges i principen logga in minst en gång.</span><span class="sxs-lookup"><span data-stu-id="1697f-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="1697f-159">Efterföljande omstarter av enheten efter den första inloggningen kommer den angivna användaren att loggas in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1697f-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="1697f-160">Endast en användare för automatisk inloggning stöds.</span><span class="sxs-lookup"><span data-stu-id="1697f-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="1697f-161">När den automatiskt inloggade användaren har aktiverats kan den inte logga ut manuellt.</span><span class="sxs-lookup"><span data-stu-id="1697f-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="1697f-162">Om du vill logga in som en annan användare måste principen först inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="1697f-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="1697f-163">Vissa händelser, till exempel större OS-uppdateringar, kan kräva att den angivna användaren loggar in på enheten igen för att återuppta beteendet för automatisk inloggning.</span><span class="sxs-lookup"><span data-stu-id="1697f-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="1697f-164">Automatisk inloggning stöds endast för MSA- och AAD-användare.</span><span class="sxs-lookup"><span data-stu-id="1697f-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="1697f-165">PFX-filstöd för Certificate Manager</span><span class="sxs-lookup"><span data-stu-id="1697f-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="1697f-166">Introducerades i Windows Insider version 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="1697f-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="1697f-167">Vi har lagt till stöd för Certifikathanteraren [för att](certificate-manager.md) nu använda .pfx-certifikat.</span><span class="sxs-lookup"><span data-stu-id="1697f-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="1697f-168">När användarna navigerar **till Inställningar** Update & Security Certificates och väljer Installera ett certifikat har användargränssnittet nu stöd för  >    >  PFX-certifikatfilen. </span><span class="sxs-lookup"><span data-stu-id="1697f-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="1697f-169">Användare kan importera PFX-certifikat, med privat nyckel, till användararkivet eller datorarkivet.</span><span class="sxs-lookup"><span data-stu-id="1697f-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="1697f-170">Visa avancerad diagnostikrapport i Inställningar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="1697f-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="1697f-171">För hanterade enheter vid felsökning av beteende är det viktigt att bekräfta att en förväntad principkonfiguration tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1697f-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="1697f-172">Tidigare i den här nya funktionen behövde detta göras av enheten via MDM eller nära enheten efter export av MDM-diagnostikloggar som samlats in via  ->  **Inställningar-konton** Åtkomst till arbete eller skola och välja  >   **Exportera** dina hanteringsloggar och visa dem på en närliggande dator.</span><span class="sxs-lookup"><span data-stu-id="1697f-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="1697f-173">Nu kan MDM-diagnostiken visas på enheten med hjälp av Edge-webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="1697f-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="1697f-174">Om du vill visa MDM-diagnostikrapporten enklare går du till sidan Åtkomst till arbete eller skola och väljer **Visa avancerad diagnostikrapport.**</span><span class="sxs-lookup"><span data-stu-id="1697f-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="1697f-175">Detta genererar och öppnar rapporten i ett nytt Edge-fönster.</span><span class="sxs-lookup"><span data-stu-id="1697f-175">This will generate and open the report in a new Edge window.</span></span>

![Visa avancerad diagnostikrapport i Inställningar app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="1697f-177">Aviseringar om offlinediagnostik</span><span class="sxs-lookup"><span data-stu-id="1697f-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="1697f-178">Detta är en uppdatering för en befintlig funktion som heter [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span><span class="sxs-lookup"><span data-stu-id="1697f-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="1697f-179">Tidigare fanns det ingen tydlig indikator för användarna att de utlöst diagnostikinsamlingen eller att den hade slutförts.</span><span class="sxs-lookup"><span data-stu-id="1697f-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="1697f-180">Det finns nu två Windows feedback om offlinediagnostik som läggs till i Windows Insider-byggen.</span><span class="sxs-lookup"><span data-stu-id="1697f-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="1697f-181">Den första är popup-meddelanden som visas för både när samlingen startar och slutförs.</span><span class="sxs-lookup"><span data-stu-id="1697f-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="1697f-182">Dessa visas när användaren är inloggad och har visuella objekt.</span><span class="sxs-lookup"><span data-stu-id="1697f-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Popup-meddelande för insamling av loggar.](./images/logcollection1.jpg)

![Popup-meddelande när logginsamlingen är klar.](./images/logcollection2.jpg)
 
<span data-ttu-id="1697f-185">Eftersom användare ofta använder offlinediagnostik som reservlogginsamlingsmekanism för när de inte har åtkomst till en visning, inte kan logga in eller är kvar i OOBE, spelas även en ljudikon upp när loggar samlas in.</span><span class="sxs-lookup"><span data-stu-id="1697f-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="1697f-186">Det här ljudet spelas upp utöver popup-meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1697f-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="1697f-187">Den här nya funktionen aktiveras när enheten uppdateras och behöver inte aktiveras eller hanteras.</span><span class="sxs-lookup"><span data-stu-id="1697f-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="1697f-188">Om denna nya feedback inte kan visas eller höras genereras fortfarande offlinediagnostik.</span><span class="sxs-lookup"><span data-stu-id="1697f-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="1697f-189">Vi hoppas att med den här nyare feedbacken blir det enklare att samla in diagnostikdata och snabbare kunna felsöka dina problem.</span><span class="sxs-lookup"><span data-stu-id="1697f-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="1697f-190">Korrigeringar och förbättringar:</span><span class="sxs-lookup"><span data-stu-id="1697f-190">Fixes and improvements:</span></span>

- <span data-ttu-id="1697f-191">Ett känt [problem har åtgärdats för Enhetsportalen där det inte fanns någon uppmaning om att ladda ned låsta filer.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="1697f-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="1697f-192">Åtgärdat [ett känt problem för Enhetsportalen med time out för filuppladdning och nedladdning.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="1697f-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="1697f-193">Börja ta emot Insider-byggen</span><span class="sxs-lookup"><span data-stu-id="1697f-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="1697f-194">Om du inte har uppdaterat nyligen startar du om enheten för att uppdatera statusen och hämta den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="1697f-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="1697f-195">Röstkommandot "Starta om enheten" fungerar bra.</span><span class="sxs-lookup"><span data-stu-id="1697f-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="1697f-196">Du kan också välja omstartsknappen i Inställningar/Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="1697f-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="1697f-197">Det har uppstått en bugg i backend-delen som du kan ha stött på, vilket gör att du kommer igång igen.</span><span class="sxs-lookup"><span data-stu-id="1697f-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="1697f-198">På en HoloLens 2-enhet **går du till Inställningar**  >  **Update & Security**  >  **Windows Insider Program** och väljer **Kom igång.**</span><span class="sxs-lookup"><span data-stu-id="1697f-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="1697f-199">Länka det konto som du använde för att registrera dig Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="1697f-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="1697f-200">Windows insider flyttas nu till kanaler.</span><span class="sxs-lookup"><span data-stu-id="1697f-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="1697f-201">Den **snabba** ringen blir Dev  **Channel,** den långsamma ringen blir **den Betakanal** och **förhandsversionsringen** blir kanalen **för förhandsversionen.**</span><span class="sxs-lookup"><span data-stu-id="1697f-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="1697f-202">Så här ser mappningen ut:</span><span class="sxs-lookup"><span data-stu-id="1697f-202">Here is what that mapping looks like:</span></span>

![Windows Förklaring av insiderkanaler](images/WindowsInsiderChannels.png)

<span data-ttu-id="1697f-204">Mer information finns i Introduktion [till Windows Insider-kanaler](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) på Windows bloggar.</span><span class="sxs-lookup"><span data-stu-id="1697f-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="1697f-205">Välj sedan **Aktiv utveckling av Windows**, välj om du vill ta emot Dev **Channel** **eller Betakanal-byggen** och granska programvillkoren.</span><span class="sxs-lookup"><span data-stu-id="1697f-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="1697f-206">Välj **Bekräfta > starta om nu** för att slutföra.</span><span class="sxs-lookup"><span data-stu-id="1697f-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="1697f-207">När enheten har startats om går du **till Inställningar > Update & Security > Sök** efter uppdateringar för att få den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="1697f-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="1697f-208">Uppdatera fel 0x80070490 för att komma runt</span><span class="sxs-lookup"><span data-stu-id="1697f-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="1697f-209">Om du stöter på ett 0x80070490 när du uppdaterar på Dev- eller Beta-kanalen kan du prova följande kortsiktiga lösning.</span><span class="sxs-lookup"><span data-stu-id="1697f-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="1697f-210">Det innebär att du flyttar din insiderkanal, hämtar uppdateringen och sedan flyttar tillbaka Insider-kanalen.</span><span class="sxs-lookup"><span data-stu-id="1697f-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="1697f-211">Steg ett – förhandsversion</span><span class="sxs-lookup"><span data-stu-id="1697f-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="1697f-212">Inställningar, Update & Security, Windows Insider Program du Release Preview **Channel**.</span><span class="sxs-lookup"><span data-stu-id="1697f-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="1697f-213">Inställningar, Update & Security, Windows Update, Check **for updates**.</span><span class="sxs-lookup"><span data-stu-id="1697f-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="1697f-214">Efter uppdateringen fortsätter du till Steg två.</span><span class="sxs-lookup"><span data-stu-id="1697f-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="1697f-215">Steg två – Dev Channel</span><span class="sxs-lookup"><span data-stu-id="1697f-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="1697f-216">Inställningar, Update & Security, Windows Insider Program väljer du **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="1697f-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="1697f-217">Inställningar, Update & Security, Windows Update, Check **for updates**.</span><span class="sxs-lookup"><span data-stu-id="1697f-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="1697f-218">FFU-nedladdning och flash-riktningar</span><span class="sxs-lookup"><span data-stu-id="1697f-218">FFU download and flash directions</span></span>

<span data-ttu-id="1697f-219">Om du vill testa med ett flyg signerat ffu måste du först flygupplåsa enheten innan du flashar den flyg signerade ffu.</span><span class="sxs-lookup"><span data-stu-id="1697f-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="1697f-220">På datorn:</span><span class="sxs-lookup"><span data-stu-id="1697f-220">On PC:</span></span>
    1. <span data-ttu-id="1697f-221">Ladda ned ffu till datorn från [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="1697f-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="1697f-222">Installera ARC (Advanced Recovery Companion) från Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="1697f-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="1697f-223">På HoloLens – Flight Unlock: **Öppna Inställningar** Update &  >  **Security**  >  **Windows Insider Program** sedan registrera dig och starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="1697f-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="1697f-224">Flash FFU – Nu kan du flasha den flyg signerade FFU:en med arc.</span><span class="sxs-lookup"><span data-stu-id="1697f-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="1697f-225">Ge feedback och rapportera problem</span><span class="sxs-lookup"><span data-stu-id="1697f-225">Provide feedback and report issues</span></span>

<span data-ttu-id="1697f-226">Använd appen [Feedbackhubben på](hololens-feedback.md) din dator HoloLens att ge feedback och rapportera problem.</span><span class="sxs-lookup"><span data-stu-id="1697f-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="1697f-227">Med Feedbackhubben ser du till att all nödvändig diagnostikinformation ingår för att våra tekniker snabbt ska kunna felsöka och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="1697f-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="1697f-228">Problem med den kinesiska och japanska versionen av HoloLens bör rapporteras på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="1697f-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="1697f-229">Se till att acceptera uppmaningen som frågar om du vill Feedbackhubben åtkomst till mappen Dokument (välj **Ja när** du tillfrågas).</span><span class="sxs-lookup"><span data-stu-id="1697f-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="1697f-230">Obs! För utvecklare</span><span class="sxs-lookup"><span data-stu-id="1697f-230">Note for developers</span></span>

<span data-ttu-id="1697f-231">Du är välkommen och uppmanas att prova att utveckla dina program med insider-HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1697f-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="1697f-232">Läs dokumentationen [HoloLens developer för](https://developer.microsoft.com/windows/mixed-reality/development) att komma igång.</span><span class="sxs-lookup"><span data-stu-id="1697f-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="1697f-233">Samma instruktioner fungerar med Insider-HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1697f-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="1697f-234">Du kan använda samma version av Unity och Visual Studio som du redan använder för HoloLens utveckling.</span><span class="sxs-lookup"><span data-stu-id="1697f-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="1697f-235">Sluta ta emot Insider-byggen</span><span class="sxs-lookup"><span data-stu-id="1697f-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="1697f-236">Om du inte längre vill ta emot Insider-versioner av Windows Holographic kan du avanmäla dig när [](hololens-recovery.md) din HoloLens kör en produktionsversion, eller så kan du återställa din enhet med hjälp av Advanced Recovery Companion för att återställa enheten till en icke-Insider-version av Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="1697f-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="1697f-237">Det finns ett känt problem där användare som avregistrerar sig från Insider Preview skapar efter att ha installerat om en ny förhandsversion manuellt skulle uppleva en blå skärm.</span><span class="sxs-lookup"><span data-stu-id="1697f-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="1697f-238">Därefter måste de återställa sin enhet manuellt.</span><span class="sxs-lookup"><span data-stu-id="1697f-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="1697f-239">Fullständig information om om du skulle påverkas eller inte finns i mer information om det [här kända problemet.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="1697f-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="1697f-240">Så här kontrollerar du HoloLens kör ett produktionsbygge:</span><span class="sxs-lookup"><span data-stu-id="1697f-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="1697f-241">Gå till **Inställningar > System > Om** och leta reda på build-numret.</span><span class="sxs-lookup"><span data-stu-id="1697f-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="1697f-242">[Se den nya versionen för produktions build-nummer.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="1697f-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="1697f-243">Så här avanmäler du dig från Insider-byggen:</span><span class="sxs-lookup"><span data-stu-id="1697f-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="1697f-244">På en HoloLens som kör en produktionsbygge **går du till Inställningar > Update & Security > Windows Insider Program** och väljer Stoppa **Insider-byggen.**</span><span class="sxs-lookup"><span data-stu-id="1697f-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="1697f-245">Följ anvisningarna för att avanmäla enheten.</span><span class="sxs-lookup"><span data-stu-id="1697f-245">Follow the instructions to opt out your device.</span></span>
