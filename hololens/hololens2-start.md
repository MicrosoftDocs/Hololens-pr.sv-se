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
# <a name="set-up-your-hololens-2"></a>Konfigurera HoloLens 2

Första gången du aktiverar HoloLens vägleds du genom att konfigurera din enhet, logga in med ett användarkonto och styra HoloLens till dina ögon.  Det här avsnittet går igenom den första installationsupplevelsen för HoloLens 2.

I nästa avsnitt får du lära dig hur du arbetar med HoloLens och interagerar med hologram. Om du vill gå vidare till den artikeln kan [du läsa Komma igång med HoloLens 2.](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Innan du börjar

Kontrollera att du har följande tillgängligt innan du börjar:

**En nätverksanslutning**. Du måste ansluta HoloLens till ett nätverk för att konfigurera det. Med HoloLens 2 kan du ansluta med Wi-Fi eller via Ethernet (du behöver en USB-C-till-Ethernet-adapter). Första gången du ansluter behöver du ett öppet eller lösenordsskyddat nätverk som inte kräver att du navigerar till en webbplats eller använder certifikat för att ansluta. [Läs mer om de webbplatser som HoloLens använder.](hololens-offline.md)

**En Microsoft-konto**. Du måste också logga in på HoloLens med en Microsoft-konto (eller med ditt arbetskonto om din organisation äger enheten). Om du inte har ett Microsoft-konto går du till [account.microsoft.com](https://account.microsoft.com) och ställer in ett kostnadsfritt.

**Ett säkert, välbelyst utrymme utan problem.** [Information om hälsa och säkerhet](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**De valfria bekväma tillbehören** som medkom med hololens för att hjälpa dig att få den mest bekväma formen. [Mer om passning och bekvämlighet.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Konfigurera Windows

Första gången du startar HoloLens 2 är din första uppgift att konfigurera Windows Holographic.  När du startar HoloLens kommer du att höra musik och se en Windows-logotyp.

![Första skärmen under den första starten](images/01-magic-moment.png)

HoloLens 2 går igenom följande steg:

1. Välj språk.

    ![Välj språk](images/04-language.png)

1. Välj din region.

    ![Välj region](images/05-region.png)

1. Kalibrera HoloLens till dina ögon.  Om du väljer att hoppa över kalibreringen uppmanas du att göra det nästa gång du loggar in.

    För att kalibrera tittar du på en uppsättning mål (kallas gems). Det går bra om du blinkar eller stänger ögonen under kalibreringen, men försök att inte titta på andra objekt i rummet eller det fysiska utrymmet. HoloLens använder den här processen för att lära sig om din ögonposition så att den bättre kan återge din holografiska värld. Efter kalibreringen visas hologram korrekt även när visor-programmet skiftar på huvudet.

    Kalibreringsinformation lagras lokalt på enheten och är inte associerad med någon kontoinformation. Mer information finns i [Kalibreringsdata och säkerhet.](hololens-calibration.md#calibration-data-and-security)

    ![Skärmen Val av kalibrering](images/06-et-corners.png)

1. Anslut till Internet (välj Wi-Fi eller Ethernet-anslutning).

     HoloLens anger tidszonen automatiskt baserat på information som hämtas från Wi-Fi nätverk. När installationen är klar kan du ändra tidszonen med hjälp av appen Inställningar.

    ![Ansluta till Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Om du fortsätter förbi Wi-Fi-steget och senare behöver växla till ett annat nätverk  medan du fortfarande är konfigurerad kan du trycka på knapparna Volym ned och **Ström** samtidigt för att återgå till det här steget om du kör en operativsystemversion från oktober 2019 eller senare. För tidigare versioner kan [](hololens-recovery.md) du behöva återställa enheten eller starta om den på en plats där Wi-Fi inte är tillgängligt för att förhindra att den ansluter automatiskt.
    > 
    > Observera också att det finns en tidsgräns för autentiseringsuppgifter på två minuter under installationen av HoloLens. Användarnamnet/lösenordet måste anges inom två minuter, annars rensas fältet användarnamn automatiskt.

1. Logga in på ditt användarkonto. Du väljer mellan Mitt **arbete eller min skola äger det och** jag äger **det**.

    - När du väljer **Mitt arbete eller min skola äger det** loggar du in med ett Azure AD-konto. Om din organisation använder Azure AD Premium och har konfigurerat automatisk MDM-registrering registreras HoloLens automatiskt i MDM. Om din organisation inte använder Azure AD Premium är automatisk MDM-registrering inte tillgänglig. I så fall måste du manuellt [registrera HoloLens i enhetshanteringen](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Ange din organisations kontoinformation.
        1. Godkänn sekretesspolicyn och licensavtalet för slutanvändare.
        1. Logga in med dina autentiseringsuppgifter för Azure AD. Detta kan omdirigeras till din organisations inloggningssida.
        1. Fortsätt att konfigurera enheten.

    - När du väljer **Jag äger den** loggar du in med en Microsoft-konto. När installationen är klar kan du [manuellt registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Ange din Microsoft-konto information.
        2. Ange ditt lösenord. Om ditt Microsoft-konto [tvåstegsverifiering (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)slutför du verifieringsprocessen.

    ![Ange användare](images/13-device-owner.png)

1. Välj om du vill aktivera tal på HoloLens 2 och om du vill skicka diagnostiktelemetri.

    ![Aktivera Cortana](images/22-do-more-with-voice.png)

1. Välj telemetrinivå. Om det går aktiverar du Fullständig telemetri. Den här informationen hjälper verkligen HoloLens-teknikteamet.

     ![Telemetrinivå](images/24-telemetry.png)

1. Lär dig hur du använder startgesten på HoloLens 2.

     ![Lär dig hur du använder startgesten bild 1 ](images/26-01-startmenu-learning.png) ![ Lär dig hur du använder startgesten, bild 2](images/26-02-startmenu-learning.png)

Grattis!  Installationen är klar och du är redo att använda HoloLens!

## <a name="next-steps"></a>Nästa steg

1. Börja interagera direkt med Mixed Reality och navigera Windows 10 på din HoloLens – kolla in **tipsappen** för praktiska självstudier för handinteraktioner. Använd startgesten för att gå till Start eller säg "Gå till Start" och välj Tips.

1. Klicka nedan för att fortsätta läsa om att komma runt HoloLens 2.

> [!div class="nextstepaction"]
> [Kom igång med HoloLens 2](hololens2-basic-usage.md)
