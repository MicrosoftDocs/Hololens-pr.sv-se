---
title: Konfigurera HoloLens 2
description: Lär dig hur du set up your HoloLens 2 for the first time over Wi-Fi network with a Microsoft (MSA) or Azure Active Directory (AAD) account (AAD) (Konfigurera HoloLens 2 för första gången över Wi-Fi-nätverk med antingen ett Microsoft-konto (MSA) eller Azure Active Directory-konto (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380090"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="1dcd1-104">Konfigurera HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1dcd1-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="1dcd1-105">Första gången du aktiverar HoloLens vägleds du genom att konfigurera din enhet, logga in med ett användarkonto och styra HoloLens till dina ögon.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="1dcd1-106">Det här avsnittet går igenom den första installationsupplevelsen för HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="1dcd1-107">I nästa avsnitt får du lära dig hur du arbetar med HoloLens och interagerar med hologram.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="1dcd1-108">Om du vill gå vidare till den artikeln kan [du läsa Komma igång med HoloLens 2.](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="1dcd1-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="1dcd1-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1dcd1-109">Before you start</span></span>

<span data-ttu-id="1dcd1-110">Kontrollera att du har följande tillgängligt innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="1dcd1-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="1dcd1-111">**En nätverksanslutning**.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-111">**A network connection**.</span></span> <span data-ttu-id="1dcd1-112">Du måste ansluta HoloLens till ett nätverk för att konfigurera det.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="1dcd1-113">Med HoloLens 2 kan du ansluta med Wi-Fi eller via Ethernet (du behöver en USB-C-till-Ethernet-adapter).</span><span class="sxs-lookup"><span data-stu-id="1dcd1-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="1dcd1-114">Första gången du ansluter behöver du ett öppet eller lösenordsskyddat nätverk som inte kräver att du navigerar till en webbplats eller använder certifikat för att ansluta.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="1dcd1-115">[Läs mer om de webbplatser som HoloLens använder.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="1dcd1-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="1dcd1-116">**En Microsoft-konto**.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-116">**A Microsoft account**.</span></span> <span data-ttu-id="1dcd1-117">Du måste också logga in på HoloLens med en Microsoft-konto (eller med ditt arbetskonto om din organisation äger enheten).</span><span class="sxs-lookup"><span data-stu-id="1dcd1-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="1dcd1-118">Om du inte har ett Microsoft-konto går du till [account.microsoft.com](https://account.microsoft.com) och ställer in ett kostnadsfritt.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="1dcd1-119">**Ett säkert, välbelyst utrymme utan problem.**</span><span class="sxs-lookup"><span data-stu-id="1dcd1-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="1dcd1-120">[Information om hälsa och säkerhet](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="1dcd1-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="1dcd1-121">**De valfria bekväma tillbehören** som medkom med hololens för att hjälpa dig att få den mest bekväma formen.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="1dcd1-122">[Mer om passning och bekvämlighet.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="1dcd1-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="1dcd1-123">Konfigurera Windows</span><span class="sxs-lookup"><span data-stu-id="1dcd1-123">Set up Windows</span></span>

<span data-ttu-id="1dcd1-124">Första gången du startar HoloLens 2 är din första uppgift att konfigurera Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="1dcd1-125">När du startar HoloLens kommer du att höra musik och se en Windows-logotyp.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Första skärmen under den första starten](images/01-magic-moment.png)

<span data-ttu-id="1dcd1-127">HoloLens 2 går igenom följande steg:</span><span class="sxs-lookup"><span data-stu-id="1dcd1-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="1dcd1-128">Välj språk.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-128">Select your language.</span></span>

    ![Välj språk](images/04-language.png)

1. <span data-ttu-id="1dcd1-130">Välj din region.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-130">Select your region.</span></span>

    ![Välj region](images/05-region.png)

1. <span data-ttu-id="1dcd1-132">Kalibrera HoloLens till dina ögon.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="1dcd1-133">Om du väljer att hoppa över kalibreringen uppmanas du att göra det nästa gång du loggar in.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="1dcd1-134">För att kalibrera tittar du på en uppsättning mål (kallas gems).</span><span class="sxs-lookup"><span data-stu-id="1dcd1-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="1dcd1-135">Det går bra om du blinkar eller stänger ögonen under kalibreringen, men försök att inte titta på andra objekt i rummet eller det fysiska utrymmet.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="1dcd1-136">HoloLens använder den här processen för att lära sig om din ögonposition så att den bättre kan återge din holografiska värld.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="1dcd1-137">Efter kalibreringen visas hologram korrekt även när visor-programmet skiftar på huvudet.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="1dcd1-138">Kalibreringsinformation lagras lokalt på enheten och är inte associerad med någon kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="1dcd1-139">Mer information finns i [Kalibreringsdata och säkerhet.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="1dcd1-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Skärmen Val av kalibrering](images/06-et-corners.png)

1. <span data-ttu-id="1dcd1-141">Anslut till Internet (välj Wi-Fi eller Ethernet-anslutning).</span><span class="sxs-lookup"><span data-stu-id="1dcd1-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="1dcd1-142">HoloLens anger tidszonen automatiskt baserat på information som hämtas från Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="1dcd1-143">När installationen är klar kan du ändra tidszonen med hjälp av appen Inställningar.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Ansluta till Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="1dcd1-145">Om du fortsätter förbi Wi-Fi-steget och senare behöver växla till ett annat nätverk  medan du fortfarande är konfigurerad kan du trycka på knapparna Volym ned och **Ström** samtidigt för att återgå till det här steget om du kör en operativsystemversion från oktober 2019 eller senare.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="1dcd1-146">För tidigare versioner kan [](hololens-recovery.md) du behöva återställa enheten eller starta om den på en plats där Wi-Fi inte är tillgängligt för att förhindra att den ansluter automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="1dcd1-147">Observera också att det finns en tidsgräns för autentiseringsuppgifter på två minuter under installationen av HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="1dcd1-148">Användarnamnet/lösenordet måste anges inom två minuter, annars rensas fältet användarnamn automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="1dcd1-149">Logga in på ditt användarkonto.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-149">Sign in to your user account.</span></span> <span data-ttu-id="1dcd1-150">Du väljer mellan Mitt **arbete eller min skola äger det och** jag äger **det**.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="1dcd1-151">När du väljer **Mitt arbete eller min skola äger det** loggar du in med ett Azure AD-konto.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="1dcd1-152">Om din organisation använder Azure AD Premium och har konfigurerat automatisk MDM-registrering registreras HoloLens automatiskt i MDM.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="1dcd1-153">Om din organisation inte använder Azure AD Premium är automatisk MDM-registrering inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="1dcd1-154">I så fall måste du manuellt [registrera HoloLens i enhetshanteringen](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="1dcd1-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="1dcd1-155">Ange din organisations kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="1dcd1-156">Godkänn sekretesspolicyn och licensavtalet för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="1dcd1-157">Logga in med dina autentiseringsuppgifter för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="1dcd1-158">Detta kan omdirigeras till din organisations inloggningssida.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="1dcd1-159">Fortsätt att konfigurera enheten.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-159">Continue setting up the device.</span></span>

    - <span data-ttu-id="1dcd1-160">När du väljer **Jag äger den** loggar du in med en Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="1dcd1-161">När installationen är klar kan du [manuellt registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="1dcd1-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="1dcd1-162">Ange din Microsoft-konto information.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="1dcd1-163">Ange ditt lösenord.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-163">Enter your password.</span></span> <span data-ttu-id="1dcd1-164">Om ditt Microsoft-konto [tvåstegsverifiering (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)slutför du verifieringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Ange användare](images/13-device-owner.png)

1. <span data-ttu-id="1dcd1-166">Välj om du vill aktivera tal på HoloLens 2 och om du vill skicka diagnostiktelemetri.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>

    ![Aktivera Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="1dcd1-168">Välj telemetrinivå.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-168">Select your telemetry level.</span></span> <span data-ttu-id="1dcd1-169">Om det går aktiverar du Fullständig telemetri.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="1dcd1-170">Den här informationen hjälper verkligen HoloLens-teknikteamet.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-170">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetrinivå](images/24-telemetry.png)

1. <span data-ttu-id="1dcd1-172">Lär dig hur du använder startgesten på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-172">Learn how to use the start gesture on HoloLens 2.</span></span>

     <span data-ttu-id="1dcd1-173">![Lär dig hur du använder startgesten bild 1 ](images/26-01-startmenu-learning.png) ![ Lär dig hur du använder startgesten, bild 2](images/26-02-startmenu-learning.png)</span><span class="sxs-lookup"><span data-stu-id="1dcd1-173">![Learn how to use the start gesture, image 1](images/26-01-startmenu-learning.png) ![Learn how to use the start gesture, image 2](images/26-02-startmenu-learning.png)</span></span>

<span data-ttu-id="1dcd1-174">Grattis!</span><span class="sxs-lookup"><span data-stu-id="1dcd1-174">Congratulations!</span></span>  <span data-ttu-id="1dcd1-175">Installationen är klar och du är redo att använda HoloLens!</span><span class="sxs-lookup"><span data-stu-id="1dcd1-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="1dcd1-176">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1dcd1-176">Next steps</span></span>

1. <span data-ttu-id="1dcd1-177">Börja interagera direkt med Mixed Reality och navigera Windows 10 på din HoloLens – kolla in **tipsappen** för praktiska självstudier för handinteraktioner.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-177">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="1dcd1-178">Använd startgesten för att gå till Start eller säg "Gå till Start" och välj Tips.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="1dcd1-179">Klicka nedan för att fortsätta läsa om att komma runt HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1dcd1-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1dcd1-180">Kom igång med HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1dcd1-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
