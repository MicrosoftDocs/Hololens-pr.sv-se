---
title: Använda Microsofts Endpoint Manager Intune för att hantera HoloLens enheter
description: Lär dig hur du använder MDM för att konfigurera CSP, princip och hantera HoloLens enheter med mixad verklighet i stor skala med Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0a0f26750ff6ea881babfab44af95cbbefa0574674336934ccf1443df1701a96
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663263"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Använda Microsofts Endpoint Manager Intune för att hantera HoloLens enheter

Det finns flera olika inställningar som du kan hantera via MDM. Intune-enheter kan grupperas tillsammans och konfigurationer kan distribueras till dessa grupper av användare eller enheter. Appar kan också distribueras och hanteras, konfigurera enheter för att ansluta till nätverket, samt konfigurera uppdateringar så att de sker vid den tidpunkt som önskas och på den uppdateringsring som behövs. 

## <a name="how-to-manage-via-intune"></a>Så här hanterar du via Intune

### <a name="device-categories-and-groups"></a>Enhetskategorier och grupper
Med Intune kan du skapa enhetskategorier för att automatiskt lägga till enheter i grupper baserat på kategorier som du skapar, till exempel teknik, sjukvård, utvecklare och så vidare. Tanken är att göra det enklare att hantera enheter som kör Windows Holographic for Business.
Läs mer: [Kategorisera enheter i grupper](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Enhetens konfigurationsprofiler
Intune innehåller inställningar och funktioner som du kan aktivera eller inaktivera på olika enheter i din organisation. Dessa inställningar och funktioner hanteras med hjälp av profiler. Du kan till exempel skapa en profil som aktiverar Cortana eller använder Microsoft Defender SmartScreen på enheter som kör Windows Holographic for Business.
Du kan använda OMA-URI i dina profiler för att anpassa vissa inställningar, skapa enhetsbegränsningar och konfigurera ett virtuellt privat nätverk (VPN) och ett trådlöst nätverk.
[Kom igång med konfigurationsprofiler](/mem/intune/configuration/device-profiles)och [profilöversikt.](/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Exempel på vad som kan hanteras och konfigureras

Om du använder MDM för att hantera enheter får du en mängd olika objekt som kan väljas. 

### <a name="wi-fi"></a>Wi-Fi
Med [Wi-Fi-inställningar](/mem/intune/configuration/wi-fi-settings-configure) kan du tilldela trådlösa nätverksinställningar till användare och enheter. När du tilldelar Wi-Fi profil får användarna åtkomst till företagets Wi-Fi utan att de behöver konfigurera den själva.
Läs mer om [hur du konfigurerar nätverket för HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certifikat
Certifikat förbättrar säkerheten genom att tillhandahålla kontoautentisering, Wi-Fi,VPN-kryptering och SSL-kryptering av webbinnehåll. Även om administratörer kan hantera certifikat på enheter manuellt via etableringspaket är det bästa praxis att använda MDM-systemet för att hantera dessa certifikat under hela livscykeln – från registrering till förnyelse och återkallelse. MDM-systemet kan automatiskt distribuera dessa certifikat till enheternas certifikatarkiv när du har registrerat enheten (så länge MDM-systemet stöder Simple Certificate Enrollment Protocol (SCEP) eller Public Key Cryptography Standards #12 (PKCS #12)). MDM kan också fråga efter och ta bort registrerade klientcertifikat eller utlösa en ny registreringsbegäran innan det aktuella certifikatet upphör att gälla. 

### <a name="proxy"></a>Proxy
De flesta företagsnätverk i intranätet använder en proxy för att hantera intern trafik. Med HoloLens 2 kan du konfigurera en proxyserver för Ethernet och Wi-Fi anslutningar. De här inställningarna gäller inte för VPN-anslutningar. Mer information om proxyinställningar för Windows 10 finns i [NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
Organisationer använder ofta ett VPN för att styra åtkomsten till appar och resurser på företagets intranät. HoloLens 2 har stöd för SSL VPN-anslutningar, som kräver ett nedladdningsbart plugin-program från Microsoft Store och som är specifika för den VPN-leverantör du väljer. 
- Läs mer om [VPN på HoloLens](hololens-network.md#vpn).
- Mer information om VPN-profiler finns i [VPNv2 CSP.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Distribuera och hantera appar
Du kan lägga till appar på enheter som kör Windows Holographic for Business med hjälp av Intune. En MDM-lösning gör det möjligt för IT-beslutsfattare och administratörer att automatiskt installera (push-installera) sina egna verksamhetsapplikationer eller köpa appar via butiken för en grupp användare. Det finns många sätt att distribuera appar på, bland annat:
-   [Intune och Företagsportal]( app-deploy-intune.md)
-   [Microsoft Store för företag]( app-deploy-store-business.md)

Läs mer om apphantering via Intune.
-   [Lägga till appar i Intune](/mem/intune/apps/apps-add)
-   [Lägga till Microsoft Store-appar](/mem/intune/apps/store-apps-windows)
-   [Lägga till appar som du skapar](/mem/intune/apps/lob-apps-windows)
- [Tilldela appar till grupper](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Programuppdateringar
Intune innehåller en funktion som kallas uppdateringsringar för Windows 10-enheter. I dessa uppdateringsringar finns en grupp med inställningar som avgör hur uppdateringar ska installeras. Du kan till exempel skapa en underhållsperiod för installation av uppdateringar, eller välja att datorn startas om när uppdateringarna har installerats. En uppdateringsring kan tillämpas på flera enheter som kör Windows Holographic for Business.
Läs mer om hur du [hanterar HoloLens och](hololens-updates.md) hantera [programuppdateringar via Intune.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Konfigurera kioskläge
Med hjälp av delnings- eller gästdatorfunktionerna i Intune kan du konfigurera Windows Holographic for Business-enheter så att de körs som kiosk. Dessa enheter kan köra en app (kioskläge med en app) eller flera appar (kioskläge med flera appar). Helskärmsläge är ett användargränssnitt för att styra vilka identiteter som har åtkomst till vilka appar som standard.
Lär dig hur [du HoloLens som helskärmsläge]( hololens-kiosk.md)

