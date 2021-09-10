---
title: Hantera anpassade appar för HoloLens (första gen)
description: Lär dig hur du installerar, avinstallerar och läser in anpassade holografiska appar på HoloLens-enheter med hjälp av Enhetsportalen och Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428524"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Hantera anpassade appar för HoloLens (första gen)

HoloLens stöder många befintliga program från Microsoft Store, samt nya appar som skapats specifikt för HoloLens. Den här artikeln fokuserar på anpassade holografiska program.  

Mer information om Store-appar finns [i Hantera appar med Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Följande information skapades för HoloLens (1:a gen), även kallat HoloLens Developer Edition vid den tidpunkten. Därför var separat inläsning av appar via enhetsportalen och installation av appar via Visual Studio vanligt då. För företagsdistributioner rekommenderar vi inte att du aktiverar Utvecklarläge, som båda dessa metoder använder. Om du är intresserad av en säker appdistributionsmetod kan du läsa vår [apphantering: Översikt](app-deploy-overview.md).
>
> Om du letar efter någon av utvecklarmetoden för appinstallation för HoloLens 2 enheter kan du gå till:
>
> - [Enhetsportalen: Installera en app](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Använda Visual Studio för att distribuera och felsöka appar](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installera anpassade appar

Du kan installera dina egna program på HoloLens antingen med hjälp av Enhetsportalen eller genom att distribuera apparna från Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installera ett programpaket med Enhetsportalen

1. Upprätta en anslutning från [Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal) till HoloLens.

1. I det vänstra navigeringsfönstret går du till **sidan** Appar.

1. Under **Appaket** bläddrar du till den .appx-fil som är associerad med ditt program.

   > [!IMPORTANT]
   > Se till att referera till eventuella associerade beroende- och certifikatfiler.

1. Välj **Go**.

   > [!div class="mx-imgBorder"]
   > ![Installera appformulär i Windows Enhetsportalen på Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Distribuera från Microsoft Visual Studio 2015

1. Öppna appens lösning Visual Studio (SLN-fil).

1. Öppna projektets **Egenskaper**.

1. Välj följande build-konfiguration: **Master/x86/Remote Machine**.

1. När du väljer **Fjärrdator:**
   - Kontrollera att adressen pekar på ipWi-Fi adressen för din HoloLens.
   - Ange autentisering till **Universal (Unencrypted Protocol).**
   
1. Skapa din lösning.

1. Om du vill distribuera appen från utvecklingsdatorn till HoloLens väljer du **Fjärrdator.** Om du redan har en befintlig version på HoloLens väljer du **Ja för** att installera den här nyare versionen.  

   ![Fjärrdatordistribution för appar som ska Microsoft HoloLens i Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. Programmet installeras och startas automatiskt på din HoloLens.

När du har installerat en app finns den i listan Alla appar **(** **Starta**  >  **Alla appar**).
