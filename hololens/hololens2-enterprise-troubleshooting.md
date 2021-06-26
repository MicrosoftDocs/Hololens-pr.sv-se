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
# <a name="troubleshooting-implementation-and-managed-devices"></a>Felsökning av implementering och hanterade enheter 

Den här artikeln beskriver hur du löser flera problem eller besvarar frågor om implementering och hantering av HoloLens 2.

>[!IMPORTANT]
> Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt. Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.


<a id="list"></a>
- [EAP-felsökning](#eap-troubleshooting)
- [Felsökning av Wi-Fi](#wi-fi-troubleshooting)
- [Felsökning av nätverk](#network-troubleshooting)
- [Det går inte att logga in på en tidigare konfigurerad HoloLens-enhet](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Det går inte att logga in efter uppdatering till Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot-felsökning](#autopilot-troubleshooting)
- [Vanliga frågor och svar om Hanterade HoloLens-enheter](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP-felsökning
1. Dubbel kontroll Wi-Fi profilen har rätt inställningar:
    - EAP-typen är korrekt konfigurerad, vanliga EAP-typer: EAP-TLS (13), EAP-TTLS (21) och PEAP (25).
    - Wi-Fi SSID-namnet är rätt och matchar med HEX-strängen.
    - För EAP-TLS innehåller TrustedRootCA SHA-1-hashen för serverns betrodda rotcertifikatutfärdare. På Windows PC-kommandot "certutil.exe -dump cert_file_name" visas certifikatets SHA-1-hashsträng.
2. Samla in infångade nätverkspaket på åtkomstpunkten, kontrollanten eller AAA-serverloggarna för att ta reda på var EAP-sessionen misslyckas.
    - Om den EAP-identitet som tillhandahålls av HoloLens inte förväntas kontrollerar du om identiteten har etablerats korrekt via Wi-Fi profil eller klientcertifikat.
    - Om servern avvisar HoloLens-klientcertifikatet kontrollerar du om det nödvändiga klientcertifikatet har etablerats på enheten.
    - Om HoloLens avvisar servercertifikat kontrollerar du om serverns rotcertifikatutfärdare har etablerats på HoloLens.
3. Om företagsprofilen etableras via Wi-Fi kan du använda etableringspaketet på en Windows 10 dator. Om det även misslyckas på en Windows 10 dator följer du felsökningsguiden för Windows-klient 802.1X-autentisering.
4. Skicka feedback via Feedbackhubben.

[Tillbaka till listan](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi felsökning

Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:

1. Kontrollera att Wi-Fi är aktiverat. Du kan kontrollera det genom att använda gesten Start och sedan välja Inställningar > Nätverk & Internet > Wi-Fi. Om Wi-Fi är på kan du prova att stänga av det och sedan på igen.
2. Flytta datorn närmare routern eller åtkomstpunkten.
3. Starta om Wi-Fi router och starta sedan om HoloLens. Försök att ansluta igen.
4. Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran. Du hittar den här informationen på tillverkarens webbplats.

När du loggar in på ett företags- eller organisationskonto på enheten kan den även använda MDM-principen (Mobile Enhetshantering), om principen har konfigurerats av IT-administratören.

## <a name="network-troubleshooting"></a>Felsökning av nätverk
Om nätverksproblem är ett hinder för att distribuera och använda HoloLens 2 i din organisation kan du lära dig hur två välkända diagnostiska verktyg för nätverk, Fiddler och Wireshark, kan hjälpa dig att genomsöka, diagnostisera och identifiera problem. Mer information finns [i](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) den här bloggen.

[Tillbaka till listan](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Det går inte att logga in på en tidigare konfigurerad HoloLens-enhet

Om enheten tidigare har ställts in för någon annan, antingen för en klient eller för en tidigare anställd och du [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) inte har lösenordet för att låsa upp enheten, kan du använda Intune för att fjärrensa enheten. Enheten blinkar sedan igen.  
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

- En administratör eller användare har tagit bort enheten i Azure Portal med hjälp av PowerShell.
- Enheten har tagits bort från Azure AD-klientorganisationen på grund av inaktivitet. För en effektivt hanterad miljö rekommenderar vi vanligtvis ATT IT-administratörer tar bort [inaktuella, inaktiva enheter från sin Azure AD-klientorganisation.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

När en enhet som påverkas försöker kontakta Azure AD-klienten igen efter att den har tagits bort kan den inte autentiseras med Azure AD. Den här effekten är ofta osynlig för användaren av enheten, eftersom cachelagrad inloggning via PIN-kod fortsätter att tillåta användaren att logga in.

### <a name="mitigation"></a>Åtgärd
Det finns för närvarande inget sätt att lägga till en borttagna HoloLens-enhet i Azure AD. Berörda enheter måste vara rensade omstreckade genom att följa anvisningarna för [att omsnedstrecka enheten](hololens-recovery.md#clean-reflash-the-device).

## <a name="autopilot-troubleshooting"></a>Autopilot-felsökning

Följande artiklar kan vara en användbar resurs om du vill veta mer och felsöka Autopilot-problem, men tänk på att de här artiklarna baseras på Windows 10 Desktop och all information kan inte gälla HoloLens:

- [Windows Autopilot – kända problem](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Felsöka problem med registrering av Windows-enheter i Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Principkonflikter](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Vanliga frågor och svar om Hanterade HoloLens-enheter

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kan jag använda System Center Konfigurationshanteraren (SCCM) för att hantera HoloLens-enheter?

Nej. Du måste använda ett MDM-system för att hantera HoloLens-enheter.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kan jag använda Active Directory Domain Services (AD DS) för att hantera HoloLens-användarkonton?

Nej. Du måste använda Azure Active Directory (Azure AD) för att hantera användarkonton för HoloLens-enheter.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Kan HoloLens automatisk registrering av DATA Capture Systems (ADCS)?

Nej.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kan HoloLens delta i Integrerad Windows-autentisering?

Nej.

### <a name="does-hololens-support-branding"></a>Stöder HoloLens varumärkesyttning?

Nej. Du kan dock komma runt det här problemet med någon av följande metoder:

- Skapa en anpassad app och aktivera [sedan Helskärmsläge](hololens-kiosk.md). Den anpassade appen kan ha varumärkesanpassad anpassning och kan starta andra appar (till exempel Remote Assist).  
- Ändra alla användarprofilbilder i Azure AD till företagets logotyp. Detta kanske dock inte är önskvärt för alla scenarier.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Vilka loggningsfunktioner erbjuder HoloLens 2?

Loggning är begränsad till spårningar som kan avbildas i utvecklings- eller felsökningsscenarier, eller telemetri som enheterna skickar till Microsoft-servrar.

## <a name="questions-about-securing-hololens-devices"></a>Frågor om att skydda HoloLens-enheter

Se [vår HoloLens 2-säkerhetsinformation.](security-overview.md)
För HoloLens 1st Gen-enheter kan du läsa dessa [vanliga frågor och svar.](hololens1-faq-security.md)

[Tillbaka till listan](#list)
