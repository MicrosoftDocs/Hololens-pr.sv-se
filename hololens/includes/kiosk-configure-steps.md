---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859432"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune kioskmall för enstaka app](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune kioskmall för enstaka app

1. Skapa en konfigurationsprofil <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Välj kioskmall <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Välj om en enskild app eller flera appar ska vara helskärmsläge och välj även typ av användarmål för helskärmsläge <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Välj den app som ska köras i helskärmsläge <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Lämna resten av alternativen som de är <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Välj vilka grupper/enheter eller användare som den här konfigurationsprofilen ska tilldelas till <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Granska och skapa för att spara konfigurationsprofilen
8. Utför MDM-synkronisering från antingen enheten eller Intune för att tillämpa konfigurationen på enheten. [Synkronisera enheter från Intune](/mem/intune/remote-actions/device-sync#sync-a-device) eller på enheten via **Inställningar -> Accounts -> Work or school ->** select the connected account **-> Info -> Sync**
9. Logga in som målanvändare för helskärmsläge.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune kioskmall för flera appar](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune kioskmall för flera appar

1. Skapa en konfigurationsprofil <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Välj kioskmall <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Välj om en enskild app eller flera appar ska vara helskärmsläge och välj även typ av användarmål för helskärmsläge <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Välj de appar som ska köras i helskärmsläge <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Lämna resten av alternativen som de är <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Välj vilka grupper/enheter eller användare som den här konfigurationsprofilen ska tilldelas till <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Granska och skapa för att spara konfigurationsprofilen
8. Utför MDM-synkronisering från antingen enheten eller Intune för att tillämpa konfigurationen på enheten. [Synkronisera enheter från Intune](/mem/intune/remote-actions/device-sync#sync-a-device) eller på enheten via **Inställningar -> Accounts -> Work or school ->** select the connected account **-> Info -> Sync**
9. Logga in som målanvändare för helskärmsläge.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune anpassad mall](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune anpassad mall

1. Skapa xml-konfiguration för önskad helskärmsupplevelse. Se [exempel här](../hololens-kiosk-reference.md#kiosk-xml-code-samples) för att börja.

1. Skapa en anpassad konfigurationsprofil <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Ange namnet på den anpassade konfigurationsprofilen och klicka på "Lägg till" i avsnittet "Konfigurationsinställningar" för att lägga till OMA-URI-inställningar. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Ange namnet på OMA-URI-inställningarna.

    1. I textrutan OMA-URI anger du **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Välj Datatyp som **Sträng.**
    1. I textrutan värde kopierar du och klistrar in xml-filen för tilldelad åtkomstkonfiguration (se referenslänkar för exempel baserat på ditt scenario och uppdatera efter behov innan du kopierar inklistring).
    1. Välj knappen Spara för att spara inställningen och konfigurationen.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Välj vilka grupper/enheter eller användare som den här konfigurationsprofilen ska tilldelas till. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Granska och skapa för att spara konfigurationsprofilen.
1. Utför MDM-synkronisering från antingen enheten eller Intune för att tillämpa konfigurationen på enheten. [Synkronisera enheter från Intune](/mem/intune/remote-actions/device-sync#sync-a-device) eller på enheten via **Inställningar -> Accounts -> Work or school ->** select the connected account **-> Info -> Sync**
1. Logga in som målanvändare för helskärmsläge.

# <a name="runtime-provisioning---multi-app"></a>[Etablering av körning – flera appar](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Etablering av körning – flera appar

1. Skapa xml-konfiguration för önskad helskärmsupplevelse. Se [exempel här](../hololens-kiosk-reference.md#kiosk-xml-code-samples) för att börja.

1. Öppna [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. På sidan Start väljer du **Etablera HoloLens enheter.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Välj **Etablera HoloLens 2 enheter och** välj sedan Nästa. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Namnge projektet. Du kan också skriva en beskrivning. Fortsätt **genom att** välja Slutför.

6. Längst ned till vänster på skärmen väljer du Växla **till avancerad redigerare.** Bekräfta att du växlar till den avancerade redigeraren genom att välja **Ja.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. På vänster sida expanderar du Körningsinställningar, TilldeladÅtkomst och väljer **MultiAppAssignedAccess.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Välj knappen **Bläddra...** för att öppna Utforskaren. Och välj den konfigurerade XML-filen för helskärmsläge.

9. Välj **Exportera** och **sedan Etableringspaket**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Ändra ägartyp till **IT-administratör.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Välj **Nästa** tre gånger. Välj sedan **Build (Skapa).**

12. När ditt etableringspaket har byggts öppnar du mappen Utdataplats. .ppkg-filen är ditt etableringspaket. Valfritt steg: Spara projektet.

13. Nu kan du använda ditt etableringspaket. Du kan [antingen tillämpa ett konfigurationspaket på HoloLens under](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) installationen eller tillämpa ett [konfigurationspaket](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)på HoloLens efter installationen .

14. Logga in som målanvändare för helskärmsläge.

# <a name="runtime-provisioning---single-app"></a>[Etablering av körning – enskild app](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Etablering av körning – enskild app

1. Öppna [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. På sidan Start väljer du **Etablera HoloLens enheter.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Välj **Etablera HoloLens 2 enheter och** välj sedan Nästa. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Namnge projektet. Du kan också skriva en beskrivning. Fortsätt **genom att** välja Slutför.

5. Längst ned till vänster på skärmen väljer du Växla **till avancerad redigerare.** Bekräfta att du växlar till den avancerade redigeraren genom att välja **Ja.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. På vänster sida expanderar du Körningsinställningar, TilldeladÅtkomst och väljer **TilldeladÅtkomstInställningar.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Definiera helskärmsläge i textrutan. Följande skapar till exempel ett enda app-helskärmsläge för ett lokalt konto med namnet LocalAccount som är inställningsappen.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Välj **Exportera** och **sedan Etableringspaket**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Ändra ägartyp till **IT-administratör.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Välj **Nästa** tre gånger. Välj sedan **Build (Skapa).**

11. När ditt etableringspaket har byggts öppnar du mappen Utdataplats. .ppkg-filen är ditt etableringspaket. Valfritt steg: Spara projektet.

12. Nu kan du använda ditt etableringspaket. Du kan [antingen tillämpa ett konfigurationspaket på HoloLens under](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) installationen eller tillämpa ett [konfigurationspaket](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)på HoloLens efter installationen .