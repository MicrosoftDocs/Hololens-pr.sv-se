---
title: HoloLens 2-implementering och felsökning av hanterade enheter
description: Felsöka HoloLens 2 enheter i en företagsmiljö
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636885"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="20d70-104">Felsöka implementering och hanterade enheter</span><span class="sxs-lookup"><span data-stu-id="20d70-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="20d70-105">Den här artikeln beskriver hur du löser flera problem eller besvarar frågor om implementering och hantering av HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="20d70-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="20d70-106">Innan du startar en felsökningsprocedur kontrollerar du att enheten debiteras **till 20 till 40 procent** av batterikapaciteten om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="20d70-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="20d70-107">Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="20d70-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="20d70-108">EAP-felsökning</span><span class="sxs-lookup"><span data-stu-id="20d70-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="20d70-109">Felsökning av Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="20d70-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="20d70-110">Felsökning av nätverk</span><span class="sxs-lookup"><span data-stu-id="20d70-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="20d70-111">Det går inte att logga in på en tidigare HoloLens enhet</span><span class="sxs-lookup"><span data-stu-id="20d70-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="20d70-112">Det går inte att logga in efter uppdatering till Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="20d70-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="20d70-113">Autopilot-felsökning</span><span class="sxs-lookup"><span data-stu-id="20d70-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="20d70-114">Vanliga frågor och svar HoloLens hanterade HoloLens enheter</span><span class="sxs-lookup"><span data-stu-id="20d70-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="20d70-115">EAP-felsökning</span><span class="sxs-lookup"><span data-stu-id="20d70-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="20d70-116">Dubbelkolla Wi-Fi profilen har rätt inställningar:</span><span class="sxs-lookup"><span data-stu-id="20d70-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="20d70-117">EAP-typen är korrekt konfigurerad, vanliga EAP-typer: EAP-TLS (13), EAP-TTLS (21) och PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="20d70-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="20d70-118">Wi-Fi SSID-namnet är rätt och matchar med HEX-strängen.</span><span class="sxs-lookup"><span data-stu-id="20d70-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="20d70-119">För EAP-TLS innehåller TrustedRootCA SHA-1-hashen för serverns betrodda rotcertifikatutfärdarcertifikat.</span><span class="sxs-lookup"><span data-stu-id="20d70-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="20d70-120">På Windows pc-kommandot "certutil.exe -dump cert_file_name" visar certifikatets SHA-1-hashsträng.</span><span class="sxs-lookup"><span data-stu-id="20d70-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="20d70-121">Samla in infångade nätverkspaket på åtkomstpunkten, kontrollanten eller AAA-serverloggarna för att ta reda på var EAP-sessionen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="20d70-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="20d70-122">Om EAP-identiteten som tillhandahålls av HoloLens inte förväntas kontrollerar du om identiteten har etablerats korrekt via Wi-Fi profilen eller klientcertifikatet.</span><span class="sxs-lookup"><span data-stu-id="20d70-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="20d70-123">Om servern avvisar HoloLens klientcertifikat kontrollerar du om det nödvändiga klientcertifikatet har etablerats på enheten.</span><span class="sxs-lookup"><span data-stu-id="20d70-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="20d70-124">Om HoloLens avvisar servercertifikatet kontrollerar du om serverns rotcertifikatutfärdare har etablerats på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="20d70-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="20d70-125">Om företagsprofilen etableras via ett Wi-Fi kan du använda etableringspaketet på en Windows 10 dator.</span><span class="sxs-lookup"><span data-stu-id="20d70-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="20d70-126">Om det även misslyckas på Windows 10 dator följer du felsökningsguiden för Windows 802.1X-klientautentisering.</span><span class="sxs-lookup"><span data-stu-id="20d70-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="20d70-127">Skicka feedback via Feedbackhubben.</span><span class="sxs-lookup"><span data-stu-id="20d70-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="20d70-128">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="20d70-129">Wi-Fi felsökning</span><span class="sxs-lookup"><span data-stu-id="20d70-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="20d70-130">Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:</span><span class="sxs-lookup"><span data-stu-id="20d70-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="20d70-131">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="20d70-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="20d70-132">Kontrollera genom att använda gesten Start och välj sedan Inställningar > Nätverk & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="20d70-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="20d70-133">Om Wi-Fi är på kan du prova att stänga av den och sedan aktivera igen.</span><span class="sxs-lookup"><span data-stu-id="20d70-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="20d70-134">Flytta datorn närmare routern eller åtkomstpunkten.</span><span class="sxs-lookup"><span data-stu-id="20d70-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="20d70-135">Starta om Wi-Fi router och starta sedan om HoloLens.</span><span class="sxs-lookup"><span data-stu-id="20d70-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="20d70-136">Försök att ansluta igen.</span><span class="sxs-lookup"><span data-stu-id="20d70-136">Try connecting again.</span></span>
4. <span data-ttu-id="20d70-137">Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran.</span><span class="sxs-lookup"><span data-stu-id="20d70-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="20d70-138">Du hittar den här informationen på tillverkarens webbplats.</span><span class="sxs-lookup"><span data-stu-id="20d70-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="20d70-139">När du loggar in på ett företags- eller organisationskonto på enheten kan den även tillämpa mdm-principen (Mobile Enhetshantering), om principen har konfigurerats av IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="20d70-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="20d70-140">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="20d70-141">Felsökning av nätverk</span><span class="sxs-lookup"><span data-stu-id="20d70-141">Network Troubleshooting</span></span>
<span data-ttu-id="20d70-142">Om nätverksproblem är ett hinder för att distribuera och använda HoloLens 2 i din organisation konfigurerar du Fiddler och/eller Wireshark för att samla in och analysera HTTP/HTTPS-trafik.</span><span class="sxs-lookup"><span data-stu-id="20d70-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="20d70-143">Konfigurera Fiddler för att samla in HTTP-trafik</span><span class="sxs-lookup"><span data-stu-id="20d70-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="20d70-144">Fiddler är en webbfelsökningsproxy och används för att felsöka HTTP(S)-problem.</span><span class="sxs-lookup"><span data-stu-id="20d70-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="20d70-145">Den registrerar varje HTTP-begäran som datorn gör och registrerar allt som är associerat med den.</span><span class="sxs-lookup"><span data-stu-id="20d70-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="20d70-146">Genom att upptäcka problem med slutanvändarautentisering för DINA HTTPS-appar får du bättre produktivitet och effektivitet för HoloLens två användningsfall.</span><span class="sxs-lookup"><span data-stu-id="20d70-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="20d70-147">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="20d70-147">Prerequisites</span></span>
 
