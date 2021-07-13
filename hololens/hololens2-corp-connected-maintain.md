---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – Underhåll
description: Lär dig hur du underhåller HoloLens 2 enheter över ett företagsanslutna nätverk med Dynamics 365-guider.
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637004"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="f6e2f-104">Underhåll – Företagsansluten guide</span><span class="sxs-lookup"><span data-stu-id="f6e2f-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="f6e2f-105">Uppdatera HoloLens</span><span class="sxs-lookup"><span data-stu-id="f6e2f-105">Update HoloLens</span></span>

<span data-ttu-id="f6e2f-106">Microsoft har utformat Windows Update för företag för att ge IT-administratörer ytterligare Windows Update-centrerade hanteringsfunktioner, till exempel möjligheten att distribuera uppdateringar till grupper av enheter och definiera underhåll windows för installation av uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="f6e2f-107">En populär metod för att hantera uppdateringar är att skjuta upp funktioner i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="f6e2f-108">På så sätt kan administratörer uppdatera och förhandsgranska nya funktioner, få förstahandskunskaper och informera supportavdelningen om eventuella nya ändringar.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="f6e2f-109">Lär dig hur [du hanterar HoloLens uppdateringar,](/hololens/hololens-updates)inklusive schemalagda dagar, schemalagd tid och inställning av aktiva timmar på enheten, så att den uppdateras utanför arbetstid.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="f6e2f-110">Uppdatera Dynamics 365-guider (och andra Store-appar)</span><span class="sxs-lookup"><span data-stu-id="f6e2f-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="f6e2f-111">Dynamics 365-guider är In-Box app och kan uppdateras via Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="f6e2f-112">För alla appar som laddas ned via Microsoft Store kan de [uppdateras via själva Microsoft Store](/hololens/holographic-store-apps#update-apps) manuellt.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="f6e2f-113">Så här uppdaterar du LOB-appar</span><span class="sxs-lookup"><span data-stu-id="f6e2f-113">How to update LOB apps</span></span>

