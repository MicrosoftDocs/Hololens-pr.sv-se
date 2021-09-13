---
title: Konfigurera HoloLens med hjälp av ett konfigurationspaket (HoloLens)
description: Windows etablering gör det enkelt för IT-administratörer att konfigurera slutanvändarenheten utan avbildning.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033907"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Konfigurera HoloLens med hjälp av ett konfigurationspaket

[Windows etablering gör det](/windows/configuration/provisioning-packages/provisioning-packages) enkelt för IT-administratörer att konfigurera slutanvändarensenheter utan avbildning. Windows Configuration Designer är ett verktyg för att konfigurera avbildningar och körningsinställningar som sedan är inbyggda i konfigurationspaket.

Några av de HoloLens konfigurationer som du kan tillämpa i ett konfigurationspaket är följande:

- Uppgradera till [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Konfigurera ett lokalt konto
- Konfigurera en Wi-Fi anslutning
- Tillämpa certifikat på enheten
- Aktivera utvecklarläge
- Konfigurera helskärmsläge genom att följa [våra detaljerade anvisningar.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

## <a name="provisioning-package-hololens-wizard"></a>Guiden Konfigurera HoloLens paket

Guiden HoloLens hjälper dig att konfigurera följande inställningar i ett konfigurationspaket:

- Uppgradera till Enterprise Edition

    > [!NOTE]
    > Detta bör endast användas för HoloLens första generationens enheter. Inställningar i ett etableringspaket tillämpas endast om etableringspaketet innehåller en uppgraderingslicens för utgåva till Windows Holographic for Business eller om enheten redan har [uppgraderats](hololens1-upgrade-enterprise.md)till Windows Holographic for Business .

- Konfigurera HoloLens första upplevelsen (OOBE)
- Konfigurera Wi-Fi nätverk
- Registrera enheten i Azure Active Directory skapa ett lokalt konto
- Lägga till certifikat
- Aktivera utvecklarläge
- Konfigurera helskärmsläge genom att följa [detaljerade anvisningar.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

> [!WARNING]
> Du måste köra Windows Configuration Designer på Windows 10 konfigurera Azure Active Directory registrering med någon av guiderna.

Etableringspaket kan innehålla hanteringsinstruktioner och principer, anpassade nätverksanslutningar och principer med mera.

> [!TIP]
> Använd skrivbordsguiden för att skapa ett paket med vanliga inställningar och växla sedan till den avancerade redigeraren för att lägga till andra inställningar, appar, principer osv.

## <a name="steps-for-creating-provisioning-packages"></a>Steg för att skapa etableringspaket

1. **Alternativ 1:** [Från Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Detta inkluderar HoloLens 2 funktioner.
2. **Alternativ 2:** [Från Windows Assessment and Deployment Kit (ADK) för Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Om du Windows Configuration Designer från Windows ADK väljer du **Configuration Designer** i dialogrutan Välj de funktioner som **du vill** installera. Det här alternativet inkluderar inte HoloLens 2 funktioner.

> [!NOTE]
> Om du vet att du kommer att använda en offlinedator som behöver åtkomst till Windows Configuration Designer följer du instruktionerna [offline app install(hololens-recovery.md#download-arc-without-using-the-app-store) för Advanced Recovery Companion. Gör Windows Configuration Designer till ditt val. 

### <a name="2-create-the-provisioning-package"></a>2. Skapa etableringspaketet

Använd verktyget Windows Configuration Designer för att skapa ett konfigurationspaket.

1. Öppna Windows Configuration Designer (som standard, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Välj **Etablera HoloLens enheter.**

   ![Startalternativ för ICD.](images/icd-create-options-1703.png)

3. Namnge projektet och välj **Slutför**.

4. Läs anvisningarna på **sidan Komma igång** och välj **Nästa.** Sidorna för skrivbordsetablering går igenom följande steg.
  
> [!IMPORTANT]
> När du skapar ett etableringspaket kan du inkludera känslig information i projektfilerna och i etableringspaketfilen (.ppkg). Även om du har möjlighet att kryptera .ppkg-filen krypteras inte projektfilerna. Du bör lagra projektfilerna på en säker plats och ta bort projektfilerna när de inte längre behövs.

### <a name="configure-settings"></a>Konfigurera inställningar

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Bläddra till och välj företagslicensfilen för att uppgradera HoloLens utgåvan.</br></br>Du kan också växla Ja <strong>eller</strong> <strong>Nej om du</strong> vill dölja delar av den första upplevelsen.</br></br>Om du vill konfigurera enheten utan att behöva ansluta till ett Wi-Fi-nätverk växlar du <strong>Hoppa över Wi-Fi till</strong> <strong>På</strong>.</br></br>Välj en region och tidszon där enheten ska användas. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>I det här avsnittet kan du ange information om Wi-Fi trådlösa nätverk som enheten ska ansluta automatiskt till. Om du vill göra detta väljer du <strong>På,</strong>anger SSID, nätverkstypen<strong>(</strong> Öppen eller <strong>WPA2-Personlig),</strong>och (om <strong>WPA2-Personal</strong>) lösenordet för det trådlösa nätverket.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Du kan registrera enheten i Azure Active Directory eller skapa ett lokalt konto på enheten</br></br>Innan du använder en Windows Configuration Designer för att konfigurera Azure AD-massregistrering konfigurerar <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">du Azure AD-anslutning i din organisation.</a> Det <strong>maximala antalet enheter per användare i</strong> Din Azure AD-klientorganisation avgör hur många gånger masstoken som du får i guiden kan användas. Om du vill registrera enheten i Azure AD väljer du det alternativet och anger ett eget namn för den masstoken som du får med hjälp av guiden. Ange ett förfallodatum för token (högst 30 dagar från det datum då du får token). Välj <strong>Hämta masstoken.</strong> I fönstret Let&#39;get you signed in (Nu ska vi logga <strong>in)</strong> anger du ett konto som har behörighet att ansluta en enhet till Azure AD och sedan lösenordet. Välj <strong>Acceptera</strong> för att ge Windows Configuration Designer de behörigheter som krävs. </br></br>Om du vill skapa ett lokalt konto väljer du det alternativet och anger ett användarnamn och lösenord. </br></br><strong>Viktigt:</strong> <br />(Endast Windows 10 version 1607) Om du skapar ett lokalt konto i etableringspaketet måste du ändra lösenordet med hjälp <strong>av Inställningar-appen</strong> var 42:e dag. Om lösenordet inte ändras under den perioden kan kontot vara utelåst och inte kunna logga in.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Om du vill etablera enheten med ett certifikat klickar du på <strong>Lägg till ett certifikat.</strong> Ange ett namn för certifikatet och bläddra sedan till och välj det certifikat som ska användas.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Växla Ja <strong>eller</strong> Nej <strong>för</strong> att aktivera Utvecklarläge på HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Läs mer om Utvecklarläge.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Ange inte ett lösenord för att skydda ditt etableringspaket. Om etableringspaketet skyddas av ett lösenord misslyckas etableringen HoloLens enheten.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

När du är klar väljer du **Skapa**. Det tar bara några sekunder. När paketet har skapats visas den plats där paketet lagras som en hyperlänk längst ned på sidan.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Skapa ett etableringspaket för HoloLens med hjälp av avancerad etablering

> [!NOTE]
> Ett etableringspaket som du  skapar i Avancerad etablering behöver inte innehålla en uppgraderingslicens för utgåva till Windows Holographic for Business för att tillämpa på ett HoloLens (första generationen). [Mer information finns Windows Holographic for Business för HoloLens (1:a gen).](hololens1-upgrade-enterprise.md)

1. På Windows Configuration Designer väljer du **Avancerad etablering.**
2. I fönstret **Ange projektinformation** anger du ett namn för projektet och platsen för projektet. Du kan också ange en kort beskrivning för att beskriva projektet.

3. Välj **Nästa**.

4. I fönstret **Välj vilka inställningar du vill visa och** konfigurera väljer **Windows 10 Holographic** och väljer sedan **Nästa.**

5. Välj **Slutför**.

6. Expandera **Körningsinställningar och** anpassa paketet med någon av de inställningar som [beskrivs senare i den här artikeln.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Endast Windows 10 version 1607) Om du skapar ett lokalt konto i etableringspaketet måste du ändra lösenordet med hjälp **av Inställningar-appen** var 42:e dag. Om lösenordet inte ändras under den perioden kan kontot vara utelåst och inte kunna logga in. Om användarkontot är låst måste du utföra [en fullständig enhetsåterställning.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Välj **Arkiv**  >  **Spara.**

8. Läs varningen om att projektfiler kan innehålla känslig information och välj **OK.**

    > [!IMPORTANT]
    > När du skapar ett etableringspaket kan du inkludera känslig information i projektfilerna och i etableringspaketfilen (.ppkg). Även om du har möjlighet att kryptera .ppkg-filen krypteras inte projektfilerna. Du bör lagra projektfilerna på en säker plats och ta bort projektfilerna när de inte längre behövs.

9. Välj **Exportera**  >  **etableringspaket**.

10. Ändra **Ägare till** **IT-administratör.** Detta anger prioriteten för det här etableringspaketet högre än etableringspaket som tillämpas på den här enheten från andra källor. Välj **Nästa**.

11. Ange ett värde för **Paketversion**.

    > [!TIP]
    > Du kan göra ändringar i befintliga paket och ändra versionsnumret för att uppdatera tidigare tillämpade paket.

12. I Välj **säkerhetsinformation för etableringspaketet väljer** du **Nästa.**

    > [!WARNING]
    > Om du krypterar etableringspaketet misslyckas etableringen HoloLens enheten.  

13. Välj **Nästa** för att ange den utdataplats där du vill att etableringspaketet ska gå när det har skapats. Som standard Windows Configuration Designer projektmappen som utdataplats.

    Du kan också välja Bläddra **för att** ändra standardplatsen för utdata.

14. Välj **Nästa**.

15. Välj **Skapa** för att börja skapa paketet. Projektinformationen visas på byggsidan och förloppsfältet anger byggstatus.

16. När bygget är klart väljer du **Slutför.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Tillämpa ett konfigurationspaket på HoloLens under installationen

HoloLens 2 enheter på Windows Holographic, version 2004 eller [version 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) eller senare kan använda en USB-enhet för att tillämpa ett etableringspaket. Kopiera bara .ppkg-filen till USB-enhetens rot. Etableringspaket tillämpas endast om de finns i roten på USB-enheten. Flera etableringspaket som finns tillämpas sekventiellt.

HoloLens 2 enheter [på Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) eller senare har nyare funktioner för att effektivisera och förenkla den här processen, vilket gör den automatisk. Läs följande avsnitt:

- [Automatisk start från USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Bekräfta automatiskt etableringspaket i OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatisk etablering utan att använda användargränssnittet](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Använd USB-kabeln för att ansluta enheten till en dator (eller USB-enhet för HoloLens 2 enligt ovan) och starta sedan enheten. Fortsätt inte förbi sidan **First interactable moment** i OOBE.
    - På HoloLens (första generationen) innehåller den här sidan en blå ruta.
    - På HoloLens 2 innehåller den här sidan koltrasten.

2. Tryck kort på och släpp knapparna **Volym ned** **och Ström** samtidigt.

3. HoloLens visas som en enhet i Utforskaren på datorn.

4. I Utforskaren du och släpper etableringspaketet (.ppkg) till enhetens lagringsplats.

5. Tryck kort och släpp knapparna **Volym ned** och **Ström** samtidigt på sidan **Första interagerande ögonblick** i OOBE.

6. Enheten frågar dig om du litar på paketet och vill tillämpa det. Bekräfta att du litar på paketet.

7. Du ser om paketet har tillämpats korrekt eller inte. Om det misslyckades kan du åtgärda paketet och försöka igen. Om det lyckades fortsätter du med OOBE.

> [!NOTE]
> Om enheten köptes före augusti 2016 måste du logga in på enheten med hjälp av en Microsoft-konto, hämta den senaste uppdateringen av operativsystemet och sedan återställa operativsystemet för att tillämpa etableringspaketet.

### <a name="auto-launch-provisioning-from-usb"></a>Automatisk start från USB

- Automatiserade processer möjliggör mindre användarinteraktion när USB-enheter med etableringspaket används under OOBE.

Innan den här versionen behövde användare starta etableringsskärmen manuellt under OOBE för att etablera med en knappkombination. Nu kan användarna hoppa över knappkombinationen genom att använda ett etableringspaket på en USB-lagringsenhet.

1. Anslut USB-enheten med etableringspaketet under OOBE:s första interaktionsbara ögonblick
1. När enheten är redo att etableras öppnas automatiskt prompten med etableringssidan.

Obs! Om en USB-enhet lämnas ansluten medan enheten startas räknas den befintliga USB-lagringsenheten upp i OOBE och ytterligare enheter som ansluts till.

Läs om hur [du tillämpar etableringspaket under OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Bekräfta automatiskt etableringspaket i OOBE
- Automatiserad process som tillåter mindre användarinteraktion. När sidan Etableringspaket visas tillämpas automatiskt alla paket i listan.

När etableringens huvudskärm visas räknar OOBE ned 10 sekunder innan alla etableringspaket börjar tillämpas automatiskt. Användarna kan fortfarande bekräfta eller avbryta inom dessa 10 sekunder efter att ha verifierat de paket som de förväntade sig.

### <a name="automatic-provisioning-without-using-ui"></a>Automatisk etablering utan att använda användargränssnittet
- Kombinerade automatiska processer för minskade enhetsinteraktioner för etablering. 

Genom att kombinera automatisk start av etablering från USB-enheter och automatisk bekräftelse av etableringspaket kan en användare etablera HoloLens 2 enheter automatiskt utan att använda enhetens användargränssnitt eller ens använda enheten. Du kan fortsätta att använda samma USB-enhet och etableringspaket för flera enheter. Detta är användbart för att distribuera flera enheter samtidigt i samma område. 

1. [Skapa ett etableringspaket med](hololens-provisioning.md) hjälp [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Kopiera paketet till en USB-lagringsenhet.
1. [Flasha HoloLens version 2](hololens-insider.md#ffu-download-and-flash-directions) [till 19041.1361 eller nyare version.](https://aka.ms/hololens2previewdownload) 
1. När [Advanced Recovery Companion har](https://www.microsoft.com/store/productId/9P74Z35SFRS8) flashade klart kopplar enheten från USB-C-kabeln. 
1. Anslut DIN USB-enhet till enheten.
1. När enheten HoloLens 2 startar i OOBE identifierar den automatiskt etableringspaketet på USB-enheten och startar etableringssidan.
1. Efter 10 sekunder tillämpar enheten automatiskt etableringspaketet. 

Enheten har nu konfigurerats och skärmen Etableringen lyckades visas.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Tillämpa/ta bort ett konfigurationspaket för att HoloLens efter installationen

> [!NOTE]
> Dessa steg gäller för alla HoloLens 2 HoloLens enheter (första generationen) på Windows Holographic, version 1809 och senare.

Följ dessa steg på datorn:
1. Skapa ett etableringspaket enligt beskrivningen i [Skapa ett etableringspaket för HoloLens med hjälp HoloLens guiden](hololens-provisioning.md).
2. Anslut enheten HoloLens en dator med hjälp av en USB-kabel. HoloLens visas som en enhet i Utforskaren på datorn.
3. Dra och släpp etableringspaketet till mappen Dokument på HoloLens.

På din HoloLens du följande steg:
1. Gå till **Inställningar** > **Konton** > **Åtkomst till arbete eller skola**. 
2. I **Relaterade Inställningar** du Lägg till eller ta bort ett **etableringspaket**.
3. På nästa sida väljer du Lägg **till ett paket** för att starta filväljaren och välja ditt etableringspaket. Om mappen är tom kontrollerar du att du väljer **Den här enheten** och väljer **Dokument.**

När paketet har tillämpats visas det i listan över Installerade **paket**. Om du vill visa paketinformationen eller ta bort paketet från enheten väljer du paketet i listan.

## <a name="what-you-can-configure"></a>Vad du kan konfigurera

Etableringspaket använder konfigurationstjänstleverantörer (CP:er). Om du inte är bekant med CP:er kan du gå [till Introduktion till konfigurationstjänstleverantörer (CPS) för IT-proffs.](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

När Windows i Configuration Designer skapar ett **etableringspaket** för Windows Holographic baseras inställningarna i Tillgängliga anpassningar på CSK:er som stöds i [Windows Holographic](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). I följande tabell beskrivs inställningar som du kanske vill konfigurera för HoloLens.

![Vanliga körningsinställningar för HoloLens.](images/icd-settings.png)

| Inställning | Beskrivning |
| --- | --- |
| **Certifikat** | Distribuera ett certifikat till HoloLens.  |
| **ConnectivityProfiles** | Distribuera en Wi-Fi-profil till HoloLens.   |
| **EditionUpgrade** | [Uppgradera till Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Principer** | Tillåt eller förhindra utvecklarläge på HoloLens. [Principer som stöds av Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Appinstallation via etableringspaket

Appar kan installeras via etableringspaket på HoloLens 2 enheter. På så sätt kan du enkelt använda ett paket som du kan använda för att distribuera dina appar. Läs de fullständiga anvisningarna [för att distribuera appar via Etableringspaket.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (första generationen) har begränsat stöd för installation av appar **(UniversalAppInstall)** med hjälp av ett etableringspaket. HoloLens (första generationens) enheter stöder endast installation av en app via PPKG endast under OOBE och endast med installation av användarkontext.
