---
title: Intune och Företagsportal
description: Lär dig att konfigurera, tilldela och skapa en bekväm användarupplevelse med Intune, hantering av mobila enheter och företagsportalen.
keywords: intune, app management, app, company portal, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427190"
---
# <a name="intune--company-portal"></a>Intune-& Företagsportal

Med Mobile Enhetshantering (MDM) kan du använda dina egna anpassade appar [via Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) för att distribuera dem direkt till dina HoloLens enheter. Microsoft Intune är en molnbaserad tjänst som fokuserar på hantering av mobilenheter (MDM) och hantering av mobilprogram (MAM). Intune ingår i Microsofts [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) och gör det möjligt för användarna att vara produktiva samtidigt som organisationens data skyddas. Mer information om Intune finns i [Vad är Intune.](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Installation

1. Upload till en verksamhetsrad eller ladda upp en anpassad app till din Intune-klientorganisation. Se även: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).

2. [Tilldela din app till en grupp](/mem/intune/apps/apps-deploy). Baserat på vilken tilldelningstyp du väljer kan appen levereras automatiskt eller tillgänglig för att enkelt hämtas om du har ett urval av appar.

> [!NOTE]
> När du skapar ditt appx-paket ska du se till att ta med arkitekturen för de enheter som du distribuerar till. HoloLens 2 är ARM64 och HoloLens (första generationen) är x86. Du kan inkludera båda i ett enda appx-paket om du planerar att ha en miljö med blandade enheter.

## <a name="assignment-types"></a>Tilldelningstyper

Om du vill att din app ska installeras automatiskt på enheten efter registreringen bör du **välja Krävs** för dessa grupper.
Om du vill göra din app tillgänglig för nedladdning till enheter som registrerats via företagsportalen väljer **du Tillgänglig för registrerade enheter.**

## <a name="end-user-experience"></a>End-User Experience

När du har ställt in konfigurationen i Intune är du redo för slutanvändare att ta emot dina valda appar.

Följ de här stegen för att hämta dina appar automatiskt:

1. Registrera din enhet med din klientorganisation.
2. När enheten har slutfört registreringen bör du få appen på enheten.
3. Om du inte ser appen omedelbart går du **till Inställningar Arbets-** eller skolkontoinformation och bläddrar ned för att se information om installerad  >    >    >   appstatus.

Så här kommer du till appar via Företagsportal:

1. Öppna **Start-menyn** och välj **Microsoft Store**.
2. Sök efter **Företagsportal** och ladda ned appen.
3. Logga in på ditt konto.
4. Välj den app som du vill ta emot och ladda ned den.

> [!Tip]
> Läs mer om [hur du installerar Företagsportal](/mem/intune/apps/company-portal-app) och [distribuerar och hanterar appar i Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
