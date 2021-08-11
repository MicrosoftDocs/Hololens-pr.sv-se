---
title: Sidsynlighet Inställningar sida
description: Håll dig uppdaterad med vår lista över URI:er som stöds för PageVisibilityList och Guide på HoloLens enheter med mixad verklighet.
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
ms.openlocfilehash: d2747da37ae198f7a2c051593da3ffd4cb4476dfaa7a3078a7749fa1fc912ba2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665632"
---
# <a name="page-settings-visibility"></a>Sidsynlighet Inställningar sida

En av de hanterbara funktionerna för HoloLens-enheter använder [principen Inställningar/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) för att begränsa de sidor som visas i Inställningar appen. PageVisibilityList är en princip som gör det möjligt för IT-administratörer att antingen förhindra att specifika sidor i System Inställningar-appen visas eller är tillgängliga, eller att göra det för alla sidor utom de som anges.

> [!NOTE]
> Den här funktionen är endast tillgänglig i [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) eller senare för HoloLens 2 enheter. Se till att de enheter som du tänker använda detta för uppdateras.


## <a name="examples"></a>Exempel
Sidor identifieras med en förkortad version av de publicerade URI:erna, vilket är URI minus prefixet "ms-settings:".

I följande exempel visas en princip som endast tillåter åtkomst till about- och bluetooth-sidor, som har URI:en "network-wifi" respektive "bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

I följande exempel visas en princip som skulle dölja sidan Återställning av operativsystem:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Distribuera den här principen via Intune

Det här är de konfigurationsvärden som ska anges för Intune:

- **Namn:** Ett administratörsnamn för profilen.
- **OMA-URI:** Den fullständigt kvalificerade URI:en för inställningssidan, inklusive dess [omfång](/windows/client-management/mdm/policy-configuration-service-provider). Det här exemplet på den här sidan använder `./Device` omfånget.
- **Värde:** Ett strängvärde som anger om du vill dölja eller endast *visa* de angivna sidorna. Möjliga värden är `hide:<pagename>` och `showonly:<pagename>` . 
 
Flera sidor kan anges genom att avgränsa dem med semikolon, och en lista över vanliga sidor finns nedan.

1. Skapa en **anpassad princip.**
1. När du ställer in **OMA-URI anger** du den fullständigt begränsade URI:en. Till exempel: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. När du väljer dataväljer du: **Sträng**
1. Använd **vägledningen ovan** när du anger Värde. Till exempel: **`showonly:network-wifi;network-proxy;bluetooth`** eller **`hide:reset`** 
> [!IMPORTANT]
> Se till att tilldela den anpassade enhetskonfigurationen till en grupp som enheten är avsedd att finnas i. Om det här steget inte utförs push-skickas principen men tillämpas inte.

Se [HoloLens MDM-konfiguration](hololens-mdm-configure.md) för mer information om Intune-grupper och enhetskonfigurationer.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Distribuera den här principen via ett etableringspaket

Det här är de konfigurationsvärden som anges i Windows Configuration Designer:

**Värde:** Ett strängvärde som anger om du vill dölja eller endast *visa* de angivna sidorna. Möjliga värden är `hide:<pagename>` och `showonly:<pagename>` . Flera sidor kan anges genom att avgränsa dem med semikolon, och en lista över vanliga sidor finns nedan.


1. När du skapar paketet i Windows Configuration Designer går du till **Principer > Inställningar > PageVisibilityList**
1. Ange strängen: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportera ditt etableringspaket.
1. Tillämpa paketet på enheten.
Fullständig information om hur du skapar och tillämpar ett etableringspaket finns [på HoloLens för etablering.](hololens-provisioning.md)


Oavsett vilken metod som valts bör din enhet nu ta emot ändringarna och användarna kommer att se följande Inställningar app.

![Skärmbild av aktiva timmar som ändras i Inställningar appen](images/hololens-page-visibility-list.jpg)

Om du vill konfigurera Inställningar-appsidorna så att de visar eller döljer dina egna val av sidor kan du ta en titt på de Inställningar URI:er som finns HoloLens.

## <a name="settings-uris"></a>Inställningar Uris

HoloLens enheter Windows 10 enheter har ett annat urval av sidor i Inställningar appen. På den här sidan hittar du bara de inställningar som finns på HoloLens.

