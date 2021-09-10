---
title: HoloLens 1:a (gen)-versionen
description: Lär dig mer om uppdateringar i varje HoloLens version.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428346"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1:a (gen)-versionen

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1:a generationen) Long Term Servicing
HoloLens (1:a gen) har gått in i tillståndet Long Term Servicing (LTS). Framtida uppdateringar fokuserar på problem- och säkerhetskorrigeringar, samtidigt som funktionsparitet upprätthålls med Windows 10 Holographic version 1809 för HoloLens (första gen).

För utvecklare innebär det att HoloLens (första generationens) appar inte stöder OpenXR-API:et.  Dessa headset stöds fortfarande i Unity 2019 LTS med WinRT API-backend för hela livscykeln för Unity 2019 LTS till mitten av 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic version 1809

> **Gäller för:** HoloLens (första gen)

| Funktion | Information |
|---|---|
| **Snabbåtgärder-menyn** | När du använder en app öppnar Bloom-gesten nu en snabbåtgärder-meny för att ge dig snabb åtkomst till vanliga systemfunktioner utan att behöva lämna appen. <br> Se [Konfigurera HoloLens helskärmsläge för](hololens-kiosk.md) information om snabbåtgärder-menyn i helskärmsläge.<br><br> |
| **Stoppa videoinspelning från menyn Starta eller snabbåtgärder** | Om du startar videoinspelningen Start-menyn eller snabbåtgärder-menyn kan du stoppa inspelningen från samma plats. (Glöm inte att du alltid kan göra detta med röstkommandon också.) |
| **Project till en Miracast-aktiverad enhet** | Project ditt HoloLens till en Surface-enhet i närheten eller TV/Monitor om du använder Microsoft Display-adaptern.  På **Start** väljer **du Anslut** och väljer sedan den enhet som du vill projicera till. **Obs!** Du kan distribuera HoloLens att använda Miracast projektion utan att aktivera utvecklarläge. |
| **Nya meddelanden** | Visa och svara på popup-meddelanden på HoloLens, precis som du gör på en dator. Blicka på att svara på eller avvisa dem (eller om du har en integrerande upplevelse kan du använda bloom-gesten). |
| **HoloLens överlägg**<br>(filväljare, tangentbord, dialogrutor osv.) | Nu visas överlägg som tangentbord, dialogrutor, filväljare osv. när du använder integrerande appar. |
| **Överläggsgränssnitt för visuell feedback för volymändring** | När du använder knapparna för volym upp/ned på HoloLens visas en visuell visning av volymnivån. |
| **Nytt användargränssnitt för enhetsstart** | En inläsningsindikator lades till under startprocessen för att ge visuell feedback om att systemet läses in. Starta om enheten för att se den nya inläsningsindikatorn – det är mellan meddelandet "Hello" och Windows startlogotypen. |
| **Delning i närheten** | Tillägget av Windows delning i närheten, så att du kan dela en avfångst med en Windows enhet. När du spelar in ett foto eller en video på HoloLens (eller använder delningsknappen från en app, till exempel Microsoft Edge), väljer du en enhet Windows i närheten som du vill dela med. |
| **Dela från Microsoft Edge** | Dela-knappen är nu tillgänglig Microsoft Edge windows på HoloLens. I Microsoft Edge väljer du **Dela**. Använd väljaren HoloLens dela webbinnehåll. |

#### <a name="for-international-customers"></a>För internationella kunder

| Funktion | Information |
| --- | --- |
| Lokaliserade kinesiska och japanska byggen | Använd HoloLens med lokaliserat användargränssnitt för förenklad kinesiska eller japanska, inklusive lokaliserat Pinyin-tangentbord, diktering och röstkommandon.<br>[Lär dig hur du installerar kinesiska och japanska versioner av HoloLens.](hololens1-install-localized.md) |
| Talsyntes (TTS) | Talsyntesfunktionen stöder nu kinesiska, japanska och engelska. |

#### <a name="for-administrators"></a>För administratörer

