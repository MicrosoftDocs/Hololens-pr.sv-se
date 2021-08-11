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
ms.openlocfilehash: 6f50874c39d8bffa43ff94101c81dcffe3dc1b3c34c69e940ed503dc7bd8b4ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659254"
---
# <a name="set-up-your-hololens-2"></a>Konfigurera din HoloLens 2

Första gången du aktiverar din HoloLens vägleds du genom att konfigurera din enhet, logga in med ett användarkonto och HoloLens dina ögon.  Det här avsnittet går igenom HoloLens 2 första konfigurationsupplevelsen.

I nästa avsnitt får du lära dig hur du arbetar med HoloLens och interagerar med hologram. Om du vill gå vidare till den här artikeln [kan du läsa getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Innan du börjar

Kontrollera att du har följande tillgängligt innan du börjar:

**En nätverksanslutning**. Du måste ansluta din dator HoloLens ett nätverk för att konfigurera den. Med HoloLens 2 kan du ansluta med Wi-Fi eller med ethernet (du behöver en USB-C-till-Ethernet-adapter). Första gången du ansluter behöver du ett öppet eller lösenordsskyddat nätverk som inte kräver att du navigerar till en webbplats eller använder certifikat för att ansluta. [Läs mer om de webbplatser som HoloLens använder](hololens-offline.md).

**En Microsoft-konto**. Du måste också logga in på HoloLens med en Microsoft-konto (eller med ditt arbetskonto, om din organisation äger enheten). Om du inte har ett Microsoft-konto går du till [account.microsoft.com](https://account.microsoft.com) och ställer in ett kostnadsfritt.

**Ett säkert, välbelyst utrymme utan problem.** [Information om hälsa och säkerhet](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**De valfria** bekvämlighetsaccessoarerna som HoloLens för att hjälpa dig att få den mest bekväma passningen. [Mer om passning och bekvämlighet.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Konfigurera Windows

Första gången du startar ditt HoloLens 2 är din första uppgift att konfigurera Windows Holographic.  När du startar ditt HoloLens kommer du att höra musik och se en Microsoft-logotyp.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Du kommer att se en nystandebird som går runt.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Den följer din hand.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

En knapp med en Microsoft-logotyp visas. Tryck på knappen så HoloLens 2 dig igenom följande steg:

1. Välj språk.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Välj din region.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Kalibrera HoloLens dina ögon.  Om du väljer att hoppa över kalibreringen uppmanas du nästa gång du loggar in. 

    1. Först justerar du ditt visir.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. För att kalibrera tittar du på en uppsättning mål (kallas gems). Det går bra om du blinkar eller stänger ögonen under kalibreringen, men försök att inte titta på andra objekt i rummet eller det fysiska utrymmet. HoloLens använder den här processen för att lära dig mer om ögonpositionen så att den bättre kan återge den holografiska världen. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Efter kalibreringen visas hologram korrekt även när visor-programmet skiftar på huvudet. Kalibreringsinformation lagras lokalt på enheten och är inte associerad med någon kontoinformation. Mer information finns i [Kalibreringsdata och säkerhet.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Anslut till Internet (välj Wi-Fi eller ethernet-anslutning).

     HoloLens anger tidszonen automatiskt baserat på information som hämtas från Wi-Fi nätverk. När installationen är klar kan du ändra tidszonen med hjälp av Inställningar appen.

    ![Ansluta till Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Om du fortsätter förbi Wi-Fi-steget och senare behöver växla till ett annat nätverk  medan du  fortfarande är konfigurerad, kan du trycka på knapparna Volym ned och Ström samtidigt för att återgå till det här steget om du kör en os-version från oktober 2019 eller senare. För tidigare versioner kan [](hololens-recovery.md) du behöva återställa enheten eller starta om den på en plats där Wi-Fi inte är tillgängligt för att förhindra att den ansluter automatiskt.
    > 
    > Observera också att under HoloLens installation finns en tidsgräns för autentiseringsuppgifter på två minuter. Användarnamnet/lösenordet måste anges inom två minuter, annars rensas fältet för användarnamn automatiskt.

1. HoloLens 2 söker och tillämpar en Autopilot-profil om det finns en sådan. Ingen åtgärd krävs på den här skärmen.
 
    ![Autopilot-profilsökning](images/autopilot-profile-search.png) 

1. Klicka **på** Acceptera på licensieringsskärmen.

    ![Windows-licensavtalet](images/windows-license-agreement.png)

1. Logga in på ditt användarkonto. Du väljer mellan Mitt **arbete eller min skola äger det och** jag äger **det**.

    ![Ange användare](images/13-device-owner.png)
    - När du väljer **Mitt arbete eller min skola äger det** loggar du in med ett Azure AD-konto. Om din organisation använder Azure AD Premium och har konfigurerat automatisk MDM-HoloLens registreras automatiskt i MDM. Om din organisation inte använder Azure AD Premium är automatisk MDM-registrering inte tillgänglig. I så fall måste du manuellt [registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Ange din organisations kontoinformation.
        1. Godkänn sekretesspolicyn och licensavtalet.
        1. Logga in med dina autentiseringsuppgifter för Azure AD. Detta kan omdirigeras till din organisations inloggningssida.
        1. Fortsätt att konfigurera enheten.

    - När du väljer **Jag äger den** loggar du in med en Microsoft-konto. När installationen är klar kan du [manuellt registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Ange din Microsoft-konto information.
        2. Ange ditt lösenord. Om ditt Microsoft-konto [tvåstegsverifiering (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)slutför du verifieringsprocessen.

        
1. Konfigurera Iris-inloggning genom att välja **Nästa.** Du kommer att gå igenom en upplevelse som liknar ögonrekeliken. Välj **Klar** när genomsökningen är klar. Du kan också välja Hoppa **över för** att kringgå det här steget.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Du kommer att konfigurera en PIN-kod för att logga in på enheten. Den här PIN-koden är enhetsspecifik. 

    ![Konfigurera Windows Hello](images/setup-windows-hello.png)

    ![Konfigurera PIN Windows Hello kod](images/windows-hello-pin.png)

    ![Windows Hello Installationen lyckades](images/windows-hello-successful.png) 

    
1. Välj om du vill aktivera tal HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Välj om du vill aktivera plats HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Välj telemetrinivå. Om det går aktiverar du Valfri telemetri. Den här informationen hjälper verkligen HoloLens tekniska teamet.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Lär dig hur du använder startgesten på HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Grattis!  Installationen är klar och du är redo att använda HoloLens!

## <a name="next-steps"></a>Nästa steg

1. Börja interagera direkt med Mixed Reality och navigera Windows 10 på din HoloLens – kolla **in Tips-appen** för praktiska självstudier för handinteraktioner. Använd startgesten för att gå till Start eller säg "Gå till start" och välj Tips.

1. Klicka nedan för att fortsätta läsa om att komma runt HoloLens 2.

> [!div class="nextstepaction"]
> [Ta sig runt i HoloLens 2](hololens2-basic-usage.md)
