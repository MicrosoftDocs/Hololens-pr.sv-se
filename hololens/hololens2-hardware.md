---
title: HoloLens 2-maskinvara
description: Lär dig mer om de komponenter som utgör Microsoft HoloLens 2, den senaste utvecklingen av en ouppspelad holografisk Microsoft-dator som kör Windows 10.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 4c476a2adc8f03c37e17e6324960318b4806534e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639751"
---
# <a name="about-hololens-2"></a>Om HoloLens 2

![HoloLens 2-sidvy](images/hololens2-breakdown.png)

Microsoft HoloLens 2 är en untethered holographic-dator.  Den förfinar den holografiska databehandlingsresa som påbörjades av HoloLens (första generationen) för att ge en mer bekväm och integrerande upplevelse tillsammans med fler alternativ för samarbete i mixad verklighet. HoloLens 2 körs på [Windows Holographic OS](hololens-release-notes.md), som baseras på en "variant" av Windows 10 som ger användare, administratörer och utvecklare en robust, bra och säker plattform. 

> [!NOTE]
> Det senaste Windows 11-meddelandet fokuserade på PC-versionen av Windows. Vi lanserade nyligen en större [OS-uppdatering](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) till HoloLens 2 i maj 2021 och vi arbetar med en kommande version baserad på kundfeedback för den här tiden.

Ett användarkonto krävs för att använda HoloLens 2.

## <a name="hololens-components"></a>HoloLens komponenter

- **Visor - (Visor).** Innehåller de HoloLens sensorerna och visas. Du kan rotera upp visiret medan du använder HoloLens.
- **Headband**. Använd justeringshjulet för HoloLens för att expandera huvudbandet. Med HoloLens på plats, förstyv justeringshjulet genom att dra åt höger tills huvudbandet är bekväma.
- **Ljusstyrka-knappar**. När du använder HoloLens är ljusstyrkan på vänster sida av visor-programmet nära ditttempel.
- **Volymknappar**. När du använder HoloLens är volymknapparna på höger sida av visor-programmet nära ditttempel.
- **Strömknapp**. När du använder HoloLens finns strömknappen på höger sida av det bakre yttre höljet.
- **USB-C-port**. När du använder HoloLens finns USB-C-porten på höger sida av det bakre yttre höljet under strömknappen.

## <a name="in-the-box"></a>I rutan