- <span data-ttu-id="20d70-148">HoloLens 2 enheter och datorn måste finnas i samma nätverk</span><span class="sxs-lookup"><span data-stu-id="20d70-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="20d70-149">Anteckna IP-adressen för din dator</span><span class="sxs-lookup"><span data-stu-id="20d70-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="20d70-150">Installera och konfigurera Fiddler</span><span class="sxs-lookup"><span data-stu-id="20d70-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="20d70-151">På datorn – [installera och](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) starta Fiddler.</span><span class="sxs-lookup"><span data-stu-id="20d70-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="20d70-152">På datorn – konfigurera Fiddler så att fjärrdatorer kan ansluta.</span><span class="sxs-lookup"><span data-stu-id="20d70-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="20d70-153">Gå till Fiddler Inställningar -> Anslutningar</span><span class="sxs-lookup"><span data-stu-id="20d70-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="20d70-154">Observera lyssningsporten för Fiddler (standard är 8866)</span><span class="sxs-lookup"><span data-stu-id="20d70-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="20d70-155">Markera Tillåt att fjärrdatorer ansluter</span><span class="sxs-lookup"><span data-stu-id="20d70-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="20d70-156">Klicka på Spara</span><span class="sxs-lookup"><span data-stu-id="20d70-156">Click Save</span></span>
3. <span data-ttu-id="20d70-157">På din HoloLens 2 – konfigurera Fiddler som proxyserver<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="20d70-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="20d70-158">Öppna Start-menyn och välj Inställningar</span><span class="sxs-lookup"><span data-stu-id="20d70-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="20d70-159">Välj Network & Internet (Nätverk och sedan Proxy) på den vänstra menyn</span><span class="sxs-lookup"><span data-stu-id="20d70-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="20d70-160">Rulla ned till Manuell proxykonfiguration och växla Använd en proxyserver till På</span><span class="sxs-lookup"><span data-stu-id="20d70-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="20d70-161">Ange IP-adressen för den dator där Fiddler är installerat</span><span class="sxs-lookup"><span data-stu-id="20d70-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="20d70-162">Ange det portnummer som anges ovan (standard är 8866)</span><span class="sxs-lookup"><span data-stu-id="20d70-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="20d70-163">Klicka på Spara</span><span class="sxs-lookup"><span data-stu-id="20d70-163">Click Save</span></span>

