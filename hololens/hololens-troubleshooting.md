---
title: HoloLens Felsökning av enhet
description: Håll dig uppdaterad om de vanligaste lösningarna för att HoloLens enhetsproblem och felsökningstekniker.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problem, bugg, felsöka, åtgärda, hjälp, support, HoloLens, emulator
ms.openlocfilehash: deed0d14b2567ae0a1fb2cde8ad1fbe3dbb20bb3
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351773"
---
# <a name="device-troubleshooting"></a>Felsökning av enhet

Den här artikeln beskriver hur du löser flera vanliga HoloLens problem.

>[!IMPORTANT]
> Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40 procent** av batterikapaciteten om det är möjligt. Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.

<a id="list"></a>

**Kända problem**
- [Insiderkorrigering – Varje gång strömmen går till 18 procent stängs enheten plötsligt av automatiskt](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive UWP-appen fungerar inte för Azure AD-användare](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Varför visas en 0x80180014 autopilot?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store felkod 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge kan inte starta mikrofonen](#microsoft-edge-fails-to-start-the-microphone)
- [**Åtgärdat** – Remote Assist-videon låser sig efter 20 minuter](#remote-assist-video-freezes-after-20-minutes)
- [Automatisk inloggning frågar efter inloggning](#auto-login-asks-for-log-in)
- [Microsoft Edge kan inte starta](#microsoft-edge-fails-to-launch)
- [Tangentbordet växlar inte till specialtecken](#keyboard-doesnt-switch-to-special-characters)
- [**Åtgärdat** – felet visas inte när låsta filer laddas ned](#downloading-locked-files-doesnt-error)
- [**Åtgärdat** – Enhetsportalen för uppladdning/nedladdning av filer](#device-portal-file-uploaddownload-times-out)
- [Blå skärm efter avregistrerad från Insider-förhandsgranskning på en enhet som flashats med en Insider-version](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive laddar inte upp bilder automatiskt](#onedrive-doesnt-automatically-upload-pictures)

**Allmänt**
- [HoloLens svarar inte eller startar inte](#hololens-is-unresponsive-or-wont-start)
- [Fel om "lågt diskutrymme"](#low-disk-space-error)
- [Kalibreringen misslyckas](#calibration-fails)
- [Det går inte att logga in eftersom HoloLens tidigare har ställts in för någon annan](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity fungerar inte](#unity-isnt-working)
- [Windows Enhetsportalen fungerar inte korrekt](#windows-device-portal-isnt-working-correctly)
- [Den HoloLens Emulator fungerar inte](#the-hololens-emulator-isnt-working)

**Indata**
- [Röstkommandon fungerar inte](#voice-commands-arent-working)
- [Handindata fungerar inte](#hand-input-isnt-working)

**Anslutningsmöjligheter**
- [Det går inte att ansluta till Wi-Fi](#cant-connect-to-wi-fi)

**Externa enheter** 
- [Bluetooth-enheter inte parkopplas](#bluetooth-devices-arent-pairing)
- [USB-C-mikrofonen fungerar inte](#usb-c-microphone-isnt-working)
- [Enheter som anges som tillgängliga Inställningar inte fungerar](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Varje gång strömmen går till 18 procent stängs enheten plötsligt av automatiskt

> [!NOTE]
> Det finns en korrigering för det här problemet i [Windows Insiders.](hololens-insider.md)

Det finns ett känt problem där enheten oväntat stängs av när den når 18 % batteri. Det här är ett programvaruproblem, inte ett maskinvaru- eller batteriproblem, så byt inte enheter mot detta. Om du är osäker på om problemet matchar den här buggen kan du:

1. Se till att valfri diagnostik är aktiverad på dina enheter
1. Återskapa problemet
1. Skicka ett [Feedbackhubben](hololens-feedback.md) problem
1. Dela URL:en för feedbackproblem
1. [Kontakta supporten](https://aka.ms/hololenssupport)

[Tillbaka till listan](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP-appen fungerar inte för Azure AD-användare

Om du använder OneDrive For Business med ditt Azure AD-konto kan det ha uppstått ett fel när du loggar in i din inkorg OneDrive appen. Att inte kunna logga in OneDrive appen påverkar inte automatiska uppladdningar av bilder och videor som har tagits av kameraappen. Filerna kan fortfarande sparas och nås från OneDrive för företag molnlagring. De OneDrive och HoloLens arbetar med problemet.

### <a name="workarounds"></a>Provisoriska lösningar

Krav: Kunder kan använda Microsoft Edge och enhetens operativsystem uppdateras till en version Windows Holographic, 21H1 eller nyare.

Om du har det här problemet kan du prova något av följande:

- Användare kan komma åt OneDrive For Business från Microsoft Edge och interagera med sina filer på webbplatsen från webbläsaren.
- Användarna kan installera appen OneDrive PWA att HoloLens genom att ladda ned den från Microsoft Edge. Detta gör att användarna kan visa och hantera filer på enheten igen. Läs och följ de [här anvisningarna för att installera OneDrive PWA på din HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Tillbaka till listan](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Varför visas en 0x80180014 Autopilot?

Det här felet uppstår vanligtvis under enhetsåterställning och återanvändning av flöden där HoloLens enhet har gått igenom Autopilot minst en gång. Du kan lösa problemet genom att ta [bort enheten från Microsoft Intune](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) och återställa den igen för att slutföra Autopilot-flödet.

Mer information finns i [felsökningsstegen på Autopilot-sidan.](hololens2-autopilot.md#issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store felkod 0x80131500

Vissa användare kan uppleva Microsoft Store fungerar inte som förväntat och ser felkoden 0x80131500. Det här är ett problem som orsakas av att den region som angetts på HoloLens inte är tillgänglig i Microsoft Store på HoloLens. Om du stöter på felkod 0x80131500 kan du lösa problemet genom att:

1. Ange Inställningar > tid & språk > region > land eller region till något av följande:
    - USA, Japan, Kina, Tyskland, Kanada, Storbritannien, Irland, Frankrike, Australien, Nya Zeeland.
1. Starta om Store-appen.
1. För att hela enheten ska återspegla ändringen måste enheten startas om.

Teamet HoloLens arbetar med att lägga till stöd för fler regioner.

Här kan [länder köpa HoloLens 2.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge kan inte starta mikrofonen

När användare som använder Microsoft Edge kan det inte gå att starta mikrofonen, vilket innebär att den inte kan användas för att interagera med Edge i HoloLens. Det här kända problemet är relaterat till versionen av Microsoft Edge-appen. Omstrecka inte enheten till en tidigare version eftersom detta inte löser problemet.

### <a name="who-is-affected"></a>Vem påverkas?

Användare som har Microsoft Edge version 93, 94 eller 95.
Du kan kontrollera vilken version av Microsoft Edge du har med hjälp av Microsoft Store-appen och sedan välja knappen "Se mer" som **representeras** av **...** och sedan välja Nedladdningar och uppdateringar .

### <a name="work-around"></a>Arbeta runt

Den aktuella korrigeringen finns i version 96, som är tillgänglig för användare som har registrerat sig i Microsoft Edge Insiders. Detta skiljer sig från att registrera din enhet som en Windows Insider. Läs de här anvisningarna om [du vill ha mer information om hur du registrerar dig för Edges insiderprogram.](hololens-new-edge.md#microsoft-edge-insider-channels)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist-videon låser sig efter 20 minuter

> [!NOTE]
> Det finns en nyare version av Remote Assist som har en korrigering av det här problemet. Uppdatera [Remote Assist till den](holographic-store-apps.md#update-apps) senaste versionen för att undvika det här problemet.

> [!NOTE]
> På grund av allvarlighetsgraden för det här kända problemet pausade vi tillfälligt tillgängligheten för Windows Holographic, version 21H1. 21H1-versionen är nu tillgänglig igen, så enheter kan återigen uppdateras till den senaste versionen 21H1.

I den senaste versionen [av Windows Holographic, version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)har vissa användare av Remote Assist haft videofrysningar under samtal över 20 minuter. Det här är **ett känt problem.**

### <a name="workarounds"></a>Provisoriska lösningar

Om du inte kan uppdatera Remote Assist till en nyare version kan du prova följande.

#### <a name="restart-in-between-calls"></a>Starta om mellan anrop

Om dina anrop tar mer än 20 minuter och det här problemet uppstår kan du prova att starta om enheten. Om du startar om enheten mellan Remote Assist-anrop uppdateras enheten och den förs tillbaka till ett bra tillstånd.

Om du snabbt vill starta [om Windows Holographic öppnar du version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) startmenyn och väljer användarikonen och väljer sedan **Starta om.**

[Tillbaka till listan](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatisk inloggning frågar efter inloggning

En HoloLens 2-enhet kan konfigureras för att automatiskt logga in via  ->    ->  **Inställningar-konton Inloggningsalternativ**  -> och under Obligatoriskt anger du värdet **till Aldrig**. Vissa användare kan behöva logga in på enheten igen när de uppdaterar en enhet med en mycket stor uppdatering, till exempel en funktionsuppdatering. Det här är **ett känt problem.**

Exempel på när detta kan inträffa:

- Uppdatera en enhet från Windows Holographic, version 2004 (Build 19041.xxxx) till Windows Holographic, version 21H1 (Build 20346.xxxx)
- Uppdatera en enhet för att ta en stor uppdatering av samma större version, t.ex. Windows Holographic, version 2004 till Windows Holographic, version 20H2
- Uppdatera en enhet från en fabriksavbildning till den senaste avbildningen

Detta bör inte inträffa under:

- Enheter som tar en månatlig serviceuppdatering

Metoder för att komma runt:

- Inloggningsmetoder som PIN-kod, lösenord, Iris, webbautentisering eller FIDO2-nycklar.
- Om enhetens PIN-kod inte kan sparas och andra autentiseringsmetoder inte är tillgängliga kan en användare använda [manuellt omsnedstrecksläge.](hololens-recovery.md#manual-flashing-mode-procedure)

[Tillbaka till listan](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kan inte starta

> [!NOTE]
> Det här problemet skapades ursprungligen med leveransversionen Microsoft Edge i åtanke. Det här problemet kan lösas i den [nya Microsoft Edge](hololens-new-edge.md). Om den inte är det kan du skicka feedback.

Några kunder har rapporterat ett problem där Microsoft Edge inte kan starta. För dessa kunder kvarstår problemet genom omstart och kan inte lösas med Windows eller programuppdateringar. Om det här problemet uppstår och du har bekräftat att Windows är uppdaterat kan du skicka en bugg från [Feedbackhubben-appen](hololens-updates.md#manually-check-for-updates)med följande kategori och underkategori: Installera och uppdatera > Ladda ned, installera och konfigurera Windows Update. [](hololens-feedback.md)

Det finns inga kända lösningar eftersom vi inte har kunnat rotorsaken till problemet hittills. Att lämna in en bugg via Feedbackhubben hjälper vår undersökning! Det här är **ett känt problem.**

[Tillbaka till listan](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Tangentbordet växlar inte till specialtecken

Det uppstår ett problem under OOBE, där när användaren har valt ett arbets- eller skolkonto och anger sitt lösenord och försöker växla till specialtecken på tangentbordet genom att trycka på knappen &123 ändras inte till specialtecken. Det här är **ett känt problem.**

Work-arounds:

- Stäng tangentbordet och öppna det igen genom att trycka på textfältet.
- Ange ditt lösenord felaktigt. När tangentbordet har återstartats nästa gång fungerar det som förväntat.
- Webbautentisering, stäng tangentbordet och välj **Logga in från en annan enhet.**
- Om du bara anger siffror kan en användare trycka på och hålla ned vissa tangenter för att öppna en expanderad meny.
- Använda ett USB-tangentbord.

Detta påverkar inte:

- Användare som väljer att använda ett personligt konto.

[Tillbaka till listan](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Det går inte att ladda ned låsta filer

> [!NOTE]
> Det här är **ett känt** problem som har [åtgärdats i Windows Holographic version 21H1 – juli 2021 Update](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

I tidigare versioner av Windows Holographic skulle resultatet bli en HTTP-felsida när du försöker ladda ned en låst fil. I Windows Holographic, version 21H1 update, resulterar försök att ladda ned en låst fil i att inget visas – filen laddas inte ned och det uppstår inget fel.

[Tillbaka till listan](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Enhetsportalen-filuppladdning/nedladdningstidsuppladdning
> [!NOTE]
> Det här är **ett känt** problem som har [åtgärdats i Windows Holographic version 21H1 – juli 2021 Update](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Om du tidigare har inaktiverat SSL-anslutning som en del av lösningen rekommenderar vi starkt att du återaktivera den.

Vissa kunder har upptäckt att åtgärden kanske låser sig och sedan tar slut eller aldrig slutförs när de försöker ladda upp eller ladda ned filer. Detta är separat[](#downloading-locked-files-doesnt-error) från det kända problemet "fillåst" – detta påverkar versioner av Windows Holographic, versionerna 2004, 20H2 och 21H1 på marknaden. Problemet har orsakats av en bugg i Enhetsportalen hantering av vissa begäranden och används mest konsekvent när https används, vilket är standardinställningen.

### <a name="workaround"></a>Lösning

Den här lösningen, som gäller för Wi-Fi och UsbNcm, är att inaktivera alternativet "krävs" under "SSL-anslutning". Det gör du genom att gå Enhetsportalen, **System** och välja **sidan** Inställningar. I avsnittet **Enhetssäkerhet** letar du upp **SSL-anslutning** och avmarkerar för att inaktivera **Nödvändig**.

Användaren bör sedan gå till http://, inte https:// (IP-adress) och funktioner som filuppladdning och nedladdning fungerar.

[Tillbaka till listan](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blå skärm efter avregistrerad från Insider-förhandsgranskning på en enhet som flashats med en Insider-version

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
- Omsnedstrecka enheten

    1. Försätt [HoloLens 2 i flashläge manuellt](hololens-recovery.md) genom att stänga av helt och hållet utan att ansluta. Håll sedan volymen uppåt och tryck på strömknappen.

    1. Anslut till datorn och öppna Advanced Recovery Companion.

    1. Flasha HoloLens 2 till standardbygget.

[Tillbaka till listan](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive laddar inte upp bilder automatiskt

Appen OneDrive för HoloLens stöder inte automatisk kamerauppladdning för arbets- eller skolkonton. Det här är **ett känt problem.**

Workarounds:

- Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton. Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning). Från din Microsoft-konto profil i OneDrive du aktivera automatisk överföring av kamerarulle i bakgrunden.

- Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive appen. Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive appen. Välj knappen **+** och välj **Upload**. Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > Kamerarulle**. Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.

[Tillbaka till listan](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens svarar inte eller startar inte

Om ditt HoloLens inte startar:

- Om lysdioderna bredvid strömknappen inte tänds, eller bara en lysdiod blinkar en kort stund, kan du behöva [ladda HoloLens.](hololens2-charging.md#charging-the-device)
- Om lysdioderna tänds när du trycker på strömknappen men du inte kan se något på skärmarna, gör du en hård [återställning av enheten.](hololens-recovery.md#hard-restart-procedure)

Om ditt HoloLens blir låst eller inte svarar:

- Stäng av HoloLens genom att trycka på strömknappen tills alla fem lysdioderna stänger av sig själva eller i 15 sekunder om lysdioderna inte svarar. Starta din HoloLens genom att trycka på strömknappen igen.

Om de här stegen inte fungerar kan du försöka återställa din [HoloLens 2-enhet](hololens-recovery.md) [eller HoloLens (första generationens) enhet.](hololens1-recovery.md)

[Tillbaka till listan](#list)

## <a name="low-disk-space-error"></a>Fel om "lågt diskutrymme"

Du måste frigöra lagringsutrymme genom att göra något av följande:

- Ta bort vissa blanksteg som inte används. Gå till **Inställningar**  >    >  **systemutrymmen,** välj ett utrymme som du inte längre behöver och välj sedan Ta **bort.**
- Ta bort några av hologrammen som du har placerat.
- Ta bort några bilder och videor från Photos appen.
- Avinstallera några appar från din HoloLens. I listan **Alla appar** trycker du på och håller ned den app som du vill avinstallera och väljer sedan **Avinstallera.**

[Tillbaka till listan](#list)

## <a name="calibration-fails"></a>Kalibreringen misslyckas

Kalibrering bör fungera för de flesta, men det finns fall där kalibreringen misslyckas.
  
Några möjliga orsaker till kalibreringsfel är:

- Bli störande och inte följa kalibreringsmålen
- Fel på enhetens eller enhetens visor-programmet är inte korrekt placerad
- Dirty or scratched glass
- Vissa typer av kontaktlinser och glasögon (färgade kontaktobjektiv, vissa toric kontaktobjektiv, IR-blockeringsglasögon, vissa glasögon med höga glasögon, solglasögon eller liknande)
- Mer uttalad snedstreckstillägg
- Behåring eller tjockt glasögonramar om de blockerar enheten från att se dina ögon
- Vissa ögonoperationer, ögontillstånd eller ögonoperationer, till exempel smala ögon, långa ögonfransar, amblyopia, nystagmus, vissa fall av LASIK eller andra ögonoperationer

Om kalibreringen misslyckas försöker du:

- Rensa enhetsvisorn
- Rensa glasögon
- Push-pusha enhetsvisor-programmet så nära dina ögon som möjligt
- Flytta objekt i dittvisor-program från vägen (till exempel hår)
- Slå på en lampa i rummet eller flytta ut direkt från rummet

Om du har följt alla riktlinjer och kalibreringen fortfarande inte fungerar kan du inaktivera kalibreringsuppmaning i Inställningar. Meddela oss också genom att skicka feedback i [Feedbackhubben](hololens-feedback.md).

Se även relaterad information för felsökning [av bildfärg eller ljusstyrka.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Ipd-inställningen gäller inte för HoloLens 2, eftersom ögonpositionerna beräknas av systemet. 

[Tillbaka till listan](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Det går inte att logga in eftersom HoloLens tidigare har ställts in för någon annan

Du kan [placera enheten i **flashläge och använda** Advanced Recovery Companion för](hololens-recovery.md#clean-reflash-the-device) att återställa enheten.

[Tillbaka till listan](#list)


## <a name="unity-isnt-working"></a>Unity fungerar inte

- Se [Installera verktygen för](/windows/mixed-reality/install-the-tools) den senaste versionen av Unity som rekommenderas för HoloLens utveckling.
- Kända problem med Unity HoloLens Technical Preview dokumenteras i de HoloLens [Unity-forumen](https://forum.unity3d.com/threads/known-issues.394627/).

[Tillbaka till listan](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Enhetsportalen fungerar inte korrekt

- Funktionen Förhandsgranskning i Mixed Reality kan uppvisa flera sekunders svarstid.

- På sidan Virtuella indata fungerar inte kontrollerna Gester och Rullning under avsnittet Virtuella gester. Att använda dem har ingen effekt. Det virtuella tangentbordet på den virtuella indatasidan fungerar korrekt.

- När du har aktiverat utvecklarläget i Inställningar kan det ta några sekunder innan växlingen aktiveras så att Enhetsportalen aktiveras.

[Tillbaka till listan](#list)

## <a name="the-hololens-emulator-isnt-working"></a>Den HoloLens Emulator fungerar inte

Information om HoloLens finns i vår utvecklardokumentation.  Läs mer om [felsökning av HoloLens emulatorn](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


- Alla appar i Microsoft Store är inte kompatibla med emulatorn. Till exempel är Young Conker och Fragment inte spelbara i emulatorn.
- Du kan inte använda pc-webbkameran i Emulator.
- Funktionen Live-förhandsgranskning i Windows Enhetsportalen fungerar inte med emulatorn. Du kan fortfarande samla Mixed Reality videor och bilder.

[Tillbaka till listan](#list)

## <a name="voice-commands-arent-working"></a>Röstkommandon fungerar inte

Om Cortana svarar på dina röstkommandon kontrollerar du att Cortana är aktiverat. I listan Alla appar väljer du **notebook-Cortana**  >    >    >  **notebook-Inställningar** för att göra ändringar. Mer information om vad du kan säga finns i [Använda din röst med HoloLens](hololens-cortana.md).

På HoloLens (första generationen) går det inte att konfigurera inbyggd taligenkänning. Den är alltid aktiverad. På HoloLens 2 kan du välja om du vill aktivera både taligenkänning och Cortana under enhetskonfigurationen.

Om din HoloLens 2 inte svarar på din röst kontrollerar du att Taligenkänning är aktiverat. Gå till **Starta**  >  **Inställningar**  >    >  **Sekretesstal** och aktivera **Taligenkänning.**

[Tillbaka till listan](#list)

## <a name="hand-input-isnt-working"></a>Handindata fungerar inte

För att HoloLens ska kunna se dina händer måste du hålla dem inom gestens ram.  Startsidan Mixed Reality feedback som meddelar dig när dina händer spåras.  Feedbacken är annorlunda i olika versioner av HoloLens:

- På HoloLens (första generationen) ändras blickmarkören från en punkt till en ring
- På HoloLens 2 visas en markör med markören nära en pektavla och en handröta visas när pektangenterna ligger längre bort

Många integrerande appar följer indatamönster som liknar Mixed Reality Home.  Läs mer om att använda [handindata HoloLens (första generationen)](hololens1-basic-usage.md#use-hololens-with-your-hands) och [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Observera att vissa typer av handsken inte fungerar med handspårning om du använder handsken.  Ett vanligt exempel är svarta handskes, som tenderar att absorbera IR-ljus och inte hämtas av djupkameran.  Om ditt arbete omfattar skyddshandske rekommenderar vi att du provar en ljusare färg, till exempel blå eller grå.  Ett annat exempel är stora baggy gloves, som tenderar att dölja formen på din hand. Vi rekommenderar att du använder så väl formpassning som möjligt för bästa resultat.

Om ditt visir har fingeravtryck eller utsmetning använder du mikrofiberrensningsmeden som HoloLens för att rensa visorn.

[Tillbaka till listan](#list)

## <a name="cant-connect-to-wi-fi"></a>Det går inte att ansluta till Wi-Fi

Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:

- Kontrollera att Wi-Fi är aktiverat. Kontrollera genom att använda gesten Start och välj sedan **Inställningar**  >  **&amp; Internet-Wi-Fi**  >  **för nätverk.** Om Wi-Fi är på kan du prova att stänga av och sedan aktivera det igen.
- Flytta datorn närmare routern eller åtkomstpunkten.
- Starta om Wi-Fi router och starta [sedan om HoloLens](hololens-recovery.md). Försök att ansluta igen.
- Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran. Du hittar den här informationen på tillverkarens webbplats.

[Tillbaka till listan](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth-enheter parkopplas inte

Om du har problem med [att koppla Bluetooth enhet](hololens-connect-devices.md)kan du prova följande:

- Gå till **Inställningar**  >  **Enheter** och kontrollera att Bluetooth är aktiverat. Om den är det inaktiverar du den och sätter på den igen.
- Kontrollera att din Bluetooth är helt debiterad eller har nya batterier.
- Om du fortfarande inte kan ansluta startar [du om HoloLens](hololens-recovery.md).

[Tillbaka till listan](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-mikrofonen fungerar inte

Tänk på att vissa USB-C-mikrofoner felaktigt rapporterar sig själva som både *en mikrofon och* en talare. Det här är ett problem med mikrofonen och inte med HoloLens. När du ansluter en av dessa mikrofoner HoloLens kan ljudet gå förlorat. Lyckligtvis finns det en enkel korrigering.  

I **Inställningar**  ->    ->  **systemljud** anger du uttryckligen de inbyggda talarna **(Analog Feature Audio Driver)** som **standardenheten**. HoloLens den här inställningen även om mikrofonen tas bort och återansluts senare.

![Felsöka USB-C-mikrofoner.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Enheter som anges som tillgängliga Inställningar inte fungerar

HoloLens (första generationen) stöder inte Bluetooth ljudprofiler. Bluetooth ljudenheter, till exempel högtalare och headset, kan visas som tillgängliga i HoloLens,men de stöds inte.

HoloLens 2 stöder Bluetooth A2DP-ljudprofilen för stereouppspelning. Profilen Bluetooth handsfree som aktiverar mikrofoninfångning från en Bluetooth kringutrustning stöds inte på HoloLens 2.

Om du har problem med att Bluetooth en enhet kontrollerar du att det är en enhet som stöds. Enheter som stöds är följande:

- QWERTY på engelska Bluetooth tangentbord (du kan använda dem var du än använder det holografiska tangentbordet).
- Bluetooth mice.
- Klicka [HoloLens .](hololens1-clicker.md)

Du kan koppla samman Bluetooth HID- och GATT-enheter med HoloLens. Du kan dock behöva installera motsvarande tillhörande appar från Microsoft Store att använda enheterna.

[Tillbaka till listan](#list)
