---
title: Företagsregistrering av HoloLens i MAC-adress begränsad Wi-Fi miljö
description: Mac-adress för nätverk på HoloLens 2 enheter
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1be1a8aa021c2a588b120fc9fa148b6c5dafd2840bbefa0d8ea9701751834521
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665594"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Företagsregistrering av HoloLens i MAC-adress begränsad Wi-Fi miljö

Det här dokumentet beskriver ett vanligt scenario som vi har identifierat i kundmiljöer där Wi-Fi begränsas av MAC-adresser eller certifikat krävs för att ansluta trådlösa nätverk.

## <a name="example-scenario"></a>Exempel på ett scenario

Många kunder i säkra miljöer har begränsningar för sina trådlösa eller kabelanslutna nätverk som endast tillåter att godkända enheter (baserat på MAC-adresser) kan ansluta korrekt. Detta kan framtvingas via MAC-adressfiltrering på en trådlös åtkomstpunkt eller via en DHCP-server. Dessutom kan vissa trådlösa nätverk skyddas med PEAP, vilket kräver att ett certifikat tillämpas på enheten innan autentisering på det trådlösa nätverket.

I det här scenariot kan två viktiga krav leda till fördröjningar eller kräva manuella åtgärder HoloLens ansluta enheter till nätverket:

- Det trådlösa PEAP-certifikatet måste tillämpas på enheten innan enheten kan ansluta till det trådlösa nätverket.
- MAC-adressen för HoloLens Wi-Fi adaptern måste vara registrerad.

De viktigaste utmaningarna med kraven ovan är:

1. MAC-adressen kan för närvarande bara identifieras från Inställningar på enheten eller från Intune efter en lyckad registrering.

2. Utan MAC-adressen kan enheten inte ansluta till Wi-Fi Network för att påbörja registreringen.

3. Manuella lösningar på dessa utmaningar kräver att en tekniker interagerar med enheten.

## <a name="solutions"></a>Lösningar

Det finns många sätt att förbättra den här situationen, beroende på vilken infrastruktur som är tillgänglig i miljön.

| Lösning | Fördelar | Krav |
| --- | --- | --- |
| Etableringspaket med Ethernet-adapter | Förbättrar OOBE-upplevelsen och ger en snabbare teknikerupplevelse. | HoloLens USB-C Hub + Ethernet-adaptern och teknikern behöver fortfarande interagera med enheten för MAC-avskiljning och OOBE-slutförande |
| Autopilot med Intune-registrering via Ethernet | Det här är en enkelstegsanslutning och registrering av enheten till kundmiljön. MAC-avskiljning kan slutföras utan att du behöver interagera med enheten | Intune aktiverat för kundens AAD-klientorganisation och en HoloLens USB-C Ethernet-adapter |
| Automatiserad rapportering av MAC-adresser | När enheter registreras med Intune-klienten kan ett skript rapportera MAC-adressen till teknikern. | Intune PowerShell-cmdlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Etableringspaket med Ethernet-adapter

> [!NOTE] 
> Om det kabelanslutna nätverket också omfattas av MAC-begränsningar måste MAC-adressen för USB-C Hub + Ethernet-adaptern också vara förhandsgodkänd. Var försiktig med det här kortet eftersom det tillåter åtkomst till nätverket från andra enheter.

### <a name="requirements"></a>Krav

- Kabelansluten nätverksport med åtkomst till kundens nätverk
- HoloLens Kompatibel USB-C Hub med Ethernet-adapter – Alla nätverkskort som inte kräver några ytterligare drivrutiner eller programinstallationer bör vara lämpliga.
- Etableringspaket som innehåller:
  - Innehåller information om trådlöst nätverk och certifikat
  - Du kan också ange registreringsinformation för organisationens Azure AD
  - Innehåller eventuella andra nödvändiga etableringsinställningar

### <a name="process"></a>Process

