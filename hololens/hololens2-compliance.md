---
title: HoloLens 2 Efterlevnad och GDPR
description: GDPR-dokumentation
keywords: HoloLens, GDPR, sekretess, PII
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
ms.openlocfilehash: 3365e69c8408b75a5d4e1177df938f435dec05d9dc181c698d7991159645d15a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660147"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 sekretesspolicy

Ett av de viktigaste elementen i GDPR är "designskydd av data". Det här konceptet gäller särskilt för mobila enheter, till exempel HoloLens 2, på grund av deras portabilitet, obegränsade Internetanslutningar och öppna kommunikationskanaler. Resultatet är att HoloLens 2:s [](/hololens/security-architecture) säkerhet har gjorts om för att tillhandahålla avancerat, innovativt säkerhets- och integritetsskydd från fall till slut, med både Microsofts tillvägagångssätt för sekretess- och [GDPR-föreskrifter.](https://privacy.microsoft.com/)

 >[!NOTE]
> Det här dokumentet gäller inte för HoloLens (första generationen).

## <a name="privacy-overview"></a>Sekretessöversikt

HoloLens 2 är en fristående Windows som kör Windows Holographic och som kör appar och lösningar i en miljö med avancerad mixad verklighet. Den kan användas som en säker offlineenhet eller distribueras som en [hanterad enhet](/mem/intune/fundamentals/windows-holographic-for-business) i din organisation. Se följande länkar för att förstå hur HoloLens 2 och Microsoft använder och skyddar dina data:

1. [Microsofts sekretesspolicy – HoloLens –](https://privacy.microsoft.com/privacystatement)  expandera avsnittet Företag och utvecklare i den vänstra navigeringsmenyn och välj Programvara och apparater för företag **och utvecklare.** Gå till **HoloLens** avsnitt.
2. [Windows 10 och onlinetjänster](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & guide för sekretessefterlevnad](/windows/privacy/windows-10-and-privacy-compliance)
4. [Sekretess och personliga data i Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Nätverkssäkerhet
Efter de HoloLens två [vanliga](/hololens/common-scenarios)distributionsscenarierna skyddas dina data av [Azures](/azure/compliance/) förstklassiga efterlevnad tillsammans med integrering av juridiska/regelmässiga standarder. Om du är nybörjare på Azure AD och Dynamics 365 Remote Assist kan du gå till checklistan för Azure- och [Dynamics 365-ansvarsberedskap för GDPR.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Dessutom ger Windows Defender Firewall viktiga funktioner för att skydda enhetsanslutningen. Med HoloLens 2 är brandväggen alltid aktiverad och det finns inga sätt att inaktivera den programmatiskt eller via användargränssnittet. När HoloLens 2 distribueras som en hanterad enhet med Hjälp av [Intune](/mem/intune/protect/device-compliance-get-started)finns fler efterlevnadsfunktioner tillgängliga med integrering för [Endpoint med Microsoft Intune](/mem/intune/protect/advanced-threat-protection) som en Mobile Threat Defense-lösning.

Läs mer om HoloLens 2 [säkerhet och arkitektur.](/hololens/security-architecture)

## <a name="os-security"></a>OS-säkerhet
Uppdateringar görs automatiskt (som standard) så att HoloLens 2 alltid är uppdaterad med den senaste versionen av Windows Holographic och eventuella installerade appar. Se följande för att förstå mer om hur vårt operativsystem är säkert utformat:

1. [Tillståndsseparation och isolering](/hololens/security-state-separation-isolation)
1. [Adminlös operativsystem](/hololens/security-adminless-os)
1. [Begränsa lösenordsanvändning](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fysisk säkerhet
HoloLens 2 har flashminne som skyddas av [BitLocker-kryptering](/hololens/security-encryption-data-protection). Enheten och dess lokala data kan flashas offline med [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) eller fjärrensas via MDM om den har distribuerats som en hanterad enhet.

## <a name="data-protection"></a>Dataskydd
Windows uppdateringar körs automatiskt (som standard) och [Azure-integrering](/hololens/security-encryption-data-protection#Azure-integration) skyddar data som skickas mellan sig själv och molnet.

När du distribuerar HoloLens 2 till externa klienter ser [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) till att känsliga företagsdata och resurser är både separata och säkra.

Delning av diagnostikdata med Microsoft kan konfigureras manuellt av MDM eller av användaren under OOBE. Det finns två alternativ: Valfria diagnostikdata och Nödvändiga diagnostikdata. Om din ursprungliga diagnostikinställning behöver ändras vid ett senare tillfälle i felsökningssyfte kan den ändras av användaren i **Inställningar -> Privacy -> Diagnostics & Feedback** eller AV IT-administratören (MDM) om är en hanterad enhet. Mer information om [diagnostik, feedback och sekretess finns i Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Enhetsdiagnostikloggar innehåller personligt identifierbar information (PII), till exempel om vilka processer eller program som användaren startar under typiska åtgärder. När flera användare delar en HoloLens-enhet (till exempel om användare loggar in på samma enhet med olika Microsoft Azure Active Directory-konton (Azure AD) kan diagnostikloggarna innehålla PII-information som gäller för flera användare.

Det finns [flera insamlingsmetoder och databevarandeprinciper](/hololens/hololens-diagnostic-logs) för att samla in diagnostikdata från HoloLens 2.  Mer information om hur Microsoft samlar in och använder diagnostikdata finns i [Microsofts](https://privacy.microsoft.com/privacystatement) sekretesspolicy – diagnostik – expandera **Windows** i den vänstra navigeringsmenyn och välj **Diagnostik.** Gå till **avsnittet** Diagnostik.
