---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Underhåll
description: Håll dig uppdaterad med våra tips för att underhålla och stödja HoloLens-enheter i ett molnanslutet nätverk.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378879"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="60768-104">Underhåll – Molnansluten guide</span><span class="sxs-lookup"><span data-stu-id="60768-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="60768-105">Uppdateringar</span><span class="sxs-lookup"><span data-stu-id="60768-105">Updates</span></span>

<span data-ttu-id="60768-106">Microsoft har Windows Update för företag för att ge IT-administratörer ytterligare Windows Update-centrerade hanteringsfunktioner, till exempel möjligheten att distribuera uppdateringar till grupper av enheter och definiera underhåll windows för installation av uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="60768-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="60768-107">Lär dig hur [du hanterar HoloLens-uppdateringar,](https://docs.microsoft.com/hololens/hololens-updates) inklusive schemalagda dagar, schemalagd tid och inställning av aktiva timmar på enheten så att den uppdateras utanför arbetstid.</span><span class="sxs-lookup"><span data-stu-id="60768-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="60768-108">Remote Assist är In-Box app och kan uppdateras via Microsoft Store appen.</span><span class="sxs-lookup"><span data-stu-id="60768-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="60768-109">För alla appar som laddas ned via Microsoft Store de uppdateras [via själva Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) manuellt.</span><span class="sxs-lookup"><span data-stu-id="60768-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="60768-110">Supportplan</span><span class="sxs-lookup"><span data-stu-id="60768-110">Support Plan</span></span>

<span data-ttu-id="60768-111">En supportplan är utmärkt att ha på plats.</span><span class="sxs-lookup"><span data-stu-id="60768-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="60768-112">Det är användbart att ha någon eller en grupp tränad på att felsöka registreringsprocessen på HoloLens-enheter och även allmän användning av HoloLens-enheten i din organisation.</span><span class="sxs-lookup"><span data-stu-id="60768-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="60768-113">För att dina användare ska kunna lösa sina problem snabbare föreslår vi att eskaleringsprocessen hanteras på ett liknande sätt som i den här ordningen:</span><span class="sxs-lookup"><span data-stu-id="60768-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="60768-114">Supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="60768-114">Your Support desk.</span></span>
2. <span data-ttu-id="60768-115">Ditt HoloLens Expert-team</span><span class="sxs-lookup"><span data-stu-id="60768-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="60768-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Felsökningsdokument för HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="60768-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="60768-117">Kontakta supporten</span><span class="sxs-lookup"><span data-stu-id="60768-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="60768-118">Utvecklingsplan</span><span class="sxs-lookup"><span data-stu-id="60768-118">Development Plan</span></span>

<span data-ttu-id="60768-119">Nu när enheten har registrerats är du redo att distribuera verksamhetsapplikationer (LOB-appar) till dina enheter.</span><span class="sxs-lookup"><span data-stu-id="60768-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="60768-120">Det här är anpassade appar som skapats för&#39;organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="60768-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="60768-121">Om du redan har en verksamhetslinjeapp är&#39;redo att [distribuera din app via MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="60768-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="60768-122">Om du&#39;föredrar en annan metod kan du läsa översikten över programdistributionen för [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) för att lära dig fler metoder för att distribuera din LOB-app till dina enheter.</span><span class="sxs-lookup"><span data-stu-id="60768-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="60768-123">Om du&#39;har skapat en egen LOB-app eller om du fortfarande håller på att skapa den kan du läsa våra utvecklingsdokument för mixad verklighet för att börja utforma och [skapa prototyper](https://docs.microsoft.com/windows/mixed-reality/design/design) eller lära dig huvudbegreppen för att komma igång med utveckling med [mixad verklighet.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="60768-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="60768-124">Enhetshantering</span><span class="sxs-lookup"><span data-stu-id="60768-124">Device Management</span></span> 

<span data-ttu-id="60768-125">Den här guiden talade om att konfigurera Mobile Enhetshantering (MDM) men den användes inte för att tillämpa enhetsbegränsningar eller principer tillämpades på enheter.</span><span class="sxs-lookup"><span data-stu-id="60768-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="60768-126">Enhetshantering kan användas både för att tillåta åtkomst genom att push-certifikat, eller begränsa åtkomst med en mängd olika enhetsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="60768-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="60768-127">I många fall kan enheter ha anslutningsbegränsningar som Bluetooth, VPN, USB eller till och med stänga av åtkomst till kameran eller mikrofonen.</span><span class="sxs-lookup"><span data-stu-id="60768-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="60768-128">Om du är intresserad av detta rekommenderar vi att du läser vår [vanliga sida om enhetsbegränsningar.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="60768-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="60768-129">Det finns andra mer komplexa enhetsbegränsningar som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="60768-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="60768-130">Exempel:</span><span class="sxs-lookup"><span data-stu-id="60768-130">Such as:</span></span>

- <span data-ttu-id="60768-131">Begränsa de sidor som kan visas i appen Inställningar med hjälp av [InställningarPageVisibility,](settings-uri-list.md)så att användarna bara kan komma åt de inställningar som de behöver justera, till exempel ändra deras Wi-Fi anslutning.</span><span class="sxs-lookup"><span data-stu-id="60768-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="60768-132">Använd [helskärmsläge](hololens-kiosk.md) för att begränsa användargränssnittet som visas för användare på en enhet.</span><span class="sxs-lookup"><span data-stu-id="60768-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="60768-133">Du kan ange Helskärmsläge för att visa en enda app eller flera appar med en anpassad startsida.</span><span class="sxs-lookup"><span data-stu-id="60768-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="60768-134">Kiosker kan också presentera olika upplevelser för olika användare.</span><span class="sxs-lookup"><span data-stu-id="60768-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="60768-135">[Windows Application Control (WDAC) för](windows-defender-application-control-wdac.md) att hålla specifika appar eller processer från att starta helt.</span><span class="sxs-lookup"><span data-stu-id="60768-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="60768-136">Om du vill veta mer om fler olika metoder för enhetshantering eller enhetsbegränsningar kan du ta nästa steg och läsa vår Enhetshantering Översikt.</span><span class="sxs-lookup"><span data-stu-id="60768-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="60768-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="60768-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60768-138">Läs översikten över CPS och Enhetshantering</span><span class="sxs-lookup"><span data-stu-id="60768-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)