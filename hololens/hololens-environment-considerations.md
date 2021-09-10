---
title: HoloLens miljööverväganden
description: Få bästa möjliga upplevelse med hjälp HoloLens när du optimerar enheten för dina ögon och din miljö.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holographic frame, field of view, fov, kalibrering, spaces, environment, how-to, HoloLens, mixed reality, mixed reality headsets
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427846"
---
# <a name="hololens-environment-considerations"></a>HoloLens miljööverväganden

HoloLens blandar det holografiska med den "verkliga" världen och placerar hologram i din miljö. Ett holografiskt appfönster "låser sig" på väggen, en holografisk ballerina som snurrar på tabeltopen och en nätt liten kloss sitter ovanpå din ovetande väns huvud. När du använder ett integrerande spel eller en app sprids den holografiska världen ut för att fylla din miljö, men du kan fortfarande se och flytta runt i utrymmet.

Hologrammen du placerar förblir där du har placera dem, även om du stänger av enheten.

## <a name="setting-up-an-environment"></a>Konfigurera en miljö

HoloLens enheter vet hur de ska placera stabila och exakta hologram genom *att spåra* användare i ett utrymme. Utan korrekt spårning förstår inte enheten miljön eller användaren i den. Hologram kan visas på fel platser, inte visas på samma plats varje gång eller visas inte alls. De data som används för att spåra användare representeras på den *rumsliga kartan*.  

Spårningsprestanda påverkas kraftigt av den miljö som användaren finns i, och att justera en miljö för att ge stabil och konsekvent spårning är en konst i stället för en vetenskap. Många olika miljöfaktorer sammanförs för att möjliggöra spårning, men som Mixed Reality-utvecklare finns det flera faktorer som du kan tänka på för att finjustera ett utrymme för bättre spårning.

### <a name="lighting"></a>Belysning

Windows Mixed Reality använder visuellt ljus för att spåra användarens plats. När en miljö är för ljus kan kamerorna bli mättade och inget ses. Om miljön är för mörk kan kamerorna inte hämta tillräckligt med information och inget visas. Belysningen bör vara jämn och tillräckligt ljus som en människa kan se utan ansträngning, men inte så ljust att lampan har svårt att titta på.  

Områden där det finns punkter med starkt ljus i ett övergripande dim-område är också problematiska, eftersom kameran måste justeras vid in- och utflyttning från ljusa utrymmen. Detta kan leda till att enheten "försvinner" och att ändringen i ljus motsvarar en platsändring. Stabila ljusnivåer i ett område leder till bättre spårning.  

Alla utomhusbelysning kan också orsaka instabilitet i spåraren, eftersom sol kan variera avsevärt över tid. Till exempel kan spårning i samma utrymme under sommaren kontra snö ge drastiskt olika resultat, eftersom det belysnade utrymmet utanför kan vara högre vid olika tidpunkter på året.  

Om du har en meter är en stadig 500–1 000 meter ett bra ställe att börja på.  

#### <a name="types-of-lighting"></a>Typer av belysning

Olika typer av ljus i ett utrymme kan också påverka spårningen. Glödlampan pulserar med den ac-elektricitet som passerar – om AC-frekvensen är 50 Hz så pulserar lampan vid 50 Hz. För en människa märks inte detta pulserande. Men HoloLens 30 camera (30 bilder) ser dessa ändringar – vissa bildrutor är väl upplysta, vissa är dåligt upplysta och vissa blir överreponerade när kameran försöker kompensera för ljuspulser.  

I USA är elektricitetsfrekvensens standard 60 Hz, så glödlampans pulser räknas av med HoloLens-bildfrekvens – 60 Hz-pulser justeras med HoloLens' 30 FRAME-bildhastighet. Många länder har dock en AC-frekvensstandard på 50 Hz, vilket innebär att vissa HoloLens bildrutor tas under pulserna och andra inte gör det. I synnerhet har belysning i Europa varit känd för att orsaka problem.  

Det finns några saker som du kan försöka lösa problem med omskolning. Temperatur, glödlampans ålder och uppvärmningscykler är vanliga orsaker till att glödlampan blir äldre och att byta ut glödlampan kan vara till hjälp. Det kan också vara bra att ändra glödlampan och se till att de aktuella dragningarna är konstanta.  

