---
title: Konfigurera HoloLens helskärmsläge
description: Lär dig att konfigurera och använda en kioskkonfiguration för att låsa apparna på HoloLens enheter.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033197"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Konfigurera HoloLens helskärmsläge

## <a name="what-is-kiosk-mode"></a>Vad är helskärmsläge?

Helskärmsläge är en funktion där du kan styra vilka program som visas på Start-menyn när en användare loggar in på HoloLens. Det finns två scenarier som stöds:

1. **Helskärmsläge för en** app – Ingen startmeny visas och en enskild app startas automatiskt när användaren loggar in. <br> *I exemplet* används : En enhet som endast kör Appen Dynamics 365-guider.
2. **Helskärmsläge för flera** appar – Start-menyn visar endast de program som angavs i helskärmskonfigurationen när en användare loggar in. Du kan välja att starta en app automatiskt om du vill. <br> *Exempel använder*: En enhet som endast visar Store-appen, Feedbackhubben och Inställningar på Start-menyn.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Beskrivning av helskärmsläge när en användare loggar in

I följande tabell visas funktionerna i de olika helskärmslägena.

| &nbsp; |Start-menyn |Snabbåtgärder-menyn |Kamera och video |Miracast |Cortana |Inbyggda röstkommandon |
| --- | --- | --- | --- | --- | --- | --- |
|Helskärmsläge för en app |Inaktiverad |Inaktiverad |Inaktiverad |Inaktiverad   |Inaktiverad |Aktiverad* |
|Helskärmsläge för flera appar |Enabled |Aktiverad*  |Tillgänglig*  |Tillgänglig* |Tillgänglig*   |Aktiverad*  |

