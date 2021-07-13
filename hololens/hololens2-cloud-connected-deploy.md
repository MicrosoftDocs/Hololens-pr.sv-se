---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Distribuera
description: Lär dig hur du validerar registrering och Fjärrhjälp för HoloLens enheter över ett molnanslutet nätverk.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Enhetshantering
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635185"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="b7ba1-104">Distribuera – Molnansluten guide</span><span class="sxs-lookup"><span data-stu-id="b7ba1-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="b7ba1-105">Nu när allt har konfigurerats bör du vara redo att distribuera enheter.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="b7ba1-106">Nu bör du dock först verifiera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="b7ba1-107">Först ska processen för Azure AD-anslutning och MDM-registrering verifieras, följt av verifiering av att ett Remote Assist-anrop kan göras.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="b7ba1-108">Registreringsverifiering</span><span class="sxs-lookup"><span data-stu-id="b7ba1-108">Enrollment Validation</span></span>

<span data-ttu-id="b7ba1-109">Nu när allt är korrekt konfigurerat för Azure AD- och MDM-registrering bör resten nu vara en snabb.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="b7ba1-110">Du&#39;behöver en Wi-Fi-anslutning HoloLens enheten, samt ett av de tidigare konfigurerade AAD-användarkontona.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="b7ba1-111">Om enheten inte&#39;i fabriksinställningarna är det nu ett bra tillfälle att [omstrecka enheten](/hololens/hololens-recovery#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="b7ba1-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="b7ba1-112">När enheten är i OOBE&#39;du börja interagera och följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="b7ba1-113">Den kritiska uppmaningen är när du uppmanas att **Vem äger den här HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="b7ba1-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="b7ba1-114">Välj **Mitt arbete eller min skola äger den och ange** autentiseringsuppgifterna för ditt Azure AD-konto.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="b7ba1-115">När registreringen lyckas uppmanas&#39;att konfigurera en PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="b7ba1-116">Den här PIN-koden är unik för den här enheten för den här användaren.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="b7ba1-117">Du uppmanas också att ange Iris-genomsökningar, röstdata och telemetriinställningar, och slutligen kan du&#39;lära dig hur du öppnar Start-menyn och slutför OOBE.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="b7ba1-118">När du har landat i Mixed Reality Start öppnar du Start-menyn den **Start-gest som** du precis har lärt dig.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="b7ba1-119">Välj **Inställningar** app och **sedan System.**</span><span class="sxs-lookup"><span data-stu-id="b7ba1-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="b7ba1-120">Den första information som&#39;ser är enhetsnamnet, som för din HoloLens 2-enhet blir HOLOLENS följt av en sträng med &quot; &quot; sex tecken.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="b7ba1-121">Anteckna det här namnet.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-121">Take note of this name.</span></span>

![HoloLens 2 Inställningar – Om](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="b7ba1-123">Du kan kontrollera att enheten har registrerats i Azure AD i Inställningar appen.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="b7ba1-124">Från **Inställningar väljer** du Konton **Åtkomst** till arbete eller  ->  **skola.**</span><span class="sxs-lookup"><span data-stu-id="b7ba1-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="b7ba1-125">På den här skärmen kan du kontrollera att du har registrerats genom att se Ansluten till &quot; _namnofAAD_&#39;s Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="b7ba1-126">Ansluten med _yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; .</span><span class="sxs-lookup"><span data-stu-id="b7ba1-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="b7ba1-127">För att verifiera att enheten har anslutits till Azure AD kan vi kontrollera Azure Active Directory från [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Enheter Alla enheter och söka  ->    ->    ->  efter enhetsnamnet.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="b7ba1-128">Du&#39;kan se att enheten är en del av Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory – Enhet](./images/aad-enrollment.png)

<span data-ttu-id="b7ba1-130">Därefter&#39;du logga in på Microsoft Endpoint Manager [administrationscenter.](https://endpoint.microsoft.com/#home)</span><span class="sxs-lookup"><span data-stu-id="b7ba1-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="b7ba1-131">Logga in och välj **Enheter** och **sedan Alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="b7ba1-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="b7ba1-132">Härifrån kan du söka i HoloLens enhetsnamn&#39;enhetsnamn.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="b7ba1-133">Du bör kunna se dina HoloLens i Intune.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune – Enhet](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="b7ba1-135">Verifiering av fjärrhjälpsamtal</span><span class="sxs-lookup"><span data-stu-id="b7ba1-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="b7ba1-136">När&#39;har kontrollerat att enheten har registrerats i både din AAD och MDM&#39;det dags att testa Remote Assist-anropet.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="b7ba1-137">För den här&#39;måste du ha HoloLens-enheten och en Windows 10-dator, samt ett andra Azure AD-användarkonto för datorn.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="b7ba1-138">Det här verifieringssteget förutsätter att du tidigare har slutfört det senaste verifieringssteget och att enheten har registrerats och att Azure AD-användaren finns på enheten.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="b7ba1-139">Om du inte redan har Microsoft Teams installerat på datorn kan du ladda ned [Teams här](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span><span class="sxs-lookup"><span data-stu-id="b7ba1-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="b7ba1-140">Logga in Teams det andra Azure AD-användarkontot än det som för närvarande är inloggad på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="b7ba1-141">När du har loggat in på datorn är du redo att ta emot anropet.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="b7ba1-142">Lås upp HoloLens och logga in.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="b7ba1-143">Starta remote assist-appen genom att öppna **Start-menyn** och välja **Fjärrhjälp.**</span><span class="sxs-lookup"><span data-stu-id="b7ba1-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="b7ba1-144">Remote Assist paketeras inte bara som en inkorgsapp utan fästs HoloLens 2&#39;startmenyn.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="b7ba1-145">Om du inte&#39;den fäst på Start-menyn öppnar du listan Alla appar **för** att leta efter den.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="b7ba1-146">När Remote Assist startar bör den identifiera enhetens användare via [enkel inloggning](/azure/active-directory/manage-apps/what-is-single-sign-on) och logga in i appen.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-146">Once Remote Assist starts it should identify the user of the device via [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="b7ba1-147">I appen väljer du **Sök och** söker efter den andra användaren på datorn.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="b7ba1-148">Välj användaren för att starta anropet.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="b7ba1-149">Besvara anropet från datorn.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-149">From your PC, answer the call.</span></span>

<span data-ttu-id="b7ba1-150">Grattis, du&#39;har anslutit och är på fjärrhjälpsamtalet.</span><span class="sxs-lookup"><span data-stu-id="b7ba1-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="b7ba1-151">Se till att prova specifika funktioner för fjärrhjälp, till exempel att använda:</span><span class="sxs-lookup"><span data-stu-id="b7ba1-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="b7ba1-152">Anteckningar</span><span class="sxs-lookup"><span data-stu-id="b7ba1-152">Inking annotations</span></span>](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="b7ba1-153">Dela en fil och vy i mixad verklighet</span><span class="sxs-lookup"><span data-stu-id="b7ba1-153">Share a file and view in mixed reality</span></span>](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="b7ba1-154">Få hjälp i en annan HoloLens app</span><span class="sxs-lookup"><span data-stu-id="b7ba1-154">Get help in another HoloLens app</span></span>](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="b7ba1-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b7ba1-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b7ba1-156">Molnansluten distribution – Underhåll</span><span class="sxs-lookup"><span data-stu-id="b7ba1-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)