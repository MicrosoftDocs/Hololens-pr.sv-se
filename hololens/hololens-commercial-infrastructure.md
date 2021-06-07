---
title: Riktlinjer för infrastruktur för HoloLens
description: Lär dig mer om riktlinjerna för infrastruktur för HoloLens-enheter, inklusive stöd för trådlösa nätverk, fjärrhjälp och hantering av mobila enheter.
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
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379997"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurera ditt nätverk för HoloLens

Den här delen av dokumentet kräver följande personer:

1. Nätverksadministratör med behörighet att göra ändringar i proxyn/brandväggen
2. Azure Active Directory administratör
3. Mobile Enhetshanteraren Admin

## <a name="infrastructure-requirements"></a>Infrastrukturkrav

HoloLens är i grunden en mobil Windows-enhet som är integrerad med Azure.  Det fungerar bäst i kommersiella miljöer med trådlös nätverkstillgänglighet (Wi-Fi) och åtkomst till Microsoft-tjänster.

Viktiga molntjänster är:

- Azure active directory (Azure AD)
- Windows Update (WU)

Kommersiella kunder behöver enterprise mobility management (EMM) eller mdm-infrastruktur för hantering av mobila enheter för att hantera HoloLens-enheter i stor skala.  Den här guiden [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) som exempel, även om alla leverantörer med fullständigt stöd för Microsoft Policy kan stödja HoloLens.  Fråga din leverantör av hantering av mobila enheter om de stöder HoloLens 2.

HoloLens stöder en begränsad uppsättning frånkopplade molnupplevelser.

### <a name="wireless-network-eap-support"></a>EAP-stöd för trådlösa nätverk

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens-specifika nätverkskrav

Kontrollera att den [här listan](hololens-offline.md) över slutpunkter tillåts i nätverksbrandväggen. Detta gör att HoloLens kan fungera korrekt.

### <a name="remote-assist-specific-network-requirements"></a>Specifika nätverkskrav för fjärrhjälp

