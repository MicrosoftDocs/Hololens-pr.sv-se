---
title: Vanliga distributionsscenarier
description: Läs mer om att distribuera och HoloLens i företagsmiljöer, inklusive infrastruktur, Azure Active Directory och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189247"
---
# <a name="common-deployment-scenarios"></a>Vanliga distributionsscenarier

## <a name="overview"></a>Översikt

Det kan vara svårt att ta reda på hur du distribuerar en ny enhet första gången. Här delar vi olika sätt att distribuera och hantera Microsoft HoloLens 2 enheter i organisationen.

Du vill ha lösningar – distribuerade i stor skala. Vi vill ta dig dit. Först ska vi prata om stegen för att distribuera enheter, därför hologram, för att uppnå värde för ditt scenario med mixad verklighet, oavsett om du använder D365 Remote Assist, guider eller ett tjänstaktiverad Azure-program med mixad verklighet som du har skapat.

Du kan vara en beslutsfattare, IT-proffs eller ett innovationsteam som vill HoloLens i din organisation. När du bygger från konceptbevis till en skalad distribution kan våra distributionsguider ge en uppfattning HoloLens din IT-infrastruktur – oavsett hur stor eller liten den är. Följande distributionsscenarier är de vanligaste:

| Scenario |Användning | Huvudpunkter |
|---------|---------|---------|
| [Scenario A: Molnanslutna enheter](hololens2-cloud-connected-overview.md) | När du först börjar distributionen kan du börja i liten storlek och distribuera en enskild enhet som är ansluten till molnet bara för att se den grundläggande processen. | Enheter kommer att anslutas till molntjänster och offentligt Internet. Detta passar bäst för kundanvändningsfall, fälttjänster och konceptbevis.|
| [Scenario B: Organisationens nätverk](hololens2-corp-connected-overview.md) | När du distribuerar till produktion i stor skala kan du behöva integrera med din egen organisations nätverk. | Enheter ansluts till ett trådlöst "företagsnätverk". Detta passar bäst för interna användare eller används i företagsmiljön.|
| [Scenario C: Säker offlinemiljö](hololens-common-scenarios-offline-secure.md) | Vissa verksamhetskritiska processer eller vissa företagsprinciper kan kräva användning av offlinemiljöer. | Enheter ansluts till ett mycket restriktivt nätverk eller kommer att vara helt offlineenheter. Detta lämpar sig bäst för mycket säkra miljöer eller begränsningar för Internetanslutning i avlägsna områden. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Distribuera till molnanslutna enheter

Det här scenariot är jämförbart med distribution av hanterade mobila enheter inom ett företag. HoloLens 2 distribueras för användning främst i miljöer utanför ett företagsnätverk. Företagsresurser används inte eller kan begränsas via VPN.

