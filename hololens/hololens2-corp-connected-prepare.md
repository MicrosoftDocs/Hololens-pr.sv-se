---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – Förbereda
description: Lär dig hur du förbereder för registrering HoloLens 2 enheter över ett företagsanslutet nätverk med Dynamics 365-guider.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Enhetshantering
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 76513c2f2458119785b64d8cccac4e42c2957b5af966dfdb0c165ebeda12e069
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660069"
---
# <a name="prepare---corporate-connected-guide"></a>Förbereda – Företagsansluten guide
## <a name="infrastructure-essentials"></a>Infrastruktur essentials
För både personliga distributionsscenarier och företagsdistributionsscenarier är ett MDM-system (Mobile Enhetshantering) den grundläggande infrastruktur som krävs för att distribuera och hantera Windows 10-enheter, särskilt HoloLens 2. En [Azure AD Premium-prenumeration](/azure/active-directory/fundamentals/active-directory-get-started-premium) rekommenderas som identitetsprovider **och krävs** för att stödja vissa funktioner.

> [!NOTE]
> Även om HoloLens 2 distribueras och hanteras som en mobil enhet, används den vanligtvis som en delad enhet mellan många användare.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD är en molnbaserad katalogtjänst som tillhandahåller identitets- och åtkomsthantering. Organisationer som använder Microsoft Office 365 eller Intune använder redan Azure AD, som har tre utgåvor: Kostnadsfri, Premium P1 och Premium P2 (se [Azure Active Directory-versionerna](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Alla utgåvor stöder Azure AD-enhetsregistrering, men Premium P1 krävs för att aktivera automatisk MDM-registrering som vi kommer att använda i den här guiden senare.
> [!Important]
> Det är viktigt att ha en Azure AD eftersom HoloLens-enheter inte stöder lokal AD-anslutning. Om du inte redan har en Azure AD-konfigurerad följer du anvisningarna för att komma igång och [Skapa en ny klientorganisation i Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identitetshantering
I den här guiden är [identiteten](/hololens/hololens-identity) som används Azure AD-konton. Det finns flera fördelar med Azure AD-konton, till exempel:

- Anställda använder sitt Azure AD-konto för att registrera enheten i Azure AD och kan automatiskt registrera den med organisationens MDM-lösning (Azure AD+MDM – kräver en [Azure AD Premium prenumeration).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD-konton har [ytterligare autentiseringsalternativ](/hololens/hololens-identity) via [Windows Hello för företag](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Förutom Iris-inloggning kan användare logga in från en annan enhet eller använda FIDO-säkerhetsnycklar.

> [!WARNING] 
> Anställda kan bara använda ett konto för att initiera en enhet, så det är viktigt att **din organisation styr vilket konto som aktiveras först.** Det valda kontot avgör vem som styr enheten och påverkar dina hanteringsfunktioner.

## <a name="mobile-device-management"></a>Hantering av mobila enheter
Microsoft Intune ingår i Enterprise Mobility + Security är ett molnbaserat MDM-system som hanterar enheter som är anslutna till din klientorganisation. Precis Office 365 använder Intune Azure AD för identitetshantering, så anställda använder samma autentiseringsuppgifter för att registrera enheter i Intune som de använder för att logga in på Office 365. Intune stöder också enheter som kör andra operativsystem, till exempel iOS och Android, för att tillhandahålla en komplett MDM-lösning. I den här guiden fokuserar vi på att använda Intune för att möjliggöra en distribution till ditt interna nätverk med HoloLens 2.
> [!Important] 
> Det är viktigt att ha Mobile Enhetshantering. Om du inte redan har den konfigurerad följer du den här guiden och Kom igång med Intune.

> [!Important]
> För att kunna använda guider krävs ett Azure AD-konto.

> [!Note] 
> Flera MDM-system stöder Windows 10 och de flesta stöder distributionsscenarier för personliga enheter och företagsenhet. MDM-leverantörer som stöder Windows 10 Holographic omfattar: AirWatch, MobileIron med flera. De flesta branschledande MDM-leverantörer stöder redan integrering med Azure AD. Du hittar den senaste listan över MDM-leverantörer som stöder Azure AD i [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Nätverksåtkomst 
Dynamics 365-guider är ett molnbaserat program. Om nätverksadministratören har en lista över godkännanden kan de behöva lägga till IP-adresser och/eller slutpunkter som krävs för att ansluta till Dynamics 365-servrarna. [Läs mer om att avblockera IP-adresser och URL:er.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certifikat
Certifikat förbättrar säkerheten genom att tillhandahålla kontoautentisering, Wi-Fi,VPN-kryptering och SSL-kryptering av webbinnehåll. Även om administratörer kan hantera certifikat på enheter manuellt via etableringspaket är det bästa praxis att använda MDM-systemet för att hantera dessa certifikat under hela livscykeln – från registrering till förnyelse och återkallelse. 

MDM-systemet kan automatiskt distribuera dessa certifikat till enheternas certifikatarkiv efter att du har registrerat dem (så länge ditt MDM-system stöder **Simple Certificate Enrollment Protocol (SCEP)** eller **Public Key Cryptography Standards #12 (PKCS #12).** [Lär dig mer om certifikattyper och profiler som du använder med Microsoft Intune](/mem/intune/protect/certificates-configure). MDM kan också fråga efter och ta bort registrerade klientcertifikat eller utlösa en ny registreringsbegäran innan det aktuella certifikatet upphör att gälla.

Om MDM-systemen redan har konfigurerats för certifikat kan du gå till Förbereda certifikat och nätverksprofiler för [HoloLens 2](/hololens/hololens-certificates-network) för att börja distribuera certifikat och profiler för dina HoloLens 2-enheter.

## <a name="scep"></a>SCEP

Följande tjänster krävs för SCEP-distribution, med undantag för Web Programproxy Server.

- [Certifikatutfärdare](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES-serverroll](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Connector](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Du måste också publicera NDES-URL:en utanför företagets nätverk med [hjälp av Azure AD-programproxy eller Webbåtkomstproxy.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Du kan också använda en annan valfri omvänd proxy.

![SCEP-dataflöde](./images/hololens2-scep-info-flow.png)

Om nätverket inte redan stöder SCEP, eller om nätverket är korrekt konfigurerat för SCEP med Intune, kan du gå till Konfigurera infrastruktur för att stödja SCEP med [Intune.](/mem/intune/protect/certificates-scep-configure)

Om din infrastruktur redan stöder SCEP [](/mem/intune/protect/certificates-profile-scep) måste [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) du skapa en profil för varje SCEP-certifikat som HoloLens 2 kommer att använda. Om du har problem med SCEP använder du [Felsöka användning av SCEP-certifikatprofiler för att etablera certifikat med Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
Intune stöder också användning av PKCS-certifikat (private and public key pair). Mer [information finns i Använda certifikat för privata och offentliga nycklar i Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) information.

## <a name="proxy"></a>Proxy
De flesta företagsnätverk i intranätet använder en proxy för att hantera extern trafik. Med HoloLens 2 kan du konfigurera en proxyserver för Ethernet-, Wi-Fi- och VPN-anslutningar.

Det finns några olika typer av proxy och sätt att konfigurera proxy. I den här guiden väljer vi att välja **Wi-Fi-proxy, ange via PAC-URL** och distribuera via MDM . Detta innebär fördelarna med att distribueras via MDM automatiskt, att kunna uppdatera PAC-filen i stället för att använda en server:port-konfiguration och slutligen använda Wi-Fi-proxy för att konfigurera proxyn så att den endast gäller för en enda Wi-Fi-anslutning så att enheterna kan användas fortfarande om de är anslutna på en annan plats.

Mer information om proxyinställningar för Windows 10 finns i [Skapa en Wi-Fi profil](/mem/intune/configuration/wi-fi-settings-configure)för enheter i Microsoft Intune – Azure .

## <a name="line-of-business-apps"></a>Verksamhetsapplikationer 
Även om flera appar kan installeras via Microsoft Store är det troligt att du har en egen anpassad app som du har skapat specifikt för att använda i mixad verklighet. Dessa anpassade appar som distribueras i hela organisationen för din verksamhet kallas verksamhetsapplikationer (LOB).
  
Det finns flera sätt att distribuera program till HoloLens 2 enheter. Appar kan distribueras direkt via MDM, Microsoft Store för företag(MSfB) eller separat inlästa via ett etableringspaket. För den här guidens skull kommer vi att distribuera appar via MDM med hjälp av nödvändig appinstallation. Detta gör att dina LOB-appar kan laddas ned automatiskt till dina HoloLens när de har avslutat registreringen.

För dig som inte har en egen LOB tillhandahåller vi en exempelapp för att testa distributionsflödet. Den här appen kommer att [vara appen MRTK-exempel](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) och har redan förbyggts och paketerats för att testa konceptbevis.

Mer information om appdistribution finns i [Apphantering: Översikt.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 stöder endast körning av UWP ARM64-appar.

## <a name="guides-playbook"></a>Spelbok för guider
Guider använder en Microsoft Dataverse-miljö som datalager för dina Guider-appar. Det är viktigt att förstå den större bilden av hur din Dataverse-miljö interagerar med dina guider och din klientorganisation. Vi kommer inte att gå igenom hur du hanterar ditt dataversum i den här guiden, men läs Grundläggande begrepp för att distribuera [Dynamics 365-guider – Dynamics 365 Mixed Reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Nästa steg 
> [!div class="nextstepaction"]
> [Företagsansluten distribution – Konfigurera](hololens2-corp-connected-configure.md)