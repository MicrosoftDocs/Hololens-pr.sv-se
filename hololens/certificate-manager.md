---
title: Certifikathanteraren
description: Lär dig hur du installerar, hanterar och tar bort certifikat manuellt på HoloLens 2-enheter med mixad verklighet.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378752"
---
# <a name="certificate-manager"></a><span data-ttu-id="51f5c-103">Certifikathanteraren</span><span class="sxs-lookup"><span data-stu-id="51f5c-103">Certificate Manager</span></span>

- <span data-ttu-id="51f5c-104">Förbättrad gransknings-, diagnostik- och valideringsverktyg för enhetssäkerhet och efterlevnad via den nya certifikathanteraren.</span><span class="sxs-lookup"><span data-stu-id="51f5c-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="51f5c-105">Med den här funktionen kan du distribuera, felsöka och validera dina certifikat i stor skala i kommersiella miljöer.</span><span class="sxs-lookup"><span data-stu-id="51f5c-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="51f5c-106">I Windows Holographic, version 20H2, lägger vi till en certifikathanterare i hololens 2-inställningsappen.</span><span class="sxs-lookup"><span data-stu-id="51f5c-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="51f5c-107">Gå till **Inställningar > Update & Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="51f5c-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="51f5c-108">Den här funktionen ger ett enkelt och användarvänligt sätt att visa, installera och ta bort certifikat på enheten.</span><span class="sxs-lookup"><span data-stu-id="51f5c-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="51f5c-109">Med den nya Certifikathanteraren har administratörer och användare nu förbättrat gransknings-, diagnos- och valideringsverktygen för att säkerställa att enheterna förblir säkra och kompatibla.</span><span class="sxs-lookup"><span data-stu-id="51f5c-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="51f5c-110">**Granskning:** Möjlighet att verifiera att ett certifikat har distribuerats korrekt eller att bekräfta att det har tagits bort på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="51f5c-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="51f5c-111">**Diagnos:** När problem uppstår kan det spara tid och hjälpa till med felsökningen att verifiera att rätt certifikat finns på enheten.</span><span class="sxs-lookup"><span data-stu-id="51f5c-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="51f5c-112">**Validering:** Att verifiera att ett certifikat har det avsedda syftet och är funktionellt kan spara mycket tid, särskilt i kommersiella miljöer innan certifikat distribueras i större skala.</span><span class="sxs-lookup"><span data-stu-id="51f5c-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="51f5c-113">Om du snabbt vill hitta ett specifikt certifikat i listan finns det alternativ för att sortera efter namn, arkiv eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="51f5c-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="51f5c-114">Användare kan också söka efter ett certifikat direkt.</span><span class="sxs-lookup"><span data-stu-id="51f5c-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="51f5c-115">Om du vill visa enskilda certifikategenskaper väljer du certifikatet och klickar på **Info**.</span><span class="sxs-lookup"><span data-stu-id="51f5c-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="51f5c-116">Certifikatinstallationen stöder för närvarande .cer- och .crt-filer.</span><span class="sxs-lookup"><span data-stu-id="51f5c-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="51f5c-117">Enhetsägare kan installera certifikat på den lokala datorn och den aktuella användaren.  alla andra användare kan bara installera i aktuell användare.</span><span class="sxs-lookup"><span data-stu-id="51f5c-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="51f5c-118">Användare kan bara ta bort certifikat som installerats direkt från inställningsgränssnittet.</span><span class="sxs-lookup"><span data-stu-id="51f5c-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="51f5c-119">Om ett certifikat har installerats på annat sätt måste det också tas bort av samma mekanism.</span><span class="sxs-lookup"><span data-stu-id="51f5c-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="51f5c-120">Så här installerar du ett certifikat:</span><span class="sxs-lookup"><span data-stu-id="51f5c-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="51f5c-121">Anslut hololens 2 till en dator.</span><span class="sxs-lookup"><span data-stu-id="51f5c-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="51f5c-122">Placera den certifikatfil som du vill installera på en plats på din HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="51f5c-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="51f5c-123">Gå till **Inställningar app > Uppdatera & Security > certifikat** och välj Installera ett certifikat.</span><span class="sxs-lookup"><span data-stu-id="51f5c-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="51f5c-124">Klicka **på Importera** fil och navigera till den plats där du sparade certifikatet.</span><span class="sxs-lookup"><span data-stu-id="51f5c-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="51f5c-125">Välj **Butiksplats.**</span><span class="sxs-lookup"><span data-stu-id="51f5c-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="51f5c-126">Välj **Certifikatarkiv.**</span><span class="sxs-lookup"><span data-stu-id="51f5c-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="51f5c-127">Klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="51f5c-127">Click **Install**.</span></span>

<span data-ttu-id="51f5c-128">Certifikatet bör nu installeras på enheten.</span><span class="sxs-lookup"><span data-stu-id="51f5c-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="51f5c-129">Så här tar du bort ett certifikat:</span><span class="sxs-lookup"><span data-stu-id="51f5c-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="51f5c-130">Du kan visa MDM-distribuerade certifikat i Certificate Manager, men du kan inte avinstallera dem i Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="51f5c-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="51f5c-131">Du måste avinstallera dem via MDM.</span><span class="sxs-lookup"><span data-stu-id="51f5c-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="51f5c-132">Gå till **Inställningar App > Update and Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="51f5c-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="51f5c-133">Sök efter certifikatet efter namn i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="51f5c-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="51f5c-134">Välj certifikatet.</span><span class="sxs-lookup"><span data-stu-id="51f5c-134">Select the certificate.</span></span>
1. <span data-ttu-id="51f5c-135">Klicka på **Ta bort**</span><span class="sxs-lookup"><span data-stu-id="51f5c-135">Click **Remove**</span></span>
1. <span data-ttu-id="51f5c-136">Välj **Ja när** du uppmanas att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="51f5c-136">Select **Yes** when prompted for confirmation.</span></span>



![Certifikatvisare i appen Inställningar under Certifikat](images/certificate-viewer-device.jpg)

![Bild som visar hur du använder användargränssnittet för certifikat för att installera ett certifikat i Inställningar.](images/certificate-device-install.jpg)
