---
title: Felsökning av HoloLens-enhet
description: Håll dig uppdaterad om de vanligaste lösningarna på problem med HoloLens-enheter och felsökningstekniker.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problem, bugg, felsöka, åtgärda, hjälp, support, HoloLens, emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924629"
---
# <a name="device-troubleshooting"></a>Felsökning av enhet

Den här artikeln beskriver hur du löser flera vanliga HoloLens-problem.

>[!IMPORTANT]
> Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40** procent av batterikapaciteten om det är möjligt. Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.

<a id="list"></a>

**Kända problem**
- [Remote Assist-videon låser sig efter 20 minuter](#remote-assist-video-freezes-after-20-minutes)
- [Automatisk inloggning frågar efter inloggning](#auto-login-asks-for-log-in)
- [Microsoft Edge kan inte starta](#microsoft-edge-fails-to-launch)
- [Tangentbordet växlar inte till specialtecken](#keyboard-doesnt-switch-to-special-characters)
- [Det visas inget fel när låsta filer laddas ned](#downloading-locked-files-doesnt-error)
- [Enhetsportalen-filuppladdning/nedladdningstidsuppladdning](#device-portal-file-uploaddownload-times-out)
- [Blå skärm efter avregistrerad från Insider-förhandsgranskning på en enhet som flashats med en Insider-version](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive laddar inte upp bilder automatiskt](#onedrive-doesnt-automatically-upload-pictures)

**Allmänt**
- [HoloLens svarar inte eller startar inte](#hololens-is-unresponsive-or-wont-start)
- [Fel om "lågt diskutrymme"](#low-disk-space-error)
- [Kalibreringen misslyckas](#calibration-fails)
- [Det går inte att logga in eftersom min HoloLens tidigare har ställts in för någon annan](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity fungerar inte](#unity-isnt-working)
- [Windows Enhetsportalen fungerar inte korrekt](#windows-device-portal-isnt-working-correctly)
- [HoloLens-emulatorn fungerar inte](#the-hololens-emulator-isnt-working)

**Indata**
- [Röstkommandon fungerar inte](#voice-commands-arent-working)
- [Handinmatningen fungerar inte](#hand-input-isnt-working)

**Anslutningsmöjligheter**
- [Det går inte att ansluta till Wi-Fi](#cant-connect-to-wi-fi)

**Externa enheter** 
- [Bluetooth-enheter parkopplas inte](#bluetooth-devices-arent-pairing)
- [USB-C-mikrofonen fungerar inte](#usb-c-microphone-isnt-working)
- [Enheter som anges som tillgängliga i Inställningar fungerar inte](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist-videon låser sig efter 20 minuter

> [!NOTE]
> På grund av det här kända problemets allvarlighetsgrad har vi för närvarande pausat tillgängligheten för Windows Holographic, version 21H1. Om du fortfarande vill uppdatera dina enheter till 21H1 kan du läsa anvisningarna i vår version längst [upp på sidan.](hololens-release-notes.md)

I den senaste versionen av [Windows Holographic, version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)har vissa användare av Remote Assist haft videofrysning under samtal över 20 minuter. Det här är **ett känt problem.**

### <a name="workarounds"></a>Provisoriska lösningar

#### <a name="restart-in-between-calls"></a>Starta om mellan anrop

Om dina anrop tar mer än 20 minuter och det här problemet uppstår kan du prova att starta om enheten. Om du startar om enheten mellan Remote Assist-anrop uppdateras enheten och den förs tillbaka till ett bra tillstånd.

Om du snabbt vill starta om en enhet i [Windows Holographic öppnar du version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) startmenyn och väljer användarikonen och väljer sedan **Starta om.**

#### <a name="revert-to-an-older-build"></a>Återgå till en äldre version

Vissa kunder har upptäckt att det här problemet inte längre uppstår när de återgår till en tidigare version av operativsystemet. Om du har upptäckt att dina enheter har det här problemet kan du prova följande steg:


Workarounds:

- Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton. Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning). Från din Microsoft-konto i OneDrive kan du aktivera automatisk överföring av kamerarulle i bakgrunden.

- Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive-appen. Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive-appen. Välj knappen **+** och välj Ladda **upp.** Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > camera roll**. Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.


1. [Ladda ned versionen för Windows Holographic, version 20H2 – maj 2021 Update](https://aka.ms/hololens2download/10.0.19041.1146)
1. Följ [instruktionerna för att återgå till en tidigare os-version](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Pausa [antingen OS-uppdateringar på enheten manuellt](hololens-updates.md#pause-updates-via-device) eller för många enheter [med uppsnackning via MDM.](hololens-updates.md#configure-an-update-deferral-policy)

[Tillbaka till listan](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatisk inloggning frågar efter inloggning

En HoloLens 2-enhet kan konfigureras för att automatiskt logga in **via** Inställningskonton  ->    ->  **Inloggningsalternativ** -> och under  Obligatoriskt anger du **värdet till Aldrig**. Vissa användare kan behöva logga in på enheten igen när de uppdaterar en enhet med en mycket stor uppdatering, till exempel en funktionsuppdatering. Det här är **ett känt problem.**

Exempel på när detta kan inträffa:

- Uppdatera en enhet från Windows Holographic version 2004 (Build 19041.xxxx) till Windows Holographic, version 21H1 (Build 20346.xxxx)
- Uppdatera en enhet för att ta en stor uppdatering av samma större version, t.ex. Windows Holographic, version 2004 till Windows Holographic, version 20H2
- Uppdatera en enhet från en fabriksavbildning till den senaste avbildningen

Detta bör inte inträffa under:

- Enheter som tar en månatlig serviceuppdatering

Metoder för att komma runt:

- Inloggningsmetoder som PIN-kod, lösenord, Iris, webbautentisering eller FIDO2-nycklar.
- Om enhetens PIN-kod inte kan sparas och andra autentiseringsmetoder inte är tillgängliga kan en användare använda [manuellt omsnedstrecksläge.](hololens-recovery.md#manual-procedure)

[Tillbaka till listan](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kan inte starta

> [!NOTE]
> Det här problemet skapades ursprungligen med leveransversionen Microsoft Edge i åtanke. Det här problemet kan lösas i den [nya Microsoft Edge](hololens-new-edge.md). Om den inte är det kan du skicka feedback.

Några kunder har rapporterat ett problem där Microsoft Edge inte kan starta. För dessa kunder kvarstår problemet genom omstart och kan inte lösas med Windows- eller programuppdateringar. Om det här problemet uppstår och du har bekräftat att Windows är uppdaterat kan du skicka in en bugg från [Feedbackhubben-appen](hololens-updates.md#manually-check-for-updates)med följande kategori och underkategori: Installera och uppdatera > Ladda ned, installera och konfigurera Windows Update. [](hololens-feedback.md)

Det finns inga kända lösningar eftersom vi inte har kunnat rotorsaken till problemet hittills. Att lämna in en bugg via Feedbackhubben hjälper vår undersökning! Det här är **ett känt problem.**

[Tillbaka till listan](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Tangentbordet växlar inte till specialtecken

Det uppstår ett problem under OOBE, där när användaren har valt ett arbets- eller skolkonto och anger sitt lösenord och försöker växla till specialtecken på tangentbordet genom att trycka på knappen &123 ändras inte till specialtecken. Det här är **ett känt problem.**

Work-arounds:
-   Stäng tangentbordet och öppna det igen genom att trycka på textfältet.
-   Ange ditt lösenord felaktigt. När tangentbordet har återstartats nästa gång fungerar det som förväntat.
- Webbautentisering, stäng tangentbordet och välj **Logga in från en annan enhet.**
-   Om du bara anger siffror kan en användare trycka på och hålla ned vissa tangenter för att öppna en expanderad meny.
-   Använda ett USB-tangentbord.

Detta påverkar inte:
- Användare som väljer att använda ett personligt konto.

[Tillbaka till listan](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Det går inte att ladda ned låsta filer
> ! Obs! Det här **är ett känt** problem som har åtgärdats Windows Insider version 20348.1403.


I tidigare versioner av Windows Holographic skulle resultatet bli en HTTP-felsida när du försöker ladda ned en låst fil. I Windows Holographic version 21H1 Update, som försöker ladda ned en låst fil, resulterar det i att inget synligt händer – filen laddas inte ned och det uppstår inget fel. 

[Tillbaka till listan](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Enhetsportalen-filuppladdning/nedladdningstidsuppladdning
> ! Obs! Det här **är ett känt** problem som åtgärdas i Windows Insider version 20348.1403. Om du tidigare har inaktiverat SSL-anslutning som en del av lösningen rekommenderar vi starkt att du återaktivera den.


Vissa kunder har upptäckt att åtgärden kan se ut att stanna upp när de försöker ladda upp eller ladda ned filer och sedan ta slut eller aldrig slutföras. Detta är separat[](#downloading-locked-files-doesnt-error) från det kända problemet "fillås" – detta påverkar Windows Holographic- versionerna 2004, 20H2 och 21H1 på marknaden. Problemet har orsakats av en bugg i Enhetsportalen hantering av vissa begäranden och används mest konsekvent när https används, vilket är standardinställningen. 

### <a name="workaround"></a>Lösning

Den här lösningen, som gäller Wi-Fi och UsbNcm, är att inaktivera alternativet "krävs" under "SSL-anslutning". Det gör du genom att Enhetsportalen, **System** och välja **sidan** Inställningar. I avsnittet **Enhetssäkerhet** letar du upp **SSL-anslutning** och avmarkerar för att inaktivera **Nödvändig**.

Användaren bör sedan gå till http://, inte https:// (IP-adress) och funktioner som filuppladdning och nedladdning fungerar.

[Tillbaka till listan](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blå skärm efter avregistrerad insiderförhandsvisning på en enhet som flashats med en Insider-version

Det här är ett problem som påverkar användare som är i en Insider-förhandsversion, omsnedstreckade sina HoloLens 2 med en ny insiderförhandsvisning och sedan avregistrerade från Insider-programmet. Det här är **ett känt problem.**

Detta påverkar inte:
- Användare som inte har registrerats i Windows Insider 
- Insiders:
    - Om en enhet har registrerats sedan Insider-versioner var version 18362.x
    - Om de flashade ett Insider-signerat 19041.x-bygge och förblir registrerade i Insider-programmet

Runt om: 
- Undvik problemet 
    - Flasha en icke-insider-version. En av de regelbundna månatliga uppdateringarna.
    - Håll dig i insiderförhandsvisning
- Omstrecka enheten

    1. Försätt [HoloLens 2 i flashläge manuellt](hololens-recovery.md) genom att stänga av helt och hållet utan att ansluta. Håll sedan volymen uppåt och tryck på strömknappen.
    
    1. Anslut till datorn och öppna Advanced Recovery Companion.
    
    1. Flasha HoloLens 2 till standardbygget.

[Tillbaka till listan](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive laddar inte upp bilder automatiskt

OneDrive-appen för HoloLens stöder inte automatisk kamerauppladdning för arbets- eller skolkonton. Det här är **ett känt problem.**

Workarounds:

- Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton. Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning). Från din Microsoft-konto i OneDrive kan du aktivera automatisk överföring av kamerarulle i bakgrunden.

- Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive-appen. Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive-appen. Välj knappen **+** och välj Ladda **upp.** Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > camera roll**. Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.

[Tillbaka till listan](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens svarar inte eller startar inte

Om hololens inte startar:

- Om lysdioderna bredvid strömknappen inte tänds eller bara en lysdiod blinkar en kort stund kan du behöva debitera [HoloLens.](hololens2-charging.md#charging-the-device)
- Om lysdioderna tänds när du trycker på strömknappen men du inte kan se något på skärmarna, gör du en hård [återställning av enheten.](hololens-recovery.md#hard-reset-procedure)

Om hololens blir låst eller inte svarar:

- Stäng av HoloLens genom att trycka på strömknappen tills alla fem lysdioderna stänger av sig själva eller i 15 sekunder om lysdioderna inte svarar. Starta HoloLens genom att trycka på strömknappen igen.

Om de här stegen inte fungerar kan du försöka återställa [din HoloLens 2-enhet](hololens-recovery.md) eller [HoloLens-enhet (första generationen).](hololens1-recovery.md)

[Tillbaka till listan](#list)

## <a name="low-disk-space-error"></a>Fel om "lågt diskutrymme"

Du måste frigöra lagringsutrymme genom att göra något av följande:

- Ta bort vissa blanksteg som inte används. Gå till **Inställningar**  >    >  **Systemutrymmen**, välj ett utrymme som du inte längre behöver och välj sedan Ta **bort.**
- Ta bort några av de hologram som du har placerat.
- Ta bort några bilder och videor från appen Foton.
- Avinstallera några appar från hololens. I listan **Alla appar** trycker du på och håller ned den app som du vill avinstallera och väljer sedan **Avinstallera.**

[Tillbaka till listan](#list)

## <a name="calibration-fails"></a>Kalibreringen misslyckas

Kalibrering bör fungera för de flesta, men det finns fall där kalibreringen misslyckas.
  
Några potentiella orsaker till kalibreringsfel är:

- Bli störande och inte följa kalibreringsmålen
- Dirty or scratched device visor or device visor not positioned properly
- Dirty eller scratched glass
- Vissa typer av kontaktlinser och glasögon (färgade kontaktlinser, några toric kontaktlinser, IR-blockeringsglasögon, några glasögon med höga glasögon, solglasögon eller liknande)
- Mer uttalad snedstreck och vissa ögonfragnstillägg
- Behåring eller tjocka glasögonramar om de blockerar enheten från att se dina ögon
- Vissa ögonlyssna, ögontillstånd eller ögonoperationer som smala ögon, långa ögonfransar, amblyopia, nystagmus, vissa fall av LASIK eller andra ögonoperationer

Om kalibreringen misslyckas försöker du:

- Rensa enhetsvisor-programmet
- Rensa glasögonen
- Push-pusha enhetsvisor-programmet så nära dina ögon som möjligt
- Flytta objekt i ditt visor-program från vägen (till exempel hår)
- Aktivera en lampa i rummet eller flytta ut direkt från rummet

Om du har följt alla riktlinjer och kalibreringen fortfarande misslyckas kan du inaktivera kalibreringsuppmaning i Inställningar. Meddela oss också genom att skicka feedback i [Feedbackhubben](hololens-feedback.md).

Se även relaterad information för felsökning [av bildfärg eller ljusstyrka.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Inställningen IPD gäller inte för HoloLens 2, eftersom ögonpositioner beräknas av systemet. 

[Tillbaka till listan](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Det går inte att logga in eftersom min HoloLens tidigare har ställts in för någon annan

Du kan [placera enheten i **flashläge och använda** Advanced Recovery Companion för](hololens-recovery.md#clean-reflash-the-device) att återställa enheten.

[Tillbaka till listan](#list)


## <a name="unity-isnt-working"></a>Unity fungerar inte

- Se [Installera verktygen för](/windows/mixed-reality/install-the-tools) den senaste versionen av Unity som rekommenderas för HoloLens-utveckling.
- Kända problem med Unity HoloLens Technical Preview finns dokumenterade i [HoloLens Unity-forumen](https://forum.unity3d.com/threads/known-issues.394627/).

[Tillbaka till listan](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Enhetsportalen fungerar inte korrekt

- Funktionen Förhandsgranskning i Mixed Reality kan uppvisa flera sekunders svarstid.

- På sidan Virtuella indata fungerar inte gester- och rullningskontrollerna i avsnittet Virtuella gester. Att använda dem har ingen effekt. Det virtuella tangentbordet på den virtuella indatasidan fungerar korrekt.

- När du har aktiverat Utvecklarläge i Inställningar kan det ta några sekunder innan växeln aktiveras för Enhetsportalen aktiveras.

[Tillbaka till listan](#list)

## <a name="emulator"></a>Emulator
### <a name="the-hololens-emulator-isnt-working"></a>HoloLens-emulatorn fungerar inte

Information om HoloLens-emulatorn finns i vår utvecklardokumentation.  Läs mer om felsökning [av HoloLens-emulatorn](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).


- Alla appar i Microsoft Store är inte kompatibla med emulatorn. Till exempel är Young Conker och Fragment inte spelbara i emulatorn.
- Du kan inte använda pc-webbkameran i emulatorn.
- Funktionen Liveförhandsgranskning i Windows Enhetsportalen fungerar inte med emulatorn. Du kan fortfarande samla Mixed Reality videor och bilder.

[Tillbaka till listan](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Jag kan inte hitta eller använda tangentbordet för att skriva i HoloLens 2-emulatorn

*Kommer snart*

[Tillbaka till listan](#list)

## <a name="voice-commands-arent-working"></a>Röstkommandon fungerar inte

Om Cortana inte svarar på dina röstkommandon kontrollerar du att Cortana är aktiverat. I listan Alla appar Cortana-menyn Notebook Settings  >    >  **(Notebook-inställningar för**  >  **Cortana-menyn)** för att göra ändringar. Mer information om vad du kan säga finns i [Använda din röst med HoloLens](hololens-cortana.md).

På HoloLens (första generationen) kan inte inbyggd taligenkänning konfigureras. Den är alltid aktiverad. På HoloLens 2 kan du välja om du vill aktivera både taligenkänning och Cortana under enhetskonfigurationen.

Om HoloLens 2 inte svarar på din röst kontrollerar du att Taligenkänning är aktiverat. Gå till  >  **Startinställningar**  >    >  **Sekretesstal** och aktivera **Taligenkänning.**

[Tillbaka till listan](#list)

## <a name="hand-input-isnt-working"></a>Handindata fungerar inte

För att säkerställa att HoloLens kan se dina händer måste du hålla dem inom gestens ram.  Startsidan Mixed Reality feedback som meddelar dig när dina händer spåras.  Feedbacken är annorlunda i olika versioner av HoloLens:
- På HoloLens (1:a gen) ändras blickmarkören från en punkt till en ring
- På HoloLens 2 visas en handmarkör när din hand är nära en pektavla och en handröta visas när pekarna är längre bort

Många integrerande appar följer indatamönster som liknar Mixed Reality Home.  Läs mer om att använda handindata [på HoloLens (första generationen)](hololens1-basic-usage.md#use-hololens-with-your-hands) och [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Observera att vissa typer av handsken inte fungerar med handspårning om du bär handskydd.  Ett vanligt exempel är svarta handskes, som tenderar att absorbera IR-ljus och inte hämtas av djupkameran.  Om ditt arbete omfattar skyddshandske rekommenderar vi att du provar en ljusare färg, till exempel blå eller grå.  Ett annat exempel är stora baggy gloves, som tenderar att dölja formen på din hand. Vi rekommenderar att du använder så väl formpassning som möjligt för bästa resultat.

Om ditt visir har fingeravtryck eller utsmetning använder du mikrofiberrensningen som medkom med HoloLens för att rensa visorn.

[Tillbaka till listan](#list)

## <a name="cant-connect-to-wi-fi"></a>Det går inte att ansluta till Wi-Fi

Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:

- Kontrollera att Wi-Fi är aktiverat. Kontrollera genom att använda gesten Start och sedan välja **Inställningar**  >  **&amp; Nätverkets**  >  **Internet-Wi-Fi.** Om Wi-Fi är på kan du prova att stänga av den och sedan aktivera igen.
- Flytta datorn närmare routern eller åtkomstpunkten.
- Starta om Wi-Fi router och starta [sedan om HoloLens](hololens-recovery.md). Försök att ansluta igen.
- Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran. Du hittar den här informationen på tillverkarens webbplats.

[Tillbaka till listan](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth-enheter parkopplas inte

Om du har problem med att [koppla en Bluetooth-enhet](hololens-connect-devices.md)kan du prova följande:

- Gå till  >  **Inställningar Enheter** och kontrollera att Bluetooth är aktiverat. Om den är det inaktiverar du den och sätter på den igen.
- Kontrollera att Bluetooth-enheten är helt debiterad eller har nya batterier.
- Om du fortfarande inte kan ansluta startar [du om HoloLens](hololens-recovery.md).

[Tillbaka till listan](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-mikrofonen fungerar inte
Tänk på att vissa USB-C-mikrofoner felaktigt rapporterar sig själva som både *en mikrofon och* en talare. Det här är ett problem med mikrofonen och inte med HoloLens. När någon av dessa mikrofoner ansluts till HoloLens kan ljudet gå förlorat. Lyckligtvis finns det en enkel korrigering.  

I **Inställningar**  ->    ->  **Systemljud** anger du uttryckligen de inbyggda talarna **(Analog Feature Audio Driver)** som **Standardenhet**. HoloLens bör komma ihåg den här inställningen även om mikrofonen tas bort och återansluts senare.

![Felsöka USB-C-mikrofoner](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Enheter som anges som tillgängliga i Inställningarna fungerar inte

HoloLens (första generationen) stöder inte Bluetooth-ljudprofiler. Bluetooth-ljudenheter, till exempel högtalare och headset, kan visas som tillgängliga i HoloLens-inställningar, men de stöds inte.

HoloLens 2 stöder Bluetooth A2DP-ljudprofilen för stereouppspelning. Profilen Bluetooth Hands Free som aktiverar mikrofoninfångning från bluetooth-kringutrustning stöds inte på HoloLens 2.

Om du har problem med att använda en Bluetooth-enhet kontrollerar du att det är en enhet som stöds. Enheter som stöds är följande:

- QWERTY Bluetooth-tangentbord på engelska (du kan använda dem var som helst där du använder det holografiska tangentbordet).
- Bluetooth-mice.
- [HoloLens-klickaren](hololens1-clicker.md).

Du kan koppla ihop andra Bluetooth HID- och GATT-enheter med din HoloLens. Du kan dock behöva installera motsvarande tillhörande appar från Microsoft Store för att faktiskt använda enheterna.

[Tillbaka till listan](#list)
