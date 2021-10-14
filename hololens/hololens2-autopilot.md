---
title: Windows Autopilot för HoloLens 2
description: Lär dig hur du konfigurerar, konfigurerar och felsöker Autopilot på HoloLens 2 enheter.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: sekerawa
ms.openlocfilehash: 05eb629e05395f04ddb8723d58d41db4161896fa
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964589"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot för HoloLens 2

## <a name="overview"></a>Översikt

Om du vill distribuera i stor skala rekommenderar vi att du kommer igång Windows Autopilot. Det anses vara "låg touch" på så sätt att det avsevärt förenklar HoloLens för både IT-användare och slutanvändare. 

På en hög nivå skapar en IT-administratör vanligtvis företagsklara konfigurationer och registrerar HoloLens 2 enheter på MDM-portaler. När HoloLens 2 enheter startar med oobe (out-of-box experience) och ansluter till Internet laddas företagsklara konfigurationer för registrerade HoloLens 2-enheter ned automatiskt och tillämpas för att göra enheterna företagsklara utan åtgärder från användarens sida.

Mer information finns i Översikt [över Windows Autopilot-| Microsoft Docs](/mem/autopilot/windows-autopilot) artikeln.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Autopilot-scenario som stöds på HoloLens 2

> [!NOTE]
> Autopilot-konfigurationen för HoloLens i Microsoft Endpoint Manager övergår från **offentlig förhandsversion** till **allmän tillgänglighet.** Alla klienter kommer att kunna konfigurera Autopilot i MEM-administrationscentret.

Från och med Windows Holographic version 2004 stöder HoloLens 2 Windows [Självdirebuerande Autopilot-läge](/mem/autopilot/self-deploying) med Microsoft Intune (MDM från tredje part stöds inte). Den här konfigurationen minskar omkostnaderna för inventeringshantering, kostnaden för förberedelse av praktiska enheter och supportsamtal från anställda under installationen. Läs mer i [autopilot Windows dokumentationen.](/mem/autopilot/windows-autopilot)

