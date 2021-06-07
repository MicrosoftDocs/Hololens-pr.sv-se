---
title: Information om HoloLens 1:a (gen)
description: Läs mer om uppdateringar i varje ny HoloLens-version.
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
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "111378708"
---
# <a name="hololens-1st-gen-release-notes"></a>Information om HoloLens 1:a (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1:a gen) Long Term Servicing
HoloLens (1:a gen) har gått in i tillståndet Long Term Servicing (LTS). Framtida uppdateringar fokuserar på problem- och säkerhetskorrigeringar, samtidigt som funktionsparitet upprätthålls med Windows 10 Holographic version 1809 för HoloLens (första generationen).

För utvecklare innebär det att HoloLens-appar (första generationen) inte stöder OpenXR-API:et.  Dessa headset stöds fortfarande i Unity 2019 LTS med WinRT API-backend för hela livscykeln för Unity 2019 LTS till mitten av 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, version 1809

> **Gäller för:** HoloLens (1:a gen)

| Funktion | Information |
|---|---|
| **Snabbåtgärder-menyn** | När du använder en app öppnar Bloom-gesten nu en snabbåtgärder-meny för att ge dig snabb åtkomst till vanliga systemfunktioner utan att behöva lämna appen. <br> Information [om snabbåtgärder-menyn i helskärmsläge](hololens-kiosk.md) finns i Konfigurera HoloLens i helskärmsläge.<br><br> |
| **Stoppa videoinspelning från menyn Starta eller snabbåtgärder** | Om du startar videoinspelningen Start-menyn eller snabbåtgärder-menyn kan du stoppa inspelningen från samma plats. (Glöm inte att du alltid kan göra detta med röstkommandon också.) |
| **Projicera till en Miracast-aktiverad enhet** | Projicera ditt HoloLens-innehåll till en Surface-enhet i närheten eller TV/Monitor om du använder Microsoft Display-adapter.  På **Start** väljer du **Anslut** och sedan den enhet som du vill projicera till. **Obs!** Du kan distribuera HoloLens för att använda Miracast-projektion utan att aktivera utvecklarläge. |
| **Nya meddelanden** | Visa och svara på popup-meddelanden på HoloLens, precis som du gör på en dator. Blicka på att svara på eller avvisa dem (eller om du har en integrerande upplevelse kan du använda bloom-gesten). |
| **HoloLens-överlägg**<br>(filväljare, tangentbord, dialogrutor osv.) | Nu visas överlägg som tangentbord, dialogrutor, filväljare osv. när du använder integrerande appar. |
| **Överläggsgränssnitt för visuell feedback för volymändring** | När du använder knapparna för volym upp/ned på HoloLens visas en visuell visning av volymnivån. |
| **Nytt användargränssnitt för enhetsstart** | En inläsningsindikator lades till under startprocessen för att ge visuell feedback om att systemet läses in. Starta om enheten för att se den nya inläsningsindikatorn – det är mellan meddelandet "Hello" och Windows-startlogotypen. |
| **Delning i närheten** | Tillägg av windows delning i närheten, så att du kan dela en avbildning med en Windows-enhet i närheten. När du spelar in ett foto eller en video på HoloLens (eller använder delningsknappen från en app, till exempel Microsoft Edge), väljer du en Windows-enhet i närheten att dela med. |
| **Dela från Microsoft Edge** | Dela-knappen är nu tillgänglig Microsoft Edge windows på HoloLens. I Microsoft Edge väljer du **Dela**. Använd HoloLens-delningsväljaren för att dela webbinnehåll. |

#### <a name="for-international-customers"></a>För internationella kunder

| Funktion | Information |
| --- | --- |
| Lokaliserade kinesiska och japanska byggen | Använd HoloLens med lokaliserat användargränssnitt för förenklad kinesiska eller japanska, inklusive lokaliserat Pinyin-tangentbord, diktering och röstkommandon.<br>[Lär dig hur du installerar de kinesiska och japanska versionerna av HoloLens.](hololens1-install-localized.md) |
| Talsyntes (TTS) | Talsyntesfunktionen stöder nu kinesiska, japanska och engelska. |

#### <a name="for-administrators"></a>För administratörer

