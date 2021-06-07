---
title: HoloLens 2 – information
description: Håll dig uppdaterad med alla uppdateringar i varje ny HoloLens 2-version.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378883"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 – information

För att säkerställa att du får en produktiv upplevelse med dina HoloLens-enheter fortsätter vi att släppa funktions-, bugg- och säkerhetsuppdateringar. På den här sidan kan du se vad som är nytt för HoloLens varje månad. Om du vill hämta den senaste HoloLens 2-uppdateringen kan du antingen söka efter uppdateringar och uppdatera manuellt eller få FFU (Full Flash Update) att [flasha](hololens-recovery.md#clean-reflash-the-device)enheten via Advanced Recovery Companion . [](hololens-update-hololens.md#check-for-updates-and-manually-update) [Nedladdningen](https://aka.ms/hololens2download) hålls uppdaterad och ger den senaste allmänt tillgängliga versionen.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, version 21H1
- Build-version 20346.1002

Den här uppdateringen innehåller funktioner för två målgrupper: funktioner som kan användas av vem som helst på en enhet av slutanvändaren och nya enhetshanteringsalternativ som kan konfigureras av IT-administratörer. I tabellen nedan anges de funktioner som är relevanta för varje målgrupp. Om du är IT-administratör kan du ta en titt på vår [checklista för IT-administratör – Uppdatera.](#it-admin---update-checklist)
>[!IMPORTANT]
>För att kunna uppdatera till den här versionen måste HoloLens 2-enheter för närvarande köra uppdateringen från februari 2021 (version 19041.1136) eller nyare. Om du inte ser den här funktionsuppdateringen bör du först uppdatera enheten och försöka igen.

>[!NOTE]
>Idag stöder Microsoft HoloLens 2 månatliga underhållsuppdateringar (bugg- och säkerhetskorrigeringar) för följande versioner:
>- Windows Holographic, version 20H2 (Build 19041.1128+)
>- Windows Holographic, version 2004 (Build 19041.1103+)
>- Windows Holographic, version 1903 (Build 18362+) 
>
> I och med introduktionen av Windows Holographic version 21H1 erbjuder vi månatliga underhållsuppdateringar för **Windows Holographic version 1903.** Detta gör att vi kan fokusera på nyare versioner och fortsätta att leverera värdefulla förbättringar. 


| Funktionsnamn                                              | Kort beskrivning                                                                      | Målgrupp | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Ny Microsoft Edge](#introducing-the-new-microsoft-edge)  | Den nya Chromium-baserade Microsoft Edge är nu tillgänglig för HoloLens 2. | Slutanvändare | 
[WebXR och 360 Viewer](#webxr-and-360-viewer) | Prova integrerande webbupplevelser och 360-videouppspelning. | Slutanvändare | 
[Ny inställningsapp](#new-settings-app) | Den äldre inställningsappen ersätts av en uppdaterad version med nya funktioner och inställningar. | Slutanvändare |
[Kalibrering av visningsfärg](#display-color-calibration) | Välj en alternativ färgprofil för holoLens 2-visningen. | Slutanvändare |
[Standardappväljare](#default-app-picker) | Välj vilken app som ska starta för varje fil eller länktyp. | Slutanvändare |
[Volymkontroll per app](#per-app-volume-control) | Kontrollera volym på appnivå oberoende av systemvolym. | Slutanvändare |
[Installera webbappar](#install-web-apps) | Installera webbappar på HoloLens 2, till exempel Microsoft Office, med den nya Microsoft Edge webbläsaren. | Slutanvändare |
[Svep till typ](#swipe-to-type) | Använd fingertipset för att "svepa" ord på det holografiska tangentbordet. | Slutanvändare |
[Energimeny från Start](#power-menu-from-start) | Starta om och stäng av HoloLens-enheten på Start-menyn. | Slutanvändare |
[Flera användare visas på inloggningsskärmen](#multiple-users-listed-on-sign-in-screen) | Visa flera användarkonton på skärmen Logga in. | Slutanvändare |
[Stöd för extern USB-C-mikrofon](#usb-c-external-microphone-support) | Använd USB-C-mikrofoner för appar och/eller Fjärrhjälp. | Slutanvändare |
[Besökarinloggning automatiskt för kiosker](#visitor-auto-logon-for-kiosks) | Aktiverar automatisk inloggning på besökarkonton som ska användas för helskärmsläge. | IT-administratör |
[Nya AUMID:er för nya appar i helskärmsläge](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMID för nya inställningar och Edge-appar. | IT-administratör |
[Förbättrad fel vid leverans i helskärmsläge](#kiosk-mode-behavior-changes-for-handling-of-failures) | Helskärmsläge söker efter global tilldelad åtkomst innan den tomma startmenyn. | IT-administratör |
[Nya inställningarURI:er för synlighet för sidinställningar](#new-settings-uris-for-page-settings-visibility) | 20+ nya SettingsURIs för principen Settings/PageVisibilityList. | IT-administratör |
[Konfigurera återställningsdiagnostik](#configuring-fallback-diagnostics-via-settings-app) | Ange återställningsdiagnostikbeteende i inställningsappen. | IT-administratör |
[Dela saker med enheter i närheten](#share-things-with-nearby-devices) | Dela filer eller URL:er från en HoloLens till en dator. | Alla |
[Nya os-diagnostikspårningar](#new-os-diagnostic-traces) | Ny felsökare i Inställningar för OS-uppdateringar. | IT-administratör |
[Leveransoptimering förhandsversion](#delivery-optimization-preview) | Minska bandbreddsförbrukningen för nedladdningar från flera HoloLens-enheter. | IT-administratör |

Läs relaterad information:

- [Besök HoloLens Emulator-arkivet](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Fjärrhjälp för Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-guider](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Introduktion till det nya Microsoft Edge

![Animering av en Microsoft Edge logotyp till en Microsoft Edge logotyp](images/new-edge.gif)

Den nya Microsoft Edge [använder Chromium-projektet](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) med öppen källkod för att skapa bättre kompatibilitet för kunder och mindre fragmentering av webben för webbutvecklare.

> [!IMPORTANT]
> Den här Microsoft Edge ersätter automatiskt äldre Microsoft Edge, som [inte längre stöds](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) i nya versioner.

![Skärmbild Microsoft Edge ny app](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Starta den nya Microsoft Edge

Den nya Microsoft Edge ![ikon Microsoft Edge nytt program](images/new_edge_logo.png) (representeras av en blå och grön virvelikon) fästs på Start-menyn och startas automatiskt när du aktiverar en webblänk.

> [!NOTE]
> När du startar den nya Microsoft Edge på HoloLens 2 importeras dina inställningar och data från äldre Microsoft Edge. Om du fortsätter att använda äldre Microsoft Edge när du har lanserat den nya Microsoft Edge kommer dessa nya data inte att synkroniseras från äldre Microsoft Edge till den nya Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurera principinställningar för den nya Microsoft Edge

Den nya Microsoft Edge erbjuder IT-administratörer en mycket bredare uppsättning webbläsarprinciper på HoloLens 2 än vad som tidigare var tillgängligt med äldre Microsoft Edge.

Här är några användbara resurser för att lära dig mer om att hantera principinställningar för den nya Microsoft Edge:

- [Konfigurera Microsoft Edge principinställningar med Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge (äldre version) till Microsoft Edge principmappning](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome för Microsoft Edge principmappning](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Fullständig [Microsoft Edge Enterprise-dokumentation](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> På grund av mängden webbläsarprinciper som stöds av den nya Microsoft Edge kan vårt team inte garantera att varje ny princip fungerar på HoloLens 2. Vi har dock testat och bekräftat att den nya Microsoft Edge motsvarigheten till varje äldre Microsoft Edge princip som tidigare hade stöd för HoloLens 2 fungerar som förväntat. Se [Microsoft Edge (äldre version) att Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) principmappning för att hitta den nya Microsoft Edge motsvarigheten till varje äldre Microsoft Edge webbläsarprincip som du använde med HoloLens 2.
>
> Det finns minst två nya Microsoft Edge som vi vet inte *kommer att fungera* med HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Vad du kan förvänta dig av den nya Microsoft Edge på HoloLens 2

Eftersom den nya Microsoft Edge är en inbyggd Win32-app med ett nytt UWP-adapterlager som gör att den kan köras på enheter som endast UWP, till exempel HoloLens 2, kanske vissa funktioner inte är omedelbart tillgängliga. Vi kommer att stödja nya scenarier och funktioner under de kommande månaderna, så kontrollera det här utrymmet för att få uppdaterad information.

**Scenarier och funktioner som förväntas fungera:**
- Första körningen, logga in på profilen och synkronisera
- Webbplatser bör återges och fungera som förväntat
- De flesta webbläsarfunktioner (favoriter, historik osv.) bör fungera som förväntat
- Mörkt läge
- Installera webbappar på enheten
- Installera tillägg (hör av dig till oss om du använder tillägg som inte fungerar korrekt på HoloLens 2)
- Visa och markera en PDF
- Rumsligt ljud från ett enda webbläsarfönster
- Automatisk och manuell uppdatering av webbläsaren
- Spara en PDF från menyn Skriv ut (med alternativet Spara till PDF)
- WebXR- och 360 Viewer-tillägg
- Innehållsåterställning till rätt fönster vid bläddring över flera fönster i din miljö

**Scenarier och funktioner förväntas inte fungera:**
- Rumsligt ljud från flera fönster med samtidiga ljudströmmar
- "Se det, säg det"
- Skriva ut

**Kända problem i webbläsaren:**

- Förhandsgranskningen av förstoringsglaset i det holografiska tangentbordet har inaktiverats för den nya Microsoft Edge. Vi hoppas kunna återerera den här funktionen i en kommande uppdatering när förstoringsglaset fungerar som det ska.
- Ljud kan spelas upp från fel webbläsarfönster om du har ett annat webbläsarfönster öppet och aktivt. Du kan komma runt det här problemet genom att stänga det andra aktiva fönstret som inte ska spela upp ljud.
- När du spelar upp ljud från ett webbläsarfönster i [läget "Följ mig"](hololens2-basic-usage.md#follow-me-stop-following)fortsätter ljudet att spelas upp om du inaktiverar läget "Följ mig". Du kan komma runt det här problemet genom att stoppa ljuduppspelningen innan du inaktiverar läget "Följ mig" eller genom att stänga fönstret med **X-knappen.**
- Om du interagerar Microsoft Edge aktiva program kan andra 2D-appfönster oväntat inaktiveras. Du kan återaktivera dessa fönster genom att interagera med dem igen.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-kanaler

Teamet Microsoft Edge tre förhandsgranskningskanaler tillgängliga för Edge Insider-communityn: Beta, Dev och Canary. När du installerar en förhandsgranskningskanal avinstalleras inte den utgivna versionen Microsoft Edge på din HoloLens 2, och du kan installera fler än en på samma gång. 

Besök startsidan [Microsoft Edge Insider om du](https://www.microsoftedgeinsider.com) vill veta mer om Edge Insider-communityn. Om du vill veta mer om de olika Edge Insider-kanalerna och komma igång kan du gå till [nedladdningssidan för Edge Insider.](https://www.microsoftedgeinsider.com/download)

Det finns några tillgängliga metoder för att installera Microsoft Edge Insider-kanaler till HoloLens 2:

**Direktinstallation på enheten (för närvarande endast tillgängligt för ohanterade enheter)**
  1. På din HoloLens 2 går du till [nedladdningssidan för Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Välj knappen **Ladda ned för HoloLens 2** för den Edge Insider-kanal som du vill installera.
  1. Starta den nedladdade MSIX-filen från Edge-nedladdningskön eller från enhetens mapp "Nedladdningar" (med Utforskaren).
  1. [Appinstallationsprogrammet](app-deploy-app-installer.md) startas.
  1. Välj **knappen** Installera.
  1. Efter en lyckad installation hittar du Microsoft Edge Beta, Dev eller Canary som en separat **post i Alla appar** listan över Start-menyn.

**Installera via pc med Windows Enhetsportalen [(kräver att utvecklarläge](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) är aktiverat på HoloLens 2)**
  1. Gå till nedladdningssidan för [Edge Insider på din dator.](https://www.microsoftedgeinsider.com/download)
  1. Välj knappen med listrutan bredvid knappen "Download for Windows 10" (Ladda ned för Windows 10) för den Edge **Insider-kanal** som du vill installera.
  1. Välj **HoloLens 2** i den nedrullningsna menyn.
  1. Spara .msix-filen i mappen "Nedladdningar" på datorn (eller en annan mapp som du enkelt kan hitta).
  1. Använd [Windows Enhetsportalen](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) på datorn för att installera den nedladdade MSIX-filen på HoloLens 2.
  1. Efter en lyckad installation hittar du Microsoft Edge Beta, Dev eller Canary som en separat **post i Alla appar** listan över Start-menyn.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Använda WDAC för att blockera nya Microsoft Edge

För att IT-administratörer ska kunna uppdatera [sin WDAC-princip](windows-defender-application-control-wdac.md) för att blockera den nya Microsoft Edge-appen måste du lägga till följande i principen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Hantera slutpunkter för den nya Microsoft Edge

Vissa miljöer kan ha nätverksbegränsningar att ta hänsyn till som ett övervägande. Aktivera dessa Microsoft-slutpunkter för att säkerställa en smidig upplevelse med den [nya Edge.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Läs mer om de tillgängliga [slutpunkterna för HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Installera webbappar
 > [!Note]
>Från och [med Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)kommer Office-webbappen inte längre vara förinstallerad.

Du kan använda den nya Edge för att installera webbappar tillsammans Microsoft Store appar. Du kan till exempel installera Microsoft Office webbapp för att visa och redigera filer som finns på SharePoint eller OneDrive. Om du vill installera Office-webbappen går du till och väljer knappen Tillgänglig app https://www.office.com **eller Installera Office** i adressfältet.  Bekräfta **genom att** välja Installera.

> [!IMPORTANT]
> Funktionen för Office-webbapp är endast tillgänglig när din HoloLens 2 har en aktiv Internetanslutning.

### <a name="webxr-and-360-viewer"></a>WebXR och 360 Viewer

Den nya Microsoft Edge har stöd för WebXR, som är den nya standarden för att skapa integrerande webbupplevelser (ersätt WebVR). Många avancerade webbupplevelser har utformats med VR i åtanke (de ersätter ditt synfält med en virtuell miljö), men dessa upplevelser stöds också av HoloLens 2. WebXR-standarden möjliggör även förhöjda och integrerande webbupplevelser med mixad verklighet som använder din fysiska miljö. När utvecklare ägnar mer tid åt WebXR förväntar vi oss att nya förhöjda upplevelser och integrerande upplevelser med mixad verklighet kommer för HoloLens 2-kunder att testa!

360 Viewer-tillägget bygger på WebXR och installeras automatiskt tillsammans med den nya Microsoft Edge på HoloLens 2. Det här webbtillägget ger dig möjlighet att fördjupa dig i 360 graders videor. YouTube erbjuder det största urvalet av 360 videor, så vi rekommenderar att du börjar där.

#### <a name="how-to-use-webxr"></a>Så här använder du WebXR

1. Gå till en webbplats med Stöd för WebXR.
1. Välj knappen **Enter VR** (Ange VR) på webbplatsen. Platsen och den visuella representationen av den här knappen kan variera beroende på webbplats, men den kan se ut ungefär så här:

    ![Ange exempel på VR-knapp](images/75px-enter-vr.png)

1. Första gången du försöker starta en WebXR-upplevelse på en specifik domän ber webbläsaren om medgivande att ange en integrerande vy och väljer **Tillåt**.
1. Använd [HoloLens 2-gester](hololens2-basic-usage.md#the-hand-tracking-frame) för att manipulera upplevelsen.
1. Om upplevelsen inte har en exit-knapp **använder du** gesten [Start för](hololens2-basic-usage.md#start-gesture) att gå tillbaka hem.

**Rekommenderade WebXR-exempel**
- 360 Viewer (se nästa avsnitt)
- [XR-apparat](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Använda 360 Viewer

1. Gå till en 360 graders video på YouTube.
1. I videoramen väljer du headsetknappen för mixad verklighet:

    ![Knapp för att aktivera 360 Viewer](images/enter-360-viewer.jpg)

1. Första gången du försöker starta 360 Viewer på en specifik domän ber webbläsaren om medgivande för att komma in i en integrerande vy. Välj **Tillåt**.
1. [Tryck i luften](hololens2-basic-usage.md#select-using-air-tap) för att öppna uppspelningskontrollerna. Använd [handbilder och](hololens2-basic-usage.md#select-using-air-tap) tryck i luften för att spela upp/pausa, hoppa framåt/bakåt, aktivera/inaktivera undertexter eller stoppa upplevelsen (som avslutar den integrerande vyn). Uppspelningskontrollerna försvinner efter några sekunders inaktivitet.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Kända problem med WebXR och 360 Viewer
- Beroende på komplexiteten i WebXR-upplevelsen kan bildrutefrekvensen släppas eller sjunker.
- Stöd för tydligt handstöd i WebXR är inte aktiverat som standard. Utvecklare kan aktivera support via `edge://flags` genom att aktivera "WebXR Hand Input".
- 360 videor från andra webbplatser än YouTube kanske inte fungerar som förväntat.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Ge feedback om WebXR och 360 Viewer

Dela feedback och buggar med vårt team via **funktionen Skicka feedback** i det nya Microsoft Edge.

### <a name="new-settings-app"></a>Ny inställningsapp

I den här versionen introducerar vi en ny version av appen Inställningar. Den nya appen Inställningar innehåller nya funktioner och utökade inställningar för HoloLens 2 inom följande områden: Ljud, Power &-strömsparläge, Network & Internet, Appar, konton, Hjälpmedel med mera.

> [!NOTE]
> Eftersom den nya appen Inställningar skiljer sig från den äldre inställningsappen tas eventuella inställningsfönster som du tidigare placerat runt din miljö bort vid uppdateringen.

![Startsida för appen Nya inställningar](images/new-settings-app.png)

**Nya funktioner och inställningar**
- Inställningssökning: Sök efter inställningar från startsidan inställningar med nyckelord eller inställningens namn.
- System > Sound:
  - Enheter för indata- och utdataljud: Välj dina indata- och utdataljudenheter oberoende av varandra (till exempel lyssna på ljud via Bluetooth-ljud eller använd en USB-C-mikrofon för ljudindata).
    > [!NOTE]
    > Bluetooth-mikrofoner stöds inte av HoloLens 2.
  - Appvolym: justera volymen för varje app oberoende av varandra. Se [volymkontrollen per app.](#per-app-volume-control)
- System > ström & sparläge: Välj när enheten ska förströms i strömsparläge efter en tids inaktivitet.
- System > Batteri: aktivera batterisparfunktion manuellt eller ange ett tröskelvärde för batteri vid vilket tidpunkt batterisparfunktion aktiveras automatiskt.
- Enheter > USB: du kan inaktivera USB-anslutningar som standard.
- Nätverk & Internet:
  - USB-C Ethernet-kort visas nu i Network & Internet.
  - Inställningar för USB-C Ethernet-adapter är nu tillgängliga, inklusive dess IP-adress.
  - Nu kan du aktivera flygplansläge på HoloLens 2.
- Appar: du kan återställa de standardappar som används för fil- och länktyper. Mer information finns i [Standardappväljaren](#default-app-picker).
- Konton > Andra användare: enhetsägare kan lägga till användare, uppgradera standardanvändare till enhetsägare, nedgradera enhetsägare till standardanvändare och ta bort användare.
- Hjälpmedel: ändra textstorlek och vissa visuella effekter.

**Kända problem**
- Tidigare placerade inställningsfönster tas bort (se anteckningen ovan).
- Du kan inte längre byta namn på enheten med appen Inställningar. IT-administratörer kan byta namn på enheter med [hjälp av enhetsnamnmallen Windows Autopilot för HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) eller [CSP-noden](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) MDM DevDetail Ext/Microsoft/DNSComputerName.
- Ethernet-sidan visar en virtuell Ethernet-enhet ("UsbNcm") hela tiden.
- Batterianvändningen för den nya Microsoft Edge kanske inte är korrekt, på grund av dess natur som ett Win32-skrivbordsprogram som stöds av ett UWP-adapterlager (ingen korrigering förväntas snart).

#### <a name="display-color-calibration"></a>Kalibrering av visningsfärg



Med den här nya inställningen kan du välja en alternativ färgprofil för holoLens 2-skärmen. Detta kan hjälpa färger att se mer exakta ut, särskilt på lägre nivåer av skärmens ljusstyrka. Du hittar kalibrering av bildskärmsfärg i appen Inställningar på sidan System > Kalibrering.

> [!NOTE]
> Eftersom den här inställningen sparar en ny färgprofil i den inbyggda programvaran för visning är det en inställning per enhet (och inte unik för varje användarkonto).

##### <a name="how-to-use-display-color-calibration"></a>Så här använder du kalibrering av visningsfärg

1. Starta appen **Inställningar** och gå till **System > Kalibrering.**
1. Under **Kalibrering av visningsfärg** väljer du knappen **Kör kalibrering av visningsfärg.**
1. Kalibreringsupplevelsen för bildskärmsfärg startar och uppmuntrar dig att se till att ditt visor-program är på rätt plats.
1. När du har gått igenom dialogrutorna för instruktioner blir skärmen automatiskt nedtonad till 30 % ljusstyrka.
    > [!TIP]
    > Om du har problem med att se den nedtonade scenen i din miljö kan du manuellt justera ljusstyrkan på HoloLens 2 med hjälp av ljusstyrka-knapparna till vänster på enheten.
1. Välj knappar 1–6 för att omedelbart prova varje färgprofil och hitta en som ser bäst ut för dina ögon (detta innebär vanligtvis den profil som hjälper scenen att verka mest neutral, med gråskalningsmönster och hudtoner som ser ut som förväntat.)

    ![Visa färgavvisningsscen](images/color-cal-ui.png)
    
1. När du är nöjd med den valda profilen väljer du knappen **Spara & Avsluta**
1. Om du föredrar att inte göra ändringar väljer du **knappen Avbryt & Avsluta** så återställs dina ändringar

> [!TIP]
> Här är några användbara tips att tänka på när du använder inställningen för kalibrering av bildskärmsfärg:
> - Du kan köra kalibrering av visningsfärg på nya sätt från Inställningar när du vill
> - Om någon på enheten tidigare har använt inställningen för att ändra färgprofiler visas datum/tid för den senaste ändringen på sidan Inställningar
> - När du kör kalibreringen av bildskärmsfärgen markeras den färgprofil som sparades tidigare och Profil 0 visas inte (eftersom Profil 0 representerar visningens ursprungliga färgprofil)
> - Om du vill återgå till visningens ursprungliga färgprofil kan du göra det från sidan Inställningar (se hur [du återställer färgprofilen](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Återställa färgprofilen 

Om du är missnöjd med den anpassade färgprofilen som sparats till din HoloLens 2 kan du återställa enhetens ursprungliga färgprofil:
1. Starta appen **Inställningar** och gå till **System > Kalibrering.**
1. Under **kalibrering av visningsfärg** väljer du **knappen Återställ till standardfärgprofil.**
1. När dialogrutan öppnas väljer du Starta **om** om du är redo att starta om HoloLens 2 och tillämpa ändringarna.

#### <a name="top-display-color-calibration-known-issues"></a>Kända problem med kalibrering av de främsta bildskärmsfärgerna

- På sidan Inställningar visas statussträngen som anger när färgprofilen senast ändrades tills du läser in sidan på nytt i Inställningar.
    - Lösning: Välj en annan inställningssida och välj sedan sidan Kalibrering igen.

#### <a name="default-app-picker"></a>Standardappväljare

När du aktiverar en hyperlänk eller öppnar en filtyp med fler än en installerad app, vilket stöder det, visas ett nytt fönster med en uppmaning om att välja vilken installerad app som ska hantera filen eller länktypen. I det här fönstret kan du också välja att den valda appen ska hantera filen eller länktypen "En gång" eller "Alltid".

Om du väljer "Alltid" men senare vill ändra vilken app som hanterar en viss fil eller länktyp kan du återställa dina sparade standardvärden i **Inställningar > Appar.** Rulla längst ned på sidan och välj knappen **Rensa** under "Standardappar för filtyper" och/eller "Standardappar för länktyper". Till skillnad från liknande inställning på stationära datorer kan du inte återställa standardvärden för enskilda filtyper.

#### <a name="per-app-volume-control"></a>Volymkontroll per app

I den här Windows-versionen kan användarna justera volymnivån för varje app manuellt. På så sätt kan användarna bättre fokusera på de appar som de behöver, eller bättre höra när de använder flera appar. Till exempel att behöva stänga av volymen för en app när en annan person anropas för fjärrhjälp i en annan.

Om du vill ange volymen för en enskild app går du till **Inställningar**  ->    ->  **Systemljud** och under Avancerade ljudalternativ väljer **du Appvolym och enhetsinställningar.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Svep till typ

Vissa kunder tycker att det går snabbare att "skriva" på virtuella tangentbord genom att svepa formen på ordet som de tänker skriva, och vi förhandsgranskar den här funktionen för det holografiska tangentbordet. Du kan svepa ett ord i taget genom att skicka fingertipset genom det holografiska tangentbordets plan, svepa formen på ordet och sedan dra upp fingertipset från tangentbordets plan. Du kan svepa upp uppföljningsord utan att behöva trycka på blanksteget genom att ta bort ditt finger från tangentbordet mellan ord. Du vet att funktionen fungerar om du ser en svepspår efter ditt fingerförflyttning på tangentbordet.

Observera att den här funktionen kan vara svår att använda och bemästra på grund av den typ av holografiskt tangentbord där du inte känner dig motståndskraftig mot ditt finger (till skillnad från en mobiltelefonvisning). 

### <a name="power-menu-from-start"></a>Energimeny från Start

En ny meny där användaren kan logga ut, stänga av och starta om enheten. En indikator i HoloLens-Startskärmen som visar när en systemuppdatering är tillgänglig.

#### <a name="how-to-use"></a>Använd så här

1. Öppna HoloLens-Startskärmen med [startgesten eller](hololens2-basic-usage.md#start-gesture) säga "Go to Start".

2. Lägg märke till ellipsikonen (...) bredvid användarprofilbilden:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Välj användarprofilbilden med dina händer eller röstkommandot "Power".

4. En meny visas med alternativ för att logga ut, starta om eller stänga av enheten:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Välj menyalternativ för att logga ut, starta om eller stänga av hololens. Alternativet Logga ut kanske inte är tillgängligt om enheten har ställts in för ett enskilt [Microsoft-konto (MSA) eller ett lokalt konto.](hololens-identity.md)

6. Stäng menyn genom att trycka någon annanstans eller stänga Start-menyn med gesten Start.

#### <a name="update-indicator"></a>Uppdateringsindikator

När en uppdatering är tillgänglig tänds ellipsikonen för att indikera att uppdateringen kommer att startas om. Menyalternativen ändras också för att återspegla förekomsten av uppdateringen.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Flera användare visas på inloggningsskärmen

Tidigare visade inloggningsskärmen endast den senast inloggade användaren, samt en startpunkt för "Annan användare". Vi har fått feedback från kunder om att detta inte räcker om flera användare har loggat in på enheten. De var fortfarande nödvändiga för att skriva in användarnamnet igen.

Introducerades i den här  Windows-versionen. När du väljer Annan användare som finns till höger om fältet PIN-kodspost visas flera användare med tidigare inloggning på enheten på skärmen Logga in. På så sätt kan användarna välja sin användarprofil och sedan logga in med sina Windows Hello autentiseringsuppgifter. En ny användare kan också läggas till på enheten från sidan Andra användare via knappen **Lägg till** konto.

I menyn Andra användare visar knappen Andra användare den senaste användaren som loggat in på enheten. Välj den här knappen för att återgå till inloggningsskärmen för den här användaren.

![Standard för inloggningsskärmen](./images/multiusers1.jpg)

<br>

![Inloggningsskärm för andra användare](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Stöd för extern USB-C-mikrofon

> [!IMPORTANT]
> Om du ansluter **en USB-mic konfigureras den inte automatiskt som indataenhet.** När användare ansluter en uppsättning USB-C-mikrofoner ser de att hörtelefonens ljud automatiskt omdirigeras till mikrofonen, men HoloLens-operativsystemet prioriterar den interna mikrofonmatrisen ovanför andra indataenhet. **Följ stegen nedan om du vill använda en USB-C-mikrofon.**

Användare kan välja USB-C-anslutna externa mikrofoner med hjälp **av panelen** Ljudinställningar. USB-C-mikrofoner kan användas för att anropa, spela in osv.

Öppna appen **Inställningar** och välj   >  **Systemljud.**

![Ljudinställningar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Om du vill använda externa **mikrofoner med Remote Assist** måste användarna klicka på hyperlänken "Hantera ljudenheter".
>
> Använd sedan listrutan för att ange den externa mikrofonen som Standard **eller** **Standard för kommunikation.** Om **du** väljer Standard används den externa mikrofonen överallt.
>
> Om **du väljer Kommunikationsstandard** innebär det att den externa mikrofonen kommer att användas i Remote Assist och andra kommunikationsappar, men HoloLens mic-matrisen kan fortfarande användas för andra uppgifter.

![Hantera ljudenheter](images/usbc-mic-2.png)

<br>

![Ange mikrofonstandard](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Vad gäller för stöd för Bluetooth-mikrofon?

Tyvärr stöds bluetooth-mikrofoner fortfarande inte för närvarande på HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Felsöka USB-C-mikrofoner

Tänk på att vissa USB-C-mikrofoner felaktigt rapporterar sig själva som både *en mikrofon och* en talare. Det här är ett problem med mikrofonen och inte med HoloLens. När någon av dessa mikrofoner ansluts till HoloLens kan ljudet gå förlorat. Lyckligtvis finns det en enkel korrigering.  

I **Inställningar**  ->    ->  **Systemljud** anger du uttryckligen de inbyggda talarna **(Analog Feature Audio Driver)** som **Standardenhet**. HoloLens bör komma ihåg den här inställningen även om mikrofonen tas bort och återansluts senare.

![Felsöka USB-C-mikrofoner](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Besökarinloggning automatiskt för kiosker

Den här nya funktionen gör att automatisk inloggning på besökarkonton kan användas för helskärmsläge.

För en icke-AAD-konfiguration för att konfigurera en enhet för besökarinloggning automatiskt:

1. Skapa ett etableringspaket som:
    1. Konfigurerar **körningsinställningar/AssignedAccess för** att tillåta besökarkonton.
    1. Du kan också registrera enheten i MDM **(Körningsinställningar/Arbetsplats/Registreringar)** så att den kan hanteras senare.
    1. Skapa inte ett lokalt konto
1. [Tillämpa etableringspaketet](hololens-provisioning.md).

För en AAD-konfiguration kan användare uppnå något som liknar detta i dag utan den här ändringen. AAD-anslutna enheter som konfigurerats för helskärmsläge kan logga in på ett besökarkonto med en enda knapptryckning från inloggningsskärmen. När du har loggat in på besökarkontot frågar enheten inte om inloggning igen förrän besökaren uttryckligen loggas ut från Start-menyn eller enheten startas om.

Besökarinloggning automatiskt kan hanteras via anpassad [OMA-URI-princip:](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)

- URI-värde: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Policy  | Beskrivning   | Konfigurationer  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Tillåter att en besökare automatiskt kan logga in på en kiosk   | 1 (Ja), 0 (Nej, standard.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Använda de nya inställningarna och Edge-apparna i helskärmsläge

När appar [inkluderas i helskärmsläge](hololens-kiosk.md)lägger IT-administratören ofta till appen i helskärmsläge men använder dess appanvändarmodell-ID (AUMID). Eftersom både inställningsappen och Microsoft Edge-appen betraktas som nya appar och skiljer sig från de äldre apparna Helskärmsläge som använder AU AUMID för dessa appar måste uppdateras för att använda nya AUMID.

När du ändrar en helskärmsläge så att den innehåller de nya apparna rekommenderar vi att du lägger till i det nya AUMID och lämnar den gamla. Detta skapar en enkel övergång när användarna uppdaterar operativsystemet och behöver inte ta emot nya principer för att fortsätta använda helskärmsläge som avsett.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App för gamla inställningar       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Ny inställningsapp       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Gammal Microsoft Edge app | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Ny Microsoft Edge app | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Beteendeändringar i helskärmsläge för hantering av fel

Om en enhet hade en kioskkonfiguration i äldre versioner, vilket är en kombination av både global tilldelad åtkomst och AAD-gruppmedlem tilldelad åtkomst, skulle användaren inte se något som visas på[Start-menyn](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)om det inte gick att fastställa AAD-gruppmedlemskap.

Från och med den här Windows-versionen används den globala helskärmskonfigurationen (om sådan finns) om det uppstår fel i helskärmsläget för AAD-grupper.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nya inställnings-URI:er för synlighet för sidinställningar

I [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) lade vi till principen [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) för att begränsa de sidor som visas i appen Inställningar. PageVisibilityList är en princip som gör det möjligt för IT-administratörer att antingen förhindra att specifika sidor i appen Systeminställningar visas eller är tillgängliga, eller att göra det för alla sidor utom de som anges.

Om du [besöker Synlighet för sidinställningar](settings-uri-list.md)finns instruktioner för att använda denna CSP och listan över URI:er som var tillgängliga i tidigare versioner.

Vi utökar listan över tillgängliga inställnings-URI:er som IT-administratörer kan hantera. Vissa av dessa URI:er är för nyligen tillgängliga områden i den nya inställningsappen. Om du använder principen Settings/PageVisibilityList granskar du följande lista och justerar dina tillåtna eller blockerade sidor efter behov.

> [!NOTE]
> **Inaktuell: ms-settings:network-proxy**
>
> En inställningssida är inaktuell i dessa nyare byggen. Den gamla **&**  >  **internetproxy** är inte längre tillgänglig som en global inställning. De nya proxyinställningarna per anslutning finns under **Network & Internet**  >  **Wi-Fi Properties (Egenskaper för Internet-Wi-Fi)** eller Network & Internet Ethernet Properties  >   **(Internet**  >  **Ethernet-egenskaper).**  >  

<br>

| Sidan Inställningar                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Appar > Apps & funktioner                               | `ms-settings:appsfeatures`                         |
| Appar > Apps & funktioner > Avancerade alternativ          | `ms-settings:appsfeatures-app`                     |
| Appar > offlinekartor                                  | `ms-settings:maps`                                 |
| Appar > offlinekartor > Hämta kartor                  | `ms-settings:maps-downloadmaps`                    |
| Enheter > mus                                      | `ms-settings:mouse`                                |
| Enheter > USB                                        | `ms-settings:usb`                                  |
| Network & Internet > Airplane mode (Internetläge > nätverk                   | `ms-settings:network-airplanemode`                 |
| Sekretess > allmänt                                    | `ms-settings:privacy-general`                      |
| Sekretess > ink& skriva anpassning             | `ms-settings:privacy-speechtyping`                 |
| Sekretess > rörelse                                     | `ms-settings:privacy-motion`                       |
| Sekretess > Skärmbild av kantlinjer                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Sekretess > Skärmbilder och appar                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Batteri                                     | `ms-settings:batterysaver`                         |
| System > Batteri                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > appvolym och enhetsinställningar | `ms-settings:apps-volume`                          |
| System > Sound > Manage sound devices (System > Sound > Manage sound devices (Hantera ljudenheter)              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Tid & för > datum & tid                        | `ms-settings:dateandtime`                          |
| Time & Language > tangentbord                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Uppdatera & Security > Återställ & återställning               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Uppdaterade URI:er

Tidigare skulle följande två URI:er inte ta en användare direkt till de angivna sidorna, utan blockerade endast huvudsidan för uppdateringar. Följande objekt har uppdaterats för att dirigeras till deras sidor:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurera återställningsdiagnostik via inställningsappen

I Inställningsappen kan en användare nu konfigurera beteendet för [Återställningsdiagnostik.](hololens-diagnostic-logs.md) I appen Inställningar går du till sidan  ->  **Sekretessfelsökning** för att konfigurera den här inställningen.

> [!NOTE]
> Om MDM-principen har konfigurerats för enheten kan användaren inte åsidosätta det beteendet.  

### <a name="share-things-with-nearby-devices"></a>Dela saker med enheter i närheten

Dela saker med Windows 10 enheter, inklusive både datorer och andra HoloLens 2-enheter. Du kan prova det i Inställningar  ->  **System Delade** upplevelser  ->  **för** att dela filer eller URL:er från en HoloLens till en dator. Mer information finns i Dela saker [med enheter i närheten i Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Den här funktionen kan hanteras via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nya os-diagnostikspårningar

Förutom de tidigare felsökarna i appen Inställningar har en ny felsökare lagts till med det nya inställningsappen för OS-uppdateringar. Gå till **Inställningar**  ->  **&amp; Felsök**  >  **uppdateringssäkerhet**  >  **Windows Update** och välj **Starta**. På så sätt kan du samla in spårningar samtidigt som du återskapar problemet med OS-uppdateringar för att få bättre hjälp med felsökning med DIN IT eller support.

### <a name="delivery-optimization-preview"></a>Leveransoptimering förhandsversion

Med den här HoloLens-uppdateringen Windows Holographic for Business inställningar för leveransoptimering för att minska bandbreddsförbrukningen för nedladdningar från flera HoloLens-enheter. En fullständig beskrivning av den här funktionen tillsammans med den rekommenderade nätverkskonfigurationen finns här: Leveransoptimering [för Windows 10 uppdateringar](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Följande inställningar är aktiverade som en del av hanteringsytan [och kan konfigureras från Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Några varningar om det här förhandsversionserbjudandet:

- HoloLens-stödet är begränsat i den här förhandsversionen till enbart OS-uppdateringar.
- Windows Holographic for Business stöder endast HTTP-nedladdningslägen och nedladdningar från en [Microsoft Ansluten cache slutpunkt](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); peer-to-peer-nedladdningslägen och grupptilldelningar stöds inte för HoloLens-enheter för närvarande.
- HoloLens stöder inte distribution eller leveransoptimering för Windows Server Update Services slutpunkter.
- Felsökning kräver antingen diagnostik på Ansluten cache-servern eller insamling av en spårning på HoloLens på HoloLens via **Inställningsuppdatering**  >  **& säkerhetsfelsökning**  >     >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>IT-administratör – Checklista för uppdatering

Den här checklistan hjälper dig att känna till de nya objekt som funktioner som läggs till i den här funktionsuppdateringen som kan påverka dina aktuella enhetshanteringskonfigurationer eller nya funktioner som du kanske vill börja använda.

#### <a name="updates-to-kiosk-mode"></a>Uppdateringar av helskärmsläge

✔️ nya [**AUMID:er för nya appar i helskärmsläge:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Om du tidigare använde appen Inställningar eller Microsoft Edge i helskärmsläge har vi ersatt dessa appar med nya appar som använder ett annat app-ID. Vi rekommenderar starkt att du läser [Nya AUMID:er för nya appar i helskärmsläge](#use-the-new-settings-and-edge-apps-in-kiosk-modes) nedan. På så sätt kan du antingen fortsätta att ha appen Inställningar i helskärmsläge eller inkludera den nya Microsoft Edge appen. Dessa ändringar kan göras nu och distribueras till alla enheter och möjliggöra en smidigare övergång vid uppdatering.

✔️ inloggning [**automatiskt för kiosker:**](#visitor-auto-logon-for-kiosks) 

Besökare kan nu loggas in automatiskt i en kiosk. Det här beteendet är på som standard men kan hanteras och inaktiveras.

✔️ [**fel vid fel i helskärmsläge med**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Om AAD-gruppmedlemskapet för den inloggade AAD-användaren inte har fastställts används global kioskkonfiguration för Start-menyn (om sådan finns), annars visas en tom startmeny. Även om den tomma startmenyn inte är en konfiguration som du kan konfigurera direkt, kan den här nya hanteringen vara något att informera supportavdelningen om om du använder informationsdator, eftersom detta kan gälla för dina konfigurationer eller om du vill göra nya justeringar i dina tilldelade åtkomstkonfigurationer.

#### <a name="updates-to-page-settings-visibility"></a>Uppdateringar av synlighet för sidinställningar

✔️ nya [**inställnings-URI:er för synlighet för sidinställningar**](#new-settings-uris-for-page-settings-visibility)

Om du för närvarande använder [synlighet för sidinställningar](settings-uri-list.md) kanske du vill göra justeringar i dina befintliga URI:er som du antingen har tillåtit eller blockerat.

#### <a name="updates-for-your-wdac-policy"></a>Uppdateringar för wdac-principen
✔️ Om du tidigare Microsoft Edge via WDAC bör du uppdatera wdac-principen. Granska följande och använd exempelkoden.
#### <a name="enable-new-endpoints-for-edge"></a>Aktivera nya slutpunkter för Edge
✔️ Om du har en infrastruktur som omfattar konfiguration av nätverksslutpunkter som proxy eller brandvägg aktiverar du dessa nya slutpunkter för den nya Microsoft Edge appen.

#### <a name="newly-configurable-items"></a>Nyligen konfigurerbara objekt

✔️ Konfigurera [återställningsdiagnostik:](#configuring-fallback-diagnostics-via-settings-app)Du kan konfigurera om och vem som kan samla in återställningsdiagnostik.

✔️ Dela[saker med enheter i närheten:](#share-things-with-nearby-devices)Du kan inaktivera den nya delningsfunktionen i närheten.

✔️ Konfigurera [principinställningar för den nya Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Granska de nyligen tillgängliga konfigurationerna för Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nytt diagnostikverktyg

✔️[nya os-diagnostikspårningar:](#new-os-diagnostic-traces)Samla in loggar relaterade till OS-uppdateringar.

### <a name="improvements-and-fixes-in-the-update"></a>Förbättringar och korrigeringar i uppdateringen:

- [Offlinediagnostik](hololens-diagnostic-logs.md#offline-diagnostics) innehåller även ytterligare enhetsinformation för serienummer och OS-version.
- Åtgärdar ett problem med distribution av affärsprogram via runtime-etableringspaket.
- Åtgärdar ett problem med rapportering av installationsstatus för affärsprogram.
- Åtgärdar ett problem med beständighet av nya appaket i enhetsåterställningar.
- Åtgärdar ett problem som kan leda till att felaktiga symboler har angetts i Edge för japanska kunder.
- Förbättrar återhämtningen för OS-uppdateringar för förinstallerade appar, till exempel Edge. 
- Åtgärdar en uppdateringstillförlitlighet som påverkar installationen av Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, version 20H2 – maj 2021 Update
- Build-version 19041.1146

Förbättringar och korrigeringar i uppdateringen:
- Den här månatliga kvalitetsuppdateringen innehåller inga betydande ändringar. Vi rekommenderar att du provar vår senaste version, Windows Holographic, version 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, version 1903 – maj 2021 Update
- Build-version 18362.1110

Förbättringar och korrigeringar i uppdateringen:
- Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. **Den här versionen kommer inte längre att ta emot månatliga tjänstuppdateringar**. Vi rekommenderar att du provar vår senaste version, Windows Holographic, version 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, version 20H2 – April 2021 Update
- Build-version 19041.1144

Förbättringar och korrigeringar i uppdateringen:

- Åtgärdar ett problem med rapportering av installationsstatus för affärsprogram.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, version 1903 – April 2021 Update
- Build-version 18362.1108

Förbättringar och korrigeringar i uppdateringen:

- Åtgärdar ett problem där appen Inställningar kraschar när du försöker ändra ett lösenord för ett lokalt konto.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, version 20H2 – Mars 2021 Update
- Build-version 19041.1140

Förbättringar och korrigeringar i uppdateringen:

- Kunder som använder AdvancedPhotoCapture eller LowLagPhotoCapture för att samla in foton med HoloLens 2 kan nu hämta kameraställningen upp till tre sekunder efter att fotot har tagits.
- Korrigering för en minnesläcka i Enhetsportalen Service. Problemet orsakade ökad minnesanvändning av tjänsten som gjorde att andra program inte allokerade minne.
- Åtgärdat ett problem där användare som registrerats i mellanstadierad roll inte kan logga in på enheten.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, version 1903 – Mars 2021 Update
- Build-version 18362.1102

Förbättringar och korrigeringar i uppdateringen:

- Korrigering för en minnesläcka i Enhetsportalen Service orsakade problemet ökad minnesanvändning av tjänsten som gjorde att andra program inte allokerade minne.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, version 20H2 – uppdatering februari 2021
- Build-version 19041.1136

Förbättringar och korrigeringar i uppdateringen:

- Åtgärdar ett problem med inledande enhetskonfiguration och lagring av appuppdateringar.
- Åtgärdar ett problem kring uppgraderingar och flygresor för senare HoloLens-versioner.
- Oanvända förinstallerade certifikat har tagits bort från eSIM-rotarkivet från HoloLens-enheter.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, version 1903 – uppdatering februari 2021
- Build-version 18362.1098

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. Vi rekommenderar att du provar våra senaste versioner för Windows Holographic, version 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, version 20H2 – Uppdatering januari 2021
- Build-version 19041.1134

Förbättringar och korrigeringar i uppdateringen:

- Förbättrad prestanda vid start, återuppta och användarväxling när det finns många användare på enheten.
- Arm32-stöd för [Research Mode har lagts till.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, version 1903 – Uppdatering januari 2021
- Build-version 18362.1091

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. Vi rekommenderar att du provar våra senaste versioner för Windows Holographic, version 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, version 20H2 – Uppdatering december 2020
- Build-version 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Installera appar på HoloLens 2 via Appinstallationsprogram

Vi lägger **till en ny funktion (Appinstallationsprogram)** så att du kan installera program sömlöst på dina HoloLens 2-enheter. Funktionen är på **som standard för ohanterade enheter**. För att förhindra störningar för företag är appinstallationsprogrammet **för närvarande inte tillgängligt för hanterade** enheter.  

En enhet anses vara "hanterad" **om** något av följande stämmer:
- [MDM-registrerad](hololens-enroll-mdm.md)
- Konfigurerad med [etableringspaket](hololens-provisioning.md)
- [Användaridentitet](hololens-identity.md) är Azure AD

Du kan nu installera appar utan att behöva aktivera Utvecklarläge eller använda Enhetsportalen.  Ladda bara ned Appx-paketet (via USB eller via Edge) till din enhet och gå till Appx-paketet i Utforskaren för att uppmanas att starta installationen.  Du kan också [initiera en installation från en webbsida](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Precis som appar som du installerar från Microsoft Store eller separat inläsning med mdm-funktionen för LOB [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) App-distribution [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) måste appar signeras digitalt med signeringsverktyget och det certifikat som används för att signera måste vara betrott av HoloLens-enheten innan appen kan distribueras.

**Programinstallationsanvisningar.**

1.  Kontrollera att enheten inte anses vara hanterad
1.  Kontrollera att HoloLens 2-enheten är påslagen och ansluten till datorn
1.  Kontrollera att du är inloggad på HoloLens 2-enheten
1.  På datorn navigerar du till din anpassade app och kopierar dinapp.appxbundle till dittenhetsnamn\Intern lagring\Nedladdningar.   När du har kopierat filen kan du koppla från enheten
1.  Från hololens 2-enheten öppnar du Start-menyn, Alla appar och startar Utforskaren appen.
1.  Navigera till mappen Hämtade filer. Du kan behöva välja Den här enheten först på den vänstra panelen i appen och sedan gå till Nedladdningar.
1.  Välj filen yourapp.appxbundle.
1.  Den Appinstallationsprogram startas. Välj knappen Installera för att installera din app.
Den installerade appen startas automatiskt när installationen är klar.

Du hittar exempelappar på [Windows Universal Samples GitHub för att](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) testa det här flödet.

Läs om den fullständiga processen [för att installera appar på HoloLens 2 med Appinstallationsprogram](app-deploy-app-installer.md).  

![Installera MRTK-exempel via Appinstallationsprogram](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Förbättringar och korrigeringar i uppdateringen:

- Handspårningen upprätthåller nu spårningen i många nya fall där handen tidigare skulle ha gått förlorad.  I vissa av dessa nya fall fortsätter endast positionen att uppdateras baserat på användarens verkliga hand, medan den andra situationen härleds baserat på en tidigare attityd.  Den här ändringen hjälper till att förbättra spårningskonsekvensen i rörelser som att kastar, kastar, fyller och klappar.  Det hjälper också i fall där handen är nära en yta eller håller ett objekt.  När handskriften härleds anges [värdet per gemensam noggrannhet](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) till "Ungefärlig" i stället för "Hög".
- Åtgärdat ett problem där PIN-återställning för Azure AD-konton visade felet "Något gick fel.
- Användarna bör se mycket mindre OOBE-krascher efter start när de startar ET, Iris från inställningsappen, ny användare eller popup-meddelande.
- Användarna bör ha rätt tidszon som kommer från OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, version 1903 – Uppdatering december 2020
- Build-version 18362.1088

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. Vi rekommenderar att du provar vår senaste Windows Holographic version 20H2 – December 2020 Update och den nya Appinstallationsprogram-funktionen som lagts till i versionen.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, version 20H2
- Build-version 19041.1128

Windows Holographic, version 20H2 är nu tillgänglig och innehåller en mängd nya funktioner för HoloLens 2-användare och IT-proffs. Från automatisk ögonpositionering till Certifikathanteraren i Inställningar, till förbättrade funktioner för helskärmsläge och nya Autopilot-konfigurationsfunktioner. Den här nya uppdateringen gör det möjligt för IT-team att få mer detaljerad kontroll över konfiguration och hantering av HoloLens-enheter och erbjuder användarna ännu mer sömlösa holografiska upplevelser. 

Den senaste versionen är en månatlig uppdatering av version 2004, men den här gången inkluderar vi nya funktioner. Det större versionsnumret förblir detsamma och Windows Update en månatlig version av version 2004 (version 19041). Du kan titta på build-numret på skärmen Inställningar > Om för att bekräfta att du har den senaste tillgängliga versionen 19041.1128+. Om du vill uppdatera till den senaste versionen öppnar du appen Inställningar, går till Uppdatera & Security och trycker på Sök efter uppdateringar. Mer information om hur du hanterar HoloLens-uppdateringar finns på [den här sidan.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Vad är nytt i Windows Holographic, version 20H2  

| Funktion                                              | Beskrivning                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Stöd för automatisk ögonposition](hololens-release-notes.md#auto-eye-position-support) | Beräknar aktivt ögonpositioner utan att användare går igenom kalibrering av ögonspårning.   |
| [Certifikathanteraren](hololens-release-notes.md#certificate-manager)   | Tillåter nya enklare metoder för att installera och ta bort certifikat från appen Inställningar.     |
| [Automatisk start från USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Etableringspaket på USB-enheter uppmanar automatiskt etableringssidan i OOBE.                                                         |
| [Bekräfta automatiskt etableringspaket i OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Etableringspaket tillämpas automatiskt under OOBE från etableringssidan.                                                         |
| [Automatisk etablering utan att använda användargränssnittet](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Kombinera automatisk start av etablering och automatisk bekräftelse tillsammans. |
| [Använda Autopilot med Wi-Fi anslutning](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Använd Autopilot från Wi-Fi utan behov av Ethernet-adapter. |
| [CSP och Autopilot för TenantLockdown](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | När klientregistreringen och principen har tillämpats kan enheten bara registreras i den klientorganisationen när enheten återställs eller flashas igen. |
| [Global tilldelad åtkomst](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Ny konfigurationsmetod för helskärmsläge för flera appar som tillämpar helskärmsläget på systemnivå, vilket gör den tillämplig för alla.                  |
| [Starta en app automatiskt i helskärmsläge för flera appar](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Anger att ett program ska startas automatiskt vid inloggning i helskärmsläge för flera appar.                                                        |
| [Beteendeändringar i helskärmsläge vid hantering av fel](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Fel i helskärmsläge har nu begränsad återställning.                                                                                                |
| [HoloLens-principer](hololens-release-notes.md#hololens-policies)                                    | Nya principer för HoloLens.     |
| [Cachelagra Azure AD-gruppmedlemskap för helskärmsläge offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Med en ny princip kan användare använda gruppmedlemskapscache för att använda helskärmsläge offline under ett visst antal dagar.                                        |
| [Nya enhetsbegränsningsprinciper för HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Enhetshanteringsprinciper aktiverades nyligen för HoloLens 2.                                                                                |
| [Nya energiprinciper för HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nyligen stödda principer för inställningar för tidsgräns för energi.  |
| [Uppdateringsprinciper](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nyligen aktiverade principer som tillåter kontroll över uppdateringar.           |
| [Aktiverad sidsynlighet för inställningar för HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Princip för att välja vilka sidor som visas i appen Inställningar.             |
| [Forskningsläge](hololens-release-notes.md#research-mode) | Använda forskningsläge på HoloLens 2. |
| [Ökad inspelningslängd](hololens-release-notes.md#recording-length-increased) | MRC-inspelningar är inte längre begränsade till 5 minuter. |
| [Förbättringar och korrigeringar i uppdateringen](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Ytterligare korrigeringar i uppdateringen.   |

### <a name="auto-eye-position-support"></a>Stöd för automatisk ögonposition

I HoloLens 2 möjliggör ögonpositioner korrekt hologramplacering, bekväm visningsupplevelse och förbättrad visningskvalitet. Ögonpositioner beräknas internt som en del av ögonspårningsberäkningen. Detta kräver dock att varje användare går igenom kalibrering av ögonspårning, även om upplevelsen kanske inte kräver synindata.

**Auto Eye Position (AEP)** möjliggör dessa scenarier med ett interaktionsfritt sätt att beräkna ögonpositioner för användaren. Automatisk ögonposition börjar fungera i bakgrunden automatiskt från den tidpunkt då användaren sätter på enheten. Om användaren inte har någon tidigare kalibrering av ögonspårning börjar Auto Eye Position tillhandahålla användarens ögonpositioner till visningssystemet efter en bearbetningstid på 20–30 sekunder. Användardata bevaras inte på enheten och därför upprepas den här processen om användaren tar bort och sätter på enheten igen eller om enheten startas om eller aktiveras från strömsparläge.

Det finns några systembeteendeändringar med funktionen För automatisk ögonposition när en ocalibrerad användare placerar på enheten. I det här sammanhanget refererar en ocalibrerad användare till någon som inte har gått igenom processen för ögonspårningsavbildning på enheten tidigare.

| Aktivt program | Tidigare beteende | Beteende från Windows Holographic, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Icke-blickaktiverad app eller Holographic Shell |Dialogrutan med kalibrering av ögonspårning visas. | Ingen uppmaning visas. |
| Blickaktiverad app | Dialogrutan med kalibrering av ögonspårning visas. | Uppmaningen om kalibrering av ögonspårning visas bara när programmet kommer åt blickströmmen. |

Om användaren övergår från ett icke-blickaktiverad program till ett program som använder blickdata visas kalibreringsuppmaning. 

Alla andra systembeteenden liknar när den aktuella användaren inte har en aktiv kalibrering av ögonspårning. Till exempel aktiveras inte gesten Enhandsstart. Det kommer inte att ske några ändringar i Out-Of-Box-Experience för den inledande installationen.

För upplevelser som kräver ögonögondata eller mycket exakt hologrampositionering rekommenderar vi att okalibrerade användare kör ögonspårningsavbildningar. Du kan komma åt den via kalibreringsuppmaningen för ögonspårning eller genom att starta appen Inställningar från Start-menyn och sedan välja **System > Kalibrering > Eye Kalibrering > Run eye kalibrering**.

Den här informationen hittar du senare med annan [kalibreringsinformation.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Certifikathanteraren

- Förbättrad gransknings-, diagnostik- och valideringsverktyg för enhetssäkerhet och efterlevnad via den nya certifikathanteraren. Med den här funktionen kan du distribuera, felsöka och validera dina certifikat i stor skala i kommersiella miljöer.

I Windows Holographic version 20H2 lägger vi till en certifikathanterare i hololens 2-inställningsappen. Gå till **Inställningar > Update & Security > Certificates**. Den här funktionen ger ett enkelt och användarvänligt sätt att visa, installera och ta bort certifikat på enheten. Med den nya Certifikathanteraren har administratörer och användare nu förbättrat gransknings-, diagnos- och valideringsverktygen för att säkerställa att enheterna förblir säkra och kompatibla. 

-   **Granskning:** Möjlighet att verifiera att ett certifikat har distribuerats korrekt eller att bekräfta att det har tagits bort på rätt sätt. 
-   **Diagnos:** När problem uppstår kan det spara tid och hjälpa till med felsökningen att verifiera att rätt certifikat finns på enheten. 
-   **Validering:** Att verifiera att ett certifikat har det avsedda syftet och är funktionellt kan spara mycket tid, särskilt i kommersiella miljöer innan certifikat distribueras i större skala.

Om du snabbt vill hitta ett specifikt certifikat i listan finns det alternativ för att sortera efter namn, arkiv eller förfallodatum. Användare kan också söka efter ett certifikat direkt. Om du vill visa enskilda certifikategenskaper väljer du certifikatet och klickar på **Info**. 

Certifikatinstallationen stöder för närvarande .cer- och .crt-filer. Enhetsägare kan installera certifikat på den lokala datorn och den aktuella användaren.  alla andra användare kan bara installera i aktuell användare. Användare kan bara ta bort certifikat som installerats direkt från inställningsgränssnittet. Om ett certifikat har installerats på annat sätt måste det också tas bort av samma mekanism.

#### <a name="to-install-a-certificate"></a>Så här installerar du ett certifikat: 

1.  Anslut hololens 2 till en dator.
1.  Placera den certifikatfil som du vill installera på en plats på din HoloLens 2.
1.  Gå till **Inställningar app > Uppdatera & Security > certifikat** och välj Installera ett certifikat.
1.  Klicka **på Importera** fil och navigera till den plats där du sparade certifikatet.
1.  Välj **Butiksplats.**
1.  Välj **Certifikatarkiv.**
1.  Klicka på **Installera**.

Certifikatet bör nu installeras på enheten.

#### <a name="to-remove-a-certificate"></a>Så här tar du bort ett certifikat: 
1. Gå till **Inställningar App > Update and Security > Certificates**.
1. Sök efter certifikatet efter namn i sökrutan.
1. Välj certifikatet.
1. Klicka på **Ta bort**
1. Välj **Ja när** du uppmanas att bekräfta.

![Certifikatvisare i appen Inställningar](images/certificate-viewer-device.jpg)

![Bild som visar hur du använder användargränssnittet för certifikat för att installera ett certifikat](images/certificate-device-install.jpg)

Den här informationen finns senare [på en ny Certificate Manager-sida.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatisk start från USB

- Automatiserade processer möjliggör mindre användarinteraktion när USB-enheter med etableringspaket används under OOBE.

Innan den här versionen behövde användare starta etableringsskärmen manuellt under OOBE för att etablera med en knappkombination. Nu kan användarna hoppa över knappkombinationen genom att använda ett etableringspaket på en USB-lagringsenhet. 

1. Anslut USB-enheten med etableringspaketet under OOBE:s första interaktionsbara ögonblick
1. När enheten är redo att etableras öppnas automatiskt prompten med etableringssidan. 

Obs! Om en USB-enhet lämnas ansluten medan enheten startas räknas den befintliga USB-lagringsenheten upp i OOBE och ytterligare enheter som ansluts till.

Mer information om hur du tillämpar etableringspaket under OOBE finns i [HoloLens-etableringsdokumentationen.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Mer information om [etablering av automatisk start från en USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) finns i HoloLens-etableringsdokumentationen.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Bekräfta automatiskt etableringspaket i OOBE
- Automatiserad process som tillåter mindre användarinteraktion. När sidan Etableringspaket visas tillämpas automatiskt alla paket i listan.

När etableringens huvudskärm visas räknar OOBE ned 10 sekunder innan alla etableringspaket börjar tillämpas automatiskt. Användare kan fortfarande [bekräfta eller avbryta inom](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dessa 10 sekunder efter att ha verifierat de paket som de förväntade sig.

### <a name="automatic-provisioning-without-using-ui"></a>Automatisk etablering utan att använda användargränssnittet
- Kombinerade automatiska processer för minskade enhetsinteraktioner för etablering. 

Genom att kombinera automatisk start av etablering från USB-enheter och automatisk bekräftelse av etableringspaket kan en användare etablera HoloLens 2-enheter automatiskt utan att använda enhetens användargränssnitt eller ens använda enheten. Du kan fortsätta att använda samma USB-enhet och etableringspaket för flera enheter. Detta är användbart för att distribuera flera enheter samtidigt i samma område. 

1. [Skapa ett etableringspaket med](hololens-provisioning.md) [Hjälp av Windows Configuration Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopiera paketet till en USB-lagringsenhet.
1. [Flasha din HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) till [19041.1361 eller nyare version.](https://aka.ms/hololens2previewdownload) 
1. När [Advanced Recovery Companion har](https://www.microsoft.com/store/productId/9P74Z35SFRS8) flashade klart kopplar enheten från USB-C-kabeln. 
1. Anslut DIN USB-enhet till enheten.
1. När HoloLens 2-enheten startas i OOBE identifierar den automatiskt etableringspaketet på USB-enheten och startar etableringssidan.
1. Efter 10 sekunder tillämpar enheten automatiskt etableringspaketet. 

Enheten har nu konfigurerats och visar [skärmen Etableringen lyckades.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Använda Autopilot med Wi-Fi anslutning
- Behovet av USB-C-kort för Ethernet minskar maskinvarubehoven genom att autopilot kan fungera på Wi-Fi anslutna enheterna.

Nu under OOBE söker OOBE efter en Autopilot-profil för enheten när du ansluter HoloLens 2 med Wi-Fi. Om en sådan hittas används den för att slutföra resten av AAD-kopplings- och registreringsflödet. Med andra ord är användning av Ethernet till USB-C eller Wi-Fi till USB-C-adapter inte längre ett krav, men de fortsätter att fungera om de tillhandahålls i början av OOBE. Läs mer om [Autopilot för HoloLens 2-enheter.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP för TenantLockdown och Autopilot
- Behåller enheter i organisationens klientorganisation genom att låsa dem till klientorganisationen även genom enhetsåterställning eller omstreck. Med ytterligare säkerhet genom att inte tillåta att konto skapas i via etablering. 

HoloLens 2-enheter stöder nu CSP:n TenantLockdown från och med [Windows Holographic version 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP gör att HoloLens 2 kan kopplas till MDM-registrering med hjälp av Autopilot. När CSP:n RequireNetworkInOOBE-noden för TenantLockdown har angetts till antingen true eller false (inledningsvis inställt) på HoloLens 2 finns det värdet kvar på enheten trots åter flashning, OS-uppdateringar osv. 

När RequireNetworkInOOBE-noden för TenantLockdown har angetts till true på HoloLens 2 väntar OOBE på obestämd tid på att Autopilot-profilen ska laddas ned och tillämpas efter nätverksanslutningen. 

När CPS-noden RequireNetworkInOOBE har angetts till true på HoloLens 2 tillåts inte följande åtgärder i OOBE: 
- Skapa lokal användare med hjälp av körningsetablering 
- Utföra Azure AD-anslutning via körningsetablering 
- Välja vem som äger enheten i OOBE-upplevelsen 

#### <a name="how-to-set-this-using-intune"></a>Hur ställer jag in detta med Intune? 
1. Skapa en anpassad omA URI-enhetskonfigurationsprofil och ange true för Noden RequireNetworkInOOBE enligt nedan.
OMA-URI-värdet ska vara ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Konfigurera låsning av tennant via OMA-URI](images/hololens-tenant-lockdown.png)

1. Skapa en grupp och tilldela enhetskonfigurationsprofilen till den enhetsgruppen. 

1. Gör HoloLens 2-enheten medlem i gruppen som skapades i föregående steg och utlösarsynkronisering.  

Kontrollera att enhetskonfigurationen har tillämpats i Intune-portalen. När den här enhetskonfigurationen tillämpas på HoloLens 2-enheten blir effekterna av TenantLockdown aktiva.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Hur tar jag bort initiering av RequireNetworkInOOBE för TenantLockdown på HoloLens 2 med Intune? 
1. Ta bort HoloLens 2 från enhetsgruppen som enhetskonfigurationen som skapades ovan tilldelades tidigare. 

1. Skapa en anpassad OMA URI-baserad enhetskonfigurationsprofil och ange false för RequireNetworkInOOBE enligt nedan. OMA-URI-värdet ska vara ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av inställning av RequireNetworkInOOBE till falskt via OMA-URI i Intune](images/hololens-tenant-lockdown-false.png)

1. Skapa en grupp och tilldela enhetskonfigurationsprofilen till den enhetsgruppen. 

1. Gör HoloLens 2-enheten medlem i gruppen som skapades i föregående steg och utlösarsynkronisering.

Kontrollera att enhetskonfigurationen har tillämpats i Intune-portalen. När den här enhetskonfigurationen tillämpas på HoloLens 2-enheten kommer effekterna av TenantLockdown att inaktiveras. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Vad skulle hända under OOBE om Autopilot-profilen inte har tilldelats på en HoloLens efter att TenantLockdown har angetts till true? 
OOBE väntar på obestämd tid på att Autopilot-profilen ska laddas ned och följande dialogruta visas. För att du ska kunna ta bort effekterna av TenantLockdown måste enheten först registreras med den ursprungliga klientorganisationen först med hjälp av Autopilot och RequireNetworkInOOBE måste avregistreras enligt beskrivningen i föregående steg innan begränsningar som introducerades av CSP:t TenantLockdown tas bort. 

![Enhetsvy för när principen tillämpas på enheten.](images/hololens-autopilot-lockdown.png)

Den här informationen finns nu tillsammans med resten av Autopilot under [Tenantlockdown CSP och Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Global tilldelad åtkomst – helskärmsläge
- Minskad identitetshantering för helskärmsläge genom att aktivera ny kioskmetod som tillämpar helskärmsläge på systemnivå.

Med den här nya funktionen kan IT-administratörer konfigurera en HoloLens 2-enhet för flera appar i helskärmsläge som gäller på systemnivå, saknar tillhörighet till någon identitet i systemet och gäller för alla som loggar in på enheten. Läs mer om den här nya funktionen i [hololens globala tilldelade åtkomst helskärmsläge.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisk start av ett program i helskärmsläge för flera appar 
- Fokuserad upplevelse med automatisk appstart, vilket ytterligare ökar användargränssnitts- och appval som valts för helskärmslägesupplevelser.

Gäller endast helskärmsläge för flera appar och endast 1 app kan väljas för automatisk start med det markerade attributet nedan i Konfigurationen för tilldelad åtkomst. 

Programmet startas automatiskt när användaren loggar in. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Beteendeändringar i helskärmsläge för hantering av fel
- Säkrare helskärmsläge genom att eliminera tillgängliga appar vid fel i helskärmsläge. 

Tidigare vid fel vid tillämpning av helskärmsläge använde HoloLens för att visa alla program på Start-menyn. I Windows Holographic version 20H2 om det uppstår fel visas inga appar på Start-menyn enligt nedan: 

![Bild av vad helskärmsläge nu ser ut när det misslyckas.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens-principer
- Enhetshanteringsalternativ specifikt för HoloLens som skapats för att hantera enheten. 

Nya principer för mixad verklighet har skapats för HoloLens 2-enheter i Windows Holographic version 20H2. Nya kontrollerbara inställningar är: inställning av ljusstyrka, inställning av volym, inaktivering av ljudinspelning i mixed reality-bilder, inställning när diagnostik kan samlas in och cache för AAD-gruppmedlemskap.  

| Ny HoloLens-princip                                | Beskrivning                                                                               | Kommentarer                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Tillåter att knappar för ljusstyrka inaktiveras, så om du trycker på den ändras inte ljusstyrkan.       | 1 Ja, 0 Nej (standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Tillåter att volymknappar inaktiveras så att volymen inte ändras om du trycker på den.               | 1 Ja, 0 Nej (standard)                                                |
| MixedReality\MicrophoneDisabled                    | Inaktiverar mikrofonen så att ingen ljudinspelning är möjlig på HoloLens 2.                      | 1 Ja, 0 Nej (standard)                                                |
| MixedReality\FallbackDiagnostics                   | Styr beteendet för när diagnostikloggar kan samlas in.                               | 0 Inaktiverad, 1 Aktiverad för enhetsägare, 2 Aktiverad för alla (standard) |
| MixedReality\HeadTrackingMode                      | Reserverad för framtida användning.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Styr hur många dagar azure AD-gruppmedlemskapscache används för helskärmsläge för Azure AD-grupper. | Se nedan.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cachelagra Azure AD-gruppmedlemskap för helskärmsläge offline
- Aktiverade helskärmsläge offline som ska användas med AAD-grupper i upp till 60 dagar.

Den här principen styr hur många dagar azure AD-gruppmedlemskapscache får användas för konfigurationer av tilldelad åtkomst som riktar in sig på Azure AD-grupper för inloggade användare. När det här principvärdet har angetts till ett värde som är större än 0 används cachen annars inte.  

Namn: URI-värdet AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min – 0 dagar  
Max – 60 dagar 

Steg för att använda den här principen korrekt: 
1. Skapa en enhetskonfigurationsprofil för helskärmsläge för Azure AD-grupper och tilldela den till HoloLens-enheter. 
1. Skapa en anpassad OMA URI-baserad enhetskonfiguration som anger det här principvärdet till önskat antal dagar (> 0) och tilldela det till HoloLens-enheter. 
    1. URI-värdet ska anges i textrutan OMA-URI som ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Värdet kan vara mellan min/max tillåtet.
1. Registrera HoloLens-enheter och kontrollera att båda konfigurationerna tillämpas på enheten. 
1. Låt Azure AD-användare 1 logga in när Internet är tillgängligt, när användaren loggar in och Azure AD-gruppmedlemskap har bekräftats, så skapas cacheminnet. 
1. Nu kan Azure AD-användare 1 ta HoloLens offline och använda det för helskärmsläge så länge principvärdet tillåter X antal dagar. 
1. Steg 4 och 5 kan upprepas för andra Azure AD-användare N. Nyckelpunkten här är att alla Azure AD-användare måste logga in på enheten via Internet så att vi minst en gång kan fastställa att de är medlemmar i Den Azure AD-grupp som helskärmskonfigurationen är riktad mot. 
 
> [!NOTE]
> Tills steg 4 utförs för en Azure AD-användare uppstår ett felbeteende som anges i "frånkopplade" miljöer. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nya enhetsbegränsningsprinciper för HoloLens 2
- Gör att användare kan hantera specifika enhetshanteringsprinciper, till exempel blockera tillägg eller borttagning av etableringspaket.

Nyligen aktiverade principer som tillåter fler hanteringsalternativ för HoloLens 2-enheter. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Dessa två nya regler för AllowAddProvisioningPackage och AllowRemoveProvisioningPackage läggs till i våra [vanliga enhetsbegränsningar.](hololens-common-device-restrictions.md)

> [!NOTE]
> När det gäller [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)stöder HoloLens endast konfigurationen ./Vendor/MSFT/RemoteLock/Lock. Konfigurationer som hanterar PIN-kod, till exempel återställning och återställning, stöds inte.

### <a name="new-power-policies-for-hololens-2"></a>Nya energiprinciper för HoloLens 2
- Fler alternativ för när HoloLens för strömsparläge eller lås via energisparprinciper. 

Dessa nyligen tillagda principer gör det möjligt för administratörer att styra energisparbehörigheter, till exempel tidsgräns för inaktivitet. Om du vill läsa mer om varje enskild princip klickar du på länken för principen.

|     Länk till principdokumentation                |     Kommentarer                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Exempelvärde som ska användas i Windows Configuration Designer, dvs.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Exempelvärde som ska användas i Windows Configuration Designer, dvs.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Exempelvärde som ska användas i Windows Configuration Designer, dvs. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Exempelvärde som ska användas i Windows Configuration Designer, dvs. 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Exempelvärde som ska användas i Windows Configuration Designer, dvs.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Exempelvärde som ska användas i Windows Configuration Designer, dvs.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

De här två nya åtgärderna för DisplayOffTimeoutOnBattery och DisplayOffTimeoutPluggedIn läggs till i våra [vanliga enhetsbegränsningar.](hololens-common-device-restrictions.md)

> [!NOTE]
> För konsekvent upplevelse på HoloLens 2 bör du se till att värdena för både DisplayOffTimeoutOnBattery och StandbyTimeoutOnBattery har angetts som samma värde. Samma gäller för DisplayOffTimeoutPluggedIn och StandbyTimeoutPluggedIn. Se [Visa, strömsparläge och viloläge för inaktiva timers](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) för mer information om modernt vänteläge.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nyligen aktiverade uppdateringsprinciper för HoloLens
- Fler alternativ för när uppdateringar installeras eller inaktiverar knappen Pausa uppdateringar för att säkerställa uppdateringar.

Dessa uppdateringsprinciper är nu aktiverade på HoloLens 2-enheter:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Fullständig information om dessa uppdateringsprinciper och hur du använder dem för HoloLens-enheter finns här i [Hantera HoloLens-uppdateringar.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Aktiverad sidsynlighet för inställningar för HoloLens 2
- Ökad ui-kontroll i inställningsappen, vilket kan vara förvirrande för att visa ett begränsat urval av sidor.

Vi har nu aktiverat en princip som gör det möjligt för IT-administratörer att antingen förhindra att specifika sidor i appen Systeminställningar visas eller är tillgängliga, eller att göra det för alla sidor utom de som anges. Om du vill lära dig hur du anpassar den här funktionen fullständigt klickar du på länken nedan.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Om du vill veta vilka sidinställningar du kan anpassa på HoloLens 2 kan du gå till sidan [URI:er för inställningar.](settings-uri-list.md) 
 
![Skärmbild av aktiva timmar som ändras i appen Inställningar](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Forskningsläge
I forskningsläget blir HoloLens 2 ett verktyg för forskning om datorseende. Jämfört med tidigare utgåvor har Research Mode för HoloLens 2 följande fördelar:
-   Förutom sensorer som exponeras i HoloLens (1:a gen) Research Mode tillhandahåller vi nu IMU-sensoråtkomst, inklusive en accelerometer, ett virop och en magnetometer.
-   HoloLens 2 innehåller nya funktioner som kan användas tillsammans med Research Mode. Mer specifikt gäller åtkomst till tydligt handspårnings- och ögonspårnings-API:er som kan leverera en mer omfattande uppsättning experiment.

Forskare har nu möjlighet att aktivera forskningsläget på sina HoloLens-enheter för att få åtkomst till alla dessa externa bildsensorer med extern åtkomst. Forskningsläge för HoloLens 2 ger också åtkomst till accelerometer-, holorrscope- och magnetometeravläsningar. För att skydda användarnas integritet är råa kamerabilder med ögonspårning inte tillgängliga via forskningsläget, men riktningen för ögonbilder är tillgänglig via befintliga API:er.

Mer teknisk [information finns i dokumentationen](https://docs.microsoft.com/windows/mixed-reality/research-mode) för forskningsläge.

### <a name="recording-length-increased"></a>Ökad inspelningslängd
På grund av kundfeedback har vi ökat inspelningslängden [för mixad verklighet.](holographic-photos-and-videos.md) Skärmdumpar av mixad verklighet är inte längre begränsade till 5 minuter som standard, utan beräknar i stället den maximala inspelningslängden baserat på tillgängligt diskutrymme. Enheten beräknar den maximala videoinspelningstiden baserat på tillgängligt diskutrymme upp till 80 % av det totala diskutrymmet.

> [!NOTE]
> HoloLens använder standardlängden för videoinspelning (5 minuter) om något av följande inträffar:
> - Den uppskattade maximala inspelningstiden är mindre än standardvärdet 5 minuter.
> - Det tillgängliga diskutrymmet är mindre än 20 % av det totala diskutrymmet.

Du hittar de fullständiga kraven i vår dokumentation [om holografiska foton och](holographic-photos-and-videos.md#maximum-recording-length) videor. 

### <a name="improvements-and-fixes-in-the-update"></a>Förbättringar och korrigeringar i uppdateringen:
- Fler skärmar i OOBE är nu i mörkt läge.
- Läs mer innehåll bör peka på den senaste sekretesspolicyn online.
- Åtgärdat ett problem där användare inte kunde etablera VPN-profiler via etableringspaket.
- Problem med proxykonfiguration för VPN-anslutning har åtgärdats.
- Principen för att inaktivera uppräkning av USB-funktioner via MDM för NCM för AllowUsbConnection har uppdaterats.
- Åtgärdat ett problem som förhindrade att en HoloLens-enhet visas i Utforskaren via Media Transfer Protocol (MTP) när enheten har ställts in som en [helskärmsenhet med en app.](hololens-kiosk.md) Observera att MTP (och USB-anslutning i allmänhet) fortfarande kan inaktiveras med hjälp av [principen AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Åtgärdat ett problem där ikoner i Start-menyn skalades korrekt i helskärmsläge.
- Ett problem har åtgärdats på grund av HTTP-cachelagring som stör helskärmsläge som är riktat till Azure AD-grupper.
- Ett problem har åtgärdats där användare inte kunde använda knappen Par efter aktivering av Utvecklarläge med etableringspaket, såvida de inte har inaktiverat och återaktiverat utvecklarläget.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, version 1903 – Uppdatering november 2020
- Build-version 18362.1085

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. Vi rekommenderar att du provar vår senaste funktionsversion av Windows Holographic version 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, version 2004 – uppdatering oktober 2020
- Build-version 19041.1124
 
Förbättringar och korrigeringar i uppdateringen:

- En onödig kontroll som orsakade körningssystemets fel har tagits bort.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, version 1903 – uppdatering oktober 2020
- Build-version 18362.1081

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. Vi rekommenderar att du provar våra senaste versioner för Windows Holographic, version 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, version 2004 – uppdatering september 2020
- Build-version 19041.1117

Förbättringar och korrigeringar i uppdateringen:

- Åtgärdar ett problem som hindrade Visual Studio att felsöka ett program när SupportsMultipleInstances="true" finns i appxmanifest.
- Den här versionen innehåller korrigering av NCSI-proxyidentifiering för att åtgärda misslyckad Internetidentifiering via nätverksproxy. NCSI kan använda datorproxy och proxy per profil för identifiering av Internetanslutning. Per användare-proxy kommer att stödjas av NCSI i framtida versioner.
- På de Windows Mixed Reality enheterna är framåtriktad vektor parallell med marken när användarens huvud är i en neutral position som ser framåt. Tidigare versioner av HoloLens 2 justerade dock vektorn så att den är åtsydlig mot visningspanelerna i stället, som lutas nedåt några grader i förhållande till den ideala orienteringen. Nyare versioner av HoloLens 2 har korrigerat detta för att säkerställa semantisk konsekvens mellan formfaktorer.
- Förbättrad robust handspårning som leder till färre spårningsförluster i specifika scenarier.
- Den här versionen innehåller en korrigering för att förbättra ljudtidsstämpelkvaliteten som kan ha bidragit till videoinspelningsproblem.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, version 1903 – Uppdatering september 2020
- Build-version 18362.1079

Förbättringar och korrigeringar i uppdateringen:

- På de Windows Mixed Reality enheterna är framåtriktad vektor parallell med marken när användarens huvud är i en neutral position som ser framåt. Tidigare versioner av HoloLens 2 justerade dock vektorn så att den är åtsydlig mot visningspanelerna i stället, som lutas nedåt några grader i förhållande till den ideala orienteringen. Nyare versioner av HoloLens 2 har korrigerat detta för att säkerställa semantisk konsekvens mellan formfaktorer.
- Förbättrad robust handspårning som leder till färre spårningsförluster i specifika scenarier.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, version 2004 – augusti 2020 Update
- Build-version 19041.1113

Förbättringar och korrigeringar i uppdateringen:

- Inställningsappen kommer inte längre att följa användaren till Iris-registrering eller Kalibrering av ögonspårning.
- En bugg har åtgärdats där tillämpning av ett etableringspaket under OOBE som byter namn på enheten och utför andra åtgärder (till exempel att ansluta till ett nätverk) inte kunde utföra de andra åtgärderna efter omstart av enheten på grund av namnbyte.
- Ändrade färgschemat för de första enhetskonfigurationsflödena för att förbättra den visuella kvaliteten.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, version 1903 – augusti 2020 Update
- Build-version 18362.1074

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar. Vi rekommenderar att du provar våra senaste versioner för Windows Holographic, version 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, version 2004 – uppdatering juli 2020
- Build-version 19041.1109

Förbättringar och korrigeringar i uppdateringen:

- Utvecklare kan nu välja mellan att aktivera eller inaktivera Enhetsportalen kräver en säker anslutning.
- Tillförlitligheten har förbättrats för programstarter efter OS-uppdateringar.
- Standardvärdet för inkorgens ljusstyrka har ändrats till 100 procent.
- Åtgärdat ett problem med HTTPS-vidarebefordran för Windows Enhetsportalen på HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, version 1903 – uppdatering juli 2020
- Build-version 18362.1071

Förbättringar och korrigeringar i uppdateringen:

- Åtgärdat ett problem som kan göra att hologram försvinner i Unity-program när spårningen går förlorade eller återfås.
- Åtgärdat ett problem som gjorde att exklusiva HoloLens-appar kraschade tillbaka till gränssnittet när HoloLens-emulatorn kördes med maskinvaruacceleration på vissa enheter.
- Åtgärdat ett problem som rör HTTPS-vidarebefordran för Windows Enhetsportalen på HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, version 2004 – juni 2020 Update
- Build-version 19041.1106

Förbättringar och korrigeringar i uppdateringen:

- Anpassade MRC-inspelare har nu nya standardvärden för vissa egenskaper om de inte har angetts.
  - På *MRC-videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Avancerad headset))
  - På *MRC-ljudeffekt:*
    - LoopbackGain (det aktuella värdet för "App Audio Gain" på Inspelning av mixad verklighet i Windows Enhetsportalen)
    - MicrophoneGain (det aktuella "Mic Audio Gain"-värdet på Inspelning av mixad verklighet i Windows Enhetsportalen)
- En bugg har åtgärdats för att förbättra ljudkvaliteten i scenarier med mixad verklighetsinspelning. Mer specifikt bör den här korrigeringen eliminera problem med ljud i inspelningen när **Start-menyn** visas.
- Förbättrad hologramstabilitet i inspelade videor.
- Löst ett problem där mixed reality-inspelning inte kunde spela in video efter att enheten lämnats i vänteläge i flera dagar.
- API:et HolographicSpace.UserPresence är vanligtvis inaktiverat för Unity-program. Det här beteendet undviker ett problem som gjorde att vissa appar pausades när visor-programmet vändas, även om inställningen "kör i bakgrunden" var aktiverad. API:et är nu aktiverat för Unity-versionerna 2018.4.18 och senare samt 2019.3.4 och senare.
- När du använder Enhetsportalen via en Wi-Fi-anslutning kan en webbläsare förhindra åtkomst till på grund av ett ogiltigt certifikat. Webbläsaren kan rapportera ett fel, till exempel "ERR_SSL_PROTOCOL_ERROR", även om enhetscertifikatet tidigare var betrott. I det här fallet kan du inte gå vidare till Enhetsportalen, eftersom det inte finns något alternativ för att ignorera säkerhetsvarningar. Den här uppdateringen löste problemet. Om enhetscertifikatet tidigare laddades ned och var betrott på en dator för att ta bort webbläsarens säkerhetsvarningar och SSL-felet uppstår, måste det nya certifikatet laddas ned och vara betrott för att åtgärda webbläsarens säkerhetsvarningar.
- Möjligheten att skapa ett runtime-etableringspaket som kan installera en app med hjälp av MSIX-paket har aktiverats.
- En inställning har lagts **till i Inställningar** System Hologram som gör att användarna automatiskt kan ta bort alla hologram från Mixed Reality hem när enheten stängs  >    >   av.
- Ett problem har åtgärdats som gjorde att HoloLens-appar som ändrade pixelformatet renderade svart i HoloLens-emulatorn.
- En bugg som orsakade en krasch under Iris-inloggningen har åtgärdats.
- Åtgärdat ett problem med upprepade nedladdningar av butiker för redan aktuella appar.
- En bugg har åtgärdats för att förhindra att integrerande appar Microsoft Edge flera gånger.
- Åtgärdat ett problem med lanseringar av appen Photos i de första starterna efter uppdatering från 1903-versionen.
- Förbättrad prestanda och tillförlitlighet.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, version 1903 – juni 2020 Update
- Build-version 18362.1064

Förbättringar och korrigeringar i uppdateringen:

- Anpassade MRC-inspelare har nya standardvärden för vissa egenskaper om de inte har angetts.
  - På *MRC-videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Avancerad headset))
  - På *MRC-ljudeffekt:*
    - LoopbackGain (det aktuella värdet för "App Audio Gain" på Inspelning av mixad verklighet i Windows Enhetsportalen)
    - MicrophoneGain (det aktuella "Mic Audio Gain"-värdet på Inspelning av mixad verklighet i Windows Enhetsportalen)
- API:et HolographicSpace.UserPresence är vanligtvis inaktiverat för Unity-program. Det här beteendet undviker ett problem som gör att vissa appar pausas när visor-programmet vändas, även om inställningen som ska köras i bakgrunden är aktiverad. API:et är nu aktiverat för Unity-versionerna 2018.4.18 och senare samt 2019.3.4 och senare.
- Ett problem har åtgärdats som gjorde att HoloLens-appar som ändrade pixelformatet renderade svart i HoloLens-emulatorn.
- Åtgärdat ett problem med start av photos-appen i de första starterna efter uppdatering från 1903-versionen.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, version 2004  
- Build - 19041.1103

Maj 2020-uppdateringen för HoloLens 2, *Windows Holographic, version 2004* innehåller en mängd spännande nya funktioner, till exempel stöd för Windows Autopilot, mörkt appläge, USB Ethernet-stöd för 5G/LTE-hotspots och mycket mer. Om du vill uppdatera till den senaste versionen öppnar du appen   Inställningar, **går till & Security** och väljer knappen Sök **efter**   uppdateringar. 

|             Funktion                              |          Beskrivning                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Förkonfigurera och konfigurera sömlöst nya enheter för produktion med hjälp av Windows AutoPilot                 |
|       FIDO 2-stöd                             |          Stöd för FIDO2-säkerhetsnycklar för snabb och säker autentisering för delade enheter            |
|       Förbättrad etablering                      |          Tillämpa sömlöst ett etableringspaket från en USB-enhet på hololens                              |
|       Programinstallationsstatus                 |          Kontrollera installationsstatusen i appen Inställningar för appar som har push-lagts till HoloLens 2 via MDM               |
|       Konfigurationstjänstleverantörer (CPS)   |          Nya konfigurationstjänstleverantörer har lagts till för att förbättra funktionerna för administratörskontroll                 |
|       USB 5G/LTE-stöd                       |          Utökad USB Ethernet-funktion ger stöd för 5G/LTE                                    |
|       Mörkt appläge                              |          Mörkt appläge är tillgängligt för appar som stöder både mörka och ljusa lägen, vilket förbättrar visningsupplevelsen        |
|       Röstkommandon                             |          Stöd för ytterligare systemröstkommandon för att styra HoloLens handsfree                           |
|       Förbättringar av handspårning                 |          Handspårningsförbättringar gör knappar och 2D-pekinteraktioner mer exakta                        |
|       Kvalitetsförbättringar och korrigeringar                 |          Olika förbättringar av systemprestanda och tillförlitlighet på hela plattformen                            |

### <a name="support-for-windows-autopilot"></a>Stöd för Windows Autopilot

Windows Autopilot för HoloLens 2 kan enhetsförsäljningskanalen förregistrera HoloLens i din Intune-klientorganisation. När enheter anländer är de redo att själv distribueras som delade enheter under din klientorganisation. Om du vill dra nytta av självdistribution måste enheten ansluta till ett nätverk under den första skärmen i installationen med hjälp av en USB-C-till-Ethernet.

När en användare startar själv distribuerar Autopilot, slutför processen följande steg:

1. Anslut enheten till Azure Active Directory (Azure AD).
1. Använd Azure AD för att registrera enheten i Microsoft Intune (eller en annan MDM-tjänst).
1. Ladda ned enhetsinriktade principer, certifikat och nätverksprofiler.
1. Etablera enheten.
1. Presentera inloggningsskärmen för användaren.

Läs mer i [utvärderingsguiden Windows Autopilot holoLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Kontakta kontohanteraren för att gå med i AutoPilot-förhandsversionen nu. Autopilot-redo enheter börjar levereras snart.*

### <a name="fido2-security-key-support"></a>Stöd för FIDO2-säkerhetsnyckel

Vissa användare delar en HoloLens-enhet med andra i en arbets- eller skolmiljö. Därför är det viktigt att användarna enkelt kan skriva långa användarnamn och lösenord. Med Fast Identity Online (FIDO) kan vem som helst i din organisation (Azure AD-klient) logga in sömlöst på HoloLens utan att ange ett användarnamn eller lösenord.

FIDO2-säkerhetsnycklar är en standardbaserad standardbaserad lösenordsfri autentiseringsmetod som kan komma i vilken form som helst. FIDO är en öppen standard för lösenordsfri autentisering. Det gör att användare och organisationer kan logga in på sina resurser utan användarnamn eller lösenord. I stället använder de en extern säkerhetsnyckel eller en plattformsnyckel som är inbyggd i en enhet.

Kom igång genom att gå [till Aktivera inloggning med lösenordslös säkerhetsnyckel.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Förbättrad MDM-registrering via etableringspaket

Med konfigurationspaket kan du ange HoloLens-konfiguration via en konfigurationsfil i stället för via HoloLens out-of-box-upplevelsen. Tidigare var etableringspaket tvungna att kopieras till HoloLens interna minne. Nu kan de finnas på en USB-enhet så att de är enklare att återanvända på flera HoloLens-enheter och du kan etablera enheter parallellt. Etableringspaket har nu också stöd för ett fält för registrering i enhetshantering, så det finns ingen manuell konfiguration efter etableringen.

Så här testar du det:

1. Ladda ned den senaste versionen av Windows Configuration Designer från Windows Store till din dator.
1. Välj **Etablera HoloLens-enheter**  >  **Etablera HoloLens 2-enheter.**
2. Skapa din konfigurationsprofil. Kopiera sedan alla filer som har skapats till en USB-C-lagringsenhet.
3. Anslut USB-C-enheten till alla nyligen flashade HoloLens-enheter. Tryck sedan på **strömknapparna**  +  **på volymen** för att tillämpa ditt etableringspaket.

### <a name="line-of-business-application-install-status"></a>Installationsstatus för verksamhetsbaserade program

Distribution och hantering av MDM-appar för affärsappar är avgörande för HoloLens. Administratörer och användare måste visa appens installationsstatus för granskning och diagnos. I den här versionen har vi lagt till mer information i **Inställningar**  >  **Åtkomst till** konton arbete eller  >  **skola** Klicka på din  >    >  **kontoinformation.**

### <a name="additional-csps-and-policies"></a>Ytterligare CP:er och principer

En [CSP (Configuration Service Provider) är](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ett gränssnitt för att läsa, ange, ändra eller ta bort konfigurationsinställningar på en enhet. I den här versionen lägger vi till stöd för fler principer för att öka kontrolladministratörerna har över distribuerade HoloLens-enheter. En lista över CSP:er som stöds av HoloLens finns [i NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Nytt i den här versionen:

**Policy CSP** 

Med principkonfigurationstjänstprovidern kan företaget konfigurera principer på Windows-enheter. I den här versionen har vi lagt till nya principer för HoloLens, som anges här. Mer information finns i [Princip-CPS som stöds av HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

Konfigurationstjänstleverantören NetworkQoSPolicy skapar principer för tjänstkvalitet (QoS) för nätverk. En QoS-princip utför en uppsättning åtgärder på nätverkstrafik baserat på en uppsättning matchande villkor. Mer information finns i [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Utökat USB Ethernet-stöd för 5G/LTE-anslutna enheter

Stöd har lagts till för att aktivera vissa mobila enheter förbandsband, till exempel 5G-/LTE-telefoner och Wi-Fi-hotspots, när de är anslutna till HoloLens 2 via USB. Dessa enheter visas nu i **nätverksinställningarna som en** annan Ethernet-anslutning. (Mobila enheter med trådlöst internet som kräver en extern drivrutin stöds inte.) Den här funktionen möjliggör anslutningar med hög bandbredd Wi-Fi inte är tillgänglig och Wi-Fi internet internet inte presterar tillräckligt bra. Mer information om USB-enheter som stöds finns i [Ansluta till Bluetooth- och USB-C-enheter.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Förbättringar av handspårning

Den här versionen innehåller flera handspårningsförbättringar:

- **Pekar på attitydstabilitet:** Systemet kan nu stå emot indexfingret när det ockluderas av slytan. Den här ändringen förbättrar noggrannheten när du trycker på knappar, skriver, bläddrar innehåll med mera! 
- **Minskad oavsiktliga lufttryck:** Vi har förbättrat identifieringen av lufttrycksgesten. Det finns nu färre oavsiktliga aktiveringar i flera vanliga scenarier, till exempel när du släpper händerna på sidorna.
- **Tillförlitlighet för användarväxel:** Systemet är nu snabbare och mer tillförlitligt när det gäller att uppdatera handstorleken när du delar en enhet.
- **Minskad handstöld:** Vi har förbättrat hanteringen av fall där det finns fler än två händer i vy över sensorerna. Om flera personer arbetar nära varandra finns det nu en mycket lägre risk att den spårade handen "hoppar" från användaren till någon annans hand i scenen.
- **Systemtillförlitlighet:** Åtgärdat ett problem som gjorde att handspårningen slutar fungera när enheten är under hög belastning.

### <a name="dark-mode"></a>Mörkt läge

Många Windows-appar stöder nu både mörka och ljusa lägen. HoloLens 2-användare kan välja standardläge för appar som stöder båda. Efter uppdateringen är standardappläget "mörkt", men du kan enkelt ändra den här inställningen: Gå till **Inställningar**  >  **Systemfärger** Välj ditt  >    >  **standardappläge.** 

Dessa "in-box"-appar stöder mörkt läge: 

- Inställningar 
- Microsoft Store 
- E-post 
- Kalender 
- Utforskaren 
- Feedbackhubben 
- OneDrive 
- Foton 
- 3D-visningsprogram 
- Filmer & TV 

![Fönster med mörkt läge](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Röstkommandon i systemet

Nu kan du använda röstkommandon med valfri app på enheten. Mer information finns i Använda [din röst för att använda HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Se även [Språk som stöds för HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### <a name="cortana-updates"></a>Cortana-uppdateringar

Den uppdaterade appen integreras med Microsoft 365 för att hjälpa dig att få mer gjort på dina enheter (för närvarande endast US-English). På HoloLens 2 stöder Cortana inte längre vissa enhetsspecifika kommandon, som att justera volymen eller starta om. Dessa alternativ stöds nu av de nya röstkommandona i systemet. Läs mer om den nya Cortana-appen i vår [blogg](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Kvalitetsförbättringar och korrigeringar

Förbättringar och korrigeringar i uppdateringen:  
- Introducerade ett aktivt kalibreringssystem för visning. Den här funktionen förbättrar stabiliteten och justeringen av hologram. De håller sig nu på plats när du flyttar huvudet från sida till sida.
- Åtgärdat en bugg där Wi-Fi strömmade till HoloLens regelbundet avbröts. Om ett program indikerar att det behöver strömning med låg latens implementerar du korrigeringen genom att anropa [funktionen SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- En enhet som låser sig vid strömning i forskningsläge har åtgärdats.
- Åtgärdat en bugg där i vissa fall rätt användare inte skulle visas på inloggningsskärmen när en session återupptas.
- Åtgärdat ett problem där användare inte kunde exportera MDM-loggar via **Inställningar.**
- Ett problem har åtgärdats där noggrannheten för ögonspårning omedelbart efter installationen av "out-of-box" kunde vara lägre än förväntat.
- Åtgärdat ett problem där undersystemet för ögonspårning inte kunde initieras eller utföra kalibrering under vissa förhållanden.
- Åtgärdade ett problem där ögonavsening skulle uppmanas att använda en redan kalibrerad användare.
- Åtgärdat ett problem där en drivrutin kraschade under ögonförsening.
- Åtgärdat ett problem där upprepade strömknappstryckningar kan orsaka en timeout på 60 sekunder och en shell-krasch.
- Förbättrad stabilitet för djupbuffertar.
- En **dela-knapp** har lagts till i Feedbackhubben så att användarna enklare kan dela feedback.
- Åtgärdat en bugg där RoboRaid wan inte installerades korrekt.

### <a name="known-issues"></a>Kända problem

- Ett problem med systemspråket zh-CN förhindrar röstkommandon från att ta en mixed reality-avbild eller visa enhetens IP-adress.
- Ett problem kräver att du startar Cortana-appen efter att enheten har börjat använda röstaktiveringen "Hej Cortana". Om du har uppdaterat från ett 18362-bygge kan du även se en andra appanel för den tidigare versionen av Cortana-appen som inte längre fungerar i **Starta**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, version 1903 – maj 2020 Update 
- Build-version 18362.1061

Den här månatliga kvalitetsuppdateringen innehåller inga märkbara ändringar eftersom teamet arbetade med Windows Holographic version 2004 May Update, enligt beskrivningen ovan.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, version 1903 – April 2020 Update
- Build-version 18362.1059

**Mörkt läge för appar som stöds** 

Många Windows-appar stöder både mörkt och ljust läge. HoloLens 2-kunder kan nu välja standardläge för appar som stöder båda färgschemana. Baserat på kundfeedback ställer vi in standardappläget på "mörkt", men du kan enkelt ändra den här inställningen när som helst: Gå till **Inställningar > System > Colors** för att hitta "Välj ditt **standardappläge".**

Dessa "in-box"-appar stöder mörkt läge:
- Inställningar
- Microsoft Store
- E-post
- Kalender
- Utforskaren
- Feedbackhubben
- OneDrive
- Foton
- 3D-visningsprogram
- Filmer & TV

**Förbättringar och korrigeringar i uppdateringen:** 
- Säkerställt att gränssnittsöverlägg ingår i mixed reality-bilder.
- Unreal-utvecklare kan nu använda sidan 3D-vy i Enhetsportalen för att testa och felsöka sina program.
- Förbättrad hologramstabilitet i mixed reality-avskiljning när *algoritmen HolographicDepthReprojectionMethod DepthReprojection* används.
- Felet "WinRT IStreamSocketListener API Class not registered" har åtgärdats på 32-bitars ARM-appar.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, version 1903 – mars 2020 Update 
- Build-version 18362.1056

Förbättringar och korrigeringar i uppdateringen:

- Förbättrad hologramstabilitet i mixed reality-avskiljning när *algoritmen HolographicDepthReprojectionMethod AutoPlanar* används.
- Säkerställt att koordinatsystemet som är kopplat till ett djup AVSE-exempel är konsekvent med den offentliga dokumentationen.
- Förbättrad produktivitet för utvecklare genom att göra det möjligt för kunder att klistra in stora mängder text via enhetsportalen.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, version 1903 – uppdatering februari 2020 
- Build-version 18362.1053

Förbättringar och korrigeringar i uppdateringen:

- Tillfälligt inaktiverat Api:et HolographicSpace.UserPresence för Unity-program. Den här ändringen undviker ett problem som gjorde att vissa appar pausades när visor-programmet växlades upp, även om inställningen "kör i bakgrunden" var aktiverad.
- En slumpmässig HUP-krasch som orsakats av handspårning har åtgärdats, där användaren upptäckte att användargränssnittet låser sig och sedan är tillbaka i gränssnittet efter flera sekunder.
- Förbättrad handspårning så att den övre delen av det fingeret är mindre trolig att curl oväntat när du tar hand med ditt indexfingr.
- Förbättrad tillförlitlighet för huvudspårning, rumslig mappning och andra körningar.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, version 1903 – Uppdatering januari 2020 
- Build-version 18362.1043
 
Förbättringar och korrigeringar i uppdateringen:

- Förbättrad stabilitet för exklusiva appar när du arbetar med HoloLens 2-emulatorn.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, version 1903 – Uppdatering december 2019 
- Build-version 18362.1042

Förbättringar och korrigeringar i uppdateringen:

- Introducerade LSR-korrigeringar (last stage reproducering). Förbättrad visuell rendering av hologram för att se mer stabil och klar ut genom att mer exakt redovisa deras djup. Det här symtomet blir mer märkbart efter den här uppdateringen om apparna inte anger hologramdjupet korrekt.
- Stabilitet för exklusiva appar och navigering mellan exklusiva appar har åtgärdats.
- Löst ett problem där mixed reality-inspelning inte kunde spela in video efter att enheten var i vänteläge på flera dagar.
- Förbättrad hologramstabilitet.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, version 1903 – Uppdatering november 2019 
- Build-version 18362.1039

Förbättringar och korrigeringar i uppdateringen:

- Funktionen för Select voice commands **(Välj** röstkommandon) har åtgärdats under den inledande installationen av en-CA och en-AU.
- Förbättrad visuell kvalitet på objekt placerade långt bort i de senaste versionerna av Unity Mixed Reality Toolkit (MRTK).
- Åtgärdat problem med att holografiska program fastnar i pausläge vid start tills Start-menyn öppnades och stängdes.
- Överensstämmelsekorrigeringar och förbättringar för HoloLens 2 och emulatorn i OpenXR Runtime.
