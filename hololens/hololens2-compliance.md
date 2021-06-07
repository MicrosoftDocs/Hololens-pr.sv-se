---
title: HoloLens 2– efterlevnad och GDPR
description: GDPR-dokumentation
keywords: HoloLens, GDPR, privacy, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378905"
---
# <a name="hololens-2-privacy-statement"></a>Sekretesspolicy för HoloLens 2

Ett av de viktigaste elementen i GDPR är "designskydd av data". Det här konceptet gäller särskilt för mobila enheter, till exempel HoloLens 2, på grund av deras portabilitet, obegränsade Internetanslutningar och öppna kommunikationskanaler. Till följd av detta har HoloLens 2:s [](https://docs.microsoft.com/hololens/security-architecture) säkerhet gjorts om för att tillhandahålla avancerat, innovativt säkerhets- och integritetsskydd, från end-to-end, med både Microsofts strategi för sekretess- och [GDPR-föreskrifter.](https://privacy.microsoft.com/)

 >[!NOTE]
> Det här dokumentet gäller inte för HoloLens (första generationen).

## <a name="privacy-overview"></a>Sekretessöversikt

HoloLens 2 är en fristående Windows-dator som kör Windows Holographic och som kör appar och lösningar i en miljö med avancerad mixad verklighet. Den kan användas som en säker offlineenhet eller distribueras som en [hanterad enhet](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) i din organisation. Se följande länkar för att förstå hur HoloLens 2 och Microsoft använder och skyddar dina data:
1. [Microsofts sekretesspolicy – HoloLens](https://privacy.microsoft.com/privacystatement) – expandera avsnittet Företag och utvecklare i den vänstra navigeringsmenyn och välj Programvara och apparater för företag **och utvecklare.**  Gå till **avsnittet HoloLens.**
2.  [Windows 10 och onlinetjänster](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & guide för sekretessefterlevnad](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Sekretess och personliga data i Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Nätverkssäkerhet
Efter HoloLens 2 [Common Deployment Scenarios](https://docs.microsoft.com/hololens/common-scenarios)(Vanliga distributionsscenarier för HoloLens 2) kommer dina data att skyddas av [Azures](https://docs.microsoft.com/azure/compliance/) efterlevnad i världsklass tillsammans med integrering av juridiska/regelmässiga standarder. Om du är nybörjare på Azure AD och Dynamics 365 Remote Assist kan du gå till checklistan för Azure- och [Dynamics 365-ansvarsberedskap för GDPR.](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)

Dessutom Windows Defender-brandväggen viktiga funktioner för säker enhetsanslutning. Med HoloLens 2 är brandväggen alltid aktiverad och det finns inga sätt att inaktivera den programmatiskt eller via användargränssnittet. När HoloLens 2 distribueras som en hanterad enhet med Hjälp av [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)finns fler efterlevnadsfunktioner tillgängliga med integrering för [Endpoint med Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) som en Mobile Threat Defense-lösning. 

Läs mer om säkerhet och arkitektur för HoloLens [2.](https://docs.microsoft.com/hololens/security-architecture)

## <a name="os-security"></a>OS-säkerhet
Uppdateringar görs automatiskt (som standard) så att din HoloLens 2 alltid är uppdaterad med den senaste versionen av Windows Holographic och eventuella installerade appar. Se följande för att förstå mer om hur vårt operativsystem är säkert utformat:
1. [Tillståndsseparation och isolering](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Adminlös operativsystem](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Begränsa lösenordsanvändning](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fysisk säkerhet
HoloLens 2 har flashminne som skyddas av [BitLocker-kryptering.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Enheten och dess lokala data kan flashas offline med [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) eller fjärrensas via MDM om den har distribuerats som en hanterad enhet.

## <a name="data-protection"></a>Dataskydd
Windows-uppdateringar körs automatiskt (som standard) och [Azure-integrering](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) skyddar data som skickas mellan sig själv och molnet. 

När du distribuerar HoloLens 2 till externa klienter ser [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) till att dina känsliga företagsdata och resurser är både separata och säkra. 

Delning av diagnostikdata med Microsoft kan konfigureras manuellt av MDM eller av användaren under OOBE. Det finns två alternativ: Valfria diagnostikdata och Nödvändiga diagnostikdata. Om din ursprungliga diagnostikinställning behöver ändras vid ett senare tillfälle i felsökningssyfte kan den ändras av användaren i **Inställningar -> Sekretess -> Diagnostics & Feedback** eller IT-administratören (MDM) om är en hanterad enhet. Mer information om [diagnostik, feedback och sekretess finns i Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Enhetsdiagnostikloggar innehåller personligt identifierbar information (PII), till exempel om vilka processer eller program som användaren startar under typiska åtgärder. När flera användare delar en HoloLens-enhet (till exempel om användare loggar in på samma enhet med olika Microsoft Azure Active Directory-konton (Azure AD) kan diagnostikloggarna innehålla PII-information som gäller för flera användare.

 

Det finns [flera insamlingsmetoder och databevarandeprinciper](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) för att samla in diagnostikdata från HoloLens 2.  Mer information om hur Microsoft samlar in och använder diagnostikdata finns i [Microsofts](https://privacy.microsoft.com/privacystatement) sekretesspolicy – diagnostik – expandera **Windows** i den vänstra navigeringsmenyn och välj **Diagnostik.** Gå till **avsnittet** Diagnostik.
