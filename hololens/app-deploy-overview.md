---
title: Översikt – Apphantering
description: Kom igång med en översikt över apphantering med mixad verklighet med hantering av mobila enheter, Microsoft Store för företag och etableringspaket.
keywords: HoloLens, user, account, app, application management,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378765"
---
# <a name="app-management-overview"></a>Apphantering: Översikt

Du kan distribuera appar på fyra olika sökvägar: **Mobile Enhetshantering (MDM),** **Microsoft Store för företag**, **Microsoft Store** eller genom att installera dem via **Etablera**.

## <a name="mobile-device-management-mdm"></a>Mobile Enhetshantering (MDM)

En MDM-lösning gör det möjligt för IT-beslutsfattare och administratörer att automatiskt installera (push-installera) sina egna, verksamhetsbaserade appar eller köpa appar via butiken för en grupp användare. HoloLens-enheter fungerar bäst med Microsoft Endpoint Manager (Intune) för [programhantering.](app-deploy-intune.md) Intune erbjuder även användare mer begränsad kontroll över IT-hanterade appar via Företagsportal nedladdningsbara upplevelsen.

> [!NOTE]
> Följande anvisningar är för användare som vill hantera sina program med Intune. Microsoft rekommenderar att du använder Intune för program- och enhetshantering.

Mobile Enhetshantering (MDM) gäller för:

* MDM distribuerad + Företagsportal
* Verksamhetsapplikationer (icke-offentliga) appar
* Manuell installation av tillgängliga program via Företagsportal
* Push-meddelanden för administratörer via MDM-princip
* Automatisk uppdatering via MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store för företag

Med [Microsoft Store för företag](app-deploy-store-business.md) IT-beslutsfattare och administratörer i företag att hitta, skaffa, hantera och distribuera kostnadsfria och betalda appar. IT-administratörer kan hantera Microsoft Store-appar och privata verksamhetsapplikationer i ett lager, samt tilldela och återanvända licenser efter behov. Mer information finns i [Krav för att använda Microsoft Store för företag](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

Följande Microsoft Store för företag gäller för:

* Offentliga appar eller verksamhetsapplikationer
* Automatisk installation av nödvändiga program via MDM-association
* Användaren laddar ned appar manuellt
* Automatisk uppdatering

## <a name="microsoft-store-apps"></a>Microsoft Store-appar

Med Microsoft Store it-beslutsfattare och administratörer i företag att hitta, skaffa, hantera och distribuera offentliga appar.

Den Microsoft Store här Microsoft Store gäller för:

* Endast offentliga appar
* Användaren laddar ned appar manuellt
* Uppdatera automatiskt om du är ansluten till Internet

Mer information finns i [Holographic Store-appar.](https://docs.microsoft.com/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Installera via etableringspaket

[Med etableringspaket](app-deploy-provisioning-package.md) kan du installera anpassade appar eller branschapplikationer, så att IT-proffs och administratörer snabbt kan installera appar på en lokal enhet via USB. Den här installationen kan göras utan internetanslutning och för alla identitetstyper.

Installation via etableringspaket gäller för:

* Verksamhets-/egenutvecklade (icke-offentliga) appar
* Offentliga appar (om offlineinstallationsprogram är tillgängligt)
* Endast USB-sidladdning
* Ingen automatisk uppdatering (kräver manuella uppdateringar via etableringspaket)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installera appar på HoloLens 2 via Appinstallationsprogram

Med hjälp [Appinstallationsprogram](app-deploy-app-installer.md) användare en upplevelse som är enkel för att installera appar på lokala enheter eller dela en app med någon annan som inte är bekant med andra appinstallationsmetoder på HoloLens. Detta kan göras utan att du behöver aktivera utvecklarläge eller använda Enhetsportalen. Det här är en enkel metod för att distribuera en helt skapad app. Oavsett om du bara vill degradera din app till en annan användare med en HoloLens eller om du vill distribuera din app fungerar den här metoden enkelt.

Installation via Appinstallationsprogram gäller för:

* Verksamhets-/egenutvecklade (icke-offentliga) appar
* Endast sidobelastning
* Kräver inte utvecklarläge eller enhetsportal
* Enkelt för slutanvändare att installera
