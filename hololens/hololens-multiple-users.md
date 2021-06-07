---
title: Dela din HoloLens med flera personer
description: Du kan konfigurera HoloLens så att det delas av Azure Active Directory konton eller av flera användare som använder ett enda konto.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378831"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="8269e-103">Dela din HoloLens med flera personer</span><span class="sxs-lookup"><span data-stu-id="8269e-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="8269e-104">Det är vanligt att dela en HoloLens med många personer eller att många personer delar en uppsättning HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="8269e-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="8269e-105">Den här artikeln beskriver de olika sätt som du kan dela en enhet på.</span><span class="sxs-lookup"><span data-stu-id="8269e-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="8269e-106">Dela med flera personer, var och en med sitt eget konto</span><span class="sxs-lookup"><span data-stu-id="8269e-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="8269e-107">**Krav:** HoloLens-enheten måste köra Windows 10 version 1803 eller senare.</span><span class="sxs-lookup"><span data-stu-id="8269e-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="8269e-108">HoloLens (1:a gen) måste också [uppgraderas till Windows Holographic for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8269e-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="8269e-109">När de använder sina egna Azure Active Directory-konton (Azure AD) kan flera användare behålla sina egna användarinställningar och användardata på enheten.</span><span class="sxs-lookup"><span data-stu-id="8269e-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="8269e-110">Följ dessa steg för att konfigurera det för att se till att flera personer kan använda sina egna konton på din HoloLens:</span><span class="sxs-lookup"><span data-stu-id="8269e-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="8269e-111">Kontrollera att enheten körs med Windows 10 version 1803 eller senare.</span><span class="sxs-lookup"><span data-stu-id="8269e-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="8269e-112">Om du använder en HoloLens-enhet (första generationens) [uppgraderar du enheten till Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8269e-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="8269e-113">När du ställer in enheten väljer du Mitt **arbete eller min skola** äger den och loggar in med ett Azure AD-konto.</span><span class="sxs-lookup"><span data-stu-id="8269e-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="8269e-114">När du är klar med installationenkontrollerar du att kontoinställningarna (  >  **Inställningar)** innehåller **Andra användare**.</span><span class="sxs-lookup"><span data-stu-id="8269e-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="8269e-115">Om du vill använda HoloLens följer varje användare dessa steg:</span><span class="sxs-lookup"><span data-stu-id="8269e-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="8269e-116">Om en annan användare har använt enheten gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="8269e-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="8269e-117">Tryck på strömknappen en gång för att gå till vänteläge och tryck sedan på strömknappen igen för att återgå till låsskärmen</span><span class="sxs-lookup"><span data-stu-id="8269e-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="8269e-118">HoloLens 2-användare kan välja användarpanelen från Start-menyn för att logga ut den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="8269e-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="8269e-119">Använd autentiseringsuppgifterna för ditt Azure AD-konto för att logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="8269e-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="8269e-120">Om det är första gången du använder enheten måste du [kalibrera](hololens-calibration.md) HoloLens till dina egna ögon.</span><span class="sxs-lookup"><span data-stu-id="8269e-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="8269e-121">Om du vill se en lista över enhetsanvändare eller ta bort en användare från enheten går du till **Inställningar**  >  **Konton**  >  **Andra användare.**</span><span class="sxs-lookup"><span data-stu-id="8269e-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="8269e-122">Dela med flera personer, alla med samma konto</span><span class="sxs-lookup"><span data-stu-id="8269e-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="8269e-123">Flera användare kan också dela en HoloLens-enhet när du använder ett enda användarkonto.</span><span class="sxs-lookup"><span data-stu-id="8269e-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="8269e-124">**På HoloLens 2** uppmanar enheten den nya användaren att snabbt kalibrera och anpassa visningsupplevelsen när en ny användare sätter enheten på huvudet för första gången (samtidigt som samma konto är inloggad).</span><span class="sxs-lookup"><span data-stu-id="8269e-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="8269e-125">Enheten kan lagra kalibreringsinformationen så att enheten i framtiden automatiskt kan optimera kvaliteten och bekvämligheten för varje användares tittarupplevelse.</span><span class="sxs-lookup"><span data-stu-id="8269e-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="8269e-126">Användarna behöver inte kalibrera enheten igen.</span><span class="sxs-lookup"><span data-stu-id="8269e-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="8269e-127">**På HoloLens (första generationens)** måste användare som delar ett konto be att omcalibrera i appen Inställningar.</span><span class="sxs-lookup"><span data-stu-id="8269e-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="8269e-128">Läs mer om [kalibrering.](hololens-calibration.md)</span><span class="sxs-lookup"><span data-stu-id="8269e-128">Read more about [calibration](hololens-calibration.md).</span></span>
