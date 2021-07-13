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
# <a name="set-up-your-hololens-2"></a>Konfigurera din HoloLens 2

Första gången du aktiverar din HoloLens vägleds du genom att konfigurera din enhet, logga in med ett användarkonto och HoloLens dina ögon.  Det här avsnittet går igenom HoloLens 2 första konfigurationsupplevelsen.

I nästa avsnitt får du lära dig hur du arbetar med HoloLens och interagerar med hologram. Om du vill gå vidare till den artikeln kan [du läsa Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Innan du börjar

Kontrollera att du har följande tillgängligt innan du börjar:

**En nätverksanslutning**. Du måste ansluta din dator HoloLens ett nätverk för att konfigurera den. Med HoloLens 2 kan du ansluta med Wi-Fi eller via Ethernet (du behöver en USB-C-till-Ethernet-adapter). Första gången du ansluter behöver du ett öppet eller lösenordsskyddat nätverk som inte kräver att du navigerar till en webbplats eller använder certifikat för att ansluta. [Läs mer om de webbplatser som HoloLens använder](hololens-offline.md).

**En Microsoft-konto**. Du måste också logga in på HoloLens med en Microsoft-konto (eller med ditt arbetskonto, om din organisation äger enheten). Om du inte har ett Microsoft-konto går du till [account.microsoft.com](https://account.microsoft.com) och ställer in ett kostnadsfritt.

**Ett säkert, välbelyst utrymme utan problem.** [Information om hälsa och säkerhet](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**De valfria** bekvämlighetsaccessoarerna som HoloLens för att hjälpa dig att få den mest bekväma formen. [Mer om passning och bekvämlighet.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Konfigurera Windows

Första gången du startar din HoloLens 2 är din första uppgift att konfigurera Windows Holographic.  När du startar HoloLens du musik och ser en Windows logotyp.

![Första skärmen under den första starten](images/01-magic-moment.png)

Du kommer att se en upptrassandebird som går runt.

![Mingbird-flyg](images/hummingbird-1.png)

Följ den med din hand.

![Mingbird som går på när närmre](images/hummingbird-2.png)

HoloLens 2 går du igenom följande steg:

1. Välj språk.

    ![Välj språk](images/04-language.png)

1. Välj din region.

    ![Välj region](images/05-region.png)

1. Kalibrera HoloLens för dina ögon.  Om du väljer att hoppa över kalibreringen uppmanas du att göra det nästa gång du loggar in. 

    1. Först justerar du ditt visor-programmet.
    
        ![Skärmen Val av kalibrering](images/06-et-corners.png)

    2. För att kalibrera tittar du på en uppsättning mål (kallas gems). Det går bra om du blinkar eller stänger ögonen under kalibreringen, men försök att inte titta på andra objekt i rummet eller det fysiska utrymmet. HoloLens använder den här processen för att lära dig om din ögonposition så att den bättre kan återge din holografiska värld. 

        ![Justera för dina ögon](images/07-adjust-eyes.png)

        Efter kalibreringen visas hologram korrekt även när visor-programmet skiftar på huvudet. Kalibreringsinformation lagras lokalt på enheten och är inte associerad med någon kontoinformation. Mer information finns i [Kalibreringsdata och säkerhet.](hololens-calibration.md#calibration-data-and-security)

        ![Kalibreringen är klar](images/calibration-complete.png)

1. Anslut till Internet (välj Wi-Fi eller Ethernet-anslutning).

     HoloLens anger tidszonen automatiskt baserat på information som hämtas från Wi-Fi nätverk. När installationen är klar kan du ändra tidszonen med hjälp av Inställningar appen.

    ![Ansluta till Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Om du fortsätter förbi Wi-Fi-steget och senare behöver växla till ett annat nätverk  medan du fortfarande är konfigurerad kan du trycka på knapparna Volym ned och **Ström** samtidigt för att återgå till det här steget om du kör en operativsystemversion från oktober 2019 eller senare. För tidigare versioner kan [](hololens-recovery.md) du behöva återställa enheten eller starta om den på en plats där Wi-Fi inte är tillgängligt för att förhindra att den ansluter automatiskt.
    > 
    > Observera också att det HoloLens tidsgränsen för autentiseringsuppgifter på två minuter under installationen. Användarnamnet/lösenordet måste anges inom två minuter, annars rensas fältet användarnamn automatiskt.

1. HoloLens 2 söker och tillämpar en Autopilot-profil om det finns en sådan. Ingen åtgärd krävs på den här skärmen.
 
    ![Autopilot-profilsökning](images/autopilot-profile-search.png) 

1. Klicka **på** Acceptera på licensieringsskärmen.

    ![Windows-licensavtalet](images/windows-license-agreement.png)

1. Logga in på ditt användarkonto. Du väljer mellan Mitt **arbete eller min skola äger det och** jag äger **det**.

    ![Ange användare](images/13-device-owner.png)
    - När du väljer **Mitt arbete eller min skola äger det** loggar du in med ett Azure AD-konto. Om din organisation använder Azure AD Premium och har konfigurerat automatisk MDM-HoloLens registreras automatiskt i MDM. Om din organisation inte använder Azure AD Premium är automatisk MDM-registrering inte tillgänglig. I så fall måste du manuellt [registrera HoloLens i enhetshanteringen](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Ange din organisations kontoinformation.
        1. Godkänn sekretesspolicyn och licensavtalet för slutanvändare.
        1. Logga in med dina autentiseringsuppgifter för Azure AD. Detta kan omdirigeras till din organisations inloggningssida.
        1. Fortsätt att konfigurera enheten.

    - När du väljer **Jag äger den** loggar du in med en Microsoft-konto. När installationen är klar kan du [manuellt registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Ange din Microsoft-konto information.
        2. Ange ditt lösenord. Om ditt Microsoft-konto [tvåstegsverifiering (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)slutför du verifieringsprocessen.

        
1. Konfigurera Iris-inloggning genom att välja **Nästa.** Du kommer att gå igenom en upplevelse som liknar ögonavsening. Välj **Klar** när genomsökningen är klar. Du kan också välja Hoppa **över för** att kringgå det här steget.
    
    ![Iris-installationen ](images/setup-iris.png) ![ Iris-installationen har slutförts](images/iris-setup-complete.png) 
     
  
1. Du kommer att konfigurera en PIN-kod för att logga in på enheten. Den här PIN-koden är enhetsspecifik. 

    ![Konfigurera Windows Hello](images/setup-windows-hello.png)

    ![Konfigurera PIN Windows Hello kod](images/windows-hello-pin.png)

    ![Windows Hello Installationen lyckades](images/windows-hello-successful.png) 
    
1. Välj om du vill aktivera tal HoloLens 2.

    ![Aktivera Cortana](images/22-do-more-with-voice.png)

1. Välj om du vill aktivera plats HoloLens 2.
    
    ![Aktivera platstjänster](images/setup-location-services.png)

1. Välj telemetrinivå. Om det går aktiverar du Valfri telemetri. Den här informationen hjälper HoloLens teknikteamet.

     ![Telemetrinivå](images/24-telemetry.png)

1. Lär dig hur du använder startgesten på HoloLens 2.

     ![Lär dig hur du använder startgesten, bild 1](images/26-01-startmenu-learning.png)

     ![Lär dig hur du använder startgesten, bild 2](images/26-02-startmenu-learning.png)

Grattis!  Installationen är klar och du är redo att använda HoloLens!

## <a name="next-steps"></a>Nästa steg

1. Börja interagera direkt med Mixed Reality och navigera Windows 10 på din HoloLens – kolla **in Tips-appen** för praktiska självstudier för handinteraktioner. Använd startgesten för att gå till Start eller säg "Gå till start" och välj Tips.

1. Klicka nedan för att fortsätta läsa om att komma runt HoloLens 2.

> [!div class="nextstepaction"]
> [Ta sig runt i HoloLens 2](hololens2-basic-usage.md)
