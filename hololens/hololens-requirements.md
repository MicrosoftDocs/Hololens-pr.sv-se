---
title: Konfigurera HoloLens i en kommersiell miljö
description: Läs mer om att distribuera och hantera HoloLens i företagsmiljöer, inklusive infrastruktur, Azure Active Directory och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378824"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>Distribution och hantering av HoloLens 2-företag

Den här översikten är avsedd att hjälpa IT-proffs att förstå överväganden för att distribuera Microsoft HoloLens hantera enheter inom företaget.

HoloLens 2 körs på Windows 10 Holographic som ger organisationer robusta, flexibla, inbyggda tekniker för hantering av mobila enheter och appar. Windows 10 Holographic har stöd för livscykelhantering från hela enheten för att ge företag kontroll över sina enheter, data och appar. HoloLens 2 kan enkelt införlivas i standardmetoder för livscykeln, från enhetsregistrering, konfiguration och programhantering till underhåll och tillbakatagning med hjälp av en omfattande lösning för hantering av mobila enheter.

## <a name="prepare"></a>Förbereda

När du förbereder distributionen av HoloLens 2 till företagets företagsmiljö finns det flera överväganden som du bör granska och förstå när du börjar planera för skalningsdistributioner av HoloLens 2.

### <a name="infrastructure-essentials"></a>Information om infrastruktur

