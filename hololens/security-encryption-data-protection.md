---
title: Kryptering och dataskydd
description: Lär dig mer om kryptering och dataskydd på HoloLens 2 enheter, inklusive BitLocker och Azure-integrering.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, Encryption, Data Protection, BitLocker Device, BitLocker, bitlocker, bitlocker encryption, azure integration,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639377"
---
# <a name="encryption-and-data-protection"></a>Kryptering och dataskydd

Kryptering och dataskydd skyddar data när enheten blir stulen eller borttappad och förhindrar obehöriga program från att komma åt känslig information.

## <a name="bitlocker-device-encryption"></a>BitLocker-enhetskryptering

BitLocker är en krypteringsfunktion med fullständig volym för integritetsskydd av skrivskyddade media (RO) och sekretessskydd för skrivbara media.  Sedan det startades har det varit en effektiv skärm mot obehörig åtkomst till data under offlineattacker. HoloLens 2 aktiverar Bitlocker Enhetskryptering (BDE) som standard för att skydda data från obehörig fysisk åtkomst till enheten. Microsoft utvecklas alltid för att uppfylla framtidens behov och fortsätter att investera och förbättra den här tekniken.

BDE är en dataskyddsfunktion som använder AES-XTS-256-kryptering på alla volymer i enhetens tillståndsavgränsade layout. BDE tillhandahåller kryptering på enhetsnivå i en tillståndsavgränsad layout. BitLocker Enhetskryptering aktiveras automatiskt på operativsystem och fasta datavolymer och kan inte stängas av, även av IT-administratörer, så att enheten alltid är skyddad.

BDE-krypteringsnycklar används sedan för att transparent dekryptera binärfiler och de data som krävs för att starta enheten. När operativsystemets volym låses upp och ett system startas blir andra volymer tillgängliga med hjälp av en volymspecifik version av skyddet för automatisk upplåsning. Inga andra skydd är tillgängliga för att upprätthålla användarsekretess och enheten kan bara låsas upp på samma enhet. Tvingande för skrivskyddad (RO) på nödvändiga volymer tillämpas och framtvingas omedelbart, med början från den första starten. Bitlocker-återställningsnyckeln behövs inte i livscykeln HoloLens 2.

## <a name="azure-integration"></a>Azure-integrering 

HoloLens 2 gör det möjligt för kunder att integrera sina enheter med Azure-tjänster. Kommunikation mellan HoloLens 2-enheter och Azure använder TLS-protokollet (Transport Layer Security) för att skydda data som skickas mellan sig själv och molntjänster som ger stark autentisering, meddelandesekretess och integritet. Alla Azure-tjänster har fullständigt stöd för TLS 1.2 och alla tjänster där kunder endast använder TLS 1.2 accepterar endast TLS 1.2-trafik. Azures krypteringsstandarder för data under överföring beskrivs i Översikt över [Azure-kryptering.](/azure/security/fundamentals/encryption-overview) Besök Azure-dokumentationen om du vill veta mer [om metodtips för datasäkerhet och kryptering i Azure.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive exempel på molnintegrering med HoloLens 2 har en funktion för automatisk uppladdning där dina filer och dokument kan laddas upp automatiskt till molnet när du är ansluten till Internet. Det går inte att inaktivera automatisk synkronisering av filer via en princip, men den kan konfigureras direkt via UX. 
