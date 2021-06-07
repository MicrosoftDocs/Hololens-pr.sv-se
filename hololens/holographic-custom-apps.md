---
title: Hantera anpassade appar för HoloLens (första generationen)
description: Lär dig hur du installerar, avinstallerar och läser in anpassade holografiska appar på HoloLens-enheter med hjälp av Enhetsportalen och Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378772"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="504e0-104">Hantera anpassade appar för HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="504e0-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="504e0-105">HoloLens stöder många befintliga program från Microsoft Store, samt nya appar som skapats specifikt för HoloLens.</span><span class="sxs-lookup"><span data-stu-id="504e0-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="504e0-106">Den här artikeln fokuserar på anpassade holografiska program.</span><span class="sxs-lookup"><span data-stu-id="504e0-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="504e0-107">Mer information om Store-appar finns [i Hantera appar med Store.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="504e0-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="504e0-108">Följande information skapades för HoloLens (första generationen), även kallat HoloLens Developer Edition vid den tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="504e0-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="504e0-109">Därför var separat inläsning av appar via enhetsportalen och installation av appar via Visual Studio vanligt förekommande då.</span><span class="sxs-lookup"><span data-stu-id="504e0-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="504e0-110">För företagsdistributioner rekommenderar vi inte att du aktiverar Utvecklarläge, som båda dessa metoder använder.</span><span class="sxs-lookup"><span data-stu-id="504e0-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="504e0-111">Om du är intresserad av en säker appdistributionsmetod kan du läsa vår [apphantering: Översikt.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="504e0-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="504e0-112">Om du letar efter någon av utvecklarmetoden för appinstallation för HoloLens 2-enheter kan du gå till:</span><span class="sxs-lookup"><span data-stu-id="504e0-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="504e0-113">Enhetsportalen: Installera en app</span><span class="sxs-lookup"><span data-stu-id="504e0-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="504e0-114">Använda Visual Studio för att distribuera och felsöka appar</span><span class="sxs-lookup"><span data-stu-id="504e0-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="504e0-115">Installera anpassade appar</span><span class="sxs-lookup"><span data-stu-id="504e0-115">Install custom apps</span></span>

<span data-ttu-id="504e0-116">Du kan installera dina egna program på HoloLens antingen med Enhetsportalen eller genom att distribuera apparna från Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="504e0-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="504e0-117">Installera ett programpaket med Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="504e0-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="504e0-118">Upprätta en anslutning från [Enhetsportalen](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) till HoloLens-målet.</span><span class="sxs-lookup"><span data-stu-id="504e0-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="504e0-119">I det vänstra navigeringsfönstret går du till **sidan** Appar.</span><span class="sxs-lookup"><span data-stu-id="504e0-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="504e0-120">Under **Appaket bläddrar** du till den .appx-fil som är associerad med ditt program.</span><span class="sxs-lookup"><span data-stu-id="504e0-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="504e0-121">Se till att referera till eventuella associerade beroende- och certifikatfiler.</span><span class="sxs-lookup"><span data-stu-id="504e0-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="504e0-122">Välj **Go**.</span><span class="sxs-lookup"><span data-stu-id="504e0-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="504e0-123">![Installera appformulär i Windows Enhetsportalen på Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="504e0-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="504e0-124">Distribuera från Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="504e0-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="504e0-125">Öppna appens lösning Visual Studio (SLN-fil).</span><span class="sxs-lookup"><span data-stu-id="504e0-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="504e0-126">Öppna projektets **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="504e0-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="504e0-127">Välj följande byggkonfiguration: **Master/x86/Fjärrdator**.</span><span class="sxs-lookup"><span data-stu-id="504e0-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="504e0-128">När du väljer **Fjärrdator:**</span><span class="sxs-lookup"><span data-stu-id="504e0-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="504e0-129">Se till att adressen pekar på Wi-Fi IP-adressen för din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="504e0-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="504e0-130">Ange universal **(okrypterat protokoll) för autentisering.**</span><span class="sxs-lookup"><span data-stu-id="504e0-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="504e0-131">Skapa din lösning.</span><span class="sxs-lookup"><span data-stu-id="504e0-131">Build your solution.</span></span>

1. <span data-ttu-id="504e0-132">Om du vill distribuera appen från utvecklingsdatorn till din HoloLens väljer du **Fjärrdator.**</span><span class="sxs-lookup"><span data-stu-id="504e0-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="504e0-133">Om du redan har en befintlig version på HoloLens väljer du **Ja för** att installera den nyare versionen.</span><span class="sxs-lookup"><span data-stu-id="504e0-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Fjärrdatordistribution för appar som ska Microsoft HoloLens i Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="504e0-135">Programmet installeras och startas automatiskt på din HoloLens.</span><span class="sxs-lookup"><span data-stu-id="504e0-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="504e0-136">När du har installerat en app finns den  i listan Alla appar (**Starta**  >  **Alla appar**).</span><span class="sxs-lookup"><span data-stu-id="504e0-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