Processen kan variera beroende på enhetens programvarunivå. Om enheten har uppdateringen [från maj 2004](hololens-release-notes.md#windows-holographic-version-2004)följer du stegen nedan.

1. Placera etableringspaketet på roten av ett USB-minne och anslut till hubben.
2. Anslut Ethernet-kabel till Hub + Ethernet-adaptern.
3. Anslut USB-C Hub till HoloLens enhet.
4. Aktivera HoloLens och sätt på enheten.
5. Tryck på **knappen Volym ned och Ström för** att tillämpa etableringspaketet.
6. Teknikern kan nu följa OOBE och när den är klar öppnar du Inställningar appen för att hämta MAC-adressen för enheten.

Om enheten har en operativsystemsbygge före [uppdateringen från maj 2004](hololens-release-notes.md#windows-holographic-version-2004)följer du stegen nedan.

1. Sätt på HoloLens och anslut enheten till en dator.
2. Enheten bör visas på datorn som en fillagringsenhet.
3. Kopiera etableringspaketet till enheten
4. Anslut Ethernet-kabel till hubben.
5. Anslut USB-C Hub till HoloLens enhet.
6. Placera på HoloLens
7. Tryck på **knappen Volym ned och Ström** för att tillämpa etableringspaketet.
8. Teknikern kan nu följa OOBE och när den är klar öppnar du Inställningar appen för att hämta MAC-adressen för enheten.

### <a name="benefits"></a>Fördelar

Detta gör att en "enkel touch" av enheten kan tillämpa rätt etableringspaket och samla in MAC-adressen för enheten. [Du kan skapa etableringspaket genom att följa riktlinjerna här.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot med Intune-registrering

### <a name="requirements"></a>Krav

- Kabelansluten nätverksport med åtkomst till kundens nätverk
- HoloLens enheter som kör Windows Holographic 2004
- HoloLens Kompatibel USB-C Ethernet-adapter
- Intune har ställts in och aktiverats för kundens klientorganisation
- Enheten har registrerats för Autopilot och importerats till kundklientorganisationen
- Intune-principer som definierats för enheten:
   - Innehåller information om trådlöst nätverk och certifikat
   - Innehåller eventuella andra nödvändiga etableringsinställningar

Detta gör det möjligt för en kund med avancerade nätverkskrav att registrera enheterna i en praktisk och skalbar metod

Ytterligare förutsättningar krävs enligt nedan:
1. [Aktivera klientorganisationen för autopilotförhandsvisningen](hololens2-autopilot.md).
1. Skapa HoloLens för att ersätta etableringspaketet i Intune.
1. Skapa HoloLens Intune-principer.
1. Tilldela enheterna till rätt grupp.

### <a name="process"></a>Process

1. Anslut ethernet-kabeln till adaptern och anslut adaptern till USB-C-porten på HoloLens 2-enheten.

2. Aktivera HoloLens.

3. Enheten bör automatiskt ansluta till Internet under OOBE via Ethernet-adaptern. Den bör identifiera Autopilot-konfigurationen och automatiskt registreras med Azure AD och Intune.

4. Enheten tillämpar de nödvändiga Wi-Fi certifikat och annan konfiguration efter behov via Intune.

5. När det är klart kan teknikern läsa in Intune-portalen (Endpoint Manager) och gå in på sidan med enhetsegenskaper på **Start ->-enheter -> DeviceName -> Hardware**.

6. Den Wi-Fi MAC-adressen visas i Intune-portalen.

   ![MAC-adress via Intune](images/mac-address-intune.jpg)

7. Teknikern lägger till den här MAC-adressen som en tillåten enhet.

### <a name="benefits"></a>Fördelar

Detta gör det möjligt för teknikern att distribuera enheten från lådan för att registreras i Azure AD och Intune utan att teknikern behöver ha på sig enheten eller interagera manuellt med HoloLens-miljön.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Rapportering av MAC-adresser till teknikern

### <a name="requirements"></a>Krav

- Auktorisering av "Intune Graph PowerShell" mot kundens klientorganisation
- Installation av Intune-Graph PowerShell på teknikerdatorn.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Läsåtkomst till intune-elementen "Hanterade enheter". (Supportansvarig eller högre, eller en anpassad roll)

För närvarande finns det inget "enkelt" sätt att utlösa ett automationskommando baserat på registreringen av en ny enhet i Intune. Därför ger det här kommandot teknikern ett enkelt sätt att hämta MAC-adressen utan att behöva logga in på portalen och hämta den manuellt.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Detta returnerar namnet och MAC-adressen för alla HoloLens som har registrerats under de senaste 30 dagarna.

![MAC-adress via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Process

När Intune-registreringen har slutförts kör teknikern skriptet ovan för att hämta MAC-adressen.
