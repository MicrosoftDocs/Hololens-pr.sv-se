---
title: Integritets- och körningsatitet som stöds av maskinvara
description: Integritets- och körningsatitet som stöds av maskinvara
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: security, hololens, Hardware backed integrity, runtime attestation, UEFI, UEFI secure boot, secure boot, TPM, threat protection, Windows Anti-Persistence Assurance, code integrity, code protection,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de12231b87c028ed9d8ca785a5b351fc4cb1c6fd8dbe304e4baaccd6803c5f6a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665411"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Maskinvarubackad integritet och runtime-attestation

Maskinvarubaserade integritets- och körningsatablerar skyddar mot hot som kommer före starten av ett operativsystem, under körning, när enheten använder maskinvara och fjärratablereringstjänster för att säkerställa att integriteten upprätthålls vid start och under körningstid.

## <a name="uefi-secure-boot"></a>Säker start i UEFI

HoloLens 2 framtvingar alltid säker start med Unified Extensible Firmware Interface (UEFI) och UEFI startar Windows Holographic for Business.
Säker start säkerställer att hela startkedjan verifieras för integritet och att Windows alltid startar med rätt säkerhetsprinciper tillämpade på den. Läs mer om [Säker start.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

Den Trusted Platform Module (TPM) är ett specialiserad chip på en slutpunktsenhet. HoloLens 2 använder TPM 2.0, som ger maskinvarut framtvingad nyckelisolering. Läs mer om [grunderna i TPM.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Skydd mot hot för beständig åtkomst

Målet med de flesta cyberattacker är att upprätthålla beständig åtkomst till en enhet. För cyberbrott gör upprätthållandet av denna beständighet att en komprometterad Windows-enhet kan ansluta till ett botnät, sälja åtkomst till enheten eller andra skadliga användare eller aktivera upprepad datastöld. I en värld av riktade attacker är beständighet viktigt för en lyckad cyberattack – antingen på en enhet eller (oftare) ett helt nätverk.  

I själva verket betraktas riktade attacker som "avancerade permanenta hot" på grund av deras strategiska behov av att upprätthålla åtkomsten till en målenhet eller ett målnätverk. Därför anser Windows Holographic for Business att skydd mot beständighet är absolut avgörande och använder antipersensteknik för att göra ett ironi för kundens säkerhetsindata.

### <a name="secure-boot"></a>Säker start

HoloLens 2 framtvingar säker start Extensible Firmware Interface Unified Extensible Firmware Interface (UEFI) för alla kärnoperativsystemets tillstånd. UEFI startar bara Microsofts betrodda plattformar, vilket säkerställer att hela startkedjan verifieras för integritet och att Windows alltid startar med rätt säkerhetsprinciper tillämpade. HoloLens 2 inte säker start inaktiveras och tillåter inte heller startprogrammet från tredje part.

> [!Tip]
> Läs mer om [Säker start.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Antipersistence Assurance

HoloLens 2 antipersistence garanterar användarna att en sådan händelse skulle minimeras om all skadlig kod skulle tas bort från systemet genom att helt enkelt stänga av enheten, även om en körning komprometterade systemet någonsin skulle inträffa, till exempel ett fjärrkryphål. För att ytterligare stärka sitt antiperssistence har HoloLens 2 lagt till kraftfullt integritetsskydd och lagt till skrivskyddade skydd.

Beständighet för operativsystemdata i form av data är fortfarande möjligt, såvida inte användaren utför push-knappåterställning (PBR) för enheten som rensar alla föränderliga partitioner. Även om beständighet för oföränderliga partitioner blir mycket svårare, måste användaren PBR HoloLens 2 för att ta bort eventuellt hotpersistence från föränderliga delar.

## <a name="code-integrity-protection"></a>Kodintegritetsskydd

Kodintegritet (CI) är en viktig säkerhetsegenskap för ett modernt operativsystem. Framtvingande av CI möjliggör bra säkerhetsbeslut, eftersom det garanterar att kodens ursprung är transparent för både användaren och operativsystemet. Fullständig kodintegritet måste utöka tidigare signering av binär avbildning och inkludera körningstvingande, till exempel kontrollflödesintegritet och dynamiska kodbegränsningar. KI är viktigt för att förhindra flera typer av attacker, inklusive socialt utformad skadlig kod, till exempel utpressningstrojaner, kryphål för fjärrkörning av kod och olika andra attackklasser.
