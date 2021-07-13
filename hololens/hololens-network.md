---
title: Anslut HoloLens till ett nätverk
description: Lär dig att konfigurera och ansluta till Internet med HoloLens och hur du identifierar enhetens IP-adress.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, trådlöst, Internet, IP, IP-adress
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640227"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="1a195-104">Anslut HoloLens till ett nätverk</span><span class="sxs-lookup"><span data-stu-id="1a195-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="1a195-105">För att kunna göra det HoloLens måste du vara ansluten till ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="1a195-106">HoloLens innehåller en 802.11ac-kompatibel 2x2 Wi-Fi-radio och att ansluta den till ett nätverk liknar att ansluta en Windows 10 Desktop- eller Mobile-enhet till ett Wi-Fi-nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="1a195-107">Den här guiden hjälper dig att:</span><span class="sxs-lookup"><span data-stu-id="1a195-107">This guide will help you:</span></span>

- <span data-ttu-id="1a195-108">Anslut till ett nätverk med hjälp av Wi-Fi, eller endast för HoloLens 2, Wi-Fi Direct eller Ethernet via USB-C</span><span class="sxs-lookup"><span data-stu-id="1a195-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="1a195-109">Inaktivera och återaktivera Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1a195-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="1a195-110">Läs mer om [att använda HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="1a195-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="1a195-111">Ansluta för första gången</span><span class="sxs-lookup"><span data-stu-id="1a195-111">Connecting for the first time</span></span>

