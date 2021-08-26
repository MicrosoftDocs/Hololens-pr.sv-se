---
title: Riktlinjer för infrastruktur för HoloLens
description: Lär dig mer om riktlinjerna för infrastruktur HoloLens enheter, inklusive stöd för trådlösa nätverk, fjärrhjälp och hantering av mobila enheter.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9b306b10ff82603fd238f195beacc300f1a82bf6
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859008"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurera ditt nätverk för HoloLens

Den här delen av dokumentet kräver följande personer:

1. Nätverksadministratör med behörighet att göra ändringar i proxyn/brandväggen
2. Azure Active Directory Admin
3. Mobile Enhetshanteraren Admin

## <a name="infrastructure-requirements"></a>Infrastrukturkrav

HoloLens är i grunden en mobil Windows som är integrerad med Azure.  Det fungerar bäst i kommersiella miljöer med trådlös nätverkstillgänglighet (Wi-Fi) och åtkomst till Microsoft-tjänster.

Viktiga molntjänster är:

- Azure active directory (Azure AD)
- Windows Uppdatera (WU)

Kommersiella kunder behöver enterprise mobility management (EMM) eller mdm-infrastruktur (hantering av mobilenheter) för att hantera HoloLens enheter i stor skala.  Den här guiden [använder Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) exempel, även om alla leverantörer med fullständigt stöd för Microsoft Policy kan stödja HoloLens.  Fråga din leverantör av hantering av mobila enheter om de stöder HoloLens 2.

HoloLens stöder en begränsad uppsättning frånkopplade molnupplevelser.

### <a name="wireless-network-eap-support"></a>EAP-stöd för trådlöst nätverk

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Specifika nätverkskrav

Kontrollera att den [här listan](hololens-offline.md) över slutpunkter tillåts i nätverksbrandväggen. Detta gör att HoloLens fungerar korrekt.

### <a name="remote-assist-specific-network-requirements"></a>Specifika nätverkskrav för Fjärrhjälp

