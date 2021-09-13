---
title: Licenskrav
description: Håll dig uppdaterad med alla licenskrav och riktlinjer som du behöver för hantering av mobila enheter, HoloLens och Fjärrhjälp.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036542"
---
# <a name="license-requirements"></a>Licenskrav

## <a name="overview"></a>Översikt
Den här sidan ger en översikt över de licenser och konton som behövs för att distribuera både hanterade och ohanterade HoloLens 2 enheter i din organisation. Den innehåller också information om licensiering av Dynamics 365 [Remote Assist och](#dynamics-365-remote-assist) [guider](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 licens- och kontokrav

 
|       &nbsp;      | Hanterade HoloLens | Ohanterade HoloLens |
|-------------------|-----------------|---------------------|
| **Företagsanvändningsfall** | | |
| [Distribuera till molnanslutna enheter – konceptbevis/pilotdistribution](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Distribuera i organisationens nätverk – distribution i stor skala](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Distribuera i säker offlinemiljö](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenser** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> eller <sup>2)</sup> | ✔️  | |
| **Konton** |  | |
| Azure AD-administratörskonto | ✔️ |  |
| Azure AD-användarkonto | ✔️ | |
| [Microsoft-konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Lokalt konto](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Automatisk registrering under](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) den första enhetskonfigurationen, som registrerar och Azure Active Directory och gör att enheten kan hanteras med Intune.
- <sup>2</sup> [Windows Autopilot för HoloLens 2](hololens2-autopilot.md) förenklar etableringen för både IT-administratörer och slutanvändare. IT-administratörer kan förkonfigurera HoloLens två principer, och vid den första starten distribueras enheter i företagsklart tillstånd utan interaktion från slutanvändaren.
- <sup>3</sup> Det här kontot [måste etableras](hololens-provisioning.md#provisioning-package-hololens-wizard) i förväg med Windows Configuration Designer (WCD).

> [!IMPORTANT]
> Active Directory (AD) kan inte användas för att hantera HoloLens enheter.
 
> [!WARNING]
> Flera användare stöds inte för en enhet som använder antingen ett MSA-konto eller ett lokalt konto.

## <a name="dynamics-365-licensing-and-requirements"></a>Licensiering och krav för Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Fjärrhjälp för Dynamics 365 

#### <a name="admin"></a>Administratör

- Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)
- [Remote Assist-prenumeration](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-användare

- Azure AD-konto

- Remote Assist-licens 

  > [!NOTE]
  > Microsoft Teams paketeras med Remote Assist

- Nätverksanslutning

#### <a name="microsoft-teams-user"></a>Microsoft Teams användare

- Azure AD-konto

- Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Nätverksanslutningar

Om du planerar att implementera det [här scenariot mellan klientorganisationen](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en licens för informationsbarriärer. Se [den här artikeln](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) för att avgöra om en Information Barrier-licens krävs.

### <a name="dynamics-365-guides"></a>Dynamics 365-guider 

#### <a name="admin"></a>Administratör

1. Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)
2. Prenumeration på Dynamics 365-guider [eller kostnadsfri utvärderingsversion](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Redigeringsguider

1. Azure AD-konto
1. [Licens för Dynamics 365-guider](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365-guideprogrammet installerat på en dator eller HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (används för att visa Analytics-instrumentpanelen)
1. Författarroll (för att skapa guider)
1. Nätverksanslutning

#### <a name="guides-user"></a>Användare av guider

1. Azure AD-konto
1. [Licens för Dynamics 365-guider](/dynamics365/mixed-reality/guides/requirements)
1. Appen Dynamics 365 Guides installerad på en HoloLens
1. Operatörsroll (för testning eller användning av guider)
1. Nätverksanslutning
