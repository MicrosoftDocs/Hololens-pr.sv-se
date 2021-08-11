---
title: Windows Autopilot för HoloLens 2
description: Lär dig hur du konfigurerar, konfigurerar och felsöker Autopilot på HoloLens 2 enheter.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: 7438b147a31ff38233412a4213a568286fb2e3b8982bc4fd6af3f9dde842fd1a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662369"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot för HoloLens 2

> [!NOTE]
> Autopilot-konfigurationen för HoloLens i Microsoft Endpoint Manager övergår från **offentlig förhandsversion** till **allmän tillgänglighet.** Alla klienter kommer att kunna konfigurera Autopilot i MEM-administrationscentret.

Från och med Windows Holographic version 2004 stöder HoloLens 2 Windows Självdi [distribuerar](/mem/autopilot/self-deploying) Autopilot med Microsoft Intune (MDM från tredje part stöds inte). Administratörer kan konfigurera oobe (out-of-box experience) i Microsoft Endpoint Manager och göra det möjligt för slutanvändarna att förbereda enheter för företagsanvändning med liten eller ingen interaktion. Detta minskar omkostnaderna för lagerhantering, kostnaden för förberedelse av praktiska enheter och supportsamtal från anställda under installationen. Läs mer i [autopilot Windows dokumentationen.](/mem/autopilot/windows-autopilot)

