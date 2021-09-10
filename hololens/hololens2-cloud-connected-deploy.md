---
title: Distributionsguide – Molnansluten HoloLens 2-distribution i stor skala med Remote Assist – Distribuera
description: Lär dig hur du validerar registrering och fjärrhjälp för HoloLens enheter över ett molnanslutet nätverk.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Enhetshantering
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428053"
---
# <a name="deploy---cloud-connected-guide"></a>Distribuera – Molnansluten guide

Nu när allt har konfigurerats bör du vara redo att distribuera enheter. Nu bör du dock först verifiera konfigurationen. Först ska processen för Azure AD-anslutning och MDM-registrering verifieras, följt av verifiering av att ett Remote Assist-anrop kan placeras.

## <a name="enrollment-validation"></a>Registreringsvalidering

Nu när allt är korrekt konfigurerat för Azure AD- och MDM-registrering bör resten nu vara ett ögonblick. Du&#39;en Wi-Fi-anslutning och HoloLens-enheten, samt ett av de tidigare konfigurerade AAD-användarkontona.

Om enheten inte&#39;närvarande är i fabriksinställningarnas tillstånd är det nu ett bra tillfälle att [omstrecka enheten](/hololens/hololens-recovery#clean-reflash-the-device).

1. När enheten är i OOBE&#39;du börja interagera och följa anvisningarna. 
1. Den kritiska frågan blir när du tillfrågas **om Vem äger den här HoloLens?** Välj **Mitt arbete eller min skola äger den och ange** autentiseringsuppgifterna för ditt Azure AD-konto.
1. När registreringen lyckas uppmanas&#39;att konfigurera en PIN-kod. Den här PIN-koden är unik för den här enheten för den här användaren. Du uppmanas också att ange Iris-genomsökningar, röstdata och telemetriinställningar. Slutligen kan du&#39;lära dig att öppna Start-menyn och slutföra OOBE.
1. När du landar i Mixed Reality Start öppnar du Start-menyn med hjälp av **gesten Start som du** precis har lärt dig.
1. Välj **Inställningar** app och **välj System.** Den första information som&#39;ser är enhetsnamnet, som för din HoloLens 2-enhet blir HOLOLENS följt av en &quot; &quot; sex teckensträng.
1. Anteckna det här namnet.

![HoloLens 2 Inställningar – Om.](./images/hololens2-settings-about.jpg)

7. Du kan kontrollera att enheten har registrerats i Azure AD i den Inställningar appen. I **Inställningar du** Konton **Åtkomst** till arbete eller  ->  **skola.** På den här skärmen kan du kontrollera att du har registrerats genom att se Ansluten till &quot; _namnofAAD_&#39;s Azure AD. Ansluten med _yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; .


För att verifiera att enheten har anslutits till Azure AD kan vi kontrollera Azure Active Directory från [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Enheter Alla enheter och  ->    ->    ->  söka efter enhetsnamnet. Du&#39;kan se att enheten är en del av Azure Active Directory.


![Azure Active Directory – Enhet.](./images/aad-enrollment.png)

Därefter måste&#39;logga in på Microsoft Endpoint Manager [administrationscenter.](https://endpoint.microsoft.com/#home) Logga in och välj **Enheter** och **sedan Alla enheter.** Härifrån kan du söka i HoloLens enhetsnamn&#39;enhetsnamn. Du bör kunna se dina HoloLens i Intune.

![Intune – Enhet.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validering av Fjärrhjälp-anrop

När du&#39;verifierat att enheten har registrerats i både din AAD och MDM&#39;det dags att testa Remote Assist-anropet. För den här&#39;måste du ha HoloLens-enheten och en Windows 10-dator samt ett andra Azure AD-användarkonto för datorn.

Det här valideringssteget förutsätter att du tidigare har slutfört det senaste verifieringssteget och att enheten har registrerats och att Azure AD-användaren finns på enheten.


1. Om du inte redan har Microsoft Teams installerat på datorn kan du ladda ned [Teams här](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Logga in Teams det andra Azure AD-användarkontot än det som för närvarande är inloggad på HoloLens. När du har loggat in på datorn är du redo att ta emot anropet.
3. Lås upp HoloLens och logga in.
4. Starta remote assist-appen genom att öppna **Start-menyn** och välja **Fjärrhjälp.** Remote Assist paketeras inte bara som en inkorgsapp utan fästs HoloLens 2&#39;startmenyn. Om du inte&#39;den fästs på Start-menyn öppnar du listan Alla appar **för** att leta efter den.
5. När Remote Assist startar bör den identifiera enhetens användare via [enkel inloggning](/azure/active-directory/manage-apps/what-is-single-sign-on) och logga in i appen.
6. I appen väljer du Sök **och** söker efter den andra användaren på datorn. Välj användaren för att starta anropet.
7. Besvara anropet från datorn.

Grattis, du&#39;har anslutit och är på fjärrhjälpsamtalet. Se till att prova specifika funktioner för fjärrhjälp, till exempel att använda:

- [Anteckningar för pennanteckningar](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Dela en fil och vy i mixad verklighet](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Få hjälp i en annan HoloLens app](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Nästa steg

> [!div class="nextstepaction"]
> [Molnansluten distribution – Underhåll](hololens2-cloud-connected-maintain.md)