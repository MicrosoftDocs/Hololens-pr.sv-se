---
title: Läsa in och installera appar på sidan via HoloLens 2 Appinstallationsprogram
description: Lär dig hur du installerar och felsöker appar med appinstallationsprogrammet och läser in och installerar appar via användargränssnittet.
keywords: app management, app, hololens, app installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033069"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Installera appar på HoloLens 2 via Appinstallationsprogram

> [!NOTE]
> Den här funktionen har gjorts tillgänglig [i Windows Holographic version 20H2 – December 2020 Update](hololens-release-notes.md). Kontrollera att enheten har [uppdaterats för](hololens-update-hololens.md) att använda den här funktionen.

Vi har **lagt till en ny funktion (Appinstallationsprogram)** så att du kan installera program sömlöst på dina HoloLens 2 enheter. Funktionen är på **som standard för ohanterade enheter**. För att förhindra störningar för företag är appinstallationsprogrammet **inte tillgängligt för hanterade enheter** just nu.  

En enhet betraktas som "hanterad" **om** något av följande stämmer:

- [MDM-registrerad](hololens-enroll-mdm.md)
- Konfigurerad med [konfigurationspaket](hololens-provisioning.md)
- [Användaridentitet](hololens-identity.md) är Azure AD

Nu kan du installera appar utan att behöva aktivera Utvecklarläge eller använda Enhetsportalen.  Ladda ned (via USB eller Microsoft Edge) Appx-paketet till enheten och gå till Appx-paketet i Utforskaren för att uppmanas att starta installationen.  Du kan också [initiera en installation från en webbsida](/windows/msix/app-installer/installing-windows10-apps-web). Precis som appar som du installerar från Microsoft Store eller separat inläsning med mdm-funktionen för LOB [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) App-distribution [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) måste appar signeras digitalt med signeringsverktyget och certifikatet som används för att signera måste vara betrott av HoloLens-enheten innan appen kan distribueras.

## <a name="requirements"></a>Krav

### <a name="for-your-devices"></a>För dina enheter:

Den här funktionen är för närvarande tillgänglig Windows Holographic 20H2-versionerna för HoloLens 2 enheter. Se till att alla enheter som använder den här metoden [uppdateras](hololens-update-hololens.md).

### <a name="for-your-apps"></a>För dina appar:

Appens lösningskonfiguration måste vara antingen **Huvud** eller **Version** eftersom Appinstallationsprogram använder beroenden från arkivet. Mer information om hur [du skapar appaket](/windows/msix/app-installer/create-appinstallerfile-vs)finns i .

Appar som installeras via den här metoden måste signeras digitalt. Du måste använda ett certifikat för att signera appen. Du kan antingen hämta ett certifikat från [MS-listan](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)över betrodda certifikatutfärdare, i vilket fall du inte behöver vidta några extra åtgärder. Eller så kan du signera ett eget certifikat, men certifikatet måste skickas till enheten.

- Så här signerar du [appar med signeringsverktyget.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Certifikatalternativ:**

- [MS-lista över betrodda certifikatutfärdare](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Välj en certifikatdistributionsmetod.**

- [Etableringspaket](hololens-provisioning.md) kan tillämpas på lokala enheter.
- MDM kan användas för att [tillämpa certifikat med enhetskonfigurationer](/mem/intune/protect/certificates-configure).
- Använd certifikathanteraren [på enheten.](certificate-manager.md)

## <a name="installation-method"></a>Installationsmetod

1. Kontrollera att enheten inte anses vara hanterad.
1. Kontrollera att HoloLens 2-enheten är på och att du är inloggad.
1. På datorn navigerar du till din anpassade app och kopierar yourapp.appxbundle till dittenhetsnamn\Internt Storage\Nedladdningar.
    När du har kopierat filen kan du koppla från enheten och slutföra installationen senare.
1. Från din HoloLens 2-enhet öppnar du **Start-menyn,** **väljer Alla appar** och startar **Utforskaren** appen.
1. Navigera till mappen Hämtade filer. Du kan behöva välja Den här enheten först på den vänstra panelen **i** appen och sedan gå till Nedladdningar.
1. Välj filen yourapp.appxbundle.
1. Den Appinstallationsprogram startas. Välj knappen **Installera** för att installera din app.

Den installerade appen startar automatiskt när installationen är klar.

![Installera MRTK-exempel via Appinstallationsprogram.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Felsöka installationer

Om det inte gick att installera appen kontrollerar du följande för att felsöka:

- Din app är antingen en huvud- eller version.
- Enheten uppdateras till en version som den här funktionen är tillgänglig på.
- Du [är ansluten till Internet](hololens-network.md).
- Slutpunkterna [för Microsoft Store](hololens-offline.md) är korrekt konfigurerade.  

## <a name="web-installer"></a>Webbinstallationsprogram

Användare kan installera en app direkt från en webbserver. Det här flödet använder Appinstallationsprogram tillsammans med en distributionsmetod som är enkel att ladda ned och installera.

### <a name="how-to-set-up-web-install"></a>Så här ställer du in webbinstallation:

1. Kontrollera att appen är korrekt konfigurerad för installation.
1. Följ de [här stegen för att aktivera installation från en webbsida.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Slutanvändarupplevelse:

1. Användaren tar emot och installerar certifikat på enheten med hjälp av en tidigare vald metod.
1. Användaren besöker url:en som skapades i steget ovan.

Appen kommer nu att installeras på enheten. Du hittar appen genom att öppna **Start-menyn** och välja knappen **Alla appar** för att hitta din app.

- Mer hjälp med att felsöka installationsmetoden för appinstallation finns i [Felsöka problem med installationsprogrammet för appar.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Användargränssnittet under uppdateringsprocessen stöds inte. Alternativet ShowPrompt på den [här sidan och](/windows/msix/app-installer/update-settings) relaterade alternativ stöds därför inte.

## <a name="sample-apps"></a>Exempelappar

Prova att Appinstallationsprogram någon av våra tillgängliga exempelappar. 
> [!div class="nextstepaction"]
> [Exempelappar](/windows/mixed-reality/develop/features-and-samples)
