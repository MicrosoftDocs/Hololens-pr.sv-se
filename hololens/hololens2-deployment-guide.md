---
title: Distribuera molnanslutna HoloLens 2 till externa klienter
description: Distributionsguide för HoloLens 2 för externa klienter (med fjärrhjälp som exempel)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033407"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Distribuera molnanslutna HoloLens 2 till externa klienter

Den här guiden är ett tillägg till [den molnanslutna distributionsguiden.](hololens2-cloud-connected-overview.md) Den används i situationer där din organisation vill skicka HoloLens 2 enheter till en extern klients anläggning för kort- eller långsiktig användning. Den externa klienten loggar in på HoloLens 2-enheten med de autentiseringsuppgifter som tillhandahålls av din organisation och använder [Remote Assist](/dynamics365/mixed-reality/remote-assist/ra-overview) för att kontakta dina experter. Den här guiden [innehåller allmänna HoloLens 2-distributionsrekommendationer](#general-deployment-recommendations) som gäller för de [](#common-external-client-deployment-concerns) flesta externa HoloLens 2-distributionsscenarier och vanliga problem som kunder har när de distribuerar Remote Assist för extern användning. 

## <a name="prerequisites"></a>Förutsättningar

Följande infrastruktur bör vara på plats enligt den [molnanslutna distributionsguiden](hololens2-cloud-connected-overview.md) för att distribuera HoloLens 2 externt.

- Azure AD Join med mdm-automatisk registrering – MDM-hanterad (Intune)
- Användare loggar in med sitt eget företagskonto (Azure AD)
    - En eller flera användare per enhet stöds.

### <a name="remote-assist-licensing-and-requirements"></a>Licensiering och krav för Remote Assist

- Azure AD-konto (krävs för att köpa prenumerationen och tilldela licenser)
- [Remote Assist-prenumeration](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (eller [Remote Assist-utvärderingsversion)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

Mer [information om Remote Assist finns i](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-användare

- Remote Assist-licens
- Nätverksanslutning

### <a name="microsoft-teams-user"></a>Microsoft Teams användare

- Microsoft Teams eller [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Nätverksanslutningar

## <a name="general-deployment-recommendations"></a>Allmänna distributionsrekommendationer

Vi rekommenderar följande steg för extern distribution HoloLens 2:

1. Använd den [senaste versionen HoloLens operativsystem som](https://aka.ms/hololens2download) baslinjeversion.
1. Tilldela användarbaserade eller enhetsbaserade licenser genom att följa stegen nedan:
    1. [Skapa en grupp i AAD och lägg till medlemmar](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) för HoloLens/RA-användare.
    1. [Tilldela enhetsbaserade eller användarbaserade licenser till den](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) här gruppen.
    1. (Valfritt) Målgrupper för [MDM-principer (hantering av mobil](hololens-enroll-mdm.md) enhet).

1. Anslut AAD-enheter till din klientorganisation, [registrera automatiskt](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)och konfigurera via [Autopilot](/hololens/hololens2-autopilot). Mer information finns i [enhetens ägare.](/hololens/security-adminless-os#device-owner)
    1. Den första användaren på enheten blir enhetens ägare.
    1. Om enheten är AAD-ansluten görs användaren som utförde anslutningarna till enhetens ägare.
    
1. [Lås enheten](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) i klientorganisationen så att den bara kan vara ansluten av din klientorganisation.
    1. Se även [CSP för klientlås.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Konfigurera helskärmsläge med global tilldelad åtkomst](/hololens/hololens-global-assigned-access-kiosk).

1. Inaktivera följande (valfritt) funktioner:
    1. Möjlighet att placera enheten i utvecklarläge [här.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Möjlighet att ansluta HoloLens till en dator för att kopiera datum inaktivera [USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Om du inte vill inaktivera USB men vill kunna använda ett etableringspaket på enheten via USB följer du anvisningarna för hur du tillåter installation av [etableringspaket.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Använd [Windows Defender programkontroll (WDAC)](/hololens/windows-defender-application-control-wdac) för att tillåta eller blockera appar på HoloLens 2-enheten.
1. Uppdatera Remote Assist till den senaste versionen som en del av installationen. Överväg följande två alternativ:
    1. Gå till Windows **Microsoft Store --> Remote Assist --> och Uppdatera app.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – som tillåter automatiska appuppdateringar – är aktiverat som standard. Håll enheten ansluten för att ta emot uppdateringar.
1. [Inaktivera alla inställningssidor](/hololens/settings-uri-list) utom nätverksinställningarna för att tillåta användare att ansluta till gästnätverk på klientplatser.
1. [Hantera HoloLens uppdateringar](/hololens/hololens-updates)
    1. Alternativ för [att styra OS-uppdateringar](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) eller tillåta att flödet flödar fritt.
1. Ange [vanliga enhetsbegränsningar.](/hololens/hololens-common-device-restrictions)

Nu är dina externa klienter redo att använda sina HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Vanliga problem med distribution av externa klienter

- [Se till att klienter inte kan kommunicera med varandra](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Se till att klienter inte kan komma åt företagsresurser](#ensure-that-clients-wont-have-access-to-company-resources)
- [Dölja eller begränsa appar](#hidden-or-restricted-apps)
- [Hantera lösenord för dina klienter](#password-management-for-your-clients) 
- [Se till att klienter inte kan komma åt chatthistoriken](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Se till att externa klienter inte kan kommunicera med varandra

Remote Assist HoloLens till HoloLens-anrop stöds inte. Klienter kan söka efter, men kan inte kommunicera med varandra. [Informationsbarriärer i Microsoft 365](/microsoft-365/compliance/information-barriers) kan ytterligare begränsa med vem en klient kan söka efter och anropa. Ett annat alternativ är att [använda Microsoft Teams begränsad katalogsökning](/MicrosoftTeams/teams-scoped-directory-search).

 > [!NOTE]
> Eftersom enkel inloggning är aktiverat är det viktigt att inaktivera webbläsaren med hjälp [Windows Defender programkontroll (WDAC).](/hololens/windows-defender-application-control-wdac) Om en extern klient öppnar webbläsaren och använder webbversionen av Teams har klienten åtkomst till din chatthistorik.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Se till att klienterna inte har åtkomst till företagsresurser

Det finns två alternativ att överväga.

Det första alternativet är en metod med flera lager:

1. Tilldela endast licenser som användaren behöver. Om du inte tilldelar OneDrive, Outlook, SharePoint, Yammer osv. har användaren inte åtkomst till dessa resurser. De enda licenser som användarna behöver är Remote Assist-, Intune- och AAD-licenser för att börja.
1. Blockera appar (till exempel e-post) som du inte vill att klienterna ska komma åt (Se [Appar är dolda eller begränsade).](#apps are hidden or restricted)
1. Dela inte användarnamn eller lösenord med klienter. För att logga in på HoloLens 2 krävs en e-postadress och en numerisk PIN-kod.

Det andra alternativet är att skapa en separat klient som är värd för klienter (se Bild 1.1).

**Bild 1.1**

![Avbildning av tjänstklientorganisation.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Dolda eller begränsade appar

[Helskärmsläge](/hololens/hololens-kiosk) [och/eller Windows Defender programkontroll (WDAC)](/hololens/windows-efender-application-control-wdac) är alternativ för att dölja och/eller begränsa program.

### <a name="password-management-for-your-clients"></a>Lösenordshantering för dina klienter

1. Ta bort lösenordets giltighetstid. Det här alternativet kan dock öka risken för att ett konto komprometteras. Nist-lösenordsrekommendation är att ändra lösenord var 30–90:e dag.
1. Utöka lösenordets giltighetstid för HoloLens 2 enheter så att de överskrider 90 dagar.
1. Enheterna ska returneras till din organisation för att ändra lösenorden. Det här alternativet kan dock orsaka problem om enheterna förväntas finnas på klientens anläggning i över 90 dagar.  
1. För enheter som skickas till flera klienter återställer du lösenorden innan du skickar enheten till klienter.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Kontrollera att klienterna inte har åtkomst till chatthistoriken

Remote Assist rensar chatthistoriken efter varje session. Chatthistorik kommer dock att vara tillgänglig för Microsoft Teams användare.

> [!NOTE]
> Eftersom enkel inloggning är aktiverat är det viktigt att inaktivera webbläsaren med hjälp [Windows Defender programkontroll (WDAC).](/hololens/windows-defender-application-control-wdac)  Om en extern klient öppnar webbläsaren och använder webbversionen av Teams har klienten åtkomst till samtals-/chatthistorik.