1. Den rekommenderade bandbredden för optimala prestanda för Remote Assist är 1,5 Mbit/s. Mer information [finns i de detaljerade](/MicrosoftTeams/prepare-network) nätverkskraven.
**(Observera att om du inte har nätverkshastigheter på minst 1,5 Mbit/s kommer Remote Assist fortfarande att fungera. Kvaliteten kan dock bli dålig).**
1. Kontrollera att dessa portar och URL:er tillåts i nätverksbrandväggen för att Microsoft Teams ska fungera. Håll dig uppdaterad med den [senaste listan med portar](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Läs mer om de specifika [nätverkskraven för Fjärrhjälp](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Läs mer om hur [du förbereder organisationens nätverk för Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Guidespecifika nätverkskrav

Guider kräver endast nätverksåtkomst för att ladda ned och använda appen.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Vägledning

> [!NOTE]
> Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.

1. Kontrollera att du har en Azure AD-licens.
Läs [HoloLens licenskrav för](hololens-licenses-requirements.md) ytterligare information.

1. Om du planerar att använda automatisk registrering måste du konfigurera [Azure AD-registrering.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Se till att företagets användare finns i Azure Active Directory (Azure AD).
Se följande anvisningar [för att](/azure/active-directory/fundamentals/add-users-azure-active-directory) lägga till användare.

1. Vi föreslår att användare som behöver liknande licenser läggs till i samma grupp.
    1. [Skapa en grupp](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Lägga till användare i grupper](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Se till att företagets användare (eller användargrupp) tilldelas nödvändiga licenser.
Om du behöver tilldela licenser följer du dessa [anvisningar.](/azure/active-directory/fundamentals/license-users-groups)

1. Gör bara det här steget om användarna förväntas registrera sina HoloLens/Mobila enheter på dig (Det finns tre alternativ) Dessa steg säkerställer att företagets användare (eller en grupp användare) kan lägga till enheter.
    1. **Alternativ 1:** Ge alla användare behörighet att ansluta enheter till Azure AD.
**Logga in på Azure Portal som administratör**  >  **Azure Active Directory**  >  **Enheter**  >  **Enhets-Inställningar**  >
 **Ange Användare kan ansluta enheter till Azure AD till *Alla***

    1. **Alternativ 2:** Ge valda användare/grupper behörighet att ansluta enheter till Azure AD Logga **in** på Azure Portal som administratör Azure Active Directory Enheter Enhet Inställningar Ange användare kan ansluta enheter till Azure AD till vald avbildning som visar Konfiguration av  >    >    >    >
 **** 
 ![ Azure AD-anslutna enheter](images/azure-ad-image.png)

    1. **Alternativ 3:** Du kan blockera alla användare från att ansluta sina enheter till domänen. Det innebär att alla enheter måste registreras manuellt.

## <a name="mobile-device-manager-guidance"></a>Vägledning för Enhetshanteraren mobila enheter

### <a name="ongoing-device-management"></a>Pågående enhetshantering

> [!NOTE]
> Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.

Pågående enhetshantering beror på din infrastruktur för hantering av mobila enheter.  De flesta har samma allmänna funktioner, men användargränssnittet kan variera mycket.

1. [Med CPS (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) kan du skapa och distribuera hanteringsinställningar för enheterna i nätverket. Se listan [över HoloLens för](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) referens.

1. [Efterlevnadsprinciper](/intune/device-compliance-get-started) är regler och inställningar som enheter måste uppfylla för att vara kompatibla i företagets infrastruktur. Använd dessa principer med villkorlig åtkomst för att blockera åtkomst till företagsresurser för enheter som inte är kompatibla. Du kan till exempel skapa en princip som kräver att BitLocker är aktiverat.

1. [Skapa en efterlevnadsprincip.](/intune/protect/compliance-policy-create-windows)

1. Villkorlig åtkomst tillåter/nekar mobila enheter och mobila program från att komma åt företagsresurser. Två dokument som kan vara användbara är Plan your CA Deployment (Planera [distributionen av certifikatutfärdaren)](/azure/active-directory/conditional-access/plan-conditional-access) [och Best Practices (Metodtips).](/azure/active-directory/conditional-access/best-practices)

1. [Den här](/intune/fundamentals/windows-holographic-for-business) artikeln beskriver Intunes hanteringsverktyg för HoloLens.

1. [Skapa en enhetsprofil](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Hantera uppdateringar

Intune innehåller en funktion som kallas uppdateringsringar för Windows 10-enheter, inklusive HoloLens 2 och HoloLens v1 (med Holographic for Business). Uppdateringsringar innehåller en grupp inställningar som avgör hur och när uppdateringar installeras.

Du kan till exempel skapa en underhållsperiod för installation av uppdateringar, eller välja att datorn startas om när uppdateringarna har installerats.  Du kan också välja att pausa uppdateringar på obestämd tid tills du är redo att uppdatera.

Läs mer om [att konfigurera uppdateringsringar med Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Programhantering

Hantera HoloLens program via:

1. Microsoft Store  
  Den Microsoft Store är det bästa sättet att distribuera och använda program på HoloLens.  Det finns en bra uppsättning grundläggande HoloLens program som redan finns i butiken eller så kan [du publicera dina egna](/windows/uwp/publish/).  
  Alla program i butiken är tillgängliga offentligt för alla, men om det inte är acceptabelt kan du gå till Microsoft Store för företag.  

1. [Microsoft Store för företag](/microsoft-store/)  
  Microsoft Store för företag and Education är en anpassad butik för din företagsmiljö.  Du kan använda de Microsoft Store inbyggda Windows 10 och HoloLens för att hitta, hämta, distribuera och hantera appar för din organisation.  Du kan också distribuera appar som är specifika för din kommersiella miljö men inte för världen.

1. Programdistribution och -hantering via Intune eller någon annan lösning för hantering av mobila enheter  
  De flesta lösningar för hantering av mobila enheter, inklusive Intune, är ett sätt att distribuera affärsprogram direkt till en uppsättning registrerade enheter.  Se den här artikeln för [installation av Intune-appen.](/intune/apps-deploy)

1. _rekommenderas inte_ Enhetsportalen  
  Program kan också installeras på HoloLens direkt med hjälp av Windows Enhetsportalen.  Detta rekommenderas inte eftersom utvecklarläget måste vara aktiverat för att använda enhetsportalen.

Läs mer om [att installera appar på HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certifikat

Du kan distribuera certifikat via MDM-providern. Om ditt företag kräver certifikat stöder Intune PKCS, PFX och SCEP. Det är viktigt att förstå vilket certifikat som är rätt för ditt företag. Gå till dokumentationen [om certifikatkonfigurationer](/intune/protect/certificates-configure) för att avgöra vilket certifikat som är bäst för dig. Om du planerar att använda certifikat för HoloLens autentisering kan PFX eller SCEP vara rätt för dig.

Se följande steg för att använda [SCEP](/intune/protect/certificates-profile-scep).

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Uppgradera till Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (commercial suite) är endast avsett för HoloLens första generationens enheter. Profilen tillämpas inte på HoloLens 2 enheter.

Anvisningar för hur du uppgraderar till den kommersiella sviten finns i dokumentationen [om holografiska](/intune/configuration/holographic-upgrade) uppgraderingar.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Så här konfigurerar du helskärmsläge med Microsoft Intune

1. Synkronisera Microsoft Store till Intune (se följande [anvisningar).](/intune/apps/windows-store-for-business)

1. Kontrollera appinställningarna
    1. Logga in på Microsoft Store företagskonto
    1. **Hantera > Products and Services > Apps and Software > Välj den app som du vill synkronisera > Private Store-tillgänglighet > Välj "Alla" eller "Specifika grupper"**
        >[!NOTE]
        >Om du inte ser den app som du vill använda måste du "hämta" appen genom att söka i Butiken efter din app. Klicka på sökfältet i det övre högra hörnet > skriver in namnet på appen > klickar på appen och **> väljer "Hämta".**
    1. Om du inte ser dina appar **i Intune > Client Apps > Apps** kan du behöva synkronisera dina [appar](/intune/apps/windows-store-for-business#synchronize-apps) igen.

1. [Skapa en enhetsprofil för helskärmsläge](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Du kan konfigurera olika användare så att de har olika kiosklägesupplevelser genom att använda "Azure AD" som "Användarinloggningstyp". Det här alternativet är dock endast tillgängligt i helskärmsläge för flera appar. Helskärmsläge för flera appar fungerar bara med en app och flera appar.

![Bild som visar konfiguration av helskärmsläge i Intune](images/aad-kioskmode.png)

Information om andra MDM-tjänster finns i leverantörens dokumentation. Läs anvisningarna [HoloLens helskärmsläge](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) om du behöver använda en anpassad inställning och fullständig XML-konfiguration för att konfigurera en helskärmsläge i MDM-tjänsten.

## <a name="certificates-and-authentication"></a>Certifikat och autentisering

Certifikat kan distribueras via din MDM (se "certifikat" i [MDM-avsnittet](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Certifikat kan också distribueras till HoloLens via paketetablering. Mer [information HoloLens finns](hololens-provisioning.md) i HoloLens etablering.

### <a name="additional-intune-quick-links"></a>Ytterligare intune-snabblänkar

1. [Skapa profiler:](/intune/configuration/device-profile-create) Med profiler kan du lägga till och konfigurera inställningar som ska skickas till enheterna i din organisation.

