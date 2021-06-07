---
title: Windows Defender programkontroll – WDAC
description: Översikt över vad Windows Defender Application Control är och hur du använder det för att hantera HoloLens-enheter med mixad verklighet.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378796"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender programkontroll – WDAC

WDAC gör det möjligt för IT-administratörer att konfigurera sina enheter för att blockera start av appar på enheter. Detta skiljer sig från metoder för enhetsbegränsning, till exempel helskärmsläge, där användaren får ett användargränssnitt som döljer apparna på enheten, men de kan fortfarande startas. Medan WDAC implementeras visas apparna fortfarande i listan Alla appar, men WDAC hindrar dessa appar och processer från att kunna startas av enhetsanvändaren.

En enhet kan tilldelas mer än en WDAC-princip. Om flera WDAC-principer har angetts i ett system gäller de mest restriktiva. 

> [!NOTE]
> När slutanvändarna försöker starta en app som blockeras av WDAC får de på HoloLens inget meddelande om att de inte kan starta appen.

Följande är en guide för användare som lär sig hur de använder WDAC och Windows PowerShell för att tillåta eller blockera appar på [HoloLens 2-enheter med Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

När användare söker efter appar som Windows 10 på sin dator med hjälp av det första exempelsteget kan de behöva göra några försök att begränsa resultaten.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Om du inte känner till det fullständiga namnet på paketet kan du behöva köra Get-AppxPackage -name \* YourBestGuess några gånger \* för att hitta det. När du har fått namnet kör du sedan "$package 1 = Get-AppxPackage -name Actual.PackageName"

Om du till exempel kör följande för Microsoft Edge returneras fler än ett resultat, men i listan kan du se att det fullständiga namn du behöver är Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Paketfamiljenamn för appar på HoloLens

I den guide som länkas ovan kan du manuellt redigera newPolicy.xml lägga till regler för program som endast är installerade på HoloLens med deras paketfamiljenamn. Ibland kan det finnas appar som du kan använda som inte finns på den stationära dator som du vill lägga till i principen.

Här är en lista över vanliga och In-Box för HoloLens 2-enheter.

| Appnamn                   | Paketfamiljenamn                                |
|----------------------------|----------------------------------------------------|
| 3D-visningsprogram                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Appinstallationsprogram              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalender                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Kamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365-guider        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Fjärrhjälp för Dynamics 365 | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Feedbackhubben               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Utforskaren              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| E-post                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmer & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Foton                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Inställningar                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tips                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – Appinstallationsprogram blockerar endast Appinstallationsprogram appen och inte appar som har installerats från andra källor, till exempel Microsoft Store eller från din MDM-lösning.

### <a name="how-to-find-a-package-family-name"></a>Hitta ett paketfamiljenamn

Om en app inte finns med i listan kan en användare använda Enhetsportalen, ansluten till en HoloLens 2 som har installerat appen som vill blockeras, för att fastställa PackageRelativeID och därifrån hämta PackageFamilyName.

1. Installera appen på din HoloLens 2-enhet. 
1. Öppna Inställningar -> Uppdateringar & Security -> För utvecklare, aktivera **Utvecklarläge** och sedan **Enhetsportal.** 
    1. Mer information om instruktioner finns i konfigurera [och använda enhetsportalen här.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. När Enhetsportalen är ansluten går du till **Vyer** och sedan **Appar.** 
1. I panelen Installerade appar använder du listrutan för att välja den installerade appen. 
1. Leta upp PackageRelativeID. 
1. Kopiera apptecken före !. Dessa tecken blir PackageFamilyName.


