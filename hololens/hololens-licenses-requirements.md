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
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640294"
---
# <a name="license-requirements"></a>Licenskrav

## <a name="hololens-2-device-managed"></a>HoloLens 2-enhet (hanterad)

[Azure AD-konto](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) kan inte användas för att hantera HoloLens enheter.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) eller någon annan MDM.
- [Windows Autopilot för HoloLens 2](hololens2-autopilot.md)– förenklar etableringen för både IT-administratörer och slutanvändare. IT-administratörer kan förkonfigurera HoloLens 2 principer, och vid första starten distribueras enheter i företagsklart tillstånd utan interaktion från slutanvändaren. 

  > [!NOTE]
  > Windows Autopilot kräver [att Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) [och automatisk registrering](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) först konfigureras för Autopilot-flödet med låg pekfunktion och distribution av enheter. 

### <a name="business-use-case"></a>Användningsfall för företag: 

- [Distributionsscenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) – konceptbevis eller pilotdistribution.

- [Distributionsscenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) – distribution i stor skala.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 Endast enhet (ej hanterad)

När du använder antingen ett Microsoft-konto (MSA) eller ett lokalt konto krävs inga ytterligare licenser för dessa konton.

[Lokalt konto](/windows/security/identity-protection/access-control/local-accounts)

- Det här kontot måste [etableras](hololens-provisioning.md#provisioning-package-hololens-wizard) i förväg med Windows Configuration Designer (WCD).

[Microsoft-konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Flera användare stöds inte för en enhet som använder något av dessa konton.

### <a name="business-use-case"></a>Användningsfall för företag: 

- [Distributionsscenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) – offline eller säker distribution.
 
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

- Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Nätverksanslutningar

Om du planerar att implementera det här [scenariot för flera klienter](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)kan du behöva en informationsbarriärlicens. Se [den här artikeln](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) för att avgöra om en Information Barrier-licens krävs.

### <a name="dynamics-365-guides"></a>Dynamics 365-guider 

#### <a name="admin"></a>Administratör

- Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)
- Prenumeration på Dynamics 365-guider [eller kostnadsfri utvärderingsversion](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Skapare av guider

1. Azure AD-konto
1. [Licens för Dynamics 365-guider](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides-programmet installerat på en dator eller HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (används för att visa Analytics-instrumentpanelen)
1. Författarroll (för att skapa guider)
1. Nätverksanslutning

#### <a name="guides-user"></a>Användare av guider

1. Azure AD-konto
1. [Licens för Dynamics 365-guider](/dynamics365/mixed-reality/guides/requirements)
1. Appen Dynamics 365 Guides installerad på en HoloLens
1. Operatörsroll (för testning eller användning av guider)
1. Nätverksanslutning
