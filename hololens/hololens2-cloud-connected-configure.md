---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Fjärrhjälp – Konfigurera
description: Lär dig hur du ställer in konfigurationer för att registrera HoloLens-enheter i ett molnanslutet nätverk i stor skala med Remote Assist.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378785"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurera – Molnansluten guide

I det här avsnittet av guiden går&#39;igenom hur du ställer in automatisk registrering för din klient och hur du tillämpar licenser för både Intune och Remote Assist.

## <a name="azure-users-and-groups"></a>Azure-användare och -grupper

Azure och Intune med det tillägget använder användare och grupper för att tilldela konfigurationer och licenser. För att verifiera det här distributionsflödet och kunna göra ett Remote Assist-anrop från en användare till en annan&#39;du två användarkonton.

Vi kan skapa en enskild användargrupp för att tilldela licenser. Vi kan ansluta båda användarna till samma grupp och tillämpa en licens för Intune och Fjärrhjälp för den gruppen.

Om du inte&#39;har åtkomst till två Azure AD-konton i en användargrupp kan du använda; här är snabbstartsguiderna för:

- [Så här skapar du en användare](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Så här skapar du en grupp](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Lägga till användare i en grupp](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Lägg till användare som skapats för att skapa en grupp
- [Konfigurera Azure AD så att en användargrupp kan ansluta till enheter](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Se till att den nya användargruppen har behörighet att registrera enheter i Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatisk registrering på HoloLens 2

För att få en smidig och smidig upplevelse är det enkelt att konfigurera Azure Active Directory Join (AADJ) och automatisk registrering i Intune för HoloLens 2-enheter. Detta gör att användare kan ange sina autentiseringsuppgifter för organisationens inloggningsuppgifter under OOBE och automatiskt registrera med Azure AD och registrera enheten i MDM.

Genom att [använda Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kan vi välja tjänster och navigera på några sidor tills vi kan välja Hämta en Premium-utvärderingsversion. Du kanske märker att det Azure Active Directory Premium 1 och 2, för automatisk registrering räcker P1. Vi kan välja Intune, välja användaromfång för automatisk registrering och välja gruppen som skapades tidigare.

Fullständig information och anvisningar finns i guiden om [hur du aktiverar automatisk registrering för Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Programlicenser

Med en programlicens kan en användare antingen installera företagsköpta appar eller uppgradera från en kostnadsfri utvärderingsversion till den fullständiga versionen av en app. Programlicenser kan tillämpas på antingen användare, användargrupper eller enhetsgrupper. Du&#39;behöver Remote Assist-licenser för användare i din organisation för att kunna använda Remote Assist. I den här guiden tilldelar vi Remote Assist-licenser till användargruppen som vi skapade ovan i [Azure-användare och -grupper.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Licenskraven kan vara olika beroende på om användaren kommer att göra Remote Assist-anropet från en enhet eller om användaren kommer att vara en fjärransluten medarbetare från Microsoft Teams. Som standard markeras kryssrutorna Remote Assist och Teams. I den här guiden rekommenderar vi att du lämnar standardrutorna markerade.

1. Läs mer om de olika [licens- och produktkraven per roll.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Det finns några olika typer av Remote Assist-licenser, så se till att få rätt för dina behov.
2. Du&#39;måste skaffa [licensen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Tillämpa dina licenser](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) på gruppen.

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Molnansluten distribution – Distribuera](hololens2-cloud-connected-deploy.md)