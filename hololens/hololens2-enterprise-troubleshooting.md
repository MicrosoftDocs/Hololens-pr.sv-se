---
title: HoloLens 2-implementering och felsökning av hanterad enhet
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
ms.openlocfilehash: f038cbf58b6dfaef0395a1ea5b406cce23e4e3fe0464c6bfc1162518f9caf3ff
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659784"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Felsökning av implementering och hanterade enheter 

Den här artikeln beskriver hur du löser flera problem eller besvarar frågor om implementering och hantering av HoloLens 2.

>[!IMPORTANT]
> Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt. Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.


<a id="list"></a>
- [EAP-felsökning](#eap-troubleshooting)
- [Felsökning av Wi-Fi](#wi-fi-troubleshooting)
- [Felsökning av nätverk](#network-troubleshooting)
- [Det går inte att logga in på en tidigare HoloLens enhet](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Det går inte att logga in efter uppdatering till Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot-felsökning](#autopilot-troubleshooting)
- [Vanliga frågor och svar HoloLens hanterade enheter](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP-felsökning
1. Dubbelkolla Wi-Fi profilen har rätt inställningar:
    - EAP-typen är korrekt konfigurerad, vanliga EAP-typer: EAP-TLS (13), EAP-TTLS (21) och PEAP (25).
    - Wi-Fi SSID-namnet är rätt och matchar med HEX-strängen.
    - För EAP-TLS innehåller TrustedRootCA SHA-1-hashen för serverns betrodda rotcertifikatutfärdarcertifikat. På Windows pc-kommandot "certutil.exe -dump cert_file_name" visas certifikatets SHA-1-hashsträng.
2. Samla in infångade nätverkspaket på åtkomstpunkten, kontrollanten eller AAA-serverloggarna för att ta reda på var EAP-sessionen misslyckas.
    - Om EAP-identiteten som tillhandahålls av HoloLens inte förväntas kontrollerar du om identiteten har etablerats korrekt via Wi-Fi profil eller klientcertifikat.
    - Om servern avvisar HoloLens klientcertifikat kontrollerar du om det nödvändiga klientcertifikatet har etablerats på enheten.
    - Om HoloLens avvisar servercertifikatet kontrollerar du om serverns rotcertifikatutfärdare har etablerats på HoloLens.
3. Om företagsprofilen etableras via ett Wi-Fi-etableringspaket bör du överväga att tillämpa etableringspaketet på en Windows 10 dator. Om det också misslyckas på Windows 10 dator följer du felsökningsguiden för Windows 802.1X-autentisering.
4. Skicka feedback via Feedbackhubben.

[Tillbaka till listan](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi felsökning

Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:

1. Kontrollera att Wi-Fi är aktiverat. Om du vill kontrollera det använder du gesten Start och väljer Inställningar > Nätverk & Internet > Wi-Fi. Om Wi-Fi är på kan du prova att stänga av det och sedan på igen.
2. Flytta datorn närmare routern eller åtkomstpunkten.
3. Starta om Wi-Fi router och starta sedan om HoloLens. Försök att ansluta igen.
4. Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran. Du hittar den här informationen på tillverkarens webbplats.

När du loggar in på ett företags- eller organisationskonto på enheten kan den även använda MDM-principen (Mobile Enhetshantering), om principen har konfigurerats av IT-administratören.

[Tillbaka till listan](#list)

## <a name="network-troubleshooting"></a>Felsökning av nätverk
Om nätverksproblem är ett hinder för att distribuera och använda HoloLens 2 i din organisation konfigurerar du Fiddler och/eller Wireshark för att samla in och analysera HTTP/HTTPS-trafik. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurera Fiddler för att samla in HTTP-trafik
Fiddler är en webbfelsökningsproxy och används för att felsöka HTTP(S)-problem. Den registrerar varje HTTP-begäran som datorn gör och registrerar allt som är associerat med den. Att upptäcka problem med slutanvändarautentisering för dina HTTPS-appar ger bättre produktivitet och effektivitet för dina HoloLens 2 användningsfall. 

#### <a name="prerequisites"></a>Förutsättningar
 
- HoloLens 2 enheter och din dator måste finnas i samma nätverk
- Anteckna IP-adressen för din dator

#### <a name="install-and-configure-fiddler"></a>Installera och konfigurera Fiddler

1. Installera och [starta](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) Fiddler på datorn.  
1. På datorn – konfigurera Fiddler så att fjärrdatorer kan ansluta.
    1. Gå till Fiddler Inställningar -> Anslutningar
    1. Observera lyssningsporten för Fiddler (standard är 8866)
    1. Markera Tillåt att fjärrdatorer ansluter
    1. Klicka på Spara
3. På din HoloLens 2 – konfigurera Fiddler som proxyserver<sup>1</sup>:
    1. Öppna Start-menyn och välj Inställningar
    1. Välj Nätverk & Internet och sedan Proxy på den vänstra menyn
    1. Rulla ned till Manuell proxyinstallation och växla Använd en proxyserver till På
    1. Ange IP-adressen för den dator där Fiddler är installerat
    1. Ange det portnummer som anges ovan (standard är 8866)
    1. Klicka på Spara

<sup>1</sup> För versioner 20279.1006+ (Insiders och den kommande versionen) använder du följande steg för att konfigurera proxy:
1. Öppna Start-menyn och gå till sidan Wi-Fi i nätverkets egenskaper 
1. Rulla ned till Proxy
1. Ändra till manuell installation
1. Ange IP-adressen för den dator där Fiddler är installerat
1. Ange det portnummer som anges ovan. (standardvärdet är 8866)
1. Klicka på Använd
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Dekryptera HTTPS-trafik från HoloLens 2

1. På datorn – exportera Fiddler-certifikatet.
    1. Gå till Fiddler Inställningar -> HTTPS och expandera Avancerat Inställningar
    2. Klicka på Exportera Fiddler-certifikat. Den sparas på skrivbordet
    3. Flytta certifikatet till mappen Hämtade filer på din HoloLens 2

2.  På din HoloLens 2 – importera Fiddler-certifikatet.
    1. Gå till Inställningar -> Update and Security -> Certificates
    2. Klicka på Installera certifikat, bläddra till mappen Hämtade filer och välj Fiddler-certifikatet
    3. Ändra Butiksplats till Lokal dator
    4. Ändra certifikatarkiv till rot
    5. Välj Installera
    6. Bekräfta att certifikatet visas i listan över certifikat. Om inte, upprepa stegen ovan

#### <a name="inspect-https-sessions"></a>Granska HTTP(S)-sessioner

På datorn visar Fiddler de HoloLens två live-HTTP(S)-sessionerna. Kontrollpanelen i Fiddler kan visa HTTP(S)-begäran/-svar i olika vyer– till exempel visar vyn "Raw" raw-begäran eller -svaret i oformaterad text. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurera Wireshark för att samla in nätverkstrafik
Wireshark är ett analysverktyg för nätverksprotokoll och används för att inspektera TCP/UDP-trafik från och till dina HoloLens 2 enheter. Detta gör det enkelt att identifiera vilken trafik som passerar ditt nätverk till din HoloLens 2, hur mycket av den, hur ofta, hur lång svarstid det är mellan vissa hopp och så vidare.

#### <a name="prerequisites"></a>Krav:
- Datorn måste ha Internetåtkomst och stöd för Internetdelning via Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Installera och konfigurera Wireshark
1. På datorn – installera [Wireshark](https://www.wireshark.org/#download) 
1. På datorn – aktivera Mobil hotspot för att dela din Internetanslutning från Wi-Fi.
1. Starta Wireshark på datorn och samla in trafik från gränssnittet för mobil hotspot. 
1. På din HoloLens 2 – ändra Wi-Fi till datorns surfpunkt för mobil. HoloLens 2 IP-trafik visas i Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analysera Wireshark-loggar
Wireshark-filter kan hjälpa till att filtrera bort intressepaket. 

Kolla in den ursprungliga [bloggen](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Tillbaka till listan](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Det går inte att logga in på en tidigare HoloLens enhet

Om enheten tidigare har ställts in för någon annan, antingen för en klient eller för en tidigare anställd och du [](/intune/remote-actions/devices-wipe) inte har lösenordet för att låsa upp enheten, kan du använda Intune för att fjärrensa enheten. Enheten tar sedan på sig själv igen.  
> [!IMPORTANT]
> När du rensar enheten ska du lämna **Behåll registreringstillstånd och användarkonto** avmarkerat.

[Tillbaka till listan](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Det går inte att logga in efter uppdatering till Windows Holographic 21H1

### <a name="symptoms"></a>Symtom
- Det går inte att använda PIN-kod för inloggning när rätt PIN-kod har angetts.
- Användning av metoden för webbinloggning misslyckas när du har loggat in på webbsidan.
- Enheten visas inte som "Azure AD-ansluten" [i Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.

### <a name="cause"></a>Orsak
Den påverkade enheten kan ha tagits bort från Azure AD-klientorganisationen. Detta kan till exempel inträffa eftersom:

- En administratör eller användare har tagit bort enheten i Azure Portal eller med hjälp av PowerShell.
- Enheten har tagits bort från Azure AD-klientorganisationen på grund av inaktivitet. För en effektivt hanterad miljö rekommenderar vi vanligtvis att IT-administratörer tar bort [inaktuella, inaktiva enheter från sin Azure AD-klientorganisation.](/azure/active-directory/devices/manage-stale-devices)

När en enhet som påverkas försöker kontakta Azure AD-klienten igen efter att den har tagits bort, kommer den inte att autentiseras med Azure AD. Den här effekten är ofta osynlig för användaren av enheten, eftersom cachelagrad inloggning via PIN-kod fortsätter att tillåta användaren att logga in.

### <a name="mitigation"></a>Åtgärd
Det finns för närvarande inget sätt att lägga till en HoloLens en enhet i Azure AD. Berörda enheter måste vara rensade omstreckade genom att följa anvisningarna för [att omstrecka enheten](hololens-recovery.md#clean-reflash-the-device).

[Tillbaka till listan](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot-felsökning

Följande artiklar kan vara en användbar resurs om du vill veta mer och felsöka Autopilot-problem, men tänk på att de här artiklarna baseras på Windows 10 Desktop och att inte all information kan gälla för HoloLens:

- [Windows Autopilot – kända problem](/mem/autopilot/known-issues)
- [Felsöka problem med registrering av Windows-enheter i Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – principkonflikter](/mem/autopilot/policy-conflicts)

[Tillbaka till listan](#list)

## <a name="managed-hololens-devices-faqs"></a>Vanliga frågor HoloLens hanterade HoloLens enheter

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kan jag använda System Center Configuration Manager (SCCM) för att hantera HoloLens enheter?

Nej. Du måste använda ett MDM-system för att hantera HoloLens enheter.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kan jag använda Active Directory Domain Services (AD DS) för HoloLens hantera användarkonton?

Nej. Du måste använda Azure Active Directory (Azure AD) för att hantera användarkonton för HoloLens enheter.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Kan HoloLens automatisk registrering i ADCS (Automated Data Capture Systems)?

Nej.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kan HoloLens delta i integrerad Windows autentisering?

Nej.

### <a name="does-hololens-support-branding"></a>Stöder HoloLens profilering?

Nej. Du kan dock komma runt det här problemet med någon av följande metoder:

- Skapa en anpassad app och aktivera [sedan Helskärmsläge](hololens-kiosk.md). Den anpassade appen kan ha varumärkesanpassad anpassning och kan starta andra appar (till exempel Remote Assist).  
- Ändra alla användarprofilbilder i Azure AD till företagets logotyp. Detta kanske dock inte är önskvärt för alla scenarier.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Vilka loggningsfunktioner erbjuder HoloLens 2?

Loggning är begränsad till spårningar som kan avbildas i utvecklings- eller felsökningsscenarier, eller telemetri som enheterna skickar till Microsoft-servrar.

## <a name="questions-about-securing-hololens-devices"></a>Frågor om att skydda HoloLens enheter

Se [vår HoloLens 2 säkerhetsinformation](security-overview.md).
För HoloLens första generationens enheter kan du läsa dessa [vanliga frågor och svar.](hololens1-faq-security.yml)

[Tillbaka till listan](#list)
