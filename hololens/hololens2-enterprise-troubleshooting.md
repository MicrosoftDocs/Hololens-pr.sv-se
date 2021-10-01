---
title: HoloLens 2-implementering och felsökning av hanterade enheter
description: Felsöka HoloLens 2 enheter i en företagsmiljö
author: beelia
ms.author: v-beehanson
ms.date: 6/22/2021
ms.topic: article
keywords: felsökning
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 2e997514be5d067ce5e9bd7f3611b464d19a6fad
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364597"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Felsöka implementering och hanterade enheter

Den här artikeln beskriver hur du löser flera problem eller besvarar frågor om implementering och hantering av HoloLens 2.

>[!IMPORTANT]
> Innan du startar en felsökningsprocedur kontrollerar du att enheten debiteras **till 20 till 40 procent** av batterikapaciteten om det är möjligt. Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att verifiera batterikapaciteten utan att logga in på enheten.


<a id="list"></a>
- [EAP-felsökning](#eap-troubleshooting)
- [Felsökning av Wi-Fi](#wi-fi-troubleshooting)
- [Felsökning av nätverk](#network-troubleshooting)
- [Det går inte att logga in på en tidigare HoloLens enhet](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Det går inte att logga in efter uppdatering till Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot-felsökning](#autopilot-troubleshooting)
- [Vanliga frågor HoloLens hanterade HoloLens enheter](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP-felsökning
1. Kontrollera att Wi-Fi har rätt inställningar:
    - Konfigurera EAP-typen korrekt. Vanliga EAP-typer är EAP-TLS (13), EAP-TTLS (21) och PEAP (25).
    - Kontrollera namnet Wi-Fi SSID och se att det matchar HEX-strängen.
    - Kontrollera att TrustedRootCA för EAP-TLS innehåller SHA-1-hashen för serverns betrodda rotcertifikatutfärdarcertifikat. På Windows datorn visar kommandot "certutil.exe -dump cert_file_name" ett certifikats SHA-1-hashsträng.
2. Samla in infångade nätverkspaket på åtkomstpunkten, kontrollanten eller AAA-serverloggarna för att ta reda på var EAP-sessionen misslyckas.
    - Om EAP-identiteten som HoloLens tillhandahålls av är oväntad kontrollerar du om identiteten har etablerats korrekt via Wi-Fi profilen eller klientcertifikatet.
    - Om servern avvisar HoloLens klientcertifikatet kontrollerar du om det nödvändiga klientcertifikatet har etablerats på enheten.
    - Om HoloLens avvisar servercertifikatet kontrollerar du om serverns rotcertifikatutfärdare har etablerats på HoloLens.
3. Om företagsprofilen etableras via ett Wi-Fi kan du överväga att tillämpa etableringspaketet på en Windows 10 dator. Om det också misslyckas på Windows 10 dator följer du felsökningsguiden för Windows 802.1X-autentisering.
4. Skicka feedback via Feedbackhubben.

[Tillbaka till listan](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi felsökning

Här är några saker du kan prova om du inte kan ansluta HoloLens till ett Wi-Fi nätverk:

1. Kontrollera att Wi-Fi är aktiverat. Verifiera med hjälp av gesten Start och välj sedan Inställningar > Network & Internet > Wi-Fi. Om Wi-Fi är på kan du prova att stänga av och aktivera det igen.
2. Flytta datorn närmare routern eller åtkomstpunkten.
3. Starta om Wi-Fi routern och starta sedan om HoloLens. Försök att ansluta igen.
4. Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran. Du hittar den här informationen på tillverkarens webbplats.

När du loggar in på ett företags- eller organisationskonto på enheten kan den även tillämpa mdm-principen (Mobile Enhetshantering), om principen har konfigurerats av IT-administratören.

[Tillbaka till listan](#list)

## <a name="network-troubleshooting"></a>Felsökning av nätverk
Om nätverksproblem är ett hinder för att distribuera och använda HoloLens 2 i din organisation konfigurerar du Fiddler och/eller Wireshark för att samla in och analysera HTTP/HTTPS-trafik. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurera Fiddler för att samla in HTTP-trafik
Fiddler är en webbfelsökningsproxy och används för att felsöka HTTP(S)-problem. Den registrerar varje HTTP-begäran som datorn gör och registrerar allt som är associerat med den. Att upptäcka problem med slutanvändarautentisering för dina HTTPS-appar ger bättre produktivitet och effektivitet för ditt mål HoloLens 2 användningsfall. 

#### <a name="prerequisites"></a>Förutsättningar
 
- HoloLens 2 enheter och datorn måste finnas i samma nätverk
- Anteckna IP-adressen för din dator

#### <a name="install-and-configure-fiddler"></a>Installera och konfigurera Fiddler

1. På datorn – [installera och](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) starta Fiddler.  
1. På datorn – konfigurera Fiddler så att fjärrdatorer kan ansluta.
    1. Gå till Fiddler Inställningar -> Anslutningar.
    1. Observera lyssningsporten för Fiddler (standard är 8866).
    1. Markera Tillåt att fjärrdatorer ansluter.
    1. Klicka på Spara.
3. På din HoloLens 2 – konfigurera Fiddler som proxyserver<sup>1:</sup>
    1. Öppna Start-menyn och välj Inställningar.
    1. Välj Network & Internet (Nätverk och sedan Proxy) på den vänstra menyn.
    1. Rulla ned till Manuell proxykonfiguration och växla Använd en proxyserver till På.
    1. Ange IP-adressen för den dator där Fiddler är installerat.
    1. Ange det portnummer som anges ovan (standard är 8866).
    1. Klicka på Spara.

<sup>1</sup> För versioner 20279.1006+ (Insiders och den kommande versionen) använder du följande steg för att konfigurera proxy:
1. Öppna Start-menyn och gå till Wi-Fi nätverkets egenskapssida. 
1. Rulla ned till Proxy.
1. Ändra till Manuell installation.
1. Ange IP-adressen för den dator där Fiddler är installerat.
1. Ange det portnummer som anges ovan (standard är 8866).
1. Klicka på Använd.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Dekryptera HTTPS-trafik från HoloLens 2

1. På datorn – exportera Fiddler-certifikatet.
    1. Gå till Fiddler Inställningar -> HTTPS och expandera Avancerat Inställningar.
    2. Klicka på Exportera Fiddler-certifikat. Den sparas på skrivbordet.
    3. Flytta certifikatet till mappen Hämtade filer på din HoloLens 2.

2.  På din HoloLens 2 – importera Fiddler-certifikatet.
    1. Gå till Inställningar -> Update and Security -> Certificates (-> Update and Security -> Certificates.
    2. Klicka på Installera certifikat, bläddra till mappen Hämtade filer och välj Fiddler-certifikatet.
    3. Ändra Lagringsplats till Lokal dator.
    4. Ändra Certifikatarkiv till rot.
    5. Välj installera.
    6. Bekräfta att certifikatet visas i listan över certifikat. Om inte upprepar du dessa steg.

#### <a name="inspect-https-sessions"></a>Granska HTTP(S)-sessioner

På din dator visar Fiddler HoloLens 2:s live-HTTP(S)-sessioner. Kontrollpanelen i Fiddler kan visa HTTP(S)-begäran/-svar i olika vyer. Till exempel visar vyn "Raw" rå begäran eller svar i oformaterad text. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurera Wireshark för att samla in nätverkstrafik
Wireshark är ett analysverktyg för nätverksprotokoll som används för att inspektera TCP/UDP-trafik till och från dina HoloLens 2-enheter. Detta gör det enkelt att identifiera den trafik som passerar nätverket till din HoloLens 2 – hur mycket det finns, dess frekvens, hur lång svarstid det är mellan vissa hopp och så vidare.

#### <a name="prerequisites"></a>Krav:
- Datorn måste ha Internetåtkomst och stöd för Internetdelning via Wi-Fi.

#### <a name="install-and-configure-wireshark"></a>Installera och konfigurera Wireshark
1. På datorn – installera [Wireshark](https://www.wireshark.org/#download).
1. På datorn – aktivera Mobil hotspot för att dela din Internetanslutning från Wi-Fi.
1. Starta Wireshark på datorn och samla in trafik från gränssnittet för mobil hotspot. 
1. På din HoloLens 2 – ändra dess Wi-Fi till datorns mobila surfpunkt. HoloLens 2 IP-trafik visas i Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analysera Wireshark-loggar
Wireshark-filter kan hjälpa till att filtrera bort intressepaket. 

Kolla in den ursprungliga [bloggen](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Tillbaka till listan](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Det går inte att logga in på en tidigare HoloLens enhet

Om enheten tidigare har ställts in för någon annan, antingen för en klient eller för en tidigare anställd och du [](/intune/remote-actions/devices-wipe) inte har lösenordet för att låsa upp enheten, kan du använda Intune för att fjärrensa enheten. Enheten blinkar sedan igen.  
> [!IMPORTANT]
> När du rensar enheten ska du lämna **Behåll registreringstillstånd och användarkonto** avmarkerat.

[Tillbaka till listan](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Det går inte att logga in efter uppdatering till Windows Holographic 21H1

### <a name="symptoms"></a>Symtom
- Det går inte att använda PIN-kod för inloggning när rätt PIN-kod har angetts.
- Användning av metoden för webbinloggning misslyckas när du har loggat in på webbsidan.
- Enheten visas inte som "Azure AD-ansluten" [i Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Enheter.

### <a name="cause"></a>Orsak
Den påverkade enheten kan ha tagits bort från Azure AD-klientorganisationen. Detta kan till exempel inträffa eftersom:

- En administratör eller användare har tagit bort enheten i Azure Portal eller med hjälp av PowerShell.
- Enheten togs bort från Azure AD-klientorganisationen på grund av inaktivitet. För en effektivt hanterad miljö rekommenderar vi vanligtvis ATT IT-administratörer tar bort [inaktuella, inaktiva enheter från sin Azure AD-klientorganisation.](/azure/active-directory/devices/manage-stale-devices)

När en enhet som påverkas försöker kontakta Azure AD-klienten igen efter att den har tagits bort kan den inte autentiseras med Azure AD. Den här effekten är ofta osynlig för användaren av enheten, eftersom cachelagrad inloggning via PIN-kod fortsätter att tillåta användaren att logga in.

### <a name="mitigation"></a>Åtgärd
Det finns för närvarande inget sätt att lägga till HoloLens borttagna enheter i Azure AD. Berörda enheter måste vara rensade omstreckade genom att följa anvisningarna om [att omsnedstrecka enheten](hololens-recovery.md#clean-reflash-the-device).

[Tillbaka till listan](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot-felsökning

Följande artiklar kan vara en användbar resurs där du kan läsa mer och felsöka Autopilot-problem. Artiklarna baseras dock på Windows 10 Desktop och all information kan inte gälla för HoloLens:

- [Windows Autopilot – kända problem](/mem/autopilot/known-issues)
- [Felsöka problem med registrering av Windows-enheter i Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – principkonflikter](/mem/autopilot/policy-conflicts)

[Tillbaka till listan](#list)

## <a name="managed-hololens-devices-faqs"></a>Vanliga frågor och svar HoloLens hanterade HoloLens enheter

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kan jag använda System Center Configuration Manager (SCCM) för att hantera HoloLens enheter?

Nej. Du måste använda ett MDM-system för att hantera HoloLens enheter.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kan jag använda Active Directory Domain Services (AD DS) för att HoloLens hantera användarkonton?

Nej. Du måste använda Azure Active Directory (Azure AD) för att hantera användarkonton för HoloLens enheter.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Kan HoloLens automatisk registrering i ADCS (Data Capture Systems)?

Nej.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kan HoloLens delta i integrerad Windows autentisering?

Nej.

### <a name="does-hololens-support-branding"></a>Stöder HoloLens profilering?

Nej. Men du kan komma runt det här problemet med någon av följande metoder:

- Skapa en anpassad app och aktivera [sedan Helskärmsläge](hololens-kiosk.md). Den anpassade appen kan ha varumärkesanpassad anpassning och kan starta andra appar (till exempel Remote Assist).  
- Ändra alla användarprofilbilder i Azure AD till företagets logotyp. Detta kanske dock inte är önskvärt för alla scenarier.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Vilka loggningsfunktioner erbjuder HoloLens 2?

Loggning är begränsad till spårningar som kan avbildas i utvecklings- eller felsökningsscenarier, eller telemetri som enheterna skickar till Microsoft-servrar.

## <a name="questions-about-securing-hololens-devices"></a>Frågor om att skydda HoloLens enheter

Se [vår HoloLens 2-säkerhetsinformation](security-overview.md).
För HoloLens första generationens enheter kan du läsa dessa [vanliga frågor och svar.](hololens1-faq-security.yml)

[Tillbaka till listan](#list)
