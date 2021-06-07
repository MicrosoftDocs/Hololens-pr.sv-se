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
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="31768-105">Hitta, installera och avinstallera program från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="31768-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="31768-106">Den Microsoft Store är din go-to-källa för appar och spel som fungerar med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="31768-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="31768-107">När du går till Store på din HoloLens körs alla appar som du ser där på den.</span><span class="sxs-lookup"><span data-stu-id="31768-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="31768-108">Appar på HoloLens använder antingen 2D-vy eller holografisk vy.</span><span class="sxs-lookup"><span data-stu-id="31768-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="31768-109">Appar som använder 2D-vyn ser ut som fönster och kan placeras runt dig.</span><span class="sxs-lookup"><span data-stu-id="31768-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="31768-110">Appar som använder den holografiska vyn omger dig och blir den enda app som du ser.</span><span class="sxs-lookup"><span data-stu-id="31768-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="31768-111">HoloLens stöder många befintliga program från Microsoft Store och nya appar som skapats specifikt för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="31768-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="31768-112">Den här artikeln fokuserar på holografiska program från Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="31768-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="31768-113">Mer information om hur du installerar och kör anpassade appar finns i [Anpassade holografiska program.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="31768-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="31768-114">Hitta appar</span><span class="sxs-lookup"><span data-stu-id="31768-114">Find apps</span></span>

<span data-ttu-id="31768-115">Öppna Microsoft Store på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="31768-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="31768-116">Bläddra sedan efter appar och spel.</span><span class="sxs-lookup"><span data-stu-id="31768-116">Then browse for apps and games.</span></span> <span data-ttu-id="31768-117">Du kan använda [röstkommandon](hololens-cortana.md) för att söka genom att säga "Sök". När sökfönstret öppnas säger du "Börja diktera" och sedan när du uppmanas att börja säga dina söktermer.</span><span class="sxs-lookup"><span data-stu-id="31768-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="31768-118">Systemkraven för HoloLens-enheter baseras på arkitekturen i appbygget.</span><span class="sxs-lookup"><span data-stu-id="31768-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="31768-119">Om en appbygge för HoloLens (första generationen) inte har uppdaterats med till en nyare UWP i butiken för att inkludera ARM-arkitekturpaketet är den inte tillgänglig för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="31768-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="31768-120">På samma sätt gäller att om en HoloLens 2-app inte innehåller x86-arkitekturpaketet är den inte tillgänglig för HoloLens-enheter (första generationen).</span><span class="sxs-lookup"><span data-stu-id="31768-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="31768-121">HoloLens-enhetsarkitekturer:</span><span class="sxs-lookup"><span data-stu-id="31768-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="31768-122">x86 = HoloLens (första gen)</span><span class="sxs-lookup"><span data-stu-id="31768-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="31768-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="31768-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="31768-124">Den 12 januari 2021 når följande appar supportens slut på HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="31768-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="31768-125">Vi rekommenderar att du använder följande länk på enheten för att använda webbversionen av appen.</span><span class="sxs-lookup"><span data-stu-id="31768-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="31768-126">App</span><span class="sxs-lookup"><span data-stu-id="31768-126">App</span></span>        | <span data-ttu-id="31768-127">Länk</span><span class="sxs-lookup"><span data-stu-id="31768-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="31768-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="31768-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="31768-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="31768-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="31768-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="31768-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="31768-131">Installera appar</span><span class="sxs-lookup"><span data-stu-id="31768-131">Install apps</span></span>

<span data-ttu-id="31768-132">Om du vill ladda ned appar måste du vara inloggad med en Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="31768-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="31768-133">Vissa appar är kostnadsfria och kan laddas ned direkt.</span><span class="sxs-lookup"><span data-stu-id="31768-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="31768-134">För appar som kräver ett köp måste du vara inloggad på Store med din Microsoft-konto och ha en giltig betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="31768-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="31768-135">Det konto som du använder Microsoft Store måste inte vara samma som det konto som du är inloggad med.</span><span class="sxs-lookup"><span data-stu-id="31768-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="31768-136">Om du använder ett arbets- eller skolkonto på din HoloLens kan du behöva logga in med ditt personliga konto i Store-appen för att göra ett köp.</span><span class="sxs-lookup"><span data-stu-id="31768-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="31768-137">Om du vill konfigurera en betalningsmetod går du [till account.microsoft.com](https://account.microsoft.com/) väljer **Betalningssätt &**  >  **faktureringsalternativ Lägg** till ett  >  **betalningsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="31768-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="31768-138">Öppna [ **Start-menyn** genom att](holographic-home.md)utföra en [startgest eller](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) [bloomgest](hololens1-basic-usage.md) på HoloLens (första generationen).</span><span class="sxs-lookup"><span data-stu-id="31768-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="31768-139">Välj Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="31768-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="31768-140">När Store-appen har öppnats:</span><span class="sxs-lookup"><span data-stu-id="31768-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="31768-141">Använd sökfältet för att söka efter program.</span><span class="sxs-lookup"><span data-stu-id="31768-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="31768-142">Välj viktiga appar eller appar som skapats specifikt för HoloLens från någon av de utvalda kategorierna.</span><span class="sxs-lookup"><span data-stu-id="31768-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="31768-143">Längst upp till höger i Store-appen väljer du **knappen "..."** och sedan Mitt bibliotek **för** att visa alla tidigare köpta appar.</span><span class="sxs-lookup"><span data-stu-id="31768-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="31768-144">Välj **Hämta** **eller Installera** på programmets sida (ett köp kan krävas).</span><span class="sxs-lookup"><span data-stu-id="31768-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="31768-145">Uppdatera appar</span><span class="sxs-lookup"><span data-stu-id="31768-145">Update Apps</span></span>

<span data-ttu-id="31768-146">Om du vill uppdatera en app som Microsoft Store installerat från datorn kan du uppdatera appen från Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="31768-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="31768-147">För appar som installerats för Microsoft Store för företag kan du även uppdatera dessa appar från Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="31768-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="31768-148">Öppna [ **Start-menyn** genom att](holographic-home.md)utföra en [startgest eller](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) [bloomgest](hololens1-basic-usage.md) på HoloLens (första generationen).</span><span class="sxs-lookup"><span data-stu-id="31768-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="31768-149">Välj Store-appen.</span><span class="sxs-lookup"><span data-stu-id="31768-149">Select the Store app.</span></span>

1. <span data-ttu-id="31768-150">Titta längst upp till höger i Store-appen.</span><span class="sxs-lookup"><span data-stu-id="31768-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="31768-151">Välj knappen **"..."** eller "Visa mer".</span><span class="sxs-lookup"><span data-stu-id="31768-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31768-152">![Microsoft Store skärmbild av appen.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="31768-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="31768-153">Välj **Nedladdningar och uppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="31768-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="31768-154">Om enheten tidigare har identifierat uppdateringar kan det finnas en nedåtpil och ett tal som representerar väntande uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="31768-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="31768-155">Välj **Hämta uppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="31768-155">Select **Get updates**.</span></span> <span data-ttu-id="31768-156">Enheten söker nu efter uppdateringar och anger att de ska laddas ned och installeras.</span><span class="sxs-lookup"><span data-stu-id="31768-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31768-157">![Microsoft Store skärmbild av att hämta uppdateringar..](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="31768-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="31768-158">Om apparna på din enhet har distribuerats av din organisation kan de uppdateras via samma kommersiella apphanteringsmetoder.</span><span class="sxs-lookup"><span data-stu-id="31768-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="31768-159">Om detta gäller din situation kan du läsa mer via vår [översikt över distribution av kommersiella appar.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="31768-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="31768-160">Om du vill uppdatera en anpassad app som har separat inläst eller distribuerats måste du använda samma metod med den uppdaterade versionen av appen.</span><span class="sxs-lookup"><span data-stu-id="31768-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="31768-161">Mer information om hur du installerar och kör anpassade appar finns i [Anpassade holografiska program.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="31768-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="31768-162">Avinstallera appar</span><span class="sxs-lookup"><span data-stu-id="31768-162">Uninstall apps</span></span>

<span data-ttu-id="31768-163">Det finns tre sätt att avinstallera program.</span><span class="sxs-lookup"><span data-stu-id="31768-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="31768-164">Du kan avinstallera program via Microsoft Store, Start-menyn eller från Inställningar.</span><span class="sxs-lookup"><span data-stu-id="31768-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="31768-165">Du kan inte avinstallera en systemapp eller Microsoft Store själv.</span><span class="sxs-lookup"><span data-stu-id="31768-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31768-166">Om din HoloLens 2 har flera användare måste du vara inloggad som den användare som installerade appen för att avinstallera den.</span><span class="sxs-lookup"><span data-stu-id="31768-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="31768-167">Avinstallera från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="31768-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="31768-168">Öppna Microsoft Store **startmenyn** och bläddra sedan efter det program som du vill avinstallera.</span><span class="sxs-lookup"><span data-stu-id="31768-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="31768-169">Varje installerat program har en avinstallationsknapp på **sidan** Butik.</span><span class="sxs-lookup"><span data-stu-id="31768-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="31768-170">Avinstallera från Start-menyn</span><span class="sxs-lookup"><span data-stu-id="31768-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="31768-171">På **Start-menyn** eller i **Alla appar** bläddrar du till appen.</span><span class="sxs-lookup"><span data-stu-id="31768-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="31768-172">Välj och håll kvar tills menyn visas och välj sedan **Avinstallera.**</span><span class="sxs-lookup"><span data-stu-id="31768-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="31768-173">Avinstallera från inställningar</span><span class="sxs-lookup"><span data-stu-id="31768-173">Uninstall from Settings</span></span>
<span data-ttu-id="31768-174">På **Start-menyn** väljer du **Inställningar -> Appar.**</span><span class="sxs-lookup"><span data-stu-id="31768-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="31768-175">Leta upp appen i listan, markera den och klicka sedan på **Avinstallera.**</span><span class="sxs-lookup"><span data-stu-id="31768-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="31768-176">Om du inte kan avinstallera en app kan du skicka [feedback med](https://docs.microsoft.com/hololens/hololens-feedback) hjälp av Feedbackhubben.</span><span class="sxs-lookup"><span data-stu-id="31768-176">If you are unable to uninstall an app, please file [feedback](https://docs.microsoft.com/hololens/hololens-feedback) using the Feedback Hub.</span></span>
