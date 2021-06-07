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
# <a name="admin-less-operating-system"></a>Adminlös operativsystem

HoloLens 2 minimerar ytan för behörighetseskalering genom att inaktivera stöd för gruppen Administratörer och begränsa all UWP-programkod från tredje part till att endast köras som standardanvändare i sandbox-miljön AppContainer. Den här koden beviljas endast åtkomst till de resurser som skyddas av funktioner som uttryckligen visas i programmet för en icke-relevant användare, förutom resurser som är tillgängliga för alla AppContainers.
Dessa programfunktioner har fortfarande klassificeringsmodellen med tre nivåer:
  * Allmänt
  * Begränsade
  * Windows

Windows-komponenter kan också använda sandbox-miljön AppContainer via System UWPs. Mer information om Universell Windows-plattform (UWP) finns i [UWP-dokumentationen.](https://docs.microsoft.com/windows/uwp/) Dessutom använder Windows-komponenter med större behörighetsminskningsbehov (t.ex. sidor med webbläsarinnehåll eller parsare) sandbox-miljön Mindre privilegierad AppContainer (LPAC), vilket stänger av åtkomsten till den uppsättning resurser som är tillgänglig för alla AppContainers.

## <a name="device-owner"></a>Enhetens ägare

Slutligen tillåts endast "enhetsägare" att utföra specifika enhetsomfattande åtgärder, till exempel att ansluta enheten till en klient eller användarhantering. Den här gruppen fylls i av användare på enheten med något av följande steg:
  * Den första användaren på enheten är alltid ägare. 
> [!IMPORTANT]
>För Azure AD-användare är undantaget till den här regeln att om enheten är Azure AD-ansluten via Autopilot eller azure AD-massregistrering, som använder en icke-verklig användare. I det här fallet kanske den första AAD-användaren som loggar in på enheten inte blir enhetsägare automatiskt såvida inte användaren har rollen "global administratör" eller "enhetsadministratör" tilldelad i Azure Portal. Mer information finns i anteckningen nedan.  

  * När en användare upphöjs till ägare från inställnings-UX av en annan ägare på enheten.
  * Om enhetens ägare inte längre är tillgänglig (lämnar företaget) och enheten är Ansluten till Azure AD kan klientorganisationsadministratören ändra enhetens ägare till en ny användare i Azure Portal. Globala administratörer och enhetsadministratörer för en Azure AD-klientorganisation loggas implicit in som ägare på enheten utan att något av de föregående stegen krävs.  

 IT-administratörer kan hantera vilka appar som kan komma åt [via sekretesspolicyer.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Mer information om vem som blir enhetsägare på en Azure AD-ansluten enhet finns i dokumentationen "Tilldela lokal administratör" (men läs "lokal [administratör"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) som "enhetsägare" eftersom administratören inte finns på HoloLens).