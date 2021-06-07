---
title: Kända problem för HoloLens
description: Håll dig uppdaterad med vår lista över kända problem och lösningar som kan påverka HoloLens-kunder och utvecklare som använder Unity och Windows Enhetsportalen.
keywords: troubleshoot, known issue, help
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378834"
---
# <a name="known-issues-for-hololens"></a>Kända problem för HoloLens

Här är den aktuella listan över kända problem för HoloLens-enheter. Kontrollera här först om du ser ett udda beteende. Den här listan uppdateras när nya problem identifieras eller rapporteras, eller när problem åtgärdas i framtida HoloLens-programuppdateringar.

>[!NOTE]
> - Om du upptäcker ett problem som inte blockerar kan du rapportera det på din HoloLens-enhet via [Feedbackhubben](hololens-feedback.md).
> - Om problemet blockerar dig kan du, förutom att skicka feedback, skicka [en supportbegäran.](https://aka.ms/hlsupport)

- [Kända problem för alla HoloLens-generationer](#known-issues-for-all-hololens-generations)
- [Kända problem för HoloLens 2-enheter](#known-issues-for-hololens-2-devices)
- [Kända problem för HoloLens (första gen)](#known-issues-for-hololens-1st-gen)
- [Kända problem för HoloLens-emulatorn](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Kända problem för alla HoloLens-generationer

### <a name="unity"></a>Unity

- Se [Installera verktygen för](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) den senaste versionen av Unity som rekommenderas för HoloLens-utveckling.
- Kända problem med Unity HoloLens Technical Preview finns dokumenterade i [HoloLens Unity-forumen](https://forum.unity3d.com/threads/known-issues.394627/).

### <a name="windows-device-portal"></a>Windows Enhetsportalen

- Funktionen Förhandsgranskning i Mixed Reality kan uppvisa flera sekunders svarstid.

- På sidan Virtuella indata fungerar inte gester- och rullningskontrollerna i avsnittet Virtuella gester. Att använda dem har ingen effekt. Det virtuella tangentbordet på den virtuella indatasidan fungerar korrekt.

- När du har aktiverat utvecklarläget i Inställningar kan det ta några sekunder innan växeln aktiveras Enhetsportalen aktiveras.

### <a name="onedrive-camera-upload"></a>Ladda upp OneDrive-kamera

OneDrive-appen för HoloLens stöder inte automatisk kamerauppladdning för arbets- eller skolkonton.

Workarounds:

- Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton. Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning). Från din Microsoft-konto i OneDrive kan du aktivera automatisk överföring av kamerarulle i bakgrunden.

- Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive-appen. Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive-appen. Välj knappen **+** och välj Ladda **upp.** Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > kamerarulle.** Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.

## <a name="known-issues-for-hololens-2-devices"></a>Kända problem för HoloLens 2-enheter

### <a name="device-using-auto-login-asks-for-log-in"></a>Enhet med automatisk inloggning frågar efter inloggning

En HoloLens 2-enhet kan konfigureras för att automatiskt logga in **via** Inställningskonton  ->    ->  **Inloggningsalternativ** -> och under  Obligatoriskt anger du **värdet till Aldrig**. Vissa användare kan behöva logga in på enheten igen när de uppdaterar en enhet med en mycket stor uppdatering, till exempel en funktionsuppdatering.

Exempel på när detta kan inträffa:

- Uppdatera en enhet från Windows Holographic version 2004 (Build 19041.xxxx) till Windows Holographic, version 21H1 (Build 20346.xxxx)
- Uppdatera en enhet för att ta en stor uppdatering av samma större version, t.ex. Windows Holographic, version 2004 till Windows Holographic, version 20H2
- Uppdatera en enhet från en fabriksavbildning till den senaste avbildningen

Detta bör inte inträffa under:

- Enheter som tar en månatlig serviceuppdatering

Metoder för att komma runt:

- Inloggningsmetoder som PIN-kod, lösenord, Iris, webbautentisering eller FIDO2-nycklar.
- Om enhetens PIN-kod inte kan sparas och andra autentiseringsmetoder inte är tillgängliga kan en användare använda [manuellt omsnedstrecksläge.](hololens-recovery.md#manual-procedure)

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kan inte starta

> [!NOTE]
> Det här problemet skapades ursprungligen med leveransversionen Microsoft Edge i åtanke. Det här problemet kan lösas i den [nya Microsoft Edge](hololens-new-edge.md). Om den inte är det kan du skicka feedback.

Några kunder har rapporterat ett problem där Microsoft Edge inte kan starta. För dessa kunder kvarstår problemet genom omstart och kan inte lösas med Windows- eller programuppdateringar. Om det här problemet uppstår och du har bekräftat att Windows är uppdaterat kan du skicka in en bugg från [Feedbackhubben-appen](hololens-updates.md#manually-check-for-updates)med följande kategori och underkategori: Installera och uppdatera > Ladda ned, installera och konfigurera Windows Update. [](hololens-feedback.md)

Det finns inga kända lösningar eftersom vi inte har kunnat rotorsaken till problemet hittills. Att lämna in en bugg via Feedbackhubben hjälper vår undersökning!

### <a name="keyboard-does-not-switch-to-special-characters"></a>Tangentbordet växlar inte till specialtecken

Det uppstår ett problem under OOBE, där när användaren har valt ett arbets- eller skolkonto och anger sitt lösenord och försöker växla till specialtecken på tangentbordet genom att trycka på knappen &123 ändras inte till specialtecken.

Work-arounds:
-   Stäng tangentbordet och öppna det igen genom att trycka på textfältet.
-   Ange ditt lösenord felaktigt. När tangentbordet har återstartats nästa gång fungerar det som förväntat.
- Webbautentisering, stäng tangentbordet och välj **Logga in från en annan enhet.**
-   Om du bara anger siffror kan en användare trycka på och hålla ned vissa tangenter för att öppna en expanderad meny.
-   Använda ett USB-tangentbord.

Detta påverkar inte:
- Användare som väljer att använda ett personligt konto.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Den blå skärmen visas efter avregistrerade insiderförhandsbyggen på en enhet som omsnedstreckats med en Insider-version

Det här är ett problem som påverkar användare som är i en Insider-förhandsversion, omsnedstreckade sina HoloLens 2 med en ny insiderförhandsvisning och sedan avregistrerade från Insider-programmet.

Detta påverkar inte:
- Användare som inte har registrerats i Windows Insider 
- Insiders:
    - Om en enhet har registrerats sedan Insider-versioner var version 18362.x
    - Om de flashade ett Insider-signerat 19041.x-bygge och förblir registrerade i Insider-programmet

Runt om: 
- Undvik problemet 
    - Flasha en icke-insider-version. En av de regelbundna månatliga uppdateringarna.
    - Håll dig i insiderförhandsvisning
- Omsnedstrecka enheten

    1. Försätt [HoloLens 2 i flashläge manuellt](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) genom att stänga av helt och hållet utan att ansluta. Håll sedan volymen uppåt och tryck på strömknappen.
    
    1. Anslut till datorn och öppna Advanced Recovery Companion.
    
    1. Flasha HoloLens 2 till standardbygget.

## <a name="known-issues-for-hololens-1st-gen"></a>Kända problem för HoloLens (första gen)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Det går inte att ansluta och distribuera till HoloLens via Visual Studio

> [!NOTE]
> Senaste uppdatering: 8/8 @ 17:11 – Visual Studio har släppt VS 2019 version 16.2 som innehåller en korrigering av det här problemet. Vi rekommenderar att du uppdaterar till den senaste versionen för att undvika att det här felet uppstår.

Visual Studio har släppt VS 2019 Version 16.2, som innehåller en korrigering av det här problemet. Vi rekommenderar att du uppdaterar till den senaste versionen för att undvika att det här felet uppstår.

Rotorsak till problemet: Användare som använde Visual Studio 2015 eller tidiga versioner av Visual Studio 2017 för att distribuera och felsöka program på sina HoloLens och sedan använde de senaste versionerna av Visual Studio 2017 eller Visual Studio 2019 med samma HoloLens kommer att påverkas. De nyare versionerna av Visual Studio distribuerar en ny version av en komponent, men filer från den äldre versionen lämnas kvar på enheten, vilket gör att den nyare versionen misslyckas.  Detta orsakar följande felmeddelande: DEP0100: Kontrollera att målenheten har utvecklarläge aktiverat. Det gick inte att hämta någon utvecklarlicens \<ip\> på grund av felet 80004005.

#### <a name="workaround"></a>Lösning

Vårt team arbetar för närvarande med en korrigering. Under tiden kan du använda följande steg för att lösa problemet och hjälpa till att avblockera distribution och felsökning:  

1. Öppna Visual Studio.

1. Välj **File** New Project  >  **(Arkiv nytt**  >  **projekt).**

1. Välj **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Ge projektet ett namn (till exempel "HoloLensDeploymentFix") och kontrollera att Ramverk är inställt på minst .NET Framework 4.5 och välj **sedan OK.**

1. Högerklicka på noden **Referenser** i Solution Explorer lägg till följande referenser (välj i **avsnittet Bläddra** och välj **Bläddra**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Om du inte har 10.0.18362.0 installerat använder du den senaste versionen som du har. 

1. Högerklicka på projektet i Solution Explorer lägg till   >  **befintligt objekt.**

1. Bläddra till C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 och ändra filtret till **Alla filer ( . \* \* )**.

1. Välj både SirepClient.dll och SshClient.dll och Välj Lägg **till.**

1. Leta upp och välj båda filerna i Solution Explorer (de bör finnas längst ned i listan  över filer) och ändra **Kopiera** till utdatakatalog i fönstret Egenskaper till **Kopiera alltid.**

1. Överst i filen lägger du till följande i den befintliga listan med `using` -instruktioner:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. I `static void Main(...)` lägger du till följande kod:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Välj **Build**  >  **Build Solution (Skapa bygglösning).**

1. Öppna ett kommandotolkfönster och cd till mappen som innehåller den kompilerade .exe-filen (till exempel C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Kör den körbara filen och ange enhetens IP-adress som ett kommandoradsargument. (Om du är ansluten via USB kan du använda 127.0.0.1, annars kan du använda enhetens IPWi-Fi adress.)  Till exempel "HoloLensDeploymentFix 127.0.0.1".

1. När verktyget har avslutats utan meddelanden (detta bör bara ta några sekunder) kommer du nu att kunna distribuera och felsöka från Visual Studio 2017 eller senare.  Fortsatt användning av verktyget är inte nödvändigt.

Vi kommer att tillhandahålla ytterligare uppdateringar när de blir tillgängliga.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problem med att starta Microsoft Store appar på HoloLens

> [!NOTE]
> Senaste uppdatering: 04.02 kl. 10:00 – Problemet har lösts.

Du kan få problem när du försöker starta Microsoft Store appar på HoloLens. Vi har fastställt att problemet uppstår när uppdateringar av bakgrundsappen distribuerar en nyare version av ramverkspaket i specifika sekvenser medan en eller flera av deras beroende appar fortfarande körs. I det här fallet levererade en automatisk appuppdatering en ny version av .NET Native Framework (version 10.0.25531 till 10.0.27413) vilket gjorde att de appar som kördes inte uppdaterades korrekt för alla appar som kördes med den tidigare versionen av ramverket.  Flödet för framework-uppdateringen är följande:

1. Det nya ramverkspaketet laddas ned från arkivet och installeras.

1. Alla appar äldre ramverket "uppdateras" för att använda den nyare versionen.

Om steg 2 avbryts innan det slutförs misslyckas alla appar som det nyare ramverket inte har registrerats för att starta från Start-menyn.  Vi tror att alla appar på HoloLens kan påverkas av det här problemet.

Vissa användare har rapporterat att stängning av låsta appar och start av andra appar som Feedbackhubben, 3D-visningsprogram eller Photos löser problemet för dem – men det fungerar inte 100 % av gångerna.

Vi har rotorsaken till att det här problemet inte orsakade själva uppdateringen, men en bugg i operativsystemet som resulterade i att .NET Native framework-uppdateringen hanterades felaktigt. Vi är glada över att kunna meddela att vi har identifierat en korrigering och har släppt en uppdatering (OS-version 17763.380) som innehåller korrigeringen.  

Så här ser du om enheten kan ta uppdateringen:

1. Gå till appen Inställningar och öppna **Update & Security**.

1. Välj **Sök efter uppdateringar.**

1. Om det finns en uppdatering till 17763.380 uppdaterar du till den här versionen för att få korrigeringen för buggen App Hang (Appen låser sig).

1. När du uppdaterar till den här versionen av operativsystemet bör apparna fungera som förväntat.

Som vi gör med alla HoloLens OS-versioner har vi dessutom publicerat FFU-avbildningen till [Microsoft Download Center.](https://aka.ms/hololensdownload/10.0.17763.380)

Om du inte vill göra uppdateringen har vi släppt en ny version av Microsoft Store UWP-appen från och med 3/29. När du har den uppdaterade versionen av Store:

1. Öppna Store och bekräfta att den läses in.
1. Använd bloom-gesten för att öppna menyn.
1. Försök att öppna tidigare brutna appar.
1. Om det fortfarande inte går att startas trycker du på och håller ned ikonen för den brutna appen och väljer avinstallera.
1. Installera om dessa appar från Store.

Om enheten fortfarande inte kan läsa in appar kan du läsa in en version av .NET Native Framework och Runtime separat via download center genom att följa dessa steg:

1. Ladda ned [zip-filen](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) från Microsoft Download Center. När du packar upp produceras två filer.  Microsoft .NET.Native.Runtime.1.7.appx och Microsoft .NET.Native.Framework.1.7.appx.

1. Kontrollera att enheten är upplåst från utveckling.  Om du inte har gjort det tidigare kan du läsa [Använda Windows Enhetsportalen](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) för instruktioner.

1. Sedan vill du komma in i Windows Enhetsportalen. Vår rekommendation är att göra detta via USB och det gör du genom att http://127.0.0.1:10080 skriva i webbläsaren.

1. När du har Windows Enhetsportalen måste du "läsa in" de två filerna som du laddade ned. Om du vill göra det måste du gå nedåt i det vänstra sidofältet tills du kommer **till avsnittet Appar** och välja **Appar.**

1. Sedan visas en skärm som liknar nedanstående.  Du vill gå till avsnittet Installera app och **bläddra till** den plats där du uppackade de två APPX-filerna. Du kan bara göra en i taget, så när du har valt den första klickar du på "Kör" under avsnittet Distribuera. Gör sedan detta för den andra APPX-filen.

   ![Windows Enhetsportalen till Installera Side-Loaded app](images/20190322-DevicePortal.png)
   
1. Nu tror vi att dina program bör börja fungera igen och att du också kan komma till Store.

1. I vissa fall är det nödvändigt att köra det ytterligare steget för att starta 3D-visningsprogram innan berörda appar startas. 

Vi uppskattar ditt tålamod eftersom vi har gått igenom processen för att lösa det här problemet och vi ser fram emot att fortsätta arbeta med vår community för att skapa Mixed Reality upplevelser.

### <a name="device-update"></a>Enhetsuppdatering

- 30 sekunder efter en ny uppdatering kan gränssnittet försvinna en gång. Utför **bloom-gesten** för att återuppta sessionen.

### <a name="visual-studio"></a>Visual Studio

- Se [Installera verktygen för](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) den senaste versionen av Visual Studio som rekommenderas för HoloLens-utveckling.

- När du distribuerar en app Visual Studio till din HoloLens kan du se felet: Den begärda åtgärden kan inte utföras på en fil med ett **användarmappat avsnitt öppet. (Undantag från HRESULT: 0x800704C8)**. Om detta inträffar kan du försöka igen så lyckas distributionen i allmänhet.

### <a name="api"></a>API

- Om programmet ställer in [fokuspunkten](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) bakom användaren eller det normala till camera.forward visas inte hologram i Inspelning av mixad verklighet foton eller videor. Om program aktivt ställer in fokuspunkten [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) tills den här buggen har åtgärdats bör de se till att planet normal är inställt motsatt framåtriktade kamera (till exempel normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Trådlös Xbox-styrenhet

- Xbox Wireless Controller S måste uppdateras innan den kan användas med HoloLens. Kontrollera att du [är uppdaterad innan](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) du försöker parkoppla kontrollanten med en HoloLens.

- Om du startar om HoloLens när den trådlösa Xbox-styrenheten är ansluten återansluter inte styrenheten automatiskt till HoloLens. Guideknappen blinkar långsamt tills styrenheten är avstängd efter 3 minuter. Om du vill återansluta kontrollanten direkt stänger du av styrenheten genom att hålla ned guideknappen tills lampan stängs av. När du sätt på styrenheten igen återansluter den till HoloLens.

- Om hololens aktiveras i vänteläge när den trådlösa Xbox-styrenheten är ansluten aktiveras HoloLens av alla indata på styrenheten. Du kan förhindra detta genom att stänga av styrenheten när du är klar med den.

## <a name="known-issues-for-hololens-emulator"></a>Kända problem för HoloLens-emulatorn

- Alla appar i Microsoft Store är inte kompatibla med emulatorn. Till exempel är Young Conker och Fragment inte spelbara i emulatorn.
- Du kan inte använda pc-webbkameran i emulatorn.
- Funktionen Liveförhandsgranskning i Windows Enhetsportalen fungerar inte med emulatorn. Du kan fortfarande samla Mixed Reality videor och bilder.
