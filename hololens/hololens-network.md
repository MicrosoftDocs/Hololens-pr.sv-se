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
# <a name="connect-hololens-to-a-network"></a>Anslut HoloLens till ett nätverk

För att kunna göra det HoloLens måste du vara ansluten till ett nätverk. HoloLens innehåller en 802.11ac-kompatibel 2x2 Wi-Fi-radio och att ansluta den till ett nätverk liknar att ansluta en Windows 10 Desktop- eller Mobile-enhet till ett Wi-Fi-nätverk. Den här guiden hjälper dig att:

- Anslut till ett nätverk med hjälp av Wi-Fi, eller endast för HoloLens 2, Wi-Fi Direct eller Ethernet via USB-C
- Inaktivera och återaktivera Wi-Fi

Läs mer om [att använda HoloLens offline](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Ansluta för första gången

Första gången du använder HoloLens vägleds du genom anslutning till ett Wi-Fi nätverk. Om du har problem med att ansluta till Wi-Fi under installationen kontrollerar du att nätverket antingen är ett öppet lösenordsskyddat nätverk eller ett internt portalnätverk. Kontrollera också att nätverket inte kräver att du använder ett certifikat för att ansluta. Efter installationen kan du ansluta till andra typer av Wi-Fi nätverk.

På HoloLens 2 enheter kan en användare också använda en [USB-C till Ethernet-adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) för att ansluta direkt till Wi-Fi för att hjälpa till med att konfigurera enheten. När enheten har ställts in kan en användare fortsätta att använda adaptern eller så kan de koppla bort enheten från adaptern och ansluta till [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)efter att ha ställt in . 

## <a name="connecting-to-wi-fi-after-setup"></a>Ansluta till Wi-Fi efter installationen

1. Förforma **gesten Start** och välj **Inställningar**. Appen Inställningar placeras automatiskt framför dig.
1. Välj **Network & Internet**  >  **Wi-Fi**. Kontrollera att Wi-Fi är aktiverat. Om du inte ser nätverket rullar du nedåt i listan.
1. Välj ett nätverk och välj **sedan Anslut**.
1. Om du uppmanas att ange ett nätverkslösenord skriver du det och väljer **sedan Nästa.**

![HoloLens Wi-Fi inställningar](./images/hololens-2-wifi-settings.jpg)

Kontrollera att du är ansluten till Wi-Fi nätverk genom att kontrollera Wi-Fi status på **Start-menyn:**

1. Öppna **Start-menyn.**
1. Titta längst upp till vänster på **Start-menyn** för Wi-Fi status. Tillståndet för Wi-Fi och SSID för det anslutna nätverket visas.

> [!TIP]
> Om Wi-Fi inte är tillgänglig kan du också [ansluta till mobilnät och 5G-nätverk.](hololens-cellular.md)

> [!IMPORTANT]
> Användare kan inte finjustera nätverksväxlingsbeteendet för Wi-Fi för HoloLens 2 – det enda sättet att uppdatera Wi-Fi-listan är att växla **Wi-Fi av** och på . Detta förhindrar många problem, t.ex. när en enhet kan "fastna" i en AP när den är utanför intervallet.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Anslut HoloLens till Enterprise Wi-Fi Network

Företagsprofiler Wi-Fi använder EAP (Extensible Authentication Protocol) för att autentisera Wi-Fi anslutningar. HoloLens Enterprise Wi-Fi-profil kan konfigureras via MDM eller etableringspaket som skapats av [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).

Konfigurationsinstruktioner Microsoft Intune en hanterad enhet finns i [Intune.](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

Om du vill Wi-Fi ett konfigurationspaket i WCD krävs en förkonfigurerad Wi-Fi en .xml-fil. Här är ett exempel Wi-Fi profil för WPA2-Enterprise med EAP-TLS-autentisering:

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


Serverns rotcertifikatutfärdarcertifikat och klientcertifikat kan behöva etableras på enheten beroende på EAP-typ.

Ytterligare resurser:

- WLANv1Profile-schema: [[MS-GPWL]: Trådlös LAN-profil v1 schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Kontrollera vår [felsökningssida](hololens2-enterprise-troubleshooting.md#) om du har problem med att ansluta till ditt Wi-Fi.

## <a name="configure-network-proxy"></a>Konfigurera nätverksproxy

Det här avsnittet beskriver nätverksproxy för HoloLens OS- och UWP-appar (Universal Windows Platform) som använder Windows HTTP-stack. Program som använder icke-Windows HTTP-stacken kan ha sin egen proxykonfiguration och -hantering. 

### <a name="proxy-configurations"></a>Proxykonfigurationer 

- PAC-skript (Proxy Auto-Config): En [PAC-fil](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (öppnar en webbplats som inte kommer från Microsoft) innehåller en JavaScript-funktion FindProxyForURL(url, host). 
- Statisk proxy: i form av Server:Port.  
- Web Proxy Auto-Discovery Protocol (WPAD): Ange URL för proxykonfigurationsfilen via DHCP eller DNS. 

### <a name="proxy-provisioning-methods"></a>Proxyetableringsmetoder 
Det finns tre sätt att etablera proxys:

 

1.  **Inställningar Ui:** 
    1. Proxy per användare (20H2 eller tidigare):
        1. Öppna Start-menyn och välj Inställningar.
        2. Välj Nätverk & Internet och sedan Proxy på den vänstra menyn.
        3. Rulla ned till Manuell proxykonfiguration och växla Använd en proxyserver till På.
        4. Ange IP-adressen för proxyservern.
        5. Ange portnumret.
        6. Klicka på Spara.
      1. WiFi-proxy (21H1 eller senare):
          1. Öppna Start-menyn och gå Wi-Fi sidan Egenskaper för ditt nätverk.
          1. Rulla ned till Proxy
          1. Ändra till manuell installation
          1. Ange IP-adressen för proxyservern.
          1. Ange portnumret.
          1. Klicka på Använd.
        
 2. **MDM** 
     1. Intune – Använd de här [stegen för](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) att konfigurera proxy i Intune. Du måste rulla längst ned i avsnittet.
     1. Andra MDM-lösningar från tredje part – Använd en [WiFi CSP](/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Öppna Windows Configuration Designer
    1. Klicka på Avancerad etablering, ange namnet på den nya Project klicka på Nästa.
    1. Välj Windows Holographic (HoloLens 2) och klicka på Nästa.
    1. Importera PPKG (valfritt) och klicka på Slutför.
    1. Expandera Runtime Inställningar -> Connectivity Profiles -> WLAN -> WLAN Proxy.
    1. Ange SSID för ditt Wi-Fi och klicka på Lägg till.
    1. Välj ditt Wi-Fi i det vänstra fönstret och ange önskade anpassningar. De aktiverade anpassningarna visas i fetstil på den vänstra menyn.
    1. Klicka på Spara och avsluta.
    1. [Tillämpa](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) etableringspaketet på HoloLens.

[Molntjänstleverantörer](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) ligger bakom många av hanteringsuppgifterna och principerna för Windows 10, både i Microsoft Intune och hos mdm-tjänstleverantörer som inte kommer från Microsoft. Du kan också använda [Windows Configuration Designer för](/windows/configuration/provisioning-packages/provisioning-install-icd) att skapa ett [konfigurationspaket](/windows/configuration/provisioning-packages/provisioning-packages) och tillämpa det på HoloLens 2.
De mest sannolika CPS som kommer att tillämpas på din HoloLens 2 är:

- [WiFi CSP:](/windows/client-management/mdm/wifi-csp)per profil Wi-Fi proxy 

[Andra CPS som stöds i HoloLens enheter](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
En VPN-anslutning kan ge en säkrare anslutning och åtkomst till företagets nätverk och Internet. HoloLens 2 har stöd för inbyggda VPN-klienter och UWP VPN-plugin-program (Universal Windows Platform). 

Inbyggda VPN-protokoll som stöds:
- IKEv2
- L2TP
- PPTP

Om certifikatet används för autentisering för den inbyggda VPN-klienten måste det nödvändiga klientcertifikatet läggas till i användarens certifikatarkiv. Om du vill ta reda på om ett VPN-plugin-program från tredje part stöder HoloLens 2 går du till Store för att hitta VPN-appen och kontrollerar om HoloLens visas som en enhet som stöds och på sidan Systemkrav stöder appen ARM- eller ARM64-arkitektur. HoloLens endast stöd för Universal Windows Platform-program för VPN från tredje part.

 VPN kan hanteras av MDM via [Inställningar/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)och anges via [Vpnv2-csp-principen](/windows/client-management/mdm/vpnv2-csp).

Läs mer om [hur du konfigurerar VPN med](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hjälp av dessa [guider.](/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>VPN via användargränssnitt

VPN är inte aktiverat som standard men kan aktiveras manuellt genom **att öppna Inställningar** app och navigera till Network & Internet **-> VPN**.
1. Välj en VPN-provider.
1. Skapa ett anslutningsnamn. 
1. Ange ditt servernamn eller din adress.
1. Välj VPN-typ.
1. Välj typ av inloggningsinformation. 
1. Du kan också lägga till användarnamn och lösenord.
1. Tillämpa VPN-inställningarna. 

![HoloLens VPN-inställningar](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN-uppsättning via etableringspaket

> [!TIP] 
> I vår Windows Holographic, version 20H2, har vi åtgärdat ett proxykonfigurationsproblem för VPN-anslutning. Överväg att uppgradera enheter till den här versionen om du tänker använda det här flödet.

1. Starta Windows Configuration Designer.
1. Klicka **på HoloLens enheter** och välj sedan målenhet och **Nästa.**
1. Ange paketnamn och sökväg.
1. Klicka **på Växla till avancerad redigerare.**
1. Öppna **Körningsinställningar**  ->  **AnslutningarProfiler**  ->  **VPN**  ->  **VPNInställningar**.
1. Konfigurera VPNProfileName
1. Välj ProfileType: **Intern** eller **Tredje part.**
    1. För Intern profil väljer du **NativeProtocolType** och konfigurerar sedan server, routningsprincip, autentiseringstyp och andra inställningar.
    1. För profilen "Tredje part" konfigurerar du server-URL, VPN-plugin-programpaketfamiljenamn (endast 3 fördefinierade) och anpassade konfigurationer.
1. Exportera paketet.
1. Anslut din HoloLens och kopiera .ppkg-filen till enheten. 
1. På HoloLens använder du VPN .ppkg genom att öppna Start-menyn och välja Inställningar-kontoåtkomst för arbete eller skola Lägg till eller ta bort etableringspaket  ->    ->    ->   -> Välj ditt VPN-paket.


### <a name="setting-up-vpn-via-intune"></a>Konfigurera VPN via Intune
Följ bara Intune-dokumenten för att komma igång. När du följer de här stegen bör du tänka på de inbyggda VPN-protokoll som HoloLens enheter stöder. 

[Skapa VPN-profiler för att ansluta till VPN-servrar i Intune](/mem/intune/configuration/vpn-settings-configure).

[Windows 10 och Windows Holographic-enhetsinställningar för att lägga till VPN-anslutningar med Intune](/mem/intune/configuration/vpn-settings-windows-10).

Kom ihåg att tilldela [profilen när du är klar.](/mem/intune/configuration/device-profile-assign)

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN via MDM-lösningar från tredje part
Exempel på VPN-anslutning från tredje part:
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

Inbyggt IKEv2 VPN-exempel:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Inaktivera Wi-Fi på HoloLens (första gen)

### <a name="using-the-settings-app-on-hololens"></a>Använda appen Inställningar på HoloLens

1. Öppna **Start-menyn.**
1. Välj **Inställningar** från **Start** eller i **listan Alla** appar till höger på **Start-menyn.** Appen **Inställningar** placeras automatiskt framför dig.
1. Välj **Nätverk & Internet.**
1. Välj skjutreglaget Wi-Fi för att flytta den till **läget Av.** Detta inaktiverar RF-komponenterna i Wi-Fi radio och inaktiverar alla Wi-Fi på HoloLens.

    > [!WARNING]
    > När Wi-Fi är inaktiverad kan HoloLens automatiskt läsa in dina [blanksteg.](hololens-spaces.md)

1. Flytta skjutreglaget till **läget På** för att aktivera Wi-Fi och återställa Wi-Fi på Microsoft HoloLens. Det valda Wi-Fi **(på eller** **av)** bevaras vid omstarter.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identifiera IP-adressen för HoloLens i Wi-Fi nätverk

### <a name="by-using-the-settings-app"></a>Med hjälp av Inställningar appen

1. Öppna **Start-menyn.**
1. Välj **Inställningar** från **Start** eller i **listan Alla** appar till höger på **Start-menyn.** Appen **Inställningar** placeras automatiskt framför dig.
1. Välj **Nätverk & Internet.**
1. Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.

    ![Maskinvaruegenskaper i Wi-Fi inställningar](./images/wifi-hololens-hwdetails.jpg)

   IP-adressen visas bredvid **IPv4-adressen**.

### <a name="by-using-voice-commands"></a>Med hjälp av röstkommandon

Beroende på dina enheter kan du antingen använda inbyggda röstkommandon eller Cortana för att visa din IP-adress. På byggen efter [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) talar vi "What's my IP address?" (Vad är min IP-adress? och den visas. För tidigare versioner eller HoloLens (första generationen) säger du "Hej Cortana, Vad är min IP-adress?" och Cortana att visa och läsa upp din IP-adress.

### <a name="by-using-windows-device-portal"></a>Med hjälp av Windows Enhetsportalen

1. Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Gå till **avsnittet** Nätverk.  
   I det här avsnittet visas din IP-adress och annan nätverksinformation. Med den här metoden kan du kopiera och klistra in IP-adressen på utvecklingsdatorn.

## <a name="change-ip-address-to-static-address"></a>Ändra IP-adress till statisk adress
### <a name="by-using-settings"></a>Med hjälp av Inställningar
 
1. Öppna **Start-menyn.**
1. Välj **Inställningar** från **Start** eller i **listan Alla** appar till höger på **Start-menyn.** Appen **Inställningar** placeras automatiskt framför dig.
1. Välj **Nätverk & Internet.**
1. Rulla ned till under listan över tillgängliga Wi-Fi nätverk och välj **Maskinvaruegenskaper**.
1. I fönstret **Redigera IP-inställningar** ändrar du det första fältet till **Manuell**.
1. Ange önskad IP-konfiguration i de återstående fälten och klicka sedan på **Spara.**

### <a name="by-using-windows-device-portal"></a>Med hjälp av Windows Enhetsportalen

1. Öppna enhetsportalen i en webbläsare [på datorn.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Gå till **avsnittet** Nätverk.
1. Välj knappen **IPv4-konfiguration.**
1. Välj **Använd följande IP-adress och** ange önskad TCP/IP-konfiguration.
1. Välj **Använd följande DNS-serveradresser och** ange önskade och alternativa DNS-serveradresser om det behövs.
1. Klicka på **Spara**. 
