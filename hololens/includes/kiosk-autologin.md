---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859412"
---
# <a name="non-aad-configuration"></a>[Icke-AAD-konfiguration](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Icke-AAD-konfiguration

1. Skapa ett etableringspaket som:
    1. Konfigurerar Körningsinställningar/AssignedAccess för att tillåta besökarkonton.
    1. Du kan också registrera enheten i MDM (Körningsinställningar/Arbetsplats/Registreringar) så att den kan hanteras senare.
    1. Skapa inte ett lokalt konto
2. [Tillämpa etableringspaketet](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[AAD-konfiguration](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD-konfiguration

AAD-anslutna enheter som konfigurerats för helskärmsläge kan logga in på ett besökarkonto med en enda knapptryckning från inloggningsskärmen. När användaren har loggat in på besökarkontot uppmanas enheten inte att logga in igen förrän besökaren uttryckligen har loggat ut från Start-menyn eller enheten startas om.

Automatisk inloggning för besökare kan hanteras via anpassad [OMA-URI-princip:](/mem/intune/configuration/custom-settings-windows-10)

- URI-värde: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Policy | Description | Konfigurationer |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Tillåter att en besökare automatiskt kan logga in på en kiosk. | 1 (Ja), 0 (Nej, standard.) |