Precis som för Surface-enheter rekommenderar vi att kunderna arbetar med sina Microsoft [Molnlösningsleverantör](https://partner.microsoft.com/cloud-solution-provider) (återförsäljare eller distributör) för att registrera enheter med Autopilot-tjänsten via Partnercenter. Andra metoder för enhetsregistrering beskrivs [](/mem/autopilot/add-devices) i dokumentationen för att lägga till enheter, men genom att utnyttja Microsofts kanalpartners säkerställer du den effektivaste sökvägen från hela till slutet.



När en användare startar själv distribuerar Autopilot utför Autopilot följande steg:

1. Anslut enheten till Azure Active Directory (Azure AD). Observera att Autopilot för HoloLens inte stöder Active Directory-anslutning eller Hybrid Azure AD-anslutning.

1. Använd Azure AD för att registrera enheten i Microsoft Endpoint Manager (eller en annan MDM-tjänst).

1. Ladda ned och tillämpa enhetsinriktade principer, certifikat, nätverksprofiler och program.

1. Etablera enheten.

1. Presentera inloggningsskärmen för användaren.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurera Autopilot för HoloLens 2

Följ stegen nedan för att konfigurera din miljö:

1. [Granska kraven för Windows Autopilot för HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Aktivera automatisk MDM-registrering](#2-enable-automatic-mdm-enrollment)

1. [Registrera enheter i Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Skapa en enhetsgrupp.](#4-create-a-device-group)

1. [Skapa en distributionsprofil.](#5-create-a-deployment-profile)

1. [Kontrollera konfigurationen för sidan för registreringsstatus (ESP).](#6-verify-the-esp-configuration)

1. [Kontrollera profilstatusen för HoloLens enheter.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Granska kraven för att Windows Autopilot för HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Läs följande avsnitt i artikeln om Windows Autopilot-krav:

- [Nätverkskrav](/mem/autopilot/networking-requirements)  
- [Licenskrav](/mem/autopilot/licensing-requirements)  
- [Konfigurationskrav](/mem/autopilot/configuration-requirements)

**Läs avsnittet ["Krav"](/windows/deployment/windows-autopilot/self-deploying#requirements)i artikeln Windows Autopilot Self-Deploying-läge.** Din miljö måste uppfylla dessa krav samt standardkraven för Windows Autopilot. Du behöver inte granska avsnitten "Steg för steg" och "Validering" i artikeln. Procedurerna senare i den här artikeln innehåller motsvarande steg som är specifika för HoloLens.

Information om hur du registrerar enheter och konfigurerar profiler finns i [2. Registrera enheter i Windows Autopilot](#3-register-devices-in-windows-autopilot) och [4. Skapa en distributionsprofil i](#5-create-a-deployment-profile) den här artikeln. Om du vill konfigurera och hantera profiler för själv distribuerande Autopilot-läge kontrollerar du att du [har åtkomst Microsoft Endpoint Manager administrationscentret.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Granska HoloLens operativsystemkrav:

- Enheterna måste finnas [på Windows Holographic version 2004](hololens-release-notes.md#windows-holographic-version-2004) (version 19041.1103) eller senare. Om du vill bekräfta byggversionen på enheten eller flasha om till det senaste operativsystemet använder du ARC [(Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) och våra instruktioner för att [flasha om enheten.](/hololens/hololens-recovery#clean-reflash-the-device) Observera att enheter som levereras fram till slutet av september 2020 Windows Holographic version 1903 förinstallerade. Kontakta återförsäljaren för att se till att Autopilot-redo enheter levereras till dig.

- Windows Holographic, version 2004 stöder endast Autopilot via Ethernet-anslutning. Kontrollera att HoloLens är ansluten till Ethernet med hjälp av en "USB-C till Ethernet"-adapter **innan du slår på** den. Vid enhetsstart krävs ingen användarinteraktion. Om du planerar för en Autopilot-HoloLens många enheter rekommenderar vi att du planerar för adapterinfrastrukturen. Vi rekommenderar inte USB-hubbar eftersom de ofta kräver att ytterligare drivrutiner från tredje part installeras som inte stöds på HoloLens.

- [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (version 19041.1128) eller senare har stöd för Autopilot via Wi-Fi, även om du fortfarande kan använda Ethernet-kort. För enheter som är anslutna via Wi-Fi får användaren endast:

     - Gå igenom den upptrassadebird-scenen
     - Välj språk och språk
     - Köra ögonavsening
     - Upprätta nätverksanslutning

- Windows Holographic, version 20H2 har stöd för [CSP:et Tenantlockdown](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)och Autopilot, som låser en enhet till en klient och ser till att enheten förblir bunden till den klientorganisationen vid oavsiktliga eller avsiktliga återställningar eller rensningar.  

- Kontrollera att enheterna inte redan är medlemmar i Azure AD och inte är registrerade i Intune (eller något annat MDM-system). Autopilot-processen för själv distribution slutför de här stegen. Kontrollera att all enhetsrelaterad information har rensats på sidorna **Enheter** i både Azure AD- och Intune-portalerna. Observera att funktionen "Konvertera alla målenheter till Autopilot" inte stöds på HoloLens för tillfället.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Aktivera automatisk MDM-registrering:

För att Autopilot ska lyckas måste du aktivera automatisk MDM-registrering i ditt Azure Portal. Detta gör att enheten kan registreras utan en användare.

I dialogrutan [Azure Portal](https://portal.azure.com/#home) du **Azure Active Directory**  ->  **Mobility (MDM och MAM)**  ->  **Microsoft Intune**. Konfigurera sedan **MDM-användaromfånget**. Du måste välja **Alla.**

Läs följande korta guide om [hur du aktiverar automatisk mdm-registrering](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) eller [snabbstartsguiden](/mem/intune/enrollment/quickstart-setup-auto-enrollment) för automatisk registrering för att få ännu mer information.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Registrera enheter i Windows Autopilot

Dina enheter måste vara registrerade i Windows Autopilot innan den första installationen. MEM-dokumentation om enhetsregistrering finns i Lägga [till enheter i Autopilot.](/mem/autopilot/add-devices)  

Det finns tre huvudsakliga sätt att registrera HoloLens enheter:

 - **Återförsäljare kan registrera enheter i Partnercenter när du gör en beställning.**

   > [!NOTE]  
   > Det här är den rekommenderade sökvägen för att lägga till enheter i Autopilot-tjänsten. [Läs mer](/mem/autopilot/partner-registration).  

 - **Du kan [skicka en supportbegäran](hololens2-autopilot-registration-support.md) direkt till Microsoft.**
 - **Hämta maskinvaruhashvärdet (även kallat maskinvaru-ID) och registrera enheten manuellt i MEM-administrationscentret.**

#### <a name="obtain-hardware-hash"></a>Hämta maskinvaru-hash
Det finns två sätt att hämta maskinvaruhashvärdet.
1. Du kan [skicka en supportbegäran](hololens2-autopilot-registration-support.md) direkt till Microsoft.
2. Du kan hämta den från enheten. Enheten registrerar sin maskinvaruhash i en CSV-fil under OOBE-processen, eller senare när en enhetsägare startar insamlingen av diagnostikloggen (beskrivs i följande procedur). Vanligtvis är enhetsägaren den första användaren som loggar in på enheten.
     > [!WARNING]
     > I byggen före 20H2 kan du inte samla in maskinvaruhashvärdet för Autopilot via den här metoden om du har gått igenom OOBE och telemetrin har angetts till Obligatorisk. För att samla in din maskinvaruhash via den här metoden anger du telemetrialternativet till Fullständig via Inställningar-appen och väljer Sekretess -> Diagnostics.

    1. Starta enheten HoloLens 2.

    1. På enheten trycker du på **knapparna Ström** **och Volym** ned samtidigt och släpper dem sedan. Enheten samlar in diagnostikloggar och maskinvaruhashvärdet och lagrar dem i en uppsättning .zip filer.

   1. Fullständig information och en instruktionsvideo för hur du förformar detta finns i [offlinediagnostik.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Använd en USB-C-kabel för att ansluta enheten till en dator.

    1. På datorn öppnar du Utforskaren. Öppna **Den här datorn Storage \\ \<*HoloLens device name*> \\ \\ dokument** och leta upp AutopilotDiagnostics.zip filen.  

       > [!NOTE]  
       > Filen .zip kanske inte omedelbart är tillgänglig. Om filen inte är klar ännu kan du se en HoloLensDiagnostics.temp-fil i mappen Dokument. Uppdatera fönstret om du vill uppdatera listan med filer.
    
    1. Extrahera innehållet i AutopilotDiagnostics.zip filen.

    1. I de extraherade filerna letar du upp DEN CSV-fil som har filnamnsprefixet "DeviceHash". Kopiera filen till en enhet på den dator där du kan komma åt den senare.  

       > [!IMPORTANT]  
       > Data i CSV-filen ska använda följande rubrik- och radformat:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrera enheten via MEM

1. I [Microsoft Endpoint Manager administrationscenter](https://endpoint.microsoft.com)väljer **du**  >  **Enheter Windows** Windows  >  **registrering** och sedan Importera  >  **enheter** under **Windows Autopilot Deployment Program**.

1. Under **Lägg Windows Autopilot-enheter** väljer du DeviceHash CSV-filen, **öppnar** och väljer sedan **Importera.**  

   > [!div class="mx-imgBorder"]
   > ![Använd kommandot Importera för att importera maskinvaruhashvärdet.](./images/hololens-ap-hash-import.png)

1. När importen är klar väljer du Enheter **som**  >  **Windows**  >  **Windows**  >  **enhetsregistrering**  >  **Synkronisera**. Processen kan ta några minuter att slutföra, beroende på hur många enheter som synkroniseras. Om du vill se den registrerade enheten väljer du **Uppdatera**.  

   > [!div class="mx-imgBorder"]
   > ![Använd kommandona Synkronisera och Uppdatera för att visa enhetslistan.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Skapa en enhetsgrupp

1. I [Microsoft Endpoint Manager administrationscentret](https://endpoint.microsoft.com)väljer du **Grupper**  >  **Ny grupp.**

1. För **Grupptyp** väljer du **Säkerhet** och anger sedan ett gruppnamn och en beskrivning.

1. För **Medlemskapstyp** väljer du antingen **Tilldelad** eller **Dynamisk enhet.**

1. Gör något av följande:  

   - Om du valde **Tilldelad** **för Medlemskapstyp** i föregående steg väljer du **Medlemmar** och lägger sedan till Autopilot-enheter i gruppen. Autopilot-enheter som ännu inte har registrerats visas med hjälp av enhetens serienummer som enhetsnamn.
   - Om du valde  **Dynamiska enheter** som Medlemskapstyp i föregående steg väljer du Dynamiska **enhetsmedlemmar** och anger sedan kod i **Avancerad** regel som liknar följande:
     - Om du vill skapa en grupp som innehåller alla dina Autopilot-enheter anger du: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intunes grupptaggfält mappar till **OrderID-attributet** på Azure AD-enheter. Om du vill skapa en grupp som innehåller alla dina Autopilot-enheter som har en specifik grupptagg (Azure AD-enhetens OrderID) måste du skriva: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Om du vill skapa en grupp som innehåller alla dina Autopilot-enheter som har ett specifikt inköpsorder-ID skriver du: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Dessa regler är målattribut som är unika för Autopilot-enheter.
1. Välj **Spara** och välj sedan **Skapa.**

### <a name="5-create-a-deployment-profile"></a>5. Skapa en distributionsprofil

1. I [Microsoft Endpoint Manager administrationscentret väljer](https://endpoint.microsoft.com)du **Enheter**  >  **Windows**  >  **Windows registrering** Windows  >  **Autopilot-distributionsprofiler**  >  **Skapa**  >  **profil HoloLens**.
   ![Listrutan Skapa profil innehåller ett HoloLens objekt.](./images/hololens-ap-enrollment-profiles.png)

1. Ange ett profilnamn och en beskrivning och välj sedan **Nästa.**  
   Du bör se en lista som innehåller **HoloLens**. Om det här alternativet inte finns använder du något av [feedbackalternativen](hololens2-autopilot.md#feedback-and-support-for-autopilot) för att kontakta oss.

   > [!div class="mx-imgBorder"]
   > ![Lägga till ett profilnamn och en beskrivning](./images/hololens-ap-profile-name.png)

1. På sidan **Out-of-box experience (OOBE)** är de flesta av inställningarna förkonfigurerade för att effektivisera OOBE för den här utvärderingen. Du kan också konfigurera följande inställningar:  

   - **Språk (region):** Välj språk för OOBE. Vi rekommenderar att du väljer ett språk i listan över språk [som stöds för HoloLens 2](hololens2-language-support.md).
   - **Konfigurera tangentbord automatiskt:** Om du vill kontrollera att tangentbordet matchar det valda språket väljer du **Ja.**
   - **Använd mall för enhetsnamn:** Om du automatiskt  vill ange enhetsnamnet under OOBE väljer du Ja och anger sedan mallfrasen och platshållarna i Ange ett **namn.** Ange till exempel ett prefix och en platshållare för ett slumptal med fyra `%RAND:4%` &mdash; siffror.
     > [!NOTE]  
     > Om du använder en mall för enhetsnamn startar OOBE-processen om enheten ytterligare en gång efter att enhetsnamnet har applicerats och innan den ansluts till Azure AD. Den här omstarten gör att det nya namnet börjar gälla.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurera OOBE-inställningar](./images/hololens-ap-profile-oobe.png)

1. När du har konfigurerat inställningarna väljer du **Nästa.**
1. På sidan **Omfångstaggar** kan du lägga till de omfångstaggar som du vill använda för den här profilen. Mer information om omfångstaggar finns i [Använda RBAC och omfångstaggar för distribuerad IT](/mem/intune/fundamentals/scope-tags.md). När du är klar väljer du **Nästa**.
1. På sidan **Tilldelningar** väljer du **Valda grupper** för **Tilldela till**.
1. Under **VALDA GRUPPER** väljer du + Välj grupper som ska **inkluderas.**
1. I listan **Välj grupper att ta** med väljer du den enhetsgrupp som du skapade för Autopilot-HoloLens enheter och väljer sedan **Nästa.**  
  
   Om du vill undanta grupper väljer du Välj **grupper att exkludera** och väljer de grupper som du vill undanta.

   > [!div class="mx-imgBorder"]
   > ![Tilldela en enhetsgrupp till profilen.](./images/hololens-ap-profile-assign-devicegroup.png)

1. På sidan **Granska + skapa** granskar du inställningarna och väljer sedan Skapa **för** att skapa profilen.  

   > [!div class="mx-imgBorder"]
   > ![Granska + skapa](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. Verifiera ESP-konfigurationen

Sidan för registreringsstatus (ESP) visar status för den fullständiga enhetskonfigurationsprocessen som körs när en MDM-hanterad användare loggar in på en enhet för första gången. Kontrollera att ESP-konfigurationen liknar följande och kontrollera att tilldelningarna är korrekta.  

> [!div class="mx-imgBorder"]
> ![ESP-konfiguration](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Kontrollera profilstatusen för HoloLens enheter

1. I Microsoft Endpoint Manager Administrationscenter väljer du **Enheter**  >  **Windows**  >  **Windows registrera**  >  **enheter**.

1. Kontrollera att HoloLens enheter visas och att deras profilstatus är **Tilldelad.**  

   > [!NOTE]  
   > Det kan ta några minuter för profilen att tilldelas till enheten.  

   > [!div class="mx-imgBorder"]
   > ![Enhets- och profiltilldelningar.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot för HoloLens 2-användarupplevelse

När ovanstående instruktioner har slutförts går HoloLens två användare igenom följande funktioner för att etablera sina HoloLens enheter:  

1. Autopilot-upplevelsen kräver Internetåtkomst. Använd något av följande alternativ för att ge Internetåtkomst:

    - Anslut enheten till ett Wi-Fi i OOBE och sedan identifiera Autopilot-upplevelsen automatiskt. Det här är den enda gången du behöver interagera med OOBE tills Autopilot-upplevelsen har slutförts på egen hand. Observera att som standard väntar HoloLens 2 i 10 sekunder för att identifiera Autopilot när du har upptäckt Internet. Om ingen Autopilot-profil identifieras inom 10 sekunder visas licensavtalet för OOBE. Om du stöter på det här scenariot startar du om enheten så att du kan göra ett nytt försök att identifiera Autopilot. Observera också att OOBE endast kan vänta på Autopilot under obestämd tid om Klientlåsprincip har angetts på enheten.

    - Anslut enheten med Ethernet med hjälp av "USB-C till Ethernet"-kort för kabelansluten Internetanslutning och låt HoloLens 2 fullständig Autopilot-upplevelse automatiskt.

    - Anslut enheten med "USB-C till Wifi"-kort för trådlös Internetanslutning och låt HoloLens 2 slutföra Autopilot-upplevelsen automatiskt.

        > [!IMPORTANT]  
       > Enheter som försöker använda Wi-Fi i OOBE för Autopilot måste finnas [på Windows Holographic version 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > För enheter som använder Ethernet-kort måste du ansluta enheten till nätverket innan OOBE (Out-of-the-Box Experience) startar. Enheten avgör om den etableras som en Autopilot-enhet på den första OOBE-skärmen. Om enheten inte kan ansluta till nätverket, eller om du väljer att inte etablera enheten som en Autopilot-enhet, kan du inte ändra till Autopilot-etablering vid ett senare tillfälle. I stället skulle du behöva starta om den här proceduren för att etablera enheten som en Autopilot-enhet.

1. Enheten bör starta OOBE automatiskt. Interagera inte med OOBE. Luta dig i stället tillbaka och koppla av! Låt HoloLens 2 identifiera nätverksanslutning och tillåt att oobe slutförs automatiskt. Enheten kan starta om under OOBE. OOBE-skärmarna bör likna följande.

   ![OOBE steg 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE steg 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE steg 3](./images/autopilot-device-setup.jpg)

1. I slutet av OOBE kan du logga in på enheten med ditt användarnamn och lösenord.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>CSP för TenantLockdown och Autopilot

HoloLens 2-enheter har stöd för CSP:Windows TenantLockdown från och med Windows Holographic version 20H2. Denna CSP behåller enheter i organisationens klientorganisation genom att låsa dem till den klientorganisationen även genom enhetsåterställning eller omstreck.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP gör att HoloLens 2 kan kopplas till MDM-registrering med hjälp av Autopilot. När CSP:n RequireNetworkInOOBE-noden för TenantLockdown har angetts till värdet true eller false (inledningsvis) på HoloLens 2 finns det värdet kvar på enheten trots åter flashning, OS-uppdateringar osv.

När Noden RequireNetworkInOOBE för TenantLockdown har angetts till true för HoloLens 2 väntar OOBE på obestämd tid på att Autopilot-profilen ska laddas ned och tillämpas efter nätverksanslutningen.

När CPS-noden RequireNetworkInOOBE har angetts till true på HoloLens 2 tillåts inte följande åtgärder i OOBE:

- Skapa lokal användare med hjälp av körningsetablering 
- Utföra Azure AD Join-åtgärder via körningsetablering 
- Välja vem som äger enheten i OOBE-upplevelsen 

#### <a name="how-to-set-this-using-intune"></a>Hur ställer jag in detta med Intune? 
1. Skapa en anpassad omA URI-enhetskonfigurationsprofil och ange true för Noden RequireNetworkInOOBE enligt nedan.
OMA-URI-värdet ska vara ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Konfigurera låsning av tennant via OMA-URI](images/hololens-tenant-lockdown.png)

1. Skapa en grupp och tilldela enhetskonfigurationsprofilen till den enhetsgruppen.

1. Gör HoloLens 2 enhetsmedlem i gruppen som skapades i föregående steg och utlösarsynkronisering.  

Kontrollera att enhetskonfigurationen har tillämpats i Intune-portalen. När den här enhetskonfigurationen har HoloLens 2-enheten blir effekterna av TenantLockdown aktiva.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Hur avindelar jag RequireNetworkInOOBE för TenantLockdown på HoloLens 2 med Intune?

1. Ta bort HoloLens 2 från enhetsgruppen som enhetskonfigurationen som skapades ovan tilldelades tidigare.

1. Skapa en anpassad OMA URI-baserad enhetskonfigurationsprofil och ange false för RequireNetworkInOOBE enligt nedan.
OMA-URI-värdet ska vara ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av inställning av RequireNetworkInOOBE till falskt via OMA-URI i Intune](images/hololens-tenant-lockdown-false.png)

1. Skapa en grupp och tilldela enhetskonfigurationsprofilen till den enhetsgruppen. 

1. Gör HoloLens 2 enhetsmedlem i gruppen som skapades i föregående steg och utlösarsynkronisering.

Kontrollera att enhetskonfigurationen har tillämpats i Intune-portalen. När den här enhetskonfigurationen tillämpas på HoloLens 2-enheten kommer effekterna av TenantLockdown att inaktiveras.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Vad skulle hända under OOBE om Autopilot-profilen inte har tilldelats på en HoloLens när TenantLockdown har angetts till true? 
OOBE väntar på obestämd tid på att Autopilot-profilen ska laddas ned och följande dialogruta visas. För att du ska kunna ta bort effekterna av TenantLockdown måste enheten först registreras med den ursprungliga klientorganisationen först med hjälp av Autopilot och RequireNetworkInOOBE måste avregistreras enligt beskrivningen i föregående steg innan begränsningar som introducerades av CSP:t TenantLockdown tas bort.

![Enhetsvy för när principen tillämpas på enheten.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Kända problem & begränsningar

- Vi undersöker ett problem där enhetskontextbaserad programinstallation som konfigurerats i MEM inte gäller för HoloLens. [Läs mer om enhetskontext och installation av användarkontext.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- När autopilot konfigureras via Wi-Fi kan det finnas en instans där Autopilot-profilen inte laddas ned när Internetanslutningen först upprättas. I det här fallet visas licensavtalet (EULA) och användaren kan välja att fortsätta med en annan konfigurationsupplevelse än Autopilot. Om du vill försöka konfigurera med Autopilot igen sätter du enheten i strömsparläge och startar sedan om eller startar om enheten och låter den försöka igen.
- Funktionen "Konvertera alla målenheter till Autopilot" stöds inte på HoloLens för tillfället.  

### <a name="troubleshooting"></a>Felsökning

Följande artiklar kan vara en användbar resurs om du vill veta mer och felsöka Autopilot-problem, men tänk på att de här artiklarna baseras på Windows 10 Desktop och att inte all information kan gälla för HoloLens:

- [Windows Autopilot – kända problem](/mem/autopilot/known-issues)
- [Felsöka problem med registrering av Windows-enheter i Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – principkonflikter](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Feedback och support för Autopilot

Använd någon av följande metoder för att ge feedback eller rapportera problem:

- Kontakta återförsäljaren eller distributören om du vill ha support för enhetsregistrering.
- För allmänna supportfrågor om Windows Autopilot eller om problem som profiltilldelningar, gruppskapande eller MEM-portalkontroller kan du kontakta [Microsoft Endpoint Manager support](/mem/get-support)  
- Om enheten är registrerad i Autopilot-tjänsten och profilen har tilldelats på MEM-portalen kontaktar du HoloLens [supporten](/hololens/) (se kortet "Support"). Öppna en supportbiljett och inkludera skärmbilder och loggar om det är tillämpligt genom att samla in [diagnostikloggar offline](hololens-diagnostic-logs.md#offline-diagnostics) under oobe (out-of-box-experience).
- Om du vill rapportera ett problem från enheten använder du Feedbackhubben på din HoloLens. I Feedbackhubben väljer du kategorin **Enhet för**  >  **företagshantering.**
- Om du vill ge allmän feedback om Autopilot för HoloLens kan du skicka in den här [undersökningen](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Ta bort Autopilot-enheter

Du kanske inte längre vill använda en enhet för Autopilot eller registrera dina enheter till en annan klientorganisation. Om du vill göra detta läser du[how för att ta bort Autopilot-enheter.](/mem/autopilot/add-devices#delete-autopilot-devices)