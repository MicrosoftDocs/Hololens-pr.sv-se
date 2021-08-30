---
title: Hantera HoloLens uppdateringar
description: Lär dig hur dina administratörer kan använda hantering av mobila enheter för att hantera uppdateringar HoloLens enheter.
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
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190046"
---
# <a name="manage-hololens-updates"></a>Hantera HoloLens uppdateringar

HoloLens använder Windows Update på samma sätt som andra Windows 10 enheter. När en uppdatering är tillgänglig laddas den ned och installeras automatiskt nästa gång enheten är ansluten till Internet. Den här artikeln beskriver hur du hanterar uppdateringar i ett företag eller en annan hanterad miljö. Information om hur du hanterar uppdateringar av enskilda HoloLens-enheter finns [i Uppdatera HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Hantera uppdateringar automatiskt

### <a name="managing-updates-by-using-windows-update-for-business"></a>Hantera uppdateringar med hjälp Windows Update for Business

Windows Holographic for Business kan använda [Windows Update för företag för](/windows/deployment/update/waas-manage-updates-wufb) att hantera uppdateringar. Alla HoloLens 2 enheter kan använda Windows Holographic for Business. Se till att de använder Windows Holographic for Business version 10.0.18362.1042 eller en senare version. Om du har HoloLens (första generationens) enheter måste du uppgradera dem till [Windows Holographic for Business](hololens1-upgrade-enterprise.md) för att kunna hantera deras uppdateringar.

Windows Uppdatering för företag ansluter HoloLens enheter direkt till Windows Update-tjänsten. Genom att Windows Update for Business kan du styra flera aspekter av uppdateringsprocessen, det vill säga vilka enheter som får &mdash; vilka uppdateringar vid vilken tidpunkt. Du kan till exempel distribuera uppdateringar till en delmängd av enheterna för testning och sedan distribuera uppdateringar till de återstående enheterna senare. Eller så kan du definiera olika uppdateringsscheman för olika typer av uppdateringar.

> [!NOTE]  
> För HoloLens-enheter kan du automatiskt hantera funktionsuppdateringar (släpps två gånger per år) och kvalitetsuppdateringar (släpps varje månad eller efter behov, inklusive kritiska säkerhetsuppdateringar). Mer information om uppdateringstyper finns i [Typer av uppdateringar som hanteras av Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Du kan konfigurera Windows Update för företag för HoloLens med hjälp av principer i en MDM-lösning (Mobile Enhetshantering), till exempel Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Hantera Windows Update för företag med hjälp av Microsoft Intune

En detaljerad diskussion om hur du använder Intune för att konfigurera Windows Update för företag finns i [Hantera Windows 10-programuppdateringar i Intune.](/intune/protect/windows-update-for-business-configure) Mer information om de specifika Intune-funktioner som HoloLens stöder finns i [Intune-uppdateringshanteringsfunktioner som HoloLens stöder](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune innehåller två principtyper för att hantera *uppdateringar: Windows 10 uppdateringsring* *och Windows 10 för funktionsuppdatering*. Principtypen Windows 10 för funktionsuppdatering är för närvarande i offentlig förhandsversion och stöds inte för HoloLens.
>  
> Du kan använda Windows 10 för uppdateringsring för att hantera HoloLens 2 uppdateringar.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurera uppdateringsprinciper för HoloLens 2 eller HoloLens (första generationen)

I det här avsnittet beskrivs de principer som du kan använda för att hantera uppdateringar för antingen HoloLens 2 eller HoloLens (första gen). Mer information om de funktioner som är tillgängliga för HoloLens 2 finns i Planera och konfigurera [uppdateringsutrullningar för HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[Princip-CSP – Update](/windows/client-management/mdm/policy-csp-update) definierar de principer som konfigurerar Windows Update for Business.

> [!NOTE]  
> En lista över specifika leverantörer av principkonfigurationstjänster (CPS) som stöds av specifika utgåvor av HoloLens finns i [Princip-CPS](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)som stöds av HoloLens enheter .

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurera automatiska kontroller för uppdateringar

Du kan använda **principen Update/AllowAutoUpdate** för att hantera automatiska uppdateringsbeteenden, till exempel genomsökning, nedladdning och installation av uppdateringar. Mer information om tillgängliga inställningar för den här principen finns [i Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> I Microsoft Intune kan du använda Beteende **för automatisk uppdatering för** att ändra den här principen. Mer information finns i [Hantera Windows 10-programuppdateringar i Intune.](/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Konfigurera ett uppdateringsschema

Använd följande principer för att konfigurera hur och när uppdateringar ska tillämpas:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Värden: **0**–**7** (0 = varje dag, 1 = söndag, 7 = lördag)
  - Standardvärde: **0** (varje dag)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Värden: 0–23 (0 = midnatt, 23 = 11 PM)
  - Standardvärde: 03:00

#### <a name="configure-active-hours"></a>Konfigurera aktiva timmar
Från och Windows Holographic kan en IT-administratör i [version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ange intervallet för aktiva timmar för HoloLens 2 enheter.

Aktiva timmar identifierar den tidsperiod då du förväntar dig att enheten ska användas. Automatiska omstarter efter en uppdatering sker utanför de aktiva timmarna. Det angivna intervallet räknas från starttiden för aktiva timmar. Du kan använda MDM enligt beskrivningen i [Konfigurera aktiva timmar med MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM använder inställningarna Update/ActiveHoursStart och Update/ActiveHoursEnd och Update/ActiveHoursMaxRange i CSP-principen för att konfigurera aktiva timmar.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) – Det här värdet anger sluttiden. Det finns högst 12 timmar från starttiden.
    -   Värden som stöds är 0–23, där 0 är 12:00, 1 är 01:00 osv.
    -   Standardvärdet är 17 (17:00).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Det här värdet anger maximalt antal aktiva timmar från starttiden.
    -   Värden som stöds är 8–18.
    -   Standardvärdet är 18 (timmar).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Det här värdet anger starttiden. Det finns högst 12 timmar från sluttiden.
    -   Värden som stöds är 0–23, där 0 är 12:00, 1 är 01:00 osv.
    -   Standardvärdet är 8 (08:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Endast för enheter Windows 10 kör version 1607

Du kan använda följande uppdateringsprinciper för att konfigurera enheter för att hämta uppdateringar från Windows Server Update Service (WSUS), i stället för från Windows Update:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Uppdatera/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planera och konfigurera uppdateringsutrullningar för HoloLens 2

HoloLens 2 stöder fler funktioner för uppdateringsautomatisering än vad HoloLens (första gen) har. Detta gäller särskilt om du använder Microsoft Intune för att hantera Windows För företag-principer. De här funktionerna gör det enklare för dig att planera och implementera uppdateringsutrullningar i organisationen.

#### <a name="plan-the-update-strategy"></a>Planera uppdateringsstrategin

Windows Uppdateringar för företag stöder upp skjuta upp principer. När Microsoft släpper en uppdatering kan du använda en upp skjuta upp princip för att definiera hur lång tid som ska vänta innan uppdateringen installeras på enheter. Genom att associera delmängder av dina enheter (även kallade uppdateringsringar) med olika uppsänkningsprinciper kan du samordna en strategi för uppdateringsutrullning för din organisation.

Tänk dig till exempel en organisation som har 1 000 enheter och som måste uppdatera enheterna i fem vågor. Organisationen kan skapa fem uppdateringsringar, som du ser i följande tabell.

|Group |Antal enheter |Upp skjuta upp (dagar) |
| ---| :---: | :---: |
|Grp 1 (IT-personal) |5 |0 |
|Grp 2 (tidiga anammare) |50 |60 |
|Grp 3 (huvud 1) |250 |120 |
|Grp 4 (huvud 2) |300 |150 |
|Grp 5 (huvud 3) |395 |180 |

Så här går processen över tid till hela organisationen.

![Tidslinje för distribution av uppdateringar.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurera en princip för uppsenning av uppdateringar

En uppseningsprincip anger antalet dagar mellan det datum då en uppdatering blir tillgänglig och det datum då uppdateringen erbjuds till en enhet.

Du kan konfigurera olika upp senareläggningar för funktionsuppdateringar och kvalitetsuppdateringar. I följande tabell visas de specifika principer som ska användas för varje typ och den maximala upp skjuta upp för varje typ.

|Kategori |Policy |Maximal upp skjuta upp |
| --- | --- | --- |
|Funktionsuppdateringar |DeferFeatureUpdatesPeriodInDays |365 dagar |
|Kvalitetsuppdateringar |DeferQualityUpdatesPeriodInDays |30 dagar |

#### <a name="pause-updates-via-device"></a>Pausa uppdateringar via enhet

Om en användare inte har åtkomst till MDM kan de individuellt pausa uppdateringar i upp till 35 dagar manuellt på en HoloLens 2-enhet på [version Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) eller senare. Användare kan komma åt den här inställningen genom att gå till Inställningar > Update &  Security > Advanced options (Avancerade alternativ för Uppdatering **& Security >)** rulla ned till Pausa uppdateringar och välja det datum tills de pausar uppdateringar. När en användare har nått pausgränsen måste enheten få nya uppdateringar innan de kan pausa igen. 

Från och [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2)kan den här funktionen för pausuppdateringar hanteras för HoloLens 2 enheter. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (standard) – Aktiverad
    - 1 – Inaktiverad

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Intune-uppdateringshanteringsfunktioner som HoloLens stöder

Du kan använda följande intune-uppdateringshanteringsfunktioner för att hantera uppdateringar för HoloLens.

- **Skapa** och **tilldela:** Dessa funktioner lägger till Windows 10 en uppdateringsring i listan över uppdateringsringar. Mer information finns i Skapa [och tilldela uppdateringsringar.](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Pausa:** Om det uppstår ett problem när du distribuerar en funktion eller kvalitetsuppdatering kan du pausa uppdateringen i 35 dagar (med början från ett angivet datum). Den här pausen förhindrar att andra enheter installerar uppdateringen förrän du har löst eller åtgärdat problemet. Om du pausar en funktionsuppdatering erbjuds kvalitetsuppdateringar fortfarande till enheter för att säkerställa att de förblir säkra. När en uppdateringstyp har pausats visar översiktsfönstret för den ringen hur många dagar som återstår innan uppdateringstypen återupptas. När den angivna tiden har passerat upphör pausen automatiskt att gälla och uppdateringsprocessen återupptas.

  När uppdateringsringen har pausats kan du välja något av följande alternativ:

  - **Utöka**: Utöka pausperioden för en uppdateringstyp med 35 dagar.
  - **Återuppta:** Återställ uppdateringar för den ringen till aktiv åtgärd. Du kan pausa uppdateringsringen igen om det behövs.

  > [!NOTE]  
  > Avinstallationsåtgärden för uppdateringsringar stöds inte för HoloLens 2 enheter. 

### <a name="delivery-optimization-preview"></a>Leveransoptimering förhandsversion

[Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) har aktiverat en tidig förhandsversion för leveransoptimeringsinställningar för att minska bandbreddsförbrukningen för nedladdningar från flera HoloLens enheter. En fullständig beskrivning av den här funktionen tillsammans med den rekommenderade nätverkskonfigurationen finns här: Leveransoptimering [för Windows 10 uppdateringar](/windows/deployment/update/waas-delivery-optimization).

Följande inställningar är aktiverade som en del av hanteringsytan [och kan konfigureras från Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Några varningar om det här förhandsversionserbjudandet:

- HoloLens stödet är begränsat i den här förhandsversionen till enbart OS-uppdateringar.
- Windows Holographic for Business stöder endast HTTP-nedladdningslägen och nedladdningar från en [Microsoft Ansluten cache slutpunkt](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); peer-to-peer-nedladdningslägen och grupptilldelningar stöds inte för HoloLens enheter för närvarande.
- HoloLens stöder inte distribution eller leveransoptimering för Windows Server Update Services slutpunkter.
- Felsökning kräver antingen diagnostik på Ansluten cache-servern eller insamling av en spårning på HoloLens på HoloLens via **Inställningar**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

## <a name="manually-check-for-updates"></a>Söka efter uppdateringar manuellt

Även HoloLens regelbundet söker efter systemuppdateringar, kan det finnas omständigheter då du vill kontrollera manuellt.

Om du vill söka efter uppdateringar manuellt **går du till Inställningar** Update & Security Check for updates  >  **(Säkerhetskontroll** för  >  **uppdatering).** Om Inställningar visar att enheten är uppdaterad har du alla uppdateringar som är tillgängliga för tillfället.

## <a name="manually-roll-back-an-update"></a>Återställa en uppdatering manuellt

I vissa fall kanske du vill återgå till en tidigare version av HoloLens programvara. Processen för att göra detta beror på om du använder HoloLens 2 eller HoloLens (första generationen).

### <a name="revert-to-a-previous-version-hololens-2"></a>Återgå till en tidigare version (HoloLens 2)

Du kan återställa uppdateringar och återgå till en tidigare version av HoloLens 2 med hjälp av [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) för att återställa HoloLens till den tidigare versionen.

> [!NOTE]
> Om du återgår till en tidigare version tas dina personliga filer och inställningar bort.

Om du vill återgå till en tidigare version HoloLens 2 följer du dessa steg:

1. Kontrollera att du inte har några telefoner eller Windows enheter som är anslutna till datorn.
1. På datorn laddar du ned [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) från Microsoft Store.
1. Ladda ned [den senaste versionen HoloLens 2.](https://aka.ms/hololens2download)
1. När dessa hämtningar är klara öppnar du Filutforskaren Nedladdningar, högerklickar på den komprimerade  >  mappen (.zip) som du precis har laddat ned och väljer sedan **Extrahera alla** Extrahera för att expandera  >   filen.
1. Använd en USB-A till USB-C-kabel för att HoloLens till datorn. Även om du har använt andra kablar för att ansluta HoloLens fungerar den här typen av kabel bäst.
1. Advanced Recovery Companion identifierar automatiskt HoloLens enhet. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuellt paketval** och öppnar sedan den mapp som du tidigare expanderade.
1. Välj installationsfilen (.ffu).
1. Välj **Installera programvara** och följ sedan instruktionerna.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Återgå till en tidigare version (HoloLens (första generationen))

Du kan återställa uppdateringar och återgå till en tidigare version av HoloLens (första generationen) med hjälp av [Windows Device Recovery Tool (WDRT) för](https://support.microsoft.com/help/12379) att återställa HoloLens till den tidigare versionen.

> [!NOTE]
> Om du återgår till en HoloLens version tas dina personliga filer och inställningar bort.

Om du vill återgå till en tidigare version HoloLens (första generationen) följer du dessa steg:

1. Se till att du inte har några telefoner eller Windows enheter som är anslutna till datorn.
1. Ladda ned verktyget Windows [(WDRT) på datorn.](https://support.microsoft.com/help/12379)
1. Ladda ned [återställningspaketet HoloLens Anniversary Update](https://aka.ms/hololensrecovery).
1. När hämtningarna är klara öppnar du Filutforskaren Nedladdningar, högerklickar på den komprimerade  >  mappen (.zip) som du precis har laddat ned och väljer sedan **Extrahera alla** Extrahera för att expandera  >   filen.
1. Använd mikro-USB-kabeln som tillhandahölls tillsammans med din HoloLens för att ansluta HoloLens till datorn. Även om du har använt andra kablar för att ansluta HoloLens enhet fungerar den här bäst.
1. WDRT identifierar automatiskt HoloLens enhet. Välj **Microsoft HoloLens** panelen.
1. På nästa skärm väljer du **Manuellt paketval** och öppnar sedan den mapp som du tidigare expanderade.
1. Välj installationsfilen (.ffu).
1. Välj **Installera programvara** och följ sedan instruktionerna.

**Om WDRT inte identifierar din enhet**

Om WDRT inte identifierar enheten HoloLens provar du att starta om datorn. Om det inte fungerar väljer du **Min enhet identifierades** inte, Microsoft HoloLens **och** följer sedan anvisningarna.

## <a name="related-articles"></a>Relaterade artiklar

- [HoloLens 2 – information](hololens-release-notes.md)
- [Vad är Windows Update för företag?](/windows/deployment/update/waas-manage-updates-wufb)
- [Tilldela enheter till underhållskanaler för Windows 10 uppdateringar](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Hantera Windows 10-programuppdateringar i Intune](/mem/intune/protect/windows-update-for-business-configure)