### <a name="items-in-a-space"></a>Objekt i ett utrymme

HoloLens använder unika miljömärken, även kallade funktioner , *för* att hitta sig själva i ett utrymme.  

En enhet kan nästan aldrig spåras i ett funktions dåligt område, eftersom enheten inte har något sätt att veta var i utrymmet den är. Att lägga till funktioner i väggar i ett utrymme är vanligtvis ett bra sätt att förbättra spårningen. Affischer, symboler som trycks på en vägg, plantor, unika objekt eller andra liknande objekt är till hjälp. Ett rörigt skrivbord är ett bra exempel på en miljö som leder till bra spårning – det finns många olika funktioner i ett enda område.  

Använd dessutom unika funktioner i samma utrymme. Samma affisch som upprepas flera gånger över en vägg leder till exempel till enhetsförväxling eftersom HoloLens inte vet vilken av de repetitiva affischerna den tittar på. Ett vanligt sätt att lägga till unika funktioner är att använda rader med maskeringsband för att skapa unika, icke-repetitiva mönster längs väggar och golv i ett utrymme.  

En bra fråga att ställa sig själv är: om du bara såg en liten mängd av scenen, kan du hitta dig själv i utrymmet unikt? Annars är det troligt att enheten även har problem med spårning.

#### <a name="wormholes"></a>Maskhål

Om du har två områden eller regioner som ser likadana ut kan spåraren tro att de är likadana. Detta leder till att enheten luras att tro att den är någon annanstans. Vi kallar dessa typer av repetitiva *områden maskhål.*  

För att förhindra maskhål kan du försöka förhindra identiska områden i samma utrymme. Identiska områden kan ibland innehålla fabriksstationer, fönster på en byggnad, serverrack eller arbetsstationer. Genom att märka områden eller lägga till unika funktioner i varje liknande område kan du minimera maskhål.

### <a name="movement-in-a-space"></a>Rörelse i ett utrymme

Om din miljö ständigt ändras har enheten inga stabila funktioner att hitta mot.  

Ju fler flytta objekt som finns i ett utrymme, inklusive personer, desto enklare är det att förlora spårning. Flytt av transportband, objekt i olika konstruktions tillstånd och många personer i ett utrymme har alla varit kända för att orsaka spårningsproblem.

Den HoloLens kan snabbt anpassas efter dessa ändringar, men endast när det området är tydligt synligt för enheten. Områden som inte ses så ofta kan ligga efter verkligheten, vilket kan orsaka fel i den rumsliga kartan. Till exempel genomsöker en användare en vän och vänder sig sedan om medan vännen lämnar rummet. En "spökbild" av vännen finns kvar i data för rumslig mappning tills användaren genomsöker det nu tomma utrymmet på nytt.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Användarens närhet till objekt i utrymmet

På samma sätt som människor inte kan fokusera bra på objekt nära ögonen, HoloLens när objekt är nära sina kameror. Om ett objekt är för nära att ses med båda kamerorna, eller om ett objekt blockerar en kamera, har enheten mycket fler problem med spårning mot objektet.  

Kamerorna kan inte se närmare än 15 cm från ett objekt.

### <a name="surfaces-in-a-space"></a>Ytor i ett utrymme

Starkt reflektiva ytor ser troligen olika ut beroende på vinkeln, vilket påverkar spårningen. Tänk på en helt ny bil – när du flyttar runt den återspeglas lampan och du ser olika objekt på ytan när du flyttar. För spåraren representerar de olika objekten som visas på ytan en föränderlig miljö, och enheten förlorar spårning.

Färre objekt är enklare att spåra mot.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi överväganden för fingeravtryck

Så länge Wi-Fi är aktiverat korreleras kartdata med ett Wi-Fi fingeravtryck, även om de inte är anslutna till ett faktiskt WiFi-nätverk/router. Utan Wi-Fi information kan utrymme och hologram vara något långsammare att känna igen. Om Wi-Fi signaler ändras avsevärt kan enheten tro att den är helt i ett annat utrymme.

Nätverksidentifiering (till exempel SSID- eller MAC-adress) skickas inte till Microsoft och alla Wi-Fi-referenser sparas lokalt på HoloLens.

