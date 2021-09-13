---
title: Översikt över hur du konfigurerar Enhetshantering och Enhetshantering konfigurationsleverantörer
description: Lär dig hur du konfigurerar CPS, princip- och enhetshantering med mobiler Enhetshantering och etableringspaket.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032941"
---
# <a name="configure-csps-and-device-management-overview"></a>Översikt över hur du konfigurerar Enhetshantering och Enhetshantering konfigurationsleverantörer

IT-administratörer kan definiera och implementera principinställningar på HoloLens 2. Vilka konfigurationsinställningar du använder skiljer sig åt beroende på distributionsscenariot, och företagsenheter erbjuder IT det bredaste kontrollintervallet. I Windows 10 är CSP:er (Configuration Service Providers) ett gränssnitt för att läsa, ange, ändra eller ta bort konfigurationsinställningar på enheten. De här inställningarna mappar till registernycklar eller filer. Vissa konfigurationstjänstleverantörer stöder WAP-formatet, vissa stöder SyncML och vissa stöder båda.

Mer information om hur du Windows 10 Holographic för enhetshantering finns i den fullständiga listan över [CPS](/windows/client-management/mdm/configuration-service-provider-reference#hololens)som stöds i HoloLens enheter .
IT-administratörer kan också hantera princip-CSP på enheter. Se den fullständiga listan med princip-CSP:er som [stöds av HoloLens 2.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Konfigurationsmetoder

### <a name="configure-with-mdm"></a>Konfigurera med MDM

CPS och principer kan enkelt hanteras på alla personliga enheter eller företagsenhet som har registrerats i ett MDM-system. När en enhet har registrerats i MDM-lösningen kan du hantera den enheten eller en uppsättning enheter med hjälp av enhetskonfigurationer. Läs mer om hur du [hanterar dina HoloLens-enheter via MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurera med etableringspaket

HoloLens 2 stöder också inställning av en begränsad uppsättning CSP-konfigurationer för HoloLens 2-enheter via anpassade etableringspaket. Etableringspaket används vanligtvis för icke-MDM-hanterade enheter och måste tillämpas manuellt på varje enhet. Läs information om hur du skapar [anpassade etableringspaket för HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Konfigurationer

### <a name="common-device-restrictions"></a>Vanliga enhetsbegränsningar

Vissa enhetsbegränsningar är lika enkla och inaktiverar en funktion eller anslutning till enheten. Mer information om dessa finns i vanliga [enhetsbegränsningar.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Helskärmsläge

Använd helskärmsläge för att styra vilka identiteter som har åtkomst till vilka appar som standard. Helskärmsläge kan användas för en enda app eller flera appars användargränssnitt. Kioskkonfigurationer sträcker sig från en enda app för alla som använder enheten till olika val av appar för olika grupper. Helskärmsläge stoppar inte "tillåtna appar" från att starta andra appar och var inte avsett att någonsin. Läs mer genom [att läsa om helskärmsläge och hur du använder dem.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Inställningar Sidsynlighet

Använd Inställningar för att styra vilka identiteter som har åtkomst till inställningar som standard. Med den här principen Inställningar app konfigureras för att antingen endast visa de valda sidorna eller dölja alla valda sidor. [Läs mer om hur du konfigurerar tillgängliga sidor.](settings-uri-list.md)

Den här funktionen är för närvarande endast [tillgänglig i Windows Insider-versionerna](hololens-insider.md). Kontrollera att enheter som du tänker använda den här funktionen för finns i version 19041.1349+.

### <a name="wdac"></a>WDAC

Använd WDAC-konfigurationen för att kontrollera vilka appar/processer som tillåts/tillåts inte startas oavsett om systemet är i helskärmsläge eller inte.
[Se vår översikt för WDAC.](windows-defender-application-control-wdac.md)
