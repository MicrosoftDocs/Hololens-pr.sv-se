---
title: HoloLens BitLocker-kryptering
description: Lär dig hur du aktiverar BitLocker-enhetskryptering för att skydda filer som lagras HoloLens enheter med mixad verklighet.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b07bb87b34ec966472bcbde000106590570fd7e7063ab503724884fa266bb34
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662691"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (första generationen) BitLocker-kryptering

HoloLens (första generationen) och HoloLens 2 stöder båda enhetskryptering med BitLocker, men BitLocker är alltid aktiverat på HoloLens 2.

Den här artikeln hjälper dig att aktivera och hantera BitLocker HoloLens (första generationen).

På HoloLens (första generationen) kan du aktivera BitLocker-enhetskryptering manuellt eller med hjälp av hantering av mobila enheter (MDM). Följ de här instruktionerna för att [aktivera BitLocker-enhetskryptering](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) för att skydda filer och information som lagras på HoloLens. Med enhetskryptering kan du skydda dina data med krypteringsmetoden AES-CBC 128, som motsvarar [EncryptionMethodByDriveType metod 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) i BitLocker-konfigurationstjänstprovidern (CSP). Personal som har rätt krypteringsnyckel (till exempel ett lösenord) kan dekryptera den eller utföra en dataåterställning.

## <a name="enable-device-encryption-using-mdm"></a>Aktivera enhetskryptering med MDM

Du kan använda MDM-providern (Mobile Enhetshantering) för att tillämpa en princip som kräver enhetskryptering. Principen som ska användas är [inställningen Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) i CSP-princip.

[Se anvisningar för att aktivera enhetskryptering med Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Andra MDM-verktyg finns i mdm-providerns dokumentation för instruktioner. Om MDM-providern kräver anpassad URI för enhetskryptering använder du följande konfiguration:

- **Namn:** ett namn som du väljer
- **Beskrivning**: valfritt
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Datatyp:** heltal
- **Värde**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Aktivera enhetskryptering med ett etableringspaket

Konfigurationspaket är filer som skapas av Windows Configuration Designer-verktyget som tillämpar en angiven konfiguration på en enhet. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Skapa ett etableringspaket som uppgraderar Windows Holographic Edition och aktiverar kryptering

1. [Skapa ett etableringspaket för HoloLens.](hololens-provisioning.md)
1. Gå till **Körningsinställningar**  >    >  **Principer Säkerhet** och välj **RequireDeviceEncryption**.

    ![Kräv inställningen enhetskryptering inställd på Ja](images/device-encryption.png)

1. Hitta XML-licensfilen som angavs när du köpte Commercial Suite.

1. Bläddra till och välj XML-licensfilen som angavs när du köpte Commercial Suite.
    > [!NOTE]
    > Du kan konfigurera [ytterligare inställningar i konfigurationspaketet](hololens-provisioning.md).

1. Klicka på **Spara** på **Arkiv**-menyn. 

1. Läs varningen som förklarar att projektfiler kan innehålla känslig information och klicka på **OK.**

    > [!IMPORTANT]
    > När du skapar ett etableringspaket kan du inkludera känslig information i projektfilerna och etableringspaketfilen (.ppkg). Även om du har möjlighet att kryptera .ppkg-filen krypteras inte projektfilerna. Du bör lagra projektfilerna på en säker plats och ta bort projektfilerna när de inte längre behövs.

1. På menyn **Exportera** klickar du på **Etableringspaket**.
1. Ändra **Ägare** till **IT-administratör**, vilket anger prioriteten för det här etableringspaketet högre än etableringspaket som tillämpas på den här enheten från andra källor och välj **sedan Nästa.**
1. Ange ett värde för **Paketversion**.

    > [!TIP]
    > Du kan göra ändringar i befintliga paket och ändra versionsnumret för att uppdatera tidigare tillämpade paket.

1. På sidan **Välj säkerhetsinformation för etableringspaketet klickar** du på **Nästa.**
1. Klicka **på** Nästa för att ange den utdataplats där du vill att etableringspaketet ska gå när det har skapats. Som standard Windows ICD projektmappen som utdataplats.

    Du kan också klicka på Bläddra för att ändra standardplatsen för utdata.

1. Klicka på **Nästa**.
1. Klicka **på Skapa** för att börja skapa paketet. Projektinformationen visas på byggsidan och förloppsfältet anger byggstatus.
1. När bygget är klart klickar du på **Slutför.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Tillämpa etableringspaketet på HoloLens

1. Anslut enheten via USB till en dator och starta enheten, men  fortsätt inte förbi sidan anpassa för den första installationen (den första sidan med den blå rutan).
1. Tryck en kort stund på och släpp **knapparna Volym ned** **och** Ström samtidigt.
1. HoloLens visas som en enhet i Utforskaren på datorn.
1. I Utforskaren du och släpper etableringspaketet (.ppkg) till enhetens lagring.
1. Tryck kort på och släpp **knapparna Volym ned** och **Ström** samtidigt på sidan **Anpassa.**
1. Enheten frågar dig om du litar på paketet och vill tillämpa det. Bekräfta att du litar på paketet.
1. Du kommer att se om paketet har tillämpats korrekt eller inte. Om det inte gick kan du åtgärda paketet och försöka igen. Om det lyckades fortsätter du med enhetskonfigurationen.

> [!NOTE]
> Om enheten köptes före augusti 2016 måste du logga in på enheten med en Microsoft-konto, hämta den senaste OS-uppdateringen och sedan återställa operativsystemet för att tillämpa etableringspaketet.

## <a name="verify-device-encryption"></a>Verifiera enhetskryptering

Krypteringen är tyst på HoloLens. Så här kontrollerar du enhetens krypteringsstatus:

- På HoloLens du till **Inställningar**  >  **System**  >  **Om**. **BitLocker** **aktiveras** om enheten är krypterad. 

    ![Om skärmen som visar Att BitLocker är aktiverat](images/about-encryption.png)
