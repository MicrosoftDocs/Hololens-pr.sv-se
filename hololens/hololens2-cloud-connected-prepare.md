---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Förbereda
description: Lär dig hur du förbereder dig för att registrera HoloLens-enheter i ett molnanslutet nätverk med Azure Active Directory och identitetshantering.
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378782"
---
# <a name="prepare---cloud-connected-guide"></a>Förbereda – Molnansluten guide

I slutet av den här artikeln kommer du att ha ställt in Azure AD, MDM och förstå mer om hur du använder Azure AD-konton och nätverkskrav. Det här avsnittet av guiden hjälper dig och din organisation att förbereda distributionen av HoloLens 2 till molnet och använda Dynamics 365 Remote Assist. Den kommer att gå igenom vikten av varje del av infrastrukturen samt tillhandahålla länkar till guider som hjälper dig att konfigurera dessa delar efter behov.

## <a name="infrastructure-essentials"></a>Information om infrastruktur

För både personliga och företagsdistributionsscenarier är ett MDM-system den grundläggande infrastruktur som krävs för att distribuera och hantera Windows 10 Holographic enheter. En Azure AD Premium-prenumeration rekommenderas som identitetsprovider och krävs för att stödja vissa funktioner.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD är en molnbaserad katalogtjänst som tillhandahåller identitets- och åtkomsthantering. Organisationer som använder Microsoft Office 365 eller Intune använder redan Azure AD, som har tre utgåvor: Kostnadsfri, Premium P1 och Premium P2 (se [Azure Active Directory utgåvor](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Alla utgåvor stöder Azure AD-enhetsregistrering, men Premium P1 krävs för att aktivera automatisk MDM-registrering som vi kommer att använda i den här guiden senare.

> [!IMPORTANT]
> Det är viktigt att ha Azure Active Directory eftersom HoloLens-enheter inte stöder lokal AD-anslutning. Om du inte&#39;en ny klientorganisation Azure Active Directory du följa anvisningarna i den här länken för att komma igång och skapa en [ny klient i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identitetshantering

Anställda kan bara använda ett konto för att initiera en enhet så&#39;är viktigt att din organisation kontrollerar vilket konto som aktiveras först. Det valda kontot avgör vem som styr enheten och påverkar dina hanteringsfunktioner.

I den här guiden har vi valt att [för](https://docs.microsoft.com/hololens/hololens-identity) den identitet som används ska vi använda Azure AD-konton eller Azure Active Directory-konton. Det finns flera fördelar med Azure AD-konton som vi vill använda, till exempel:

- Anställda använder sitt Azure AD-konto för att registrera enheten i Azure AD och automatiskt registrera den med organisationens&#39;MDM-lösning (Azure AD+ MDM – kräver Azure AD Premium).
- Azure AD-konton [har stöd för enkel inloggning.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) När en användare loggar in på Remote Assist identifieras deras identitet från den inloggade Azure AD-användaren och användaren loggas in i appen för en smidigare upplevelse.
- Azure AD-konton har [ytterligare autentiseringsalternativ](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Förutom Iris kan inloggningsanvändare logga in från en annan enhet eller använda FIDO-säkerhetsnycklar.

### <a name="mobile-device-management"></a>Hantering av mobila enheter

Microsoft [Intune,](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)en del av Enterprise Mobility + Security, är ett molnbaserat MDM-system som hanterar enheter som är anslutna till din klientorganisation. Precis som i Office 365 använder Intune Azure AD för identitetshantering, så anställda använder samma autentiseringsuppgifter för att registrera enheter i Intune som de använder för att logga in på Office 365. Intune stöder också enheter som kör andra operativsystem, till exempel iOS och Android, för att tillhandahålla en komplett MDM-lösning. I den här guiden kommer vi&#39;fokusera på att använda Intune för att möjliggöra en molndistribution i stor skala med HoloLens 2.

> [!IMPORTANT]
> Det är viktigt att mobile-Enhetshantering. Om du inte&#39;har den konfigurerad följer du den här guiden och [kommer igång med Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Flera MDM-system stöder Windows 10 och de flesta har stöd för distributionsscenarier för personliga enheter och företagsenhet. MDM-leverantörer som stöder Windows 10 Holographic för närvarande är: AirWatch, MobileIron med flera. De flesta branschledande MDM-leverantörer stöder redan integrering med Azure AD. MdM-leverantörerna som stöder Azure AD finns i [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Nätverk

I den här konfigurationen förväntar vi oss att HoloLens 2-enheter ansluter till Internet från alla tillgängliga öppna Wi-Fi nätverk. Eftersom en användare kan behöva ändra nätverksanslutningen baserat på plats bör de lära sig att [ansluta HoloLens-enheter till Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

För Dynamics 365 Remote Assist finns det en mängd olika nätverksförhållanden, inklusive bandbredd, svarstid, jitter och paketförlust, som kan påverka din videosamtalsupplevelse. Ljud- och videosamtal kan vara möjliga i miljöer med minskad bandbredd, men du kan uppleva funktionsförsämring. När du använder Dynamics 365 Remote Assist på HoloLens måste du tänka på följande nätverkskrav:

**Minst:** 1,5 Mbit/s upp/ned krävs för videosamtal i peer-to-peer-kvalitet med upplösningen HD 1080p vid 30 mb/s.

**Optimalt:** För videosamtal i hd-kvalitet med upplösningen HD 1080p bör 4–5 Mbit/s upp/ned förväntas.

Mer information:

- [Nätverkskrav](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Rekommendationer för nätverksoptimering](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Valfritt: Anslut din HoloLens till VPN

De enheter som ansluts till den här guiden kommer att ansluta till nätverket via ett externt molnnätverk. Det kan vara så att för att få åtkomst till företagsresurser&#39;måste ansluta dina enheter via VPN. Det finns flera olika sätt att ansluta dina enheter till VPN, både där slutanvändaren kan ansluta via enhetens användargränssnitt eller enheterna kan hanteras och ta emot VPN-profilen från antingen en PPKG eller MDM. Hur du ställer in VPN beskrivs inte&#39;den här artikeln, så om du&#39;vill veta mer om de olika VPN-protokollen eller olika sätt att hantera VPN kan du gå till dessa guider för information om [HoloLens och VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Molnansluten distribution – Konfigurera](hololens2-cloud-connected-configure.md)
