---
title: HoloLens 2 funktioner och lösningar
description: Lär dig mer Microsoft HoloLens kommersiella funktioner som gör det enklare för företag att hantera HoloLens enheter.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, commercial, features, mdm, mobile device management, kiosk mode, applications, identity, Bitlocker, iris, Windows Hello, Azure-powered, Autopilot, mixed reality, WDAC
ms.openlocfilehash: 5a68c4199cba20bba9d3aaa5183819975ea7b3f4
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635824"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 funktioner och lösningar

## <a name="what-can-hololens-2-do-for-you"></a>Vad kan HoloLens 2 göra åt dig?

Samarbeta utan gränser och agera med precision för att öka medarbetarnas produktivitet med program med mixad verklighet HoloLens 2. Håll dig i fokus, handsfree längre och mer bekväm med inbyggda röstkommandon, ögonspårning och världsankare för kontinuerligt fokus på att utföra uppgifter på ett säkert sätt utan fel. Anslut med fjärranslutna kollegor i realtid och arbeta tillsammans på en omfattande holografisk arbetsyta som överläggs i din fysiska miljö för att snabbt lösa problem vid tidpunkten för arbetet. Få avkastning direkt med ett robust ekosystem med program som stöds med Säkerhet, tillförlitlighet och skalbarhet hos Microsoft.  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2 funktioner

Vad gör HoloLens 2 så kraftfull?

| Funktion | Beskrivning |
|---------|-------------|
| Världsankare | Fäst hologram förblir exakt på plats. HoloLens 2 förstår din arbetsyta. Det digitala innehållet finns alltså kvar över tid – fäst vid objekt eller ytor där du arbetar. |
| Handspårning | Beröra, förstå och flytta hologram på ett sätt som känns naturligt. HoloLens 2 anpassas efter dina händer för en nynöjd nöjdhet i dina interaktioner. |
| Ögonspårning | Få en ny kontextnivå och mänsklig förståelse. HoloLens 2 förstår exakt var du letar, så att det kan förstå din avsikt och anpassa hologrammen efter dina ögon i realtid. |
| Röstaktiverad | Med inbyggda röstkommandon kan du snabbt navigera HoloLens 2 när dina händer är upptagna med en uppgift. |
| Ergonomisk | HoloLens 2 är enkelt (3,28kg) som innehåller ett system för uppringning som stöder utökad användning. |
| Stor FoV | Expandera din holografiska arbetsyta med hög upplösning och stora visningsfält. |
| Untethered | Flytta fritt, utan kablar eller externa paket för att komma igång med jobbet. |
| Azure-drivna | Strömma 3D-innehåll med hög återgivning som kan vara fäst vid en plats och/eller ett objekt som finns kvar mellan användare med Azure Mixed Reality-tjänster.
| Capture med mixad verklighet | Dokumentera en upplevelse som ett foto eller en video att dela med andra i realtid. |
| Windows Hello för företag | Irisbaserad biometrisk autentisering tar dig snabbt och säkert till arbetsflödet. |
| Windows Autopilot | Konfigurera och förkonfigurera tjänster för HoloLens 2 så att de är redo att använda direkt från start på distribuerade arbeten. |
| Os-uppdateringar | Håll dig säker med månatliga underhållsuppdateringar och dra nytta av nya produktivitets- och hanterbarhetsfunktioner i bi-årliga versioner. |
| Hantera enheter enkelt | Hantera flera HoloLens 2 enheter samtidigt med lösningar som Microsoft Intune, VMware Workspace One, MobileIron och många fler. |
| Arbeta i reglerade miljöer | HoloLens 2 har en omfattande enhetsportfölj som stöder starkt reglerade miljöer, inklusive miljöer som är avsedda för ISO-klass 5.0 och UL-klass I, division 2. |


## <a name="managing-hololens-2-in-your-organization"></a>Hantera HoloLens 2 i din organisation
HoloLens 2 innehåller funktioner som gör det enklare för organisationer att hantera och använda HoloLens enheter. Vissa funktioner ingår i enheten medan andra kan aktiveras av [Mobile Enhetshantering (MDM)](hololens-mdm-configure.md) för HoloLens eller via [Etableringspaket](hololens-provisioning.md) med hjälp [av Windows Configuration Designer.](app-deploy-provisioning-package.md#setup)

| Jag vill... | Lösning | Description |  
|---------| ------------|------------|
Hantera hur mina slutanvändare loggar in | [**Identitet**](hololens-identity.md) | HoloLens 2 stöder flera typer av användaridentiteter – Azure Active Directory (AAD), Microsoft-konto (MSA) och lokala konton.  |
| Kryptera användardata | [**Datasäkerhet**](security-encryption-data-protection.md) | BitLocker-datakryptering är aktiverat HoloLens 2 för att ge samma säkerhetsnivå som andra Windows enhet. | 
Hantera Hololens-enheter i min organisation | [**Hantering av mobila enheter**](hololens-mdm-configure.md) | Hantera inställningar, välj appar för att installera och ange säkerhetskonfigurationer som skräddarsytts efter organisationens behov på flera HoloLens 2 enheter från en central plats. | 
|Minimera installationstiden för nya användare och enheter | [**Autopilot**](hololens2-autopilot.md) | Konfigurera oobe (out-of-box experience) i Microsoft Endpoint Manager och gör det möjligt för slutanvändarna att förbereda enheter för företagsanvändning med liten eller ingen interaktion. |  
| Kontrollera OS-uppdateringar för mina enheter | [**Windows Update för företag**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | Windows Uppdatering för företag ger kontrollerade operativsystemuppdateringar till enheter och stöd för den långsiktiga underhållskanalen. |  
| Tillåt att specifika och LOB-appar laddas ned |[**Programhantering**](app-deploy-overview.md) | Välj hur du distribuerar och styr appar för valda grupper HoloLens 2 användare. | 
| Visa eller dölja specifika appar på Start-menyn |[**Helskärmsläge**](hololens-kiosk.md) | Konfigurera HoloLens 2 så att den fungerar som en fast enhet för användning i appdemo eller dedikerade företagsappar. 
| Skydda min miljö genom att låsa appar | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender Programkontroll (WDAC) blockerar appar och processer från att startas av enhetsanvändaren.
| Hantera enhetssäkerhet med regler för appar och processer | [**Principer (CPS)**](hololens-csp-policy-overview.md) | IT-administratörer kan definiera och implementera principinställningar med hjälp av en befintlig lista över princip-CPP:er som stöds HoloLens 2. |  
| Hantera hur en enhet ansluter till Internet | [**Nätverk och anslutning**](hololens-certificates-network.md) | Använd certifikatbaserad autentisering för att få åtkomst till Wi-Fi, VPN eller interna resurser. | 
| Dela enheten med flera användare | [**Automatiskt anpassad visning**](hololens-calibration.md#auto-eye-position-support) | HoloLens 2 visas justeras automatiskt med Auto Eye Position (AEP), vilket eliminerar behovet av att köra en manuell kalibreringsprocess när enheten [delas mellan användare](hololens-multiple-users.md). |

Lär dig [mer om licensieringskrav](hololens-licenses-requirements.md) för ovanstående lösningar.

## <a name="next-steps"></a>Nästa steg
> [!div class="nextstepaction"]
> [Utforska HoloLens 2 alternativ](hololens2-options.md)

> [!div class="nextstepaction"]
>[Planera HoloLens 2-distribution](hololens-requirements.md) 
