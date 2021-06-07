---
title: Dela din HoloLens med flera personer
description: Du kan konfigurera HoloLens så att det delas av Azure Active Directory konton eller av flera användare som använder ett enda konto.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378831"
---
# <a name="share-your-hololens-with-multiple-people"></a>Dela din HoloLens med flera personer

Det är vanligt att dela en HoloLens med många personer eller att många personer delar en uppsättning HoloLens-enheter.  Den här artikeln beskriver de olika sätt som du kan dela en enhet på.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Dela med flera personer, var och en med sitt eget konto

**Krav:** HoloLens-enheten måste köra Windows 10 version 1803 eller senare.  HoloLens (1:a gen) måste också [uppgraderas till Windows Holographic for Business](hololens-upgrade-enterprise.md).

När de använder sina egna Azure Active Directory-konton (Azure AD) kan flera användare behålla sina egna användarinställningar och användardata på enheten.

Följ dessa steg för att konfigurera det för att se till att flera personer kan använda sina egna konton på din HoloLens:

1. Kontrollera att enheten körs med Windows 10 version 1803 eller senare.
   > [!IMPORTANT]
   > Om du använder en HoloLens-enhet (första generationens) [uppgraderar du enheten till Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. När du ställer in enheten väljer du Mitt **arbete eller min skola** äger den och loggar in med ett Azure AD-konto.
1. När du är klar med installationenkontrollerar du att kontoinställningarna (  >  **Inställningar)** innehåller **Andra användare**.

Om du vill använda HoloLens följer varje användare dessa steg:

1. Om en annan användare har använt enheten gör du något av följande:
   - Tryck på strömknappen en gång för att gå till vänteläge och tryck sedan på strömknappen igen för att återgå till låsskärmen
   - HoloLens 2-användare kan välja användarpanelen från Start-menyn för att logga ut den aktuella användaren.

1. Använd autentiseringsuppgifterna för ditt Azure AD-konto för att logga in på enheten.  
    Om det är första gången du använder enheten måste du [kalibrera](hololens-calibration.md) HoloLens till dina egna ögon.

Om du vill se en lista över enhetsanvändare eller ta bort en användare från enheten går du till **Inställningar**  >  **Konton**  >  **Andra användare.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Dela med flera personer, alla med samma konto

Flera användare kan också dela en HoloLens-enhet när du använder ett enda användarkonto.

**På HoloLens 2** uppmanar enheten den nya användaren att snabbt kalibrera och anpassa visningsupplevelsen när en ny användare sätter enheten på huvudet för första gången (samtidigt som samma konto är inloggad). Enheten kan lagra kalibreringsinformationen så att enheten i framtiden automatiskt kan optimera kvaliteten och bekvämligheten för varje användares tittarupplevelse. Användarna behöver inte kalibrera enheten igen.

**På HoloLens (första generationens)** måste användare som delar ett konto be att omcalibrera i appen Inställningar.  Läs mer om [kalibrering.](hololens-calibration.md)
