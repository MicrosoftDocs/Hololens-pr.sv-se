---
title: HoloLens information om helskärmsläge
description: Information och exempel för kiosker på HoloLens enheter.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863959"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Referensinformation för helskärmsläge

Den här sidan innehåller användbar information för att konfigurera HoloLens enhetens helskärmsläge. Dessa referenser omfattar AUMID:er för inkorgsappar och hitta dina, och flera XML-exempel för helskärmsläge, som bara är några redigeringar från att vara redo att användas för flera olika scenarier. Information om hur du ställer in en helskärmsläge finns på [sidan Konfigurera en helskärm.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Programanvändarmodell-ID:n (AUMID:er)  

Allmän information om hur du väljer helskärmsappar finns i [Riktlinjer för att välja en app för tilldelad åtkomst (helskärmsläge).](/windows/configuration/guidelines-for-assigned-access-app)

Om du använder ett MDM-system (Mobile Enhetshantering) eller ett etableringspaket för att konfigurera helskärmsläge använder du [CSP (AssignedAccess Configuration Service Provider)](/windows/client-management/mdm/assignedaccess-csp) för att ange program. CSP:n [använder PROGRAManvändarmodell-ID:n (AUMID) för](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) att identifiera program. I följande tabell visas AUMID:er för vissa in-box-program som du kan använda i en helskärmsläge för flera appar.

<a id="aumids"></a>

|Appnamn |AUMID |
| --- | --- |
|3D-visningsprogram |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Enhetsväljare på HoloLens (första generationen) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Enhetsväljare på HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365-guider |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Fjärrhjälp för Dynamics 365 |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|&nbsp;Feedbackhubb |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Utforskaren |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|E-post |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Gamla Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Ny Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
|Filmer & TV |Microsoft.Video \_ 8wekyb3d8bbwe \! Microsoft.Video |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Foton |Microsoft. Windows. \_Photos 8wekyb3d8bbwe \! App |
|Gamla Inställningar |HolographicSystemSettings_cw5n1h2txyewy! App |
|Ny Inställningar |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tips |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Om du vill aktivera foto- eller videoinspelning måste du aktivera kameraappen som en kioskapp.  
> <sup>2</sup> Tänk på följande när du aktiverar kameraappen:
> - Snabbåtgärder-menyn innehåller knapparna Foto och Video.
> - Du bör också aktivera en app (till exempel Photos, e-post eller OneDrive) som kan interagera med eller hämta bilder.  
>  
> <sup>3</sup> Även om du inte aktiverar Cortana som en kioskapp aktiveras inbyggda röstkommandon. Kommandon som är relaterade till inaktiverade funktioner har dock ingen effekt.  
> <sup>4</sup> Du kan inte aktivera Miracast direkt. Om du Miracast som en helskärmsapp aktiverar du appen Kamera och appen Enhetsväljare.

Dessutom kan Mixed Reality start inte anges som en kioskapp.

Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>XML-kodexempel för helskärmsläge

1. [Global tilldelad åtkomstprofil för flera appar](#multiple-app-global-assigned-access-profile)
1. [Flera globala app-tilldelade åtkomstprofiler exklusive enhetsägare](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Flera app-tilldelade åtkomstprofiler för ett lokalt konto eller ett AAD-användarkonto](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Flera app-tilldelade åtkomstprofiler för två AAD-användare eller fler](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Flera app-tilldelade åtkomstprofiler för en AAD-grupp](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Flera app-tilldelade åtkomstprofiler för två AAD-grupper eller fler](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Flera app-tilldelade åtkomstprofiler för ett AAD-konto och en AAD-grupp](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Flera app-tilldelade åtkomstprofiler för besökare](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Ersätt TODO-åtgärder enligt dina behov.

### <a name="multiple-app-global-assigned-access-profile"></a>Global tilldelad åtkomstprofil för flera appar

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Flera globala app-tilldelade åtkomstprofiler exklusive enhetsägare

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Flera app-tilldelade åtkomstprofiler för ett lokalt konto eller ett AAD-användarkonto

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Flera app-tilldelade åtkomstprofiler för två AAD-användare eller fler

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Flera app-tilldelade åtkomstprofiler för en AAD-grupp

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Flera app-tilldelade åtkomstprofiler för två AAD-grupper eller fler

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Flera app-tilldelade åtkomstprofiler för ett AAD-konto och en AAD-grupp

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Flera app-tilldelade åtkomstprofiler för besökare

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Tillbaka till listan](#kiosk-xml-code-samples) <br>
Återgå till [scenarier som stöds för helskärmsläge baserat på identitetstyp](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
