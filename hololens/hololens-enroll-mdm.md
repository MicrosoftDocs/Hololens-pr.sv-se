---
title: Registrera HoloLens i MDM
description: Lär dig hur du registrerar HoloLens i hantering av mobila enheter (MDM) för enklare hantering av flera enheter.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f466abe45a1a9ad676f8dd6a94244473c084be7
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202887"
---
# <a name="enroll-hololens-in-mdm"></a>Registrera HoloLens i MDM

Du kan hantera flera Microsoft HoloLens enheter samtidigt med hjälp av lösningar som [Microsoft Intune](/intune/windows-holographic-for-business). Du kommer att kunna hantera inställningar, välja appar för att installera och ange säkerhetskonfigurationer som skräddarsytts efter organisationens behov. Se Hantera enheter som [kör Windows Holographic med Microsoft Intune](/intune/windows-holographic-for-business), de konfigurationstjänstleverantörer [(CPS)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)som stöds i Windows Holographic och de principer som [stöds av Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Hantering av mobila enheter (MDM), inklusive VPN-, BitLocker- och helskärmslägesfunktioner, är endast tillgängligt när du [uppgraderar till Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Krav

 Din organisation måste ha Mobile Enhetshantering (MDM) inställt för att kunna hantera HoloLens enheter. MDM-providern kan Microsoft Intune en tredjepartsprovider som använder Microsoft MDM-API:er.

## <a name="different-ways-to-enroll"></a>Olika sätt att registrera

Beroende på vilken typ av [identitet som](hololens-identity.md) valts under OOBE eller efter inloggningen finns det olika registreringsmetoder.

- Om Identity är Azure AD klickar du antingen på knappen OOBE **eller Inställningar App** Access  ->  **Work**  ->  **Anslut** School.
    - För Azure AD sker [automatisk MDM-registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) endast om Azure AD har konfigurerats med registrerings-URL:er.

- Om Identity är Azure AD och enheten har förregistrerats med Intune MDM-servern med en specifik tilldelad konfigurationsprofil sker Azure AD-Join och automatisk [MDM-registrering](hololens-enroll-mdm.md#auto-enrollment-in-mdm) under OOBE.
    - Kallas även [Autopilot-flöde](hololens2-autopilot.md) tillgängligt [i versionerna 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)


- Om Identity är MSA använder du knappen **Inställningar App** Access Work  ->  **eller School**  ->  **Anslut.**
    - Kallas även för flödet Lägg till arbetskonto (AWA).
- Om Identity är Lokal användare använder du **Inställningar App** Access Work eller School Enroll only in device management link (Registrera  ->    ->  **endast i enhetshantering).**
    - Kallas även för ett rent MDM-registreringsflöde.

När enheten har registrerats med MDM-servern återspeglar Inställningar nu att enheten har registrerats i enhetshanteringen.

## <a name="auto-enrollment-in-mdm"></a>Automatisk registrering i MDM

Om din organisation har en [Azure Premium-prenumeration](https://azure.microsoft.com/overview/), använder Azure Active Directory (Azure AD) och en MDM-lösning som accepterar en Azure AD-token för autentisering (för närvarande stöds endast i Microsoft Intune och AirWatch) kan IT-administratören konfigurera Azure AD att automatiskt tillåta MDM-registrering när användaren loggar in med sin Azure AD Konto. [Lär dig hur du konfigurerar Azure AD-registrering](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) [och Azure Active Directory-integrering med MDM](/windows/client-management/mdm/azure-active-directory-integration-with-mdm) för detaljerad bakgrundsinformation.

När automatisk registrering är aktiverat behövs ingen extra manuell registrering. När användaren loggar in med ett Azure AD-konto registreras enheten i MDM när du har slutfört den första körningen.

När en enhet är Azure AD-ansluten kan det påverka vem som anser att [enhetens ägare är](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Avregistrera HoloLens Intune

Beroende på registreringsmetoden kanske det inte går att avregistrera enheten.

Om enheten har registrerats med ett Azure AD-konto eller Autopilot kan den inte avregistreras från Intune. Om du vill ta bort HoloLens från Azure AD eller återansluta till en annan klientorganisation än Azure AD måste du [återställa/omsnedstrecka](hololens-recovery.md#restart-the-device) enheten.

Om enheten har registrerats från ett MSA-konto som har lagt till ett arbetskonto eller från ett lokalt konto som endast har registrerats i enhetshanteringen kan du avregistrera enheten. Öppna Start-menyn och välj sedan **knappen Inställningar App** Access Work (Åtkomst till  ->  **app) eller School**  ->  *YourAccount* Disconnect  ->  **(Ditt** konto för att koppla från).

## <a name="enrollment-troubleshooting"></a>Felsökning av registrering

### <a name="ensure-device-is-successfully-connected-to-internet-before-attempting-enrollment-post-oobe"></a>Kontrollera att enheten är ansluten till Internet innan du försöker registrera efter OOBE

När användaren har loggat in ser du till att det finns en Internetanslutning genom att bläddra till en internetuppriktad webbplats på enheten.

### <a name="ensure-that-azure-active-directory-aad-join-is-not-disabled-in-your-aad-tenant"></a>Kontrollera att Azure Active Directory (AAD) inte är inaktiverat i din AAD klient

Se Konfigurera [enhetsinställningarna för](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) information om de tillgängliga alternativen i Azure Portal.

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Kontrollera att användaren har tilldelats en giltig licens

Se Felsöka Windows problem med [enhetsregistreringen i Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) avsnitt, t.ex. Kontrollera begränsningar för enhetstyp och Tilldela en giltig licens till [användaren.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user) [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Kontrollera att MDM-registreringen inte blockeras för Windows enheter

För att registreringen ska lyckas måste du se till att dina HoloLens enheter kan registreras. Eftersom HoloLens betraktas som en Windows enhet behöver det inte finnas några registreringsbegränsningar som kan blockera distributionen. [Granska den här listan över](/mem/intune/enrollment/enrollment-restrictions-set) begränsningar och se till att du kan registrera dina enheter.
