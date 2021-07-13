---
title: Introduktion till den nya Microsoft Edge
description: Läs mer om den nya Edge-appen
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, browser
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 41978c626328903cf480a3315d56841f187bc123
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640193"
---
# <a name="introducing-the-new-microsoft-edge"></a>Introduktion till den nya Microsoft Edge

![Animering av äldre Microsoft Edge logotyp till ny Microsoft Edge logotyp](images/new-edge.gif)

Den nya Microsoft Edge [inför Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) projekt med öppen källkod för att skapa bättre kompatibilitet för kunder och mindre fragmentering av webben för webbutvecklare.

Med [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)är den nya Microsoft Edge tillgänglig för HoloLens 2 kunder för första gången! Dela feedback och buggar med vårt team via **funktionen Skicka feedback** i den nya Microsoft Edge eller via [Feedbackhubben](hololens-feedback.md).

> [!IMPORTANT]
> Den här Microsoft Edge ersätter automatiskt äldre Microsoft Edge, som [inte längre stöds](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) i nya versioner.

![Skärmbild Microsoft Edge ny app](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Starta den nya Microsoft Edge

Den nya Microsoft Edge ![ikon Microsoft Edge ny fil](images/new_edge_logo.png) (representeras av en blå och grön virvelikon) fästs på Start-menyn och startas automatiskt när du aktiverar en webblänk.

> [!NOTE]
> När du startar den nya Microsoft Edge på HoloLens 2 importeras dina inställningar och data från äldre Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurera principinställningar för den nya Microsoft Edge

Den nya Microsoft Edge erbjuder IT-administratörer en mycket bredare uppsättning webbläsarprinciper på HoloLens 2 än vad som tidigare var tillgängligt med äldre Microsoft Edge.

Här är några användbara resurser för att lära dig mer om att hantera principinställningar för den nya Microsoft Edge:

- [Konfigurera Microsoft Edge principinställningar med Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge (äldre version) Microsoft Edge principmappning](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome för Microsoft Edge principmappning](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Fullständig [Microsoft Edge Enterprise-dokumentation](/deployedge/)

> [!IMPORTANT]
> På grund av mängden webbläsarprinciper som stöds av den nya Microsoft Edge kan vårt team inte garantera att varje ny princip fungerar på HoloLens 2. Vi har dock testat och bekräftat att det nya Microsoft Edge motsvarar varje äldre Microsoft Edge-princip som tidigare hade stöd för HoloLens 2 fungerar som förväntat. Se [Microsoft Edge (äldre version) att Microsoft Edge för](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) att hitta den nya Microsoft Edge motsvarigheten till varje äldre Microsoft Edge-webbläsarprincip som du använde med HoloLens 2.
>
> Det finns minst två nya Microsoft Edge som vi vet *inte kommer att fungera* med HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Vad du kan förvänta dig av den nya Microsoft Edge på HoloLens 2

Eftersom den nya Microsoft Edge är en ursprunglig Win32-app med ett nytt UWP-kortlager som gör att den kan köras på enheter som endast använder UWP, till exempel HoloLens 2, kanske vissa funktioner inte är omedelbart tillgängliga. Vi kommer att stödja nya scenarier och funktioner under de kommande månaderna, så kontrollera det här utrymmet för uppdaterad information.

**Scenarier och funktioner som förväntas fungera:**
- Första körningen, logga in på profilen och synkronisera
- Webbplatser bör återges och fungera som förväntat
- De flesta webbläsarfunktioner (favoriter, historik osv.) bör fungera som förväntat
- Mörkt läge
- Installera webbappar på enheten
- Installera tillägg (berätta för oss om du använder tillägg som inte fungerar korrekt på HoloLens 2)
- Visa och markera en PDF
- Rumsligt ljud från ett enda webbläsarfönster
- Automatisk och manuell uppdatering av webbläsaren
- Spara en PDF från menyn Skriv ut (med alternativet Spara till PDF)
- WebXR- och 360 Viewer-tillägg
- Innehållsåterställning till rätt fönster när du bläddrar över flera fönster i din miljö

**Scenarier och funktioner förväntas inte fungera:**
- Rumsligt ljud från flera fönster med samtidiga ljudströmmar
- "Se, säg det"
- Skriva ut

**De främsta kända webbläsarproblemen:**
- Förhandsgranskningen av förstoringsglaset i det holografiska tangentbordet har inaktiverats för den nya Microsoft Edge. Vi hoppas kunna återerälda den här funktionen i en kommande uppdatering när förstoringen fungerar som den ska.
- Ljud kan spelas upp från fel webbläsarfönster om du har ett annat webbläsarfönster öppet och aktivt. Du kan komma runt det här problemet genom att stänga det andra aktiva fönstret som inte ska spela upp ljud.
- När du spelar upp ljud från ett webbläsarfönster i läget "Följ mig" fortsätter ljudet att spelas upp om du inaktiverar läget "Följ mig". Du kan komma runt det här problemet genom att stoppa ljuduppspelningen innan du inaktiverar läget "Följ mig" eller genom att stänga fönstret med X-knappen.
- Om du interagerar Microsoft Edge aktiva fönster kan andra 2D-appfönster oväntat inaktiveras. Du kan återaktivera dessa fönster genom att interagera med dem igen.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insiderkanaler

Teamet Microsoft Edge tre förhandsgranskningskanaler som är tillgängliga för Edge Insider-communityn: Beta, Dev och Canary. När du installerar en förhandsgranskningskanal avinstalleras inte den utgivna versionen av Microsoft Edge på din HoloLens 2, och du kan installera fler än en på samma gång. 

Besök startsidan [Microsoft Edge Insider om du](https://www.microsoftedgeinsider.com) vill veta mer om Edge Insider-communityn. Om du vill veta mer om de olika Edge Insider-kanalerna och komma igång kan du gå till [nedladdningssidan för Edge Insider.](https://www.microsoftedgeinsider.com/download)

Det finns några tillgängliga metoder för att installera Microsoft Edge Insider-kanaler till HoloLens 2:

**Direktinstallation på enheten (för närvarande endast tillgängligt för ohanterade enheter)**
  1. På din HoloLens 2 går du till [nedladdningssidan för Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Välj knappen **Ladda ned HoloLens 2** för den Edge Insider-kanal som du vill installera.
  1. Starta den nedladdade MSIX-filen från edge-nedladdningskön eller från enhetens mapp "Nedladdningar" (med hjälp av Utforskaren).
  1. [Appinstallationsprogrammet](app-deploy-app-installer.md) startas.
  1. Välj **knappen** Installera.
  1. Efter en lyckad installation hittar du Microsoft Edge Beta, Dev eller Canary som en separat **post i listan Alla appar** över Start-menyn.

**Installera via dator med Windows Enhetsportalen [(utvecklarläge måste](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) vara aktiverat på HoloLens 2)**
  1. Gå till nedladdningssidan för [Edge Insider på datorn.](https://www.microsoftedgeinsider.com/download)
  1. Välj knappen **med listrilen** bredvid knappen "Download for Windows 10" (Ladda ned för Windows 10) för den Edge Insider-kanal som du vill installera.
  1. Välj **HoloLens 2** i den nedrullningsna menyn.
  1. Spara .msix-filen i mappen "Nedladdningar" på datorn (eller en annan mapp som du enkelt kan hitta).
  1. Använd [Windows Enhetsportalen](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) på datorn för att installera den nedladdade MSIX-filen på HoloLens 2.
  1. Efter en lyckad installation hittar du Microsoft Edge Beta, Dev eller Canary som en separat **post i listan Alla appar** över Start-menyn.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Använda WDAC för att blockera nya Microsoft Edge

För att IT-administratörer ska kunna uppdatera [sin WDAC-princip](windows-defender-application-control-wdac.md) för att blockera den nya Microsoft Edge-appen måste du lägga till följande i principen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Hantera slutpunkter för den nya Microsoft Edge

Vissa miljöer kan ha nätverksbegränsningar att ta hänsyn till. Aktivera dessa Microsoft-slutpunkter för att säkerställa en smidig upplevelse med den [nya Gränsen.](/deployedge/microsoft-edge-security-endpoints)

Läs mer om de tillgängliga [slutpunkterna för HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Installera webbappar
 > [!Note]
> Från och [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)kommer Office webbappen inte längre att vara förinstallerad. 

Du kan använda den nya Edge för att installera webbappar tillsammans Microsoft Store appar. Du kan till exempel installera Microsoft Office webbapp för att visa och redigera filer som finns på SharePoint eller OneDrive. Om du vill Office webbappen går du till och väljer knappen App Available (Tillgänglig app) https://www.office.com **eller Install Office** (Installera Office) i adressfältet.  Bekräfta **genom att** välja Installera.
> [!IMPORTANT]
> Office webbappens funktioner är bara tillgängliga när HoloLens 2 har en aktiv Internetanslutning.

## <a name="webxr-and-360-viewer"></a>WebXR och 360 Viewer


Den nya Microsoft Edge har stöd för WebXR, som är den nya standarden för att skapa integrerande webbupplevelser (ersätt WebVR). Många integrerande webbupplevelser har utformats med VR i åtanke (de ersätter ditt synfält med en virtuell miljö), men dessa upplevelser stöds också av HoloLens 2. WebXR-standarden möjliggör även fördjupande webbupplevelser med förhöjd och mixad verklighet som använder din fysiska miljö. När utvecklare ägnar mer tid åt WebXR förväntar vi oss att nya förhöjda och integrerande upplevelser med mixad verklighet kommer att tas emot för HoloLens 2 kunder att testa!

Tillägget 360 Viewer bygger på WebXR och installeras automatiskt tillsammans med den nya Microsoft Edge på HoloLens 2. Det här webbtillägget ger dig möjlighet att fördjupa dig i 360-gradiga videor. YouTube erbjuder det största urvalet av 360 videor, så vi rekommenderar att du börjar där.

### <a name="how-to-use-webxr"></a>Så här använder du WebXR

1. Gå till en webbplats med WebXR-stöd.
1. Välj knappen **Enter VR** (Ange VR) på webbplatsen. Platsen och den visuella representationen av den här knappen kan variera beroende på webbplats, men den kan se ut ungefär så här:

    ![Ange exempel på VR-knapp](images/75px-enter-vr.png)

1. Första gången du försöker starta en WebXR-upplevelse på en specifik domän ber webbläsaren om medgivande att ange en integrerande vy och väljer **Tillåt**.
1. Använd [HoloLens 2 gester](hololens2-basic-usage.md#the-hand-tracking-frame) för att manipulera upplevelsen.
1. Om upplevelsen inte har en exit-knapp **använder du** gesten [Start för](hololens2-basic-usage.md#start-gesture) att gå tillbaka hem.

**Rekommenderade WebXR-exempel**
- 360 Viewer (se nästa avsnitt)
- [XR-apparat](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Använda 360 Viewer

1. Gå till en 360 graders video på YouTube.
1. I videoramen väljer du headsetknappen för mixad verklighet:

    ![Knapp för att aktivera 360 Viewer](images/enter-360-viewer.jpg)

1. Första gången du försöker starta 360 Viewer på en specifik domän ber webbläsaren om medgivande för att komma in i en integrerande vy. Välj **Tillåt**.
1. [Tryck i luften](hololens2-basic-usage.md#select-using-air-tap) för att öppna uppspelningskontrollerna. Använd [handbilder och](hololens2-basic-usage.md#select-using-air-tap) tryck i luften för att spela upp/pausa, hoppa framåt/bakåt, aktivera/inaktivera undertexter eller stoppa upplevelsen (som avslutar den integrerande vyn). Uppspelningskontrollerna försvinner efter några sekunders inaktivitet.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Kända problem med WebXR och 360 Viewer
- Beroende på komplexiteten i WebXR-upplevelsen kan bildrutefrekvensen släppas eller sjunker.
- Stöd för tydligt handstöd i WebXR är inte aktiverat som standard. Utvecklare kan aktivera support via edge://flags genom att aktivera "WebXR Hand Input".
- 360 videor från andra webbplatser än YouTube kanske inte fungerar som förväntat.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Ge feedback om WebXR och 360 Viewer

Dela feedback och buggar med vårt team via **funktionen Skicka feedback** i det nya Microsoft Edge.
