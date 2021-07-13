---
title: Förbereda certifikat och nätverksprofiler för HoloLens 2
description: Lär dig hur du konfigurerar, använder, distribuerar och felsöker certifikat för nätverk på HoloLens 2 enheter med mixad verklighet.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639275"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Förbereda certifikat och nätverksprofiler för HoloLens 2

Certifikatbaserad autentisering är ett vanligt krav för kunder som använder HoloLens 2. Du kan kräva certifikat för åtkomst till Wi-Fi, för att ansluta till VPN-lösningar eller för åtkomst till interna resurser i din organisation.

Eftersom HoloLens 2-enheter vanligtvis är anslutna till Azure Active Directory (Azure AD) och hanteras av Intune eller någon annan MDM-provider måste du distribuera sådana certifikat med hjälp av en Simple Certificate Enrollment Protocol-certifikatinfrastruktur (SCEP) eller PKCS-certifikatinfrastruktur (Public Key Cryptography Standard) som är integrerad med din MDM-lösning. 

>[!NOTE]
> Om du inte har en MDM-provider kan [](hololens-provisioning.md#steps-for-creating-provisioning-packages) du fortfarande distribuera certifikat via ett konfigurationspaket i [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) eller via Certificate [Manager](certificate-manager.md) genom att gå till Inställningar > Update & Security > **Certificate Manager**.

## <a name="certificate-requirements"></a>Certifikatkrav
Rotcertifikat krävs för att distribuera certifikat via en SCEP- eller PKCS-infrastruktur. Andra program och tjänster i din organisation kan kräva att rotcertifikat distribueras till dina HoloLens 2-enheter. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi anslutningskrav
För att en enhet ska kunna tillhandahållas automatiskt med den Wi-Fi konfigurationen för företagsnätverket behöver du en Wi-Fi konfigurationsprofil. Du kan konfigurera Intune eller en annan MDM-provider för att distribuera dessa profiler till dina enheter. Om nätverkssäkerheten kräver att enheterna är en del av den lokala domänen kan du också behöva utvärdera din Wi-Fi-nätverksinfrastruktur för att se till att den är kompatibel med HoloLens 2-enheter (HoloLens 2-enheter är endast Azure AD-anslutna).

## <a name="deploy-certificate-infrastructure"></a>Distribuera certifikatinfrastruktur
Om det inte redan finns någon SCEP- eller PKCS-infrastruktur måste du förbereda en. För att stödja användning av SCEP- eller PKCS-certifikat för autentisering kräver Intune att ett [certifikatanslutningsapp används.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> När du använder SCEP med en Microsoft CA måste du också konfigurera [registreringstjänst för nätverksenheter (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Mer information finns i [Konfigurera en certifikatprofil för dina enheter i Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuera certifikat och Wi-Fi/VPN-profil
Följ dessa steg om du vill distribuera certifikat och profiler:
1.  Skapa en profil för vart och ett av rotcertifikaten och mellanliggande certifikaten (se [Skapa betrodda certifikatprofiler](/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Var och en av dessa profiler måste ha en beskrivning som innehåller ett förfallodatum i formatet DD/MM/YYYYY. **Certifikatprofiler utan förfallodatum distribueras inte.**
1.  Skapa en profil för varje SCEP- eller PKCS-certifikat (se Skapa en SCEP-certifikatprofil eller Skapa en [PKCS-certifikatprofil)](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Var och en av dessa profiler måste ha en beskrivning som innehåller ett förfallodatum i formatet DD/MM/ÅYYY. **Certifikatprofiler utan förfallodatum distribueras inte.**

    > [!NOTE]
    > Eftersom HoloLens 2 anses vara en delad enhet, flera användare per enhet, rekommenderar vi att du distribuerar enhetscertifikat i stället för användarcertifikat för Wi-Fi autentisering där det är möjligt

3.  Skapa en profil för varje företagsnätverk Wi-Fi (se [Wi-Fi-inställningar för Windows 10 enheter och senare enheter](/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Vi rekommenderar att Wi-Fi till [enhetsgrupper i](/mem/intune/configuration/device-profile-assign) stället för användargrupper där det är möjligt. 

    > [!TIP]
    > Du kan också exportera en fungerande Wi-Fi profil från en Windows 10 dator i företagsnätverket. Den här exporten skapar en XML-fil med alla aktuella inställningar. Importera sedan den här filen till Intune och använd den som Wi-Fi för dina HoloLens 2 enheter. Se [Exportera och importera Wi-Fi inställningar för Windows enheter.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Skapa en profil för varje företags-VPN (se [Windows 10 och Windows Holographic-enhetsinställningar](/intune/vpn-settings-windows-10)för att lägga till VPN-anslutningar med Intune ).

## <a name="troubleshooting-certificates"></a>Felsöka certifikat

Om du behöver verifiera att ett certifikat har distribuerats korrekt använder du [Certifikathanteraren](certificate-manager.md) på enheten för att verifiera att certifikatet finns.  

>[!WARNING]
> Du kan visa MDM-distribuerade certifikat i Certificate Manager, men du kan inte avinstallera dem i Certificate Manager. Du måste avinstallera dem via MDM.


