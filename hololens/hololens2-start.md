---
title: Konfigurera din HoloLens 2
description: Lär dig att konfigurera din HoloLens 2 för första gången över Wi-Fi-nätverk med antingen ett Microsoft-konto (MSA) eller Azure Active Directory-konto (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636804"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="82f5c-104">Konfigurera din HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="82f5c-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="82f5c-105">Första gången du aktiverar din HoloLens vägleds du genom att konfigurera din enhet, logga in med ett användarkonto och HoloLens dina ögon.</span><span class="sxs-lookup"><span data-stu-id="82f5c-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="82f5c-106">Det här avsnittet går igenom HoloLens 2 första konfigurationsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="82f5c-107">I nästa avsnitt får du lära dig hur du arbetar med HoloLens och interagerar med hologram.</span><span class="sxs-lookup"><span data-stu-id="82f5c-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="82f5c-108">Om du vill gå vidare till den artikeln kan [du läsa Getting around HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="82f5c-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="82f5c-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="82f5c-109">Before you start</span></span>

<span data-ttu-id="82f5c-110">Kontrollera att du har följande tillgängligt innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="82f5c-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="82f5c-111">**En nätverksanslutning**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-111">**A network connection**.</span></span> <span data-ttu-id="82f5c-112">Du måste ansluta din dator HoloLens ett nätverk för att konfigurera den.</span><span class="sxs-lookup"><span data-stu-id="82f5c-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="82f5c-113">Med HoloLens 2 kan du ansluta med Wi-Fi eller via Ethernet (du behöver en USB-C-till-Ethernet-adapter).</span><span class="sxs-lookup"><span data-stu-id="82f5c-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="82f5c-114">Första gången du ansluter behöver du ett öppet eller lösenordsskyddat nätverk som inte kräver att du navigerar till en webbplats eller använder certifikat för att ansluta.</span><span class="sxs-lookup"><span data-stu-id="82f5c-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="82f5c-115">[Läs mer om de webbplatser som HoloLens använder](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="82f5c-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="82f5c-116">**En Microsoft-konto**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-116">**A Microsoft account**.</span></span> <span data-ttu-id="82f5c-117">Du måste också logga in på HoloLens med en Microsoft-konto (eller med ditt arbetskonto, om din organisation äger enheten).</span><span class="sxs-lookup"><span data-stu-id="82f5c-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="82f5c-118">Om du inte har ett Microsoft-konto går du till [account.microsoft.com](https://account.microsoft.com) och ställer in ett kostnadsfritt.</span><span class="sxs-lookup"><span data-stu-id="82f5c-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="82f5c-119">**Ett säkert, välbelyst utrymme utan problem.**</span><span class="sxs-lookup"><span data-stu-id="82f5c-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="82f5c-120">[Information om hälsa och säkerhet](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="82f5c-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="82f5c-121">**De valfria** bekvämlighetsaccessoarerna som HoloLens för att hjälpa dig att få den mest bekväma formen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="82f5c-122">[Mer om passning och bekvämlighet.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="82f5c-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="82f5c-123">Konfigurera Windows</span><span class="sxs-lookup"><span data-stu-id="82f5c-123">Set up Windows</span></span>

<span data-ttu-id="82f5c-124">Första gången du startar din HoloLens 2 är din första uppgift att konfigurera Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="82f5c-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="82f5c-125">När du startar HoloLens du musik och ser en Windows logotyp.</span><span class="sxs-lookup"><span data-stu-id="82f5c-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Första skärmen under den första starten](images/01-magic-moment.png)

<span data-ttu-id="82f5c-127">Du kommer att se en upptrassandebird som går runt.</span><span class="sxs-lookup"><span data-stu-id="82f5c-127">You will see a hummingbird flying around.</span></span>

![Mingbird-flyg](images/hummingbird-1.png)

<span data-ttu-id="82f5c-129">Följ den med din hand.</span><span class="sxs-lookup"><span data-stu-id="82f5c-129">Follow it with your hand.</span></span>

![Mingbird som går på när närmre](images/hummingbird-2.png)

<span data-ttu-id="82f5c-131">HoloLens 2 går du igenom följande steg:</span><span class="sxs-lookup"><span data-stu-id="82f5c-131">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="82f5c-132">Välj språk.</span><span class="sxs-lookup"><span data-stu-id="82f5c-132">Select your language.</span></span>

    ![Välj språk](images/04-language.png)

1. <span data-ttu-id="82f5c-134">Välj din region.</span><span class="sxs-lookup"><span data-stu-id="82f5c-134">Select your region.</span></span>

    ![Välj region](images/05-region.png)

1. <span data-ttu-id="82f5c-136">Kalibrera HoloLens för dina ögon.</span><span class="sxs-lookup"><span data-stu-id="82f5c-136">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="82f5c-137">Om du väljer att hoppa över kalibreringen uppmanas du att göra det nästa gång du loggar in.</span><span class="sxs-lookup"><span data-stu-id="82f5c-137">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="82f5c-138">Först justerar du ditt visor-programmet.</span><span class="sxs-lookup"><span data-stu-id="82f5c-138">First, you'll adjust your visor.</span></span>
    
        ![Skärmen Val av kalibrering](images/06-et-corners.png)

    2. <span data-ttu-id="82f5c-140">För att kalibrera tittar du på en uppsättning mål (kallas gems).</span><span class="sxs-lookup"><span data-stu-id="82f5c-140">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="82f5c-141">Det går bra om du blinkar eller stänger ögonen under kalibreringen, men försök att inte titta på andra objekt i rummet eller det fysiska utrymmet.</span><span class="sxs-lookup"><span data-stu-id="82f5c-141">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="82f5c-142">HoloLens använder den här processen för att lära dig om din ögonposition så att den bättre kan återge din holografiska värld.</span><span class="sxs-lookup"><span data-stu-id="82f5c-142">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Justera för dina ögon](images/07-adjust-eyes.png)

        <span data-ttu-id="82f5c-144">Efter kalibreringen visas hologram korrekt även när visor-programmet skiftar på huvudet.</span><span class="sxs-lookup"><span data-stu-id="82f5c-144">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="82f5c-145">Kalibreringsinformation lagras lokalt på enheten och är inte associerad med någon kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="82f5c-145">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="82f5c-146">Mer information finns i [Kalibreringsdata och säkerhet.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="82f5c-146">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Kalibreringen är klar](images/calibration-complete.png)

1. <span data-ttu-id="82f5c-148">Anslut till Internet (välj Wi-Fi eller Ethernet-anslutning).</span><span class="sxs-lookup"><span data-stu-id="82f5c-148">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="82f5c-149">HoloLens anger tidszonen automatiskt baserat på information som hämtas från Wi-Fi nätverk.</span><span class="sxs-lookup"><span data-stu-id="82f5c-149">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="82f5c-150">När installationen är klar kan du ändra tidszonen med hjälp av Inställningar appen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-150">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Ansluta till Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="82f5c-152">Om du fortsätter förbi Wi-Fi-steget och senare behöver växla till ett annat nätverk  medan du fortfarande är konfigurerad kan du trycka på knapparna Volym ned och **Ström** samtidigt för att återgå till det här steget om du kör en operativsystemversion från oktober 2019 eller senare.</span><span class="sxs-lookup"><span data-stu-id="82f5c-152">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="82f5c-153">För tidigare versioner kan [](hololens-recovery.md) du behöva återställa enheten eller starta om den på en plats där Wi-Fi inte är tillgängligt för att förhindra att den ansluter automatiskt.</span><span class="sxs-lookup"><span data-stu-id="82f5c-153">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="82f5c-154">Observera också att det HoloLens tidsgränsen för autentiseringsuppgifter på två minuter under installationen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-154">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="82f5c-155">Användarnamnet/lösenordet måste anges inom två minuter, annars rensas fältet användarnamn automatiskt.</span><span class="sxs-lookup"><span data-stu-id="82f5c-155">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="82f5c-156">HoloLens 2 söker och tillämpar en Autopilot-profil om det finns en sådan.</span><span class="sxs-lookup"><span data-stu-id="82f5c-156">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="82f5c-157">Ingen åtgärd krävs på den här skärmen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-157">No action is needed on this screen.</span></span>
 
    ![Autopilot-profilsökning](images/autopilot-profile-search.png) 

1. <span data-ttu-id="82f5c-159">Klicka **på** Acceptera på licensieringsskärmen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-159">Click **Accept** on the licensing screen.</span></span>

    ![Windows-licensavtalet](images/windows-license-agreement.png)

1. <span data-ttu-id="82f5c-161">Logga in på ditt användarkonto.</span><span class="sxs-lookup"><span data-stu-id="82f5c-161">Sign in to your user account.</span></span> <span data-ttu-id="82f5c-162">Du väljer mellan Mitt **arbete eller min skola äger det och** jag äger **det**.</span><span class="sxs-lookup"><span data-stu-id="82f5c-162">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    ![Ange användare](images/13-device-owner.png)
    - <span data-ttu-id="82f5c-164">När du väljer **Mitt arbete eller min skola äger det** loggar du in med ett Azure AD-konto.</span><span class="sxs-lookup"><span data-stu-id="82f5c-164">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="82f5c-165">Om din organisation använder Azure AD Premium och har konfigurerat automatisk MDM-HoloLens registreras automatiskt i MDM.</span><span class="sxs-lookup"><span data-stu-id="82f5c-165">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="82f5c-166">Om din organisation inte använder Azure AD Premium är automatisk MDM-registrering inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="82f5c-166">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="82f5c-167">I så fall måste du manuellt [registrera HoloLens i enhetshanteringen](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="82f5c-167">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="82f5c-168">Ange din organisations kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="82f5c-168">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="82f5c-169">Godkänn sekretesspolicyn och licensavtalet för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="82f5c-169">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="82f5c-170">Logga in med dina autentiseringsuppgifter för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82f5c-170">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="82f5c-171">Detta kan omdirigeras till din organisations inloggningssida.</span><span class="sxs-lookup"><span data-stu-id="82f5c-171">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="82f5c-172">Fortsätt att konfigurera enheten.</span><span class="sxs-lookup"><span data-stu-id="82f5c-172">Continue setting up the device.</span></span>

    - <span data-ttu-id="82f5c-173">När du väljer **Jag äger den** loggar du in med en Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="82f5c-173">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="82f5c-174">När installationen är klar kan du [manuellt registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="82f5c-174">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="82f5c-175">Ange din Microsoft-konto information.</span><span class="sxs-lookup"><span data-stu-id="82f5c-175">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="82f5c-176">Ange ditt lösenord.</span><span class="sxs-lookup"><span data-stu-id="82f5c-176">Enter your password.</span></span> <span data-ttu-id="82f5c-177">Om ditt Microsoft-konto [tvåstegsverifiering (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)slutför du verifieringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="82f5c-177">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

        
1. <span data-ttu-id="82f5c-178">Konfigurera Iris-inloggning genom att välja **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="82f5c-178">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="82f5c-179">Du kommer att gå igenom en upplevelse som liknar ögonavsening.</span><span class="sxs-lookup"><span data-stu-id="82f5c-179">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="82f5c-180">Välj **Klar** när genomsökningen är klar.</span><span class="sxs-lookup"><span data-stu-id="82f5c-180">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="82f5c-181">Du kan också välja Hoppa **över för** att kringgå det här steget.</span><span class="sxs-lookup"><span data-stu-id="82f5c-181">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="82f5c-182">![Iris-installationen ](images/setup-iris.png) ![ Iris-installationen har slutförts](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="82f5c-182">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="82f5c-183">Du kommer att konfigurera en PIN-kod för att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="82f5c-183">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="82f5c-184">Den här PIN-koden är enhetsspecifik.</span><span class="sxs-lookup"><span data-stu-id="82f5c-184">This PIN is device specific.</span></span> 

    ![Konfigurera Windows Hello](images/setup-windows-hello.png)

    ![Konfigurera PIN Windows Hello kod](images/windows-hello-pin.png)

    ![Windows Hello Installationen lyckades](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="82f5c-188">Välj om du vill aktivera tal HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="82f5c-188">Select whether to enable speech on HoloLens 2.</span></span>

    ![Aktivera Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="82f5c-190">Välj om du vill aktivera plats HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="82f5c-190">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Aktivera platstjänster](images/setup-location-services.png)

1. <span data-ttu-id="82f5c-192">Välj telemetrinivå.</span><span class="sxs-lookup"><span data-stu-id="82f5c-192">Select your telemetry level.</span></span> <span data-ttu-id="82f5c-193">Om det går aktiverar du Valfri telemetri.</span><span class="sxs-lookup"><span data-stu-id="82f5c-193">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="82f5c-194">Den här informationen hjälper HoloLens teknikteamet.</span><span class="sxs-lookup"><span data-stu-id="82f5c-194">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetrinivå](images/24-telemetry.png)

1. <span data-ttu-id="82f5c-196">Lär dig hur du använder startgesten på HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="82f5c-196">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Lär dig hur du använder startgesten, bild 1](images/26-01-startmenu-learning.png)

     ![Lär dig hur du använder startgesten, bild 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="82f5c-199">Grattis!</span><span class="sxs-lookup"><span data-stu-id="82f5c-199">Congratulations!</span></span>  <span data-ttu-id="82f5c-200">Installationen är klar och du är redo att använda HoloLens!</span><span class="sxs-lookup"><span data-stu-id="82f5c-200">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="82f5c-201">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="82f5c-201">Next steps</span></span>

1. <span data-ttu-id="82f5c-202">Börja interagera direkt med Mixed Reality och navigera Windows 10 på din HoloLens – kolla **in Tips-appen** för praktiska självstudier för handinteraktioner.</span><span class="sxs-lookup"><span data-stu-id="82f5c-202">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="82f5c-203">Använd startgesten för att gå till Start eller säg "Gå till start" och välj Tips.</span><span class="sxs-lookup"><span data-stu-id="82f5c-203">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="82f5c-204">Klicka nedan för att fortsätta läsa om att komma runt HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="82f5c-204">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="82f5c-205">Ta sig runt i HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="82f5c-205">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
