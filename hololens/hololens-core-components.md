---
title: Planera HoloLens 2-distribution i en kommersiell miljö
description: Lär dig mer om kärnbehoven för att distribuera och hantera HoloLens i företagsmiljöer, inklusive infrastruktur, Azure Active Directory och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961478"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planera HoloLens 2-distribution i en kommersiell miljö

## <a name="overview"></a>Översikt
> [!NOTE]
> Den här översikten är avsedd att hjälpa IT-proffs att förstå överväganden för att distribuera och Microsoft HoloLens 2 enheter inom en organisation. För slutanvändare av enheter kan du [gå till Grundläggande information för](hololens2-setup.md) att komma igång.

HoloLens 2 körs på Windows 10 Holographic som ger organisationer robusta, flexibla, inbyggda tekniker för hantering av mobila enheter och appar. Windows 10 Holographic har stöd för livscykelhantering från hela enheten så att företag kan kontrollera sina enheter, data och appar. HoloLens 2 kan enkelt införlivas i standardlivscykeln, från enhetsregistrering, konfiguration och programhantering till underhåll och tillbakatagning med hjälp av en omfattande lösning för hantering av mobila enheter.

Följande steg kan hjälpa dig genom processen för HoloLens 2-implementering i din organisation.

| | |
|--|--|
| ![Steg 1](images/1green.png)| <br/> **[Vanliga distributionsscenarier:](hololens-requirements.md)** Förstå distributionsscenarier och utforska de kärnkomponenter som behövs för att distribuera HoloLens 2-enheter. |
| ![Steg 2](images/2green.png)| <br/> **[Förbered:](#prepare)** Bekanta dig med de grundläggande infrastrukturerna som behövs för HoloLens 2. |
| ![Steg 3](images/3green.png) | <br/> **[Konfigurera](#configure)**: Lär dig hur du konfigurerar viktiga komponenter för en molnbaserad distribution. |
| ![Steg 4](images/4green.png) | <br/> **[Distribuera:](#deploy)** Upptäck hur du distribuerar dina enheter och distribuerar dina program på ett säkert och effektivt sätt. |
| ![Steg 5](images/5green.png) | <br/> **[Underhåll:](#maintain)** Ta reda på vad som behövs för att korrekt upprätthålla statusen för dina HoloLens 2-enheter och säkerställa efterlevnad med företagets policy. |

## <a name="prepare"></a>Förbereda

Lär dig mer om viktiga infrastrukturtjänster som krävs för att stödja en fullständig uppsättning HoloLens 2-funktioner. 

| Komponent | Beskrivning |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Tillhandahåller identitets- och åtkomsthantering för HoloLens 2  |
| [Hantering av mobila enheter](hololens-mdm-configure.md)| Hanterar HoloLens 2-enheter som är anslutna till din klientorganisation  |
| [Wi-Fi-nätverk](hololens-commercial-infrastructure.md)| Wi-Fi är tillgänglig och enheter kan anslutas till Internet  |

## <a name="configure"></a>Konfigurera

Använd Intune och Autopilot som low-touch-lösningar för att registrera och konfigurera HoloLens 2 till din organisations Azure AD-klientorganisation och MDM.

| Komponent | Beskrivning |
|-----------|------------|
| [Automatisk registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Efter den första inloggningen registreras enheter automatiskt med Azure AD och registreras i MDM  |
| [Programlicenser](hololens2-cloud-connected-configure.md#application-licenses)| Kan tillämpas på antingen användare, användargrupper eller enhetsgrupper  |
| [Azure-användare och -grupper](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Hjälper till att tilldela konfigurationer och licenser för HoloLens 2  |

## <a name="deploy"></a>Distribuera

Distribuera dina HoloLens 2-enheter och verifiera deras konfiguration. 

| Komponent | Beskrivning |
|-----------|------------|
| [Registreringsverifiering](hololens2-corp-connected-deploy.md#enrollment-validation) | Kontrollera att enheten har anslutits till Azure AD från Inställningar eller Azure Portal |
| [Certifikatverifiering](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Kontrollera inställningarna och kontrollera att de har distribuerats korrekt |
| [Verifiera appinstallationer](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Bekräfta att appen finns och arbetar med hololens 2 |

## <a name="maintain"></a>Underhåll

Använd Windows Update för företag tillsammans med DITT MDM-system eller Microsoft Store för att hålla din flotta av HoloLens 2 och appar uppdaterade.

| Komponent | Beskrivning |
|-----------|------------|
| [Uppdatera HoloLens 2](hololens-updates.md) | Konfigurera uppdateringar efter behov via Windows Updates for Business |
| [Uppdatera appar](app-deploy-overview.md) | Konfigurera via DITT MDM-system eller Microsoft Store
