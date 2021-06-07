---
title: Distributionsguide för externa klienter
description: Distributionsguide för HoloLens 2 för externa klienter (med Fjärrhjälp som exempel)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378779"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Distribuera HoloLens 2 till externa klienter med fjärrhjälp

Den här guiden hjälper IT-proffs med följande mål att distribuera Microsoft HoloLens 2 enheter i organisationen:

1. Cloud Connect HoloLens 2-enheter
1. Låna HoloLens 2-enheter till externa klienter för användning
1. Säkra lånade enheter

Den här guiden ger allmänna [HoloLens 2-distributionsrekommendationer](#general-deployment-recommendations-and-instructions) som gäller för [](#common-concerns) de flesta HoloLens 2-distributionsscenarier och vanliga problem som kunder har när de distribuerar Remote Assist för extern användning.

## <a name="scenario-description"></a>Scenariobeskrivning

I det här dokumentet vill Contoso Company skicka en HoloLens 2-enhet till en extern klients anläggning för kortsiktig eller långsiktig användning. När klienten behöver hjälp med att underhålla maskiner loggar klienten in på HoloLens 2-enheten med autentiseringsuppgifter som tillhandahålls av Contoso Company och använder Remote Assist för att kontakta Contosos experter.

Läs mer om Remote Assist [här.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Krav för det här scenariot

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobila Enhetshanteraren – till exempel [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-licens
    1. [Köp Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Fjärrhjälp för utvärderingsversion](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Vanliga problem

- [Så här ser du till att externa klienter inte kan kommunicera med varandra](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Så här ser du till att klienter inte har åtkomst till företagsresurser](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Så här begränsar du appar](#how-to-restrict-apps)
- [Hantera lösenord](#how-to-manage-passwords)
- [Så här ser du till att klienter inte har åtkomst till chatthistorik](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Så här ser du till att externa klienter inte kan kommunicera med varandra

Eftersom Remote Assist HoloLens till HoloLens-anrop inte stöds kan klienter söka efter, men kan inte kommunicera med varandra. För att ytterligare begränsa vilka klienter som kan söka efter och anropa,  [kan informationsbarriärer](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) begränsa vem en klient kan kommunicera med. Ett annat alternativ att överväga är att [använda begränsad katalogsökning](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Eftersom enkel inloggning är aktiverat är det viktigt att inaktivera webbläsaren med [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Om en extern klient öppnar webbläsaren och använder webbversionen av Teams har klienten åtkomst till samtals-/chatthistorik.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Så här ser du till att klienter inte har åtkomst till företagsresurser

Det finns två alternativ att överväga.

Det första alternativet är en metod med flera lager:

1. Tilldela endast licenser som användaren behöver. Om du inte tilldelar OneDrive, Outlook, SharePoint, Yammer osv. till användaren kommer han/hon inte att ha åtkomst till dessa resurser. De enda licenser som användarna behöver är Remote Assist-, Intune- och AAD-licenser för att börja.
1. Blockera appar (till exempel e-post) som du inte vill att klienterna ska få åtkomst till [(se Så här begränsar du appar).](#how-to-restrict-apps)
1. Dela INTE användarnamn eller lösenord med klienter. För att logga in på HoloLens 2 krävs ett e-postmeddelande och en numerisk PIN-kod.

Det andra alternativet är att skapa en separat klientorganisation som är värd för klienter (se Bild 1.1).

**Bild 1.1**

![Avbildning av tjänstklientorganisation](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Så här begränsar du appar

[Helskärmsläge](https://docs.microsoft.com/hololens/hololens-kiosk) och/eller [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) är alternativ för att begränsa program.

### <a name="how-to-manage-passwords"></a>Hantera lösenord

1. Ta bort lösenordets giltighetstid. Detta ökar dock risken för att ett konto komprometteras. Rekommendationen för NIST-lösenord är att ändra lösenord var 30–90:e dag.
1. Utöka lösenordets giltighetstid för HoloLens 2-enheter till att överskrida 90 dagar.
1. Enheterna ska returneras till Contoso för att ändra lösenorden. Detta kan dock orsaka problem om enheterna förväntas finnas på klientens anläggning i över 90 dagar.  
1. För enheter som skickas till flera klienter måste du återställa lösenorden innan du skickar enheten till klienter.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Så här ser du till att klienter inte har åtkomst till chatthistorik

Remote Assist rensar chatthistoriken efter varje session. Chatthistoriken kommer dock att vara tillgänglig för Microsoft Teams-användaren.

> [!NOTE]
> Eftersom enkel inloggning är aktiverat är det viktigt att inaktivera webbläsaren med [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Om en extern klient öppnar webbläsaren och använder webbversionen av Teams har klienten åtkomst till samtals-/chatthistorik.

## <a name="general-deployment-recommendations-and-instructions"></a>Allmänna distributionsrekommendationer och instruktioner

Vi rekommenderar följande för HoloLens 2-distributionssteg:

1. Använd den [senaste HoloLens OS-versionen](https://aka.ms/hololens2download) som baslinjeversion.
1. Tilldela användarbaserade eller enhetsbaserade licenser:
    1. Användarbaserade och enhetsbaserade licenser följer båda följande steg:
        1. [Skapa en grupp i AAD och lägg till medlemmar](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) för HoloLens/RA-användare.
        1. [Tilldela enhetsbaserade eller användarbaserade licenser till](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) den här gruppen.
        1. (Valfritt) Du kan rikta in dig på grupper för MDM-principer.

1. Enheterna ska vara AAD-anslutna till din klientorganisation, [automatiskt registrerade](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)och konfigurerade via [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).
    1. Observera att den första användaren på enheten blir enhetens ägare.
    1. Observera att om enheten är AAD-ansluten blir användaren som utförde anslutningarna enhetens ägare.
    1. Mer information finns i [Enhetsägare.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [Klientorganisationen låser](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) enheten så att den bara kan vara ansluten till din klientorganisation.
    1. **Ytterligare länk: CSP** [för klientlås.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Konfigurera helskärmsläge med global tilldelad åtkomst [till här](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).
1. Vi rekommenderar att du inaktiverar följande (valfritt) funktioner:
    1. Möjlighet att föra in enheten i utvecklarläge [här.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Möjlighet att ansluta HoloLens till en dator för att kopiera datum inaktivera [USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Om du inte vill inaktivera USB men vill kunna använda ett etableringspaket på enheten via USB följer du anvisningarna som anges [**här.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Använd [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) för att tillåta eller blockera appar på HoloLens 2-enheten.
1. Uppdatera Remote Assist till den senaste versionen som en del av installationen. Det finns två alternativ för att göra detta:
    1. Detta kan göras genom att gå till Windows **Microsoft Store --> Remote Assist --> och Uppdatera app**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – som tillåter automatiska appuppdateringar – är aktiverat som standard. Håll enheten ansluten för att ta emot uppdateringar.
1. [Inaktivera alla inställningssidor](https://docs.microsoft.com/hololens/settings-uri-list) utom nätverksinställningarna så att användarna kan ansluta till gästnätverk på klientplatser.
1. [Hantera HoloLens-uppdateringar](https://docs.microsoft.com/hololens/hololens-updates)
    1. Alternativ för [att styra OS-uppdateringar](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) eller tillåta att flöda fritt.
1. [Vanliga enhetsbegränsningar.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
