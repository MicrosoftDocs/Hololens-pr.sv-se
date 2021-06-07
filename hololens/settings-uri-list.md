---
title: Synlighet för sidinställningar
description: Håll dig uppdaterad med vår lista över URI:er som stöds för PageVisibilityList och Guide på HoloLens-enheter med mixad verklighet.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, tilldelad åtkomst, kiosk, inställningssida
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380053"
---
# <a name="page-settings-visibility"></a>Synlighet för sidinställningar

En av de hanterbara funktionerna för HoloLens-enheter är att använda principen [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) för att begränsa de sidor som visas i appen Inställningar. PageVisibilityList är en princip som gör det möjligt för IT-administratörer att antingen förhindra att specifika sidor i appen Systeminställningar visas eller är tillgängliga, eller att göra det för alla sidor utom de som anges.

> [!NOTE]
> Den här funktionen är endast tillgänglig i [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) eller senare för HoloLens 2-enheter. Se till att de enheter som du tänker använda detta för uppdateras.

I följande exempel visas en princip som endast tillåter åtkomst till about- och bluetooth-sidor, som har URI:en "ms-settings:network-wifi" respektive "ms-settings:bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

Så här ställer du in detta via ett etableringspaket:

1. När du skapar paketet i Windows Configuration Designer går du till **Principer > inställningar > PageVisibilityList**
1. Ange strängen: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportera ditt etableringspaket.
1. Tillämpa paketet på enheten.
Fullständig information om hur du skapar och tillämpar ett etableringspaket finns på den [här sidan.](hololens-provisioning.md)

Detta kan göras via Intune med OMA-URI:

1. Skapa en **anpassad princip.**
1. Använd strängen när du anger OMA-URI: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. När du väljer dataväljer du: **Sträng**
1. När du skriver värdet använder du: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Se till att tilldela den anpassade enhetskonfigurationen till en grupp som enheten är avsedd att finnas i.

Mer information [om Intune-grupper och](hololens-mdm-configure.md) enhetskonfigurationer finns i HoloLens MDM-konfiguration.

Oavsett vilken metod som valts bör enheten nu ta emot ändringarna och användarna kommer att se följande inställningsapp.

![Skärmbild av aktiva timmar som ändras i appen Inställningar](images/hololens-page-visibility-list.jpg)

Om du vill konfigurera inställningsappsidorna så att de visar eller döljer dina egna val av sidor kan du ta en titt på inställnings-URI:er som är tillgängliga på HoloLens.

## <a name="settings-uris"></a>URI:er för inställningar

HoloLens-enheter Windows 10 enheter har ett annat urval av sidor i appen Inställningar. På den här sidan hittar du bara de inställningar som finns på HoloLens.

### <a name="accounts"></a>Konton
| Sidan Inställningar           | URI                                            |
|-------------------------|------------------------------------------------|
| Åtkomst till arbete eller skola | `ms-settings:workplace`                         |
| Iris-registrering       | `ms-settings:signinoptions-launchirisenrollment` |
| Inloggningsalternativ         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Appar
| Sidan Inställningar | URI                          |
|---------------|------------------------------|
| Appar & funktioner<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Appar & funktioner > Avancerade alternativ <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Appar & funktioner > Offline Maps <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Appar & funktioner > offlinekartor > Hämta kartor <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Enheter
| Sidan Inställningar | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Mus <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Sekretess
| Sidan Inställningar            | URI                                             |
|--------------------------|-------------------------------------------------|
| Kontoinformation             | `ms-settings:privacy-accountinfo`              |
| Appdiagnostik        | `ms-settings:privacy-appdiagnostics`              |
| Bakgrundsappar        | `ms-settings:privacy-backgroundapps`              |
| Kalender                 | `ms-settings:privacy-calendar`                    |
| Samtalshistorik             | `ms-settings:privacy-callhistory`                 |
| Kamera                   | `ms-settings:privacy-webcam`                      |
| Kontakter                 | `ms-settings:privacy-contacts`                    |
| Feedback & diagnostik | `ms-settings:privacy-feedback`                    |
| Dokument                | `ms-settings:privacy-documents`                   |
| E-post                    | `ms-settings:privacy-email`                       |
| Filsystem              | `ms-settings:privacy-broadfilesystemaccess`       |
| Allmänt <sup>2</sup>             | `ms-settings:privacy-general`       |
| Ink & skriva anpassning <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Location                 | `ms-settings:privacy-location`                    |
| Meddelandefunktion                | `ms-settings:privacy-messaging`                   |
| Mikrofon               | `ms-settings:privacy-microphone`                  |
| Rörelse <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Meddelanden            | `ms-settings:privacy-notifications`               |
| Andra enheter            | `ms-settings:privacy-customdevices`               |
| Bilder                 | `ms-settings:privacy-pictures`                    |
| Radioapparater                   | `ms-settings:privacy-radios`                      |
| Skärmbild av <sup>kantlinjer 2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Skärmbilder och appar <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `ms-settings:privacy-speech`                      |
| Uppgifter                    | `ms-settings:privacy-tasks`                       |
| Användarförflyttningar           | `ms-settings:privacy-backgroundspatialperception` |
| Video                   | `ms-settings:privacy-videos`                      |
| Röstaktivering       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Nätverk och Internet
| Sidan Inställningar | URI                              |
|---------------|----------------------------------|
| Flygplansläge <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>System
| Sidan Inställningar      | URI                                |
|--------------------|------------------------------------|
| Batteri <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Batteri <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Färger             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologram <sup>2</sup>  |  `ms-settings:holograms`  |
| Kalibrering <sup>2</sup> |  `ms-settings:calibration` |
| Meddelanden & åtgärder  | `ms-settings:notifications`          |
| Delade upplevelser | `ms-settings:crossdevice` 
| Ljud <sup>2</sup>           | `ms-settings:sound`<br>|
| Ljud> appvolym och enhetspreferens <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Ljud > Hantera ljudenheter <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Storage            | `ms-settings:storagesense`           |
| Storage > Configue Storage Sense <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Tids & språk
| Sidan Inställningar | URI                                           |
|---------------|-----------------------------------------------|
| Datum & tid <sup>2</sup> | `ms-settings:dateandtime`                  |
| Tangentbord <sup>2</sup> | `ms-settings:keyboard`                  |
| Språk <sup>2</sup> | `ms-settings:language`                  |
| Språk <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Språk      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Uppdatera & Security
| Sidan Inställningar                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Avancerade alternativ                    | `ms-settings:windowsupdate-options`         |
| Återställa & Recovery <sup>2</sup>      | `ms-settings:reset`         |
| Windows Insider Program               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update – Söker efter uppdateringar | `ms-settings:windowsupdate-action`          |


>  <sup>1</sup> För versioner före Windows Holographic version 21H1 tar följande två URI:er inte dig till sidorna Avancerade alternativ **eller** Alternativ.  De blockerar eller visar bara huvudsidan Windows Update sidan.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions
 
> <sup>2</sup> – Tillgängligt i Windows Holographic 21H1 eller senare.


En fullständig lista över URI Windows 10 inställningar finns i dokumentationen om [startinställningar.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