För HoloLens 2 i ett företagsdistributionsscenario finns det vissa viktiga infrastrukturtjänster som krävs för att stödja en fullständig uppsättning funktioner. HoloLens 2 har skapats med [Modern Mobile Enhetshantering](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) i åtanke för distribution och hantering. Med Azure AD Join + MDM som det främsta sättet att uppnå detta på en allt större mobil arbetsstyrka. Avsnitten nedan ger en kort översikt över varje infrastrukturkomponent som bör beaktas i din distributionsplanering för HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD är en molnbaserad katalogtjänst som tillhandahåller identitets- och åtkomsthantering. Du kan integrera den med befintliga lokala kataloger för att skapa en hybrididentitetslösning. Organisationer som använder Microsoft Office 365 eller Intune använder redan Azure AD, som har tre utgåvor: Kostnadsfri, Premium P1 och Premium P2 (se [Azure Active Directory versioner](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Alla utgåvor stöder Azure AD-enhetsregistrering, men Premium P1 krävs för att aktivera automatisk MDM-registrering. HoloLens 2 kräver Azure Active Directory Join för att aktivera de flesta funktioner på företagsnivå.

> [!NOTE]
> Lokal Active Directory-anslutning stöds inte på HoloLens 2.

### <a name="mobile-device-management"></a>Hantering av mobila enheter
HoloLens 2 är speciellt utformat för att hanteras av MDM Enhetshantering system (Mobile Enhetshantering) i en företagsmiljö. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), en del Enterprise Mobility + Security, är ett molnbaserat MDM-system som hanterar enheter i företaget. Precis som i Office 365 använder Intune Azure AD för identitetshantering, så anställda använder samma autentiseringsuppgifter för att registrera enheter i Intune som de använder för att logga in på Office 365. Flera MDM-system stöder Windows 10 och de flesta har stöd för distributionsscenarier för personliga enheter och företagsenhet. MDM-system kan också hantera programdistributioner och uppdateringar för HoloLens 2 också. Andra MDM-leverantörer som stöder HoloLens 2 är för närvarande: AirWatch, MobileIron med flera. Alla MDM-systemleverantörer har samma åtkomst till Windows 10 CSP:er (Device Management Configuration Service), vilket ger IT-organisationer friheten att välja det system som bäst passar deras hanteringskrav, oavsett om det är Microsoft Intune eller en MDM-produkt från tredje part.

> [!NOTE]
> Traditionella lokala pc-hanteringssystem som System Center Konfigurationshanteraren stöds inte på HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update för företag
Microsoft har Windows Update för företag för att ge IT-administratörer ytterligare Windows Update-centrerade hanteringsfunktioner, till exempel möjligheten att distribuera uppdateringar till grupper av enheter och definiera underhållsfönster för installation av uppdateringar. Mer information [om hur du hanterar HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 2-uppdateringar finns i dokumentationen om HoloLens-uppdateringar.

### <a name="certificates"></a>Certifikat
HoloLens 2 stöder distribution av certifikat via MDM om din miljö kräver certifikat för Corp Wi-Fi nätverksautentisering eller åtkomst till andra resurser. Vissa MDM-infrastrukturkonfigurationer kan krävas för att aktivera certifikatdistributioner till HoloLens 2. Läs om hur du [förbereder certifikat och nätverksprofiler för HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Om du använder Intune kan du läsa [certifieringskonfigurationsinformationen.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Konfigurera

MDM-administratörer kan definiera och implementera principinställningar på alla företagsenhet som har registrerats i ett MDM-system. Vilka konfigurationsinställningar du använder varierar beroende på distributionsscenariot. I Windows 10 är CSP:er (Configuration Service Providers) ett gränssnitt för att läsa, ange, ändra eller ta bort konfigurationsinställningar på enheten. De här inställningarna mappar till registernycklar eller filer. Mer information om hur Windows 10 CPS för HoloLens 2 finns i den fullständiga listan över CPS som stöds i [HoloLens-enheter.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 stöder också inställning av en begränsad uppsättning CSP-konfigurationer via anpassade etableringspaket. Etableringspaket används vanligtvis för icke-MDM-hanterade enheter och måste tillämpas manuellt på varje enhet. Mer information [om hur du skapar anpassade etableringspaket](https://docs.microsoft.com/hololens/hololens-provisioning) finns i HoloLens-etableringsdokumentationen.

> [!NOTE]
> HoloLens 2 stöder [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), vilket ger en enkel process för att hantera företagets Windows 10 enhetskonfigurationer.

### <a name="identity-management"></a>Identitetshantering

Anställda kan bara använda ett konto för att initiera en enhet så&#39;är viktigt att din organisation kontrollerar vilket konto som aktiveras först. Det valda kontot avgör vem som styr enheten och påverkar dina hanteringsfunktioner. HoloLens 2 stöder tre kontotyper: lokalt användarkonto, personligt Microsoft-konto och Azure Active Directory konton. Vi rekommenderar starkt att du Azure Active Directory identitetshanteringslösningen för företag, eftersom den ger tillgång till alla funktioner på dina HoloLens 2-enheter. Kolla in [HoloLens-identitet](https://docs.microsoft.com/hololens/hololens-identity) för mer information om identiteter för HoloLens 2.

### <a name="network-and-connectivity"></a>Nätverk och anslutning

Eftersom HoloLens 2 är en moln först-enhet krävs nätverksåtkomst till onlineresurser för att fullständiga funktioner och funktioner ska bli tillgängliga. Om du distribuerar HoloLens 2-enheter med anslutning till företagets intranätnätverk kan du behöva uppdatera proxy-/brandväggsreglerna för att tillåta åtkomst till HoloLens 2-molntjänster. Mer information finns i listan över vanliga [slutpunkter för HoloLens 2-operativsystemet](https://docs.microsoft.com/hololens/hololens-offline). Åtkomst till ytterligare slutpunkter kan krävas för att program eller andra molntjänster ska kunna köras på HoloLens 2.

Några vanliga HoloLens 2-tjänster som kräver ytterligare slutpunktsåtkomst är följande:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365-guider](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams-infrastruktur)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Certifikatdistribution

Om certifikat krävs för åtkomst till företagsnätverk Wi-Fi eller andra tjänster i din organisation stöder HoloLens 2 distribution av användar- och enhetscertifikat via MDM. Obs! DIN MDM-lösning kan kräva ytterligare infrastrukturkonfiguration för att distribuera certifikat till Windows 10 enheter.

### <a name="security-review"></a>Säkerhetsgranskning

De flesta företags IT-avdelningar kräver utvärdering och granskning av nya enheter som distribueras till ett företagsnätverk. Om din organisation behöver en säkerhetsgranskning av HoloLens 2 hittar du mer information som hjälper dig att [få säkerhetsgodkännanden.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Vanliga inställningar för HoloLens 2-enheter

När du distribuerar HoloLens 2-enheter till en företagsmiljö finns det ett antal vanliga enhetskonfigurationer som kan övervägas när du planerar distributionen av HoloLens 2. Den här listan visar konfigurationer och inställningar som är ganska vanliga och inte består av en fullständig lista över tillgängliga alternativ:

| Enhetsinställning | Kort beskrivning.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Maskinvarubegränsningar](hololens-requirements.md#hardware-restrictions)               | Maskinvarubegränsningar minskar anslutningen och hjälper till med dataskyddet.                        |
| [Wi-Fi-profiler](hololens-requirements.md#wi-fi-profiles)               | Konfigurera Wi-Fi profiler utan inblandning av användaren eller interaktion.                              |
| [Certifikat](hololens-requirements.md#certificates-1)               | Ange konto och/eller Wi-Fi autentisering, VPN-kryptering och SSL-kryptering av webbinnehåll. |
| [Proxy](hololens-requirements.md#proxy)              | Hantera intern trafik.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Kontrollera åtkomsten till appar och resurser på företagets intranät.                               |
| [Helskärmsläge](hololens-requirements.md#kiosk-mode) | Begränsar de program som visas för användare via användargränssnittet. |

#### <a name="hardware-restrictions"></a>Maskinvarubegränsningar

HoloLens 2 använder avancerad teknik som innehåller populära maskinvarufunktioner som kameror, mikrofoner, högtalare, USB-gränssnitt, Bluetooth-gränssnitt och Wi-Fi. Du kan använda maskinvarubegränsningar för att kontrollera tillgängligheten för dessa funktioner.

Nedan visas de vanligaste MDM-inställningarna som HoloLens 2 stöder för att konfigurera maskinvarubegränsningar. Vissa av dessa maskinvarubegränsningar ger anslutning och hjälp med dataskydd.

- [**Tillåt WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Om användarna kan aktivera och använda Wi-Fi radio på sina enheter
- [**Tillåt USB-anslutning:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Om USB-anslutningen är aktiverad (påverkar&#39;USB-laddning)
- [**Tillåt Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Om användarna kan aktivera och använda Bluetooth-radio på sina enheter

Läs mer om andra [vanliga enhetsbegränsningar.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Wi-Fi-profiler

De flesta Wi-Fi kräver certifikat och annan komplex information för att begränsa och skydda användaråtkomst. Den här avancerade Wi-Fi är svår för vanliga användare att konfigurera, men MDM-system kan konfigurera dessa Wi-Fi utan inblandning av användaren. Du kan skapa flera Wi-Fi profiler i MDM-systemet.

Mer information om hur Wi-Fi för Windows 10 finns i [Wi-Fi-inställningar för företagsprofil.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Certifikat

Certifikat förbättrar säkerheten genom att tillhandahålla kontoautentisering, Wi-Fi,VPN-kryptering och SSL-kryptering av webbinnehåll. Även om administratörer kan hantera certifikat på enheter manuellt via etableringspaket är det&#39;bästa praxis att använda MDM-systemet för att hantera dessa certifikat under hela livscykeln – från registrering till förnyelse och återkallning. MDM-systemet kan automatiskt distribuera dessa certifikat till enheternas&#39;-certifikatarkiv när du har registrerat enheten (så länge MDM-systemet stöder Simple Certificate Enrollment Protocol (SCEP) eller Public Key Cryptography Standards #12 (PKCS #12)). MDM kan också fråga efter och ta bort registrerade klientcertifikat eller utlösa en ny registreringsbegäran innan det aktuella certifikatet upphör att gälla.

Läs mer om hur du [förbereder certifikat och nätverksprofiler för HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

De flesta företagsnätverk i intranätet använder en proxy för att hantera intern trafik. Med HoloLens 2 kan du konfigurera en proxyserver för Ethernet och Wi-Fi anslutningar. De här inställningarna gäller inte för VPN-anslutningar.

Mer information om proxyinställningar för Windows 10 finns i [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>VPN

Organisationer använder ofta en VPN-anslutning för att styra åtkomsten till appar och resurser&#39;företagets intranät. HoloLens 2 stöder SSL VPN-anslutningar, som kräver ett nedladdningsbart plugin-program från Microsoft Store och som är specifika för den VPN-leverantör du väljer.

Mer information om VPN-profiler finns i [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Helskärmsläge

Du kan konfigurera en HoloLens 2-enhet så att den fungerar som en fast enhet, även kallad helskärmsenhet, genom att konfigurera enheten att köras i helskärmsläge. Helskärmsläge begränsar de program (eller användare) som är tillgängliga på enheten. Helskärmsläge är en praktisk funktion som du kan använda för att dedikera en HoloLens 2-enhet till företagsappar eller för att använda HoloLens 2-enheten i en appdemo.

Mer information om hur du konfigurerar en HoloLens 2 i helskärmsläge finns i [Konfigurera HoloLens som en kiosk](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Distribuera

### <a name="mdm-device-enrollment"></a>MDM-enhetsregistrering

För företagsdistributioner rekommenderar vi [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) att du endast registrerar enheter i MDM som företagsenheter med Azure AD-anslutning och automatisk MDM-registrering (Azure AD+MDM). Detta kräver Azure AD Premium stöder automatisk registrering till flera MDM-leverantörer, inklusive Intune.

Läs mer om registreringsmetoden Autopilot som distribueras [själv.](https://docs.microsoft.com/hololens/hololens2-autopilot)

### <a name="application-deployment"></a>Programdistribution

Användarproduktivitet på mobila enheter drivs ofta av appar.

Windows 10 gör det möjligt att utveckla appar som fungerar sömlöst på flera enheter med hjälp av Universell Windows-plattform (UWP) för Windows-appar.

Det finns flera sätt att distribuera program till HoloLens 2-enheter. Appar kan distribueras direkt via MDM, Microsoft Store för företag eller separat inläst via ett etableringspaket. Mer information [finns i dokumentationen för](https://docs.microsoft.com/hololens/app-deploy-overview) appdistribution.

> [!NOTE]
> HoloLens 2 stöder endast körning av UWP ARM64-appar.

## <a name="maintain"></a>Underhåll

I företags IT-miljöer måste behovet av säkerhets- och kostnadskontroll balanseras mot att ge användarna den senaste tekniken. Eftersom cyberattacker har blivit en vardaglig händelse är det viktigt att upprätthålla tillståndet för dina Windows 10 enheter. IT-it måste kontrollera konfigurationsinställningar, hålla dem från att bli inkom kompatibla och framtvinga vilka enheter som kan komma åt interna program. HoloLens 2 tillhandahåller de hanteringsfunktioner för mobilåtgärder som krävs för att säkerställa att enheterna följer företagets policy.

### <a name="os-servicing-options"></a>Servicealternativ för operativsystem

**En effektiviserad uppdateringsprocess**

Microsoft har effektiviserat Produktteknik- och lanseringscykeln i Windows så att nya funktioner, upplevelser och funktioner som efterfrågas på marknaden kan levereras snabbare än någonsin tidigare. Microsoft planerar att leverera två funktionsuppdateringar per år (12 månader). **Funktionsuppdateringar** upprättar en Current Branch eller CB och har en associerad version.

Microsoft kommer också att leverera och installera uppdateringar för säkerhet och stabilitet direkt till HoloLens 2-enheter. Dessa **kvalitetsuppdateringar,** som släpps under Microsofts kontroll via Windows Update, är tillgängliga varje månad. HoloLens 2 använder funktions- och kvalitetsuppdateringar som en del av samma standarduppdateringsprocess.

Företagskunder kan hantera uppdateringsupplevelsen och processen på HoloLens 2s med hjälp av ett MDM-system. I de flesta fall gäller principer för att hantera uppdateringsprocessen både för funktions- och kvalitetsuppdateringar. Mer information om hur [du konfigurerar MDM för HoloLens-uppdateringar](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="managing-applications"></a>Hantera program

IT-administratörer kan styra vilka appar som får installeras på HoloLens 2 och hur de ska hållas uppdaterade.

HoloLens 2 [stöder Windows Defender Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), vilket gör att administratörer kan skapa, tillåta eller inte tillåta listor över appar från Microsoft Store. Den här funktionen omfattar även inbyggda appar. Möjligheten att tillåta eller neka appar bidrar till att säkerställa att personer använder sina enheter i avsett syfte. Det är dock inte alltid en enkel metod att hitta en balans mellan vad anställda behöver eller begära och säkerhetsproblem. Att skapa listor för att tillåta eller inte tillåta kräver också att du håller dig till det föränderliga applandskapet i Microsoft Store.

Mer information finns i [CSP för programkontroll.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### <a name="retire"></a>Pensionera

Tillbakagången av enheten är den sista fasen i enhetslivscykeln. Det&#39;viktigt att enheter som ersätts med nyare modeller dras tillbaka på ett säkert sätt eftersom du inte&#39;vill att företagsdata ska finnas kvar på bortkastade enheter som kan äventyra sekretessen för dina data. IT behöver också ett sätt att ge tillräckligt stöd åt användare som behöver rensa enheter som förloras eller blir stulna.

HoloLens 2 stöder tre metoder för att ta bort enheten

**MDM-fabriksensning:** Återställer HoloLens 2 till fabriksavbildningen via administratörsinitierade MDM-kommando. Raderar alla lagrade data på enheten.

**Enhetsåterställning inifrån Inställningar:** Slutanvändare kan återställa HoloLens 2 manuellt i appen Inställningar på enheten. Raderar alla lagrade data på enheten.

**Advanced Recovery Companion (ARC):** Från en dator som kör ARC-verktyget kan en användare eller administratör flasha en HoloLens 2 som är ansluten till datorn via USB-kabel. Raderar alla lagrade data på enheten.

> [!div class="nextstepaction"]
> [Vanliga distributionsscenarier](common-scenarios.md)