Precis som för Surface-enheter rekommenderar vi att kunderna arbetar med sina Microsoft [Molnlösningsleverantör](https://partner.microsoft.com/cloud-solution-provider) (återförsäljare eller distributör) för att registrera enheter med Autopilot-tjänsten via Partnercenter.

När en användare startar själv distribuerar Autopilot utför Autopilot följande steg:

1. Anslut enheten till Azure Active Directory (Azure AD). Autopilot för HoloLens stöder inte Active Directory-anslutning eller Hybrid Azure AD-anslutning.

1. Använd Azure AD för att registrera enheten i Microsoft Endpoint Manager (eller en annan MDM-tjänst).

1. Ladda ned och tillämpa enhetsriktade principer, certifikat, nätverksprofiler och program.

1. Presentera inloggningsskärmen för användaren.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurera Autopilot för HoloLens 2

Följ stegen nedan för att konfigurera din miljö:

1. [Granska kraven för Windows Autopilot för HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Aktivera automatisk MDM-registrering](#2-enable-automatic-mdm-enrollment)

1. (Endast för Intune) [Kontrollera att MDM-registreringen inte blockeras för Windows enheter.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Registrera enheter i Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Skapa en enhetsgrupp.](#5-create-a-device-group)

1. [Skapa Autopilot-profilen och tilldela den till enhetsgruppen.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Skapa konfigurationen för sidan för registreringsstatus (ESP) och tilldela den till enhetsgruppen.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Kontrollera profilstatusen för HoloLens enheter.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Granska kraven för Windows Autopilot för HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Läs följande avsnitt i artikeln Windows Autopilot-krav:

- [Nätverkskrav](/mem/autopilot/networking-requirements)  
- [Licenskrav](/mem/autopilot/licensing-requirements)  
- [Konfigurationskrav](/mem/autopilot/configuration-requirements)

**Läs avsnittet ["Krav"](/windows/deployment/windows-autopilot/self-deploying#requirements)i artikeln Windows Autopilot Self-Deploying-läge.** Din miljö måste uppfylla dessa krav och standardkraven Windows Autopilot. Du behöver inte granska avsnitten "Steg för steg" och "Validering" i artikeln. Procedurerna senare i den här artikeln innehåller motsvarande steg som är specifika för HoloLens.

Kontrollera att enheterna inte redan är medlemmar i Azure AD och inte är registrerade i Intune (eller något annat MDM-system). Autopilot-processen för själv distribution slutför de här stegen. Kontrollera att all enhetsrelaterad information har rensats  på sidorna Enheter i både Azure AD- och Intune-portalerna. Funktionen Konvertera alla målenheter till Autopilot stöds inte på HoloLens för tillfället.

#### <a name="review-hololens-os-requirements"></a>Granska HoloLens operativsystemkrav:

Om du vill bekräfta versionsversionen på enheten eller omstrecka till det senaste operativsystemet använder du [ARC (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) och våra instruktioner för [omslag på enheten.](hololens-recovery.md) Enheter som levereras fram till slutet av september 2020 Windows Holographic version 1903 förinstallerade. Kontakta återförsäljaren för att se till att Autopilot-redo enheter levereras till dig.

 Lägsta operativsystemversion | Funktionen stöds | Kommentarer
 ------ | ------ | ------  
 [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (version 19041.1103) eller senare | 1. Själv distribuerar scenariot autopilot på HoloLens 2. | Autopilot-profilnedladdning stöds endast via Ethernet. Kontrollera att HoloLens är ansluten till Ethernet med hjälp av en "USB-C till Ethernet"-adapter **innan du slår på** den.  Om du planerar för en Autopilot-HoloLens många enheter rekommenderar vi att du planerar för adapterinfrastrukturen. Vi rekommenderar inte USB-hubbar eftersom de ofta kräver att drivrutiner från tredje part installeras som inte stöds på HoloLens.
 [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (version 19041.1128) eller senare | 1. Ladda ned Autopilot-profilen via Wi-Fi. <br> 2. [CSP för klientlåsning och Autopilot för att](#tenant-lockdown-csp-and-autopilot) låsa enheter med Autopilot-angiven klientorganisation. | Du kan fortfarande använda Ethernet-kort om du vill. För enheter som är anslutna via Wi-Fi får användaren endast: <ul> <li> Gå igenom den skarigabird-scenen. </li> <li> Välj språk och språk. </li> <li> Kör ögonavsening. </li> <li> Anslut med önskat Wi-Fi-nätverk. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Aktivera automatisk MDM-registrering:

För att Autopilot ska lyckas måste du aktivera automatisk MDM-registrering i din Azure Portal. Detta gör att enheten kan registreras utan en användare.

Läs följande korta guide [om hur du aktiverar automatisk mdm-registrering](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) eller [snabbstartsguiden](/mem/intune/enrollment/quickstart-setup-auto-enrollment) för automatisk registrering för att få ännu mer information om hur du kommer igång.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Se till att MDM-registreringen inte blockeras för Windows enheter.

För att Autopilot ska lyckas måste du se till att dina HoloLens enheter kan registreras. Eftersom HoloLens betraktas som en Windows enhet, behöver det inte finnas några registreringsbegränsningar som kan blockera distributionen. [Granska den här listan över](/mem/intune/enrollment/enrollment-restrictions-set) begränsningar och se till att du kan registrera dina enheter.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registrera enheter i Windows Autopilot

Dina enheter måste vara registrerade i Windows Autopilot innan den första installationen.

Det finns tre huvudsakliga sätt att registrera HoloLens enheter:

 - **Återförsäljare kan registrera enheter i Partnercenter när du gör en beställning.**

   > [!NOTE]  
   > Det här är den rekommenderade sökvägen för att lägga till enheter i Autopilot-tjänsten. [Läs mer](/mem/autopilot/partner-registration).  

 - **Du kan [skicka en supportbegäran](hololens2-autopilot-registration-support.md) direkt till Microsoft.**
 - **Hämta maskinvaruhashvärdet (även kallat maskinvaru-ID) och registrera enheten manuellt i MEM-administrationscentret.**

#### <a name="obtain-hardware-hash"></a>Hämta maskinvaru-hash

Du kan hämta maskinvaruhashvärdet från enheten. Enheten registrerar sin maskinvaruhash i en CSV-fil under OOBE-processen, eller senare när en enhetsägare startar insamlingen av diagnostikloggen (beskrivs i följande procedur). Vanligtvis är enhetsägaren den första användaren som loggar in på enheten.

> [!WARNING]
> Om du har gått igenom OOBE och telemetrin var inställd på Obligatoriskt i byggen före 20H2 kan du inte samla in maskinvaruhashvärdet för Autopilot med den här metoden. För att samla in din maskinvaru-hash via den här metoden anger du telemetrialternativet till Fullständig via Inställningar appen och väljer   >  **Sekretessdiagnostik.**

1. Starta enheten HoloLens 2.

1. På enheten trycker du på **knapparna Ström** **och Volym** ned samtidigt och släpper dem sedan. Enheten samlar in diagnostikloggar och maskinvaruhashvärdet och lagrar dem i en uppsättning .zip filer.

1. Fullständig information och en instruktionsvideo för hur du utför detta finns i [offlinediagnostik.](hololens-diagnostic-logs.md#offline-diagnostics)

1. Använd en USB-C-kabel för att ansluta enheten till en dator.

1. På datorn öppnar du Utforskaren. Öppna <b>Den \\ här</b> < *HoloLens enhetsnamnet* Internt Storage > <b> \\ \\ Dokument</b>och leta upp AutopilotDiagnostics.zip filen.  

   > [!NOTE]  
   > Filen .zip kanske inte omedelbart är tillgänglig. Om filen inte är klar ännu kan du se en HoloLensDiagnostics.temp-fil i mappen Dokument. Uppdatera fönstret om du vill uppdatera listan med filer.

1. Extrahera innehållet i AutopilotDiagnostics.zip filen.

1. I de extraherade filerna letar du upp DEN CSV-fil som har filnamnsprefixet "DeviceHash". Kopiera filen till en enhet på den dator där du kan komma åt den senare.  

   > [!IMPORTANT]  
   > Data i CSV-filen ska använda följande rubrik- och radformat:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrera enheten via MEM

1. I [Microsoft Endpoint Manager administrationscenter](https://endpoint.microsoft.com)väljer du  >  **Enheter Windows** Windows  >  **registrering** och   >   väljer sedan Enhetsimport under Windows Autopilot Deployment Program .

1. Under **Lägg Windows Autopilot-enheter** väljer du DeviceHash CSV-filen, **öppnar** och väljer sedan **Importera.**  

   > [!div class="mx-imgBorder"]
   > ![Använd kommandot Importera för att importera maskinvaruhashvärdet.](./images/hololens-ap-hash-import.png)

1. När importen är klar väljer du Enheter **som**  >  **Windows**  >  **Windows**  >  **enhetsregistrering Synkronisera**  >  . Processen kan ta några minuter att slutföra, beroende på hur många enheter som synkroniseras. Om du vill se den registrerade enheten väljer du **Uppdatera**.  

   > [!div class="mx-imgBorder"]
   > ![Använd kommandona Synkronisera och Uppdatera för att visa enhetslistan.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Skapa en enhetsgrupp

1. I [Microsoft Endpoint Manager administrationscentret](https://endpoint.microsoft.com)väljer du **Grupper**  >  **Ny grupp.**

1. För **Grupptyp** väljer du **Säkerhet** och anger sedan ett gruppnamn och en beskrivning.

1. För **Medlemskapstyp** väljer du antingen **Tilldelad** eller **Dynamisk enhet.**

1. Gör något av följande:  

   - Om du valde **Tilldelad** **för Medlemskapstyp** i föregående steg väljer **du Medlemmar** och lägger sedan till Autopilot-enheter i gruppen. Autopilot-enheter som ännu inte har registrerats visas med hjälp av enhetens serienummer som enhetsnamn.
   - Om du valde  **Dynamiska enheter** som Medlemskapstyp i föregående steg väljer du Dynamiska **enhetsmedlemmar** och anger sedan kod i **Avancerad** regel som liknar följande:
     - Om du vill skapa en grupp som innehåller alla dina Autopilot-enheter anger du: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intunes grupptaggfält mappar till **OrderID-attributet** på Azure AD-enheter. Om du vill skapa en grupp som innehåller alla dina Autopilot-enheter som har en specifik grupptagg (OrderID för Azure AD-enhet) måste du skriva: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Om du vill skapa en grupp som innehåller alla dina Autopilot-enheter som har ett specifikt inköpsorder-ID skriver du: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Dessa regler är målattribut som är unika för Autopilot-enheter.
1. Välj **Spara** och välj sedan **Skapa.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Skapa en Autopilot-profil och tilldela den till enhetsgruppen

1. I [Microsoft Endpoint Manager administrationscentret väljer](https://endpoint.microsoft.com)du **Enheter**  >  **Windows**  >  **Windows registrering** Windows  >  **Autopilot-distributionsprofiler**  >  **Skapa**  >  **profil HoloLens**.
   ![Listrutan Skapa profil innehåller ett HoloLens objekt.](./images/hololens-ap-enrollment-profiles.png)

1. Ange ett profilnamn och en beskrivning och välj **sedan Nästa.**  
   Du bör se en lista som innehåller **HoloLens**. Om det här alternativet inte finns använder du något av [feedbackalternativen](hololens2-autopilot.md#feedback-and-support-for-autopilot) för att kontakta oss.

   > [!div class="mx-imgBorder"]
   > ![Lägg till ett profilnamn och en beskrivning.](./images/hololens-ap-profile-name.png)

1. På sidan **OoBE (Out-of-box experience)** är de flesta inställningar förkonfigurerade för att effektivisera OOBE för den här utvärderingen. Du kan också konfigurera följande inställningar:  

   - **Språk (region):** Välj språk för OOBE. Vi rekommenderar att du väljer ett språk i listan över språk [som stöds för HoloLens 2](hololens2-language-support.md).
   - **Konfigurera tangentbord automatiskt:** Om du vill kontrollera att tangentbordet matchar det valda språket väljer du **Ja.**
   - **Använd mall för enhetsnamn:** Om du vill ange enhetsnamnet automatiskt under OOBE väljer du **Ja** och anger sedan mallfrasen och platshållarna i Ange ett **namn.** Ange till exempel ett prefix och en platshållare för ett slumptal med fyra `%RAND:4%` &mdash; siffror.
     > [!NOTE]  
     > Om du använder en mall för enhetsnamn startar OOBE-processen om enheten en gång efter att enhetsnamnet har applicerats och innan den ansluts till Azure AD. Den här omstarten gör att det nya namnet börjar gälla.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurera OOBE-inställningar.](./images/hololens-ap-profile-oobe.png)

1. När du har konfigurerat inställningarna väljer du **Nästa.**
1. På sidan **Omfångstaggar** kan du lägga till de omfångstaggar som du vill använda för den här profilen. Mer information om omfångstaggar finns i [Använda RBAC och omfångstaggar för distribuerad IT](/mem/intune/fundamentals/scope-tags.md). När du är klar väljer du **Nästa**.
1. På sidan **Tilldelningar** väljer du **Valda grupper** för **Tilldela till**.
1. Under **VALDA GRUPPER** väljer du + Välj grupper som ska **inkluderas.**
1. I listan **Välj grupper att ta** med väljer du den enhetsgrupp som du skapade för Autopilot HoloLens enheterna och väljer sedan **Nästa.**  
  
   Om du vill undanta grupper väljer du Välj **grupper som ska undantas** och väljer de grupper som du vill undanta.

   > [!div class="mx-imgBorder"]
   > ![Tilldela en enhetsgrupp till profilen.](./images/hololens-ap-profile-assign-devicegroup.png)

1. På sidan **Granska + skapa** granskar du inställningarna och väljer sedan Skapa **för** att skapa profilen.  

   > [!div class="mx-imgBorder"]
   > ![Granska + skapa.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Skapa konfiguration av sidan för registreringsstatus (ESP) och tilldela den till enhetsgruppen

Sidan för registreringsstatus (ESP) visar status för den fullständiga enhetskonfigurationsprocessen som körs när en MDM-hanterad användare loggar in på en enhet för första gången. Kontrollera att ESP-konfigurationen liknar följande och kontrollera att tilldelningarna är korrekta.  

> [!div class="mx-imgBorder"]
> ![ESP-konfiguration.](./images/hololens-ap-profile-settings.png)

Mer information om ESP finns i [Konfigurera sidan för registreringsstatus – Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Kontrollera profilstatusen för HoloLens enheter

1. I Microsoft Endpoint Manager Administrationscenter väljer du **Enheter**  >  **Windows**  >  **Windows registrering**  >  **Enheter**.

1. Kontrollera att HoloLens enheterna visas och att deras profilstatus är **Tilldelad**.  

   > [!NOTE]  
   > Det kan ta några minuter för profilen att tilldelas till enheten.  

   > [!div class="mx-imgBorder"]
   > ![Enhets- och profiltilldelningar.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot för HoloLens 2-användarupplevelse

När anvisningarna ovan är klara går HoloLens två användare igenom följande upplevelse för att etablera sina HoloLens enheter:  

1. Autopilot-upplevelsen kräver Internetåtkomst. Använd något av följande alternativ för att ge Internetåtkomst:

    - Anslut enheten till ett Wi-Fi i OOBE och sedan identifiera Autopilot-upplevelsen automatiskt. Det här är den enda gången du behöver interagera med OOBE tills Autopilot-upplevelsen har slutförts på egen hand.

    - Anslut din enhet med Ethernet med "USB-C till Ethernet"-kort för kabelansluten Internetanslutning och låt HoloLens 2 slutföra Autopilot-upplevelsen automatiskt.

    - Anslut enheten med "USB-C till Wi-Fi"-kort för trådlös Internetanslutning och låt HoloLens 2 slutföra Autopilot-upplevelsen automatiskt.

        > [!IMPORTANT]  
       > Enheter som försöker använda Wi-Fi i OOBE för Autopilot måste finnas [på Windows Holographic version 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > För enheter som använder Ethernet-kort måste du ansluta enheten till nätverket innan OOBE (Out-of-the-Box Experience) startar. Enheten avgör om den etableras som en Autopilot-enhet på den första OOBE-skärmen. Om enheten inte kan ansluta till nätverket, eller om du väljer att inte etablera enheten som en Autopilot-enhet, kan du inte ändra till Autopilot-etablering vid ett senare tillfälle. I stället skulle du behöva starta om den här proceduren för att kunna etablera enheten som en Autopilot-enhet.

1. Enheten bör starta OOBE automatiskt. Interagera inte med OOBE.

    > [!IMPORTANT]
    > Interagera inte med OOBE eller tryck på strömknappen för att föra systemet i vänteläge/avstängning medan Autopilot pågår. Detta kan leda till att Autopilot-flödet inte slutförs.

   Låt HoloLens 2 identifiera nätverksanslutningen och tillåta att oobe slutförs automatiskt. Enheten kan starta om under OOBE. OOBE-skärmarna bör likna följande.

   ![OOBE steg 1. ](./images/autopilot-welcome.jpg)
    ![ OOBE steg 2. ](./images/autopilot-step-complete.jpg)
    ![ OOBE steg 3.](./images/autopilot-device-setup.jpg)

1. I slutet av OOBE kan du logga in på enheten med ditt användarnamn och lösenord.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>CSP och Autopilot för klientlåsning

HoloLens 2-enheter stöder CSP för TenantLockdown från och med Windows Holographic, version 20H2. Denna CSP behåller enheter i organisationens klientorganisation genom att låsa dem till den klientorganisationen även genom enhetsåterställning eller omstreck.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP gör att HoloLens 2 kan kopplas till MDM-registrering med autopilot. När CSP:n RequireNetworkInOOBE-noden har angetts till antingen true eller false (inledningsvis inställt) på HoloLens 2 finns det värdet kvar på enheten trots omstreck, OS-uppdateringar osv.

När Noden RequireNetworkInOOBE för TenantLockdown har angetts till true på HoloLens 2 väntar OOBE på obestämd tid på att Autopilot-profilen ska laddas ned och tillämpas efter nätverksanslutningen.

När CPS-noden RequireNetworkInOOBE för TenantLockdown har angetts till true HoloLens 2 tillåts inte följande åtgärder i OOBE:

- Skapa lokal användare med hjälp av körningsetablering
- Utföra Azure AD-anslutning via runtime-etablering
- Välja vem som äger enheten i OOBE-upplevelsen

#### <a name="how-to-set-this-using-intune"></a>Hur ställer jag in detta med Intune?

1. Skapa en anpassad oma-URI-enhetskonfigurationsprofil och ange true för Noden RequireNetworkInOOBE enligt nedan.
OMA-URI-värdet ska vara ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Konfigurera låsning via OMA-URI.](images/hololens-tenant-lockdown.png)

1. Skapa en grupp och tilldela enhetskonfigurationsprofilen till den enhetsgruppen.

1. Gör HoloLens 2 enhetsmedlem i gruppen som skapades i föregående steg och utlösarsynkronisering.  

Kontrollera att enhetskonfigurationen har tillämpats i Intune-portalen. När den här enhetskonfigurationen tillämpas på HoloLens 2-enheten blir effekterna av TenantLockdown aktiva.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Hur avindelar jag RequireNetworkInOOBE för TenantLockdown på HoloLens 2 med Intune?

1. Ta bort HoloLens 2 från enhetsgruppen som enhetskonfigurationen som skapades ovan tilldelades tidigare.

1. Skapa en anpassad OMA URI-baserad enhetskonfigurationsprofil och ange false för RequireNetworkInOOBE enligt nedan.
OMA-URI-värdet ska vara ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av inställningen RequireNetworkInOOBE till falskt via OMA-URI i Intune.](images/hololens-tenant-lockdown-false.png)

1. Skapa en grupp och tilldela enhetskonfigurationsprofilen till den enhetsgruppen.

1. Gör HoloLens 2 enhetsmedlem i gruppen som skapades i föregående steg och utlösarsynkronisering.

Kontrollera att enhetskonfigurationen har tillämpats i Intune-portalen. När den här enhetskonfigurationen tillämpas på HoloLens 2-enheten kommer effekterna av TenantLockdown att inaktiveras.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Vad skulle hända under OOBE om Autopilot-profilen inte har tilldelats på en HoloLens när TenantLockdown har angetts till true?

OOBE väntar på obestämd tid på att Autopilot-profilen ska laddas ned och följande dialogruta visas. För att du ska kunna ta bort effekterna av TenantLockdown måste enheten först registreras med den ursprungliga klientorganisationen först med hjälp av Autopilot och RequireNetworkInOOBE måste avregistreras enligt beskrivningen i föregående steg innan begränsningar som introducerades av CSP:t TenantLockdown tas bort.

![Enhetsvy för när principen tillämpas på enheten.](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Varför såg jag inte Autopilot-upplevelsen trots att Autopilot-profilen har tilldelats i Intune?

Som standard väntar HoloLens 2 i 15 sekunder för att identifiera Autopilot efter att ha upptäckt Internet. Om ingen Autopilot-profil identifieras inom 15 sekunder innebär det att Autopilot inte har identifierats korrekt och du ser sidan EULA.

Starta om enheten och försök igen. Mer information finns i [Kända problem och begränsningar eller](hololens2-autopilot.md#known-issues-and-limitations) [Felsökning.](hololens2-autopilot.md#troubleshooting)

## <a name="known-issues-and-limitations"></a>Kända problem och begränsningar

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Varför visas en 0x80180014 Autopilot?

Det här är ett fel som visas under Autopilot-processen på enheten. Det här problemet gäller endast när HoloLens en enhet har gjort följande:

1. Har redan gått igenom Autopilot minst en gång.
1. Håller nu på att återställas och användas igen för Autopilot.

Autopilot-upplevelsen misslyckas med ett specifikt fel.

![HoloLens Felkod för Autopilot-fel](images/autopilot-0x80180014-failure.jpg)

Vilka åtgärder måste vidtas för att lösa det här felet?

1. Följ stegen i Felsöka [import och registrering av Autopilot-enheter för](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) att ta bort enheten från Intune. (Intune-administratören måste utföra den här uppgiften)
1. När steg 1 är klart startar du om enheten och loggar in.
1. Gå till **Inställningar**  ->  **Uppdatera & Återställning av**&  ->  **och** välj **Kom igång.**
    1. Om det uppstår problem med steg 2 & 3 kan du se alternativen för att återställa enheten i [Återställ/HoloLens](hololens-recovery.md).

AutoPilot bör sedan registreras.

### <a name="troubleshooting"></a>Felsökning

Följande artiklar kan vara en användbar resurs för att lära dig mer och felsöka Autopilot-problem, men de här artiklarna baseras på Windows 10 Desktop och all information kan inte gälla för HoloLens:

- [Windows Autopilot – kända problem](/mem/autopilot/known-issues)
- [Felsöka problem med registrering av Windows-enheter i Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – principkonflikter](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Feedback och support för Autopilot

Använd någon av följande metoder för att ge feedback eller rapportera problem:

- Kontakta återförsäljaren eller distributören om du vill ha support för enhetsregistrering.
- För allmänna supportfrågor om Windows Autopilot eller om problem som profiltilldelningar, gruppskapande eller MEM-portalkontroller kan du [kontakta Microsoft Endpoint Manager support](/mem/get-support)  
- Om enheten är registrerad i Autopilot-tjänsten och profilen har tilldelats på MEM-portalen kontaktar du HoloLens [supporten](/hololens/) (se kortet "Support"). Öppna en supportbiljett och ta med skärmbilder [](hololens-diagnostic-logs.md#offline-diagnostics) och loggar om det är tillämpligt genom att samla in offlinediagnostikloggar under OOBE (Out-of-Box Experience).
- Om du vill rapportera ett problem från enheten använder du Feedbackhubben på din HoloLens. I Feedbackhubben väljer du kategorin **Enhet för**  >  **företagshantering.**
- Om du vill ge allmän feedback om Autopilot för HoloLens kan du skicka in den här [undersökningen](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Ta bort Autopilot-enheter

Du kanske inte längre vill använda en enhet för Autopilot eller registrera dina enheter till en annan klientorganisation. Om du vill göra detta läser du om hur du [tar bort Autopilot-enheter.](/mem/autopilot/add-devices#delete-autopilot-devices)
