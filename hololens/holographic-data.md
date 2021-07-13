---
title: Hitta och spara filer på HoloLens
description: Lär dig hur du använder Utforskaren på HoloLens för att öppna, visa och hantera filer på din enhet med mixad verklighet.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636188"
---
# <a name="find-open-and-save-files-on-hololens"></a>Hitta, öppna och spara filer på HoloLens

Filer som du skapar HoloLens, inklusive foton och videor, sparas direkt på din HoloLens enhet. Visa och hantera dem på samma sätt som du hanterar filer på Windows 10:

- Använda appen Utforskaren åtkomst till lokala mappar.
- I en applagring.
- I en särskild mapp (till exempel video- eller musikbiblioteket).
- Använda en lagringstjänst som innehåller en app och filväljare (till exempel OneDrive).
- Använd en stationär dator som är ansluten till HoloLens med hjälp av en USB-kabel med stöd för MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Visa filer på HoloLens med Utforskaren

> Gäller för alla HoloLens 2 enheter och HoloLens (första generationen) från och med [Windows 10 april 2018-uppdateringen (RS4) för HoloLens](/windows/mixed-reality/release-notes-april-2018).

Använd Utforskaren på HoloLens för att visa och hantera filer på enheten, inklusive 3D-objekt, dokument och bilder. Gå till **Starta**   >  **Alla appar**   >  **Utforskaren** att komma igång.

> [!TIP]
> Om det inte finns några filer i Utforskaren väljer du **Den här enheten** i det övre vänstra fönstret.

Om du inte ser några filer i Utforskaren kan filtret Senaste vara aktivt (klockikonen är markerad i det vänstra fönstret). Du kan åtgärda detta genom att **välja ikonen** Detta enhetsdokument i den vänstra rutan (under klockikonen) eller öppna menyn och välja Den **här enheten.**

## <a name="find-and-view-your-photos-and-videos"></a>Hitta och visa dina foton och videor

[Med Mixed Reality Capture](holographic-photos-and-videos.md) kan du ta foton och videor med mixad verklighet HoloLens.  Dessa foton och videor sparas i enhetens mapp kamerarulle.

Du kan komma åt foton och videor som tagits med HoloLens genom att:

- åtkomst till kamerarullen direkt via [Photos appen](holographic-photos-and-videos.md).
- ladda upp foton och videor till molnlagring genom att synkronisera dina foton och videor till OneDrive.
- med hjälp Inspelning av mixad verklighet sidan för [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Appen Foton

Appen Photos är en av standardapparna på **Start-menyn** och levereras inbyggt med HoloLens. Läs mer om [hur du använder Photos för att visa innehåll.](holographic-photos-and-videos.md)

Du kan också installera [OneDrive appen](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) från Microsoft Store synkronisera foton till andra enheter.

### <a name="onedrive-app"></a>OneDrive app

[OneDrive](https://onedrive.live.com/) kan du komma åt, hantera och dela dina foton och videor med valfri enhet och med alla användare. Om du vill komma åt foton och videor som HoloLens på [OneDrive du appen från](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store på HoloLens. När du har laddat ned OneDrive appen och **Inställningar**  >  **kamerauppladdning** och aktiverar **Kamerauppladdning.**

### <a name="connect-to-a-pc"></a>Anslut till en dator

Om din HoloLens kör uppdateringen från Windows 10 april [2018](/windows/mixed-reality/release-notes-april-2018) eller senare kan du ansluta din HoloLens till en Windows 10-dator med hjälp av en USB-kabel för att bläddra bland foton och videor på enheten med hjälp av MTP (media transfer protocol). Du måste se till att enheten är upplåst för att bläddra i filer om du har en PIN-kod eller ett lösenord som har ställts in på enheten.  

Om du har aktiverat [Windows Enhetsportalen](/windows/mixed-reality/using-the-windows-device-portal)kan du använda den för att bläddra, hämta och hantera foton och videor som lagras på enheten.

## <a name="access-files-within-an-app"></a>Komma åt filer i en app

Om ett program sparar filer på enheten kan du använda programmet för att komma åt dem.

### <a name="requesting-files-from-another-app"></a>Begära filer från en annan app

Ett program kan begära att spara en fil eller öppna en fil från en annan app med hjälp av [filväljare](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Kända mappar

HoloLens har stöd för ett antal [kända mappar som](/windows/mixed-reality/app-model#known-folders) appar kan begära åtkomstbehörighet till.

## <a name="view-hololens-files-on-your-pc"></a>Visa HoloLens filer på datorn

På samma sätt som med andra mobila enheter ansluter du HoloLens till din stationära dator med hjälp av MTP (Media Transfer Protocol) och öppnar Utforskaren på datorn för att få åtkomst till dina HoloLens bibliotek för enkel överföring.

Så här ser HoloLens-filer Utforskaren på datorn:

1. Logga in på HoloLens och anslut den sedan till datorn med hjälp av USB-kabeln som medförde HoloLens.

1. Välj **Öppna enhet för att visa filer Utforskaren** eller öppna Utforskaren på datorn och navigera till enheten.

Om du vill se information HoloLens högerklickar du på enhetsnamnet i Utforskaren på datorn och väljer **egenskaper.**

> [!NOTE]
> HoloLens (första generationen) stöder inte anslutning till externa hårddiskar eller SD-kort.

## <a name="sync-to-the-cloud"></a>Synkronisera till molnet

Om du vill synkronisera foton och andra filer HoloLens till molnet installerar och installerar du OneDrive på HoloLens. Du kommer OneDrive genom att söka efter den i Microsoft Store på din HoloLens.

HoloLens inte filer och data i appen, så det är en bra idé att spara viktiga saker i OneDrive. På så sätt säkerhetskopieras din information om du återställer enheten eller avinstallerar en app.