[![Scenario Ett diagram.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>När du ska använda detta

Överväg den här distributionsmodellen för:

* Distribuera konceptbevis, piloter och fälttjänster
* Distribuera [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Grundläggande vanliga konfigurationer

* Wi-Fi är vanligtvis helt öppna för Internet- och molntjänster
* Azure AD Join med Mobile Enhetshantering (MDM) Automatisk registrering – MDM (Intune) hanterad
* Användare loggar in med sitt eget företagskonto (Azure AD)
  * En eller flera användare per enhet som stöds
* Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Helt öppen till Helskärmsläge för enskilda appar.
* Ett eller flera program distribueras via MDM

### <a name="common-challenges"></a>Vanliga utmaningar

* Avgöra vilka MDM-konfigurationer som ska gälla för HoloLens 2 baserat på scenariokrav

Motsvarande molnanslutna guide beskriver hur du registrerar HoloLens 2 i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Remote Assist när enheten har ställts in.

> [!div class="nextstepaction"]
> [Guide för molnansluten distribution](hololens2-cloud-connected-overview.md)

Använd guiden Externa klienter för att distribuera enheter till en fjärrplats för kortsiktig eller långsiktig extern användning.

> [!div class="nextstepaction"]
> [Distributionsguide för molnanslutna (externa klienter)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Distribuera i organisationens nätverk

Det här scenariot är identiskt med en klassisk distribution för Windows 10 datorer. HoloLens 2 distribueras för användning främst i företagsnätverket med åtkomst till interna företagsresurser. Internet- och molntjänster kan vara begränsade. 

[![Scenario B1-diagram.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Scenario B2-diagram.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>När du ska använda detta

Överväg den här distributionsmodellen för:

* Interna användare
* Distribuera i stor skala (pilot och produktion) i företagsmiljön

### <a name="basic-common-configurations"></a>Grundläggande vanliga konfigurationer

* Wi-Fi är ett internt företagsnätverk med åtkomst till interna resurser och begränsad åtkomst till Internet- eller molntjänster.
* Azure AD-anslutning med automatisk MDM-registrering
* MDM (Intune) Hanterad
* Användare loggar in med sitt eget företagskonto (Azure AD)
  * En eller flera användare per enhet som stöds
* Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Helt öppen till Helskärmsläge för enskilda appar.
* Ett eller flera program distribueras via MDM

### <a name="common-challenges"></a>Vanliga utmaningar

* HoloLens 2 stöder inte lokal AD-anslutning eller System Center Configuration Manager (SCCM). Endast Azure AD-anslutning med MDM. Många företag distribuerar idag fortfarande Windows 10-datorer i det här scenariot som lokala AD-anslutna enheter som hanteras av SCCM och kanske inte har infrastrukturen distribuerad/konfigurerad för att hantera interna Windows 10-enheter via molnbaserade MDM-lösningar.
* Eftersom HoloLens 2 är en molnbaserad första enhet är den starkt beroende av Internet- och molnanslutna tjänster för användarautentisering, OS-uppdateringar, MDM-hantering och så vidare. När du ansluter till ett företagsnätverk behöver proxy-/brandväggsregler troligen justeras för att aktivera åtkomst för HoloLens 2 och de program som körs på det.
* Företagsanslutning Wi-Fi kräver vanligtvis certifikat för att autentisera enheten eller användaren i nätverket. Det kan vara svårt att konfigurera den infrastruktur eller de inställningar som krävs för att Windows 10 till enheter via MDM.

Motsvarande företagsanslutna guide instruerar om hur du registrerar HoloLens 2 i din befintliga enhetshantering, tillämpar licenser efter behov och verifierar att slutanvändarna kan använda en Dynamics 365-guide, samt använda anpassade branschappar efter att enheten har ställts in.

> [!div class="nextstepaction"]
> [Guide för företagsansluten distribution](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuera i säker offlinemiljö

Det här är en typisk distribution för mycket säkra eller konfidentiella platser. HoloLens 2 distribueras för användning främst offline utan nätverks- eller Internetåtkomst.

[![Säkerhetsdiagram 1 offline.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>När du ska använda detta

Överväg den här distributionsmodellen för:

* Mycket säkra miljöer där data måste lagras internt
* "Upplevelser" där allmänheten kommer att använda enheterna
* Problem med Internetanslutningen i fjärrområdet

### <a name="basic-common-configurations"></a>Grundläggande vanliga konfigurationer

* Wi-Fi är inaktiverad. Ethernet via USB kan vara aktiverat för LAN-anslutning om det behövs
* Inte hanterad
* Lokalt användarkonto för enhets inloggning
  * HoloLens 2 stöder endast ett lokalt konto
* Olika nivåer av enhetslåsningskonfigurationer tillämpas via Etableringspaket baserat på specifika användningsfall. Dessa konfigurationer är vanligtvis begränsade på grund av säkra miljökrav
* Ett eller flera program distribueras via etableringspaket

### <a name="common-challenges"></a>Vanliga utmaningar

* Det finns en begränsad uppsättning konfigurationer tillgängliga via konfigurationspaket
* Molntjänster kan inte användas, vilket begränsar HoloLens 2 funktioner.
* Högre administrativa kostnader eftersom dessa enheter måste konfigureras, konfigureras och uppdateras manuellt.

Motsvarande offline-säker guide innehåller anvisningar för att tillämpa ett exempel på etableringspaket som låser en HoloLens 2 för användning i säkra miljöer.

> [!div class="nextstepaction"]
> [Distributionsguide för säker offlinemiljö](hololens-common-scenarios-offline-secure.md)
