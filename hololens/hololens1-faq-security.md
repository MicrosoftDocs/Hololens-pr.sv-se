---
title: Vanliga säkerhetsfrågor
description: Håll dig uppdaterad med vanliga säkerhetsfrågor och svar om HoloLens Mixed Reality-enheter.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, security
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378917"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Vanliga frågor och svar om HoloLens (första generationens) säkerhetsfrågor

1. **Vilken nivå av dataskydd erbjuder HoloLens 1?**
    1. Se [HoloLens (1:a gen) BitLocker-kryptering](hololens1-encryption.md)
1. **Vilken typ av trådlöst används?**
    1. 802.11ac och Bluetooth 4.1 LE
1. **Vilken typ av arkitektur ingår?  Till exempel: peka på punkt, nät eller något annat?**
    1. Wi-Fi kan användas i infrastrukturläge för att kommunicera med andra trådlösa åtkomstpunkter.
    1. Bluetooth kan användas för att prata peer-to-peer mellan flera HoloLens om kundernas program stöder det eller till andra Bluetooth-enheter.
1. **Vad är FCC-ID?**
    1. C3K1688
1. **Vilka frekvensintervall och kanaler fungerar enheten på och kan den konfigureras?**
    1. Wi-Fi: Frekvensintervallet kan inte konfigureras av användaren och beror på vilket land som används. I USA Wi-Fi både 2,4 GHz-kanaler (1–11) och 5 GHz-kanaler (36–64, 100–165).
    1. Bluetooth: Bluetooth använder standardintervallet 2,4–2,48 GHz.
1. **Kan enheten tillåta eller blockera specifika frekvenser?**
    1. Detta kan inte styras av användaren/enheten.
