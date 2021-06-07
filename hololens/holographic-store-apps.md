---
title: Hitta, installera och avinstallera program
description: Den Microsoft Store är din källa för appar och spel som fungerar med HoloLens.  Läs mer om att hitta, installera och avinstallera holografiska appar.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380011"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Hitta, installera och avinstallera program från Microsoft Store

Den Microsoft Store är din go-to-källa för appar och spel som fungerar med HoloLens. När du går till Store på din HoloLens körs alla appar som du ser där på den.

Appar på HoloLens använder antingen 2D-vy eller holografisk vy. Appar som använder 2D-vyn ser ut som fönster och kan placeras runt dig. Appar som använder den holografiska vyn omger dig och blir den enda app som du ser.

HoloLens stöder många befintliga program från Microsoft Store och nya appar som skapats specifikt för HoloLens.  Den här artikeln fokuserar på holografiska program från Microsoft Store.

Mer information om hur du installerar och kör anpassade appar finns i [Anpassade holografiska program.](holographic-custom-apps.md)

## <a name="find-apps"></a>Hitta appar

Öppna Microsoft Store på **Start-menyn.** Bläddra sedan efter appar och spel. Du kan använda [röstkommandon](hololens-cortana.md) för att söka genom att säga "Sök". När sökfönstret öppnas säger du "Börja diktera" och sedan när du uppmanas att börja säga dina söktermer.

> [!NOTE]
> Systemkraven för HoloLens-enheter baseras på arkitekturen i appbygget. Om en appbygge för HoloLens (första generationen) inte har uppdaterats med till en nyare UWP i butiken för att inkludera ARM-arkitekturpaketet är den inte tillgänglig för HoloLens 2-enheter. På samma sätt gäller att om en HoloLens 2-app inte innehåller x86-arkitekturpaketet är den inte tillgänglig för HoloLens-enheter (första generationen). HoloLens-enhetsarkitekturer:
> - x86 = HoloLens (första gen)
> - ARM = HoloLens 2

> [!NOTE]
> Den 12 januari 2021 når följande appar supportens slut på HoloLens-enheter. Vi rekommenderar att du använder följande länk på enheten för att använda webbversionen av appen.

| App        | Länk                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint Mobile | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>Installera appar

Om du vill ladda ned appar måste du vara inloggad med en Microsoft-konto. Vissa appar är kostnadsfria och kan laddas ned direkt. För appar som kräver ett köp måste du vara inloggad på Store med din Microsoft-konto och ha en giltig betalningsmetod.

> [!NOTE]
> Det konto som du använder Microsoft Store måste inte vara samma som det konto som du är inloggad med. Om du använder ett arbets- eller skolkonto på din HoloLens kan du behöva logga in med ditt personliga konto i Store-appen för att göra ett köp.

> [!TIP]
> Om du vill konfigurera en betalningsmetod går du [till account.microsoft.com](https://account.microsoft.com/) väljer **Betalningssätt &**  >  **faktureringsalternativ Lägg** till ett  >  **betalningsalternativ**.

1. Öppna [ **Start-menyn** genom att](holographic-home.md)utföra en [startgest eller](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) [bloomgest](hololens1-basic-usage.md) på HoloLens (första generationen).

1. Välj Microsoft Store app. När Store-appen har öppnats:
   1. Använd sökfältet för att söka efter program. 
   1. Välj viktiga appar eller appar som skapats specifikt för HoloLens från någon av de utvalda kategorierna.
   1. Längst upp till höger i Store-appen väljer du **knappen "..."** och sedan Mitt bibliotek **för** att visa alla tidigare köpta appar.

1. Välj **Hämta** **eller Installera** på programmets sida (ett köp kan krävas).

## <a name="update-apps"></a>Uppdatera appar

Om du vill uppdatera en app som Microsoft Store installerat från datorn kan du uppdatera appen från Microsoft Store appen. För appar som installerats för Microsoft Store för företag kan du även uppdatera dessa appar från Microsoft Store för företag. 

1. Öppna [ **Start-menyn** genom att](holographic-home.md)utföra en [startgest eller](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) [bloomgest](hololens1-basic-usage.md) på HoloLens (första generationen).

1. Välj Store-appen.

1. Titta längst upp till höger i Store-appen. 

1. Välj knappen **"..."** eller "Visa mer".

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store skärmbild av appen.](images/store-update-1.png)

1. Välj **Nedladdningar och uppdateringar.**
    1. Om enheten tidigare har identifierat uppdateringar kan det finnas en nedåtpil och ett tal som representerar väntande uppdateringar.

1. Välj **Hämta uppdateringar.** Enheten söker nu efter uppdateringar och anger att de ska laddas ned och installeras. 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store skärmbild av att hämta uppdateringar..](images/store-update-2.png.jpg)

> [!NOTE]
> Om apparna på din enhet har distribuerats av din organisation kan de uppdateras via samma kommersiella apphanteringsmetoder. Om detta gäller din situation kan du läsa mer via vår [översikt över distribution av kommersiella appar.](app-deploy-overview.md)
>
> Om du vill uppdatera en anpassad app som har separat inläst eller distribuerats måste du använda samma metod med den uppdaterade versionen av appen. Mer information om hur du installerar och kör anpassade appar finns i [Anpassade holografiska program.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Avinstallera appar

Det finns tre sätt att avinstallera program. Du kan avinstallera program via Microsoft Store, Start-menyn eller från Inställningar. 

> [!WARNING]
> Du kan inte avinstallera en systemapp eller Microsoft Store själv.

> [!IMPORTANT]
> Om din HoloLens 2 har flera användare måste du vara inloggad som den användare som installerade appen för att avinstallera den. 

### <a name="uninstall-from-the-microsoft-store"></a>Avinstallera från Microsoft Store

Öppna Microsoft Store **startmenyn** och bläddra sedan efter det program som du vill avinstallera.  Varje installerat program har en avinstallationsknapp på **sidan** Butik.

### <a name="uninstall-from-the-start-menu"></a>Avinstallera från Start-menyn

På **Start-menyn** eller i **Alla appar** bläddrar du till appen. Välj och håll kvar tills menyn visas och välj sedan **Avinstallera.**

### <a name="uninstall-from-settings"></a>Avinstallera från inställningar
På **Start-menyn** väljer du **Inställningar -> Appar.** Leta upp appen i listan, markera den och klicka sedan på **Avinstallera.**

Om du inte kan avinstallera en app kan du skicka [feedback med](https://docs.microsoft.com/hololens/hololens-feedback) hjälp av Feedbackhubben.
