---
title: Windows Autopilot-registreringssupport för HoloLens 2
description: Lär dig hur du får registreringssupport för Autopilot på HoloLens 2 enheter.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036491"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Registreringssupport för Autopilot

Kunder och Microsoft Cloud Solution Providers (CPS) kan nu registrera HoloLens 2 enheter genom att skicka begäranden direkt till Microsoft Support. Den här sidan beskriver kraven för följande autopilotregistreringsscenarier som stöds:

- **HoloLens 2-enhetens Autopilot-registrering.** Skickar begäran om att registrera HoloLens 2 enheter till Windows Autopilot.
- **HoloLens 2 Device Hardware Hash Request**. Skickar begäran till Microsoft Support för att förse dig med maskinvaruhash-värden som kunder eller molnleverantörer kan använda för att självregistrera enheter via Microsoft Intune eller Microsoft Partner Center.
- **HoloLens 2 Autopilot-avregistrering av enhet.** Skickar en begäran om att ta bort enheter Windows Autopilot, som vanligtvis används i scenarier med enhetens slut.

Följande tabell innehåller den information som du behöver samla in *innan du* skickar registreringsbegäranden till Microsoft Support.

| Nödvändig information | Description | Autopilot-registrering  | Begäran om maskinvaru-hash | Autopilot-avregistrering |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Klientorganisations-ID    |    Ditt Azure Active Directory-ID är en globalt unik identifierare (GUID) som skiljer sig från ditt organisationsnamn eller domän.    För att hitta ditt klientorganisations-ID loggar du in [på Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Domännamn    |   Ditt domännamn på den översta nivån; till exempel contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Bevis på ägarskap    |   Verifiera ägarbeviset genom att ladda upp den ursprungliga försäljningsfakturan eller fakturan i PDF-format. Skärmbilder accepteras inte. Fakturan eller fakturan måste innehålla följande: Enhetsserienummer. Företagsnamn.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Enhetsserienummer    |   Upload Excel i CSV-format med varje enhets serienummer på en ny rad.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Skicka supportbegäranden

> [!div class="nextstepaction"]
> [Skicka autopilotregistreringsstöd för HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
