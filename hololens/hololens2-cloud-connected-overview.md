---
title: Översikt över molnanslutna HoloLens 2 med Remote Assist
description: Lär dig hur du registrerar HoloLens 2-enheter i ett molnanslutet nätverk med Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378721"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Distributionsguide – Molnansluten HoloLens 2 med Remote Assist – översikt

Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter till organisationen med det övergripande målet att ansluta dessa enheters moln till din organisation med Dynamics 365 Remote Assist redo att användas. Tänk på att detta fungerar som en modell för proof-of-concept-distributioner till din organisation i olika HoloLens 2-användningsfall.

I guiden går vi in på hur du registrerar dina enheter i enhetshanteringen, tillämpar licenser efter behov och kontrollerar att slutanvändarna omedelbart kan använda Fjärrhjälp när enheten har ställts in. För att göra detta går vi igenom de viktiga delar av infrastrukturen som behövs för att komma igång – att uppnå distribution i stor skala med HoloLens 2.

[![Molnanslutet scenario ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>I den här guiden

Den här guiden har det specifika målet att konfigurera Remote Assist i din organisation på dina HoloLens-enheter. Vi kommer att gå in på de behov som krävs för att uppnå det målet. För att bibehålla fokus på det här målet är vissa förberedelser och konfigurationer förvalda för att optimera för den här distributionen eller för att minska de objekt som behövs för att konfigurera. Du informeras om de här alternativen och kan anpassa distributionen utifrån dina affärsbehov.

Det här är en uppsättning som liknar [scenario A: Distribuera](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)till moln anslut-enheter , vilket är ett bra alternativ för många Proof of Concept-distributioner, som omfattar:

- Wi-Fi nätverk är vanligtvis helt öppna för Internet- och molntjänsterna
- Azure AD Join med automatisk MDM-registrering – MDM (Intune) hanterad
- Användare loggar in med sitt eget företagskonto (Azure AD)
  - En eller flera användare per enhet stöds
- Olika nivåer av enhetslåsningskonfigurationer tillämpas baserat på specifika användningsfall, från Helt öppen till Helskärmsläge för enskilda appar



Inga andra enhetsbegränsningar eller konfigurationer kommer att tillämpas i den här guiden, men vi rekommenderar att du utforskar dessa alternativ när du är klar.

## <a name="learn-about-remote-assist"></a>Läs mer om Remote Assist

Remote Assist möjliggör samarbetsunderhåll och reparation, fjärrinspektion samt kunskapsdelning och utbildning. Genom att koppla samman personer i olika roller och platser kan en tekniker som använder Remote Assist ansluta till en fjärransluten medarbetare i Microsoft Teams. De kan kombinera video, skärmbilder och anteckningar för att lösa problem i realtid även när de inte&#39;på samma plats. Fjärranslutna medarbetare kan infoga referensbilder, scheman och annan användbar information som teknikern&#39;:s fysiska utrymme så att de kan referera till schemat när de arbetar med huvudena och handsfree på HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>I den här guiden kommer du att:

Förbereda:

> [!div class="checklist"]
> - [Lär dig mer om information om infrastrukturen för HoloLens 2-enheter.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Läs mer om Azure AD och konfigurera ett om du inte&#39;inte har det.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Läs mer om MDM och konfigurera med Intune om du inte redan&#39;har en klar.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Lär dig mer om nätverkskraven för Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Valfritt: VPN för att ansluta till organisationsresurser](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurera:

> [!div class="checklist"]
> - [Skapa användare och grupper.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
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

