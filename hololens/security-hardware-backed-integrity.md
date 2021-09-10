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
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124429012"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Maskinvarubackad integritet och runtime-attestation

Maskinvarubaserade integritets- och körningsatablerar skyddar mot hot som kommer före starten av ett operativsystem, under körning, när enheten använder maskinvara och fjärratablerar tjänster för att säkerställa att integriteten upprätthålls vid start och under körningstid.

## <a name="uefi-secure-boot"></a>Säker start i UEFI

HoloLens 2 framtvingar alltid säker start med Unified Extensible Firmware Interface (UEFI) och UEFI startar Windows Holographic for Business.
Säker start säkerställer att hela startkedjan verifieras för integritet och att Windows alltid startar med rätt säkerhetsprinciper tillämpade på den. Läs mer om [Säker start.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

Den Trusted Platform Module (TPM) är ett specialiserad chip på en slutpunktsenhet. HoloLens 2 använder TPM 2.0, som ger maskinvarut framtvingad nyckelisolering. Läs mer om [grunderna i TPM.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Skydd mot hot för beständig åtkomst

Målet med de flesta cyberattacker är att upprätthålla beständig åtkomst till en enhet. För cyberbrott gör upprätthållandet av denna beständighet att en komprometterad Windows-enhet kan ansluta till ett botnät, sälja åtkomst till enheten eller andra skadliga användare eller aktivera upprepad datastöld. I en värld av riktade attacker är beständighet viktigt för en lyckad cyberattack – oavsett om det är på en enhet eller (vanligare) ett helt nätverk.  

I själva verket betraktas riktade attacker som "avancerade permanenta hot" på grund av deras strategiska behov av att upprätthålla åtkomsten till en målenhet eller ett målnätverk. Därför anser Windows Holographic for Business att det är absolut nödvändigt att skydda sig mot beständighet och att använda antipersensteknik för att göra ett säkerhetsindata från en kund.

### <a name="secure-boot"></a>Säker start

HoloLens 2 framtvingar säker start Extensible Firmware Interface Unified Extensible Firmware Interface (UEFI) på alla grundläggande operativsystemstillstånd. UEFI startar bara Microsofts betrodda plattformar, vilket säkerställer att hela startkedjan verifieras för integritet och att Windows alltid startar med rätt säkerhetsprinciper. HoloLens 2 inte säker start inaktiveras och tillåter inte heller startprogrammet från tredje part.

> [!Tip]
> Läs mer om [Säker start.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Antipersistence Assurance

HoloLens 2 antipersistence garanterar sina användare att en sådan händelse skulle minimeras om all skadlig kod togs bort från systemet bara genom att stänga av enheten, även om en körning komprometterade systemet någonsin skulle inträffa, till exempel ett fjärrkryphål. För att ytterligare stärka sitt antipersistence har HoloLens 2 lagt till kraftfullt integritetsskydd och satt skrivskydd på plats.

Beständighet för operativsystemdata i form av data är fortfarande möjligt, såvida inte användaren utför push-knappåterställning (PBR) för enheten som rensar alla föränderliga partitioner. Även om beständighet för oföränderliga partitioner blir mycket svårare måste användaren använda PBR HoloLens 2 för att ta bort eventuella hotpersistence från föränderliga delar.

## <a name="code-integrity-protection"></a>Kodintegritetsskydd

Kodintegritet (CI) är en viktig säkerhetsegenskap för ett modernt operativsystem. Framtvingande av CI möjliggör bra säkerhetsbeslut, eftersom det garanterar att kodens ursprung är transparent för både användaren och operativsystemet. Fullständig kodintegritet måste utöka tidigare signering av binär avbildning och inkludera körningstvingande, till exempel kontrollflödesintegritet och dynamiska kodbegränsningar. KI är viktigt för att förhindra flera typer av attacker, inklusive socialt utformad skadlig kod, till exempel utpressningstrojaner, kryphål för fjärrkörning av kod och olika andra attackklasser.
