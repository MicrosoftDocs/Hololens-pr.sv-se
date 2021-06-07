---
title: Registrera HoloLens i MDM
description: Lär dig hur du registrerar HoloLens i hantering av mobila enheter (MDM) för enklare hantering av flera enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378865"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="599d7-103">Registrera HoloLens i MDM</span><span class="sxs-lookup"><span data-stu-id="599d7-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="599d7-104">Du kan hantera flera Microsoft HoloLens enheter samtidigt med hjälp av lösningar som [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="599d7-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="599d7-105">Du kommer att kunna hantera inställningar, välja appar för att installera och ange säkerhetskonfigurationer som skräddarsytts efter organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="599d7-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="599d7-106">Se Hantera enheter som kör [Windows Holographic med Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), de konfigurationstjänstleverantörer [(CPS)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)som stöds i Windows Holographic och de principer som stöds [av Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="599d7-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="599d7-107">Hantering av mobila enheter (MDM), inklusive FUNKTIONERNA VPN, Bitlocker och helskärmsläge, är endast tillgängligt när du uppgraderar [till Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="599d7-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="599d7-108">Krav</span><span class="sxs-lookup"><span data-stu-id="599d7-108">Requirements</span></span>

 <span data-ttu-id="599d7-109">Din organisation måste ha Mobile Enhetshantering (MDM) konfigurerad för att kunna hantera HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="599d7-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="599d7-110">MDM-providern kan Microsoft Intune eller en tredjepartsprovider som använder Microsoft MDM-API:er.</span><span class="sxs-lookup"><span data-stu-id="599d7-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="599d7-111">Olika sätt att registrera</span><span class="sxs-lookup"><span data-stu-id="599d7-111">Different ways to enroll</span></span>

<span data-ttu-id="599d7-112">Beroende på vilken typ av [identitet som](hololens-identity.md) valts under OOBE eller efter inloggningen finns det olika registreringsmetoder.</span><span class="sxs-lookup"><span data-stu-id="599d7-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="599d7-113">Om Identity är Azure AD klickar du antingen på knappen Åtkomst till **arbets-** eller skolappen under OOBE  ->  **eller**  ->  **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="599d7-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="599d7-114">För Azure AD sker [automatisk MDM-registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) endast om Azure AD har konfigurerats med registrerings-URL:er.</span><span class="sxs-lookup"><span data-stu-id="599d7-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="599d7-115">Om Identity är Azure AD och enheten har förregistrerats med Intune MDM-servern med en specifik konfigurationsprofil tilldelad, sker Azure AD-Join och automatisk [MDM-registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) under OOBE.</span><span class="sxs-lookup"><span data-stu-id="599d7-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="599d7-116">Kallas även [Autopilot-flöde](hololens2-autopilot.md) tillgängligt [i versionerna 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="599d7-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="599d7-117">Om Identity är MSA använder du **knappen Inställningar**  ->  **Appåtkomst Till arbete eller School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="599d7-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="599d7-118">Kallas även för flödet Lägg till arbetskonto (AWA).</span><span class="sxs-lookup"><span data-stu-id="599d7-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="599d7-119">Om Identitet är Lokal användare använder du **inställningar**  ->  **Appåtkomst till arbete eller skola** Registrera endast i  ->  **enhetshanteringslänken.**</span><span class="sxs-lookup"><span data-stu-id="599d7-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="599d7-120">Kallas även för ett rent MDM-registreringsflöde.</span><span class="sxs-lookup"><span data-stu-id="599d7-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="599d7-121">När enheten har registrerats med MDM-servern återspeglar appen Inställningar nu att enheten har registrerats i enhetshanteringen.</span><span class="sxs-lookup"><span data-stu-id="599d7-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="599d7-122">Automatisk registrering i MDM</span><span class="sxs-lookup"><span data-stu-id="599d7-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="599d7-123">Om din organisation har en [Azure Premium-prenumeration](https://azure.microsoft.com/overview/), använder Azure Active Directory (Azure AD) och en MDM-lösning som accepterar en Azure AD-token för autentisering (för närvarande stöds endast i Microsoft Intune och AirWatch) kan IT-administratören konfigurera Azure AD att automatiskt tillåta MDM-registrering när användaren loggar in med sitt Azure AD-konto.</span><span class="sxs-lookup"><span data-stu-id="599d7-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="599d7-124">Lär dig hur du konfigurerar Azure AD-registrering.</span><span class="sxs-lookup"><span data-stu-id="599d7-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="599d7-125">När automatisk registrering är aktiverat krävs ingen extra manuell registrering.</span><span class="sxs-lookup"><span data-stu-id="599d7-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="599d7-126">När användaren loggar in med ett Azure AD-konto registreras enheten i MDM när du har slutfört den första körningen.</span><span class="sxs-lookup"><span data-stu-id="599d7-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="599d7-127">När en enhet är Ansluten till Azure AD kan det påverka vem som anser att [enhetens ägare är](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="599d7-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="599d7-128">Avregistrera HoloLens från Intune</span><span class="sxs-lookup"><span data-stu-id="599d7-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="599d7-129">Beroende på registreringsmetoden är det inte alltid möjligt att enheten avregistreras.</span><span class="sxs-lookup"><span data-stu-id="599d7-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="599d7-130">Om enheten har registrerats med ett Azure AD-konto eller Autopilot kan den inte avregistreras från Intune.</span><span class="sxs-lookup"><span data-stu-id="599d7-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="599d7-131">Om du vill avansluta HoloLens från Azure AD eller återansluta till en annan klientorganisation än Azure AD måste du [återställa/omsnedställa](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) enheten.</span><span class="sxs-lookup"><span data-stu-id="599d7-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="599d7-132">Om enheten har registrerats från ett MSA-konto som har lagt till ett arbetskonto eller från ett lokalt konto som endast registrerats i enhetshanteringen kan du avregistrera enheten.</span><span class="sxs-lookup"><span data-stu-id="599d7-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="599d7-133">Öppna Start-menyn och välj sedan knappen **Inställningar**  ->  **Appåtkomst Till arbete eller Skola**  ->  *DittKonto*  ->  **Koppla** från.</span><span class="sxs-lookup"><span data-stu-id="599d7-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>