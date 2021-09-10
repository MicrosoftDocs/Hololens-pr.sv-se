---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – Underhåll
description: Lär dig hur du underhåller HoloLens 2 enheter över ett företagsanslutna nätverk med Dynamics 365-guider.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Enhetshantering
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428773"
---
# <a name="maintain---corporate-connected-guide"></a>Underhåll – Företagsansluten guide

## <a name="update-hololens"></a>Uppdatera HoloLens

Microsoft har utformat Windows Update för företag för att ge IT-administratörer ytterligare Windows Update-centrerade hanteringsfunktioner, till exempel möjligheten att distribuera uppdateringar till grupper av enheter och definiera underhåll windows för installation av uppdateringar.

En populär metod för att hantera uppdateringar är att skjuta upp funktioner i 30 dagar. På så sätt kan administratörer uppdatera och förhandsgranska nya funktioner, få förstahandskunskaper och informera supportavdelningen om eventuella nya ändringar.

Lär dig hur [du hanterar HoloLens uppdateringar,](/hololens/hololens-updates)inklusive schemalagda dagar, schemalagd tid och inställning av aktiva timmar på enheten, så att den uppdateras utanför arbetstid.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Uppdatera Dynamics 365-guider (och andra Store-appar)

Dynamics 365-guider är In-Box app och kan uppdateras via Microsoft Store appen. För alla appar som laddas ned via Microsoft Store kan de [uppdateras via själva Microsoft Store](/hololens/holographic-store-apps#update-apps) manuellt.

## <a name="how-to-update-lob-apps"></a>Så här uppdaterar du LOB-appar

LOB-appar kan uppdateras på samma sätt som de lades till i Intune. Appar kan uppdateras i Intune genom att ladda upp den nya appen med ett högre versionsnummer till den befintliga appkonfigurationen. När enheten synkroniseras med Intune ser du att det finns en nyare appversion och att den nyare appen laddas ned och ersätts av den gamla appen.

1. Om du vill ladda upp den nyare appen går du till [MEM-portalen](https://endpoint.microsoft.com/#home)Appar -> Alla appar  ->     ->  *TheNameOfDappegenskaper.*  ->  
2. Bredvid Appinformation väljer du **Redigera.**
3. För värdet för &quot; Välj fil att uppdatera väljer du &quot; filen.
4. Härifrån kan du använda snabbmenyn för att öppna Utforskaren och ladda upp den nyare versionen av LOB-appen. Se till att inkludera beroenden efter behov.

Se mer: [Intune-appdistribution för HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Utvecklingsplan

När enheten har registrerats är du nu redo att distribuera fler LOB-appar till dina enheter. I den här guiden använder vi en exempelapp, men det är mer troligt att du vill använda anpassade appar som skapats för din organisations behov.

Om du redan har en LOB-app är du redo att [distribuera din app via MDM.](/hololens/app-deploy-intune) Om du föredrar en annan metod kan du läsa översikten över programdistributionen [för HoloLens 2](/hololens/app-deploy-overview) för att lära dig fler metoder för att distribuera din LOB-app till dina enheter.

Om du ännu inte har skapat din egen LOB-app eller om du fortfarande håller på att skapa den, kan du läsa våra dokument om utveckling av mixad verklighet för att börja utforma och [skapa prototyper](/windows/mixed-reality/design/design) eller lära dig de grundläggande begreppen för att komma igång med utveckling med [mixad verklighet.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Supportplan

En supportplan är utmärkt att ha på plats. Det är användbart att ha någon, eller en grupp, tränad på att felsöka registreringsprocessen på HoloLens-enheter och även allmän användning av HoloLens i din organisation. För att användarna ska kunna lösa sina problem snabbare föreslår vi att eskaleringsprocessen hanteras på ett liknande sätt som i den här ordningen:

1. Supportavdelningen.
2. Ditt HoloLens Expert-team
3. [HoloLens Docs](/hololens/)  /  [HoloLens felsökningsdokument](/hololens/hololens-troubleshooting)
4. [Kontakta supporten](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Enhetshantering

Den här guiden talade om att konfigurera Mobile Enhetshantering (MDM) och använde den för att konfigurera vissa enhetskonfigurationer och tillämpa inställningar för att tillåta åtkomst när det gäller Wi-Fi certifikat och proxy. MDM kan dock också användas för att tillämpa enhetsbegränsningar via CPS och principer.

I många fall kan enheter ha anslutningsbegränsningar, till exempel Bluetooth VPN, USB eller till och med inaktivera åtkomst till kameran eller mikrofonen. Om du är intresserad av något av dessa intressen rekommenderar vi att du läser vår [vanliga sida om enhetsbegränsningar.](/hololens/hololens-common-device-restrictions)

Det finns andra mer komplexa enhetsbegränsningar som du kan använda. Exempel:

- Begränsa de sidor som kan visas i Inställningar-appen med hjälp av [SettingsPageVisibility](/hololens/settings-uri-list), så att användarna bara kan komma åt de inställningar som de behöver justera, till exempel ändra Wi-Fi anslutning.
- Använd [helskärmsläge](/hololens/hololens-kiosk) för att begränsa användargränssnittet som visas för användare på en enhet. Du kan ange Helskärmsläge för att visa en enda app eller flera appar med en anpassad startsida. Kiosker kan också presentera olika upplevelser för olika användare.
- [Windows programkontroll (WDAC) för](/hololens/windows-defender-application-control-wdac) att hålla specifika appar eller processer från att starta helt.

Om du vill veta mer om ytterligare metoder för enhetshantering eller enhetsbegränsningar kan du ta nästa steg och läsa [vår Enhetshantering Översikt](/hololens/hololens-csp-policy-overview).





