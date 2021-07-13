---
title: Distributionsguide – Företagsansluten HoloLens 2 med Dynamics 365-guider – Distribuera
description: Lär dig att konfigurera distributioner av HoloLens 2 enheter över ett företagsanslutet nätverk med Dynamics 365-guider.
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637072"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="50e3a-104">Distribuera – Företagsansluten guide</span><span class="sxs-lookup"><span data-stu-id="50e3a-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="50e3a-105">En viktig del av varje distribution är att se till att distributionen är korrekt konfigurerad innan du testar den själv för att säkerställa en smidig upplevelse för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="50e3a-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="50e3a-106">Eftersom vi distribuerar Wi-Fi-certifikatet via MDM måste vi först konfigurera HoloLens och registrera enheter i ett öppet Wi-Fi-nätverk eller ett nätverk som inte kräver certifikatet.</span><span class="sxs-lookup"><span data-stu-id="50e3a-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="50e3a-107">När HoloLens oobe och registrerats tar enheten emot nätverkscertifikatet och LOB som konfigurerats tidigare och vi kommer att kunna verifiera att båda har tagits emot av enheten.</span><span class="sxs-lookup"><span data-stu-id="50e3a-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="50e3a-108">Efteråt kan du bekräfta att du både kan skapa och köra en testguide.</span><span class="sxs-lookup"><span data-stu-id="50e3a-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="50e3a-109">Registreringsverifiering</span><span class="sxs-lookup"><span data-stu-id="50e3a-109">Enrollment Validation</span></span>

