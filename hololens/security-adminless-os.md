---
title: Säkerhet för adminlös operativsystem
description: Lär dig mer om operativsystem utan administratörer, enhetsägare och säkerhet på HoloLens enheter med mixad verklighet.
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
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428194"
---
# <a name="admin-less-operating-system"></a>Adminlös operativsystem

HoloLens 2 minimerar ytan för behörighetseskalering genom att inaktivera stöd för gruppen Administratörer och begränsa all UWP-programkod från tredje part till att endast köras som standardanvändare i sandbox-miljön appcontainer. Den här koden beviljas endast åtkomst till de resurser som skyddas av funktioner som uttryckligen visas i programmet för en icke-relevant användare, förutom resurser som är tillgängliga för alla AppContainers.
Dessa programfunktioner har fortfarande klassificeringsmodellen med tre nivåer:
  * Allmänt
  * Begränsade
  * Windows

Windows-komponenter kan också utnyttja appcontainer-sandbox-miljön via system-UWPs. Mer information om Universal Windows Platform (UWP) finns i [UWP-dokumentationen.](/windows/uwp/) Dessutom kan Windows-komponenter med större behörighetsminskningsbehov (t.ex. sidor med webbläsarinnehåll eller parserer) använda sandbox-miljön Mindre privilegierad AppContainer (LPAC), vilket minskar åtkomsten till uppsättningen resurser som är tillgängliga för alla AppContainers.

## <a name="device-owner"></a>Enhetens ägare

Slutligen tillåts endast "enhetsägare" att utföra specifika åtgärder för hela enheten, till exempel att ansluta enheten till en klient eller användarhantering. Den här gruppen fylls i av användare på enheten med något av följande steg:
  * Den första användaren på enheten är alltid ägare. 
> [!IMPORTANT]
>För Azure AD-användare är undantaget till den här regeln att om enheten är Azure AD-ansluten via Autopilot eller azure AD-massregistrering, som använder en icke-verklig användare. I det här fallet kanske den första AAD-användaren som loggar in på enheten inte blir enhetsägare automatiskt om inte användaren har rollen "global administratör" eller "enhetsadministratör" tilldelad i Azure Portal. Mer information finns i anteckningen nedan.  

  * När en användare upphöjs till ägare från Inställningar UX av en annan ägare på enheten.
  * Om enhetens ägare inte längre är tillgänglig (lämnar företaget) och enheten är Ansluten till Azure AD kan klientorganisationsadministratören ändra enhetens ägare till en ny användare i Azure Portal. Globala administratörer och enhetsadministratörer för en Azure AD-klientorganisation loggas implicit in som ägare på enheten utan att något av de föregående stegen krävs.  

 IT-administratörer kan hantera vilka appar som kan komma åt [via sekretesspolicyer.](/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Mer information om vem som blir enhetsägare på en Azure AD-ansluten enhet finns i dokumentationen "Tilldela lokal administratör" (men läs "lokal [administratör"](/azure/active-directory/devices/assign-local-admin) som "enhetsägare" eftersom administratören inte finns på HoloLens).