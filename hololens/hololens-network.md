---
title: Ansluta HoloLens till ett nätverk
description: Lär dig att konfigurera och ansluta till Internet med HoloLens och hur du identifierar enhetens IP-adress.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, trådlöst, Internet, ip, ip-adress
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923609"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="36e69-104">Ansluta HoloLens till ett nätverk</span><span class="sxs-lookup"><span data-stu-id="36e69-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="36e69-105">För att kunna göra det mesta på din HoloLens måste du vara ansluten till ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="36e69-106">HoloLens innehåller en 802.11ac-kompatibel 2x2 Wi-Fi-radio och att ansluta den till ett nätverk liknar att ansluta en Windows 10 Desktop- eller Mobile-enhet till ett Wi-Fi-nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="36e69-107">Den här guiden hjälper dig att:</span><span class="sxs-lookup"><span data-stu-id="36e69-107">This guide will help you:</span></span>

- <span data-ttu-id="36e69-108">Anslut till ett nätverk med Wi-Fi eller endast för HoloLens 2, Wi-Fi Direct eller Ethernet via USB-C</span><span class="sxs-lookup"><span data-stu-id="36e69-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="36e69-109">Inaktivera och återaktivera Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="36e69-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="36e69-110">Läs mer om [att använda HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="36e69-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="36e69-111">Ansluta för första gången</span><span class="sxs-lookup"><span data-stu-id="36e69-111">Connecting for the first time</span></span>

<span data-ttu-id="36e69-112">Första gången du använder hololens vägleds du genom anslutning till ett Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="36e69-113">Om du har problem med att ansluta till Wi-Fi under installationen kontrollerar du att nätverket antingen är ett öppet lösenordsskyddat nätverk eller ett internt portalnätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="36e69-114">Kontrollera också att nätverket inte kräver att du använder ett certifikat för att ansluta.</span><span class="sxs-lookup"><span data-stu-id="36e69-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="36e69-115">Efter installationen kan du ansluta till andra typer av Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="36e69-116">På HoloLens 2-enheter kan en användare också använda ett [USB-C till Ethernet-kort](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) för att ansluta direkt till Wi-Fi för att hjälpa till med att konfigurera enheten.</span><span class="sxs-lookup"><span data-stu-id="36e69-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="36e69-117">När enheten har ställts in kan en användare fortsätta att använda adaptern eller så kan de koppla bort enheten från adaptern och ansluta till [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)efter att ha ställt in .</span><span class="sxs-lookup"><span data-stu-id="36e69-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="36e69-118">Ansluta till Wi-Fi efter installationen</span><span class="sxs-lookup"><span data-stu-id="36e69-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="36e69-119">Förforma **gesten Start** och välj **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="36e69-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="36e69-120">Appen Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="36e69-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="36e69-121">Välj **Network & Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="36e69-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="36e69-122">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="36e69-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="36e69-123">Om du inte ser nätverket rullar du nedåt i listan.</span><span class="sxs-lookup"><span data-stu-id="36e69-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="36e69-124">Välj ett nätverk och välj sedan **Anslut.**</span><span class="sxs-lookup"><span data-stu-id="36e69-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="36e69-125">Om du uppmanas att ange ett nätverkslösenord skriver du det och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="36e69-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi inställningar](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="36e69-127">Kontrollera att du är ansluten till Wi-Fi nätverk genom att kontrollera Wi-Fi status på **Start-menyn:**</span><span class="sxs-lookup"><span data-stu-id="36e69-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="36e69-128">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="36e69-129">Titta längst upp till vänster på **Start-menyn** för Wi-Fi status.</span><span class="sxs-lookup"><span data-stu-id="36e69-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="36e69-130">Tillståndet för Wi-Fi och SSID för det anslutna nätverket visas.</span><span class="sxs-lookup"><span data-stu-id="36e69-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="36e69-131">Om Wi-Fi inte är tillgänglig kan du också [ansluta till mobilnät och 5G-nätverk.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="36e69-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36e69-132">Användare kan inte finjustera Wi-Fi roamingbeteendet för HoloLens 2 – det enda sättet att uppdatera Wi-Fi-listan är att växla **Wi-Fi Av och På**.</span><span class="sxs-lookup"><span data-stu-id="36e69-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="36e69-133">Detta förhindrar många problem, t.ex. när en enhet kan "fastna" i en AP när den är utanför intervallet.</span><span class="sxs-lookup"><span data-stu-id="36e69-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="36e69-134">Ansluta HoloLens till Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="36e69-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="36e69-135">Företagsprofiler Wi-Fi använder EAP (Extensible Authentication Protocol) för att autentisera Wi-Fi anslutningar.</span><span class="sxs-lookup"><span data-stu-id="36e69-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="36e69-136">HoloLens Enterprise Wi-Fi profilen kan konfigureras via MDM eller etableringspaket som skapats av [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="36e69-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="36e69-137">Konfigurationsinstruktioner Microsoft Intune en hanterad enhet finns i [Intune.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)</span><span class="sxs-lookup"><span data-stu-id="36e69-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="36e69-138">Om du vill Wi-Fi ett konfigurationspaket i WCD krävs en förkonfigurerad Wi-Fi en .xml-fil.</span><span class="sxs-lookup"><span data-stu-id="36e69-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="36e69-139">Här är ett exempel Wi-Fi profil för WPA2-Enterprise med EAP-TLS-autentisering:</span><span class="sxs-lookup"><span data-stu-id="36e69-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="36e69-140">Serverns rotcertifikatutfärdarcertifikat och klientcertifikat kan behöva etableras på enheten beroende på EAP-typ.</span><span class="sxs-lookup"><span data-stu-id="36e69-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="36e69-141">Ytterligare resurser:</span><span class="sxs-lookup"><span data-stu-id="36e69-141">Additional resources:</span></span>

- <span data-ttu-id="36e69-142">WLANv1Profile-schema: [[MS-GPWL]: Trådlös LAN-profil v1 schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="36e69-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="36e69-143">EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="36e69-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="36e69-144">Kontrollera vår [felsökningssida](hololens2-enterprise-troubleshooting.md#) om du har problem med att ansluta till ditt Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="36e69-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="36e69-145">Konfigurera nätverksproxy</span><span class="sxs-lookup"><span data-stu-id="36e69-145">Configure Network Proxy</span></span>

<span data-ttu-id="36e69-146">Det här avsnittet beskriver nätverksproxy för HoloLens OS- och Universell Windows-plattform-appar (UWP) som använder Windows HTTP-stack.</span><span class="sxs-lookup"><span data-stu-id="36e69-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="36e69-147">Program som använder HTTP-stackar som inte kommer från Windows kan ha sin egen proxykonfiguration och -hantering.</span><span class="sxs-lookup"><span data-stu-id="36e69-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="36e69-148">Proxykonfigurationer</span><span class="sxs-lookup"><span data-stu-id="36e69-148">Proxy Configurations</span></span> 

- <span data-ttu-id="36e69-149">PAC-skript (Proxy Auto-Config): En [PAC-fil](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (öppnar en webbplats som inte kommer från Microsoft) innehåller en JavaScript-funktion FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="36e69-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="36e69-150">Statisk proxy: i form av Server:Port.</span><span class="sxs-lookup"><span data-stu-id="36e69-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="36e69-151">Web Proxy Auto-Discovery Protocol (WPAD): Ange URL för proxykonfigurationsfilen via DHCP eller DNS.</span><span class="sxs-lookup"><span data-stu-id="36e69-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="36e69-152">Proxyetableringsmetoder</span><span class="sxs-lookup"><span data-stu-id="36e69-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="36e69-153">Det finns tre sätt att etablera proxys:</span><span class="sxs-lookup"><span data-stu-id="36e69-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="36e69-154">**Inställningsgränssnitt:**</span><span class="sxs-lookup"><span data-stu-id="36e69-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="36e69-155">Proxy per användare (20H2 eller tidigare):</span><span class="sxs-lookup"><span data-stu-id="36e69-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="36e69-156">Öppna Start-menyn och välj Inställningar.</span><span class="sxs-lookup"><span data-stu-id="36e69-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="36e69-157">Välj Nätverk & Internet och sedan Proxy på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="36e69-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="36e69-158">Rulla ned till Manuell proxykonfiguration och växla Använd en proxyserver till På.</span><span class="sxs-lookup"><span data-stu-id="36e69-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="36e69-159">Ange IP-adressen för proxyservern.</span><span class="sxs-lookup"><span data-stu-id="36e69-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="36e69-160">Ange portnumret.</span><span class="sxs-lookup"><span data-stu-id="36e69-160">Enter the port number.</span></span>
        6. <span data-ttu-id="36e69-161">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="36e69-161">Click Save.</span></span>
      1. <span data-ttu-id="36e69-162">WiFi-proxy (21H1 eller senare):</span><span class="sxs-lookup"><span data-stu-id="36e69-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="36e69-163">Öppna Start-menyn och gå Wi-Fi sidan Egenskaper för ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="36e69-164">Rulla ned till Proxy</span><span class="sxs-lookup"><span data-stu-id="36e69-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="36e69-165">Ändra till manuell installation</span><span class="sxs-lookup"><span data-stu-id="36e69-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="36e69-166">Ange IP-adressen för proxyservern.</span><span class="sxs-lookup"><span data-stu-id="36e69-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="36e69-167">Ange portnumret.</span><span class="sxs-lookup"><span data-stu-id="36e69-167">Enter the port number.</span></span>
          1. <span data-ttu-id="36e69-168">Klicka på Använd.</span><span class="sxs-lookup"><span data-stu-id="36e69-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="36e69-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="36e69-169">**MDM**</span></span> 
     1. <span data-ttu-id="36e69-170">Intune – Använd de här [stegen för](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) att konfigurera proxy i Intune.</span><span class="sxs-lookup"><span data-stu-id="36e69-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="36e69-171">Du måste rulla längst ned i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="36e69-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="36e69-172">Andra MDM-lösningar från tredje part – Använd en [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="36e69-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="36e69-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="36e69-173">**PPKG**</span></span> 
    1. <span data-ttu-id="36e69-174">Öppna Windows Configuration Designer</span><span class="sxs-lookup"><span data-stu-id="36e69-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="36e69-175">Klicka på Avancerad etablering, ange namnet på det nya projektet och klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="36e69-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="36e69-176">Välj Windows Holographic (HoloLens 2) och klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="36e69-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="36e69-177">Importera PPKG (valfritt) och klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="36e69-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="36e69-178">Expandera Körningsinställningar - > anslutningsprofiler - > WLAN -> WLAN-proxy.</span><span class="sxs-lookup"><span data-stu-id="36e69-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="36e69-179">Ange SSID för ditt Wi-Fi och klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="36e69-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="36e69-180">Välj ditt Wi-Fi i det vänstra fönstret och ange önskade anpassningar.</span><span class="sxs-lookup"><span data-stu-id="36e69-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="36e69-181">De aktiverade anpassningarna visas i fetstil på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="36e69-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="36e69-182">Klicka på Spara och avsluta.</span><span class="sxs-lookup"><span data-stu-id="36e69-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="36e69-183">[Tillämpa](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) etableringspaketet på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36e69-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="36e69-184">[Molntjänstleverantörer](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) ligger bakom många av hanteringsuppgifterna och principerna för Windows 10, både i Microsoft Intune och hos MDM-tjänstleverantörer som inte kommer från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36e69-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="36e69-185">Du kan också använda [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) för att skapa ett [konfigurationspaket](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) och tillämpa det på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="36e69-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="36e69-186">De mest sannolika CPS som kommer att tillämpas på din HoloLens 2 är:</span><span class="sxs-lookup"><span data-stu-id="36e69-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="36e69-187">[WiFi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)per profil Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="36e69-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="36e69-188">Andra CPS som stöds i HoloLens-enheter</span><span class="sxs-lookup"><span data-stu-id="36e69-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="36e69-189">VPN</span><span class="sxs-lookup"><span data-stu-id="36e69-189">VPN</span></span>
<span data-ttu-id="36e69-190">En VPN-anslutning kan ge en säkrare anslutning och åtkomst till företagets nätverk och Internet.</span><span class="sxs-lookup"><span data-stu-id="36e69-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="36e69-191">HoloLens 2 har stöd för inbyggda VPN-Universell Windows-plattform VPN-plugin-program (UWP).</span><span class="sxs-lookup"><span data-stu-id="36e69-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="36e69-192">Inbyggda VPN-protokoll som stöds:</span><span class="sxs-lookup"><span data-stu-id="36e69-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="36e69-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="36e69-193">IKEv2</span></span>
- <span data-ttu-id="36e69-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="36e69-194">L2TP</span></span>
- <span data-ttu-id="36e69-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="36e69-195">PPTP</span></span>

<span data-ttu-id="36e69-196">Om certifikatet används för autentisering för den inbyggda VPN-klienten måste det nödvändiga klientcertifikatet läggas till i användarens certifikatarkiv.</span><span class="sxs-lookup"><span data-stu-id="36e69-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="36e69-197">Om du vill ta reda på om ett VPN-plugin-program från tredje part stöder HoloLens 2 går du till Store för att hitta VPN-appen och kontrollerar om HoloLens visas som en enhet som stöds och på sidan Systemkrav stöder appen ARM- eller ARM64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="36e69-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="36e69-198">HoloLens stöder endast Universell Windows-plattform-program för VPN från tredje part.</span><span class="sxs-lookup"><span data-stu-id="36e69-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="36e69-199">VPN kan hanteras av MDM via [Inställningar/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)och anges via  [Vpnv2-csp-principen](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="36e69-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="36e69-200">Läs mer om [hur du konfigurerar VPN med](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hjälp av dessa [guider.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="36e69-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="36e69-201">VPN via användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="36e69-201">VPN via UI</span></span>

<span data-ttu-id="36e69-202">VPN är inte aktiverat som standard men  kan aktiveras manuellt genom att öppna appen Inställningar och navigera **till Network & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="36e69-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="36e69-203">Välj en VPN-provider.</span><span class="sxs-lookup"><span data-stu-id="36e69-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="36e69-204">Skapa ett anslutningsnamn.</span><span class="sxs-lookup"><span data-stu-id="36e69-204">Create a connection name.</span></span> 
1. <span data-ttu-id="36e69-205">Ange ditt servernamn eller din adress.</span><span class="sxs-lookup"><span data-stu-id="36e69-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="36e69-206">Välj VPN-typ.</span><span class="sxs-lookup"><span data-stu-id="36e69-206">Select the VPN type.</span></span>
1. <span data-ttu-id="36e69-207">Välj typ av inloggningsinformation.</span><span class="sxs-lookup"><span data-stu-id="36e69-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="36e69-208">Du kan också lägga till användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="36e69-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="36e69-209">Tillämpa VPN-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="36e69-209">Apply the VPN settings.</span></span> 

![HoloLens VPN-inställningar](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="36e69-211">VPN-uppsättning via etableringspaket</span><span class="sxs-lookup"><span data-stu-id="36e69-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="36e69-212">I vår Windows Holographic version 20H2 har vi åtgärdat ett proxykonfigurationsproblem för VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="36e69-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="36e69-213">Överväg att uppgradera enheter till den här versionen om du planerar att använda det här flödet.</span><span class="sxs-lookup"><span data-stu-id="36e69-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="36e69-214">Starta Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="36e69-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="36e69-215">Klicka **på Etablera HoloLens-enheter** och välj sedan målenhet och **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="36e69-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="36e69-216">Ange paketnamn och sökväg.</span><span class="sxs-lookup"><span data-stu-id="36e69-216">Enter package name and path.</span></span>
1. <span data-ttu-id="36e69-217">Klicka **på Växla till avancerad redigerare.**</span><span class="sxs-lookup"><span data-stu-id="36e69-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="36e69-218">Öppna **Körningsinställningar**  ->  **AnslutningarProfiler**  ->  **VPN**  ->  **VPNInställningar.**</span><span class="sxs-lookup"><span data-stu-id="36e69-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="36e69-219">Konfigurera VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="36e69-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="36e69-220">Välj ProfileType: **Native** eller **Third Party**.</span><span class="sxs-lookup"><span data-stu-id="36e69-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="36e69-221">För Intern profil väljer du **NativeProtocolType** och konfigurerar sedan server, routningsprincip, autentiseringstyp och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="36e69-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="36e69-222">För profilen "Tredje part" konfigurerar du server-URL, PAKETfamiljenamn för VPN-plugin-program (endast 3 fördefinierade) och anpassade konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="36e69-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="36e69-223">Exportera paketet.</span><span class="sxs-lookup"><span data-stu-id="36e69-223">Export your package.</span></span>
1. <span data-ttu-id="36e69-224">Anslut din HoloLens och kopiera .ppkg-filen till enheten.</span><span class="sxs-lookup"><span data-stu-id="36e69-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="36e69-225">På HoloLens tillämpar du VPN .ppkg genom att öppna Start-menyn och välja Åtkomst till kontoinställningar för arbete eller skola Lägg till eller ta bort etableringspaket  ->    ->    ->   -> Välj ditt VPN-paket.</span><span class="sxs-lookup"><span data-stu-id="36e69-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="36e69-226">Konfigurera VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="36e69-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="36e69-227">Följ bara Intune-dokumenten för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="36e69-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="36e69-228">När du följer de här stegen bör du tänka på de inbyggda VPN-protokoll som HoloLens-enheter stöder.</span><span class="sxs-lookup"><span data-stu-id="36e69-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="36e69-229">[Skapa VPN-profiler för att ansluta till VPN-servrar i Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="36e69-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="36e69-230">[Windows 10 och Windows Holographic-enhetsinställningar för att lägga till VPN-anslutningar med Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="36e69-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="36e69-231">Kom ihåg att tilldela [profilen när du är klar.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="36e69-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="36e69-232">VPN via MDM-lösningar från tredje part</span><span class="sxs-lookup"><span data-stu-id="36e69-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="36e69-233">Exempel på VPN-anslutning från tredje part:</span><span class="sxs-lookup"><span data-stu-id="36e69-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="36e69-234">Inbyggt IKEv2 VPN-exempel:</span><span class="sxs-lookup"><span data-stu-id="36e69-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="36e69-235">Inaktivera Wi-Fi på HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="36e69-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="36e69-236">Använda inställningsappen på HoloLens</span><span class="sxs-lookup"><span data-stu-id="36e69-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="36e69-237">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="36e69-238">Välj appen **Inställningar** från **Start** eller från **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="36e69-239">Appen  Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="36e69-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="36e69-240">Välj **Nätverk & Internet**.</span><span class="sxs-lookup"><span data-stu-id="36e69-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="36e69-241">Välj skjutreglaget Wi-Fi för att flytta den till **läget Av.**</span><span class="sxs-lookup"><span data-stu-id="36e69-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="36e69-242">Detta inaktiverar RF-komponenterna i Wi-Fi radio och inaktiverar alla Wi-Fi på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36e69-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="36e69-243">När Wi-Fi är inaktiverat kan HoloLens inte läsa in dina blanksteg [automatiskt.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="36e69-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="36e69-244">Flytta skjutreglaget till **läget På** för att aktivera Wi-Fi och återställa Wi-Fi på Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36e69-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="36e69-245">Det valda Wi-Fi **(på eller** **av)** bevaras vid omstarter.</span><span class="sxs-lookup"><span data-stu-id="36e69-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="36e69-246">Identifiera IP-adressen för din HoloLens i det Wi-Fi nätverket</span><span class="sxs-lookup"><span data-stu-id="36e69-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="36e69-247">Med appen Inställningar</span><span class="sxs-lookup"><span data-stu-id="36e69-247">By using the Settings app</span></span>

1. <span data-ttu-id="36e69-248">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="36e69-249">Välj appen **Inställningar** från **Start** eller från **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="36e69-250">Appen  Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="36e69-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="36e69-251">Välj **Nätverk & Internet**.</span><span class="sxs-lookup"><span data-stu-id="36e69-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="36e69-252">Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="36e69-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Maskinvaruegenskaper i Wi-Fi inställningar](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="36e69-254">IP-adressen visas bredvid **IPv4-adressen**.</span><span class="sxs-lookup"><span data-stu-id="36e69-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="36e69-255">Med hjälp av röstkommandon</span><span class="sxs-lookup"><span data-stu-id="36e69-255">By using voice commands</span></span>

<span data-ttu-id="36e69-256">Beroende på dina enheter kan du antingen använda inbyggda röstkommandon eller Cortana för att visa din IP-adress.</span><span class="sxs-lookup"><span data-stu-id="36e69-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="36e69-257">På byggen efter [19041.1103 talar](hololens-release-notes.md#windows-holographic-version-2004) du "What's my IP address?" (Vad är min IP-adress?</span><span class="sxs-lookup"><span data-stu-id="36e69-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="36e69-258">och den visas.</span><span class="sxs-lookup"><span data-stu-id="36e69-258">and it will be displayed.</span></span> <span data-ttu-id="36e69-259">För tidigare versioner eller HoloLens (första generationen) säger du "Hej Cortana, vad är min IP-adress?"</span><span class="sxs-lookup"><span data-stu-id="36e69-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="36e69-260">och Cortana visar och läser upp din IP-adress.</span><span class="sxs-lookup"><span data-stu-id="36e69-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="36e69-261">Med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="36e69-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="36e69-262">Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="36e69-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="36e69-263">Gå till **avsnittet** Nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="36e69-264">I det här avsnittet visas din IP-adress och annan nätverksinformation.</span><span class="sxs-lookup"><span data-stu-id="36e69-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="36e69-265">Med den här metoden kan du kopiera och klistra in IP-adressen på utvecklingsdatorn.</span><span class="sxs-lookup"><span data-stu-id="36e69-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="36e69-266">Ändra IP-adress till statisk adress</span><span class="sxs-lookup"><span data-stu-id="36e69-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="36e69-267">Med hjälp av inställningar</span><span class="sxs-lookup"><span data-stu-id="36e69-267">By using Settings</span></span>
 
1. <span data-ttu-id="36e69-268">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="36e69-269">Välj appen **Inställningar** från **Start** eller från **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="36e69-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="36e69-270">Appen  Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="36e69-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="36e69-271">Välj **Nätverk & Internet**.</span><span class="sxs-lookup"><span data-stu-id="36e69-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="36e69-272">Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="36e69-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="36e69-273">I fönstret **Redigera IP-inställningar** ändrar du det första fältet till **Manuell.**</span><span class="sxs-lookup"><span data-stu-id="36e69-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="36e69-274">Ange önskad IP-konfiguration i de återstående fälten och klicka sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="36e69-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="36e69-275">Med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="36e69-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="36e69-276">Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="36e69-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="36e69-277">Gå till **avsnittet** Nätverk.</span><span class="sxs-lookup"><span data-stu-id="36e69-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="36e69-278">Välj knappen **IPv4-konfiguration.**</span><span class="sxs-lookup"><span data-stu-id="36e69-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="36e69-279">Välj **Använd följande IP-adress och ange** önskad TCP/IP-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="36e69-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="36e69-280">Välj **Använd följande DNS-serveradresser** och ange önskade och alternativa DNS-serveradresser om det behövs.</span><span class="sxs-lookup"><span data-stu-id="36e69-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="36e69-281">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="36e69-281">Click **Save**.</span></span> 
