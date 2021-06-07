---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – Distribuera
description: Lär dig hur du ställer in distributioner av HoloLens 2-enheter via ett företagsanslutet nätverk med Dynamics 365-guider.
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378780"
---
# <a name="deploy---corporate-connected-guide"></a>Distribuera – Företagsansluten guide

En viktig del av varje distribution är att se till att distributionen är korrekt konfigurerad innan du testar den själv för att säkerställa en smidig upplevelse för slutanvändaren.

Eftersom vi distribuerar Wi-Fi-certifikatet via MDM måste vi först konfigurera HoloLens och registrera enheter i ett öppet Wi-Fi-nätverk eller ett nätverk som inte kräver certifikatet. När HoloLens har slutfört OOBE och registrerats får enheten nätverkscertifikatet och LOB som konfigurerats tidigare och vi kommer att kunna verifiera att båda har tagits emot av enheten.

Efteråt kan du bekräfta att du både kan skapa och köra en testguide.

## <a name="enrollment-validation"></a>Registreringsverifiering

Nu när allt är korrekt konfigurerat för Azure AD- och MDM-registrering bör resten nu vara en snabb. Du behöver en Wi-Fi och HoloLens-enheten och ett av de tidigare konfigurerade Azure AD-användarkontona.

Om enheten för närvarande inte är i ett fabriksinställningstillstånd är det nu ett bra tillfälle att [omstrecka enheten](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. När enheten är i OOBE måste du börja interagera och följa anvisningarna.

2. Anslut till ett Wi-Fi nätverk som inte kräver certifikat för att ansluta till Wi-Fi. Detta gör att enheten kan ladda ned certifikatet som ska användas på organisationens Wi-Fi efter den första installationen.

3. Den kritiska uppmaningen blir när du **tillfrågas Vem äger hololens?** Välj **Mitt arbete eller min skola äger den och ange** autentiseringsuppgifterna för ditt Azure AD-konto.

4. När registreringen lyckas uppmanas du att konfigurera en PIN-kod. Den här PIN-koden är unik för den här enheten för den här användaren. Du uppmanas också att ange Iris-genomsökningar, röstdata och telemetriinställningar. Slutligen får du lära dig hur du öppnar Start-menyn och slutför OOBE.

5. När du har landat i Mixed Reality Start öppnar du Start-menyn med hjälp av **gesten Start som du** precis har lärt dig.

6. Välj appen **Inställningar** och välj **System**. Den första informationen du ser är enhetsnamnet, som för din HoloLens 2-enhet är &quot; HOLOLENS följt av en sex &quot; teckensträng.

7. Anteckna det här namnet.

    ![Skärmen HoloLens 2-inställningar](./images/hololens2-settings-about.jpg)

8. Kontrollera att enheten har anslutits till Azure AD. Det finns två sätt:

    1.  Appen Inställningar. Från **Inställningar väljer** du **Konton** Åtkomst till arbete  ->  **eller skola.** Från den här skärmen kan du kontrollera att du har registrerats genom att se Ansluten till &quot; namnofAAD&#39;s Azure AD. Ansluten med *yourusername@nameofAAD.onmicrosoft.com* . Detta kontrollerar att enheten är ansluten till din organisation&#39;Azure AD.

    1. Den [Azure Portal](https://portal.azure.com/#home). Gå till **Azure Active Directory**  ->    ->  **Enheter Alla** enheter och sök efter enhetsnamnet. Under Kopplingstyp visas den som "Azure AD-ansluten".
        ![Verifiera anslutningstyp i Azure AD](./images/hololens2-devices-all-devices.png)

9. Kontrollera att enheten har registrerats med MDM. Det finns två sätt:

    1. Från **Inställningar** väljer du **Konton Åtkomst** till arbete eller  ->  **skola.** Från den här skärmen kan du kontrollera att du har registrerats genom att se Ansluten till &quot; namnofAAD&#39;s Azure AD. Ansluten med *yourusername@nameofAAD.onmicrosoft.com* . Från det här Åtkomst till arbets- eller skolkonto &quot; genom att välja Ansluten till namnofAAD&#39;s Azure AD. Anslutet yourusername@nameofAAD.onmicrosoft.com &quot; av och välj **knappen** Info.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Logga in och välj **Enheter** och **sedan Alla enheter.** Härifrån kan du söka i holoLens-enheten&#39;namn. Du bör kunna se din HoloLens listad i Intune.

        ![Verifiera hanteras av Intune i Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi certifikatverifiering

Vid det här laget bör enheten ha tagit emot Wi-Fi certifikatet. Den enklaste verifieringen du kan göra är att försöka ansluta Wi-Fi anslutning som du&#39;har tagit emot certifikatet för. Öppna appen **Inställningar och** gå till **&amp; Nätverkets**  ->  **Internet-Wi-Fi** och välj Wi-Fi-anslutningen. När du är ansluten öppnar du Microsoft Edge appen och bekräftar att du kan navigera till en webbplats.

Om du vill bekräfta att du har fått certifikatet på enheten kan du använda [Certifikathanteraren.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Verifiera installationen av LOB-appen

Om du vill se installationsförloppet för en hanterad app kan du antingen se om appen har installerats eller markera Inställningar. När du har registrerat HoloLens med en användare i den tilldelade gruppen och konfigurerat en LOB-app som en obligatorisk installation för vår grupp, laddas appen automatiskt ned till HoloLens.

Öppna Start-menyn och välj **Alla appar**. Beroende på hur många appar du har kan du behöva använda knapparna för **att komma upp eller** ned **på** sidan.

Om du vill verifiera installationen av appen på enheten kan du göra det **via** Inställningar Konton Åtkomst till arbete eller skola. Välj kontot och sedan knappen Information och rulla ned för att se olika konfigurationer och appar som tillämpas på enheten från  ->    ->  MDM. 

Om du vill verifiera installationen från Intune går du till [installationsstatussidan](https://endpoint.microsoft.com/#home)appar -> alla appar på  ->     ->   ->   mem-portalen.

Se mer: [Intune-appdistribution för HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validera Dynamics 365-guider

Det finns lägen för appen Guider på HoloLens, redigering och drift. Du måste slutföra redigeringen av en guide innan du använder den.

### <a name="authoring-the-guide"></a>Redigera guiden

Vi behöver inte göra mycket för den här snabba valideringen. Välj bara den guide som du förberedde på datorn. Du behöver fästpunkten i [guiden . För en](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)snabb validering kan du använda en holografisk fästpunkt. Därefter bör du placera [dina steg och modeller](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Du behöver **redigeringsrollen** för att logga in på datorn och författaren på HoloLens. Rollen Operatör är skrivskyddade och har ingen åtkomst till PC-appen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Använda guiden

När dina hologram är på plats kan du testa att använda guiden. 
- Välj **operatörsläge**
- Klicka dig igenom stegen i guiden.

Mer detaljerad information om hur du använder en guide finns i följande resurser:

[Översikt över hur du använder en guide i Dynamics 365-guider](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Lär dig mer om kortet Step som operatör i Dynamics 365-guider](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Nästa steg 
> [!div class="nextstepaction"]
> [Företagsansluten distribution – Underhåll](hololens2-corp-connected-maintain.md)