\*Mer information om hur du aktiverar inaktiverade funktioner eller hur röstkommandon interagerar med inaktiverade funktioner och Cortana finns [i HoloLens AUMIDs för appar.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Viktiga allmänna överväganden innan du konfigurerar helskärmsläge

1. Fastställ vilken typ av användarkonto som HoloLens i din miljö – HoloLens stöder Azure Active Directory-konton (AAD), Microsoft-konton (MSA) och lokala konton. Dessutom stöds även tillfälligt skapade konton som kallas gäster/besökare (endast för AAD-anslutna enheter). Läs mer i [Hantera användaridentitet och inloggning för HoloLens](hololens-identity.md).
2. Fastställ målen för helskärmsläge – Oavsett om det är alla, en enskild användare, vissa användare eller användare som är medlemmar i AAD-grupper osv.
3. För helskärmsläge för flera appar bestämmer du vilka program som ska visas på Start-menyn. För varje program krävs [dess PROGRAManvändarmodell-ID (AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Kontrollera om helskärmsläget ska tillämpas på HoloLens via antingen runtime-etableringspaket eller MDM-servern (Mobile Enhetshantering).

## <a name="security-considerations"></a>Säkerhetsöverväganden

Helskärmsläge bör inte betraktas som en säkerhetsmetod, utan som ett sätt att styra startupplevelsen vid användar inloggning. Du kan kombinera helskärmsläge med alternativen som anges nedan om det finns specifika säkerhetsrelaterade behov:

- När Inställningar har konfigurerats för att visas i helskärmsläge och du vill styra vilka sidor som visas i Inställningar-appen kan du gå till [Sidvisning Inställningar synlighet](settings-uri-list.md)
- När du vill styra åtkomsten till vissa maskinvarufunktioner, till exempel kamera, Bluetooth osv. för vissa appar, se Principer i [Princip-CSP](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)som stöds av HoloLens 2 – Windows Client Management . Du kan läsa våra [vanliga enhetsbegränsningar](hololens-common-device-restrictions.md) för idéer.
- Helskärmsläge blockerar inte en app (konfigurerad som en del av helskärmsläget) från att starta andra appar. Om du vill blockera start av vissa appar/processer på HoloLens kan du gå till Använda Windows Defender Application Control på [HoloLens 2](/mem/intune/configuration/custom-profile-hololens) enheter i Microsoft Intune – Azure

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Viktiga tekniska överväganden för helskärmsläge för HoloLens

Gäller endast om du planerar att använda etableringspaket för körning eller skapa kioskkonfigurationer manuellt. I konfigurationen för helskärmsläge används en hierarkisk struktur som baseras på XML:

- En tilldelad åtkomstprofil definierar vilka program som visas på Start-menyn i helskärmsläge. Du kan definiera flera profiler i samma XML-struktur, som du kan referera till senare.
- En tilldelad åtkomstkonfiguration refererar till en profil och målanvändare för profilen, till exempel en viss användare, en AAD-grupp eller en besökare osv. Du kan definiera flera konfigurationer i samma XML-struktur beroende på komplexiteten i dina användningsscenarier (se scenarion som stöds nedan).
- Mer information finns i [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Scenarier som stöds för helskärmsläge baserat på identitetstyp

Se [referenslänkar](hololens-kiosk-reference.md#kiosk-xml-code-samples) för exempel baserat på ditt scenario och uppdatera efter behov innan du kopierar.

> [!NOTE]
> Använd ENDAST XML om du inte använder Intunes användargränssnitt för att skapa helskärmskonfiguration.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>För användare som loggar in som antingen lokalt konto eller MSA

| **Önskad helskärmsupplevelse** | **Rekommenderad kioskkonfiguration** | **Sätt att konfigurera**  | **Kommentarer** |
| --- | --- | --- | --- |
| Alla användare som loggar in får en helskärmsupplevelse. | [Konfigurera en global tilldelad åtkomstprofil för flera appar](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Etablering av körning – flera appar](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global tilldelad åtkomst [kräver 20H2 och nyare byggen](hololens-release-notes.md#windows-holographic-version-20h2) |
| Specifika användare som loggar in får en helskärmsupplevelse.  | [Konfigurera en eller flera app-tilldelade åtkomstprofiler (efter behov) och ange namnet på en viss användare.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Se alternativen som stöds nedan.](#steps-in-configuring-kiosk-mode-for-hololens) | För helskärmsläge för enskilda appar stöds endast lokalt användarkonto eller MSA-konto HoloLens. <br> För helskärmsläge för flera appar stöds endast MSA-konto eller AAD-konto HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>För användare som loggar in som AAD-konto

| **Önskad helskärmsupplevelse** | **Rekommenderad kioskkonfiguration** | **Sätt att konfigurera** | **Kommentarer** |
| --- | --- | --- | --- |
| Alla användare som loggar in får en helskärmsupplevelse. | [Konfigurera en global tilldelad åtkomstprofil för flera appar](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Etablering av körning – flera appar](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global tilldelad åtkomst [kräver 20H2 och nyare byggen](hololens-release-notes.md#windows-holographic-version-20h2) |
| Varje användare som loggar in får en helskärmsupplevelse förutom vissa användare. | [Konfigurera en global tilldelad åtkomstprofil för flera appar genom att exkludera vissa användare (som måste vara enhetsägare).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Etablering av körning – flera appar](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global tilldelad åtkomst [kräver 20H2 och nyare byggen](hololens-release-notes.md#windows-holographic-version-20h2) |
| Varje AAD-användare får en separat helskärmsupplevelse som är specifik för den användaren. | [Konfigurera tilldelad åtkomstkonfiguration för varje användare som anger sitt AAD-kontonamn.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Etablering av körning – flera appar](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Användare i olika AAD-grupper upplever helskärmsläge som endast är för deras grupp. | [Konfigurera tilldelad åtkomstkonfiguration för varje önskad AAD-grupp.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Etablering av körning – flera appar](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • När en användare loggar in och HoloLens är ansluten till Internet, och om användaren är medlem i en AAD-grupp för vilken kioskkonfiguration finns, kommer användaren att uppleva helskärmsläge för den AAD-gruppen. <br> • Om det inte finns något Internet tillgängligt när användaren loggar in, kommer användaren att [HoloLens beteende i felläge.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Om Internettillgänglighet inte garanteras när användaren loggar in och AAD-gruppbaserad informationsdator behöver användas kan du överväga att använda [AADGroupMembershipCacheValidityInDayspolicy.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • För optimal upplevelse med AAD-grupper under inloggningen rekommenderar vi att du använder [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Användare som behöver använda HoloLens för tillfälliga ändamål får en helskärmsupplevelse. | [Konfigurera konfiguration av tilldelad åtkomst för besökare](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Etablering av körning – enskild app](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Tillfälligt användarkonto skapas automatiskt av HoloLens inloggning och tas bort när den tillfälliga användaren loggar ut. <br> • Överväg att aktivera [principen för automatisk inloggning för besökare.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Steg i att konfigurera helskärmsläge för HoloLens

Helskärmskonfigurationer kan skapas och tillämpas på följande sätt:

1. Med MDM-serverns användargränssnitt, t.ex. Intunes kioskmallar eller anpassade OMA-URI-konfigurationer, som sedan fjärrtill tillämpas på HoloLens.
2. Med runtime-etableringspaket, som sedan tillämpas direkt på HoloLens.

Här följer följande sätt att konfigurera, välj fliken som matchar den process som du vill använda.

1. [Microsoft Intune kioskmall för enstaka app](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune kioskmall för flera appar](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune anpassad mall](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Etablering av körning – flera appar](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Etablering av körning – enskild app](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Hur kan besökarkonton automatiskt logga in i helskärmsläge?

På versioner [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) och senare:

- Konfigurationerna AAD och Icke-ADD stöder både besökarkonton som automatiskt har aktiverats för helskärmsläge.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Stöds helskärmsupplevelsen på HoloLens (första generationen)?

Helskärmsläge är endast tillgängligt om enheten har Windows Holographic for Business. Alla HoloLens 2 enheter levereras med Windows Holographic for Business och det finns inga andra utgåvor. Varje HoloLens 2-enhet kan köra helskärmsläge från lådan.

HoloLens (första generationens) enheter måste uppgraderas både när det gäller operativsystemsversion och OS-version. Här finns mer information om hur du uppdaterar en [](hololens1-upgrade-enterprise.md) HoloLens (första gen) till Windows Holographic for Business utgåvan. Om du vill uppdatera HoloLens (första generationens) enhet för att använda helskärmsläge måste du först se till att enheten kör Windows 10, version 1803 eller en senare version. Om du har använt Windows Device Recovery-verktyget för att återställa din HoloLens-enhet (första generationens) till standardbygget, eller om du har installerat de senaste uppdateringarna, är enheten redo att konfigurera.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Hur använder jag enhetsportalen för att konfigurera helskärmsläge i icke-produktionsmiljöer?

Konfigurera enheten [HoloLens att använda Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). Den Enhetsportalen är en webbserver på HoloLens som du kan ansluta till från en webbläsare på datorn.

 > [!CAUTION]
 > När du HoloLens att använda Enhetsportalen måste du aktivera Utvecklarläge på enheten. Utvecklarläge på en enhet som har Windows Holographic for Business kan du läsa in appar sida vid sida. Den här inställningen medför dock en risk att en användare kan installera appar som inte har certifierats av Microsoft Store. Administratörer kan blockera möjligheten att aktivera utvecklarläge med hjälp av inställningen **ApplicationManagement/AllowDeveloper Unlock** i [CSP-principen](/windows/client-management/mdm/policy-configuration-service-provider). [Läs mer om Utvecklarläge.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Helskärmsläge kan ställas in via Enhetsportalen:s REST API genom att göra en POST till /api/holographic/kioskmode/settings med en obligatorisk frågesträngsparameter ("kioskModeEnabled" med värdet "true" eller "false") och en valfri parameter ("startupApp" med ett värde för ett paketnamn). Tänk på att Enhetsportalen endast är avsett för utvecklare och inte ska aktiveras på enheter som inte är utvecklare. Den REST API kan komma att ändras i framtida uppdateringar/versioner.

## <a name="troubleshooting"></a>Felsökning

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problem – Inga appar visas på Start-menyn i helskärmsläge

**Symtom**

När fel uppstår vid tillämpning av helskärmsläge visas följande beteende:

- Före Windows Holographic, version 20H2 – HoloLens alla program i Start-menyn.
- Windows Holographic, version 20H2 – om en enhet har en kioskkonfiguration, som är en kombination av både global tilldelad åtkomst och tilldelad åtkomst för AAD-gruppmedlem, visas "inget som visas på Start"-menyn om det inte går att fastställa AAD-gruppmedlemskap.

    ![Bild av vad helskärmsläge nu ser ut när det misslyckas.](images/hololens-kiosk-failure-behavior.png )

- Från och [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)letar helskärmsläget efter global tilldelad åtkomst innan en tom startmeny visas. Helskärmsupplevelsen kommer att gå tillbaka till en global helskärmskonfiguration (om sådan finns) om det uppstår fel i helskärmsläge för AAD-grupp.

**Felsökningsanvisningar**

- Kontrollera att AUMID för appen har angetts korrekt och att den inte innehåller versioner. Exempel finns [HoloLens AUMID:er](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) för inkorgsappar.
- Kontrollera att programmet är installerat på enheten för den användaren.
- Om helskärmskonfigurationen baseras på AAD-grupper ska du se till att det finns en Internetanslutning när AAD-användaren loggar in. Om du vill konfigurerar du [principen MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) så att den även kan fungera utan Internet.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problem – Det gick inte att skapa ett paket med helskärmsläge

**Symtom**

En dialogruta som nedan visas.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Felsökningsanvisningar**

1. Klicka på hyperlänken som visas som i dialogrutan ovan.
1. Öppna ICD.log i en textredigerare och dess innehåll bör indikera felet.

> [!NOTE]
> Om du har gjort flera försök kontrollerar du tidsstämplarna i loggen. Detta hjälper dig att kontrollera de aktuella problemen.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problem – Etableringspaketet har skapats men det gick inte att tillämpa det.

**Symtom**

Felet visas när du tillämpar etableringspaketet på Hololens

**Felsökningsanvisningar**

1. Bläddra till mappen där Windows Configuration Designer-projektet för runtime-etableringspaketet finns.
1. Öppna ICD.log och kontrollera att det inte finns några fel i loggen när du skapar etableringspaketet. Vissa fel visas inte under bygget men loggas fortfarande i ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problem – Flera app-tilldelade åtkomst till AAD-gruppen fungerar inte

**Symtom**

Vid AAD-användarin inloggning försätts inte enheten i helskärmsläge

**Felsökningsanvisningar**

- Bekräfta i KONFIGURATIONs-XML för tilldelad åtkomst att GUID för den AAD-grupp som den inloggade användaren är medlem i används och inte GUID för AAD-användaren.
- Bekräfta att AAD-användaren verkligen visas som medlem i AAD-målgruppen i Intune-portalen.
