---
title: Översikt över molnanslutna HoloLens 2 med Remote Assist
description: Lär dig hur du registrerar HoloLens 2-enheter via ett molnanslutet nätverk med hjälp av Dynamics 365 Remote Assist.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923541"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Distributionsguide – Molnansluten HoloLens 2 med Remote Assist – översikt

Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Fjärrhjälp till organisationen. Detta fungerar som en modell för proof-of-concept-distributioner till din organisation i en mängd olika HoloLens 2-användningsfall. Konfigurationen liknar scenario [A: Distribuera till enheter som ansluter till molnet.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

I guiden går vi in på hur du registrerar dina enheter i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Fjärrhjälp när enheten har ställts in. För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2. Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.

## <a name="prerequisites"></a>Förutsättningar

Följande infrastruktur bör finnas på plats för att distribuera HoloLens 2. Om inte ingår det att konfigurera Azure och Intune i den här guiden:

- Wi-Fi
    - Nätverk är vanligtvis öppna för Internet- och molntjänster
- Azure Active Directory (Azure AD)-anslutning med automatisk MDM-registrering[(Azure AD P1-prenumeration krävs)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- MDM (Intune) Hanterad
    - Ett eller flera program distribueras via MDM.
- Användare loggar in med sitt eget företagskonto (Azure AD)
    - En eller flera användare per enhet stöds.

:::image type="content" alt-text="Molnanslutet scenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Läs mer om Remote Assist

Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning. Genom att koppla samman personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare i Microsoft Teams. De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte&#39;på samma plats. Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikern&#39;:s fysiska utrymme så att de kan referera till schemat när de arbetar med heads-up och handsfree på HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licensiering och krav för Remote Assist

- Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)
- [Remote Assist-prenumeration](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-användare

- Remote Assist-licens
- Nätverksanslutning

#### <a name="microsoft-teams-user"></a>Microsoft Teams-användare

- Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Nätverksanslutningar

Om du planerar att implementera det här [scenariot för flera klienter](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en informationsbarriärlicens. Se [den här artikeln](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) för att avgöra om en Information Barrier-licens krävs.

## <a name="in-this-guide-you-will"></a>I den här guiden kommer du att:

Förbereda:

> [!div class="checklist"]
> - [Lär dig mer om grundläggande infrastruktur för HoloLens 2-enheter.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Läs mer om Azure AD och konfigurera ett om du inte&#39;inte har det.](hololens2-cloud-connected-prepare.md#azure-active-directory)
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
> - [Konfigurera HoloLens 2 och verifiera registreringen.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Kontrollera att du kan göra ett Remote Assist-anrop.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Underhåll:

> [!div class="checklist"]
> - [Uppdatera Remote Assist med hjälp av Microsoft Store appen.](hololens2-cloud-connected-maintain.md#updates)
> - [Skapa en supportplan.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Utvecklingsplan.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Molnansluten distribution – Förbereda](hololens2-cloud-connected-prepare.md)

