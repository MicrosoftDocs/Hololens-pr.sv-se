---
title: Hantera HoloLens-uppdateringar
description: Lär dig hur dina administratörer kan använda hantering av mobila enheter för att hantera uppdateringar av HoloLens-enheter.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: faa6bb2b095d69c3538063b1c042c5ce5e215d33
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924085"
---
# <a name="manage-hololens-updates"></a>Hantera HoloLens-uppdateringar

HoloLens använder Windows Update på samma sätt som andra Windows 10 enheter. När en uppdatering är tillgänglig laddas den ned och installeras automatiskt nästa gång enheten är ansluten till Internet. Den här artikeln beskriver hur du hanterar uppdateringar i ett företag eller en annan hanterad miljö. Information om hur du hanterar uppdateringar av enskilda HoloLens-enheter finns i [Uppdatera HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Hantera uppdateringar automatiskt

### <a name="managing-updates-by-using-windows-update-for-business"></a>Hantera uppdateringar med hjälp av Windows Update för företag

Windows Holographic for Business kan använda [Windows Update för företag](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) för att hantera uppdateringar. Alla HoloLens 2-enheter kan använda Windows Holographic for Business. Se till att de använder Windows Holographic for Business version 10.0.18362.1042 eller en senare version. Om du har HoloLens-enheter (första generationen) måste du uppgradera dem till [Windows Holographic for Business](hololens1-upgrade-enterprise.md) för att kunna hantera deras uppdateringar.

Windows Update för företag ansluter HoloLens-enheter direkt till Windows Update tjänsten. Med hjälp Windows Update för företag kan du styra flera aspekter av uppdateringsprocessen, det vill säga vilka enheter &mdash; som får vilka uppdateringar vid vilken tidpunkt. Du kan till exempel distribuera uppdateringar till en delmängd av enheterna för testning och sedan distribuera uppdateringar till de återstående enheterna senare. Eller så kan du definiera olika uppdateringsscheman för olika typer av uppdateringar.

> [!NOTE]  
> För HoloLens-enheter kan du automatiskt hantera funktionsuppdateringar (släpps två gånger per år) och kvalitetsuppdateringar (släpps varje månad eller efter behov, inklusive kritiska säkerhetsuppdateringar). Mer information om uppdateringstyper finns i [Typer av uppdateringar som hanteras av Windows Update för företag](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Du kan konfigurera Windows Update för företag för HoloLens med hjälp av principer i en MDM-lösning (Mobile Enhetshantering), till exempel Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Hantera Windows Update för företag med hjälp av Microsoft Intune

En detaljerad beskrivning av hur du använder Intune för att konfigurera Windows Update för företag finns i [Hantera Windows 10-programuppdateringar i Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Mer information om de specifika Intune-funktioner som HoloLens stöder finns i [Intune-uppdateringshanteringsfunktioner som HoloLens stöder.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Intune har två principtyper för att hantera *uppdateringar: Windows 10 uppdateringsring* *och Windows 10 funktionsuppdatering.* Den Windows 10 av principtypen funktionsuppdatering är i offentlig förhandsversion just nu och stöds inte för HoloLens.
>  
> Du kan använda Windows 10 för att hantera HoloLens 2-uppdateringar.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurera uppdateringsprinciper för HoloLens 2 eller HoloLens (första generationen)

I det här avsnittet beskrivs de principer som du kan använda för att hantera uppdateringar för HoloLens 2 eller HoloLens (första generationen). Mer information om de funktioner som är tillgängliga för HoloLens 2 finns i Planera och konfigurera [uppdateringslanser för HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[Princip-CSP – Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definierar de principer som konfigurerar Windows Update för företag.

> [!NOTE]  
> En lista över specifika leverantörer av principkonfigurationstjänster (CPS) som stöds av specifika utgåvor av HoloLens finns i Princip-CPS som stöds av [HoloLens-enheter.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurera automatiska kontroller för uppdateringar

Du kan använda **principen Update/AllowAutoUpdate** för att hantera automatiska uppdateringsbeteenden, till exempel genomsökning, hämtning och installation av uppdateringar. Mer information om de tillgängliga inställningarna för den här principen finns [i Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> I Microsoft Intune kan du använda Beteende **för automatisk uppdatering för** att ändra den här principen. Mer information finns i [Hantera Windows 10 programuppdateringar i Intune.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Konfigurera ett uppdateringsschema

Använd följande principer för att konfigurera hur och när uppdateringar ska tillämpas:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Värden: **0**–**7** (0 = varje dag, 1 = söndag, 7 = lördag)
  - Standardvärde: **0** (varje dag)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Värden: 0–23 (0 = midnatt, 23 = 23 = 23:00)
  - Standardvärde: 03:00

#### <a name="configure-active-hours"></a>Konfigurera aktiva timmar
Från och [med Windows Holographic, version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) kan en IT-administratör ange intervallet för aktiva timmar för HoloLens 2-enheter.

Aktiva timmar identifierar den tidsperiod då du förväntar dig att enheten ska användas. Automatiska omstarter efter en uppdatering sker utanför de aktiva timmarna. Det angivna intervallet räknas från starttiden för aktiva timmar. Du kan använda MDM enligt beskrivningen i [Konfigurera aktiva timmar med MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM använder inställningarna Update/ActiveHoursStart och Update/ActiveHoursEnd och Update/ActiveHoursMaxRange i CSP-princip för att konfigurera aktiva timmar.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) – Det här värdet anger sluttiden. Det finns högst 12 timmar från starttiden.
    -   Värden som stöds är 0–23, där 0 är 12:00, 1 är 01:00 osv.
    -   Standardvärdet är 17 (17:00).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Det här värdet anger maximalt antal aktiva timmar från starttiden.
    -   Värden som stöds är 8–18.
    -   Standardvärdet är 18 (timmar).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Det här värdet anger starttiden. Det finns en maxtid på 12 timmar från sluttiden.
    -   Värden som stöds är 0–23, där 0 är 12:00, 1 är 01:00 osv.
    -   Standardvärdet är 8 (08:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Endast för enheter Windows 10 version 1607

Du kan använda följande uppdateringsprinciper för att konfigurera enheter för att hämta uppdateringar från Windows Server Update Service (WSUS), i stället för från Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planera och konfigurera uppdateringslanser för HoloLens 2

HoloLens 2 stöder fler funktioner för uppdateringsautomatisering än Vad HoloLens (första generationen) har. Detta gäller särskilt om du använder Microsoft Intune för att hantera Windows Update för företag principer. De här funktionerna gör det enklare för dig att planera och implementera uppdateringsutrullningar i hela organisationen.

#### <a name="plan-the-update-strategy"></a>Planera uppdateringsstrategin

Windows Updates for Business stöder upp skjuta upp principer. När Microsoft släpper en uppdatering kan du använda en upp skjuta upp-princip för att definiera hur lång tid som ska vänta innan du installerar uppdateringen på enheter. Genom att associera delmängder av dina enheter (även kallade uppdateringsringar) med olika upplåsningsprinciper kan du samordna en strategi för uppdateringsutgivning för din organisation.

Tänk dig till exempel en organisation som har 1 000 enheter och som måste uppdatera enheterna i fem vågor. Organisationen kan skapa fem uppdateringsringar, som du ser i följande tabell.

|Group |Antal enheter |Upp skjuta upp (dagar) |
| ---| :---: | :---: |
|Grp 1 (IT-personal) |5 |0 |
|Grp 2 (tidiga införare) |50 |60 |
|Grp 3 (huvud 1) |250 |120 |
|Grp 4 (huvud 2) |300 |150 |
|Grp 5 (huvud 3) |395 |180 |

Så här går processen över tid till hela organisationen.

![Tidslinje för att distribuera uppdateringar](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurera en princip för upp skjuta upp uppdateringar

En uppseningsprincip anger antalet dagar mellan det datum då en uppdatering blir tillgänglig och det datum då uppdateringen erbjuds till en enhet.

Du kan konfigurera olika upp skjuta upp för funktionsuppdateringar och kvalitetsuppdateringar. I följande tabell visas de specifika principer som ska användas för varje typ och den maximala upp skjuta upp för var och en.

|Kategori |Policy |Maximal upp skjuta upp |
| --- | --- | --- |
|Funktionsuppdateringar |DeferFeatureUpdatesPeriodInDays |365 dagar |
|Kvalitetsuppdateringar |DeferQualityUpdatesPeriodInDays |30 dagar |

#### <a name="pause-updates-via-device"></a>Pausa uppdateringar via enhet

Om en användare inte har åtkomst till MDM kan de pausa uppdateringar individuellt i upp till 35 dagar manuellt på en HoloLens 2-enhet på [Windows Holographic-version 2004](hololens-release-notes.md#windows-holographic-version-2004) eller senare. Användarna kan nå den här inställningen genom att gå till Inställningar > Update &  Security > Advanced **options** (Avancerade alternativ) för att bläddra ned till Pausa uppdateringar och välja det datum tills de ska pausa uppdateringar. När en användare har nått pausgränsen måste enheten få nya uppdateringar innan de kan pausa igen. 

Från och [med Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2)kan den här funktionen för pausuppdateringar hanteras för HoloLens 2-enheter. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (standard) – Aktiverad
    - 1 – Inaktiverad

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Intune-uppdateringshanteringsfunktioner som HoloLens stöder

Du kan använda följande funktioner för Uppdateringshantering i Intune för att hantera uppdateringar för HoloLens.

- **Skapa** och **tilldela:** Dessa funktioner lägger till Windows 10 en uppdateringsring i listan över uppdateringsringar. Mer information finns i Skapa [och tilldela uppdateringsringar.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Pausa:** Om du stöter på problem när du distribuerar en funktion eller kvalitetsuppdatering kan du pausa uppdateringen i 35 dagar (från ett angivet datum). Den här pausen förhindrar att andra enheter installerar uppdateringen förrän du har löst eller åtgärdat problemet. Om du pausar en funktionsuppdatering erbjuds kvalitetsuppdateringar fortfarande till enheter för att säkerställa att de förblir säkra. När en uppdateringstyp har pausats visar översiktsfönstret för den ringen hur många dagar som återstår innan uppdateringstypen återupptas. När den angivna tiden har passerat upphör pausen automatiskt att gälla och uppdateringsprocessen återupptas.

  När uppdateringsringen har pausats kan du välja något av följande alternativ:

  - **Utöka**: Utöka pausperioden för en uppdateringstyp i 35 dagar.
  - **Återuppta:** Återställ uppdateringar för den ringen till aktiv åtgärd. Du kan pausa uppdateringsringen igen om det behövs.

  > [!NOTE]  
  > Avinstallationsåtgärden för uppdateringsringar stöds inte för HoloLens 2-enheter. 

### <a name="delivery-optimization-preview"></a>Leveransoptimering förhandsversion

[Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) har aktiverat en tidig förhandsversion för leveransoptimeringsinställningar för att minska bandbreddsförbrukningen för nedladdningar från flera HoloLens-enheter. En mer fullständig beskrivning av den här funktionen tillsammans med den rekommenderade nätverkskonfigurationen finns här: [Leveransoptimering för Windows 10 uppdateringar](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Följande inställningar är aktiverade som en del av hanteringsytan [och kan konfigureras från Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Några varningar om det här förhandsversionserbjudandet:

- Stödet för HoloLens är begränsat i den här förhandsversionen till enbart OS-uppdateringar.
- Windows Holographic for Business stöder endast HTTP-nedladdningslägen och nedladdningar från en [Microsoft Ansluten cache slutpunkt](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); peer-to-peer-nedladdningslägen och grupptilldelningar stöds inte för HoloLens-enheter för närvarande.
- HoloLens stöder inte distribution eller leveransoptimering för Windows Server Update Services slutpunkter.
- Felsökning kräver antingen diagnostik på Ansluten cache-servern eller insamling av en spårning på HoloLens på HoloLens **via** Inställningsuppdatering  >  **& Säkerhetsfelsökning**  >     >   **Windows Update**.

## <a name="manually-check-for-updates"></a>Söka efter uppdateringar manuellt

Även om HoloLens regelbundet söker efter systemuppdateringar kan det finnas omständigheter då du vill kontrollera detta manuellt.

Om du vill söka efter uppdateringar manuellt går du  >  **till Inställningar uppdatera &**  >  **säkerhetskontroll för uppdateringar.** Om appen Inställningar visar att enheten är uppdaterad har du alla uppdateringar som är tillgängliga för tillfället.

## <a name="manually-roll-back-an-update"></a>Återställa en uppdatering manuellt

I vissa fall kanske du vill återgå till en tidigare version av HoloLens-programvaran. Processen för att göra detta beror på om du använder HoloLens 2 eller HoloLens (första gen).

### <a name="revert-to-a-previous-version-hololens-2"></a>Återgå till en tidigare version (HoloLens 2)

Du kan återställa uppdateringar och återgå till en tidigare version av HoloLens 2 med hjälp av [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) för att återställa HoloLens till den tidigare versionen.

> [!NOTE]
> Om du återgår till en tidigare version tas dina personliga filer och inställningar bort.

Följ dessa steg om du vill återgå till en tidigare version av HoloLens 2:

1. Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.
1. På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.
1. Ladda ned [den senaste HoloLens 2-versionen](https://aka.ms/hololens2download).
1. När dessa hämtningar är klara öppnar du Filutforskaren Nedladdningar, högerklickar på den komprimerade (.zip) mapp som du precis har laddat ned och väljer extrahera alla extrahera för att expandera  >     >   filen.
1. Använd en USB-A till USB-C-kabel för att ansluta HoloLens-enheten till datorn. Även om du har använt andra kablar för att ansluta din HoloLens fungerar den här typen av kabel bäst.
1. Advanced Recovery Companion identifierar automatiskt din HoloLens-enhet. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuell paketval** och öppnar sedan mappen som du expanderade tidigare.
1. Välj installationsfilen (.ffu).
1. Välj **Installera programvara** och följ sedan anvisningarna.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Återgå till en tidigare version (HoloLens (första gen))

Du kan återställa uppdateringar och återgå till en tidigare version av HoloLens (första generationen) med hjälp av [Windows Device Recovery Tool (WDRT) för](https://support.microsoft.com/help/12379) att återställa HoloLens till den tidigare versionen.

> [!NOTE]
> Om du återgår till en tidigare HoloLens-version tas dina personliga filer och inställningar bort.

Följ dessa steg om du vill återgå till en tidigare version av HoloLens (första generationen):

1. Kontrollera att du inte har några telefoner eller Windows-enheter anslutna till datorn.
1. Ladda ned Windows [Device Recovery Tool (WDRT) på datorn.](https://support.microsoft.com/help/12379)
1. Ladda ned [holoLens Anniversary Update-återställningspaketet](https://aka.ms/hololensrecovery).
1. När hämtningarna är klara öppnar du Filutforskaren Nedladdningar, högerklickar på den komprimerade (.zip) mapp som du precis har laddat ned och väljer extrahera alla extrahera för att expandera  >     >   filen.
1. Använd mikro-USB-kabeln som tillhandahölls tillsammans med din HoloLens-enhet för att ansluta HoloLens-enheten till datorn. Även om du har använt andra kablar för att ansluta din HoloLens-enhet fungerar den här bäst.
1. WDRT identifierar automatiskt din HoloLens-enhet. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuell paketval** och öppnar sedan mappen som du expanderade tidigare.
1. Välj installationsfilen (.ffu).
1. Välj **Installera programvara** och följ sedan anvisningarna.

**Om WDRT inte identifierar din enhet**

Om WDRT inte identifierar HoloLens-enheten kan du prova att starta om datorn. Om det inte fungerar väljer du **Min enhet identifierades inte,** **Microsoft HoloLens** och följer sedan anvisningarna.

## <a name="related-articles"></a>Relaterade artiklar

- [Information om HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Vad är Windows Update för företag?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Tilldela enheter till underhållskanaler för Windows 10 uppdateringar](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Hantera Windows 10-programuppdateringar i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
