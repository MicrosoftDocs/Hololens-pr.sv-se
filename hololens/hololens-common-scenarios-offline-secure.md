---
title: Vanliga scenarier – Säker offline-HoloLens 2
description: Lär dig hur du ställer in ett scenario för säker offlinedistribution och appdistribution med etablering HoloLens enheter.
keywords: HoloLens, hantering, offline, offline säker
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
ms.openlocfilehash: 1da19665dd3298ece8b007e86695bfe9f298f2347a0e7e058cbd30f0ad5d35c3
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664561"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Vanliga scenarier – Säker offline-HoloLens 2

## <a name="overview"></a>Översikt

Den här guiden innehåller vägledning för att tillämpa ett exempel på etableringspaket som låser en HoloLens 2 för användning i säkra miljöer med följande begränsningar:

-   Inaktivera WiFi.
-   Inaktivera BlueTooth.
-   Inaktivera mikrofoner.
-   Förhindrar tillägg eller borttagning av etableringspaket.
-   Ingen användare kan aktivera någon av ovanstående begränsade komponenter.

[![Scenario för säker offline-anslutning ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Förbereda

Windows 10 Datorinstallation
1. [Ladda ned den senaste HoloLens 2 OS-filen](https://aka.ms/hololens2download) direkt till en dator. 
   1. Stöd för den här konfigurationen ingår i Build 19041.1117 och högre.
1. Ladda ned/installera verktyget Advanced Recovery Companion (ARC) [från Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) till datorn
1. Ladda ned/installera [det Windows verktyget Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) från Microsoft Store till datorn.
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
   |     Principer/Anslutning/AllowBluetooth                |     No                            |     Inaktiverar Bluetooth                                                                                                             |
   |     Principer/erfarenhet/AllowCortana                    |     No                            |     Inaktiverar Cortana (för att eliminera potentiella problem eftersom mikrofonerna är inaktiverade)                                          |
   |     Principer/MixedReality/MicrophoneDisabled            |     Yes                           |     Inaktiverar mikrofon                                                                                                            |
   |     Principer/Sekretess/LetAppsAccessLocation              |     Framtrigt neka                    |     Förhindrar att appar försöker komma åt platsdata (för att eliminera potentiella problem eftersom Platsspårning är inaktiverat)    |
   |     Principer/Sekretess/LetAppsAccessMicrophone            |     Framtrigt neka                    |     Förhindrar att appar försöker komma åt mikrofoner (för att eliminera potentiella problem eftersom mikrofonerna är inaktiverade)           |
   |     Principer/Säkerhet/AllowAddProvisioningPackage       |     No                            |     Förhindrar att alla lägger till etableringspaket som kan försöka åsidosätta låsta principer.                         |
   |     Principer/Säkerhet/AllowRemoveProvisioningPackage    |     No                            |     Förhindrar att någon tar bort det låsta etableringspaketet.                                                           |
   |     Principer/System/AllowLocation                       |     No                            |     Förhindrar att enheten försöker spåra platsdata.                                                                        |
   |     Principer/WiFi/AllowWiFi                             |     No                            |     Inaktiverar Wi-Fi                                                                                                                 |

1. Under Runtime Inställningar väljer **du Accounts/Users/UserName: Holo/Password**.

   Anteckna lösenordet och återställ om du vill.

1. Gå till UniversalAppInstall/UserContextApp och [konfigurera den LOB-app](app-deploy-provisioning-package.md) som du ska distribuera till dessa enheter.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av var du lägger till din app i WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. När du är klar väljer du knappen "Exportera" och följer alla uppmaningar tills ditt etableringspaket har skapats.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av knappen Exportera för det här paketet i WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Distribuera

1. Anslut HL2 till din Windows 10-dator via USB-kabel.
1. Starta ARC-verktyget och välj **HoloLens 2**

   ![HoloLens 2: Första skärmen med ett rent omstreck](images/ARC2.png)

1. På nästa skärm väljer du **Manuellt paketval.**

   ![HoloLens 2 ARC-informationsskärm](images/arc_device_info.png)

1. Gå till den tidigare nedladdade .ffu-filen och välj **Öppna**.
1. På sidan Varning väljer du **Fortsätt.**

   ![HoloLens 2 ARC-varningsskärm](images/arc_warning.png)

1. Vänta tills ARC-verktyget har slutfört installationen HoloLens 2 OS.
1. När enheten har slutfört installationen och startar igen går du från datorn till Utforskaren och kopierar den tidigare sparade PPKG-filen till enhetsmappen.

   > [!div class="mx-imgBorder"]
   > ![PPKG-fil på datorn i Utforskaren fönster.](images/offline-secure-file-explorer.png)

1. På skärmen HoloLens 2 trycker du på följande knappkombination för  att köra  etableringspaketet: Tryck på Nedvolym och Strömknapp på samma gång.
1. Du uppmanas att tillämpa etableringspaketet och välja **Bekräfta**
1. När etableringspaketet är klart väljer du **OK**.
1. Du bör sedan uppmanas att logga in på enheten med det delade lokala kontot och lösenordet.

## <a name="maintain"></a>Underhåll

Med den här konfigurationen rekommenderar vi att du startar om processen ovan och omstreckar enheten med ARC-verktyget och tillämpar ett nytt PPKG för att göra uppdateringar av operativsystemet och/eller program.