<span data-ttu-id="20d70-164"><sup>1</sup> För versioner 20279.1006+ (Insiders och den kommande versionen) använder du följande steg för att konfigurera proxy:</span><span class="sxs-lookup"><span data-stu-id="20d70-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="20d70-165">Öppna Start-menyn och gå Wi-Fi sidan Egenskaper för ditt nätverk</span><span class="sxs-lookup"><span data-stu-id="20d70-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="20d70-166">Rulla ned till Proxy</span><span class="sxs-lookup"><span data-stu-id="20d70-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="20d70-167">Ändra till manuell installation</span><span class="sxs-lookup"><span data-stu-id="20d70-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="20d70-168">Ange IP-adressen för den dator där Fiddler är installerat</span><span class="sxs-lookup"><span data-stu-id="20d70-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="20d70-169">Ange det portnummer som anges ovan.</span><span class="sxs-lookup"><span data-stu-id="20d70-169">Enter the port number noted above.</span></span> <span data-ttu-id="20d70-170">(standardvärdet är 8866)</span><span class="sxs-lookup"><span data-stu-id="20d70-170">(default is 8866)</span></span>
1. <span data-ttu-id="20d70-171">Klicka på Använd</span><span class="sxs-lookup"><span data-stu-id="20d70-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="20d70-172">Dekryptera HTTPS-trafik från HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="20d70-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="20d70-173">På datorn – exportera Fiddler-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="20d70-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="20d70-174">Gå till Fiddler Inställningar -> HTTPS och expandera Avancerat Inställningar</span><span class="sxs-lookup"><span data-stu-id="20d70-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="20d70-175">Klicka på Exportera Fiddler-certifikat.</span><span class="sxs-lookup"><span data-stu-id="20d70-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="20d70-176">Den sparas på skrivbordet</span><span class="sxs-lookup"><span data-stu-id="20d70-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="20d70-177">Flytta certifikatet till mappen Hämtade filer på din HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="20d70-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="20d70-178">På din HoloLens 2 – importera Fiddler-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="20d70-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="20d70-179">Gå till Inställningar -> Update and Security -> Certificates</span><span class="sxs-lookup"><span data-stu-id="20d70-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="20d70-180">Klicka på Installera certifikat, bläddra till mappen Hämtade filer och välj Fiddler-certifikatet</span><span class="sxs-lookup"><span data-stu-id="20d70-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="20d70-181">Ändra lagringsplats till lokal dator</span><span class="sxs-lookup"><span data-stu-id="20d70-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="20d70-182">Ändra certifikatarkiv till rot</span><span class="sxs-lookup"><span data-stu-id="20d70-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="20d70-183">Välj Installera</span><span class="sxs-lookup"><span data-stu-id="20d70-183">Select Install</span></span>
    6. <span data-ttu-id="20d70-184">Bekräfta att certifikatet visas i listan över certifikat.</span><span class="sxs-lookup"><span data-stu-id="20d70-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="20d70-185">Om inte upprepar du ovanstående steg</span><span class="sxs-lookup"><span data-stu-id="20d70-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="20d70-186">Granska HTTP(S)-sessioner</span><span class="sxs-lookup"><span data-stu-id="20d70-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="20d70-187">På din dator visar Fiddler HoloLens 2:s live-HTTP(S)-sessioner.</span><span class="sxs-lookup"><span data-stu-id="20d70-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="20d70-188">Kontrollpanelen i Fiddler kan visa HTTP(S)-begäran/-svar i olika vyer – till exempel visar vyn "Raw" rå begäran eller svar i oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="20d70-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="20d70-189">Konfigurera Wireshark för att samla in nätverkstrafik</span><span class="sxs-lookup"><span data-stu-id="20d70-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="20d70-190">Wireshark är ett analysverktyg för nätverksprotokoll och används för att inspektera TCP/UDP-trafik från och till dina HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="20d70-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="20d70-191">Detta gör det enkelt att identifiera vilken trafik som passerar ditt nätverk till din HoloLens 2, hur mycket av den, hur ofta, hur lång svarstid det är mellan vissa hopp och så vidare.</span><span class="sxs-lookup"><span data-stu-id="20d70-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="20d70-192">Krav:</span><span class="sxs-lookup"><span data-stu-id="20d70-192">Prerequisites:</span></span>