## <a name="mapping-new-spaces"></a>Mappa nya utrymmen

När du anger ett nytt blanksteg (eller läser in ett befintligt) visas en nätgrafik som sprider sig över utrymmet. Det innebär att din enhet mappar din miljö. Även om HoloLens får lära sig ett utrymme över tid finns det tips och trick för att mappa utrymmen.

## <a name="environment-management"></a>Miljöhantering

Det finns två inställningar som gör det möjligt för användare att "rensa" hologram och HoloLens att "glömma" ett blanksteg. De finns i Hologram och miljöer i inställningsappen, och den andra inställningen visas också under **Sekretess** i **inställningsappen.**  

1. **Ta bort hologram i närheten.** När du väljer den här HoloLens raderar alla fästa hologram och alla lagrade kartdata för det "aktuella utrymmet" där enheten finns. Ett nytt kartavsnitt skulle skapas och lagras i databasen för den platsen när hologram återigen placeras i samma utrymme.

1. **Ta bort alla hologram.** Om du väljer den här HoloLens alla kartdata och fästa hologram i alla blankstegsdatabaser. Inga hologram kommer att omidentifieras och eventuella hologram måste nyligen placeras för att lagra kartavsnitt i databasen igen.

## <a name="hologram-quality"></a>Hologramkvalitet

Hologram kan placeras i din miljö – högt, lågt och runt omkring dig – men du kommer att se dem via en [holografisk](/windows/mixed-reality/holographic-frame) ram som finns framför dina ögon. För att få den bästa vyn måste du justera enheten så att du kan se hela ramen. Och tveka inte att gå runt i din miljö och utforska!

För att [dina hologram ska](/windows/mixed-reality/hologram) se finare, tydliga och stabila ut måste HoloLens kalibreras bara för dig. När du först ställer HoloLens vägleds du genom den här processen. Senare, om hologram inte ser rätt ut eller om du får många fel, kan du göra justeringar.

Om du har problem med att mappa utrymmen kan du prova att ta bort hologram i närheten och mappa om utrymmet.

### <a name="calibration"></a>Kalibrering

Om dina hologram ser jitteriga eller skakiga ut, eller om du har problem med att placera hologram, är det första du försöker med [kalibreringsappen](hololens-calibration.md). Den här appen kan också vara till hjälp om du upplever problem när du använder HoloLens.

Du kommer till kalibreringsappen genom **att Inställningar**  >    >  **systemverktyg**. Välj **Öppna kalibrering** och följ instruktionerna.

Om någon annan kommer att använda din HoloLens bör de köra kalibreringsappen först så att enheten är korrekt konfigurerad för dem.

## <a name="temperature-and-regulatory-information"></a>Temperatur- och regelinformation

[HoloLens regelinformation:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Innehåller information om temperaturintervall, försäljning, radio- och TV-interferens med mera.

Se information för "HoloLens" i [Material](https://www.microsoft.com/legal/compliance/materials-substances) och > REACH Artikel 33 Disclosure on Environmental Compliance (PDF).

Här följer några riktlinjer när du använder din enhet:

1. Lagra enheten i en miljö inom temperaturintervallet (antingen i vänteläge eller av) i en timme innan du använder enheten.
1. Använd enheten i en miljö inom temperaturintervallet.
1. Använd enheten inomhus.
1. Använd enheten i skugga; Även inomhus undviker direkt genom fönster eller takfönster.
1. Om du följer riktlinjerna ovan men får oväntade säkerhetsproblem följer du stegen nedan för att skicka [feedback.](hololens-feedback.md) 
    1. Kontrollera **att Fullständig** eller **Valfri** telemetri är aktiverat på enheten. Om det inte är det aktiverar du det. 
    >[!CAUTION]
    > Telemetrin är inte retroaktiv för termiska händelser – den måste aktiveras under avslutet, annars samlas inte nödvändiga data in.
    
    2. Återskapa uppvärmningsproblemet.
    3. Ta med datum och tid då den aktuella händelsen inträffade.
    4. Skicka [feedback](hololens-feedback.md).

## <a name="see-also"></a>Se även

- [Design av rumslig mappning](/windows/mixed-reality/spatial-mapping)
- [Hologram](/windows/mixed-reality/hologram)
