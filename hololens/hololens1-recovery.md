---
title: Starta om, återställa eller återställa HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Hur du använder Windows Device Recovery-verktyget för att flasha en bild HoloLens första gen.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: d6eb706c50e97a81910180c70be1d9dbc52bc6603cbc77ad130c1dd3b6a9010e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661799"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Starta om, återställa eller HoloLens (första gen)

Om du har problem med din HoloLens kan du prova en omstart eller återställning eller till och med omsnedställa enheten med hjälp av enhetsåterställning. Den här artikeln vägleder dig genom de rekommenderade återställningsstegen i rätt ordning.

Om du vill återställa en HoloLens 2 kan du se Återställa [en HoloLens 2](hololens-recovery.md)eftersom processen skiljer sig åt.

> [!NOTE]
> Den här artikeln fokuserar på HoloLens enhet och programvara. Om dina hologram inte ser bra ut kan du läsa HoloLens miljööverväganden för information om faktorer som förbättrar hologramkvaliteten. **[](hololens-environment-considerations.md)**

## <a name="restart"></a>Starta om

### <a name="do-a-safe-restart-by-using-cortana"></a>Gör en säker omstart med hjälp av Cortana

Det säkraste sättet att starta om HoloLens är att använda Cortana, vilket vanligtvis är det första du försöker när du får problem med HoloLens.

> [!NOTE] 
> Cortana är inte tillgängligt på alla enheter.
> - Cortana är tillgängligt på alla HoloLens (första generationens) enheter. 
> - Cortana finns på HoloLens 2 enheter på versioner före Windows Holograpic, version 2004.

1. Aktivera din HoloLens.
1. Kontrollera att en användare är inloggad och att enheten inte väntar på ett lösenord för att låsa upp den.
2. Säg "Hej Cortana, starta om" eller "Hej Cortana starta om".
3. Cortana svarar och uppmanar dig att bekräfta. Vänta tills ett ljud spelas upp efter frågan och säg sedan "Ja". Enheten startas om.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Använda strömknappen för att göra en säker omstart

Om du fortfarande inte kan starta om enheten kan  du prova att starta om den med strömknappen:

1. Tryck på och håll **ned strömknappen** i 5 sekunder. Efter 1 sekund kommer alla fem lysdioderna att lysa och sedan långsamt stänga av en i ordning från höger till vänster. Efter 5 sekunder är alla lysdioder avstängda, vilket indikerar att avstängningen lyckades.
      
   > [!IMPORTANT]
   > Sluta trycka på knappen omedelbart efter att alla lysdioder har stängts av.
1. Vänta 1 minut tills avstängningen är klar. Avstängningen kan fortfarande pågår även efter att skärmarna har stängts av.
2. Sätt på enheten igen genom att trycka på och hålla ned **strömknappen** i 1 sekund.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Göra en säker omstart med hjälp av Windows Enhetsportalen

> [!NOTE]
> För den här HoloLens måste konfigureras som en utvecklarenhet. Läs mer på [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal).

Om den föregående proceduren inte fungerade kan du prova att starta om enheten med hjälp av [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal). I det övre högra hörnet hittar du alternativet att starta om eller stänga av enheten.

### <a name="do-an-unsafe-forced-restart"></a>Göra en osäker framtvingade omstart

Om de föregående metoderna inte startade om HoloLens fram en omstart. Den här metoden motsvarar att ta bort och installera om batteriet. Det är riskabelt eftersom det kan göra att enheten är i ett skadat tillstånd. Om det händer måste du flasha HoloLens.  

> [!WARNING]
> Det här är en potentiellt skadlig metod och bör endast användas om de tidigare citerade metoderna inte fungerade.

1. Tryck på och håll **ned strömknappen** i minst 10 sekunder.
   - Det är okej att hålla ned knappen i mer än 10 sekunder.
   - Det är säkert att ignorera all LED-aktivitet.
1. Släpp knappen och vänta i 2–3 sekunder.
1. Tryck och håll ned **strömknappen** i 1 sekund.
1. Om du fortfarande har  problem trycker du på strömknappen i 4 sekunder tills alla batteriindikatorer tonas ut och skärmen slutar att visa hologram. Vänta 1 minut och tryck sedan på **strömknappen** igen för att aktivera enheten.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Gå tillbaka till en tidigare version – HoloLens (första gen)

I vissa fall kanske du vill gå tillbaka till en tidigare version av HoloLens programvara. Du kan göra detta med hjälp av Windows Device Recovery Tool för att återställa HoloLens till den tidigare versionen.

> [!NOTE]
> När du går tillbaka till en tidigare version tas dina personliga filer och inställningar bort.

