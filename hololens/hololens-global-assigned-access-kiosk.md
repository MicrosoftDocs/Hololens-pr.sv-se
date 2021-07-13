---
title: Global tilldelad åtkomst
description: Kom igång med vår guide för att använda OMA-URI för globalt tilldelade åtkomst-kiosker med Intune och Windows Configuration Designer.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, tilldelad åtkomst, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640431"
---
# <a name="global-assigned-access--kiosk"></a>Global tilldelad åtkomst – helskärmsläge

Den här funktionen konfigurerar HoloLens 2-enhet för helskärmsläge för flera appar, som gäller på systemnivå, inte har någon tillhörighet till någon identitet i systemet och gäller för alla som loggar in på enheten.

> [!NOTE]
> Den här funktionen är för närvarande endast tillgänglig i Windows Insider-byggen. Om du vill prova den här funktionen innan den blir allmänt tillgänglig i HoloLens versioner kan du läsa mer [om Windows Insider-versioner.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Hur använder jag global tilldelad åtkomst i Intune?

> [!NOTE]
> Tänk på de områden som är markerade med "<!-". Dessa områden kräver att du gör ändringar baserat på dina preferenser.

1. Skapa en anpassad oma-URI-enhetskonfigurationsprofil på följande sätt och tillämpa den på HoloLens en enhetsgrupp:

    URI-värde: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Global tilldelad åtkomst OMA-URI i Intune](images/global-assigned-access-omauri.png)

2. Uppdatera och klistra in följande innehåll för värde:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Hur använder jag global tilldelad åtkomst i Windows Configuration Designer?

1. Uppdatera och spara XML-blob som nämns ovan som XML-fil. 

2. Följ stegen i Använda [ett etableringspaket för att](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)konfigurera en helskärmsläge för en app eller flera appar, särskilt avsnittet "Prov. package, step 2 – Add the kiosk configuration XML file to a provisioning package" (paket, steg 2 – Lägg till XML-filen för helskärmskonfiguration i ett konfigurationspaket) och referera till XML-filen som sparades i föregående steg.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Kan jag skapa en konfiguration där global gäller för alla och separat konfiguration gäller för 1 Azure AD-konto eller Azure AD-grupp? 

Ja, se XML-exempelbloben nedan. Global tilldelad åtkomstprofil tillämpas på HoloLens när en specifik profil för den inloggade användaren inte hittas, så det är standardkonfigurationen för helskärmsläge för den inloggade användaren.
Här är ett exempel på en XML-blob som ska användas:

> [!NOTE]
> Tänk på de markerade områdena som är markerade med `<!-` . Dessa områden kräver att du gör ändringar baserat på dina preferenser.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Exkludera DeviceOwners från global tilldelad åtkomstprofil

Med den här funktionen kan en användare som[anses](security-adminless-os.md)vara "Enhetsägare" HoloLens undantas från global tilldelad åtkomst. Se till att markerade rader läggs till i XML-bloben för kioskkonfiguration med flera appar för att kunna dra nytta av den här funktionen:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Ytterligare exempel på global tilldelad åtkomst

Det här är ett exempel på helskärmsläge för global tilldelad åtkomst som när en användare loggar in har en helskärmsläge för flera appar med Inställningar-appen, Feedbackhubben och Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Det här exemplet är en helskärmsenhet för global tilldelad åtkomst som exkluderar enhetsägaren när andra Azure AD-användare loggar in med flera appar med Inställningar-appen, Feedbackhubben och Microsoft Edge. Den här kiosken innehåller också en sekundär kioskkonfiguration för ett besökarkonto, som kan loggas in av vem som helst på låsskärmen. När en användare loggar in på besökarkontot har de en helskärmsläge för flera appar som bara har Feedbackhubben appen.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