| Funktion |  Information  |
|---|----|
| [Aktivera etablering efter installationen](hololens-provisioning.md) | Du kan nu använda ett runtime-etableringspaket när som helst med hjälp av **Inställningar.** |
| Tilldelad åtkomst med Azure AD-grupper | Nu kan du använda Azure AD-grupper för konfiguration av Windows-tilldelad åtkomst för att konfigurera helskärmskonfiguration för en eller flera appar. |
| Växla pin-kod för inloggningsprofil från inloggningsskärmen | PIN-inloggning är nu tillgängligt för **annan användare.** |
| Logga in med webbaserade Provider för autentiseringsuppgifter med lösenord | Nu kan du välja alternativet Globe-inloggning för att starta webb inloggningen med ditt lösenord. Välj Inloggningsalternativ på **inloggningsskärmen och välj alternativet** Jordglob för att starta webb inloggningen. Ange ditt användarnamn om det behövs och sedan ditt lösenord. <br>**Obs!** Du kan välja att kringgå alla alternativ för PIN-kod/smartkort när du uppmanas att logga in på webben. |
| Läs information om enhetens maskinvara via MDM så att enheter kan spåras med serienummer | IT-administratörer kan se och spåra HoloLens efter enhetsserienummer i MDM-konsolen. Se MDM-dokumentationen för funktionstillgänglighet och instruktioner. |
| Ange HoloLens-enhetsnamn via MDM (byt namn) | IT-administratörer kan se och byta namn på HoloLens-enheter i MDM-konsolen. Se MDM-dokumentationen för funktionstillgänglighet och instruktioner. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 version 1803 för Microsoft HoloLens

> **Gäller för:** HoloLens (1:a gen)

Windows 10 version 1803 är den första funktionsuppdateringen som Windows Holographic for Business sedan version 1607 Windows 10 version 1607. Den här uppdateringen introducerar följande ändringar:

- Tidigare kunde du bara kontrollera att uppgraderingslicensen för Commercial Suite hade tillämpats på din HoloLens-enhet genom att kontrollera om VPN var ett tillgängligt alternativ på enheten. Nu **visar**  >  **Inställningssystem** Windows Holographic for Business när uppgraderingslicensen har tillämpats.  [Lär dig hur du låser Windows Holographic for Business funktioner](hololens1-upgrade-enterprise.md).

- Du kan visa operativsystemets build-nummer i enhetsegenskaperna i Utforskaren appen och i [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Nu är det enklare att etablera en HoloLens-enhet med den nya guiden Etablera **HoloLens-enheter** i verktyget Windows Configuration Designer. I guiden kan du konfigurera konfigurationsupplevelsen och nätverksanslutningar, ange utvecklarläge och hämta Azure AD-masstoken. [Lär dig hur du använder den enkla etableringsguiden för HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- När du skapar ett lokalt konto i ett etableringspaket upphör lösenordet inte längre att gälla var 42:e dag.

- Du kan [konfigurera HoloLens som en helskärmsläge för en app eller flera appar.](hololens-kiosk.md) Med helskärmsläge för flera appar kan du konfigurera en HoloLens för att endast köra de appar som du anger och förhindra användare från att göra ändringar.

- Media Transfer Protocol (MTP) är aktiverat så att du kan ansluta HoloLens-enheten till en dator via USB och överföra filer mellan HoloLens och datorn. Du kan också använda Utforskaren för att flytta och ta bort filer från HoloLens.

- När du tidigare loggade in på enheten med ett Azure Active Directory-konto (Azure  AD) var du tvungen att lägga till arbetsåtkomst i **Inställningar** för att få åtkomst till företagets resurser. Nu loggar du in med ett Azure AD-konto och registreringen sker automatiskt.

- Innan du loggar in kan du välja nätverksikonen under lösenordsfältet för att välja ett annat Wi-Fi nätverk att ansluta till. Du kan också ansluta till ett gästnätverk, till exempel på ett hotell, ett konferenscenter eller ett företag.

- Nu kan du enkelt [dela HoloLens med flera personer med hjälp](hololens-multiple-users.md) av Azure AD-konton.

- Om installationen eller inloggningen misslyckas väljer du det nya alternativet **Samla in information** för att hämta diagnostikloggar för felsökning.

- Enskilda användare kan synkronisera sin företags-e-post utan att registrera sin enhet i hantering av mobila enheter (MDM). Du kan använda enheten med ett Microsoft-konto, ladda ned och installera e-postappen och lägga till ett e-postkonto direkt.

- Du kan kontrollera MDM-synkroniseringsstatusen för en enhet i **Inställningar**  >  **Konton Åtkomst** till  >  **arbets- eller**  >  **skolinformation.** I avsnittet **Status för enhetssynkronisering** kan du starta en synkronisering, se områden som hanteras av MDM och skapa och exportera en avancerad diagnostikrapport.