Om du vill gå tillbaka till en tidigare version HoloLens 1 följer du dessa steg:

1. Kontrollera att du inte har några telefoner eller enheter Windows anslutna till datorn.
1. På datorn laddar du ned [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Ladda ned [HoloLens Anniversary Update-återställningspaketet](https://aka.ms/hololensrecovery).
1. När hämtningarna är klara öppnar du **Filutforskaren**  >  **Hämtar**. Högerklicka på den komprimerade mappen som du precis laddade ned och välj **Extrahera alla**  >  **extrahera** för att packa upp den.
1. Anslut din HoloLens datorn med hjälp av den mikro-USB-kabel som den medkom med. (Även om du har använt andra kablar för att ansluta HoloLens fungerar den här bäst.)
1. WDRT identifierar automatiskt HoloLens. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuellt paketval och** väljer installationsfilen som finns i mappen som du packade upp i steg 4. (Leta efter en fil med filnamnstillägget .ffu.)
1. Välj **Installera programvara** och följ instruktionerna.

> [!NOTE]
> Om WDRT inte identifierar dina HoloLens provar du att starta om datorn. Om det inte fungerar väljer du **Min enhet har inte identifierats,** väljer **Microsoft HoloLens** och följer sedan anvisningarna.

## <a name="reset-to-factory-settings"></a>Återställa till fabriksinställningarna

> [!NOTE]
> Batteriet behöver minst en 40-procentig avgift för att återställas.

Om ditt HoloLens fortfarande har problem kan du försöka återställa det till fabrikstillstånd. Det här steget behåller versionen av Windows Holographic-programvara som är installerad på den och returnerar allt annat till fabriksinställningarna.

>[!WARNING]
> Om du återställer enheten raderas alla personliga data, appar och inställningar, inklusive information om TPM-återställning. Återställning installerar endast den senaste installerade versionen av Windows Holographic. Du måste göra om alla initieringssteg (kalibrera, ansluta till Wi-Fi, skapa ett användarkonto, ladda ned appar och så vidare).

1. Öppna appen Inställningar och välj sedan **Uppdatera**  >  **återställning.**
1. Välj alternativet **Återställ enhet** och läs bekräftelsemeddelandet.
1. Bekräfta återställningen. Enheten startar om och visar en uppsättning snurrande kugghjul och en förloppsstapel.
1. Vänta ungefär 30 minuter på att den här processen ska slutföras. När det är klart startas enheten om till "out-of-the-box"-upplevelsen.

## <a name="reinstall-the-operating-system"></a>Installera om operativsystemet

Om enheten fortfarande har problem efter omstart och återställning kan du använda ett återställningsverktyg på datorn för att installera om HoloLens operativsystem och inbyggd programvara.  

De data HoloLens behöver för återställningen paketeras i en fullständig Flash-uppdatering (FFU), som liknar en ISO-, WIM- eller VHD-fil. [Läs mer om FFU-bildfilformat.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Du kan installera ett nytt operativsystem på din HoloLens (första generationen) med hjälp av Windows Device Recovery Tool. Innan du använder verktyget bör du se om det löser problemet genom HoloLens starta om eller återställa datorn.

Återställningsprocessen kan ta en stund. När det är klart installeras den senaste versionen Windows Holographic-programvara.

Om du vill använda verktyget behöver du en dator Windows 10 eller senare med minst 4 GB ledigt lagringsutrymme. Du kan inte köra det här verktyget på en virtuell dator.

### <a name="recover-your-hololens"></a>Återställa HoloLens

1. Ladda ned och installera [Windows Device Recovery-verktyget](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) på datorn.
1. Anslut HoloLens (1:a gen) till datorn med hjälp av Micro USB-kabeln som medkom med HoloLens.
1. Öppna Windows Device Recovery och följ anvisningarna.

Om HoloLens (1:a gen) inte identifieras automatiskt väljer du **Min enhet identifierades inte.** Följ sedan anvisningarna för att föra enheten i återställningsläge.

### <a name="manual-flashing-mode"></a>Manuellt flashläge

Om enheten inte identifieras följer du dessa steg för att föra den i flashläge:

1. Koppla från enheten från valfri strömkälla.
1. Om enheten är på håller du ned **strömknappen** tills den stängs av helt.
2. Håll volymen **uppåt och** tryck en kort stund **på strömknappen.** Enheten bör endast starta och visa den mittersta lysdioden.
3. Anslut enheten till datorn.
4. Öppna Windows Device Recovery.
5. Välj **Min enhet har inte identifierats** och välj **HoloLens**. 
6. Följ instruktionerna för att återställa enheten.
