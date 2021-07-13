---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Förbereda
description: Lär dig hur du förbereder för att HoloLens enheter över ett molnanslutet nätverk med hjälp av Azure Active Directory och identitetshantering.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Enhetshantering
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639666"
---
# <a name="prepare---cloud-connected-guide"></a>Förbereda – Molnansluten guide

I slutet av den här artikeln kommer du att ha ställt in Azure AD, MDM och förstå mer om hur du använder Azure AD-konton och nätverkskrav. Det här avsnittet av guiden hjälper dig och din organisation att förbereda distributionen HoloLens 2 till molnet och använda Dynamics 365 Remote Assist. Den kommer att gå igenom vikten av varje del av infrastrukturen samt tillhandahålla länkar till guider som hjälper dig att konfigurera dessa delar efter behov.

## <a name="infrastructure-essentials"></a>Infrastruktur essentials

För både personliga distributionsscenarier och företagsdistributionsscenarier är ett MDM-system den grundläggande infrastruktur som krävs för att distribuera och hantera Windows 10 Holographic enheter. En Azure AD Premium-prenumeration rekommenderas som identitetsprovider och krävs för att stödja vissa funktioner.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD är en molnbaserad katalogtjänst som tillhandahåller identitets- och åtkomsthantering. Organisationer som använder Microsoft Office 365 eller Intune använder redan Azure AD, som har tre utgåvor: Kostnadsfri, Premium P1 och Premium P2 (se [Azure Active Directory-versioner](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Alla utgåvor stöder Azure AD-enhetsregistrering, men Premium P1 krävs för att aktivera automatisk MDM-registrering som vi kommer att använda i den här guiden senare.

> [!IMPORTANT]
> Det är viktigt att ha en Azure Active Directory eftersom HoloLens enheter inte stöder lokal AD-anslutning. Om du inte&#39;har en Azure Active Directory kan du gå till [Skapa en ny klientorganisation i Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identitetshantering

Anställda kan bara använda ett konto för att initiera en enhet, så det&#39;viktigt att din organisation styr vilket konto som aktiveras först. Det valda kontot avgör vem som styr enheten och påverkar dina hanteringsfunktioner.

I den här guiden har vi valt att för den [identitet som](/hololens/hololens-identity) används ska vi använda Azure AD-konton eller Azure Active Directory konton. Det finns flera fördelar med Azure AD-konton som vi vill använda, till exempel:

- Anställda använder sitt Azure AD-konto för att registrera enheten i Azure AD och automatiskt registrera den med organisationens MDM-lösning&#39;(Azure AD+MDM – kräver Azure AD Premium).
- Azure AD-konton [stöder enkel inloggning.](/azure/active-directory/manage-apps/what-is-single-sign-on) När en användare loggar in på Remote Assist identifieras deras identitet från den inloggade Azure AD-användaren och användaren loggas in i appen för en smidigare upplevelse.
- Azure AD-konton har [ytterligare autentiseringsalternativ](/hololens/hololens-identity) via [Windows Hello för företag](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Förutom Iris-inloggning kan användare logga in från en annan enhet eller använda FIDO-säkerhetsnycklar.

### <a name="mobile-device-management"></a>Hantering av mobila enheter

Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), en del av Enterprise Mobility + Security, är ett molnbaserat MDM-system som hanterar enheter som är anslutna till din klientorganisation. Precis Office 365 använder Intune Azure AD för identitetshantering, så anställda använder samma autentiseringsuppgifter för att registrera enheter i Intune som de använder för att logga in på Office 365. Intune stöder också enheter som kör andra operativsystem, till exempel iOS och Android, för att tillhandahålla en komplett MDM-lösning. I den här guiden kommer vi&#39;fokusera på att använda Intune för att möjliggöra en molndistribution i stor skala med HoloLens 2.

> [!IMPORTANT]
> Det är viktigt att ha Mobile Enhetshantering. Om du inte&#39;har den konfigurerad följer du den här guiden och [kom igång med Intune.](/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Flera MDM-system stöder Windows 10 och de flesta stöder distributionsscenarier för personliga enheter och företagsenhet. MDM-leverantörer som stöder Windows 10 Holographic för närvarande är: AirWatch, MobileIron med flera. De flesta branschledande MDM-leverantörer stöder redan integrering med Azure AD. Du hittar MDM-leverantörerna som stöder Azure AD i [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Nätverk

I den här konfigurationen förväntar vi HoloLens 2 enheter som ansluter till Internet från alla tillgängliga öppna Wi-Fi nätverk. Eftersom en användare kan behöva ändra nätverksanslutningen baserat på plats bör de lära sig att [ansluta HoloLens enheter till Wi-Fi.](/hololens/hololens-network)

För Dynamics 365 Remote Assist finns det en mängd olika nätverksförhållanden, inklusive bandbredd, svarstid, jitter och paketförlust, som kan påverka din videosamtalsupplevelse. Ljud- och videosamtal kan vara möjliga i miljöer med minskad bandbredd, men du kan uppleva funktionsförsämring. När du använder Dynamics 365 Remote Assist HoloLens här är nätverkskraven som du bör tänka på:

**Minst:** 1,5 Mbit/s upp/ned krävs för videosamtal i hd-kvalitet med en upplösning på 1 080p vid 30 mb/s.

**Optimal:** För videosamtal i hd-kvalitet med en upplösning på HD 1080p bör 4-5 Mbit/s upp/ned förväntas.

Mer information:

- [Nätverkskrav](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Rekommendationer för nätverksoptimering](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Valfritt: Anslut din HoloLens till VPN

De enheter som ansluts till den här guiden kommer att ansluta till nätverket via och externa molnnätverk. Det kan vara så att för att få åtkomst till företagsresurser&#39;du behöva ansluta dina enheter via VPN. Det finns flera olika sätt att ansluta dina enheter till VPN, både där slutanvändaren kan ansluta via enhetens användargränssnitt eller enheterna kan hanteras och ta emot VPN-profilen från antingen en PPKG eller MDM. Hur du ställer in VPN tas inte upp&#39;den här artikeln, så om du&#39;vill veta mer om de olika VPN-protokollen eller olika sätt att hantera VPN kan du gå till dessa guider för [information om HoloLens och VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Molnansluten distribution – Konfigurera](hololens2-cloud-connected-configure.md)
