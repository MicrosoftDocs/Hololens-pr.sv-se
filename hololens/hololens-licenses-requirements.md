---
title: Licenskrav
description: Håll dig uppdaterad med alla licenskrav och riktlinjer som du behöver för hantering av mobila enheter, HoloLens och Remote Assist.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380073"
---
# <a name="license-requirements"></a>Licenskrav

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Vägledning för MDM Enhetshantering licenser (Mobile Enhetshantering)

Om du planerar att hantera dina HoloLens-enheter behöver du Azure AD och en MDM. Active Director (AD) kan inte användas för att hantera HoloLens-enheter.
Om du planerar att använda en annan MDM än Intune krävs [Azure Active Directory en](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) ny licens.
Om du planerar att använda Intune som MDM läser du upp listan [över paket som](https://docs.microsoft.com/intune/fundamentals/licenses) innehåller Intune-licenser. **Observera att Azure AD ingår i de flesta av dessa paket.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>Identifiera de licenser som behövs för ditt scenario och dina produkter

### <a name="hololens-1st-gen-licenses-requirements"></a>Licenskrav för HoloLens (första generationen)

Du kan behöva uppgradera din HoloLens-enhet (första generationen) till Windows Holographic for Business. (Se [HoloLens kommersiella funktioner för](holoLens-commercial-features.md#feature-comparison-between-editions) att avgöra om du behöver uppgradera).

 I så fall måste du göra följande:

- Hämta en XML-fil för HoloLens Enterprise-licens
- Tillämpa XML-filen på HoloLens. Du kan göra detta via ett [etableringspaket eller](hololens-provisioning.md) via ditt [Mobila Enhetshanteraren](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="remote-assist-license-requirements"></a>Licenskrav för Remote Assist

Kontrollera att du har nödvändig licensiering och enhet, vilket du kan läsa i [kravdokumentationen.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)

1. [Remote Assist-licens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Eller prova en [Remote Assist-utvärderingsversion](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory-licens (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Om du planerar att implementera **[det här scenariot mellan klientorganisationen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** kan du behöva en licens för informationsbarriärer. Se den [här artikeln för](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) att avgöra om en Information Barrier-licens krävs.

### <a name="guides-license-requirements"></a>Licenskrav för guider

Kolla in de [uppdaterade licens- och enhetskraven.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)

1. [Azure Active Directory-licens (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guider](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
