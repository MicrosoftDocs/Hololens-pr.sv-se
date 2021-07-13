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
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640414"
---
# <a name="enroll-hololens-in-mdm"></a>Registrera HoloLens i MDM

Du kan hantera flera Microsoft HoloLens enheter samtidigt med hjälp av lösningar som [Microsoft Intune](/intune/windows-holographic-for-business). Du kommer att kunna hantera inställningar, välja appar för att installera och ange säkerhetskonfigurationer som skräddarsytts efter organisationens behov. Se Hantera enheter som [kör Windows Holographic med Microsoft Intune](/intune/windows-holographic-for-business), de konfigurationstjänstleverantörer [(CPS)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)som stöds i Windows Holographic och de principer som [stöds av Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Hantering av mobila enheter (MDM), inklusive VPN-, Bitlocker- och helskärmslägesfunktioner, är endast tillgängligt när du [uppgraderar till Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Krav

 Din organisation måste ha Mobile Enhetshantering (MDM) inställt för att kunna hantera HoloLens enheter. MDM-providern kan Microsoft Intune en tredjepartsprovider som använder Microsoft MDM-API:er.
 
## <a name="different-ways-to-enroll"></a>Olika sätt att registrera

Beroende på vilken typ av [identitet som](hololens-identity.md) valts under OOBE eller efter inloggningen finns det olika registreringsmetoder.

- Om Identity är Azure AD klickar du antingen på knappen INSTÄLLNINGAR **appåtkomst**  ->  **på arbetet eller**  ->  **Anslut** skolappen.
    - För Azure AD sker [automatisk MDM-registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) endast om Azure AD har konfigurerats med registrerings-URL:er.
     
- Om Identity är Azure AD och enheten har förregistrerats med Intune MDM-servern med en specifik tilldelad konfigurationsprofil sker Azure AD-Join och automatisk [MDM-registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) under OOBE.
    - Kallas även [Autopilot-flöde](hololens2-autopilot.md) tillgängligt [i versionerna 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Om Identity är MSA använder du Inställningar  ->  **appåtkomstknappen Arbete**  ->  **Anslut** School.
    - Kallas även för flödet Lägg till arbetskonto (AWA).
- Om Identity är Lokal användare använder du **Inställningar**  ->  **appåtkomst endast för Arbete eller Skola** Registrera endast i  ->  **enhetshanteringslänken.**
    - Kallas även för ett rent MDM-registreringsflöde.

När enheten har registrerats med MDM-servern återspeglar Inställningar nu att enheten har registrerats i enhetshanteringen.

## <a name="auto-enrollment-in-mdm"></a>Automatisk registrering i MDM

Om din organisation har en [Azure Premium-prenumeration](https://azure.microsoft.com/overview/), använder Azure Active Directory (Azure AD) och en MDM-lösning som accepterar en Azure AD-token för autentisering (för närvarande stöds endast i Microsoft Intune och AirWatch) kan IT-administratören konfigurera Azure AD att automatiskt tillåta MDM-registrering när användaren loggar in med sitt Azure AD-konto. [Lär dig hur du konfigurerar Azure AD-registrering.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

När automatisk registrering är aktiverat behövs ingen extra manuell registrering. När användaren loggar in med ett Azure AD-konto registreras enheten i MDM när du har slutfört den första körningen.

När en enhet är Azure AD-ansluten kan det påverka vem som anser att [enhetens ägare är](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Avregistrera HoloLens Intune

Beroende på registreringsmetoden kanske det inte går att avregistrera enheten.

Om enheten har registrerats med ett Azure AD-konto eller Autopilot kan den inte avregistreras från Intune. Om du vill ta bort HoloLens från Azure AD eller återansluta till en annan klientorganisation än Azure AD måste du [återställa/omsnedställa](hololens-recovery.md#reset-the-device) enheten.

Om enheten har registrerats från ett MSA-konto som har lagt till ett arbetskonto eller från ett lokalt konto som endast har registrerats i enhetshanteringen kan du avregistrera enheten. Öppna Start-menyn och välj sedan **knappen Inställningar App** Access Work (Åtkomst till  ->  **app) eller School**  ->  *YourAccount* Disconnect  ->  **(Ditt** konto för att koppla från).