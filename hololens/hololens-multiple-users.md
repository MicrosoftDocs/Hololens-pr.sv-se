---
title: Dela dina HoloLens med flera personer
description: Du kan konfigurera HoloLens ska delas av flera Azure Active Directory eller av flera användare som använder ett enda konto.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428199"
---
# <a name="share-your-hololens-with-multiple-people"></a>Dela dina HoloLens med flera personer

## <a name="overview"></a>Översikt
Företag investerar ofta i många HoloLens enheter. Hur du använder HoloLens är flexibelt över hela linjen, beroende på dina enskilda krav. Här är ett exempel på några upplevelser för flera användare: 

- Enheter som debiteras och har Dynamics 365-guider och låter dina anställda öppna Inställningar-appen för att göra justeringar i Wi-Fi som behövs, men principen För sid-Inställningar-synlighet har aktiverats för att begränsa mängden sidor som är tillgängliga i Inställningar-appen.
- Enheter som är för Remote Assist och din affärsapp som hyrs till andra företag. Dessa enheter har informationsdatorer som endast innehåller din app och Fjärrhjälp. WDAC används för att Inställningar appen och Microsoft Edge startar. I uthyrningen ingår ett USB-C-batteripaket som ger enheterna full laddning under flera skift.
- Alla dina enheter är konfigurerade för Autopilot och laddar ned alla dina företagsappar. Du har skapat några olika profiler för helskärmsläge med olika Azure AD-grupper som mål. Varje användare loggar in på HoloLens FIDO2-nycklar och loggar in på sitt eget Azure AD-konto och får en skräddarsydd upplevelse.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Dela med flera personer, var och en med sitt eget konto

**Krav:** HoloLens måste köra Windows 10 version 1803 eller senare.  HoloLens (första generationen) måste också [uppgraderas till Windows Holographic for Business](hololens-upgrade-enterprise.md).

När de använder sina Azure Active Directory-konton (Azure AD) kan flera användare behålla sina egna användarinställningar och användardata på enheten.

Om du vill kontrollera att flera personer kan använda sina egna konton på HoloLens, följer du dessa steg för att konfigurera det:

1. Kontrollera att enheten körs med Windows 10 version 1803 eller senare.
   > [!IMPORTANT]
   > Om du använder en HoloLens (första generationens) [uppgraderar du enheten till Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. När du ställer in enheten väljer du Mitt **arbete eller min skola** äger den och loggar in med ett Azure AD-konto.
1. När du är klar med konfigurationenkontrollerar du att kontoinställningarna (  >  **Inställningar-konton**) innehåller **Andra användare**.

Varje användare HoloLens följande steg för att använda den:

1. Om en annan användare har använt enheten väljer du något av följande alternativ:
   - Tryck på strömknappen en gång för att gå till vänteläge och tryck sedan på strömknappen igen för att återgå till låsskärmen
   - HoloLens 2 användare kan välja användarpanelen från Start-menyn för att logga ut den aktuella användaren.

1. Använd dina autentiseringsuppgifter för Azure AD-kontot för att logga in på enheten.  
    Om det är första gången du använder enheten måste du kalibrera den [HoloLens](hololens-calibration.md) dina ögon.

Om du vill se en lista över enhetsanvändare eller ta bort en användare från enheten går du **till Inställningar**  >  **Konton**  >  **Övriga användare.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Dela med flera personer, alla med samma konto

Flera användare kan också dela en HoloLens enhet när du använder ett enda användarkonto.

**På HoloLens 2** uppmanas den nya användaren att snabbt kalibrera och anpassa visningsupplevelsen när en ny användare sätter enheten på huvudet för första gången (samtidigt som samma konto är inloggad). Enheten kan lagra kalibreringsinformationen så att enheten i framtiden automatiskt kan optimera kvaliteten och bekvämligheten för varje användares tittarupplevelse. Användarna behöver inte kalibrera enheten igen.

**På HoloLens (första generationens)** måste användare som delar ett konto be att få omcalibrera i Inställningar appen.  Läs mer om [kalibrering.](hololens-calibration.md)