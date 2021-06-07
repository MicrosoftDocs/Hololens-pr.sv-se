---
title: Global tilldelad åtkomst
description: Kom igång med vår guide för att använda OMA-URI för globalt tilldelade åtkomst-kiosker med Intune och Windows Configuration Designer.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, tilldelad åtkomst, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380074"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="42dc1-104">Global tilldelad åtkomst – helskärmsläge</span><span class="sxs-lookup"><span data-stu-id="42dc1-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="42dc1-105">Den här funktionen konfigurerar HoloLens 2-enheten för helskärmsläge för flera appar, som gäller på systemnivå, inte har någon tillhörighet till någon identitet i systemet och gäller för alla som loggar in på enheten.</span><span class="sxs-lookup"><span data-stu-id="42dc1-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="42dc1-106">Den här funktionen är för närvarande endast tillgänglig i Windows Insider byggen.</span><span class="sxs-lookup"><span data-stu-id="42dc1-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="42dc1-107">Om du vill prova den här funktionen innan den blir allmänt tillgänglig i HoloLens-versioner kan du läsa mer [om Windows Insider](hololens-insider.md) versioner.</span><span class="sxs-lookup"><span data-stu-id="42dc1-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="42dc1-108">Hur använder jag global tilldelad åtkomst i Intune?</span><span class="sxs-lookup"><span data-stu-id="42dc1-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="42dc1-109">Tänk på de områden som är markerade med "<!-".</span><span class="sxs-lookup"><span data-stu-id="42dc1-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="42dc1-110">Dessa områden kräver att du gör ändringar baserat på dina preferenser.</span><span class="sxs-lookup"><span data-stu-id="42dc1-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="42dc1-111">Skapa en anpassad omA URI-enhetskonfigurationsprofil på följande sätt och tillämpa den på HoloLens-enhetsgruppen:</span><span class="sxs-lookup"><span data-stu-id="42dc1-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="42dc1-112">URI-värde: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="42dc1-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="42dc1-113">![Global tilldelad åtkomst OMA-URI i Intune](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="42dc1-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="42dc1-114">För värde uppdaterar och klistrar du in följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="42dc1-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="42dc1-115">Hur använder jag global tilldelad åtkomst i Windows Configuration Designer?</span><span class="sxs-lookup"><span data-stu-id="42dc1-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="42dc1-116">Uppdatera och spara XML-bloben som anges ovan som XML-fil.</span><span class="sxs-lookup"><span data-stu-id="42dc1-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="42dc1-117">Följ stegen i Använda [ett etableringspaket för att](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)konfigurera en helskärmsläge för en app eller flera appar, särskilt avsnittet "Prov.</span><span class="sxs-lookup"><span data-stu-id="42dc1-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="42dc1-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" (paket, steg 2 – Lägg till XML-filen för kioskkonfiguration i ett konfigurationspaket) och referera till XML-filen som sparades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="42dc1-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="42dc1-119">Kan jag skapa en konfiguration där global gäller för alla och separat konfiguration gäller för 1 Azure AD-konto eller Azure AD-grupp?</span><span class="sxs-lookup"><span data-stu-id="42dc1-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="42dc1-120">Ja, se XML-exempelbloben nedan.</span><span class="sxs-lookup"><span data-stu-id="42dc1-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="42dc1-121">Global tilldelad åtkomstprofil tillämpas på HoloLens när en specifik profil för den inloggade användaren inte hittas, så det är standardkonfigurationen för helskärmsläge för den inloggade användaren.</span><span class="sxs-lookup"><span data-stu-id="42dc1-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="42dc1-122">Här är ett exempel på en XML-blob som ska användas:</span><span class="sxs-lookup"><span data-stu-id="42dc1-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="42dc1-123">Tänk på de markerade områdena som är markerade med `<!-` .</span><span class="sxs-lookup"><span data-stu-id="42dc1-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="42dc1-124">Dessa områden kräver att du gör ändringar baserat på dina preferenser.</span><span class="sxs-lookup"><span data-stu-id="42dc1-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="42dc1-125">Exkludera DeviceOwners från global tilldelad åtkomstprofil</span><span class="sxs-lookup"><span data-stu-id="42dc1-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="42dc1-126">Med den här funktionen kan en användare som betraktas som["enhetsägare"](security-adminless-os.md)på HoloLens undantas från global tilldelad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="42dc1-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="42dc1-127">Se till att markerade rader läggs till i XML-bloben för helskärmskonfiguration med flera appar för att dra nytta av den här funktionen:</span><span class="sxs-lookup"><span data-stu-id="42dc1-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="42dc1-128">Ytterligare exempel på global tilldelad åtkomst</span><span class="sxs-lookup"><span data-stu-id="42dc1-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="42dc1-129">Det här är ett exempel på global tilldelad åtkomst i helskärmsläge som när en användare loggar in har en helskärmsläge för flera appar med inställningsappen, Feedbackhubben och Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="42dc1-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="42dc1-130">Det här exemplet är en global tilldelad åtkomst-kiosk som exkluderar enhetsägaren, när andra Azure AD-användare loggar in kommer att ha en helskärmsenhet för flera appar med inställningsappen, Feedbackhubben och Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="42dc1-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="42dc1-131">Den här kiosken innehåller också en sekundär kioskkonfiguration för ett besökarkonto, som kan loggas in av vem som helst på låsskärmen.</span><span class="sxs-lookup"><span data-stu-id="42dc1-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="42dc1-132">När en användare loggar in på besökarkontot har de en kiosk för flera appar som bara har Feedbackhubben appen.</span><span class="sxs-lookup"><span data-stu-id="42dc1-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