| Funktion |  Information  |
|---|----|
| [Aktivera etablering efter installationen](hololens-provisioning.md) | Nu kan du när som helst använda ett runtime-etableringspaket med **hjälp av Inställningar**. |
| Tilldelad åtkomst med Azure AD-grupper | Nu kan du använda Azure AD-grupper för konfiguration Windows tilldelad åtkomst för att konfigurera en helskärmskonfiguration för en eller flera appar. |
| Växla pin-kod för inloggningsprofil från inloggningsskärmen | PIN-inloggning är nu tillgängligt för **annan användare.** |
| Logga in med webbaserade Provider för autentiseringsuppgifter med lösenord | Nu kan du välja alternativet Globe-inloggning för att starta webb inloggningen med ditt lösenord. På inloggningsskärmen väljer du **Inloggningsalternativ och väljer** alternativet Jordglob för att starta webb inloggningen. Ange ditt användarnamn om det behövs och sedan ditt lösenord. <br>**Obs!** Du kan välja att kringgå alla alternativ för PIN-kod/smartkort när du uppmanas att logga in på webben. |
| Läs information om enhetens maskinvara via MDM så att enheter kan spåras med serienummer | IT-administratörer kan se och HoloLens efter enhetsserienummer i MDM-konsolen. Se MDM-dokumentationen för funktionstillgänglighet och instruktioner. |
| Ange HoloLens enhetsnamn via MDM (byt namn) | IT-administratörer kan se och byta namn HoloLens enheter i MDM-konsolen. Se MDM-dokumentationen för funktionstillgänglighet och instruktioner. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 version 1803 för Microsoft HoloLens

> **Gäller för:** HoloLens (första gen)

Windows 10 version 1803 är den första funktionsuppdateringen som har Windows Holographic for Business sedan versionen i Windows 10, version 1607. Den här uppdateringen introducerar följande ändringar:

- Tidigare kunde du bara kontrollera att uppgraderingslicensen för Commercial Suite hade tillämpats på din HoloLens-enhet genom att kontrollera om VPN var ett tillgängligt alternativ på enheten. Nu **Inställningar**  >  **System** Windows Holographic for Business  när uppgraderingslicensen har tillämpats. [Lär dig hur du låser Windows Holographic for Business funktioner](hololens1-upgrade-enterprise.md).

- Du kan visa operativsystemets build-nummer i enhetsegenskaperna i Utforskaren appen och [i Windows(WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Nu är det enklare att HoloLens en enhet med den nya **guiden Etablera HoloLens enheter** i Windows Configuration Designer-verktyget. I guiden kan du konfigurera konfigurationsupplevelsen och nätverksanslutningar, ange utvecklarläge och hämta Azure AD-masstoken. [Lär dig hur du använder den enkla etableringsguiden för att HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- När du skapar ett lokalt konto i ett etableringspaket upphör lösenordet inte längre att gälla var 42:e dag.

- Du kan [konfigurera HoloLens som en helskärmsläge för en app eller flera appar.](hololens-kiosk.md) Med helskärmsläge för flera appar kan du konfigurera en HoloLens att endast köra de appar som du anger och hindrar användarna från att göra ändringar.

- Media Transfer Protocol (MTP) är aktiverat så att du kan ansluta HoloLens till en dator via USB och överföra filer mellan HoloLens och datorn. Du kan också använda Utforskaren för att flytta och ta bort filer från HoloLens.

- När du tidigare loggade in på enheten med ett Azure Active Directory-konto (Azure  AD) var du sedan tvungen att lägga till arbetsåtkomst i **Inställningar för** att få åtkomst till företagets resurser. Nu loggar du in med ett Azure AD-konto och registreringen sker automatiskt.

- Innan du loggar in kan du välja nätverksikonen under lösenordsfältet för att välja ett annat Wi-Fi nätverk att ansluta till. Du kan också ansluta till ett gästnätverk, till exempel på ett hotell, ett konferenscenter eller ett företag.

- Nu kan du enkelt dela [HoloLens flera personer med hjälp av](hololens-multiple-users.md) Azure AD-konton.

- Om installationen eller inloggningen misslyckas väljer du det nya alternativet **Samla in information** för att hämta diagnostikloggar för felsökning.

- Enskilda användare kan synkronisera sin företags-e-post utan att registrera sin enhet i hantering av mobila enheter (MDM). Du kan använda enheten med ett Microsoft-konto, ladda ned och installera e-postappen och lägga till ett e-postkonto direkt.

- Du kan kontrollera MDM-synkroniseringsstatusen för en enhet **i Inställningar**  >  **åtkomst till**  >  **arbets- eller**  >  **skolinformation.** I avsnittet **Status för enhetssynkronisering** kan du starta en synkronisering, se områden som hanteras av MDM och skapa och exportera en avancerad diagnostikrapport.