### <a name="accounts"></a>Konton
| Sidan Inställningar           | URI                                            |
|-------------------------|------------------------------------------------|
| Åtkomst till arbete eller skola | `workplace`                         |
| Iris-registrering       | `signinoptions-launchirisenrollment` |
| Inloggningsalternativ         | ` signinoptions `                   |

### <a name="apps"></a>Appar
| Sidan Inställningar | URI                          |
|---------------|------------------------------|
| Appar & funktioner <sup>2</sup>     | `appsfeatures` <br> |
| Appar & funktioner > Avancerade alternativ <sup>2</sup>     | `appsfeatures-app` <br> |
| Appar & funktioner > Offline Kartor <sup>2</sup>     | `maps-maps` <br> |
| Appar & funktioner > Offline Kartor > Hämta kartor <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Enheter
| Sidan Inställningar | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Mus <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Sekretess
| Sidan Inställningar            | URI                                             |
|--------------------------|-------------------------------------------------|
| Kontoinformation             | `privacy-accountinfo`              |
| Appdiagnostik        | `privacy-appdiagnostics`              |
| Bakgrundsappar        | `privacy-backgroundapps`              |
| Kalender                 | `privacy-calendar`                    |
| Samtalshistorik             | `privacy-callhistory`                 |
| Kamera                   | `privacy-webcam`                      |
| Kontakter                 | `privacy-contacts`                    |
| Feedback & diagnostik | `privacy-feedback`                    |
| Dokument                | `privacy-documents`                   |
| E-post                    | `privacy-email`                       |
| Filsystem              | `privacy-broadfilesystemaccess`       |
| Allmänt <sup>2</sup>             | `privacy-general`       |
| Ink & skriva anpassning <sup>2</sup>             | `privacy-speechtyping`       |
| Location                 | `privacy-location`                    |
| Meddelandetjänster                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Rörelse <sup>2</sup>               | `privacy-motion`                  |
| Meddelanden            | `privacy-notifications`               |
| Andra enheter            | `privacy-customdevices`               |
| Bilder                 | `privacy-pictures`                    |
| Radioapparater                   | `privacy-radios`                      |
| Skärmbild av <sup>kantlinjer 2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Skärmbilder och appar <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `privacy-speech`                      |
| Uppgifter                    | `privacy-tasks`                       |
| Användarförflyttningar           | `privacy-backgroundspatialperception` |
| Video                   | `privacy-videos`                      |
| Röstaktivering       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Nätverk och Internet
| Sidan Inställningar | URI                              |
|---------------|----------------------------------|
| Flygplansläge <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>System
| Sidan Inställningar      | URI                                |
|--------------------|------------------------------------|
| Batteri <sup>2</sup>           | `batterysaver`<br>|
| Batteri <sup>2</sup>           | `batterysaver-settings`<br>|
| Färger             | `colors`<br>`personalization-colors` |
| Hologram <sup>2</sup>  |  `holograms`  |
| Kalibrering <sup>2</sup> |  `calibration` |
| Meddelanden & åtgärder  | `notifications`          |
| Delade upplevelser | `crossdevice` 
| Ljud <sup>2</sup>           | `sound`<br>|
| Ljud> appvolym och enhetspreferens <sup>2</sup>           | `apps-volume`<br>|
| Ljud > Hantera ljudenheter <sup>2</sup>           | `sound-devices`<br>|
| Storage            | `storagesense`           |
| Storage > Configure Storage Sense <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Tid & språk
| Sidan Inställningar | URI                                           |
|---------------|-----------------------------------------------|
| Datum & tid <sup>2</sup> | `dateandtime`                  |
| Tangentbord <sup>2</sup> | `keyboard`                  |
| Språk <sup>2</sup> | `language`                  |
| Språk <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Språk      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Uppdatera & security
| Sidan Inställningar                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Avancerade alternativ                    | `windowsupdate-options`         |
| Återställa & Recovery <sup>2</sup>      | `reset`         |
| Windows Insider Program               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Uppdatera – Söker efter uppdateringar | `windowsupdate-action`          |


- <sup>1</sup> – För versioner före Windows Holographic version 21H1 tar inte följande två  URI:er dig till sidorna Avancerade alternativ **eller** Alternativ. De blockerar eller visar bara huvudsidan Windows Uppdatering.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> – Tillgängligt i Windows Holographic 21H1 eller senare.


En fullständig lista över URI Windows 10 Inställningar finns i dokumentationen om [startinställningar.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
