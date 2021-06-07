---
title: Översikt över att konfigurera Enhetshantering och Enhetshantering
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378866"
---
# <a name="configure-csps-and-device-management-overview"></a>Översikt över att konfigurera Enhetshantering och Enhetshantering

IT-administratörer kan definiera och implementera principinställningar på HoloLens 2. Vilka konfigurationsinställningar du använder skiljer sig åt beroende på distributionsscenariot, och företagsenheter kommer att erbjuda IT det bredaste kontrollintervallet. I Windows 10 är CSP:er (Configuration Service Providers) ett gränssnitt för att läsa, ange, ändra eller ta bort konfigurationsinställningar på enheten. De här inställningarna mappar till registernycklar eller filer. Vissa konfigurationstjänstleverantörer stöder WAP-formatet, vissa stöder SyncML och vissa stöder båda.

Mer information om hur du Windows 10 Holographic för enhetshantering finns i den fullständiga listan över [CP:er som stöds i HoloLens-enheter.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
IT-administratörer kan också hantera princip-CSP på enheter. Se den fullständiga listan över princip-CSP:er som [stöds av HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Konfigurationsmetoder

### <a name="configure-with-mdm"></a>Konfigurera med MDM

CSP:er och principer kan enkelt hanteras på alla personliga enheter eller företagsenhet som registrerats i ett MDM-system. När en enhet har registrerats i MDM-lösningen kan du hantera den enheten eller en uppsättning enheter med hjälp av enhetskonfigurationer. Läs mer om hur du [hanterar dina HoloLens-enheter via MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurera med etableringspaket

HoloLens 2 stöder också inställning av en begränsad uppsättning CSP-konfigurationer för HoloLens 2-enheter via anpassade etableringspaket. Etableringspaket används vanligtvis för icke-MDM-hanterade enheter och måste tillämpas manuellt på varje enhet. Läs information om hur du skapar [anpassade etableringspaket för HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## <a name="configurations"></a>Konfigurationer

### <a name="common-device-restrictions"></a>Vanliga enhetsbegränsningar

Vissa enhetsbegränsningar är så enkla och inaktiverar en funktion eller anslutning till enheten. Mer information om dessa finns i vanliga [enhetsbegränsningar.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Helskärmsläge

Använd helskärmsläge för att styra vilka identiteter som har åtkomst till vilka appar som standard. Helskärmsläge kan användas för en enda app eller flera appars användargränssnitt. Kioskkonfigurationer sträcker sig från en enda app för alla som använder enheten till olika val av appar för olika grupper. Helskärmsläge stoppar inte "tillåtna appar" från att starta andra appar och var inte avsett att någonsin. Läs mer genom [att läsa om helskärmsläge och hur du använder dem.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Sidsynlighet för inställningar

Använd appprincipen Inställningar för att styra vilka identiteter som har åtkomst till inställningar som standard. Med den här principen kan appen Inställningar konfigureras för att antingen endast visa de valda sidorna eller dölja alla valda sidor. [Läs mer om hur du konfigurerar de tillgängliga sidorna.](settings-uri-list.md)

Den här funktionen är för närvarande endast tillgänglig [i Windows Insider skapar](hololens-insider.md). Se till att enheter som du tänker använda den här funktionen för finns på version 19041.1349+.

### <a name="wdac"></a>WDAC

Använd WDAC-konfigurationen för att kontrollera vilka appar/processer som tillåts/tillåts inte startas oavsett om systemet är i helskärmsläge eller inte.
[Se vår översikt för WDAC.](windows-defender-application-control-wdac.md)
