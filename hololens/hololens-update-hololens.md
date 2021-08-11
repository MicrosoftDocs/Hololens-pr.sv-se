---
title: Uppdatera HoloLens 2
description: Lär dig hur du kontrollerar HoloLens versionsnummer, håller dig uppdaterad med enhetsuppdateringar, går med i Insiders-programmet och återställ uppdateringar.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662830"
---
# <a name="update-hololens-2"></a>Uppdatera HoloLens 2

HoloLens använder Windows Update, precis som andra Windows 10 enheter. Din HoloLens automatiskt hämta och installera systemuppdateringar när den är ansluten till ström och ansluten till Internet, även när den är i vänteläge.

Den här artikeln går igenom HoloLens verktyg för:

- visa din aktuella operativsystemversion (build-nummer)
- söka efter uppdateringar
- uppdatera HoloLens
- gå tillbaka till en äldre uppdatering

## <a name="check-your-operating-system-version-build-number"></a>Kontrollera operativsystemversionen (build-nummer)

Du kan verifiera systemversionsnumret (build-nummer) genom att öppna Inställningar och välja **System**  >  **Om.**

## <a name="check-for-updates-and-manually-update"></a>Söka efter uppdateringar och uppdatera manuellt

Du kan söka efter uppdateringar när som helst i inställningarna.  Så här ser du tillgängliga uppdateringar och söker efter nya uppdateringar:

1. Öppna appen **Inställningar**.
1. Gå till **Update & Security** Windows  >  **Update**.
1. Välj **Sök efter uppdateringar**.

Om en uppdatering är tillgänglig börjar den ladda ned den nya versionen. När nedladdningen är klar väljer du knappen **Starta om nu** för att utlösa installationen. Om enheten är lägre än 40 % och den inte är ansluten kommer omstarten inte att starta om installationen av uppdateringen.

När HoloLens installerar uppdateringen visas snurrande kugghjul och en förloppsindikator. Stäng inte av HoloLens under den här tiden. Den startas om automatiskt när installationen är klar.

HoloLens en uppdatering i taget.  Om din HoloLens är mer än en version bakom den senaste kan du behöva gå igenom uppdateringsprocessen flera gånger för att få den helt uppdaterad.

## <a name="go-back-to-a-previous-version"></a>Gå tillbaka till en tidigare version

I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens programvara. De rekommenderade stegen är:

1. Kontakta supporten för att se om de kan åtgärda problemet.
    1. Se till **att Valfri** **eller Fullständig** telemetri är aktiverat – detta gör buggen mer användbar och enklare för tekniker att diagnostisera.
    1. [Filfeedback](hololens-feedback.md) är så beskrivande som möjligt. Anteckna rubriken eller använd delningsfunktionen så att du kan dela din bugg med supporten.
    1. Kontakta [supporten.](https://aka.ms/hlsupport) Om problemet är ett problem som måste lösas genom att gå tillbaka till en tidigare version kan de tillhandahålla FFU för att flasha enheten.

1. Om det inte fungerar återställer eller [omstreckar du HoloLens 2 med Advanced Recovery Companion](hololens-recovery.md).
    1. På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.
    1. Kontrollera att du inte har några telefoner eller Windows enheter som är anslutna till datorn.
    1. Välj vilken version du vill flasha till:
        1. Du kan ladda ned [den senaste versionen HoloLens 2.](https://aka.ms/hololens2download)
        1. Du kan använda standardbygget som ARC är värd för. (Om du väljer det här alternativet hoppar du över nästa steg.)
        1. Du kan använda ett byggstöd som du har tillgång till.
    1. När du är klar med dessa hämtningar öppnar **du Utforskaren**  >  **hämtningsbara filer.** Högerklicka på den komprimerade mappen som du precis har laddat ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.
    1. Anslut din HoloLens datorn med hjälp av en USB-A-till-USB-C-kabel. (Även om du har använt andra kablar för att ansluta HoloLens fungerar den här bäst.)
    1. Advanced Recovery Companion identifierar automatiskt HoloLens. Välj **Microsoft HoloLens** panelen.
    1. På nästa skärm väljer du **Manuellt paketval** och väljer sedan installationsfilen som finns i mappen som du packade upp i steg 4. (Leta efter en fil med filnamnstillägget .ffu.)
    1. Välj **Installera programvara** och följ instruktionerna.

> [!NOTE]
> Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.

Om du vill fortsätta använda den installerade versionen kan du också pausa uppdateringar [manuellt.](hololens-updates.md#pause-updates-via-device) Detta ger teknikteamet tid att åtgärda problemet.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program på HoloLens

Vill du se de senaste funktionerna i HoloLens?  I så fall ansluter du till Windows Insider Program; du får tillgång till förhandsversioner av HoloLens innan de blir tillgängliga för allmänheten.

[Hämta Windows Insider-förhandsgranskning för Microsoft HoloLens](hololens-insider.md).