- <span data-ttu-id="20d70-193">Datorn måste ha Internetåtkomst och stöd för Internetdelning via Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="20d70-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="20d70-194">Installera och konfigurera Wireshark</span><span class="sxs-lookup"><span data-stu-id="20d70-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="20d70-195">På datorn – installera [Wireshark](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="20d70-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="20d70-196">På datorn – aktivera Mobil hotspot för att dela din Internetanslutning från Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="20d70-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="20d70-197">Starta Wireshark på datorn och samla in trafik från gränssnittet för mobil hotspot.</span><span class="sxs-lookup"><span data-stu-id="20d70-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="20d70-198">På din HoloLens 2 – ändra dess Wi-Fi till datorns mobila hotspot.</span><span class="sxs-lookup"><span data-stu-id="20d70-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="20d70-199">HoloLens 2 IP-trafik visas i Wireshark.</span><span class="sxs-lookup"><span data-stu-id="20d70-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="20d70-200">Analysera Wireshark-loggar</span><span class="sxs-lookup"><span data-stu-id="20d70-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="20d70-201">Wireshark-filter kan hjälpa till att filtrera bort intressepaket.</span><span class="sxs-lookup"><span data-stu-id="20d70-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="20d70-202">Kolla in den ursprungliga [bloggen](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span><span class="sxs-lookup"><span data-stu-id="20d70-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="20d70-203">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="20d70-204">Det går inte att logga in på en tidigare HoloLens enhet</span><span class="sxs-lookup"><span data-stu-id="20d70-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="20d70-205">Om enheten tidigare har ställts in för någon annan, antingen för en klient eller för en tidigare anställd och du [](/intune/remote-actions/devices-wipe) inte har lösenordet för att låsa upp enheten, kan du använda Intune för att fjärrensa enheten.</span><span class="sxs-lookup"><span data-stu-id="20d70-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="20d70-206">Enheten tar sedan på sig själv igen.</span><span class="sxs-lookup"><span data-stu-id="20d70-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="20d70-207">När du rensar enheten ska du lämna **Behåll registreringstillstånd och användarkonto** avmarkerat.</span><span class="sxs-lookup"><span data-stu-id="20d70-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="20d70-208">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="20d70-209">Det går inte att logga in efter uppdatering till Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="20d70-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="20d70-210">Symtom</span><span class="sxs-lookup"><span data-stu-id="20d70-210">Symptoms</span></span>
- <span data-ttu-id="20d70-211">Det går inte att använda PIN-kod för inloggning när rätt PIN-kod har angetts.</span><span class="sxs-lookup"><span data-stu-id="20d70-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="20d70-212">Användning av metoden för webbinloggning misslyckas när du har loggat in på webbsidan.</span><span class="sxs-lookup"><span data-stu-id="20d70-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="20d70-213">Enheten visas inte som "Azure AD-ansluten" [i Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span><span class="sxs-lookup"><span data-stu-id="20d70-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="20d70-214">Orsak</span><span class="sxs-lookup"><span data-stu-id="20d70-214">Cause</span></span>
<span data-ttu-id="20d70-215">Den påverkade enheten kan ha tagits bort från Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="20d70-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="20d70-216">Detta kan till exempel inträffa eftersom:</span><span class="sxs-lookup"><span data-stu-id="20d70-216">For example, this may happen because:</span></span>

- <span data-ttu-id="20d70-217">En administratör eller användare har tagit bort enheten i Azure Portal eller med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20d70-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="20d70-218">Enheten har tagits bort från Azure AD-klientorganisationen på grund av inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="20d70-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="20d70-219">För en effektivt hanterad miljö rekommenderar vi vanligtvis att IT-administratörer tar bort [inaktuella, inaktiva enheter från sin Azure AD-klientorganisation.](/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="20d70-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="20d70-220">När en enhet som påverkas försöker kontakta Azure AD-klienten igen efter att den har tagits bort, kommer den inte att autentiseras med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="20d70-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="20d70-221">Den här effekten är ofta osynlig för användaren av enheten, eftersom cachelagrad inloggning via PIN-kod fortsätter att tillåta användaren att logga in.</span><span class="sxs-lookup"><span data-stu-id="20d70-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="20d70-222">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="20d70-222">Mitigation</span></span>
<span data-ttu-id="20d70-223">Det finns för närvarande inget sätt att lägga till en HoloLens en enhet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="20d70-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="20d70-224">Berörda enheter måste vara rensade omstreckade genom att följa anvisningarna för [att omstrecka enheten](hololens-recovery.md#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="20d70-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="20d70-225">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="20d70-226">Autopilot-felsökning</span><span class="sxs-lookup"><span data-stu-id="20d70-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="20d70-227">Följande artiklar kan vara en användbar resurs om du vill veta mer och felsöka Autopilot-problem, men tänk på att de här artiklarna baseras på Windows 10 Desktop och att inte all information kan gälla för HoloLens:</span><span class="sxs-lookup"><span data-stu-id="20d70-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="20d70-228">Windows Autopilot – kända problem</span><span class="sxs-lookup"><span data-stu-id="20d70-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="20d70-229">Felsöka problem med registrering av Windows-enheter i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="20d70-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="20d70-230">Windows Autopilot – principkonflikter</span><span class="sxs-lookup"><span data-stu-id="20d70-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="20d70-231">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="20d70-232">Vanliga frågor och svar HoloLens hanterade HoloLens enheter</span><span class="sxs-lookup"><span data-stu-id="20d70-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="20d70-233">Kan jag använda System Center Configuration Manager (SCCM) för att hantera HoloLens enheter?</span><span class="sxs-lookup"><span data-stu-id="20d70-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="20d70-234">Nej.</span><span class="sxs-lookup"><span data-stu-id="20d70-234">No.</span></span> <span data-ttu-id="20d70-235">Du måste använda ett MDM-system för att hantera HoloLens enheter.</span><span class="sxs-lookup"><span data-stu-id="20d70-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="20d70-236">Kan jag använda Active Directory Domain Services (AD DS) för HoloLens hantera användarkonton?</span><span class="sxs-lookup"><span data-stu-id="20d70-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="20d70-237">Nej.</span><span class="sxs-lookup"><span data-stu-id="20d70-237">No.</span></span> <span data-ttu-id="20d70-238">Du måste använda Azure Active Directory (Azure AD) för att hantera användarkonton för HoloLens enheter.</span><span class="sxs-lookup"><span data-stu-id="20d70-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="20d70-239">Kan HoloLens automatisk registrering i ADCS (Automated Data Capture Systems)?</span><span class="sxs-lookup"><span data-stu-id="20d70-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="20d70-240">Nej.</span><span class="sxs-lookup"><span data-stu-id="20d70-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="20d70-241">Kan HoloLens delta i integrerad Windows autentisering?</span><span class="sxs-lookup"><span data-stu-id="20d70-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="20d70-242">Nej.</span><span class="sxs-lookup"><span data-stu-id="20d70-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="20d70-243">Stöder HoloLens profilering?</span><span class="sxs-lookup"><span data-stu-id="20d70-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="20d70-244">Nej.</span><span class="sxs-lookup"><span data-stu-id="20d70-244">No.</span></span> <span data-ttu-id="20d70-245">Du kan dock komma runt det här problemet med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="20d70-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="20d70-246">Skapa en anpassad app och aktivera [sedan Helskärmsläge](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="20d70-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="20d70-247">Den anpassade appen kan ha varumärkesanpassad anpassning och kan starta andra appar (till exempel Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="20d70-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="20d70-248">Ändra alla användarprofilbilder i Azure AD till företagets logotyp.</span><span class="sxs-lookup"><span data-stu-id="20d70-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="20d70-249">Detta kanske dock inte är önskvärt för alla scenarier.</span><span class="sxs-lookup"><span data-stu-id="20d70-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="20d70-250">Vilka loggningsfunktioner erbjuder HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="20d70-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="20d70-251">Loggning är begränsad till spårningar som kan avbildas i utvecklings- eller felsökningsscenarier, eller telemetri som enheterna skickar till Microsoft-servrar.</span><span class="sxs-lookup"><span data-stu-id="20d70-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="20d70-252">Frågor om att skydda HoloLens enheter</span><span class="sxs-lookup"><span data-stu-id="20d70-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="20d70-253">Se [vår HoloLens 2 säkerhetsinformation](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="20d70-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="20d70-254">För HoloLens första generationens enheter kan du läsa dessa [vanliga frågor och svar.](hololens1-faq-security.yml)</span><span class="sxs-lookup"><span data-stu-id="20d70-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="20d70-255">Tillbaka till listan</span><span class="sxs-lookup"><span data-stu-id="20d70-255">Back to list</span></span>](#list)
