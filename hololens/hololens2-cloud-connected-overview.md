---
title: Översikt över molnanslutna HoloLens 2 med Remote Assist
description: Lär dig hur du registrerar HoloLens 2 enheter över ett molnanslutet nätverk med hjälp av Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428072"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Distributionsguide – Molnansluten HoloLens 2 med Fjärrhjälp – översikt

Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Remote Assist till organisationen. Detta fungerar som en modell för konceptbevisdistributioner till din organisation i olika HoloLens 2 användningsfall. Konfigurationen liknar scenario [A: Distribuera till enheter som ansluter till molnet.](common-scenarios.md#scenario-a) 

I guiden går vi in på hur du registrerar dina enheter i din enhetshantering, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Remote Assist när enheten har ställts in. För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2. Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.

## <a name="prerequisites"></a>Förutsättningar

Följande infrastruktur ska vara på plats för att distribuera HoloLens 2. Om inte ingår det att konfigurera Azure och Intune i den här guiden:

Det här är en konfiguration som liknar [scenario A: Distribuera](/hololens/common-scenarios#scenario-a)till cloud connect-enheter , vilket är ett bra alternativ för många Proof of Concept-distributioner, som omfattar:

- Wi-Fi är vanligtvis helt öppna för Internet- och molntjänster
- Azure AD Join med mdm-automatisk registrering – MDM-hanterad (Intune)
- Användare loggar in med sitt eget företagskonto (Azure AD)
    - En eller flera användare per enhet stöds.

:::image type="content" alt-text="Molnanslutet scenario." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Läs mer om Remote Assist

Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning. Genom att ansluta personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare på Microsoft Teams. De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte är på samma plats. Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikerns fysiska utrymme så att de kan referera till schemat när de arbetar med heads-up och handsfree på HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licensiering och krav för Remote Assist

- Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)
- [Remote Assist-prenumeration](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-användare

- Remote Assist-licens
- Nätverksanslutning

#### <a name="microsoft-teams-user"></a>Microsoft Teams användare

- Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Nätverksanslutningar

Om du planerar att implementera det här [scenariot för flera klienter](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en informationsbarriärlicens. Information om huruvida en Information Barrier-licens krävs finns i Vendors and customers use full Dynamics 365 Remote Assist capabilities (Leverantörer och kunder använder fullständiga [Dynamics 365 Remote Assist-funktioner).](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)

## <a name="in-this-guide-you-will"></a>I den här guiden kommer du att:

Förbereda:

> [!div class="checklist"]
> - [Lär dig mer om grundläggande infrastruktur för HoloLens 2 enheter.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Läs mer om Azure AD och konfigurera ett om du inte&#39;har det.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Läs mer om MDM och konfigurera med Intune om du inte redan&#39;har en klar.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Lär dig mer om nätverkskraven för Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Valfritt: VPN för att ansluta till organisationsresurser](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurera:

> [!div class="checklist"]
> - [Så här skapar du användare och grupper.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Konfigurera automatisk registrering i Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Så här tilldelar du dina programlicenser.](hololens2-cloud-connected-configure.md#application-licenses)

Distribuera:

> [!div class="checklist"]
> - [Konfigurera din HoloLens 2 och verifiera registreringen.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Kontrollera att du kan göra ett Remote Assist-anrop.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Underhåll:

> [!div class="checklist"]
> - [Uppdatera Remote Assist med hjälp av Microsoft Store appen.](hololens2-cloud-connected-maintain.md#updates)
> - [Skapa en supportplan.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Utvecklingsplan.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Molnansluten distribution – Förbereda](hololens2-cloud-connected-prepare.md)

