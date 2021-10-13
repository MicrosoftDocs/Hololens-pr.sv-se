---
title: Microsoft Store för företag
description: Lär dig hur du arbetar med Microsoft Store för företag att publicera dina mixed reality-program i din verksamhet.
keywords: Microsoft Store för företag, msfb, appdistribution, store
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924318"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store för företag

Den [Microsoft Store för företag](/microsoft-store/microsoft-store-for-business-overview) är främst utformad för IT-beslutsfattare och administratörer i företag eller organisationer med ett flexibelt sätt att hitta, skaffa, hantera och distribuera kostnadsfria och betalda appar på utvalda marknader till Windows 10 enheter i volym. 

Du kan hantera Microsoft Store-appar och privata verksamhetsapplikationer i ett lager och tilldela och använda licenser efter behov. Du kan också välja den bästa distributionsmetoden för din organisation: direkt tilldela appar till enskilda användare och team, publicera appar på privata sidor i Microsoft Store eller ansluta till hanteringslösningar för fler alternativ.

När Microsoft Store för företag används av en slutanvändare startar användaren appen Microsoft Store program. När användaren har startats kan han eller hon välja fliken med organisationens namn. Därefter visas de appar som är tillgängliga för dem eller enheten.

> [!Note]
> Microsoft Store för företag laddar inte ned (push-överför) appar automatiskt till enheter. Dock kan appar från Microsoft Store för företag associeras med din MDM-server (enhetshantering) för att rikta och synkronisera appar till enheter.

Besök följande sidor om du vill veta mer om hur du använder Microsoft Store för företag:

* [Behörighetsnivåer som används för att installera program](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Så här lägger du till en app i Store för företag](/mem/intune/apps/store-apps-windows)
* [Så här tilldelar du appar till grupper av anställda](/mem/intune/apps/windows-store-for-business)

Om du vill associera Microsoft Store för företag kan du [gå till Associera Microsoft Store för företag med Intune](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune).

> [!Tip]
> Läs mer om [att distribuera offline-appar](/microsoft-store/distribute-offline-apps) när du använder appar som Advanced Recovery Companion (ARC) och Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Använd endast privata Store-appar för Microsoft Store

- Introducerades [i Windows Holographic, version 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Principen RequirePrivateStoreOnly har aktiverats för HoloLens. Den här principen gör att Microsoft Store kan konfigureras för att endast visa det privata arkivet som konfigurerats för din organisation. Begränsa åtkomsten till endast de appar som du har gjort tillgängliga.

Läs mer om [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Smart Försök igen för appuppdateringar

- Introducerades [i Windows Holographic, version 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Nu aktiverad för HoloLens är en ny princip som gör att IT-administratörer kan ange ett återkommande datum eller ett engångsdatum för att starta om appar vars uppdatering misslyckades på grund av att appen används och tillåter att uppdateringen tillämpas. Dessa kan ställas in baserat på några olika utlösare, till exempel en schemalagd tid eller inloggning. Mer information om hur du använder den här principen finns i [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)