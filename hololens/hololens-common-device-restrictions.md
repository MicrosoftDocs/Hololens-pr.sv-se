---
title: Vanliga enhetsbegränsningar
description: Håll dig uppdaterad med vanliga enhetsbegränsningar och inställningar för HoloLens enhet med mixad verklighet.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427958"
---
# <a name="common-device-restrictions"></a>Vanliga enhetsbegränsningar 

Den här guiden hjälper IT-proffs att förstå de vanligaste hanteringsalternativen för Windows 10 Holographic operativsystem i företaget. Läs dokumentationen om MDM-systemet för att förstå hur dessa principer aktiveras av MDM-leverantören. Alla MDM-system stöder inte alla inställningar som beskrivs i den här guiden. Vissa stöder anpassade principer via OMA-URI XML-filer. Se [Microsoft Intune stöd för anpassade principer.](/mem/intune/configuration/custom-settings-windows-10) Namngivningskonventionerna kan också variera mellan MDM-leverantörer.

## <a name="prevent-changing-of-settings"></a>Förhindra ändring av inställningar
Anställda tillåts vanligtvis ändra vissa personliga enhetsinställningar som du kanske vill låsa på företagsenheter. Anställda kan interaktivt justera vissa inställningar för HoloLens via inställningsgränssnittet. Med HJÄLP av MDM kan du begränsa vilka användare som tillåts att ändra. Följande visar vanliga MDM-inställningar som stöds Windows 10 Holographic för att konfigurera inställningsbegränsningar:
-   [Tillåt VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Tillåter att användaren ändrar VPN-inställningar
-   [Tillåt manuell WiFi-konfiguration:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Gör att användare kan Wi-Fi anslutningar utanför MDM-etablerade nätverk
-   [Tillåt manuell AVregistrerad MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Om användarna tillåts ta bort arbetsplatskontot (dvs. avregistrera enheten från MDM-systemet)

Har lagts [till Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) för HoloLens 2-enheter:
- [Tillåt lägg till etableringspaket:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Växla om användare kan lägga till nya etableringspaket och skriva över med nya värden.
- [Tillåt ta bort etableringspaket:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Växla om användare kan ta bort etableringspaket så att de kan växla tidigare låsta inställningar.

Mer information om principalternativ finns i HoloLens [princip-CPP:er](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Maskinvarubegränsningar
Windows 10 Holographic enheter använder avancerad teknik som innehåller populära maskinvarufunktioner som kameror, mikrofoner, högtalare, USB-gränssnitt, Bluetooth-gränssnitt och Wi-Fi. Du kan använda maskinvarubegränsningar för att styra tillgängligheten för dessa funktioner.
I följande lista visas vanliga MDM-inställningar som Windows 10 Holographic stöder för att konfigurera maskinvarubegränsningar:

> [!NOTE]
> Vissa av dessa maskinvarubegränsningar påverkar anslutningen och hjälper till med dataskyddet.

-   [Tillåt Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Om användarna kan aktivera och använda Wi-Fi-radio på sina enheter.
-   [Tillåt USB-anslutning:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Om USB-anslutningen är aktiverad (påverkar inte USB-laddning).)
-   [Tillåt Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Om användarna kan aktivera och använda Bluetooth radio på sina enheter.
-   [Begränsa kamera:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Anger om Windows kan komma åt kameran.
-   [Begränsa mikrofoner:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Anger om Windows kan komma åt mikrofonen.

Lades till [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) för HoloLens 2 enheter. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Ställ in hur lång tid det tar innan skärmen stängs av och genom att stänga av skärmen låses enheten. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Ställ in hur lång tid det tar innan skärmen stängs av och genom att stänga av skärmen låses enheten. 
