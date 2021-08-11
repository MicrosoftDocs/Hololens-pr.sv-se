---
title: Etableringspaket
description: Lär dig mer om apppaketering, etablering, distribution och distribution av företagsapp för HoloLens enheter.
keywords: app, app deployment, enterprise app deployment, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665224"
---
# <a name="provisioning-package"></a>Etableringspaket

Konfigurationspaket kan användas för att förbereda och konfigurera enheter i en miljö utan åtkomst till slutpunktshantering. De kan också distribueras till en enhet oavsett användarens identitet, registreringsstatus, under Oobe (Out of Box Experience) eller genom att använda ett konfigurationspaket under [installationen.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Överväganden för etableringspaket:

* Icke-offentliga appar
* Endast USB-sidobelastning
* Ingen automatisk uppdatering (kräver manuella uppdateringar via PPKG:er)

Appar som installeras via ett etableringspaket måste signeras av ett certifikat i det lokala datorarkivet. Etableringspaket kan bara installera certifikat till enhetens (den lokala datorns) arkiv. Därför kan en app och ett certifikat installeras via samma etableringspaket. Om du distribuerar certifikatet från MDM eller installerar via [Certifikathanteraren](certificate-manager.md)distribuerar du certifikatet till det lokala datorarkivet för att signera appar som installerats på det här sättet.

Information om grunderna för att skapa ett etableringspaket för HoloLens enheter finns i [HoloLens Etablering](/hololens/hololens-provisioning). Om du vill distribuera en app måste du börja med avancerad etablering.

> [!NOTE]
> HoloLens (första generationen) har begränsat stöd för installation av appar **(UniversalAppInstall)** med hjälp av ett etableringspaket. HoloLens (första generationens) enheter stöder endast installation av en app via PPKG under OOBE och endast med användarkontextinstallationer.

## <a name="setup"></a>Installation

I [Windows Configuration Designer gör](https://www.microsoft.com/store/productId/9NBLGGH4TX22) du följande fyra steg.

1. Ange ApplicationManagement/AllowAllTrustedApps till "Ja". Se: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Gå till **UniversalAppInstall**  >  **UserContextAppLicense** och ange **PackageFamilyName**. Se [UniversalAppInstallera](/windows/configuration/wcd/wcd-universalappinstall). Se även: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Du kan använda Enhetsportalen på en enhet som du redan har installerat appen på. Besök sidan Appar och titta på raden PackageRelativeID, all information före "!" Är **packageFamilyName**.

3. Du ser då att du har ett nytt avsnitt, **ApplicationFile**. Använd det här området för att ladda upp ditt appx-paket.

4. Beroende på om du har köpt din app eller skapat en egen LOB-app måste du ladda upp licensfilen eller säkerhetscertifikatet.

    - För licensfil: navigera till **UniversalAppInstallera**  >  **användareContextAppLicence** och bläddra till platsen för din licens och ladda upp den.
    - För säkerhetsfilen går du till Certifikat **och väljer** det certifikat som ska installeras tillsammans med ditt .appx-paket.

Se till att spara projektet på en säker plats. Exportera **den** sedan som ett **etableringspaket**.  

Se även: [Tillämpa ditt etableringspaket på HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