- **[Brow pad](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**. Du kan ta bort och ersätta brow pad efter behov.
- **[Overhead overhead overhead](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)**. När du bär på HoloLens när du flyttar kan du använda overheadenheten för att hålla enheten på plats. När du använder HoloLens under längre perioder kan omkostnaderna göra enheten mer bekväm att ha på sig.
- **[USB-C-kabel och kabel](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**. Strömförsörjningen ansluts till elnätet. Använd USB-C-kabeln för att HoloLens till strömförsörjningen för laddning eller för att ansluta HoloLens till datorn.
- **Microfiber-mikrofiber** från . Använd för att rensa HoloLens visor-programmet.

### <a name="power-supply-details"></a>Information om strömförsörjning

Strömkabeln och USB-kabeln som levereras med enheten är den bästa mekanismen som stöds för laddning. Strömförsörjningen är en 18 W-strömförsörjning.  Den tillhandahåller 9V vid 2A.

Debiteringshastigheten och hastigheten kan variera beroende på i vilken miljö enheten körs.

För att kunna underhålla/avancera intern batteriladdningsprocent när enheten är på måste den vara ansluten minst till en 15 W-dator.

## <a name="device-specifications"></a>Enhetsspecifikationer

### <a name="display"></a>Skärm

|   | &nbsp; |
|---|---|
| **Optik** | See-through holographic lenses (waveguides) |
| **Holographic-upplösning** | 2k 3:2 lätt motorer |
| **Holografisk densitet** | >2,5 000 (ljuspunkter per radian) |
| **Ögonbaserad rendering** | Visa optimering för 3D-ögonposition |

### <a name="sensors"></a>Sensorer

|   | &nbsp; |
|---|---|
| **Huvudspårning** | 4 synliga ljuskameror |
| **Ögonspårning** | 2 IR-kameror (IR) |
| **Djup** | Djupsensor för flygtid på 1 MP |
| **Inertial Measurement Unit (IMU)** | Accelerometer,roscope, magnetometer |
| **Kamera** | 8 MP-fortfarande, 1080p30-video |

![HoloLens 2 sensorer](images/hololens2-front-view.png)

> [!NOTE]
> Ta inte upp några sensorer som visas i bilden. Huvudspårningskamerorna har en mycket bred FOV, inget bör finnas runt dem förutom att de inte täcker dem.

### <a name="audio-and-speech"></a>Ljud och tal

|   | &nbsp; |
|---|---|
| **Mikrofonmatris** | 5 kanaler |
| **Högtalare** | Inbyggt rumsligt ljud |

### <a name="compute-and-connectivity"></a>Beräkning och anslutning

|   | &nbsp; |
|---|---|
| **System på chip** | Information om Qualcomm Snapdragon 850 Compute [Platform](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| **Holografisk bearbetningsenhet** | Andra generationens anpassade holografiska bearbetningsenhet |
| **Minne** | 4 GB LPDDR4x system-DRAM |
| **Storage** | 64 GB UFS 2.1 |
| **Wi-Fi** | 802.11ac 2x2 |
| **Bluetooth** | 5.0 |
| **USB** | USB Type-C DRP |

### <a name="power"></a>Ström

|   | &nbsp; |
|---|---|
| **Batteritid** | 2–3 timmars aktiv användning. Upp till två veckors vänteläge. |
| **Batteriteknik** | [Lithium-batterier](https://www.microsoft.com/download/details.aspx?id=43388) |
| **Debiteringsbeteende** | Fullt funktionell vid debitering |
| **Typ av kylning** | Passivt kylt (inga fläktar) |
| **Power draw (Power draw)** | För att kunna underhålla/avancera intern batteriladdningsprocent när enheten är på måste den vara ansluten minst till en 15 W-dator. |

### <a name="fit"></a>Anpassning

|   | &nbsp; |
|---|---|
| **Storlekar** | Enkel storlek med justerbart band.  Passar över glasögon |
| **Vikt** | 566 gram |

## <a name="device-capabilities"></a>Enhetsfunktioner

### <a name="human-understanding"></a>Förstå andra

|   | &nbsp; |
|---|---|
| **Handspårning** | Fullständigt formulerad modell med två hand, direkt manipulering |
| **Ögonspårning** | Realtidsspårning |
| **Röst** | Kommando och kontroll på enheten; Cortana naturligt språk med Internetanslutning |

### <a name="environment-understanding"></a>Miljöförståelse

|   | &nbsp; |
|---|---|
| **Spårning med Sex frihetsgrader (6DoF)** | Positionsspårning i världsskala |
| **Rumslig mappning** | Realtidsmiljönät |
| **Capture med mixad verklighet** | Foton och videor med blandat hologram och fysisk miljö |

## <a name="pre-installed-software"></a>Förinstallerad programvara

| &nbsp; | &nbsp; |
|---|---|
| **Windows Holographic Operating System** | Med [Windows Holographic OS](hololens-release-notes.md)kan Windows 10 användare använda några av sina appar och spel i en miljö med mixad verklighet via HoloLens 2.
| **3D-visningsprogram** | [3D-visningsprogram](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) kan du enkelt visa 3D-modeller och animeringar i realtid.|
| **Cortana** | [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab)hjälper din personliga produktivitetsassistent dig att hålla reda på det som är viktigt och spara tid på att hitta det du behöver.  |
| **Dynamics 365-guider** |  [Dynamics 365-guider hjälper](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) anställda att lära sig nya färdigheter snabbare HoloLens enheter. |
| **Fjärrhjälp för Dynamics 365** | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) gör det möjligt för tekniker att samarbeta och lösa problem med fjärranslutna medarbetare med hjälp av Microsoft Teams eller Dynamics 365 Remote Assist.  |
| **Feedbackhubben** | [Feedbackhubben](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) kan du ge feedback om Windows och appar genom att dela med dig av dina förslag eller problem.  |
| **Utforskaren** | Utforskaren ett grafiskt användargränssnitt för åtkomst till filsystemen. |
| **E-post och kalender** | Med [apparna E-post](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) och Kalender kan du hålla dig uppdaterad om din e-post, hantera ditt schema och hålla kontakten med dina kontakter. |
| **Microsoft Edge** | Microsoft Edge ger dig prestanda i världsklass med mer sekretess, mer produktivitet och mer värde när du bläddrar. |
| **Microsoft Store** | Den [Microsoft Store](https://www.microsoft.com) är din go-to-källa för appar och spel som fungerar med HoloLens.|
| **Filmer & TV** | [Filmer & TV](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) ger dig den senaste underhållningen i en enkel, snabb och elegant app. |
| **OneDrive** | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) kan du komma åt och redigera filer från alla dina enheter var som helst.  |
| **Foton** | [Photos](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) kan du visa och redigera dina foton och videor, skapa filmer och skapa filmer.  |
| **Inställningar** | Appen Inställningar är den plats där du anpassar hur Windows Holographic fungerar i detalj.  |
| **Tips** | [Tips](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) kan du bemästra överraskande och mindre kända saker som du kan göra i Windows Holographic. |

## <a name="device-certifications"></a>Enhetscertifieringar

### <a name="safety"></a>Säkerhet

* [Produktsäkerhet](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Varningar och instruktioner för produktsäkerhet](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Ögonsäkerhet: HoloLens 2 har testats och uppfyller de grundläggande effektskyddskraven för ANSI Z87.1, CSA Z94.3 och EN 166.
* [SAR-information](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Regelinformation
[HoloLens: Innehåller](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)information om temperatur, försäljning, radio- och TV-interferens med mera.

## <a name="warranty-information"></a>Garantiinformation

Microsoft HoloLens 2 levereras med en begränsad [standardgaranti.](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) 


Köp omfattas av [Microsoft Store användningsvillkor och försäljning](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1). All försäljning är slutgiltig. Inga återbetalningar.

Genom att HoloLens 2 godkänner du [licensavtalet för programvara.](https://www.microsoft.com/Useterms/)

Inte avsett för barn som är yngre än 13 år.

## <a name="package-dimensions"></a>Paketdimensioner

|      Mått               |      Mått för enheter     |      Enheter     |
|--------------------------------|-----------------------|-------------------------|
|     Enhetslängd                |     378,97 mm          |     14,920 tum       |
|     Enhetsbredd                 |     247,90 mm          |     9,760 tum        |
|     Enhetsdjup                 |     163,07 mm          |     6,420 tum        |
|     Enhetsvikt                |     2,878 kg           |     6,344 lbs           |
|     Beter sig som en transportörslängd    |     446,00 mm          |     17,559 tum       |
|     Bredd på belastare     |     257,99 mm          |     10,157 tum       |
|     Beter sig på djupet     |     172,01 mm          |     6,772 tum        |
|     Belastarvikt    |     3,284 kg           |     7,240 lbs           |

> [!NOTE]
> - Enhet: Den svarta rutan i detaljhandelsstil HoloLens 2 säljs i.
> - Uppsett frakt: Den skyddande leveranspaketeringen runt enheten.

## <a name="finding-the-serial-number"></a>Hitta serienumret

Serienumret för HoloLens 2 enheter skrivs ut under visor-programmet.

1. Lyft upp visorn för enheten.
1. Titta nära brow pad.
1. Du hittar serienumret som finns nära dörren.

   <img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

Serienumret kan också hittas via en ansluten dator:

1. Anslut enheten
1. Gå till **den här datorn** i Utforskaren
1. Högerklicka och välj **Egenskaper för** HoloLens enhet
1. Då visas enhetens serienummer, som du ser i skärmbilden nedan.

   <br/><img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Nästa steg

> [!div class="nextstepaction"]
> [Jämför HoloLens 2 utgåvor](hololens2-options.md)

> [!div class="nextstepaction"]
> [Konfigurera och starta din HoloLens 2](hololens2-setup.md)
