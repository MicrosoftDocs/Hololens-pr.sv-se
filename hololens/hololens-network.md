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
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380068"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="01e7f-104">Ansluta HoloLens till ett nätverk</span><span class="sxs-lookup"><span data-stu-id="01e7f-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="01e7f-105">För att kunna göra det mesta på din HoloLens måste du vara ansluten till ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="01e7f-106">HoloLens innehåller en 802.11ac-kompatibel 2x2 Wi-Fi-radio och att ansluta den till ett nätverk liknar att ansluta en Windows 10 Desktop- eller Mobile-enhet till ett Wi-Fi-nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="01e7f-107">Den här guiden hjälper dig att:</span><span class="sxs-lookup"><span data-stu-id="01e7f-107">This guide will help you:</span></span>

- <span data-ttu-id="01e7f-108">Anslut till ett nätverk med Wi-Fi eller endast för HoloLens 2, Wi-Fi Direct eller Ethernet via USB-C</span><span class="sxs-lookup"><span data-stu-id="01e7f-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="01e7f-109">Inaktivera och återaktivera Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="01e7f-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="01e7f-110">Läs mer om [att använda HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="01e7f-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="01e7f-111">Ansluta för första gången</span><span class="sxs-lookup"><span data-stu-id="01e7f-111">Connecting for the first time</span></span>

<span data-ttu-id="01e7f-112">Första gången du använder hololens vägleds du genom anslutning till ett Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="01e7f-113">Om du har problem med att ansluta till Wi-Fi under installationen kontrollerar du att nätverket antingen är ett öppet lösenordsskyddat nätverk eller ett internt portalnätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="01e7f-114">Kontrollera också att nätverket inte kräver att du använder ett certifikat för att ansluta.</span><span class="sxs-lookup"><span data-stu-id="01e7f-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="01e7f-115">Efter installationen kan du ansluta till andra typer av Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="01e7f-116">På HoloLens 2-enheter kan en användare också använda ett [USB-C till Ethernet-kort](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) för att ansluta direkt till Wi-Fi för att hjälpa till med att konfigurera enheten.</span><span class="sxs-lookup"><span data-stu-id="01e7f-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="01e7f-117">När enheten har ställts in kan en användare fortsätta att använda adaptern eller så kan de koppla bort enheten från adaptern och ansluta till [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)efter att ha ställt in .</span><span class="sxs-lookup"><span data-stu-id="01e7f-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="01e7f-118">Ansluta till Wi-Fi efter installationen</span><span class="sxs-lookup"><span data-stu-id="01e7f-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="01e7f-119">Förforma **gesten Start** och välj **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="01e7f-120">Appen Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="01e7f-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="01e7f-121">Välj **Network & Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="01e7f-122">Kontrollera att Wi-Fi är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="01e7f-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="01e7f-123">Om du inte ser nätverket rullar du nedåt i listan.</span><span class="sxs-lookup"><span data-stu-id="01e7f-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="01e7f-124">Välj ett nätverk och välj sedan **Anslut.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="01e7f-125">Om du uppmanas att ange ett nätverkslösenord skriver du det och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi inställningar](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="01e7f-127">Kontrollera att du är ansluten till Wi-Fi nätverk genom att kontrollera Wi-Fi status på **Start-menyn:**</span><span class="sxs-lookup"><span data-stu-id="01e7f-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="01e7f-128">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="01e7f-129">Titta längst upp till vänster på **Start-menyn** för Wi-Fi status.</span><span class="sxs-lookup"><span data-stu-id="01e7f-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="01e7f-130">Tillståndet för Wi-Fi och SSID för det anslutna nätverket visas.</span><span class="sxs-lookup"><span data-stu-id="01e7f-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="01e7f-131">Om Wi-Fi inte är tillgänglig kan du också [ansluta till mobilnät och 5G-nätverk.](https://docs.microsoft.com/hololens/hololens-cellular)</span><span class="sxs-lookup"><span data-stu-id="01e7f-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01e7f-132">Användare kan inte finjustera Wi-Fi roamingbeteendet för HoloLens 2 – det enda sättet att uppdatera Wi-Fi-listan är att växla **Wi-Fi Av och På**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="01e7f-133">Detta förhindrar många problem, t.ex. när en enhet kan "fastna" i en AP när den är utanför intervallet.</span><span class="sxs-lookup"><span data-stu-id="01e7f-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="01e7f-134">Felsöka anslutningen till Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="01e7f-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="01e7f-135">Om du får problem med att ansluta till Wi-Fi kan du [se Jag kan inte ansluta till Wi-Fi.](./hololens-faq.md#i-cant-connect-to-wi-fi)</span><span class="sxs-lookup"><span data-stu-id="01e7f-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="01e7f-136">När du loggar in på ett företags- eller organisationskonto på enheten kan den även tillämpa mdm-principen (Mobile Enhetshantering), om principen har konfigurerats av IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="01e7f-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="01e7f-137">Ansluta HoloLens till Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="01e7f-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="01e7f-138">Företagsprofiler Wi-Fi använder EAP (Extensible Authentication Protocol) för att autentisera Wi-Fi anslutningar.</span><span class="sxs-lookup"><span data-stu-id="01e7f-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="01e7f-139">HoloLens Enterprise Wi-Fi profilen kan konfigureras via MDM eller etableringspaket som skapats av [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="01e7f-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="01e7f-140">Konfigurationsinstruktioner Microsoft Intune en hanterad enhet finns i [Intune.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)</span><span class="sxs-lookup"><span data-stu-id="01e7f-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="01e7f-141">Om du vill Wi-Fi ett konfigurationspaket i WCD krävs en förkonfigurerad Wi-Fi en .xml-fil.</span><span class="sxs-lookup"><span data-stu-id="01e7f-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="01e7f-142">Här är ett exempel Wi-Fi profil för WPA2-Enterprise med EAP-TLS-autentisering:</span><span class="sxs-lookup"><span data-stu-id="01e7f-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="01e7f-143">Serverns rotcertifikatutfärdarcertifikat och klientcertifikat kan behöva etableras på enheten beroende på EAP-typ.</span><span class="sxs-lookup"><span data-stu-id="01e7f-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="01e7f-144">Ytterligare resurser:</span><span class="sxs-lookup"><span data-stu-id="01e7f-144">Additional resources:</span></span>

- <span data-ttu-id="01e7f-145">WLANv1Profile-schema: [[MS-GPWL]: Trådlös LAN-profil v1 schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="01e7f-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="01e7f-146">EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="01e7f-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

## <a name="eap-troubleshooting"></a><span data-ttu-id="01e7f-147">EAP-felsökning</span><span class="sxs-lookup"><span data-stu-id="01e7f-147">EAP Troubleshooting</span></span>
> [!TIP]
> <span data-ttu-id="01e7f-148">Merparten av nätverksproblemen beror på att någon av inställningarna nedan är felaktiga i Wi-FI-profilen.</span><span class="sxs-lookup"><span data-stu-id="01e7f-148">A majority of network issues are the result of one of the below 3 settings being incorrect in the Wi-FI profile.</span></span> 
1. <span data-ttu-id="01e7f-149">Dubbelkolla Wi-Fi profilen har rätt inställningar:</span><span class="sxs-lookup"><span data-stu-id="01e7f-149">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="01e7f-150">EAP-typen är korrekt konfigurerad, vanliga EAP-typer: EAP-TLS (13), EAP-TTLS (21) och PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="01e7f-150">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="01e7f-151">Wi-Fi SSID-namnet är rätt och matchar med HEX-strängen.</span><span class="sxs-lookup"><span data-stu-id="01e7f-151">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="01e7f-152">För EAP-TLS innehåller TrustedRootCA SHA-1-hashen för serverns&#39;betrodda rotcertifikatutfärdarens certifikat.</span><span class="sxs-lookup"><span data-stu-id="01e7f-152">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="01e7f-153">På Windows PCcertutil.exe kommandot -dump cert file name (namn på -dump-certifikat) visar ett certifikat&#39;&quot; \_ s \_ &quot; SHA-1-hashsträng.</span><span class="sxs-lookup"><span data-stu-id="01e7f-153">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>

2. <span data-ttu-id="01e7f-154">Samla in infångade nätverkspaket på åtkomstpunkten, kontrollanten eller AAA-serverloggarna för att ta reda på var EAP-sessionen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="01e7f-154">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="01e7f-155">Om den EAP-identitet som tillhandahålls av HoloLens inte förväntas kontrollerar du om identiteten har etablerats korrekt via Wi-Fi profil eller klientcertifikat.</span><span class="sxs-lookup"><span data-stu-id="01e7f-155">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="01e7f-156">Om servern avvisar HoloLens-klientcertifikatet kontrollerar du om det nödvändiga klientcertifikatet har etablerats på enheten.</span><span class="sxs-lookup"><span data-stu-id="01e7f-156">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="01e7f-157">Om HoloLens avvisar servercertifikatet kontrollerar du om serverns rotcertifikatutfärdare har etablerats på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01e7f-157">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="01e7f-158">Om företagsprofilen etableras via ett Wi-Fi kan du använda etableringspaketet på en Windows 10 dator.</span><span class="sxs-lookup"><span data-stu-id="01e7f-158">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="01e7f-159">Om det också misslyckas på en Windows 10 dator följer du felsökningsguiden för [Windows-klient 802.1X-autentisering.](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)</span><span class="sxs-lookup"><span data-stu-id="01e7f-159">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="01e7f-160">Ställ in telemetrin på Fullständig eller Valfri (beroende på din version) och skicka sedan feedback via [Feedbackhubben](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="01e7f-160">Set your telemetry to Full or Optional (depending on your build) and then send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="01e7f-161">Ytterligare resurser:</span><span class="sxs-lookup"><span data-stu-id="01e7f-161">Additional resources:</span></span>
- [<span data-ttu-id="01e7f-162">Exportera trådlösa inställningar från en Windows-enhet</span><span class="sxs-lookup"><span data-stu-id="01e7f-162">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a><span data-ttu-id="01e7f-163">Konfigurera nätverksproxy</span><span class="sxs-lookup"><span data-stu-id="01e7f-163">Configure Network Proxy</span></span>

<span data-ttu-id="01e7f-164">Det här avsnittet beskriver nätverksproxy för HoloLens OS- och Universell Windows-plattform-appar (UWP) som använder Windows HTTP-stack.</span><span class="sxs-lookup"><span data-stu-id="01e7f-164">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="01e7f-165">Program som använder HTTP-stackar som inte kommer från Windows kan ha sin egen proxykonfiguration och -hantering.</span><span class="sxs-lookup"><span data-stu-id="01e7f-165">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="01e7f-166">Proxykonfigurationer</span><span class="sxs-lookup"><span data-stu-id="01e7f-166">Proxy Configurations</span></span> 

- <span data-ttu-id="01e7f-167">PAC-skript (Proxy Auto-Config): En [PAC-fil](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (öppnar en webbplats som inte kommer från Microsoft) innehåller en JavaScript-funktion FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="01e7f-167">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="01e7f-168">Statisk proxy: i form av Server:Port.</span><span class="sxs-lookup"><span data-stu-id="01e7f-168">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="01e7f-169">Web Proxy Auto-Discovery Protocol (WPAD): Ange URL för proxykonfigurationsfilen via DHCP eller DNS.</span><span class="sxs-lookup"><span data-stu-id="01e7f-169">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="01e7f-170">Proxyetableringsmetoder</span><span class="sxs-lookup"><span data-stu-id="01e7f-170">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="01e7f-171">Det finns tre sätt att etablera proxys:</span><span class="sxs-lookup"><span data-stu-id="01e7f-171">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="01e7f-172">**Inställningsgränssnitt:**</span><span class="sxs-lookup"><span data-stu-id="01e7f-172">**Settings UI:**</span></span> 
    1. <span data-ttu-id="01e7f-173">Proxy per användare (20H2 eller tidigare):</span><span class="sxs-lookup"><span data-stu-id="01e7f-173">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="01e7f-174">Öppna Start-menyn och välj Inställningar.</span><span class="sxs-lookup"><span data-stu-id="01e7f-174">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="01e7f-175">Välj Nätverk & Internet och sedan Proxy på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="01e7f-175">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="01e7f-176">Rulla ned till Manuell proxykonfiguration och växla Använd en proxyserver till På.</span><span class="sxs-lookup"><span data-stu-id="01e7f-176">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="01e7f-177">Ange IP-adressen för proxyservern.</span><span class="sxs-lookup"><span data-stu-id="01e7f-177">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="01e7f-178">Ange portnumret.</span><span class="sxs-lookup"><span data-stu-id="01e7f-178">Enter the port number.</span></span>
        6. <span data-ttu-id="01e7f-179">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="01e7f-179">Click Save.</span></span>
      1. <span data-ttu-id="01e7f-180">WiFi-proxy (21H1 eller senare):</span><span class="sxs-lookup"><span data-stu-id="01e7f-180">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="01e7f-181">Öppna Start-menyn och gå Wi-Fi sidan Egenskaper för ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-181">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="01e7f-182">Rulla ned till Proxy</span><span class="sxs-lookup"><span data-stu-id="01e7f-182">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="01e7f-183">Ändra till manuell installation</span><span class="sxs-lookup"><span data-stu-id="01e7f-183">Change to Manual Setup</span></span>
          1. <span data-ttu-id="01e7f-184">Ange IP-adressen för proxyservern.</span><span class="sxs-lookup"><span data-stu-id="01e7f-184">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="01e7f-185">Ange portnumret.</span><span class="sxs-lookup"><span data-stu-id="01e7f-185">Enter the port number.</span></span>
          1. <span data-ttu-id="01e7f-186">Klicka på Använd.</span><span class="sxs-lookup"><span data-stu-id="01e7f-186">Click Apply.</span></span>
        
 2. <span data-ttu-id="01e7f-187">**MDM**</span><span class="sxs-lookup"><span data-stu-id="01e7f-187">**MDM**</span></span> 
     1. <span data-ttu-id="01e7f-188">Intune – Använd de här [stegen för](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) att konfigurera proxy i Intune.</span><span class="sxs-lookup"><span data-stu-id="01e7f-188">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="01e7f-189">Du måste rulla längst ned i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="01e7f-189">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="01e7f-190">Andra MDM-lösningar från tredje part – Använd en [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="01e7f-190">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="01e7f-191">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="01e7f-191">**PPKG**</span></span> 
    1. <span data-ttu-id="01e7f-192">Öppna Windows Configuration Designer</span><span class="sxs-lookup"><span data-stu-id="01e7f-192">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="01e7f-193">Klicka på Avancerad etablering, ange namnet på det nya projektet och klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="01e7f-193">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="01e7f-194">Välj Windows Holographic (HoloLens 2) och klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="01e7f-194">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="01e7f-195">Importera PPKG (valfritt) och klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="01e7f-195">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="01e7f-196">Expandera Körningsinställningar - > anslutningsprofiler - > WLAN -> WLAN-proxy.</span><span class="sxs-lookup"><span data-stu-id="01e7f-196">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="01e7f-197">Ange SSID för ditt Wi-Fi och klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="01e7f-197">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="01e7f-198">Välj ditt Wi-Fi i det vänstra fönstret och ange önskade anpassningar.</span><span class="sxs-lookup"><span data-stu-id="01e7f-198">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="01e7f-199">De aktiverade anpassningarna visas i fetstil på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="01e7f-199">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="01e7f-200">Klicka på Spara och avsluta.</span><span class="sxs-lookup"><span data-stu-id="01e7f-200">Click Save and Exit.</span></span>
    1. <span data-ttu-id="01e7f-201">[Tillämpa](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) etableringspaketet på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01e7f-201">[Apply](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="01e7f-202">[Molntjänstleverantörer](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) ligger bakom många av hanteringsuppgifterna och principerna för Windows 10, både i Microsoft Intune och hos MDM-tjänstleverantörer som inte kommer från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01e7f-202">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="01e7f-203">Du kan också använda [Windows Configuration Designer för](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) att skapa ett [konfigurationspaket](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) och tillämpa det på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="01e7f-203">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="01e7f-204">De mest sannolika CPS:erna som kommer att tillämpas på din HoloLens 2 är:</span><span class="sxs-lookup"><span data-stu-id="01e7f-204">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="01e7f-205">[WiFi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)per profil Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="01e7f-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="01e7f-206">Andra CP:er som stöds i HoloLens-enheter</span><span class="sxs-lookup"><span data-stu-id="01e7f-206">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="01e7f-207">VPN</span><span class="sxs-lookup"><span data-stu-id="01e7f-207">VPN</span></span>
<span data-ttu-id="01e7f-208">En VPN-anslutning kan ge en säkrare anslutning och åtkomst till företagets nätverk och Internet.</span><span class="sxs-lookup"><span data-stu-id="01e7f-208">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="01e7f-209">HoloLens 2 har stöd för inbyggda VPN-Universell Windows-plattform VPN-plugin-program (UWP).</span><span class="sxs-lookup"><span data-stu-id="01e7f-209">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="01e7f-210">Inbyggda VPN-protokoll som stöds:</span><span class="sxs-lookup"><span data-stu-id="01e7f-210">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="01e7f-211">IKEv2</span><span class="sxs-lookup"><span data-stu-id="01e7f-211">IKEv2</span></span>
- <span data-ttu-id="01e7f-212">L2TP</span><span class="sxs-lookup"><span data-stu-id="01e7f-212">L2TP</span></span>
- <span data-ttu-id="01e7f-213">PPTP</span><span class="sxs-lookup"><span data-stu-id="01e7f-213">PPTP</span></span>

<span data-ttu-id="01e7f-214">Om certifikatet används för autentisering för den inbyggda VPN-klienten måste det nödvändiga klientcertifikatet läggas till i användarcertifikatarkivet.</span><span class="sxs-lookup"><span data-stu-id="01e7f-214">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="01e7f-215">Om du vill ta reda på om ett VPN-plugin-program från tredje part stöder HoloLens 2 går du till Store för att hitta VPN-appen och kontrollerar om HoloLens visas som en enhet som stöds och på sidan Systemkrav stöder appen ARM- eller ARM64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="01e7f-215">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="01e7f-216">HoloLens stöder endast Universell Windows-plattform-program för VPN från tredje part.</span><span class="sxs-lookup"><span data-stu-id="01e7f-216">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="01e7f-217">VPN kan hanteras av MDM via [Inställningar/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)och anges via  [Vpnv2-csp-principen](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="01e7f-217">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="01e7f-218">Läs mer om [hur du konfigurerar VPN med](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) dessa [guider.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="01e7f-218">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="01e7f-219">VPN via användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="01e7f-219">VPN via UI</span></span>

<span data-ttu-id="01e7f-220">VPN är inte aktiverat som standard men  kan aktiveras manuellt genom att öppna appen Inställningar och gå **till Network & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-220">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="01e7f-221">Välj en VPN-provider.</span><span class="sxs-lookup"><span data-stu-id="01e7f-221">Select a VPN provider.</span></span>
1. <span data-ttu-id="01e7f-222">Skapa ett anslutningsnamn.</span><span class="sxs-lookup"><span data-stu-id="01e7f-222">Create a connection name.</span></span> 
1. <span data-ttu-id="01e7f-223">Ange ditt servernamn eller din adress.</span><span class="sxs-lookup"><span data-stu-id="01e7f-223">Enter your server name or address.</span></span>
1. <span data-ttu-id="01e7f-224">Välj VPN-typ.</span><span class="sxs-lookup"><span data-stu-id="01e7f-224">Select the VPN type.</span></span>
1. <span data-ttu-id="01e7f-225">Välj typ av inloggningsinformation.</span><span class="sxs-lookup"><span data-stu-id="01e7f-225">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="01e7f-226">Du kan också lägga till användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="01e7f-226">Optionally add user name and password.</span></span>
1. <span data-ttu-id="01e7f-227">Tillämpa VPN-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="01e7f-227">Apply the VPN settings.</span></span> 

![HoloLens VPN-inställningar](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="01e7f-229">VPN-uppsättning via etableringspaket</span><span class="sxs-lookup"><span data-stu-id="01e7f-229">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="01e7f-230">I vår Windows Holographic version 20H2 har vi åtgärdat ett proxykonfigurationsproblem för VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="01e7f-230">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="01e7f-231">Överväg att uppgradera enheter till den här versionen om du tänker använda det här flödet.</span><span class="sxs-lookup"><span data-stu-id="01e7f-231">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="01e7f-232">Starta Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="01e7f-232">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="01e7f-233">Klicka **på Etablera HoloLens-enheter** och välj sedan målenhet och **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-233">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="01e7f-234">Ange paketnamn och sökväg.</span><span class="sxs-lookup"><span data-stu-id="01e7f-234">Enter package name and path.</span></span>
1. <span data-ttu-id="01e7f-235">Klicka **på Växla till avancerad redigerare.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-235">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="01e7f-236">Öppna **Körningsinställningar**  ->  **AnslutningarProfiler**  ->  **VPN**  ->  **VPNInställningar**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-236">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="01e7f-237">Konfigurera VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="01e7f-237">Configure VPNProfileName</span></span>
1. <span data-ttu-id="01e7f-238">Välj ProfileType: **Intern** eller **Tredje part.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-238">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="01e7f-239">För Intern profil väljer du **NativeProtocolType** och konfigurerar sedan server, routningsprincip, autentiseringstyp och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="01e7f-239">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="01e7f-240">För profilen "Tredje part" konfigurerar du server-URL, VPN-plugin-programpaketfamiljenamn (endast 3 fördefinierade) och anpassade konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="01e7f-240">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="01e7f-241">Exportera paketet.</span><span class="sxs-lookup"><span data-stu-id="01e7f-241">Export your package.</span></span>
1. <span data-ttu-id="01e7f-242">Anslut din HoloLens och kopiera .ppkg-filen till enheten.</span><span class="sxs-lookup"><span data-stu-id="01e7f-242">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="01e7f-243">På HoloLens tillämpar du VPN .ppkg genom att öppna Start-menyn och välja Inställningar Kontoåtkomst till arbete eller skola Lägg till eller ta bort etableringspaket  ->    ->    ->   -> Välj ditt VPN-paket.</span><span class="sxs-lookup"><span data-stu-id="01e7f-243">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="01e7f-244">Konfigurera VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="01e7f-244">Setting up VPN via Intune</span></span>
<span data-ttu-id="01e7f-245">Följ bara Intune-dokumenten för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="01e7f-245">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="01e7f-246">När du följer de här stegen bör du tänka på de inbyggda VPN-protokoll som HoloLens-enheter stöder.</span><span class="sxs-lookup"><span data-stu-id="01e7f-246">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="01e7f-247">[Skapa VPN-profiler för att ansluta till VPN-servrar i Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="01e7f-247">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="01e7f-248">[Windows 10 och Windows Holographic-enhetsinställningar för att lägga till VPN-anslutningar med Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="01e7f-248">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="01e7f-249">Kom ihåg att tilldela [profilen när du är klar.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="01e7f-249">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="01e7f-250">VPN via MDM-lösningar från tredje part</span><span class="sxs-lookup"><span data-stu-id="01e7f-250">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="01e7f-251">Exempel på VPN-anslutning från tredje part:</span><span class="sxs-lookup"><span data-stu-id="01e7f-251">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="01e7f-252">Inbyggt IKEv2 VPN-exempel:</span><span class="sxs-lookup"><span data-stu-id="01e7f-252">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="01e7f-253">Inaktivera Wi-Fi hololens (första gen)</span><span class="sxs-lookup"><span data-stu-id="01e7f-253">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="01e7f-254">Använda inställningsappen på HoloLens</span><span class="sxs-lookup"><span data-stu-id="01e7f-254">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="01e7f-255">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-255">Open the **Start** menu.</span></span>
1. <span data-ttu-id="01e7f-256">Välj appen **Inställningar** från **Start** eller från **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-256">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="01e7f-257">Appen  Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="01e7f-257">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="01e7f-258">Välj **Nätverk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-258">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="01e7f-259">Välj skjutreglaget Wi-Fi för att flytta den till **läget Av.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-259">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="01e7f-260">Detta inaktiverar RF-komponenterna i Wi-Fi radio och inaktiverar alla Wi-Fi på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01e7f-260">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="01e7f-261">När Wi-Fi är inaktiverat kan HoloLens inte läsa in dina utrymmen [automatiskt.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="01e7f-261">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="01e7f-262">Flytta skjutreglaget till läget **På** för att aktivera Wi-Fi och återställa Wi-Fi på Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01e7f-262">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="01e7f-263">Det valda Wi-Fi **(på eller** **av)** bevaras vid omstarter.</span><span class="sxs-lookup"><span data-stu-id="01e7f-263">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="01e7f-264">Identifiera IP-adressen för din HoloLens i det Wi-Fi nätverket</span><span class="sxs-lookup"><span data-stu-id="01e7f-264">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="01e7f-265">Med hjälp av appen Inställningar</span><span class="sxs-lookup"><span data-stu-id="01e7f-265">By using the Settings app</span></span>

1. <span data-ttu-id="01e7f-266">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-266">Open the **Start** menu.</span></span>
1. <span data-ttu-id="01e7f-267">Välj appen **Inställningar** från **Start** eller från **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-267">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="01e7f-268">Appen  Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="01e7f-268">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="01e7f-269">Välj **Nätverk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-269">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="01e7f-270">Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-270">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Maskinvaruegenskaper i Wi-Fi inställningar](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="01e7f-272">IP-adressen visas bredvid **IPv4-adressen**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-272">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="01e7f-273">Med hjälp av röstkommandon</span><span class="sxs-lookup"><span data-stu-id="01e7f-273">By using voice commands</span></span>

<span data-ttu-id="01e7f-274">Beroende på dina enheter kan du antingen använda inbyggda röstkommandon eller Cortana för att visa din IP-adress.</span><span class="sxs-lookup"><span data-stu-id="01e7f-274">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="01e7f-275">På byggen efter [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) talar vi "What's my IP address?" (Vad är min IP-adress?</span><span class="sxs-lookup"><span data-stu-id="01e7f-275">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="01e7f-276">och den visas.</span><span class="sxs-lookup"><span data-stu-id="01e7f-276">and it will be displayed.</span></span> <span data-ttu-id="01e7f-277">För tidigare versioner eller HoloLens (första gen) säger du "Hej Cortana, Vad är min IP-adress?"</span><span class="sxs-lookup"><span data-stu-id="01e7f-277">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="01e7f-278">och Cortana visar och läser upp din IP-adress.</span><span class="sxs-lookup"><span data-stu-id="01e7f-278">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="01e7f-279">Med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="01e7f-279">By using Windows Device Portal</span></span>

1. <span data-ttu-id="01e7f-280">Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="01e7f-280">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="01e7f-281">Gå till **avsnittet** Nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-281">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="01e7f-282">I det här avsnittet visas din IP-adress och annan nätverksinformation.</span><span class="sxs-lookup"><span data-stu-id="01e7f-282">This section displays your IP address and other network information.</span></span> <span data-ttu-id="01e7f-283">Med den här metoden kan du kopiera och klistra in IP-adressen på utvecklingsdatorn.</span><span class="sxs-lookup"><span data-stu-id="01e7f-283">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="01e7f-284">Ändra IP-adress till statisk adress</span><span class="sxs-lookup"><span data-stu-id="01e7f-284">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="01e7f-285">Med hjälp av inställningar</span><span class="sxs-lookup"><span data-stu-id="01e7f-285">By using Settings</span></span>
 
1. <span data-ttu-id="01e7f-286">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-286">Open the **Start** menu.</span></span>
1. <span data-ttu-id="01e7f-287">Välj appen **Inställningar** från **Start** eller från **listan Alla** appar till höger på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-287">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="01e7f-288">Appen  Inställningar placeras automatiskt framför dig.</span><span class="sxs-lookup"><span data-stu-id="01e7f-288">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="01e7f-289">Välj **Nätverk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-289">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="01e7f-290">Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-290">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="01e7f-291">I fönstret **Redigera IP-inställningar** ändrar du det första fältet till **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-291">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="01e7f-292">Ange önskad IP-konfiguration i de återstående fälten och klicka sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-292">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="01e7f-293">Med hjälp av Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="01e7f-293">By using Windows Device Portal</span></span>

1. <span data-ttu-id="01e7f-294">Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="01e7f-294">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="01e7f-295">Gå till **avsnittet** Nätverk.</span><span class="sxs-lookup"><span data-stu-id="01e7f-295">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="01e7f-296">Välj knappen **IPv4-konfiguration.**</span><span class="sxs-lookup"><span data-stu-id="01e7f-296">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="01e7f-297">Välj **Använd följande IP-adress och** ange önskad TCP/IP-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="01e7f-297">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="01e7f-298">Välj **Använd följande DNS-serveradresser och** ange önskade och alternativa DNS-serveradresser om det behövs.</span><span class="sxs-lookup"><span data-stu-id="01e7f-298">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="01e7f-299">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01e7f-299">Click **Save**.</span></span> 