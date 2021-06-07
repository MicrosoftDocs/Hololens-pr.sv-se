---
title: Uppdatera HoloLens
description: Lär dig hur du kontrollerar ditt HoloLens-versionsnummer, håller dig uppdaterad med enhetsuppdateringar, går med i Insiders-programmet och återställningsuppdateringar.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378822"
---
# <a name="update-hololens"></a>Uppdatera HoloLens

HoloLens använder Windows Update, precis som andra Windows 10 enheter. HoloLens laddar automatiskt ned och installerar systemuppdateringar när den är ansluten till ström och ansluten till Internet, även när den är i vänteläge.

Den här artikeln går igenom HoloLens-verktyg för:

- visa din aktuella operativsystemversion (build-nummer)
- söka efter uppdateringar
- uppdatera HoloLens manuellt
- gå tillbaka till en äldre uppdatering

## <a name="check-your-operating-system-version-build-number"></a>Kontrollera operativsystemversionen (build-nummer)

Du kan verifiera systemversionsnumret (build-nummer) genom att öppna appen Inställningar och välja **System**  >  **About (System om).**

## <a name="check-for-updates-and-manually-update"></a>Söka efter uppdateringar och uppdatera manuellt

Du kan söka efter uppdateringar när som helst i inställningarna.  Så här ser du tillgängliga uppdateringar och söker efter nya uppdateringar:

1. Öppna appen **Inställningar**.
1. Gå till **Update & Security**  >  **Windows Update**.
1. Välj **Sök efter uppdateringar**.

Om en uppdatering är tillgänglig börjar den ladda ned den nya versionen. När nedladdningen är klar väljer du knappen **Starta om nu** för att utlösa installationen. Om enheten är lägre än 40 % och den inte är ansluten kommer omstarten inte att starta om installationen av uppdateringen.

När hololens installerar uppdateringen visas snurrande kugghjul och en förloppsindikator. Stäng inte av hololens under den här tiden. Den startas om automatiskt när installationen är klar.

HoloLens tillämpar en uppdatering i taget.  Om din HoloLens är mer än en version bakom den senaste kan du behöva gå igenom uppdateringsprocessen flera gånger för att få den helt uppdaterad.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Gå tillbaka till en tidigare version – HoloLens 2

I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens-programvaran. Du kan göra detta med hjälp av Advanced Recovery Companion för att återställa din HoloLens till den tidigare versionen.

> [!NOTE]
> Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.

Följ dessa steg om du vill gå tillbaka till en tidigare version av HoloLens 2:

1. Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.
1. På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.
1. Ladda ned [den senaste HoloLens 2-versionen](https://aka.ms/hololens2download).
1. När du är klar med dessa nedladdningar öppnar du **Hämtningsbara filer**  >  **i Utforskaren.** Högerklicka på den komprimerade mappen som du precis har laddat ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.
1. Anslut din HoloLens till datorn med hjälp av en USB-A till USB-C-kabel. (Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)
1. Advanced Recovery Companion identifierar automatiskt din HoloLens. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuellt paketval** och väljer sedan installationsfilen som finns i mappen som du packade upp i steg 4. (Leta efter en fil med filnamnstillägget .ffu.)
1. Välj **Installera programvara** och följ instruktionerna.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Gå tillbaka till en tidigare version – HoloLens (första gen)

I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens-programvaran. Du kan göra detta med hjälp av återställningsverktyget för Windows-enheter för att återställa din HoloLens till den tidigare versionen.

> [!NOTE]
> Om du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.

Följ dessa steg om du vill gå tillbaka till en tidigare version av HoloLens 1:

1. Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.
1. Ladda ned Windows [Device Recovery Tool (WDRT) på datorn.](https://support.microsoft.com/help/12379)
1. Ladda ned [holoLens Anniversary Update-återställningspaketet](https://aka.ms/hololensrecovery).
1. När hämtningarna är klara öppnar du  >  **Hämtningsbara filer i Utforskaren.** Högerklicka på den komprimerade mappen som du precis laddade ned och välj **Extrahera alla extrahera**  >  **för** att packa upp den.
1. Anslut din HoloLens till datorn med hjälp av den mikro-USB-kabel som den medkom med. (Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här bäst.)
1. WDRT identifierar automatiskt din HoloLens. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuellt paketval och** väljer installationsfilen i mappen som du packade upp i steg 4. (Leta efter en fil med filnamnstillägget .ffu.)
1. Välj **Installera programvara** och följ instruktionerna.

> [!NOTE]
> Om WDRT inte identifierar hololens kan du prova att starta om datorn. Om det inte fungerar väljer du **Min enhet identifierades inte,** **Microsoft HoloLens** och följer sedan anvisningarna.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program på HoloLens

Vill du se de senaste funktionerna i HoloLens?  I så fall ansluter du till Windows Insider Program; du får tillgång till förhandsversioner av HoloLens-programuppdateringar innan de blir tillgängliga för allmänheten.

[Hämta Windows Insider förhandsgranskning för Microsoft HoloLens](hololens-insider.md).
