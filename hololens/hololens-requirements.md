---
title: Planera HoloLens 2-distribution i en kommersiell miljö
description: Läs mer om att distribuera och hantera HoloLens i företagsmiljöer, inklusive infrastruktur, Azure Active Directory och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924612"
---
# <a name="common-deployment-scenarios"></a>Vanliga distributionsscenarier

## <a name="overview"></a>Översikt

Den här sidan innehåller en översikt över arkitektur på hög nivå för tre vanliga scenarier när du distribuerar och hanterar Microsoft HoloLens 2 enheter inom företaget.

Ofta bestäms hur du hanterar dina enheter och får åtkomst till organisationens resurser i stor utsträckning av faktorer som redan finns på plats. Baserat på din befintliga infrastruktur uppmanar vi dig att granska det vanliga enhetshanteringsformatet (MDM) i följande scenarier och sedan läsa [Planning HoloLens 2 deployments in a commercial](hololens-core-components.md) environment (Planera HoloLens 2-distributioner i en kommersiell miljö) för att avgöra vilket scenario som passar dina behov. Det finns också tre motsvarande guider som kan användas under distributionen.


 1. [Distributionsguide för molnansluten miljö](hololens2-cloud-connected-overview.md)
     1. [Distributionsguide för molnansluten miljö (externa klienter)](hololens2-deployment-guide.md)
 1. [Distributionsguide för företagsnätverk](hololens2-corp-connected-overview.md)
 1. [Distributionsguide för säker offlinemiljö](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Distribuera till molnanslutna enheter

Det här scenariot är jämförbart med distribution av hanterade mobila enheter inom ett företag. HoloLens 2 distribueras för användning främst i miljöer utanför ett företagsnätverk. Företagsresurser används inte eller kan begränsas via VPN. 
 * Grundläggande vanliga konfigurationer
   * Wi-Fi är vanligtvis helt öppna för Internet- och molntjänsterna.
   * Azure AD Join med Mobile Enhetshantering (MDM) Automatisk registrering – MDM (Intune) Hanterad
   * Användare loggar in med sitt eget företagskonto (Azure AD)
     * En eller flera användare per enhet som stöds
   * Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Fullständigt öppen till Helskärmsläge för enskild app.
   * Ett eller flera program distribueras via MDM

* Vanliga utmaningar
   * Avgöra vilka MDM-konfigurationer som ska tillämpas på HoloLens 2 baserat på scenariokrav.

[![Scenario Ett diagram ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Motsvarande molnanslutna guide beskriver hur du registrerar HoloLens 2 i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Remote Assist när enheten har ställts in. Använd guiden Externa klienter för att distribuera enheter till en fjärrplats för kortsiktig eller långsiktig extern användning.

> [!div class="nextstepaction"]
> [Distributionsguide för molnansluten miljö](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Distributionsguide för molnansluten miljö (externa klienter)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Distribuera i organisationens nätverk

Det här scenariot är identiskt med en klassisk distribution för Windows 10 datorer. HoloLens 2 distribueras för användning främst i företagsnätverket med åtkomst till interna företagsresurser. Internet- och molntjänster kan vara begränsade. 

 * Grundläggande vanliga konfigurationer
   * Wi-Fi är ett internt företagsnätverk med åtkomst till interna resurser och begränsad åtkomst till Internet- eller molntjänster.
   * Azure AD Join med automatisk MDM-registrering
   * MDM (Intune) Hanterad
   * Användare loggar in med sitt eget företagskonto (Azure AD)
     * En eller flera användare per enhet som stöds
   * Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Fullständigt öppen till Helskärmsläge för enskild app.
   * Ett eller flera program distribueras via MDM

 * Vanliga utmaningar
   * HoloLens 2 stöder inte lokal AD-anslutning eller SCCM. Endast Azure AD-anslutning med MDM. Många företag distribuerar idag fortfarande Windows 10-datorer i det här scenariot som lokala AD-anslutna enheter som hanteras av System Center Konfigurationshanteraren (SCCM) och kanske inte har infrastrukturen distribuerad/konfigurerad för att hantera interna Windows 10-enheter via molnbaserade MDM-lösningar.
   * Eftersom HoloLens 2 är en molnenhet förlitar den sig mycket på Internet- och molnanslutna tjänster för användarautentisering, OS-uppdateringar, MDM-hantering och så vidare. När du ansluter till ett företagsnätverk behöver proxy-/brandväggsregler troligen justeras för att aktivera åtkomst för HoloLens 2 och de program som körs på det.
   * Företagsanslutning Wi-Fi kräver vanligtvis certifikat för att autentisera enheten eller användaren i nätverket. Det kan vara svårt att konfigurera den infrastruktur eller de inställningar som krävs för att Windows 10 till enheter via MDM.

[![Scenario B1-diagram ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Scenario B2-diagram ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Motsvarande företagsnätverksguide instruerar om hur du registrerar HoloLens 2 i din befintliga enhetshantering, tillämpar licenser efter behov och verifierar att slutanvändarna kan använda en Dynamics 365-guide, samt använda anpassade branschappar efter att enheten har ställts in.

> [!div class="nextstepaction"]
> [Distributionsguide för företagsnätverk](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuera i säker offlinemiljö

Det här är en typisk distribution för mycket säkra eller konfidentiella platser. HoloLens 2 distribueras för användning främst offline utan nätverks- eller Internetåtkomst. 
 * Grundläggande vanliga konfigurationer
   * Wi-Fi är inaktiverad. Ethernet via USB kan aktiveras för LAN-anslutning om det behövs.
   * Inte hanterad.
   * Lokalt användarkonto för enhets inloggning.
     * HoloLens 2 stöder endast ett lokalt konto.
   * Olika nivåer av enhetslåsningskonfigurationer tillämpas via Etableringspaket baserat på specifika användningsfall. Dessa konfigurationer är vanligtvis begränsade på grund av säkra miljökrav.
   * Ett eller flera program distribueras via etableringspaket

 * Vanliga utmaningar
   * Det finns en begränsad uppsättning konfigurationer tillgängliga via konfigurationspaket
   * Molntjänster kan inte användas, vilket begränsar HoloLens 2-funktionerna.
   * Högre administrativa kostnader eftersom dessa enheter måste konfigureras, konfigureras och uppdateras manuellt.

[![Offline– säkert diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Motsvarande offline-säker guide innehåller anvisningar för att tillämpa ett exempel på etableringspaket som låser en HoloLens 2 för användning i säkra miljöer.

> [!div class="nextstepaction"]
> [Distributionsguide för säker offlinemiljö](hololens-common-scenarios-offline-secure.md)


