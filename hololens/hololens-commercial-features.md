---
title: Kommersiella funktioner
description: Lär dig mer Microsoft HoloLens Commercial Suite funktioner som gör det enklare för företag att hantera HoloLens-enheter.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, commercial, features, mdm, mobile device management, kiosk mode
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379993"
---
# <a name="commercial-features"></a>Kommersiella funktioner

HoloLens innehåller funktioner som gör det enklare för företag att hantera HoloLens-enheter.

Alla HoloLens 2-enheter har kommersiella funktioner tillgängliga.

HoloLens (första generationen) kom med två licensieringsalternativ, utvecklarlicensen och en kommersiell licens. Om du vill låsa upp HoloLens kommersiella funktioner uppgraderar du från utvecklarlicensen till en kommersiell licens. Om du vill köpa Microsoft HoloLens Commercial Suite kontaktar du din Microsoft-konto chef.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Viktiga kommersiella funktioner

- **Helskärmsläge.** Du kan använda HoloLens i demonstrationer eller demonstrera upplevelser med hjälp av helskärmsläge för att begränsa vilka appar som kan köras.

  ![Med helskärmsläge startar HoloLens direkt i den app du väljer.](images/201608-kioskmode-400px.png)

- **Mobile Enhetshantering (MDM) för HoloLens.** IT-avdelningen kan hantera flera HoloLens-enheter samtidigt med hjälp av lösningar som Microsoft Intune. Du kan hantera inställningar, välja appar att installera och ange säkerhetskonfigurationer som är skräddarsydda för organisationens behov.

  ![Mobile Enhetshantering på HoloLens ger enhetshantering i företagsklass över flera enheter.](images/201608-enterprisemanagement-400px.png)

- **Windows Update för företag.** Windows Update för företag ger kontrollerade uppdateringar av operativsystem till enheter och stöd för den långsiktiga underhållskanalen.
- **Datasäkerhet.** BitLocker-datakryptering är aktiverat på HoloLens för att ge samma säkerhetsnivå som andra Windows-enheter.
- **Åtkomst till arbetet.** Alla i din organisation kan fjärransluta till företagsnätverket via ett virtuellt privat nätverk (VPN) på en HoloLens. HoloLens kan också komma åt Wi-Fi nätverk som kräver autentiseringsuppgifter.
- **Microsoft Store för företag.** IT-avdelningen kan också konfigurera en privat företagsbutik som endast innehåller företagets appar för din specifika HoloLens-användning. Distribuera företagets programvara på ett säkert sätt till en vald grupp av företagsanvändare.

## <a name="feature-comparison-between-editions"></a>Funktionsjämförelse mellan utgåvor

|Funktioner |HoloLens (1:a gen) Development Edition |HoloLens (1:a gen) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Enhetskryptering (BitLocker) | |✔️ |✔️ |
|Virtuellt privat nätverk (VPN) | |✔️ |✔️ |
|[Helskärmsläge](hololens-kiosk.md) | |✔️ |✔️ |
|**Hantering och distribution** | | | |
|Mobile Enhetshantering (MDM) | |✔️ |✔️ |
|Möjlighet att blockera avregistrera | |✔️ |✔️ |
|Certifikatbaserad åtkomst Wi-Fi företag | |✔️ |✔️ |
|Microsoft Store (konsument) |Konsument |Filtrera med hjälp av MDM |Filtrera med hjälp av MDM |
|[Business Store-portalen](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Säkerhet och identitet** | | | |
|Logga in med Azure Active Directory (Azure AD)-konto |✔️ |✔️ |✔️ |
|Logga in med Microsoft-konto (MSA) |✔️ |✔️ |✔️ |
|Nästa generations autentiseringsuppgifter med PIN-upplåsning |✔️ |✔️ |✔️ |
|[Säker start](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Service och support** | | | |
|Automatiska systemuppdateringar när de tas emot |✔️ |✔️ |✔️ |
|[Windows Update för företag](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Aktivera kommersiella funktioner

Din organisations IT-administratör kan konfigurera kommersiella funktioner som Microsoft Store för företag, helskärmsläge och företagsåtkomst Wi-Fi åtkomst. Dokumentationen [Microsoft HoloLens](index.yml) innehåller stegvisa instruktioner för att registrera enheter och installera appar från Microsoft Store för företag.

## <a name="see-also"></a>Se även

- [Microsoft HoloLens](index.yml)
- [Helskärmsläge](hololens-kiosk.md)
- [CPS som stöds i HoloLens-enheter](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store för företagsprogram och affärsprogram](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Arbeta med verksamhetsapplikationer](/microsoft-store/working-with-line-of-business-apps)