<span data-ttu-id="50e3a-110">Nu när allt är korrekt konfigurerat för Azure AD- och MDM-registrering bör resten nu vara en snabb.</span><span class="sxs-lookup"><span data-stu-id="50e3a-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="50e3a-111">Du behöver en Wi-Fi och HoloLens och ett av de tidigare konfigurerade Azure AD-användarkontona.</span><span class="sxs-lookup"><span data-stu-id="50e3a-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="50e3a-112">Om enheten för närvarande inte är i ett fabriksinställningstillstånd är det nu ett bra tillfälle att [omstrecka enheten](/hololens/hololens-recovery#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="50e3a-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="50e3a-113">När enheten är i OOBE måste du börja interagera och följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="50e3a-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="50e3a-114">Anslut till ett Wi-Fi nätverk som inte kräver certifikat för att ansluta till Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="50e3a-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="50e3a-115">Detta gör att enheten kan ladda ned certifikatet som ska användas på organisationens Wi-Fi efter den första installationen.</span><span class="sxs-lookup"><span data-stu-id="50e3a-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="50e3a-116">Den kritiska uppmaningen är när du uppmanas att **Vem äger den här HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="50e3a-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="50e3a-117">Välj **Mitt arbete eller min skola äger den och ange** autentiseringsuppgifterna för ditt Azure AD-konto.</span><span class="sxs-lookup"><span data-stu-id="50e3a-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="50e3a-118">När registreringen lyckas uppmanas du att konfigurera en PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="50e3a-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="50e3a-119">Den här PIN-koden är unik för den här enheten för den här användaren.</span><span class="sxs-lookup"><span data-stu-id="50e3a-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="50e3a-120">Du uppmanas också att ange Iris-genomsökningar, röstdata och telemetriinställningar. Slutligen får du lära dig hur du öppnar Start-menyn och slutför OOBE.</span><span class="sxs-lookup"><span data-stu-id="50e3a-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="50e3a-121">När du har landat i Mixed Reality Start öppnar du Start-menyn med hjälp av **gesten Start som du** precis har lärt dig.</span><span class="sxs-lookup"><span data-stu-id="50e3a-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="50e3a-122">Välj **Inställningar** app och sedan **System**.</span><span class="sxs-lookup"><span data-stu-id="50e3a-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="50e3a-123">Den första informationen du ser är enhetsnamnet, som för din HoloLens 2-enhet är &quot; HOLOLENS följt av en sex &quot; teckensträng.</span><span class="sxs-lookup"><span data-stu-id="50e3a-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="50e3a-124">Anteckna det här namnet.</span><span class="sxs-lookup"><span data-stu-id="50e3a-124">Take note of this name.</span></span>

    ![HoloLens 2 Inställningar skärm](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="50e3a-126">Kontrollera att enheten har anslutits till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="50e3a-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="50e3a-127">Det finns två sätt:</span><span class="sxs-lookup"><span data-stu-id="50e3a-127">There are two ways;</span></span>

    1.  <span data-ttu-id="50e3a-128">Appen Inställningar.</span><span class="sxs-lookup"><span data-stu-id="50e3a-128">The Settings app.</span></span> <span data-ttu-id="50e3a-129">Från **Inställningar väljer** du Konton **Åtkomst** till arbete eller  ->  **skola.**</span><span class="sxs-lookup"><span data-stu-id="50e3a-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="50e3a-130">Från den här skärmen kan du kontrollera att du har registrerats genom att se Ansluten till &quot; namnofAAD&#39;s Azure AD.</span><span class="sxs-lookup"><span data-stu-id="50e3a-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="50e3a-131">Ansluten med *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="50e3a-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="50e3a-132">Detta kontrollerar att enheten är ansluten till din organisation&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="50e3a-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="50e3a-133">Den [Azure Portal](https://portal.azure.com/#home).</span><span class="sxs-lookup"><span data-stu-id="50e3a-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="50e3a-134">Gå till **Azure Active Directory**  ->  **Enheter**  ->  **Alla enheter** och sök efter enhetsnamnet.</span><span class="sxs-lookup"><span data-stu-id="50e3a-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="50e3a-135">Under Kopplingstyp visas den som "Azure AD-ansluten".</span><span class="sxs-lookup"><span data-stu-id="50e3a-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="50e3a-136">![Verifiera anslutningstyp i Azure AD](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="50e3a-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="50e3a-137">Kontrollera att enheten har registrerats med MDM.</span><span class="sxs-lookup"><span data-stu-id="50e3a-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="50e3a-138">Det finns två sätt:</span><span class="sxs-lookup"><span data-stu-id="50e3a-138">There are two ways;</span></span>

    1. <span data-ttu-id="50e3a-139">Från **Inställningar** väljer du **Konton Åtkomst** till arbete eller  ->  **skola.**</span><span class="sxs-lookup"><span data-stu-id="50e3a-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="50e3a-140">Från den här skärmen kan du kontrollera att du har registrerats genom att se Ansluten till &quot; namnofAAD&#39;s Azure AD.</span><span class="sxs-lookup"><span data-stu-id="50e3a-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="50e3a-141">Ansluten med *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="50e3a-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="50e3a-142">Från det här Åtkomst till arbets- eller skolkonto &quot; genom att välja Ansluten till namnofAAD&#39;s Azure AD.</span><span class="sxs-lookup"><span data-stu-id="50e3a-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="50e3a-143">Anslutet yourusername@nameofAAD.onmicrosoft.com &quot; av och välj **knappen** Info.</span><span class="sxs-lookup"><span data-stu-id="50e3a-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="50e3a-144">[Microsoft Endpoint Manager Administrationscenter](https://endpoint.microsoft.com/#home).</span><span class="sxs-lookup"><span data-stu-id="50e3a-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="50e3a-145">Logga in och välj **Enheter** och **sedan Alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="50e3a-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="50e3a-146">Härifrån kan du söka i HoloLens enhetsnamn&#39;enhetsnamn.</span><span class="sxs-lookup"><span data-stu-id="50e3a-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="50e3a-147">Du bör kunna se dina HoloLens i Intune.</span><span class="sxs-lookup"><span data-stu-id="50e3a-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Verifiera hanteras av Intune i Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="50e3a-149">Wi-Fi certifikatverifiering</span><span class="sxs-lookup"><span data-stu-id="50e3a-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="50e3a-150">Vid det här laget bör enheten ha tagit emot Wi-Fi certifikatet.</span><span class="sxs-lookup"><span data-stu-id="50e3a-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="50e3a-151">Den enklaste verifieringen du kan göra är att försöka ansluta Wi-Fi anslutning som du&#39;har tagit emot certifikatet för.</span><span class="sxs-lookup"><span data-stu-id="50e3a-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="50e3a-152">Öppna appen **Inställningar** och gå till **&amp; Nätverkets**  ->  **Internet-Wi-Fi** och välj Wi-Fi-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="50e3a-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="50e3a-153">När du är ansluten öppnar du Microsoft Edge appen och bekräftar att du kan navigera till en webbplats.</span><span class="sxs-lookup"><span data-stu-id="50e3a-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="50e3a-154">Om du vill bekräfta att du har fått certifikatet på enheten kan du använda [Certifikathanteraren.](/hololens/certificate-manager)</span><span class="sxs-lookup"><span data-stu-id="50e3a-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="50e3a-155">Verifiera installationen av LOB-appen</span><span class="sxs-lookup"><span data-stu-id="50e3a-155">Validate LOB app install</span></span>

<span data-ttu-id="50e3a-156">Om du vill se installationsförloppet för en hanterad app kan du antingen se om appen är installerad eller kontrollera Inställningar.</span><span class="sxs-lookup"><span data-stu-id="50e3a-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="50e3a-157">När du har registrerat HoloLens med en användare i den tilldelade gruppen genom att konfigurera en LOB-app som en obligatorisk installation för vår grupp, laddas appen automatiskt ned till HoloLens.</span><span class="sxs-lookup"><span data-stu-id="50e3a-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="50e3a-158">Öppna Start-menyn och välj **Alla appar**.</span><span class="sxs-lookup"><span data-stu-id="50e3a-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="50e3a-159">Beroende på hur många appar du har kan du behöva använda knapparna för **att komma upp eller** ned **på** sidan.</span><span class="sxs-lookup"><span data-stu-id="50e3a-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="50e3a-160">Om du vill verifiera installationen av appen på enheten kan du göra det via Inställningar-konton Åtkomst till arbete eller skola. Välj kontot och sedan knappen Information och rulla ned för att se olika konfigurationer och appar som tillämpas på enheten från  ->    ->  MDM. </span><span class="sxs-lookup"><span data-stu-id="50e3a-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="50e3a-161">Om du vill verifiera installationen från Intune går du till [installationsstatussidan](https://endpoint.microsoft.com/#home)appar -> alla appar på  ->     ->   ->   mem-portalen.</span><span class="sxs-lookup"><span data-stu-id="50e3a-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="50e3a-162">Se mer: [Intune-appdistribution för HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="50e3a-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="50e3a-163">Validera Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="50e3a-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="50e3a-164">Det finns lägen för appen Guider på HoloLens, redigering och drift.</span><span class="sxs-lookup"><span data-stu-id="50e3a-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="50e3a-165">Du måste slutföra redigeringen av en guide innan du använder den.</span><span class="sxs-lookup"><span data-stu-id="50e3a-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="50e3a-166">Redigera guiden</span><span class="sxs-lookup"><span data-stu-id="50e3a-166">Authoring the Guide</span></span>

<span data-ttu-id="50e3a-167">Vi behöver inte göra mycket för den här snabba valideringen.</span><span class="sxs-lookup"><span data-stu-id="50e3a-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="50e3a-168">Välj bara den guide som du förberedde på datorn.</span><span class="sxs-lookup"><span data-stu-id="50e3a-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="50e3a-169">Du behöver fästpunkten i [guiden . För en](/dynamics365/mixed-reality/guides/hololens-app-anchor)snabb validering kan du använda en holografisk fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="50e3a-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="50e3a-170">Därefter bör du placera [dina steg och modeller](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span><span class="sxs-lookup"><span data-stu-id="50e3a-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="50e3a-171">Du behöver **redigeringsrollen** för att logga in på datorn och författaren på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="50e3a-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="50e3a-172">Rollen Operatör är skrivskyddade och har ingen åtkomst till PC-appen.</span><span class="sxs-lookup"><span data-stu-id="50e3a-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="50e3a-173">Använda guiden</span><span class="sxs-lookup"><span data-stu-id="50e3a-173">Operating the Guide</span></span>

<span data-ttu-id="50e3a-174">När dina hologram är på plats kan du testa att använda guiden.</span><span class="sxs-lookup"><span data-stu-id="50e3a-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="50e3a-175">Välj **operatörsläge**</span><span class="sxs-lookup"><span data-stu-id="50e3a-175">Select **Operator mode**</span></span>
- <span data-ttu-id="50e3a-176">Klicka dig igenom stegen i guiden.</span><span class="sxs-lookup"><span data-stu-id="50e3a-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="50e3a-177">Mer detaljerad information om hur du använder en guide finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="50e3a-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="50e3a-178">Översikt över hur du använder en guide i Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="50e3a-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="50e3a-179">Lär dig mer om kortet Step som operatör i Dynamics 365-guider</span><span class="sxs-lookup"><span data-stu-id="50e3a-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="50e3a-180">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="50e3a-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="50e3a-181">Företagsansluten distribution – Underhåll</span><span class="sxs-lookup"><span data-stu-id="50e3a-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
