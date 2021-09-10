---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – Konfigurera
description: Lär dig hur du ställer in konfigurationer för att distribuera HoloLens 2 enheter över ett företagsanslutet nätverk med Dynamics 365-guider.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Enhetshantering
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428770"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurera – Företagsansluten guide

## <a name="azure-users-and-groups"></a>Azure-användare och -grupper

Azure och Intune med det tillägget använder användare och grupper för att tilldela konfigurationer och licenser. För att verifiera det här distributionsflödet och kontrollera att du kan skapa och använda en guide behöver&#39;ett användarkonto.

Vi kan skapa en enskild användargrupp specifikt för att tilldela licenser.

Om du inte&#39;har åtkomst till två Azure AD-konton i en användargrupp kan du använda; här är snabbstartsguiderna för:

- [Så här skapar du en användare](/mem/intune/fundamentals/quickstart-create-user)
- [Så här skapar du en grupp](/mem/intune/fundamentals/quickstart-create-group)
- [Lägg till användare i en grupp](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Lägg till skapade användare för att skapa grupp
- [Konfigurera Azure AD så att en användargrupp kan ansluta till enheter](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Se till att den nya användargruppen har behörighet att registrera enheter i Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatisk registrering på HoloLens 2

För att få en smidig och smidig upplevelse är det enkelt att konfigurera Azure Active Directory Join (AADJ) och automatisk registrering i Intune för HoloLens 2 enheter. Detta gör att användarna kan ange sina autentiseringsuppgifter för organisationens inloggningsuppgifter under OOBE och automatiskt registrera sig med Azure AD och registrera enheten i MDM.

Med hjälp [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kan vi välja tjänster och navigera på några sidor tills vi kan välja Hämta en Premium utvärderingsversion. Du kanske märker att det Azure Active Directory Premium 1 och 2 – för automatisk registrering räcker det med P1. Vi kan välja Intune och välja användaromfånget för automatisk registrering och välja den grupp som skapades tidigare.

Fullständig information och anvisningar finns i guiden om [hur du aktiverar automatisk registrering för Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Anslutning Wi-Fi företag

Företagsanslutningar Wi-Fi kräver ofta certifikatbaserad autentisering för kunder som använder HoloLens 2. Du måste distribuera sådana certifikat med hjälp av en Simple Certificate Enrollment Protocol-certifikatinfrastruktur (SCEP) eller PKCS-certifikatinfrastruktur (Public Key Cryptography Standard) som är integrerad med din MDM-lösning. Att använda Intune för Wi-Fi, certifikat och proxyinställningar skapar en sömlös upplevelse för slutanvändarna.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Distribuera certifikat och Wi-Fi profiler

Följ dessa steg om du vill Microsoft Endpoint Manager certifikat och profiler via en Microsoft Endpoint Manager:

1. Skapa en profil för varje rotcertifikat och mellanliggande certifikat (se [Skapa betrodda certifikatprofiler).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Var och en av dessa profiler måste ha en beskrivning som innehåller ett förfallodatum i formatet DD/MM/YYYYY.

    > [!CAUTION]
    > **Certifikatprofiler utan förfallodatum distribueras inte**.

2. Skapa en profil för varje SCEP- eller PKCS-certifikat (se Skapa en SCEP-certifikatprofil eller Skapa en [PKCS-certifikatprofil)](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Var och en av dessa profiler måste ha en beskrivning som innehåller ett förfallodatum i formatet DD/MM/ÅYYY.

    > [!CAUTION]
    > **Certifikatprofiler utan förfallodatum distribueras inte.**

    > [!Note]
    > Eftersom HoloLens 2 anses vara en delad enhet, det vill säga flera användare per enhet, rekommenderar vi att du distribuerar enhetscertifikat i stället för användarcertifikat för Wi-Fi autentisering där det är möjligt.

3. Skapa en profil för företagets Wi-Fi nätverk (se [Wi-Fi-inställningar för enheter Windows 10 enheter och senare](/intune/wi-fi-settings-windows)). I din Wi-Fi profil kan du välja att använda proxyinställningarna i din organisation.

    Alternativen är:
    - **Inga**: Inga proxyinställningar konfigureras.
    - **Konfigurera manuellt:** Ange **proxyserverns IP-adress** och **dess portnummer.**
    - **Konfigurera automatiskt**: Ange den URL som pekar till ett PAC-skript. Ange till exempel *http://proxy.contoso.com/proxy.pac* .

    Mer information om PAC-filer finns under [PAC-fil (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (öppnar en webbplats som inte tillhör Microsoft).
 
    > [!Note]
    > Vi rekommenderar att Wi-Fi till enhetsgrupper i stället för användargrupper där det är möjligt.
     
    > [!Tip]
    > Du kan också exportera en fungerande Wi-Fi från en Windows 10 dator i företagsnätverket. Den här exporten skapar en XML-fil med alla aktuella inställningar. Importera sedan den här filen till Intune och använd den som Wi-Fi för dina HoloLens 2 enheter. Se [Exportera och importera Wi-Fi-inställningar för Windows-enheter](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Tilldela](/mem/intune/configuration/device-profile-assign) enhetsprofilerna till HoloLens enhetsgrupp.

2.  [Övervaka](/mem/intune/configuration/device-profile-monitor) enhetsprofilerna i Intune.

Om det finns problem med Wi-Fi-profiler kan du gå [till Felsöka Wi-Fi för enhetskonfiguration i Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Felsöka extern Internetåtkomst när Corp är anslutet
När tjänster försöker att inte gå igenom en a konfigurerad proxyserver kan de försöka ansluta via brandväggen. Du kan lägga till en lista över slutpunktsspecifik information i brandväggsreglerna för att felsöka dessa problem.

Om du blockeras vid brandväggsportar aktiverar du vissa vanliga [slutpunkter](/hololens/hololens-offline) för HoloLens.

Du kan också aktivera guider specifika portar: [Internet-tillgängliga URL:er som krävs för anslutning till Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Appdistribution

Att distribuera en LOB-app via MDM är en metod som är enkel att skala och som kan distribueras automatiskt till dina enheter vid registrering i en skapad grupp.

Om du fortfarande utvecklar dina appar eller inte har någon ännu kan du använda en exempelapp för hubben MRTK-exempel. Den här exempelappen är redo att användas och kräver inte användning av Unity eller Visual Studio. [Ladda ned exempelappen MRTK- exempel.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Om du föredrar att använda din egen app eller är intresserad av apputveckling för Mixed Reality kan du läsa vår [dokumentation om Mixed Reality utvecklare.](/windows/mixed-reality/design/design)

> [!NOTE]
> Systemkraven för HoloLens baseras på arkitekturen i appbygget. HoloLens 2 enheter använder ARM-arkitektur. När du skapar dina Visual Studio bör du se till att du har valt rätt arkitektur för enheten och inkluderar eventuella beroenden som behövs.

> [!IMPORTANT]
> När du distribuerar LOB-appar är det viktigt att även överföra certifikatet till Intune och tilldela det till samma grupp som är avsedd att använda appen, annars installeras det inte korrekt.

### <a name="upload-and-assign-the-app"></a>Upload och tilldela appen

1. Gå till [administrationscentret för MEM.](https://endpoint.microsoft.com/#home)

2. Välj **Appar**  ->  **Alla appar** och välj **knappen +** Lägg till.

3. Under Övrigt väljer **du Branschapp**. Klicka **på välj**.

4. Välj appaketfilen, det här är din APPXBUNDLE-fil, eller i vårt exempel är appen _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Du meddelas om saknade beroenden. I det här fallet måste vi ladda upp _Microsoft.VCLibs.ARM.14.00.appx_. Sök efter den under **Välj en fil**.

6. Välj OK.

7. På nästa skärm fylls de obligatoriska fälten i automatiskt. Välj **Nästa**.

8. Under Obligatorisk lägger du till vår tidigare skapade grupp för att göra den här appen obligatorisk för gruppen. Detta gör att appen laddas ned automatiskt till registrerade enheter i gruppen. Välj **Nästa**.

9. Välj **Skapa**.

Läs mer: [Tilldela appar till grupper i Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Installationsguider: Programlicenser, dataversum och redigering

För att kunna använda Dynamics 365-guider behöver du göra en del förberedelser. Det finns tre områden där vi måste förbereda oss: användare, dataversum och guiderna själva.

### <a name="users-and-application-licenses"></a>Användare och programlicenser

För att någon ska kunna använda guider måste de använda ett Azure AD-konto, som vi har ställt in i den här guiden tidigare.

Du måste också tilldela licens för Dynamics 365-guider till den användare som du har skapat. Du gör detta från [Administrationscenter för Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). Tilldela även licensen till ditt primära Azure-konto.

Följ [den här korta guiden](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) med bilder för stegvisa instruktioner om hur du tillämpar programlicenser.

### <a name="set-up-the-dataverse"></a>Konfigurera dataversum

För att [kunna konfigurera en produktionsmiljö](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) måste du uppfylla två krav. Du måste ha [**rollen Systemadministratör**](/power-platform/admin/database-security) **och** du måste ha en [**Power Apps-licens**](/power-platform/admin/signup-question-and-answer) (eller en Licens för [**Dynamics 365-guider**](/dynamics365/mixed-reality/guides/setup-step-one) som innehåller en Power Apps licens). Om du följer den här guiden när du har skapat Azure AD uppfyller du rollkraven för Systemadministratör. Vi har också tilldelat en guidelicens i föregående steg.

I den här guiden skapar [du en Microsoft Dataverse-miljö:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Börja med att använda [Power Platform-administratörscenter](https://admin.powerplatform.microsoft.com/environments) och skapa en ny miljö.
2. När du skapar **den nya** miljön för **den** typ&#39;du välja **Produktion.**
3. Är det viktigt att du växlar Skapa **en databas för den här miljön?**  till **Ja.**
4. I dialogrutan  **Lägg till**  databas anger du alternativet Aktivera  **Dynamics 365-appar**  till  **Ja.**

Du bör öka den maximala filstorleken för objekt i dataversum. Om du ökar den maximala filstorleken kan du ladda upp större 3D-modeller eller videofiler som du kommer att använda senare i dina guider. Följ en kort guide för [att ändra den maximala filstorleken för uppladdning.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Slutligen måste du installera [och konfigurera lösningen](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). I [Power Platform-administratörscenter](https://admin.powerplatform.microsoft.com/environments)du Resurser  \& gt;  **Dynamics 365-appar,** **välj Dynamics 365-guider** i listan och välj sedan **Installera**.  

Du måste [lägga till säkerhetsrollen](/dynamics365/mixed-reality/guides/assign-role) Guider innan du kan använda apparna.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Skapa en testguide på datorn via redigering

När du skapar guider börjar du alltid på datorn. Skapa stegen, välja modeller och fäst guiden. Detta följs av att placera innehåll för guiden senare i redigeringsläge på din HoloLens enhet. I den här guiden föreslår vi att du gör en kort testguide med minimala steg och modeller.

Om du vill börja lära dig om redigering för guider börjar du här med [redigeringsöversikten.](/dynamics365/mixed-reality/guides/authoring-overview) Om du vill få en snabb översikt kan du titta på den här korta videon.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Valfritt: Helskärmsläge

Helskärmsläge är ett läge där IT-administratören kan konfigurera startmenyns användargränssnitt så att endast en enda app eller ett val av appar visas. Helskärmsläge kan också tillämpas på specifika användare, grupper eller på enhetsnivå. och i vissa fall kan du undanta vissa användare från helskärmsläge och fortfarande ge dem åtkomst till den vanliga Start-menyn.

Helskärmsläge har många olika variabler, både i omfång och konfigurationer som kan anges samt metoder för att distribuera helskärmsläge till HoloLens. På grund av alla dessa variabler lämnas helskärmsläge som _valfritt för_ den här guiden och kommer inte att gås tillbaka igen. Om du tror att du har ett företag som behöver begränsa tillgängliga appar till användare eller om du vill lära dig mer kan du lära dig hur du ställer in [HoloLens som en kiosk.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Valfritt: WDAC

WDAC gör att IT-administratörer kan konfigurera sina enheter för att blockera start av appar på enheter. Detta skiljer sig från metoder för enhetsbegränsning, till exempel helskärmsläge, där användaren ser ett användargränssnitt som döljer apparna på enheten, men de kan fortfarande startas. När WDAC implementeras visas apparna fortfarande i listan Alla appar, men WDAC hindrar dessa appar och processer från att kunna startas av enhetsanvändaren.

Mer information finns i Använda [WDAC och Windows PowerShell tillåta eller blockera](/mem/intune/configuration/custom-profile-hololens)appar på HoloLens 2 enheter med Microsoft Intune .

[Windows Defender Programkontroll – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Nästa steg 
> [!div class="nextstepaction"]
> [Företagsansluten distribution – Distribuera](hololens2-corp-connected-deploy.md)