<span data-ttu-id="1a195-112">Första gången du använder HoloLens vägleds du genom anslutning till ett Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="1a195-113">Om du har problem med att ansluta till Wi-Fi under installationen kontrollerar du att nätverket antingen är ett öppet lösenordsskyddat nätverk eller ett internt portalnätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="1a195-114">Kontrollera också att nätverket inte kräver att du använder ett certifikat för att ansluta.</span><span class="sxs-lookup"><span data-stu-id="1a195-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="1a195-115">Efter installationen kan du ansluta till andra typer av Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="1a195-116">På HoloLens 2 enheter kan en användare också använda en [USB-C till Ethernet-adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) för att ansluta direkt till Wi-Fi för att hjälpa till med att konfigurera enheten.</span><span class="sxs-lookup"><span data-stu-id="1a195-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="1a195-117">När enheten har ställts in kan en användare fortsätta att använda adaptern eller så kan de koppla bort enheten från adaptern och ansluta till [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)efter att ha ställt in .</span><span class="sxs-lookup"><span data-stu-id="1a195-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="1a195-118">Ansluta till Wi-Fi efter installationen</span><span class="sxs-lookup"><span data-stu-id="1a195-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="1a195-119">Förforma **gesten Start** och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="1a195-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="1a195-120">Appen Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="1a195-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="1a195-121">Välj **Network & Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="1a195-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="1a195-122">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="1a195-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="1a195-123">Om du inte ser nätverket rullar du nedåt i listan.</span><span class="sxs-lookup"><span data-stu-id="1a195-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="1a195-124">Välj ett nätverk och välj **sedan Anslut**.</span><span class="sxs-lookup"><span data-stu-id="1a195-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="1a195-125">Om du uppmanas att ange ett nätverkslösenord skriver du det och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="1a195-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi inställningar](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="1a195-127">Kontrollera att du är ansluten till Wi-Fi nätverk genom att kontrollera Wi-Fi status på **Start-menyn:**</span><span class="sxs-lookup"><span data-stu-id="1a195-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="1a195-128">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="1a195-129">Titta längst upp till vänster på **Start-menyn** för Wi-Fi status.</span><span class="sxs-lookup"><span data-stu-id="1a195-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="1a195-130">Tillståndet för Wi-Fi och SSID för det anslutna nätverket visas.</span><span class="sxs-lookup"><span data-stu-id="1a195-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="1a195-131">Om Wi-Fi inte är tillgänglig kan du också [ansluta till mobilnät och 5G-nätverk.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="1a195-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a195-132">Användare kan inte finjustera nätverksväxlingsbeteendet för Wi-Fi för HoloLens 2 – det enda sättet att uppdatera Wi-Fi-listan är att växla **Wi-Fi av** och på .</span><span class="sxs-lookup"><span data-stu-id="1a195-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="1a195-133">Detta förhindrar många problem, t.ex. när en enhet kan "fastna" i en AP när den är utanför intervallet.</span><span class="sxs-lookup"><span data-stu-id="1a195-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="1a195-134">Anslut HoloLens till Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="1a195-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="1a195-135">Företagsprofiler Wi-Fi använder EAP (Extensible Authentication Protocol) för att autentisera Wi-Fi anslutningar.</span><span class="sxs-lookup"><span data-stu-id="1a195-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="1a195-136">HoloLens Enterprise Wi-Fi-profil kan konfigureras via MDM eller etableringspaket som skapats av [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="1a195-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="1a195-137">Konfigurationsinstruktioner Microsoft Intune en hanterad enhet finns i [Intune.](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)</span><span class="sxs-lookup"><span data-stu-id="1a195-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="1a195-138">Om du vill Wi-Fi ett konfigurationspaket i WCD krävs en förkonfigurerad Wi-Fi en .xml-fil.</span><span class="sxs-lookup"><span data-stu-id="1a195-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="1a195-139">Här är ett exempel Wi-Fi profil för WPA2-Enterprise med EAP-TLS-autentisering:</span><span class="sxs-lookup"><span data-stu-id="1a195-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="1a195-140">Serverns rotcertifikatutfärdarcertifikat och klientcertifikat kan behöva etableras på enheten beroende på EAP-typ.</span><span class="sxs-lookup"><span data-stu-id="1a195-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="1a195-141">Ytterligare resurser:</span><span class="sxs-lookup"><span data-stu-id="1a195-141">Additional resources:</span></span>

- <span data-ttu-id="1a195-142">WLANv1Profile-schema: [[MS-GPWL]: Trådlös LAN-profil v1 schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="1a195-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="1a195-143">EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="1a195-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="1a195-144">Kontrollera vår [felsökningssida](hololens2-enterprise-troubleshooting.md#) om du har problem med att ansluta till ditt Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="1a195-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="1a195-145">Konfigurera nätverksproxy</span><span class="sxs-lookup"><span data-stu-id="1a195-145">Configure Network Proxy</span></span>

<span data-ttu-id="1a195-146">Det här avsnittet beskriver nätverksproxy för HoloLens OS- och UWP-appar (Universal Windows Platform) som använder Windows HTTP-stack.</span><span class="sxs-lookup"><span data-stu-id="1a195-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="1a195-147">Program som använder icke-Windows HTTP-stacken kan ha sin egen proxykonfiguration och -hantering.</span><span class="sxs-lookup"><span data-stu-id="1a195-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="1a195-148">Proxykonfigurationer</span><span class="sxs-lookup"><span data-stu-id="1a195-148">Proxy Configurations</span></span> 

- <span data-ttu-id="1a195-149">PAC-skript (Proxy Auto-Config): En [PAC-fil](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (öppnar en webbplats som inte kommer från Microsoft) innehåller en JavaScript-funktion FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="1a195-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="1a195-150">Statisk proxy: i form av Server:Port.</span><span class="sxs-lookup"><span data-stu-id="1a195-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="1a195-151">Web Proxy Auto-Discovery Protocol (WPAD): Ange URL för proxykonfigurationsfilen via DHCP eller DNS.</span><span class="sxs-lookup"><span data-stu-id="1a195-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="1a195-152">Proxyetableringsmetoder</span><span class="sxs-lookup"><span data-stu-id="1a195-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="1a195-153">Det finns tre sätt att etablera proxys:</span><span class="sxs-lookup"><span data-stu-id="1a195-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="1a195-154">**Inställningar Ui:**</span><span class="sxs-lookup"><span data-stu-id="1a195-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="1a195-155">Proxy per användare (20H2 eller tidigare):</span><span class="sxs-lookup"><span data-stu-id="1a195-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="1a195-156">Öppna Start-menyn och välj Inställningar.</span><span class="sxs-lookup"><span data-stu-id="1a195-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="1a195-157">Välj Nätverk & Internet och sedan Proxy på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="1a195-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="1a195-158">Rulla ned till Manuell proxykonfiguration och växla Använd en proxyserver till På.</span><span class="sxs-lookup"><span data-stu-id="1a195-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="1a195-159">Ange IP-adressen för proxyservern.</span><span class="sxs-lookup"><span data-stu-id="1a195-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="1a195-160">Ange portnumret.</span><span class="sxs-lookup"><span data-stu-id="1a195-160">Enter the port number.</span></span>
        6. <span data-ttu-id="1a195-161">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1a195-161">Click Save.</span></span>
      1. <span data-ttu-id="1a195-162">WiFi-proxy (21H1 eller senare):</span><span class="sxs-lookup"><span data-stu-id="1a195-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="1a195-163">Öppna Start-menyn och gå Wi-Fi sidan Egenskaper för ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="1a195-164">Rulla ned till Proxy</span><span class="sxs-lookup"><span data-stu-id="1a195-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="1a195-165">Ändra till manuell installation</span><span class="sxs-lookup"><span data-stu-id="1a195-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="1a195-166">Ange IP-adressen för proxyservern.</span><span class="sxs-lookup"><span data-stu-id="1a195-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="1a195-167">Ange portnumret.</span><span class="sxs-lookup"><span data-stu-id="1a195-167">Enter the port number.</span></span>
          1. <span data-ttu-id="1a195-168">Klicka på Använd.</span><span class="sxs-lookup"><span data-stu-id="1a195-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="1a195-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="1a195-169">**MDM**</span></span> 
     1. <span data-ttu-id="1a195-170">Intune – Använd de här [stegen för](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) att konfigurera proxy i Intune.</span><span class="sxs-lookup"><span data-stu-id="1a195-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="1a195-171">Du måste rulla längst ned i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1a195-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="1a195-172">Andra MDM-lösningar från tredje part – Använd en [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="1a195-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="1a195-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="1a195-173">**PPKG**</span></span> 
    1. <span data-ttu-id="1a195-174">Öppna Windows Configuration Designer</span><span class="sxs-lookup"><span data-stu-id="1a195-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="1a195-175">Klicka på Avancerad etablering, ange namnet på den nya Project klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="1a195-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="1a195-176">Välj Windows Holographic (HoloLens 2) och klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="1a195-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="1a195-177">Importera PPKG (valfritt) och klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="1a195-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="1a195-178">Expandera Runtime Inställningar -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span><span class="sxs-lookup"><span data-stu-id="1a195-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="1a195-179">Ange SSID för ditt Wi-Fi och klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="1a195-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="1a195-180">Välj ditt Wi-Fi i det vänstra fönstret och ange önskade anpassningar.</span><span class="sxs-lookup"><span data-stu-id="1a195-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="1a195-181">De aktiverade anpassningarna visas i fetstil på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="1a195-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="1a195-182">Klicka på Spara och avsluta.</span><span class="sxs-lookup"><span data-stu-id="1a195-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="1a195-183">[Tillämpa](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) etableringspaketet på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a195-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="1a195-184">[Molntjänstleverantörer](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) ligger bakom många av hanteringsuppgifterna och principerna för Windows 10, både i Microsoft Intune och hos mdm-tjänstleverantörer som inte kommer från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a195-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="1a195-185">Du kan också använda [Windows Configuration Designer för](/windows/configuration/provisioning-packages/provisioning-install-icd) att skapa ett [konfigurationspaket](/windows/configuration/provisioning-packages/provisioning-packages) och tillämpa det på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1a195-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="1a195-186">De mest sannolika CPS som kommer att tillämpas på din HoloLens 2 är:</span><span class="sxs-lookup"><span data-stu-id="1a195-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="1a195-187">[WiFi CSP:](/windows/client-management/mdm/wifi-csp)per profil Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="1a195-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="1a195-188">Andra CPS som stöds i HoloLens enheter</span><span class="sxs-lookup"><span data-stu-id="1a195-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="1a195-189">VPN</span><span class="sxs-lookup"><span data-stu-id="1a195-189">VPN</span></span>
<span data-ttu-id="1a195-190">En VPN-anslutning kan ge en säkrare anslutning och åtkomst till företagets nätverk och Internet.</span><span class="sxs-lookup"><span data-stu-id="1a195-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="1a195-191">HoloLens 2 har stöd för inbyggda VPN-klienter och UWP VPN-plugin-program (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="1a195-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="1a195-192">Inbyggda VPN-protokoll som stöds:</span><span class="sxs-lookup"><span data-stu-id="1a195-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="1a195-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="1a195-193">IKEv2</span></span>
- <span data-ttu-id="1a195-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="1a195-194">L2TP</span></span>
- <span data-ttu-id="1a195-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="1a195-195">PPTP</span></span>

<span data-ttu-id="1a195-196">Om certifikatet används för autentisering för den inbyggda VPN-klienten måste det nödvändiga klientcertifikatet läggas till i användarens certifikatarkiv.</span><span class="sxs-lookup"><span data-stu-id="1a195-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="1a195-197">Om du vill ta reda på om ett VPN-plugin-program från tredje part stöder HoloLens 2 går du till Store för att hitta VPN-appen och kontrollerar om HoloLens visas som en enhet som stöds och på sidan Systemkrav stöder appen ARM- eller ARM64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="1a195-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="1a195-198">HoloLens endast stöd för Universal Windows Platform-program för VPN från tredje part.</span><span class="sxs-lookup"><span data-stu-id="1a195-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="1a195-199">VPN kan hanteras av MDM via [Inställningar/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)och anges via [Vpnv2-csp-principen](/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="1a195-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="1a195-200">Läs mer om [hur du konfigurerar VPN med](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hjälp av dessa [guider.](/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="1a195-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="1a195-201">VPN via användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="1a195-201">VPN via UI</span></span>

<span data-ttu-id="1a195-202">VPN är inte aktiverat som standard men kan aktiveras manuellt genom **att öppna Inställningar** app och navigera till Network & Internet **-> VPN**.</span><span class="sxs-lookup"><span data-stu-id="1a195-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="1a195-203">Välj en VPN-provider.</span><span class="sxs-lookup"><span data-stu-id="1a195-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="1a195-204">Skapa ett anslutningsnamn.</span><span class="sxs-lookup"><span data-stu-id="1a195-204">Create a connection name.</span></span> 
1. <span data-ttu-id="1a195-205">Ange ditt servernamn eller din adress.</span><span class="sxs-lookup"><span data-stu-id="1a195-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="1a195-206">Välj VPN-typ.</span><span class="sxs-lookup"><span data-stu-id="1a195-206">Select the VPN type.</span></span>
1. <span data-ttu-id="1a195-207">Välj typ av inloggningsinformation.</span><span class="sxs-lookup"><span data-stu-id="1a195-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="1a195-208">Du kan också lägga till användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="1a195-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="1a195-209">Tillämpa VPN-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="1a195-209">Apply the VPN settings.</span></span> 

![HoloLens VPN-inställningar](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="1a195-211">VPN-uppsättning via etableringspaket</span><span class="sxs-lookup"><span data-stu-id="1a195-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="1a195-212">I vår Windows Holographic, version 20H2, har vi åtgärdat ett proxykonfigurationsproblem för VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="1a195-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="1a195-213">Överväg att uppgradera enheter till den här versionen om du tänker använda det här flödet.</span><span class="sxs-lookup"><span data-stu-id="1a195-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="1a195-214">Starta Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="1a195-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="1a195-215">Klicka **på HoloLens enheter** och välj sedan målenhet och **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="1a195-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="1a195-216">Ange paketnamn och sökväg.</span><span class="sxs-lookup"><span data-stu-id="1a195-216">Enter package name and path.</span></span>
1. <span data-ttu-id="1a195-217">Klicka **på Växla till avancerad redigerare.**</span><span class="sxs-lookup"><span data-stu-id="1a195-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="1a195-218">Öppna **Körningsinställningar**  ->  **AnslutningarProfiler**  ->  **VPN**  ->  **VPNInställningar**.</span><span class="sxs-lookup"><span data-stu-id="1a195-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="1a195-219">Konfigurera VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="1a195-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="1a195-220">Välj ProfileType: **Intern** eller **Tredje part.**</span><span class="sxs-lookup"><span data-stu-id="1a195-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="1a195-221">För Intern profil väljer du **NativeProtocolType** och konfigurerar sedan server, routningsprincip, autentiseringstyp och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="1a195-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="1a195-222">För profilen "Tredje part" konfigurerar du server-URL, VPN-plugin-programpaketfamiljenamn (endast 3 fördefinierade) och anpassade konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="1a195-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="1a195-223">Exportera paketet.</span><span class="sxs-lookup"><span data-stu-id="1a195-223">Export your package.</span></span>
1. <span data-ttu-id="1a195-224">Anslut din HoloLens och kopiera .ppkg-filen till enheten.</span><span class="sxs-lookup"><span data-stu-id="1a195-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="1a195-225">På HoloLens använder du VPN .ppkg genom att öppna Start-menyn och välja Inställningar-kontoåtkomst för arbete eller skola Lägg till eller ta bort etableringspaket  ->    ->    ->   -> Välj ditt VPN-paket.</span><span class="sxs-lookup"><span data-stu-id="1a195-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="1a195-226">Konfigurera VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="1a195-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="1a195-227">Följ bara Intune-dokumenten för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="1a195-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="1a195-228">När du följer de här stegen bör du tänka på de inbyggda VPN-protokoll som HoloLens enheter stöder.</span><span class="sxs-lookup"><span data-stu-id="1a195-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="1a195-229">[Skapa VPN-profiler för att ansluta till VPN-servrar i Intune](/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="1a195-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="1a195-230">[Windows 10 och Windows Holographic-enhetsinställningar för att lägga till VPN-anslutningar med Intune](/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="1a195-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="1a195-231">Kom ihåg att tilldela [profilen när du är klar.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="1a195-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="1a195-232">VPN via MDM-lösningar från tredje part</span><span class="sxs-lookup"><span data-stu-id="1a195-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="1a195-233">Exempel på VPN-anslutning från tredje part:</span><span class="sxs-lookup"><span data-stu-id="1a195-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="1a195-234">Inbyggt IKEv2 VPN-exempel:</span><span class="sxs-lookup"><span data-stu-id="1a195-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="1a195-235">Inaktivera Wi-Fi på HoloLens (första gen)</span><span class="sxs-lookup"><span data-stu-id="1a195-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="1a195-236">Använda appen Inställningar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="1a195-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="1a195-237">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="1a195-238">Välj **Inställningar** från **Start** eller i **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="1a195-239">Appen **Inställningar** placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="1a195-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="1a195-240">Välj **Nätverk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="1a195-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="1a195-241">Välj skjutreglaget Wi-Fi för att flytta den till **läget Av.**</span><span class="sxs-lookup"><span data-stu-id="1a195-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="1a195-242">Detta inaktiverar RF-komponenterna i Wi-Fi radio och inaktiverar alla Wi-Fi på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a195-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="1a195-243">När Wi-Fi är inaktiverad kan HoloLens automatiskt läsa in dina [blanksteg.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="1a195-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="1a195-244">Flytta skjutreglaget till **läget På** för att aktivera Wi-Fi och återställa Wi-Fi på Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a195-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="1a195-245">Det valda Wi-Fi **(på eller** **av)** bevaras vid omstarter.</span><span class="sxs-lookup"><span data-stu-id="1a195-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="1a195-246">Identifiera IP-adressen för HoloLens i Wi-Fi nätverk</span><span class="sxs-lookup"><span data-stu-id="1a195-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="1a195-247">Med hjälp av Inställningar appen</span><span class="sxs-lookup"><span data-stu-id="1a195-247">By using the Settings app</span></span>

1. <span data-ttu-id="1a195-248">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="1a195-249">Välj **Inställningar** från **Start** eller i **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="1a195-250">Appen **Inställningar** placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="1a195-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="1a195-251">Välj **Nätverk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="1a195-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="1a195-252">Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="1a195-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Maskinvaruegenskaper i Wi-Fi inställningar](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="1a195-254">IP-adressen visas bredvid **IPv4-adressen**.</span><span class="sxs-lookup"><span data-stu-id="1a195-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="1a195-255">Med hjälp av röstkommandon</span><span class="sxs-lookup"><span data-stu-id="1a195-255">By using voice commands</span></span>

<span data-ttu-id="1a195-256">Beroende på dina enheter kan du antingen använda inbyggda röstkommandon eller Cortana för att visa din IP-adress.</span><span class="sxs-lookup"><span data-stu-id="1a195-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="1a195-257">På byggen efter [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) talar vi "What's my IP address?" (Vad är min IP-adress?</span><span class="sxs-lookup"><span data-stu-id="1a195-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="1a195-258">och den visas.</span><span class="sxs-lookup"><span data-stu-id="1a195-258">and it will be displayed.</span></span> <span data-ttu-id="1a195-259">För tidigare versioner eller HoloLens (första generationen) säger du "Hej Cortana, Vad är min IP-adress?"</span><span class="sxs-lookup"><span data-stu-id="1a195-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="1a195-260">och Cortana att visa och läsa upp din IP-adress.</span><span class="sxs-lookup"><span data-stu-id="1a195-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="1a195-261">Med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="1a195-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="1a195-262">Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="1a195-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="1a195-263">Gå till **avsnittet** Nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="1a195-264">I det här avsnittet visas din IP-adress och annan nätverksinformation.</span><span class="sxs-lookup"><span data-stu-id="1a195-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="1a195-265">Med den här metoden kan du kopiera och klistra in IP-adressen på utvecklingsdatorn.</span><span class="sxs-lookup"><span data-stu-id="1a195-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="1a195-266">Ändra IP-adress till statisk adress</span><span class="sxs-lookup"><span data-stu-id="1a195-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="1a195-267">Med hjälp av Inställningar</span><span class="sxs-lookup"><span data-stu-id="1a195-267">By using Settings</span></span>
 
1. <span data-ttu-id="1a195-268">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="1a195-269">Välj **Inställningar** från **Start** eller i **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="1a195-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="1a195-270">Appen **Inställningar** placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="1a195-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="1a195-271">Välj **Nätverk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="1a195-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="1a195-272">Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="1a195-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="1a195-273">I fönstret **Redigera IP-inställningar** ändrar du det första fältet till **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="1a195-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="1a195-274">Ange önskad IP-konfiguration i de återstående fälten och klicka sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="1a195-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="1a195-275">Med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="1a195-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="1a195-276">Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="1a195-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="1a195-277">Gå till **avsnittet** Nätverk.</span><span class="sxs-lookup"><span data-stu-id="1a195-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="1a195-278">Välj knappen **IPv4-konfiguration.**</span><span class="sxs-lookup"><span data-stu-id="1a195-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="1a195-279">Välj **Använd följande IP-adress och** ange önskad TCP/IP-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="1a195-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="1a195-280">Välj **Använd följande DNS-serveradresser och** ange önskade och alternativa DNS-serveradresser om det behövs.</span><span class="sxs-lookup"><span data-stu-id="1a195-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="1a195-281">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1a195-281">Click **Save**.</span></span> 
