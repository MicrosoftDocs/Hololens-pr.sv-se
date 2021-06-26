---
title: Felsökning av HoloLens 2-implementering och hanterad enhet
description: Felsöka HoloLens 2-enheter i en företagsmiljö
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: felsökning
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961646"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="bd0af-104">Felsökning av implementering och hanterade enheter</span><span class="sxs-lookup"><span data-stu-id="bd0af-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="bd0af-105">Den här artikeln beskriver hur du löser flera problem eller besvarar frågor om implementering och hantering av HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bd0af-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bd0af-106">Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="bd0af-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="bd0af-107">Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="bd0af-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="bd0af-108">EAP-felsökning</span><span class="sxs-lookup"><span data-stu-id="bd0af-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="bd0af-109">Felsökning av Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="bd0af-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="bd0af-110">Felsökning av nätverk</span><span class="sxs-lookup"><span data-stu-id="bd0af-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="bd0af-111">Det går inte att logga in på en tidigare konfigurerad HoloLens-enhet</span><span class="sxs-lookup"><span data-stu-id="bd0af-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="bd0af-112">Det går inte att logga in efter uppdatering till Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="bd0af-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="bd0af-113">Autopilot-felsökning</span><span class="sxs-lookup"><span data-stu-id="bd0af-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="bd0af-114">Vanliga frågor och svar om Hanterade HoloLens-enheter</span><span class="sxs-lookup"><span data-stu-id="bd0af-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="bd0af-115">EAP-felsökning</span><span class="sxs-lookup"><span data-stu-id="bd0af-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="bd0af-116">Dubbel kontroll Wi-Fi profilen har rätt inställningar:</span><span class="sxs-lookup"><span data-stu-id="bd0af-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="bd0af-117">EAP-typen är korrekt konfigurerad, vanliga EAP-typer: EAP-TLS (13), EAP-TTLS (21) och PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="bd0af-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="bd0af-118">Wi-Fi SSID-namnet är rätt och matchar med HEX-strängen.</span><span class="sxs-lookup"><span data-stu-id="bd0af-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="bd0af-119">För EAP-TLS innehåller TrustedRootCA SHA-1-hashen för serverns betrodda rotcertifikatutfärdare.</span><span class="sxs-lookup"><span data-stu-id="bd0af-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="bd0af-120">På Windows PC-kommandot "certutil.exe -dump cert_file_name" visas certifikatets SHA-1-hashsträng.</span><span class="sxs-lookup"><span data-stu-id="bd0af-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="bd0af-121">Samla in infångade nätverkspaket på åtkomstpunkten, kontrollanten eller AAA-serverloggarna för att ta reda på var EAP-sessionen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="bd0af-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="bd0af-122">Om den EAP-identitet som tillhandahålls av HoloLens inte förväntas kontrollerar du om identiteten har etablerats korrekt via Wi-Fi profil eller klientcertifikat.</span><span class="sxs-lookup"><span data-stu-id="bd0af-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="bd0af-123">Om servern avvisar HoloLens-klientcertifikatet kontrollerar du om det nödvändiga klientcertifikatet har etablerats på enheten.</span><span class="sxs-lookup"><span data-stu-id="bd0af-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="bd0af-124">Om HoloLens avvisar servercertifikat kontrollerar du om serverns rotcertifikatutfärdare har etablerats på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd0af-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="bd0af-125">Om företagsprofilen etableras via Wi-Fi kan du använda etableringspaketet på en Windows 10 dator.</span><span class="sxs-lookup"><span data-stu-id="bd0af-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="bd0af-126">Om det även misslyckas på en Windows 10 dator följer du felsökningsguiden för Windows-klient 802.1X-autentisering.</span><span class="sxs-lookup"><span data-stu-id="bd0af-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="bd0af-127">Skicka feedback via Feedbackhubben.</span><span class="sxs-lookup"><span data-stu-id="bd0af-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="bd0af-128">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="bd0af-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="bd0af-129">Wi-Fi felsökning</span><span class="sxs-lookup"><span data-stu-id="bd0af-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="bd0af-130">Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:</span><span class="sxs-lookup"><span data-stu-id="bd0af-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="bd0af-131">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="bd0af-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="bd0af-132">Du kan kontrollera det genom att använda gesten Start och sedan välja Inställningar > Nätverk & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="bd0af-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="bd0af-133">Om Wi-Fi är på kan du prova att stänga av det och sedan på igen.</span><span class="sxs-lookup"><span data-stu-id="bd0af-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="bd0af-134">Flytta datorn närmare routern eller åtkomstpunkten.</span><span class="sxs-lookup"><span data-stu-id="bd0af-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="bd0af-135">Starta om Wi-Fi router och starta sedan om HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd0af-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="bd0af-136">Försök att ansluta igen.</span><span class="sxs-lookup"><span data-stu-id="bd0af-136">Try connecting again.</span></span>
4. <span data-ttu-id="bd0af-137">Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran.</span><span class="sxs-lookup"><span data-stu-id="bd0af-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="bd0af-138">Du hittar den här informationen på tillverkarens webbplats.</span><span class="sxs-lookup"><span data-stu-id="bd0af-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="bd0af-139">När du loggar in på ett företags- eller organisationskonto på enheten kan den även använda MDM-principen (Mobile Enhetshantering), om principen har konfigurerats av IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="bd0af-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="bd0af-140">Felsökning av nätverk</span><span class="sxs-lookup"><span data-stu-id="bd0af-140">Network Troubleshooting</span></span>
<span data-ttu-id="bd0af-141">Om nätverksproblem är ett hinder för att distribuera och använda HoloLens 2 i din organisation kan du lära dig hur två välkända diagnostiska verktyg för nätverk, Fiddler och Wireshark, kan hjälpa dig att genomsöka, diagnostisera och identifiera problem.</span><span class="sxs-lookup"><span data-stu-id="bd0af-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="bd0af-142">Mer information finns [i](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) den här bloggen.</span><span class="sxs-lookup"><span data-stu-id="bd0af-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="bd0af-143">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="bd0af-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="bd0af-144">Det går inte att logga in på en tidigare konfigurerad HoloLens-enhet</span><span class="sxs-lookup"><span data-stu-id="bd0af-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="bd0af-145">Om enheten tidigare har ställts in för någon annan, antingen för en klient eller för en tidigare anställd och du [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) inte har lösenordet för att låsa upp enheten, kan du använda Intune för att fjärrensa enheten.</span><span class="sxs-lookup"><span data-stu-id="bd0af-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="bd0af-146">Enheten blinkar sedan igen.</span><span class="sxs-lookup"><span data-stu-id="bd0af-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="bd0af-147">När du rensar enheten ska du lämna **Behåll registreringstillstånd och användarkonto** avmarkerat.</span><span class="sxs-lookup"><span data-stu-id="bd0af-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="bd0af-148">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="bd0af-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="bd0af-149">Det går inte att logga in efter uppdatering till Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="bd0af-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="bd0af-150">Symtom</span><span class="sxs-lookup"><span data-stu-id="bd0af-150">Symptoms</span></span>
- <span data-ttu-id="bd0af-151">Det går inte att använda PIN-kod för inloggning när rätt PIN-kod har angetts.</span><span class="sxs-lookup"><span data-stu-id="bd0af-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="bd0af-152">Användning av metoden för webbinloggning misslyckas när du har loggat in på webbsidan.</span><span class="sxs-lookup"><span data-stu-id="bd0af-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="bd0af-153">Enheten visas inte som "Azure AD-ansluten" [i Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Enheter.</span><span class="sxs-lookup"><span data-stu-id="bd0af-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="bd0af-154">Orsak</span><span class="sxs-lookup"><span data-stu-id="bd0af-154">Cause</span></span>
<span data-ttu-id="bd0af-155">Den påverkade enheten kan ha tagits bort från Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="bd0af-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="bd0af-156">Detta kan till exempel inträffa eftersom:</span><span class="sxs-lookup"><span data-stu-id="bd0af-156">For example, this may happen because:</span></span>

- <span data-ttu-id="bd0af-157">En administratör eller användare har tagit bort enheten i Azure Portal med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0af-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="bd0af-158">Enheten har tagits bort från Azure AD-klientorganisationen på grund av inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="bd0af-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="bd0af-159">För en effektivt hanterad miljö rekommenderar vi vanligtvis ATT IT-administratörer tar bort [inaktuella, inaktiva enheter från sin Azure AD-klientorganisation.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="bd0af-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="bd0af-160">När en enhet som påverkas försöker kontakta Azure AD-klienten igen efter att den har tagits bort kan den inte autentiseras med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bd0af-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="bd0af-161">Den här effekten är ofta osynlig för användaren av enheten, eftersom cachelagrad inloggning via PIN-kod fortsätter att tillåta användaren att logga in.</span><span class="sxs-lookup"><span data-stu-id="bd0af-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="bd0af-162">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="bd0af-162">Mitigation</span></span>
<span data-ttu-id="bd0af-163">Det finns för närvarande inget sätt att lägga till en borttagna HoloLens-enhet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bd0af-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="bd0af-164">Berörda enheter måste vara rensade omstreckade genom att följa anvisningarna för [att omsnedstrecka enheten](hololens-recovery.md#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="bd0af-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="bd0af-165">Autopilot-felsökning</span><span class="sxs-lookup"><span data-stu-id="bd0af-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="bd0af-166">Följande artiklar kan vara en användbar resurs om du vill veta mer och felsöka Autopilot-problem, men tänk på att de här artiklarna baseras på Windows 10 Desktop och all information kan inte gälla HoloLens:</span><span class="sxs-lookup"><span data-stu-id="bd0af-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="bd0af-167">Windows Autopilot – kända problem</span><span class="sxs-lookup"><span data-stu-id="bd0af-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="bd0af-168">Felsöka problem med registrering av Windows-enheter i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bd0af-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="bd0af-169">Windows Autopilot – Principkonflikter</span><span class="sxs-lookup"><span data-stu-id="bd0af-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="bd0af-170">Vanliga frågor och svar om Hanterade HoloLens-enheter</span><span class="sxs-lookup"><span data-stu-id="bd0af-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="bd0af-171">Kan jag använda System Center Konfigurationshanteraren (SCCM) för att hantera HoloLens-enheter?</span><span class="sxs-lookup"><span data-stu-id="bd0af-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="bd0af-172">Nej.</span><span class="sxs-lookup"><span data-stu-id="bd0af-172">No.</span></span> <span data-ttu-id="bd0af-173">Du måste använda ett MDM-system för att hantera HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="bd0af-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="bd0af-174">Kan jag använda Active Directory Domain Services (AD DS) för att hantera HoloLens-användarkonton?</span><span class="sxs-lookup"><span data-stu-id="bd0af-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="bd0af-175">Nej.</span><span class="sxs-lookup"><span data-stu-id="bd0af-175">No.</span></span> <span data-ttu-id="bd0af-176">Du måste använda Azure Active Directory (Azure AD) för att hantera användarkonton för HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="bd0af-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="bd0af-177">Kan HoloLens automatisk registrering av DATA Capture Systems (ADCS)?</span><span class="sxs-lookup"><span data-stu-id="bd0af-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="bd0af-178">Nej.</span><span class="sxs-lookup"><span data-stu-id="bd0af-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="bd0af-179">Kan HoloLens delta i Integrerad Windows-autentisering?</span><span class="sxs-lookup"><span data-stu-id="bd0af-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="bd0af-180">Nej.</span><span class="sxs-lookup"><span data-stu-id="bd0af-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="bd0af-181">Stöder HoloLens varumärkesyttning?</span><span class="sxs-lookup"><span data-stu-id="bd0af-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="bd0af-182">Nej.</span><span class="sxs-lookup"><span data-stu-id="bd0af-182">No.</span></span> <span data-ttu-id="bd0af-183">Du kan dock komma runt det här problemet med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="bd0af-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="bd0af-184">Skapa en anpassad app och aktivera [sedan Helskärmsläge](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="bd0af-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="bd0af-185">Den anpassade appen kan ha varumärkesanpassad anpassning och kan starta andra appar (till exempel Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="bd0af-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="bd0af-186">Ändra alla användarprofilbilder i Azure AD till företagets logotyp.</span><span class="sxs-lookup"><span data-stu-id="bd0af-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="bd0af-187">Detta kanske dock inte är önskvärt för alla scenarier.</span><span class="sxs-lookup"><span data-stu-id="bd0af-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="bd0af-188">Vilka loggningsfunktioner erbjuder HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="bd0af-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="bd0af-189">Loggning är begränsad till spårningar som kan avbildas i utvecklings- eller felsökningsscenarier, eller telemetri som enheterna skickar till Microsoft-servrar.</span><span class="sxs-lookup"><span data-stu-id="bd0af-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="bd0af-190">Frågor om att skydda HoloLens-enheter</span><span class="sxs-lookup"><span data-stu-id="bd0af-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="bd0af-191">Se [vår HoloLens 2-säkerhetsinformation.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bd0af-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="bd0af-192">För HoloLens 1st Gen-enheter kan du läsa dessa [vanliga frågor och svar.](hololens1-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="bd0af-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="bd0af-193">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="bd0af-193">Back to list</span></span>](#list)
