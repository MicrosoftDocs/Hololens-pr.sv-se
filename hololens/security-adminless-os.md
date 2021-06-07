---
title: Säkerhet för adminlös operativsystem
description: Lär dig mer om operativsystem utan administratörer, enhetsägare och säkerhet på HoloLens-enheter med mixad verklighet.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380037"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="349fb-104">Adminlös operativsystem</span><span class="sxs-lookup"><span data-stu-id="349fb-104">Admin-less operating system</span></span>

<span data-ttu-id="349fb-105">HoloLens 2 minimerar ytan för behörighetseskalering genom att inaktivera stöd för gruppen Administratörer och begränsa all UWP-programkod från tredje part till att endast köras som standardanvändare i sandbox-miljön AppContainer.</span><span class="sxs-lookup"><span data-stu-id="349fb-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="349fb-106">Den här koden beviljas endast åtkomst till de resurser som skyddas av funktioner som uttryckligen visas i programmet för en icke-relevant användare, förutom resurser som är tillgängliga för alla AppContainers.</span><span class="sxs-lookup"><span data-stu-id="349fb-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="349fb-107">Dessa programfunktioner har fortfarande klassificeringsmodellen med tre nivåer:</span><span class="sxs-lookup"><span data-stu-id="349fb-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="349fb-108">Allmänt</span><span class="sxs-lookup"><span data-stu-id="349fb-108">General</span></span>
  * <span data-ttu-id="349fb-109">Begränsade</span><span class="sxs-lookup"><span data-stu-id="349fb-109">Restricted</span></span>
  * <span data-ttu-id="349fb-110">Windows</span><span class="sxs-lookup"><span data-stu-id="349fb-110">Windows</span></span>

<span data-ttu-id="349fb-111">Windows-komponenter kan också använda sandbox-miljön AppContainer via System UWPs.</span><span class="sxs-lookup"><span data-stu-id="349fb-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="349fb-112">Mer information om Universell Windows-plattform (UWP) finns i [UWP-dokumentationen.](https://docs.microsoft.com/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="349fb-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="349fb-113">Dessutom använder Windows-komponenter med större behörighetsminskningsbehov (t.ex. sidor med webbläsarinnehåll eller parsare) sandbox-miljön Mindre privilegierad AppContainer (LPAC), vilket stänger av åtkomsten till den uppsättning resurser som är tillgänglig för alla AppContainers.</span><span class="sxs-lookup"><span data-stu-id="349fb-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="349fb-114">Enhetens ägare</span><span class="sxs-lookup"><span data-stu-id="349fb-114">Device owner</span></span>

<span data-ttu-id="349fb-115">Slutligen tillåts endast "enhetsägare" att utföra specifika enhetsomfattande åtgärder, till exempel att ansluta enheten till en klient eller användarhantering.</span><span class="sxs-lookup"><span data-stu-id="349fb-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="349fb-116">Den här gruppen fylls i av användare på enheten med något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="349fb-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="349fb-117">Den första användaren på enheten är alltid ägare.</span><span class="sxs-lookup"><span data-stu-id="349fb-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="349fb-118">För Azure AD-användare är undantaget till den här regeln att om enheten är Azure AD-ansluten via Autopilot eller azure AD-massregistrering, som använder en icke-verklig användare.</span><span class="sxs-lookup"><span data-stu-id="349fb-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="349fb-119">I det här fallet kanske den första AAD-användaren som loggar in på enheten inte blir enhetsägare automatiskt såvida inte användaren har rollen "global administratör" eller "enhetsadministratör" tilldelad i Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="349fb-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="349fb-120">Mer information finns i anteckningen nedan.</span><span class="sxs-lookup"><span data-stu-id="349fb-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="349fb-121">När en användare upphöjs till ägare från inställnings-UX av en annan ägare på enheten.</span><span class="sxs-lookup"><span data-stu-id="349fb-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="349fb-122">Om enhetens ägare inte längre är tillgänglig (lämnar företaget) och enheten är Ansluten till Azure AD kan klientorganisationsadministratören ändra enhetens ägare till en ny användare i Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="349fb-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="349fb-123">Globala administratörer och enhetsadministratörer för en Azure AD-klientorganisation loggas implicit in som ägare på enheten utan att något av de föregående stegen krävs.</span><span class="sxs-lookup"><span data-stu-id="349fb-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="349fb-124">IT-administratörer kan hantera vilka appar som kan komma åt [via sekretesspolicyer.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)</span><span class="sxs-lookup"><span data-stu-id="349fb-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="349fb-125">Mer information om vem som blir enhetsägare på en Azure AD-ansluten enhet finns i dokumentationen "Tilldela lokal administratör" (men läs "lokal [administratör"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) som "enhetsägare" eftersom administratören inte finns på HoloLens).</span><span class="sxs-lookup"><span data-stu-id="349fb-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>