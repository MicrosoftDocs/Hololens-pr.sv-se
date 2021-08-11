---
title: Certifikathanteraren
description: Lär dig hur du installerar, hanterar och tar bort certifikat manuellt på HoloLens 2 enheter med mixad verklighet.
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
ms.openlocfilehash: 438a132a6bafd8c93b148b9c2c817ec93cc3bc73651f08275acc130695fa09c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665190"
---
# <a name="certificate-manager"></a>Certifikathanteraren

- Förbättrad gransknings-, diagnostik- och valideringsverktyg för enhetssäkerhet och efterlevnad via den nya certifikathanteraren. Med den här funktionen kan du distribuera, felsöka och validera dina certifikat i stor skala i kommersiella miljöer.

I Windows Holographic version 20H2 lägger vi till en Certifikathanterare i HoloLens 2 Inställningar appen. Gå till **Inställningar > Update & Security > Certificates**. Den här funktionen ger ett enkelt och användarvänligt sätt att visa, installera och ta bort certifikat på enheten. Med den nya Certifikathanteraren har administratörer och användare nu förbättrat gransknings-, diagnos- och valideringsverktygen för att säkerställa att enheterna förblir säkra och kompatibla. 

-   **Granskning:** Möjlighet att verifiera att ett certifikat har distribuerats korrekt eller att bekräfta att det har tagits bort på rätt sätt. 
-   **Diagnos:** När problem uppstår kan det spara tid och hjälpa till med felsökningen att verifiera att rätt certifikat finns på enheten. 
-   **Validering:** Att verifiera att ett certifikat har det avsedda syftet och är funktionellt kan spara mycket tid, särskilt i kommersiella miljöer innan certifikat distribueras i större skala.

Om du snabbt vill hitta ett specifikt certifikat i listan finns det alternativ för att sortera efter namn, arkiv eller förfallodatum. Användare kan också söka efter ett certifikat direkt. Om du vill visa enskilda certifikategenskaper väljer du certifikatet och klickar på **Info**. 

Certifikatinstallationen stöder för närvarande .cer- och .crt-filer. Enhetsägare kan installera certifikat på den lokala datorn och den aktuella användaren.  alla andra användare kan bara installera i aktuell användare.

## <a name="to-install-a-certificate"></a>Så här installerar du ett certifikat: 

1.  Anslut din HoloLens 2 till en dator.
1.  Placera den certifikatfil som du vill installera på en plats på din HoloLens 2.
1.  Gå till **Inställningar App > Update & Security > Certificates** och välj Installera ett certifikat.
1.  Klicka **på Importera** fil och navigera till den plats där du sparade certifikatet.
1.  Välj **Butiksplats.**
1.  Välj **Certifikatarkiv.**
1.  Klicka på **Installera**.

Certifikatet bör nu installeras på enheten.

![Certifikatvisare i Inställningar under Certifikat.](images/certificate-viewer-device.jpg)

![Bild som visar hur du använder användargränssnittet för certifikat för att installera ett certifikat Inställningar.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Så här tar du bort ett certifikat:

> [!WARNING]
> Med Hjälp av Certificate Manager kan användarna bara ta bort certifikat som installerats direkt Inställningar användargränssnittet. Om ett certifikat har installerats på annat sätt måste det också tas bort av samma mekanism och kan inte tas bort från Certifikathanteraren. Du kan visa MDM-distribuerade certifikat i Certifikathanteraren, men du kan inte avinstallera dem i Certificate Manager. Du måste avinstallera dem via MDM.

1. Gå till **Inställningar App > Update and Security > Certificates**.
1. Sök efter certifikatet efter namn i sökrutan.
1. Välj certifikatet.
1. Klicka på **Ta bort**
1. Välj **Ja när** du uppmanas att bekräfta.