1. Den rekommenderade bandbredden för optimala prestanda för Remote Assist är 1,5 Mbit/s. Mer information [finns i de detaljerade](https://docs.microsoft.com/MicrosoftTeams/prepare-network) nätverkskraven.
**(Observera att om du inte har nätverkshastigheter på minst 1,5 Mbit/s fungerar Remote Assist fortfarande. Kvaliteten kan dock bli dålig).**
1. Kontrollera att dessa portar och URL:er tillåts i nätverksbrandväggen så att Microsoft Teams kan fungera. Håll dig uppdaterad med den [senaste listan över portar.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Läs mer om de specifika [nätverkskraven för Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Läs mer om hur [du förbereder organisationens nätverk för Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Särskilda nätverkskrav för guider

Guider kräver endast nätverksåtkomst för att ladda ned och använda appen.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory vägledning

> [!NOTE]
> Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.

1. Kontrollera att du har en Azure AD-licens.
Mer information [finns i Licenskrav för HoloLens.](hololens-licenses-requirements.md)

1. Om du planerar att använda automatisk registrering måste du konfigurera [Azure AD-registrering.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Se till att företagets användare finns i Azure Active Directory (Azure AD).
Se följande anvisningar [för att](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) lägga till användare.

1. Vi föreslår att användare som behöver liknande licenser läggs till i samma grupp.
    1. [Skapa en grupp](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Lägga till användare i grupper](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Kontrollera att företagets användare (eller användargrupp) har tilldelats nödvändiga licenser.
Om du behöver tilldela licenser följer du dessa [anvisningar.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)

1. Gör bara det här steget om användarna förväntas registrera sina HoloLens/Mobile-enheter på dig (Det finns tre alternativ) De här stegen säkerställer att företagets användare (eller en grupp av användare) kan lägga till enheter.
    1. **Alternativ 1:** Ge alla användare behörighet att ansluta enheter till Azure AD.
**Logga in på Azure Portal som administratör**  >  **Azure Active Directory**  >  **Enheter**  >  **Enhetsinställningar**  >
 **Ange Användare kan ansluta enheter till Azure AD till *Alla***

    1. **Alternativ 2:** Ge valda användare/grupper behörighet att ansluta enheter till Azure AD Logga in på **Azure Portal** som administratör  >  **Azure Active Directory Enhetsinställningar** Ange Användare kan ansluta enheter till Azure  >    >    >
 **AD** 
 ![ till vald bild som visar konfiguration av Azure AD-anslutna enheter](images/azure-ad-image.png)

    1. **Alternativ 3:** Du kan blockera alla användare från att ansluta sina enheter till domänen. Det innebär att alla enheter måste registreras manuellt.

## <a name="mobile-device-manager-guidance"></a>Vägledning för Enhetshanteraren mobila enheter

### <a name="ongoing-device-management"></a>Pågående enhetshantering

> [!NOTE]
> Det här steget är bara nödvändigt om ditt företag planerar att hantera HoloLens.

Pågående enhetshantering beror på din infrastruktur för hantering av mobila enheter.  De flesta har samma allmänna funktioner, men användargränssnittet kan variera mycket.

1. [Med CPS (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) kan du skapa och distribuera hanteringsinställningar för enheterna i nätverket. Se listan [över HoloLens CPS](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) som referens.

1. [Efterlevnadsprinciper](https://docs.microsoft.com/intune/device-compliance-get-started) är regler och inställningar som enheter måste uppfylla för att vara kompatibla i företagets infrastruktur. Använd dessa principer med villkorlig åtkomst för att blockera åtkomst till företagsresurser för enheter som inte är kompatibla. Du kan till exempel skapa en princip som kräver att BitLocker är aktiverat.

1. [Skapa en efterlevnadsprincip.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)

1. Villkorlig åtkomst tillåter/nekar mobila enheter och mobilappar från att komma åt företagsresurser. Två dokument som kan vara användbara är Plan your CA Deployment (Planera [din CA-distribution)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) [och Best Practices (Metodtips).](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)

1. [Den här](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) artikeln handlar om Intunes hanteringsverktyg för HoloLens.

1. [Skapa en enhetsprofil](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Hantera uppdateringar

Intune innehåller en funktion som kallas uppdateringsringar för Windows 10 enheter, inklusive HoloLens 2 och HoloLens v1 (med Holographic for Business). Uppdateringsringar innehåller en grupp med inställningar som avgör hur och när uppdateringar installeras.

Du kan till exempel skapa en underhållsperiod för installation av uppdateringar, eller välja att datorn startas om när uppdateringarna har installerats.  Du kan också välja att pausa uppdateringar på obestämd tid tills du är redo att uppdatera.

Läs mer om [att konfigurera uppdateringsringar med Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Programhantering

Hantera HoloLens-program via:

1. Microsoft Store  
  Den Microsoft Store är det bästa sättet att distribuera och använda program på HoloLens.  Det finns en bra uppsättning HoloLens-kärnprogram som redan finns i butiken, eller så kan [du publicera dina egna](https://docs.microsoft.com/windows/uwp/publish/).  
  Alla program i butiken är tillgängliga offentligt för alla, men om det inte är acceptabelt kan du kolla Microsoft Store för företag.  

1. [Microsoft Store för företag](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store för företag and Education är en anpassad butik för din företagsmiljö.  Med den kan du använda Microsoft Store inbyggda Windows 10 hololens för att hitta, hämta, distribuera och hantera appar för din organisation.  Du kan också distribuera appar som är specifika för din kommersiella miljö men inte för världen.

1. Programdistribution och -hantering via Intune eller någon annan lösning för hantering av mobila enheter  
  De flesta lösningar för hantering av mobila enheter, inklusive Intune, är ett sätt att distribuera affärsprogram direkt till en uppsättning registrerade enheter.  Läs den här artikeln om [att installera Intune-appen.](https://docs.microsoft.com/intune/apps-deploy)

1. _rekommenderas inte_ Enhetsportalen  
  Program kan också installeras på HoloLens direkt med hjälp av Windows Enhetsportalen.  Detta rekommenderas inte eftersom utvecklarläget måste vara aktiverat för att använda enhetsportalen.

Läs mer om [att installera appar på HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### <a name="certificates"></a>Certifikat

Du kan distribuera certifikat via MDM-providern. Om ditt företag kräver certifikat stöder Intune PKCS, PFX och SCEP. Det är viktigt att förstå vilket certifikat som är rätt för ditt företag. Gå till dokumentationen [om certifikatkonfigurationer](https://docs.microsoft.com/intune/protect/certificates-configure) för att avgöra vilket certifikat som är bäst för dig. Om du planerar att använda certifikat för HoloLens-autentisering kan PFX eller SCEP vara rätt för dig.

Se följande steg för att använda [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Uppgradera till Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (commercial suite) är endast avsett för HoloLens 1:a gen-enheter. Profilen tillämpas inte på HoloLens 2-enheter.

Anvisningar för hur du uppgraderar till den kommersiella sviten finns i dokumentationen [om holografiska](https://docs.microsoft.com/intune/configuration/holographic-upgrade) uppgraderingar.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Så här konfigurerar du helskärmsläge med Microsoft Intune

1. Synkronisera Microsoft Store till Intune (se följande [anvisningar).](https://docs.microsoft.com/intune/apps/windows-store-for-business)

1. Kontrollera appinställningarna
    1. Logga in på ditt Microsoft Store Business-konto
    1. **Hantera > Produkter och tjänster > Appar och programvara > Välj den app som du vill synkronisera > Private Store-tillgänglighet > Välj "Alla" eller "Specifika grupper"**
        >[!NOTE]
        >Om du inte ser den app som du vill använda måste du "hämta" appen genom att söka i Butiken efter din app. Klicka på sökfältet i det övre högra hörnet > skriver in namnet på appen > klickar på **appen och > väljer "Hämta".**
    1. Om du inte ser dina appar **i Intune > Client Apps > Apps** kan du behöva synkronisera dina [appar](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) igen.

1. [Skapa en enhetsprofil för helskärmsläge](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Du kan konfigurera olika användare så att de har olika funktioner för helskärmsläge genom att använda "Azure AD" som "Användarinloggningstyp". Det här alternativet är dock endast tillgängligt i helskärmsläge för flera appar. Helskärmsläge för flera appar fungerar bara med en app och flera appar.

![Bild som visar konfiguration av helskärmsläge i Intune](images/aad-kioskmode.png)

Information om andra MDM-tjänster finns i leverantörens dokumentation. Läs [HoloLens kioskinstruktioner](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) om du behöver använda en anpassad inställning och fullständig XML-konfiguration för att konfigurera en helskärm i MDM-tjänsten.

## <a name="certificates-and-authentication"></a>Certifikat och autentisering

Certifikat kan distribueras via din MDM (se "certifikat" i [MDM-avsnittet](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Certifikat kan också distribueras till HoloLens via paketetablering. Mer information [finns i HoloLens-etablering.](hololens-provisioning.md)

### <a name="additional-intune-quick-links"></a>Ytterligare intune-snabblänkar

1. [Skapa profiler:](https://docs.microsoft.com/intune/configuration/device-profile-create) Med profiler kan du lägga till och konfigurera inställningar som ska skickas till enheterna i din organisation.