<span data-ttu-id="f6e2f-114">LOB-appar kan uppdateras på samma sätt som de lades till i Intune.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="f6e2f-115">Appar kan uppdateras i Intune genom att ladda upp den nya appen med ett högre versionsnummer till den befintliga appkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="f6e2f-116">När enheten synkroniseras med Intune ser den att det finns en nyare appversion och att den nyare appen laddas ned och ersätter den gamla appen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="f6e2f-117">Om du vill ladda upp den nyare appen går du till [MEM-portalen](https://endpoint.microsoft.com/#home)  ->  **Appar** -> Alla appar   ->  *TheNameOfYourApp-egenskaper.*  ->  </span><span class="sxs-lookup"><span data-stu-id="f6e2f-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="f6e2f-118">Bredvid Appinformation väljer du **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="f6e2f-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="f6e2f-119">För värdet för &quot; Välj fil att uppdatera väljer du &quot; filen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="f6e2f-120">Härifrån använder du snabbmenyn för att öppna utforskaren och ladda upp den nyare versionen av LOB-appen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="f6e2f-121">Se till att inkludera beroenden efter behov.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="f6e2f-122">Se mer: [Intune-appdistribution för HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="f6e2f-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="f6e2f-123">Utvecklingsplan</span><span class="sxs-lookup"><span data-stu-id="f6e2f-123">Development Plan</span></span>

<span data-ttu-id="f6e2f-124">Nu när enheten har registrerats är du redo att distribuera fler LOB-appar till dina enheter.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="f6e2f-125">Under den här guiden använder vi en exempelapp, men det är mer troligt att du vill använda anpassade appar som skapats för din organisations behov.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="f6e2f-126">Om du redan har en LOB-app är du redo att [distribuera din app via MDM.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="f6e2f-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="f6e2f-127">Om du föredrar en annan metod kan du läsa översikten över programdistributionen [för HoloLens 2](/hololens/app-deploy-overview) för att lära dig fler metoder för att distribuera din LOB-app till dina enheter.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="f6e2f-128">Om du ännu inte har skapat en egen LOB-app eller om du fortfarande håller på att skapa den kan du läsa våra utvecklingsdokument för mixad verklighet för att börja utforma och [skapa prototyper](/windows/mixed-reality/design/design) eller lära dig de grundläggande begreppen för att komma igång med utveckling med [mixad verklighet.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="f6e2f-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="f6e2f-129">Supportplan</span><span class="sxs-lookup"><span data-stu-id="f6e2f-129">Support Plan</span></span>

<span data-ttu-id="f6e2f-130">En supportplan är utmärkt att ha på plats.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="f6e2f-131">Det är användbart att ha någon, eller en grupp, tränad på att felsöka registreringsprocessen på HoloLens-enheter och även allmän användning av HoloLens i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="f6e2f-132">För att dina användare ska kunna lösa sina problem snabbare föreslår vi att eskaleringsprocessen hanteras på ett liknande sätt som i den här ordningen:</span><span class="sxs-lookup"><span data-stu-id="f6e2f-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="f6e2f-133">Supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-133">Your Support desk.</span></span>
2. <span data-ttu-id="f6e2f-134">Ditt HoloLens expertteam</span><span class="sxs-lookup"><span data-stu-id="f6e2f-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="f6e2f-135">[HoloLens Docs](/hololens/)  /  [HoloLens felsökningsdokument](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="f6e2f-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="f6e2f-136">Kontakta supporten</span><span class="sxs-lookup"><span data-stu-id="f6e2f-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="f6e2f-137">Enhetshantering</span><span class="sxs-lookup"><span data-stu-id="f6e2f-137">Device Management</span></span>

<span data-ttu-id="f6e2f-138">Den här guiden talade om att konfigurera Mobile Enhetshantering (MDM) och använde den för att konfigurera vissa enhetskonfigurationer och tillämpa inställningar för att tillåta åtkomst när det gäller Wi-Fi certifikat och proxy.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="f6e2f-139">MDM kan dock också användas för att tillämpa enhetsbegränsningar via CSP:er och principer.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="f6e2f-140">I många fall kan enheter ha anslutningsbegränsningar, till exempel Bluetooth VPN, USB eller till och med stänga av åtkomst till kameran eller mikrofonen.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="f6e2f-141">Om du är intresserad av något av dessa rekommenderar vi att du läser vår [vanliga sida om enhetsbegränsningar.](/hololens/hololens-common-device-restrictions)</span><span class="sxs-lookup"><span data-stu-id="f6e2f-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="f6e2f-142">Det finns andra mer komplexa enhetsbegränsningar som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="f6e2f-143">Exempel:</span><span class="sxs-lookup"><span data-stu-id="f6e2f-143">Such as:</span></span>

- <span data-ttu-id="f6e2f-144">Begränsa de sidor som kan visas i Inställningar-appen med hjälp av [InställningarPageVisibility,](/hololens/settings-uri-list)så att användarna bara kan komma åt de inställningar som de behöver justera, till exempel ändra Wi-Fi anslutning.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="f6e2f-145">Använd [helskärmsläge](/hololens/hololens-kiosk) för att begränsa användargränssnittet som visas för användare på en enhet.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="f6e2f-146">Du kan ange Helskärmsläge för att visa en enda app eller flera appar med en anpassad startsida.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="f6e2f-147">Kiosker kan också presentera olika upplevelser för olika användare.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="f6e2f-148">[Windows programkontroll (WDAC) för](/hololens/windows-defender-application-control-wdac) att hålla specifika appar eller processer från att starta helt.</span><span class="sxs-lookup"><span data-stu-id="f6e2f-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="f6e2f-149">Om du vill veta mer om ytterligare metoder för enhetshantering eller enhetsbegränsningar kan du ta nästa steg och läsa vår [Enhetshantering Översikt](/hololens/hololens-csp-policy-overview).</span><span class="sxs-lookup"><span data-stu-id="f6e2f-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





