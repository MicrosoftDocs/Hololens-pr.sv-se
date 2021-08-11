---
title: Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – översikt
description: Lär dig hur du registrerar HoloLens 2 enheter med Dynamics 365-guider över ett företagsanslutet nätverk.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Enhetshantering
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 67e34ea275ef73adda840ee4f44d9c0c3c9440ef0bd2aef48cb7aaa971219220
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660096"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Distributionsguide – Företagsanslutna HoloLens 2 med Dynamics 365-guider – översikt

Den här guiden hjälper IT-proffs att planera för och distribuera Microsoft HoloLens 2 enheter med Dynamics 365-guider (guider) till organisationen. Den här guiden är utmärkt för både piloter och produktionsdistributioner och liknar [scenario B: Distribuera i organisationens nätverksguide.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) När du har testat konceptbeviset kan du använda den här guiden för att gå vidare med att integrera HoloLens i din organisation.

I den här guiden går vi in på hur du registrerar dina enheter i din befintliga enhetshantering, tillämpar licenser efter behov och kontrollerar att slutanvändarna kan använda en Dynamics 365-guide, samt hur du använder anpassade branschappar när enheten har ställts in. 

## <a name="prerequisites"></a>Förutsättningar

Följande infrastruktur bör redan finnas på plats:
- Wi-Fi
    - Internt företagsnätverk med åtkomst till interna resurser och begränsad åtkomst till Internet- eller molntjänster
    - Enhetsbaserad certifikatautentisering.
- Azure Active Directory (Azure AD) Join with MDM Auto Enrollment (Azure AD P1 subscription needed) (Azure AD P1-anslutning med mdm-automatisk registrering ([Azure AD P1-prenumeration krävs)](/azure/active-directory/fundamentals/active-directory-whatis)
- MDM (Intune) Hanterad
    - Ett eller flera program distribueras via MDM.
- Nätverk 
    - Certifikat (SCEP eller PKCS)
    - Proxykonfiguration
- Användare loggar in med sitt eget företagskonto (Azure AD)
    - En eller flera användare per enhet stöds.
- Olika nivåer av enhetslåsningskonfigurationer som tillämpas baserat på specifika användningsfall, från Fullständigt öppen till Helskärmsläge för enskild app.

## <a name="guides-licensing-and-requirements"></a>[Guider licensiering och krav](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD-konto
- Dynamics 365-guider för program PC och HoloLens
- Prenumeration på Dynamics 365-guider
    - Microsoft Dataverse (ingår)
    - Power Apps (ingår)
- Power BI Desktop
- Nätverksanslutning

[![Diagram över företagsanslutna nätverk, steg 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram över företagsanslutna nätverk, steg 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>I den här guiden kommer du att:
### <a name="prepare"></a>Förbereda
> [!div class="checklist"]
>- [Lär dig mer om grundläggande infrastruktur för HoloLens 2 enheter.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Läs mer om Azure AD och konfigurera ett om du inte har det.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Lär dig mer om identitetshantering och hur du bäst ställer in Azure AD-konton.](hololens2-corp-connected-prepare.md#identity-management)
>- [Läs mer om MDM och konfigurera med Intune om du inte redan har en klar.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Bekanta dig med certifikatbaserad Wi-Fi.](hololens2-corp-connected-prepare.md#certificates)
>- [Bekanta dig med Proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Förstå hur du kan använda branschappar.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Läs mer om hur du kan använda guider för din organisation.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurera
> [!div class="checklist"]
>- [Så här skapar du användare och grupper.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Konfigurera automatisk registrering.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Så här ställer du Wi-Fi certifikat och profiler för Wi-Fi anslutning.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload och tilldela affärs appaket (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Konfigurera Dynamics 365-guider.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Så här konfigurerar du helskärmsläge (valfritt).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Så här konfigurerar du WDAC (valfritt).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Distribuera
> [!div class="checklist"]
>-  [Verifiera registrering via enhet och MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Verifiera Wi-Fi certifikat.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Verifiera installationen av LOB-appen.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Verifiera guider via redigering och drift.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Underhåll
> [!div class="checklist"]
>- [Uppdatera HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Så här uppdaterar du guider (Store-appar).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Så här uppdaterar du LOB-appar.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Utvecklingsplan.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Skapa en supportplan.](hololens2-corp-connected-maintain.md#support-plan)
>- [Alternativ för enhetshantering.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Nästa steg 
> [!div class="nextstepaction"]
> [Företagsansluten distribution – Förbereda](hololens2-corp-connected-prepare.md)