1. **Vad är energinivån för både överföring och mottagning? Är den justerbar? Vad är åtgärdsintervallet?**
    1. Våra standarder för testning av koldioxidutsläpp finns [här.](https://fccid.io/C3K1688) Åtgärdsintervallet är mycket beroende av åtkomstpunkten och miljön , men motsvarar ungefär andra telefoner, surfplattor eller datorer av hög kvalitet.
1. **Vilken är arbetscykeln/livslängden för normal drift?**
    1. 2–3 timmar aktiv användning och upp till två veckors väntetid
    1. Batterilivslängden är inte tillgänglig.
1. **Vad är överförings- och mottagningsbeteende när ett verktyg inte är inom räckhåll?**
    1. HoloLens-överföring/-mottagning följer standardmönstret för Wi-Fi/Bluetooth. Vid gränsen till intervallet märker du förmodligen att indata blir lite sporadiska tills de kopplas från helt, men när du är inom räckhåll igen bör de snabbt återansluta.
1. **Vad är distributionsdensitet per kvadratfot?**
    1. Detta är beroende av din nätverksinfrastruktur.
1. **Kan enheten använda infrastrukturen som en klient?**
    1. Ja
1. **Vilket protokoll används?**
    1. HoloLens använder inte några upphovsrättsskyddade protokoll
1. **Uppdateringsfrekvens för operativsystem – Vad är frekvensen för OS-uppdateringar för HL?  Finns det ett fast schema?  Släpper Microsoft säkerhetskorrigeringar efter behov osv.**
    1. Microsoft tillhandahåller OS-uppdateringar till HoloLens på exakt samma sätt som det görs för Windows 10. Det finns vanligtvis två större uppdateringar per år, en under vår och en under våren. Eftersom HoloLens är en Windows-enhet är uppdateringskonceptet detsamma som för alla andra Windows-enheter. Microsoft släpper säkerhetskorrigeringar efter behov och följer samma koncept som på andra Windows-enheter.
1. **OS-härdning – Vilka alternativ finns det för att härda operativsystemet?  Kan vi ta bort eller stänga av onödiga appar eller tjänster?**
    1. HoloLens fungerar som en smartphone. Det är jämförbart med andra moderna Windows-enheter. HoloLens kan hanteras av antingen Microsoft Intune eller andra moderna Enhetshantering-lösningar som MobileIron, Airwatch eller Soti. Det finns principer som du kan ange i dessa hanteringssystem för att placera säkerhetsprinciper på enheten och för att härda enheten. Du kan också välja att ta bort onödiga program om du vill.
1. **Hur kommer program att hanteras och uppdateras? Vilken kontroll måste vi definiera vilka appar som läses in och appuppdateringsprocessen för appar som bor i Microsoft Store?**
    1. HoloLens hämtar endast program via Windows Store. Endast Appx-programpaket kan installeras, som har utvecklats för användning av HoloLens. Du kan se detta i Microsoft Store med en liten logotyp bredvid programmet som visar HoloLens-enheten. All kontroll som du har över hanteringen av Store-program gäller även för HoloLens. Du kan använda begreppet officiell butik eller butik för företag. Appar kan antingen läsas in manuellt (manuell process för att läsa in en app på en Windows-enhet) eller hanteras via en MDM så att appar hämtas automatiskt från butiken när det behövs.
1. **Hur ofta uppdateras appar i butiken för HoloLens?**
    1. När vi följer samma koncept för Microsoft Store och hämtar appar därifrån bestäms uppdateringscykeln av programmets utvecklare. Alla hanteringsalternativ som du har för att styra uppdateringsmekanismen i arkivet gäller även för HoloLens.
1. **Finns det en säker startfunktion för HoloLens?**
    1. Ja
1. **Går det att inaktivera eller koppla från kringutrustningsstöd från enheten?**
    1. Ja
1. **Går det att styra eller inaktivera användningen av portar på enheten?**
    1. HoloLens innehåller bara två portar (en för högtalare och en för debitering eller anslutning till datorer). Det går inte att inaktivera porten på grund av funktioner och återställningsorsaker.
1. **Antivirus, slutpunktsidentifiering, IPS, lista över tillåtna appar – Alla möjligheter att köra antivirus, slutpunktsidentifiering, IPS, lista över tillåtna appkontroller osv.**
    1. Windows Holographic for Business (commercial suite) stöder Windows Defender Smart Screen. Om ett antivirusprogram skulle skapa och publicera sin app på Universell Windows-plattform kan den laddas ned på HoloLens. För närvarande har inga företag gjort detta för HoloLens.
    1. Det går att tillåta appar med hjälp av Microsoft Enterprise Store, där du bara kan välja vilka specifika appar som kan laddas ned. Med MDM kan du också låsa vilka specifika appar som kan köras eller till och med visas på enheten.
1. **Kan vi sätta enheten i karantän från prod-nätverket tills vi uppdaterar enheten om den har varit offline under en längre tid?  T.ex. Enheten har satts i en låda som inte har varit påslagen under en period (sex månader) och har inte tagit emot några uppdateringar, korrigeringar osv.  När den försöker ansluta till nätverket kan vi flagga den och säga att du måste uppdatera i ett annat nätverk innan du uppmanas att ansluta till nätverket.**
    1. Det här är något som kan hanteras på infrastrukturnivå av antingen en MDM eller en lokala server. Enheten kan flaggas som in kompatibel om den inte uppfyller en angiven uppdateringsversion.
1. **Innehåller Microsoft några bakdörrar eller åtkomst till tjänster som gör att Microsoft kan ansluta till enheten för skärmdelning eller fjärrsupport?**
    1. Inga
1. **När ett PKI-certifikat genereras för betrodd kommunikation vill vi att certifikatet ska genereras på enheten så att vi vet att det bara finns på enheten, unikt för enheten och inte kan exporteras eller användas för att personifiera enheten. Är detta sant på HoloLens? Om inte, finns det en potentiell riskreducering?**
    1. CSR för SCEP genereras på själva enheten. Intune och den lokala SCEP-anslutningsappen hjälper till att skydda själva begärandena genom att lägga till och verifiera en utmaningssträng som skickas till klienten.
    1. Eftersom HoloLens (första gen och andra generationen) har en TPM-modul lagras dessa certifikat i TPM-modulen och kan inte extraheras. Även om det kunde extraheras gick det inte att verifiera utmaningssträngarna på en annan enhet, vilket gör att certifikaten/nyckeln inte kan användas på olika enheter.
