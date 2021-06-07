---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Underhåll
description: Håll dig uppdaterad med våra tips för att underhålla och stödja HoloLens-enheter i ett molnanslutet nätverk.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Enhetshantering
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378879"
---
# <a name="maintain---cloud-connected-guide"></a>Underhåll – Molnansluten guide

## <a name="updates"></a>Uppdateringar

Microsoft har Windows Update för företag för att ge IT-administratörer ytterligare Windows Update-centrerade hanteringsfunktioner, till exempel möjligheten att distribuera uppdateringar till grupper av enheter och definiera underhåll windows för installation av uppdateringar.

Lär dig hur [du hanterar HoloLens-uppdateringar,](https://docs.microsoft.com/hololens/hololens-updates) inklusive schemalagda dagar, schemalagd tid och inställning av aktiva timmar på enheten så att den uppdateras utanför arbetstid.

Remote Assist är In-Box app och kan uppdateras via Microsoft Store appen. För alla appar som laddas ned via Microsoft Store de uppdateras [via själva Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) manuellt.

## <a name="support-plan"></a>Supportplan

En supportplan är utmärkt att ha på plats. Det är användbart att ha någon eller en grupp tränad på att felsöka registreringsprocessen på HoloLens-enheter och även allmän användning av HoloLens-enheten i din organisation. För att dina användare ska kunna lösa sina problem snabbare föreslår vi att eskaleringsprocessen hanteras på ett liknande sätt som i den här ordningen:

1. Supportavdelningen.
2. Ditt HoloLens Expert-team
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Felsökningsdokument för HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Kontakta supporten](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Utvecklingsplan

Nu när enheten har registrerats är du redo att distribuera verksamhetsapplikationer (LOB-appar) till dina enheter. Det här är anpassade appar som skapats för&#39;organisationens behov.

Om du redan har en verksamhetslinjeapp är&#39;redo att [distribuera din app via MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Om du&#39;föredrar en annan metod kan du läsa översikten över programdistributionen för [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) för att lära dig fler metoder för att distribuera din LOB-app till dina enheter.

Om du&#39;har skapat en egen LOB-app eller om du fortfarande håller på att skapa den kan du läsa våra utvecklingsdokument för mixad verklighet för att börja utforma och [skapa prototyper](https://docs.microsoft.com/windows/mixed-reality/design/design) eller lära dig huvudbegreppen för att komma igång med utveckling med [mixad verklighet.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Enhetshantering 

Den här guiden talade om att konfigurera Mobile Enhetshantering (MDM) men den användes inte för att tillämpa enhetsbegränsningar eller principer tillämpades på enheter. Enhetshantering kan användas både för att tillåta åtkomst genom att push-certifikat, eller begränsa åtkomst med en mängd olika enhetsbegränsningar. 

I många fall kan enheter ha anslutningsbegränsningar som Bluetooth, VPN, USB eller till och med stänga av åtkomst till kameran eller mikrofonen. Om du är intresserad av detta rekommenderar vi att du läser vår [vanliga sida om enhetsbegränsningar.](hololens-common-device-restrictions.md)

Det finns andra mer komplexa enhetsbegränsningar som du kan använda. Exempel:

- Begränsa de sidor som kan visas i appen Inställningar med hjälp av [InställningarPageVisibility,](settings-uri-list.md)så att användarna bara kan komma åt de inställningar som de behöver justera, till exempel ändra deras Wi-Fi anslutning.
- Använd [helskärmsläge](hololens-kiosk.md) för att begränsa användargränssnittet som visas för användare på en enhet. Du kan ange Helskärmsläge för att visa en enda app eller flera appar med en anpassad startsida. Kiosker kan också presentera olika upplevelser för olika användare.  
- [Windows Application Control (WDAC) för](windows-defender-application-control-wdac.md) att hålla specifika appar eller processer från att starta helt.

Om du vill veta mer om fler olika metoder för enhetshantering eller enhetsbegränsningar kan du ta nästa steg och läsa vår Enhetshantering Översikt.

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Läs översikten över CPS och Enhetshantering](hololens-csp-policy-overview.md)