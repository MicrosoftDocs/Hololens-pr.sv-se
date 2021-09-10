---
title: Starta om, återställa eller återställa HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Använda Advanced Recovery Companion för att flasha en bild till HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: e9aad32891bb093cbce18671b76549788b19afcb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427298"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Starta om, återställa eller återställa HoloLens 2

>[!IMPORTANT]
> Innan du startar en felsökningsprocedur bör du se till att enheten debiteras **till 20 till 40 procent** av batterikapaciteten om det är möjligt. Batteriindikatorn [som finns](hololens2-setup.md#lights-that-indicate-the-battery-level) under strömknappen är ett snabbt sätt att kontrollera batterikapaciteten utan att logga in på enheten.

Använd kabeln [och USB Type-C-kabeln](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) som med HoloLens 2 eftersom det är det bästa sättet att ladda enheten. Nätaggregatet levererar 18 W ström (9V vid 2A). Med medföljande väggutrustning kan HoloLens 2 enheter ladda upp batteriet till full på mindre än 65 minuter när enheten är i vänteläge. Om tillbehören inte är tillgängliga kontrollerar du att de tillgängliga tillbehören har stöd för minst 15 W ström.

> [!NOTE]
> Om möjligt bör du undvika att använda en dator för att debitera enheten via USB, vilket är långsamt.

Om enheten är korrekt startad och körs finns det tre sätt att kontrollera batteriladdningsnivån:

- På huvudmenyn i HoloLens enhetens användargränssnitt.
- Visa lysdioden nära strömknappen (för en avgift på 40 procent bör du se minst två solida lysdioder).
    - När enheten laddas tänds batteriindikatorn för att ange den aktuella avgiftsnivån.  Det sista lampan tonas in och ut för att indikera aktiv laddning.
    - När din HoloLens är på visar batteriindikatorn batterinivån i fem steg.
    - När bara en av de fem lamporna är på är batterinivån under 20 procent.
    - Om batterinivån är kritiskt låg och du försöker slå på enheten blinkar en lampa en kort stund och går sedan ut.
- På värddatorn öppnar du **Utforskaren** och letar efter din HoloLens 2-enhet till vänster under **Den här datorn**. Högerklicka på enheten och välj **Egenskaper.** En dialogruta visar batteriladdningsnivån.

   ![En HoloLens 2-egenskapsskärm visar batteriändringsnivå.](images/ResetRecovery2.png)

Observera LED-utseendet och enhetsuppräkningen på värddatorn om enheten inte kan starta på startmenyn. Följ sedan [felsökningsguiden](hololens-troubleshooting.md). Om enhetens tillstånd inte matchar något av tillstånden som anges [](hololens-recovery.md#hard-reset-procedure) i felsökningsguiden utför du proceduren för hårdåterställning med enheten som är ansluten till strömförsörjningen, inte till din värddator. Vänta minst en timme på att enheten ska debiteras.

## <a name="reset-the-device"></a>Återställa enheten

Under vissa omständigheter kan du behöva återställa enheten manuellt utan att använda användargränssnittet för programvaran.

### <a name="standard-procedure"></a>Standardprocedur

1. Koppla från Type-C-kabeln för att koppla bort enheten från strömförsörjningen eller värddatorn.

2. Tryck och håll ned **strömknappen** i 15 sekunder. Alla lysdioder ska vara avstängda.

3. Vänta 2–3 sekunder och tryck sedan kort på **strömknappen.** Lysdioderna nära strömknappen tänds och enheten börjar starta.

4. Anslut enheten till värddatorn och öppna sedan Enhetshanteraren. (För Windows 10 trycker du **Windows** tangenten och sedan **på X** och väljer sedan **Enhetshanteraren**.) Kontrollera att enheten räknas upp korrekt enligt *Microsoft HoloLens* som visas i följande bild:

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedur för hård återställning

Om standardåterställningen inte fungerade använder du proceduren för hård återställning:

1. Koppla från Type-C-kabeln för att koppla bort enheten från strömförsörjningen eller värddatorn.

1. Håll ned **strömknapparna**  +  **för volymen** i 15 sekunder. Enheten startas om automatiskt.

1. Anslut till värddatorn.

1. Öppna Enhetshanteraren (för Windows 10 trycka **Windows** tangenten och sedan **på X-tangenten** och välj sedan **Enhetshanteraren**). Kontrollera att enheten räknas upp korrekt enligt *Microsoft HoloLens* som visas i följande bild:

   ![HoloLens 2 MicrosoftHoloLensRecovery device maanger 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Rensa omstreck på enheten

I svåra situationer kan du behöva "rensa flash"-HoloLens 2. Observera att clean-reflash inte förväntas påverka följande problem:

- [Visa färguniformitet](hololens2-display.md)
- Starta med ljud men inga visningsutdata
- [1-3-5-LED-mönster](hololens2-setup.md#lights-to-indicate-problems)
- [Överhettning](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- OS-krascher (som skiljer sig från programkrascharna)

Det finns två sätt att omsnedstrecka enheten. För båda måste du först [installera Advanced Recovery Companion från Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Om du omskär enheten raderas alla personliga data, appar och inställningar, inklusive TPM-återställningsinformation.

Som standard är Advanced Recovery Companion inställt på att ladda ned den senaste versionen av funktionen. Om du vill veta mer om den senaste [funktionsutgå HoloLens 2 viktig information.](hololens-release-notes.md) Hämta det senaste paketet HoloLens 2 Full Flash Update (FFU) för att omsnedstrecka enheten via Advanced Recovery Companion genom att ladda ned den senaste månatliga HoloLens 2-avbildningen: [https://aka.ms/hololens2download](https://aka.ms/hololens2download) . Den här versionen är den senaste allmänt tillgängliga versionen.

Innan du startar omstrecksproceduren kontrollerar du att appen är installerad och körs Windows 10 datorn och redo att identifiera enheten. Kontrollera också att HoloLens debiteras till minst 40 %.

![HoloLens två rena omstrecksskärmbild.](images/ARC1.png)

### <a name="normal-procedure"></a>Normal procedur

1. När HoloLens körs ansluter du den till den Windows 10 datorn där du tidigare öppnade appen Advanced Recovery Companion.

   Enheten identifieras automatiskt och användargränssnittet för appen Advanced Recovery startar uppdateringsprocessen:

   ![HoloLens 2 rensade omstreck första skärmen.](images/ARC2.png)

1. Välj enheten HoloLens 2 i appen Advanced Recovery Companion och följ instruktionerna för att slutföra omstrecket.

### <a name="manual-procedure"></a>Manuell procedur

Du kan behöva föra in enheten i återställningsläge om:

- Den HoloLens 2 startar inte korrekt
- Advanced Recovery Companion kan inte identifiera enheten
- Du känner inte längre till lösenordet/PIN-koden för en enhet som bara har en enda användare

1. Koppla från Type-C-kabeln för att koppla bort enheten från strömförsörjningen eller värddatorn.

2. Tryck och håll ned **strömknappen** i 15 sekunder. Alla lysdioder bör stängas av.

3. När du trycker **på knappen för** att öka volymen trycker du på och släpper **strömknappen** för att starta enheten. Vänta i 15 sekunder och släpp sedan **volymen upp.** Endast den mittersta leden av de fem lysdioderna tänds.

4. Anslut enheten till värddatorn och öppna Enhetshanteraren. (För Windows 10 trycker **du Windows** tangenten och sedan **på X** och väljer sedan **Enhetshanteraren**.) Kontrollera att enheten räknas upp korrekt enligt Microsoft HoloLens som visas i följande bild:

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   Enheten identifieras automatiskt och användargränssnittet för appen Advanced Recovery startar uppdateringsprocessen:

   ![HoloLens 2 ren omstrecksskärm.](images/ARC2.png)

6. Välj enheten HoloLens 2 i appen Advanced Recovery Companion och följ sedan anvisningarna för att slutföra omstrecket.

## <a name="troubleshoot-advanced-recovery-companion"></a>Felsöka Advanced Recovery Companion

1. Se till att din enhet debiteras till 40 % eller mer innan du försöker flasha.

1. Kontrollera att enheten är upplåst.

1. Kontrollera att enheten är ansluten direkt till värddatorn, inte en hubb.

1. Om enheten inte visas som en återställningsenhet HoloLens/HoloLens under Drivrutiner för universella seriebussdrivrutiner kontrollerar du:
    1. **Portar**, som en Qualcomm HS-USB-enhet
    1. **Andra enheter**, som en QUSB_BULK enhet – värddatorn saknar nödvändiga drivrutiner för att identifiera HoloLens. Högerklicka och välj Uppdatera drivrutin och sök efter drivrutiner online eller [markera Valfria uppdateringar i Windows Uppdatera inställningar.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674) När drivrutinen har laddats ned ska ARC kunna identifiera den.

1. Om ARC inte identifierar din enhet ser du till att du kan ansluta till enheten via Utforskaren på datorn. Om du inte kan;

    1. Det är möjligt att enheten har USB-principer som inaktiverar anslutningen. I så fall kan [du prova manuellt flashläge](hololens-recovery.md#manual-procedure).
    2. Om det inte finns några principer kan du prova en annan USB-kabel.

1. Kontrollera att enheten inte visar ett [1-3-5-LED-mönster.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Ladda ned ARC utan att använda App Store

Om IT-miljön förhindrar användning av Windows Store-appen eller begränsar åtkomsten till butiken, kan IT-administratören göra den här appen tillgänglig via en "offline"-distributionssökväg.

 >[!NOTE]
 > - IT-administratörer kan också distribuera den här appen via System Center Configuration Manager (SCCM) eller Intune.
 > - Den här guiden fokuserar på Advanced Recovery Companion, men processen kan även användas för andra "offline"-appar.

Följ dessa steg för att aktivera distributionssökvägen:

1. Gå till [Microsoft Store för företag](https://businessstore.microsoft.com) och logga in med en Azure Active Directory identitet.

1. Gå till **Hantera – Inställningar**. Aktivera Visa **offlineappar** under **Shoppingupplevelse.**

1. Gå till **butiken för min grupp** och sök efter Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Ändra **Licenstyp till** **_offline_*_, och välj _* Hantera**.

1. Under **Ladda ned paketet för offlineanvändning** väljer du den andra blå **nedladdningsknappen.** Kontrollera att filnamnstillägget är *.appxbundle*.

    - Om skrivbordsdatorn i det här skedet har Internetåtkomst dubbelklickar du på paketet för att installera appen.

    - Om måldatorn inte har någon Internetanslutning följer du dessa steg:
       1. Välj den okodade licensen och välj sedan **Generera licens.**
       2. Under **Nödvändiga ramverk väljer** du Ladda **ned**.
       3. Använd DISM för att tillämpa paketet med beroendet och licensen. Kör följande kommando från en administratörs kommandotolk:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Versionsnumret i det här kodexe exemplet kanske inte matchar den tillgängliga versionen. Du kan också ha valt en annan nedladdningsplats än i exemplet. Gör eventuella ändringar i kommandot efter behov.

> [!TIP]
> När du planerar att använda Advanced Recovery Companion för att installera en FFU offline kan det vara användbart att ladda ned flash-avbildningen. [**Ladda ned den aktuella avbildningen för HoloLens 2**](https://aka.ms/hololens2download).

Andra resurser:

- [Distribuera offlineappar](/microsoft-store/distribute-offline-apps) 
- [DISM-appaket (.appx eller .appxbundle) för kommandoradsalternativ](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
