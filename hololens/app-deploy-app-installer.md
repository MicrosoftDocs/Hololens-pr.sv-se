---
title: Läsa in och installera appar på sidan via HoloLens 2-Appinstallationsprogram
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378762"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="17ea3-104">Installera appar på HoloLens 2 via Appinstallationsprogram</span><span class="sxs-lookup"><span data-stu-id="17ea3-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="17ea3-105">Den här funktionen har gjorts tillgänglig [i Windows Holographic version 20H2 – December 2020 Update](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="17ea3-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="17ea3-106">Kontrollera att enheten har [uppdaterats för](hololens-update-hololens.md) att använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="17ea3-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="17ea3-107">Vi har **lagt till en ny funktion (Appinstallationsprogram)** så att du kan installera program sömlöst på dina HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="17ea3-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="17ea3-108">Funktionen är på **som standard för ohanterade enheter**.</span><span class="sxs-lookup"><span data-stu-id="17ea3-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="17ea3-109">För att förhindra störningar för företag är appinstallationsprogrammet **inte tillgängligt för hanterade enheter** just nu.</span><span class="sxs-lookup"><span data-stu-id="17ea3-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="17ea3-110">En enhet betraktas som "hanterad" **om** något av följande stämmer:</span><span class="sxs-lookup"><span data-stu-id="17ea3-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="17ea3-111">[MDM-registrerad](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="17ea3-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="17ea3-112">Konfigurerad med [konfigurationspaket](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="17ea3-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="17ea3-113">[Användaridentitet](hololens-identity.md) är Azure AD</span><span class="sxs-lookup"><span data-stu-id="17ea3-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="17ea3-114">Nu kan du installera appar utan att behöva aktivera Utvecklarläge eller använda Enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="17ea3-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="17ea3-115">Ladda ned (via USB eller Microsoft Edge) Appx-paketet till enheten och gå till Appx-paketet i Utforskaren för att uppmanas att starta installationen.</span><span class="sxs-lookup"><span data-stu-id="17ea3-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="17ea3-116">Du kan också [initiera en installation från en webbsida](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="17ea3-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="17ea3-117">Precis som appar som du installerar från Microsoft Store eller separat inläsning med mdm-funktionen för LOB [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) App-distribution [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) måste appar signeras digitalt med signeringsverktyget och det certifikat som används för att signera måste vara betrott av HoloLens-enheten innan appen kan distribueras.</span><span class="sxs-lookup"><span data-stu-id="17ea3-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="17ea3-118">Krav</span><span class="sxs-lookup"><span data-stu-id="17ea3-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="17ea3-119">För dina enheter:</span><span class="sxs-lookup"><span data-stu-id="17ea3-119">For your devices:</span></span>

<span data-ttu-id="17ea3-120">Den här funktionen är för närvarande tillgänglig i Windows Holographic 20H2-versioner för HoloLens 2-enheter.</span><span class="sxs-lookup"><span data-stu-id="17ea3-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="17ea3-121">Se till att alla enheter som använder den här metoden [uppdateras](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="17ea3-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="17ea3-122">För dina appar:</span><span class="sxs-lookup"><span data-stu-id="17ea3-122">For your apps:</span></span>

<span data-ttu-id="17ea3-123">Appens lösningskonfiguration måste vara antingen **Master** eller **Release** eftersom Appinstallationsprogram använder beroenden från arkivet.</span><span class="sxs-lookup"><span data-stu-id="17ea3-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="17ea3-124">Mer information om hur [du skapar appaket](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)finns i .</span><span class="sxs-lookup"><span data-stu-id="17ea3-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="17ea3-125">Appar som installeras via den här metoden måste vara digitalt signerade.</span><span class="sxs-lookup"><span data-stu-id="17ea3-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="17ea3-126">Du måste använda ett certifikat för att signera appen.</span><span class="sxs-lookup"><span data-stu-id="17ea3-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="17ea3-127">Du kan antingen hämta ett certifikat från [MS-listan](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)över betrodda certifikatutfärdare, i vilket fall du inte behöver vidta några extra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="17ea3-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="17ea3-128">Eller så kan du signera ett eget certifikat, men certifikatet måste skickas till enheten.</span><span class="sxs-lookup"><span data-stu-id="17ea3-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="17ea3-129">Så här signerar du [appar med signeringsverktyget.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="17ea3-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="17ea3-130">**Certifikatalternativ:**</span><span class="sxs-lookup"><span data-stu-id="17ea3-130">**Certificate options:**</span></span>

- [<span data-ttu-id="17ea3-131">MS-lista över betrodda certifikatutfärdare</span><span class="sxs-lookup"><span data-stu-id="17ea3-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="17ea3-132">**Välj en certifikatdistributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="17ea3-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="17ea3-133">[Etableringspaket](hololens-provisioning.md) kan tillämpas på lokala enheter.</span><span class="sxs-lookup"><span data-stu-id="17ea3-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="17ea3-134">MDM kan användas för att [tillämpa certifikat med enhetskonfigurationer.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="17ea3-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="17ea3-135">Använd certifikathanteraren [på enheten.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="17ea3-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="17ea3-136">Installationsmetod</span><span class="sxs-lookup"><span data-stu-id="17ea3-136">Installation method</span></span>

1. <span data-ttu-id="17ea3-137">Kontrollera att enheten inte anses vara hanterad.</span><span class="sxs-lookup"><span data-stu-id="17ea3-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="17ea3-138">Kontrollera att HoloLens 2-enheten är påslagen och att du är inloggad.</span><span class="sxs-lookup"><span data-stu-id="17ea3-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="17ea3-139">På datorn navigerar du till din anpassade app och kopierar yourapp.appxbundle till dittenhetsnamn\Intern lagring\Nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="17ea3-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="17ea3-140">När du har kopierat filen kan du koppla från enheten och slutföra installationen senare.</span><span class="sxs-lookup"><span data-stu-id="17ea3-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="17ea3-141">Från hololens 2-enheten öppnar du **Start-menyn,** **Alla appar** och startar **Utforskaren** appen.</span><span class="sxs-lookup"><span data-stu-id="17ea3-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="17ea3-142">Navigera till mappen Hämtade filer.</span><span class="sxs-lookup"><span data-stu-id="17ea3-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="17ea3-143">Du kan behöva välja Den här enheten först på den vänstra panelen **i** appen och sedan gå till Nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="17ea3-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="17ea3-144">Välj filen yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="17ea3-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="17ea3-145">Den Appinstallationsprogram startas.</span><span class="sxs-lookup"><span data-stu-id="17ea3-145">The App Installer will launch.</span></span> <span data-ttu-id="17ea3-146">Välj knappen **Installera** för att installera din app.</span><span class="sxs-lookup"><span data-stu-id="17ea3-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="17ea3-147">Den installerade appen startar automatiskt när installationen är klar.</span><span class="sxs-lookup"><span data-stu-id="17ea3-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installera MRTK-exempel via Appinstallationsprogram](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="17ea3-149">Felsöka installationer</span><span class="sxs-lookup"><span data-stu-id="17ea3-149">Troubleshooting Installs</span></span>

<span data-ttu-id="17ea3-150">Om det inte gick att installera appen kontrollerar du följande för att felsöka:</span><span class="sxs-lookup"><span data-stu-id="17ea3-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="17ea3-151">Din app är antingen en huvud- eller version.</span><span class="sxs-lookup"><span data-stu-id="17ea3-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="17ea3-152">Enheten uppdateras till en version som den här funktionen är tillgänglig på.</span><span class="sxs-lookup"><span data-stu-id="17ea3-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="17ea3-153">Du [är ansluten till Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="17ea3-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="17ea3-154">Slutpunkterna [för Microsoft Store](hololens-offline.md) är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="17ea3-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="17ea3-155">Webbinstallationsprogram</span><span class="sxs-lookup"><span data-stu-id="17ea3-155">Web Installer</span></span>

<span data-ttu-id="17ea3-156">Användare kan installera en app direkt från en webbserver.</span><span class="sxs-lookup"><span data-stu-id="17ea3-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="17ea3-157">Det här flödet använder Appinstallationsprogram tillsammans med en distributionsmetod som är enkel att ladda ned och installera.</span><span class="sxs-lookup"><span data-stu-id="17ea3-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="17ea3-158">Så här ställer du in webbinstallation:</span><span class="sxs-lookup"><span data-stu-id="17ea3-158">How to set up web install:</span></span>

1. <span data-ttu-id="17ea3-159">Kontrollera att appen är korrekt konfigurerad för installation.</span><span class="sxs-lookup"><span data-stu-id="17ea3-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="17ea3-160">Följ de [här stegen för att aktivera installation från en webbsida.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="17ea3-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="17ea3-161">Slutanvändarupplevelse:</span><span class="sxs-lookup"><span data-stu-id="17ea3-161">End user experience:</span></span>

1. <span data-ttu-id="17ea3-162">Användaren tar emot och installerar certifikat på enheten med hjälp av en tidigare vald metod.</span><span class="sxs-lookup"><span data-stu-id="17ea3-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="17ea3-163">Användaren besöker url:en som skapades i steget ovan.</span><span class="sxs-lookup"><span data-stu-id="17ea3-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="17ea3-164">Appen kommer nu att installeras på enheten.</span><span class="sxs-lookup"><span data-stu-id="17ea3-164">The app will now install to the device.</span></span> <span data-ttu-id="17ea3-165">Du hittar appen genom att öppna **Start-menyn** och välja knappen **Alla appar** för att hitta din app.</span><span class="sxs-lookup"><span data-stu-id="17ea3-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="17ea3-166">Mer hjälp med att felsöka installationsmetoden för appinstallation finns i [Felsöka problem med installationsprogrammet för appar.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="17ea3-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="17ea3-167">Användargränssnittet under uppdateringsprocessen stöds inte.</span><span class="sxs-lookup"><span data-stu-id="17ea3-167">UI during the update process is not supported.</span></span> <span data-ttu-id="17ea3-168">Alternativet ShowPrompt på den [här sidan och](https://docs.microsoft.com/windows/msix/app-installer/update-settings) relaterade alternativ stöds därför inte.</span><span class="sxs-lookup"><span data-stu-id="17ea3-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="17ea3-169">Exempelappar</span><span class="sxs-lookup"><span data-stu-id="17ea3-169">Sample Apps</span></span>

<span data-ttu-id="17ea3-170">Om du vill Appinstallationsprogram med några exempelappar kan du kolla in några av våra tillgängliga exempel:</span><span class="sxs-lookup"><span data-stu-id="17ea3-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="17ea3-171">MRTK-exempelhubb</span><span class="sxs-lookup"><span data-stu-id="17ea3-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="17ea3-172">Ytor</span><span class="sxs-lookup"><span data-stu-id="17ea3-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="17ea3-173">UWP-exempelappar som kan användas för testning</span><span class="sxs-lookup"><span data-stu-id="17ea3-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
