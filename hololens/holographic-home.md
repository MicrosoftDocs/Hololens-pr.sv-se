---
title: Använda Start-menyn och mixad verklighet
description: Lär dig hur du använder Start-menyn, hanterar och får åtkomst till appar och navigerar hem för mixad verklighet HoloLens enheter.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427217"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Använda Start-menyn och mixad verklighet

Precis som Windows datorupplevelsen börjar med skrivbordet börjar Windows Holographic med mixad verklighet.  Med hjälp Start-menyn kan du öppna och placera appfönster, integrerande appstartare och 3D-innehåll i mixed reality-hemmet, och deras placering i ditt fysiska utrymme kommer att sparas.

## <a name="use-the-start-menu"></a>Använd Start-menyn

Det Start-menyn på HoloLens är där du öppnar appar, ser viktig statusinformation och har åtkomst till verktyg som kameran.

Oavsett var du befinner dig HoloLens kan du alltid öppna Start-menyn med hjälp av **startgesten**.  På HoloLens (1:a gen) är startgesten [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures). På HoloLens 2 är [gesten Start](hololens2-basic-usage.md#start-gesture) att trycka på startikonen som visas vid handleden.  Du kan också öppna Start-menyn med din röst genom att säga "Gå till start".

> [!TIP]
> När Start-menyn är öppen använder du gesten Start för att stänga den eller tittar på Start-menyn säger "Stäng".

Längst upp i Start-menyn visas statusindikatorer för Wi-Fi, batteri, volym och klocka. På HoloLens 2 finns det också en lyssningsindikator som visar om enheten är talaktiverad och lyssnar efter röstkommandon. Längst ned hittar du knapparna **Foto och** **Video** där du kan ta foton och videoinspelningar.  Det finns också en **Anslut** som gör att du kan projicera vad du ser för en annan enhet med Miracast.

### <a name="find-apps-on-start-menu"></a>Hitta appar på Start-menyn

Listan Start-menyn har en **lista över fästa** appar och en **Alla appar** lista.

- Listan **Fästa appar** visar appar som har fästs. Du kan lägga till och ta bort appar från **listan** Fästa appar med hjälp av snabbmenyn som visas när du väljer **och håller ned** en appanel.

- Listan **Alla appar** visar alla appar som är installerade på enheten.  Välj knappen **Alla appar** till höger på **Start-menyn** för att komma till listan.

I båda applistorna använder du knapparna Page **up** (Sida upp) och **Page down** (Sida ned) till höger i Start-menyn för att bläddra igenom alla appar i listan.  Båda applistorna öppnas automatiskt på sidan som senast användes under en enhetssession.

> [!TIP]
> På HoloLens 2 kan du bläddra direkt i applistorna med hjälp av ditt indexfingr. Rör bara listan med fingertipset och dra uppåt eller nedåt.

### <a name="open-apps-from-start-menu"></a>Öppna appar från Start-menyn

Om du vill öppna en app Start-menyn väljer du **bara** en **appanel.** Du kan också ange namnet på en app för att öppna den.

När du öppnar en app från Start-menyn sker något av följande, beroende på hur appen är utformad:

- Ett **appfönster** placeras. Appen läses sedan in i fönstret och du kan använda den som en pekskärm.
- En **3D-appstartare** för en avancerad app placeras. Du måste sedan välja **startprogrammet** för att öppna den integrerande appen.
- Ett appfönster placeras som fungerar som **startfönster för** en integrerande app. Den integrerande appen fortsätter att starta automatiskt.

Appfönster och appstartare som placerats i mixed reality-hemmet stannar kvar tills du bestämmer dig för att ta bort dem.  De ger dig en praktisk genväg i världen för att använda dessa appfönster eller för att starta integrerande appar utan att behöva öppna dem igen från Start-menyn. 

> [!NOTE]
>Precis som på en telefon hanteras systemresurser automatiskt på HoloLens.  När du till exempel öppnar en ny avancerad app blir alla andra appar som körs omedelbart inaktiva. Du behöver inte ta bort appfönster och startfönster i mixad verklighet för att frigöra systemresurser. 

## <a name="using-apps-on-hololens"></a>Använda appar på HoloLens

Appar på HoloLens kan använda appfönstervyn eller avancerad vy. Med appfönstervyn visar appen bara dess innehåll i ett fönster. Med avancerad vy tar en app dig bort från det blandade verkliga hemmet där den sedan kan visa sitt innehåll i den fysiska miljön runt omkring dig. Appar kan också välja att använda båda vyerna.

### <a name="use-app-windows"></a>Använda appfönster

På HoloLens (första generationens) appfönster placeras och används i mixed reality-hemmet, där du kan [flytta,](hololens1-basic-usage.md#move-resize-and-rotate-apps) ändra storlek på och rotera dem som du vill. Förutom att använda appfönster med blick och gest kan du också använda dem med Bluetooth mus och tangentbord.

På HoloLens 2 kan du, förutom att använda appfönster i Mixed Reality Home, även använda ett appfönster i taget i en integrerande app. Du kan också placera ett appfönster **i Läget** Följ mig där det kommer att stå framför dig när du går runt. När du öppnar ett appfönster i en integrerande app öppnas det i **Läget Följ** mig automatiskt. Du kan [flytta, ändra storlek på och rotera](hololens2-basic-usage.md#move-resize-and-rotate-holograms) appfönster direkt med dina händer i både mixed reality-hemmet och inuti en integrerande app.

> [!NOTE]
>
> - Upp till tre appfönster kan vara aktiva i mixad verklighet i taget. Du kan öppna fler, men endast tre förblir aktiva.
> - När ett appfönster inte är aktivt visas innehåll som ser mörkare ut jämfört med ett aktivt fönster.  Vissa visar bara appikonen i stället för något innehåll.  Om du vill aktivera ett inaktivt fönster markerar **du det.**
> - Varje öppen app kan ha ett aktivt fönster i taget, Microsoft Edge kan ha upp till tre.

### <a name="close-apps"></a>Stäng appar

Om du vill stänga en app som använder ett appfönster stänger du bara appfönstret med **knappen** Stäng i namnlisten.  Du kan också titta på fönstret och säga "Stäng".

Om du vill avsluta en app som använder avancerad vy använder du gesten Start för **att öppna Start-menyn** och väljer sedan **hemknappen Mixed reality.**

Om en integrerande app är i ett brutet tillstånd och du behöver starta om den, kan du se till att appen först stängs helt genom att stänga startprogrammet i mixed reality-hemmet och sedan starta den från Start-menyn.

### <a name="default-app-picker"></a>Standardappväljare

Med [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)visas ett nytt fönster öppet där du uppmanas att välja vilken installerad app som ska hantera fil- eller länktypen när du aktiverar en hyperlänk eller öppnar en filtyp med mer än en installerad app. I det här fönstret kan du också välja att den valda appen ska hantera filen eller länktypen "En gång" eller "Alltid".

![Fönstret Appväljare.](images/default-app-picker.png)

Om du väljer "Alltid" men senare vill ändra vilken app som hanterar en viss fil- eller länktyp kan du återställa dina sparade standardvärden **i Inställningar > Appar**. Rulla längst ned på sidan och välj knappen **Rensa** under "Standardappar för filtyper" och/eller "Standardappar för länktyper". Till skillnad från liknande inställning på stationära datorer kan du inte återställa standardvärden för enskilda filtyper.

### <a name="per-app-volume-control"></a>Volymkontroll per app

Med [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)kan användarna justera volymnivån för varje app manuellt. På så sätt kan användarna bättre fokusera på de appar som de behöver, eller bättre höra när de använder flera appar. Till exempel att behöva stänga av volymen för en app när en annan person anropas för fjärrhjälp i en annan.

Om du vill ange volymen för en enskild app **går du Inställningar** systemljud och under Avancerade ljudalternativ väljer du  ->    ->   **Appvolym och enhetsinställningar.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Relaterad information

[Hitta, installera och avinstallera program från Microsoft Store](holographic-store-apps.md)
