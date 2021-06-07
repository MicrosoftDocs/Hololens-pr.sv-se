---
title: Lås Windows Holographic for Business funktioner
description: När du uppgraderar till Windows Holographic for Business tillhandahåller HoloLens extra funktioner som är utformade för företag.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378815"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Lås Windows Holographic for Business funktioner

> [!IMPORTANT]
> Den här sidan gäller endast HoloLens 1:a Gen.

Microsoft HoloLens finns i Development *Edition*, som kör Windows Holographic (en utgåva av Windows 10 som är utformad för HoloLens) och i [Commercial Suite](hololens-commercial-features.md), som innehåller extra funktioner som är utformade för företag.

När du köper Commercial Suite får du en licens som uppgraderar Windows Holographic till Windows Holographic for Business. Du kan tillämpa den här licensen på enheten antingen med hjälp av organisationens [MDM-provider (hantering](#edition-upgrade-by-using-mdm) av mobila enheter) eller med [ett etableringspaket](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> I Windows 10 version 1803 kan du kontrollera att HoloLens har uppgraderats till Business Edition genom att välja **Inställningar**  >  **system**.

## <a name="edition-upgrade-by-using-mdm"></a>Uppgradering av utgåva med hjälp av MDM

Företagslicensen kan tillämpas av valfri MDM-provider som har stöd för [WindowsLicensing Configuration Service Provider (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) Den senaste versionen av Microsoft MDM API stöder WindowsLicensing CSP.

Stegvisa instruktioner för att uppgradera HoloLens med hjälp av Microsoft Intune finns i Uppgradera enheter som kör [Windows Holographic till Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).

 För andra MDM-leverantörer kan de specifika stegen för att konfigurera och distribuera principen variera.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Uppgradering av utgåva med hjälp av ett etableringspaket

Konfigurationspaket är filer som skapas av verktyget Windows Configuration Designer och som tillämpar en angiven konfiguration på en enhet.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Skapa ett etableringspaket som uppgraderar Windows Holographic-versionen

1. [Skapa ett etableringspaket för HoloLens.](hololens-provisioning.md)
1. Gå till KörningsinställningarUtgåvaUppgradera   >  och **välj EditionUpgradeWithLicense**.

    ![Uppgradera utgåva med licensinställning vald](images/icd1.png)

1. Hitta XML-licensfilen som angavs när du köpte Commercial Suite.

    > [!NOTE]
    > Du kan konfigurera [ytterligare inställningar i konfigurationspaketet](hololens-provisioning.md).

1. Öppna menyn **File** (Arkiv) och välj **Save** (Spara). 

1. Läs varningen om att projektfiler kan innehålla känslig information och klicka på **OK.**

    > [!IMPORTANT]
    > När du skapar ett etableringspaket kan du inkludera känslig information i projektfilerna och etableringspaketfilen (.ppkg). Även om du har möjlighet att kryptera .ppkg-filen krypteras inte projektfilerna. Du bör lagra projektfilerna på en säker plats och ta bort projektfilerna när de inte längre behövs.

1. På menyn **Exportera** väljer du **Etableringspaket**.

1. Ändra **Ägare** till **IT-administratör**, vilket anger att prioriteten för det här etableringspaketet ska vara högre än andra som tillämpas på den här enheten från olika källor och välj **sedan Nästa.**

1. Ange ett värde för **Paketversion**.

    > [!TIP]
    > Du kan göra ändringar i befintliga paket och ändra versionsnumret för att uppdatera tidigare tillämpade paket.

1. På **Välj säkerhetsinformation för etableringspaketet** väljer du **Nästa.**

1. Välj **Nästa** för att ange den utdataplats där du vill att etableringspaketet ska gå när det har skapats. Som standard använder Windows ICD projektmappen som utdataplats.

    Du kan också välja Bläddra **för att** ändra standardplatsen för utdata.

1. Välj **Nästa**.

1. Välj **Skapa** för att börja skapa paketet. Byggsidan visar projektinformationen och förloppsfältet visar byggstatus.

1. När bygget är klart väljer du **Slutför**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Tillämpa etableringspaketet på HoloLens

1. Anslut enheten till en dator med hjälp av USB-kabeln. Starta enheten, men fortsätt inte förbi sidan anpassa **för** den första installationen (den första sidan med den blå rutan). På datorn visas HoloLens som en enhet i Utforskaren.

    > [!NOTE]
    > Om HoloLens-enheten körs Windows 10 version 1607 eller tidigare öppnar du Utforskaren genom att kort trycka  på och släppa knapparna **Volym** ned och Ström samtidigt på enheten.

1. I Utforskaren du och släpper etableringspaketet (.ppkg) till enhetens lagring.

1. Även om HoloLens fortfarande är på **anpassa-sidan,** trycker du kort och släpper **knapparna Volym ned** **och** Ström samtidigt igen.

1. HoloLens frågar dig om du litar på paketet och vill tillämpa det. Bekräfta att du litar på paketet.

1. Du kommer att se om paketet har tillämpats korrekt eller inte. Om det inte har tillämpats kan du åtgärda paketet och försöka igen. Om det lyckas fortsätter du med enhetskonfigurationen.
