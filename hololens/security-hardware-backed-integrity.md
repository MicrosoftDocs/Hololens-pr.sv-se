---
title: Maskinvarubackad integritet och attestation för körning
description: Maskinvarubackad integritet och attestation för körning
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
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380054"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Maskinvarubackad integritet och attestation för körning

Maskinvarubaserade integritets- och körningsatablerar skyddar mot hot som kommer före starten av ett operativsystem, under körning, när enheten använder maskinvara och fjärratablerar tjänster för att säkerställa att integriteten upprätthålls vid start och under körningstid.

## <a name="uefi-secure-boot"></a>Säker start i UEFI

HoloLens 2 tillämpar alltid säker start Extensible Firmware Interface Unified Extensible Firmware Interface (UEFI) och UEFI startar Windows Holographic for Business.
Säker start säkerställer att hela startkedjan är verifierad för integritet och att Windows alltid startar med rätt säkerhetsprinciper tillämpade på den. Läs mer om [Secure Boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

## <a name="tpm"></a>TPM

Den Trusted Platform Module (TPM) är ett specialiserad chip på en slutpunktsenhet. HoloLens 2 använder TPM 2.0, som tillhandahåller maskinvarut framtvingad nyckelisolering. Läs mer om [grunderna i TPM.](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Skydd mot persistence-åtkomsthot

Målet med de flesta cyberattacker är att upprätthålla beständig åtkomst till en enhet. För cyberbrott gör underhåll av denna beständighet att en komprometterad Windows-enhet kan ansluta till ett botnät, sälja åtkomst till enheten eller andra skadliga användare eller aktivera upprepad datastöld. I en värld av riktade attacker är beständighet avgörande för en lyckad cyberattack – antingen på en enhet eller (oftare) ett helt nätverk.  

Riktade attacker betraktas i själva verket som "avancerade permanenta hot" på grund av deras strategiska behov av att upprätthålla åtkomsten till en målenhet eller ett målnätverk. Därför anser Windows Holographic for Business att det är absolut viktigt att skydda mot beständighet och att använda antipersistenceteknik för att göra en kundsäkerhets promise.

### <a name="secure-boot"></a>Säker start

HoloLens 2 tillämpar Säker start Extensible Firmware Interface Unified Extensible Firmware Interface (UEFI) för alla kärnoperativsystemets tillstånd. UEFI startar endast Microsofts betrodda plattformar, vilket säkerställer att hela startkedjan verifieras för integritet och att Windows alltid startar med rätt säkerhetsprinciper. HoloLens 2 har inte säker start inaktiverad och tillåter inte heller startprogram från tredje part.

> [!Tip]
> Läs mer om [Säker start.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Anti-Persistence Assurance

HoloLens 2-antipersistence garanterar sina användare att en sådan händelse skulle minimeras om all skadlig kod skulle tas bort från systemet genom att helt enkelt stänga av enheten, även i sällsynta fall då systemet komprometteras, till exempel ett fjärrkryphål. För att ytterligare stärka sitt antipersistence har HoloLens 2 lagt till kraftfullt integritetsskydd och satt skrivskydd på plats.

Beständighet för operativsystemdata i form av data är fortfarande möjligt, såvida inte användaren utför push-knappåterställning (PBR) för enheten som rensar alla föränderliga partitioner. Även om beständighet för oföränderliga partitioner blir mycket svårare måste användaren använda PBR HoloLens 2 för att ta bort eventuell hotpersistence från föränderliga delar.

## <a name="code-integrity-protection"></a>Kodintegritetsskydd

Kodintegritet (CI) är en viktig säkerhetsegenskap för ett modernt operativsystem. Att framtvinga CI möjliggör bra säkerhetsbeslut, eftersom det garanterar att kodens ursprung är transparent för både användaren och operativsystemet. Fullständig kodintegritet måste utöka tidigare signering av binär avbildning och inkludera körningstvingande, till exempel kontrollflödesintegritet och dynamiska kodbegränsningar. KI är viktigt för att förhindra flera klasser av attacker, inklusive socialt utformad skadlig kod, till exempel utpressningstrojaner, kryphål för fjärrkörning av kod och olika andra attackklasser.
