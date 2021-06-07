---
title: Vanliga scenarier – Säker HoloLens 2 offline
description: Lär dig hur du ställer in ett scenario för säker distribution offline och appdistribution med etablering för HoloLens-enheter.
keywords: HoloLens, management, offline, offline secure
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378724"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Vanliga scenarier – Säker HoloLens 2 offline

## <a name="overview"></a>Översikt

Den här guiden innehåller vägledning för att tillämpa ett exempel på etableringspaket som låser en HoloLens 2 för användning i säkra miljöer med följande begränsningar:

-   Inaktivera WiFi.
-   Inaktivera BlueTooth.
-   Inaktivera mikrofoner.
-   Förhindrar tillägg eller borttagning av etableringspaket.
-   Ingen användare kan aktivera någon av ovanstående begränsade komponenter.

[![Scenario för offline-säkerhet ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Förbereda

Windows 10 datorinstallation
1. [Ladda ned den senaste HoloLens 2 OS-filen](https://aka.ms/hololens2download) direkt till en dator. 
   1. Stöd för den här konfigurationen ingår i Build 19041.1117 och högre.
1. Ladda ned/installera arc-verktyget (Advanced Recovery Companion) [från Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) till datorn
1. Ladda ned/installera det [senaste WCD-verktyget (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) från Microsoft Store till datorn.
1. [Ladda ned OfflineSecureHL2_Sample mappen med projektfilerna för](https://aka.ms/HoloLensDocs-SecureOfflineSample) att skapa PPKG.
1. Förbered ditt [verksamhets offlineprogram för PPKG-distribution.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Konfigurera

Skapa ett paket för säker konfigurationsetablering

1. Starta WCD-verktyget på datorn.
1. Välj File -> Open project (Arkiv **-> Open project).**
  1. Navigera till platsen för den tidigare sparade OfflineSecureHL2_Sample mapp och välj: OfflineSecureHL2_Sample.icdproj.xml
1. Projektet bör öppnas och du bör nu ha en lista över tillgängliga anpassningar:

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av konfigurationspaketet som är öppet i WCD](images/offline-secure-sample-wcd.png)

   Konfigurationer som anges i det här konfigurationspaketet:
   
   |     Objekt                                                |     Inställning                       |     Beskrivning                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Konton/användare                                    |     Lokalt användarnamn och & lösenord    |     För dessa offlineenheter måste ett enda användarnamn och lösenord anges och delas av alla användare av enheten.          |
   |     First Experience/HoloLens/SkipCalibration       |     Sant                          |     Hoppar över kalibrering endast under den första enhetskonfigurationen                                                                             |
   |     First Experience/HoloLens/SkipTraining          |     Sant                          |     Hoppar över enhetsträning under den inledande enhetskonfigurationen                                                                              |
   |     Första upplevelsen/HoloLens/WiFi                  |     Sant                          |     Hoppar Wi-Fi konfigurationen under den inledande enhetskonfigurationen                                                                                 |
   |     Principer/Anslutning/AllowBluetooth                |     Inga                            |     Inaktiverar Bluetooth                                                                                                             |
   |     Principer/erfarenhet/AllowCortana                    |     Inga                            |     Inaktiverar Cortana (för att eliminera potentiella problem eftersom mikrofonerna är inaktiverade)                                          |
   |     Principer/MixedReality/MicrophoneDisabled            |     Ja                           |     Inaktiverar mikrofon                                                                                                            |
   |     Principer/Sekretess/LetAppsAccessLocation              |     Framtrigt neka                    |     Förhindrar att appar försöker komma åt platsdata (för att eliminera potentiella problem eftersom Platsspårning är inaktiverat)    |
   |     Principer/Sekretess/LetAppsAccessMicrophone            |     Framtrigt neka                    |     Förhindrar att appar försöker komma åt mikrofoner (för att eliminera potentiella problem eftersom mikrofonerna är inaktiverade)           |
   |     Principer/Säkerhet/AllowAddProvisioningPackage       |     Inga                            |     Förhindrar att alla lägger till etableringspaket som kan försöka åsidosätta låsta principer.                         |
   |     Principer/Säkerhet/AllowRemoveProvisioningPackage    |     Inga                            |     Förhindrar att någon tar bort det låsta etableringspaketet.                                                           |
   |     Principer/System/AllowLocation                       |     Inga                            |     Förhindrar att enheten försöker spåra platsdata.                                                                        |
   |     Principer/WiFi/AllowWiFi                             |     Inga                            |     Inaktiverar Wi-Fi                                                                                                                 |

1. Under Körningsinställningar väljer du **Konton/Användare/Användarnamn: Holo/Lösenord.**

   Anteckna lösenordet och återställ om du vill.

1. Gå till UniversalAppInstall/UserContextApp och [konfigurera den LOB-app](app-deploy-provisioning-package.md) som du ska distribuera till dessa enheter.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av var du lägger till din app i WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. När du är klar väljer du knappen "Exportera" och följer alla uppmaningar tills ditt etableringspaket har skapats.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av knappen Exportera för det här paketet i WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Distribuera

1. Anslut HL2 till din Windows 10 via USB-kabel.
1. Starta ARC-verktyget och välj **HoloLens 2**

   ![HoloLens 2 , inledande skärm med rent omstreck](images/ARC2.png)

1. På nästa skärm väljer du **Manuellt paketval.**

   ![HoloLens 2 ARC-informationsskärmen](images/arc_device_info.png)

1. Gå till den tidigare nedladdade .ffu-filen och välj **Öppna**.
1. På sidan Varning väljer du **Fortsätt.**

   ![HoloLens 2 ARC-varningsskärm](images/arc_warning.png)

1. Vänta tills ARC-verktyget har slutfört HoloLens 2 OS-installationen.
1. När enheten har slutfört installationen och startar igen går du från datorn till Utforskaren och kopierar den tidigare sparade PPKG-filen till enhetsmappen.

   > [!div class="mx-imgBorder"]
   > ![PPKG-fil på datorn i Utforskaren fönster.](images/offline-secure-file-explorer.png)

1. På HoloLens 2 trycker du på följande knappkombination för  att köra etableringspaketet: Tryck på Volym ned och **Strömknapp** på samma gång.
1. Du uppmanas att tillämpa etableringspaketet och välja **Bekräfta**
1. När etableringspaketet är klart väljer du **OK**.
1. Du bör sedan uppmanas att logga in på enheten med det delade lokala kontot och lösenordet.

## <a name="maintain"></a>Underhåll

Med den här konfigurationen rekommenderar vi att du startar om processen ovan och omstreckar enheten med ARC-verktyget och tillämpar ett nytt PPKG för att göra uppdateringar av operativsystemet och/eller program.
