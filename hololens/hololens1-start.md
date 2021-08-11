---
title: Konfigurera HoloLens (första generationen)
description: Lär dig att konfigurera ditt HoloLens (första gen) för första gången över Wi-Fi-nätverk med antingen ett Microsoft-konto (MSA) eller Azure Active Directory-konto (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9e09ba1a022428b098392464e5cd2abf84911bd6a86d8e699036b8fc4f91470a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661854"
---
# <a name="set-up-your-hololens-1st-gen"></a>Konfigurera din HoloLens (första generationen)

Första gången du aktiverar din HoloLens vägleds du genom att bygga om enheten, konfigurera enheten och logga in.  Den här artikeln går igenom HoloLens första start- och konfigurationsupplevelsen (första generationen).

I nästa avsnitt får du lära dig hur du arbetar med HoloLens och interagerar med hologram. Om du vill gå vidare till den här artikeln [kan du läsa Kom igång HoloLens (1:a gen)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Innan du börjar

Kontrollera att du har följande tillgängligt innan du börjar:

**En Wi-Fi anslutning**. Du måste ansluta din dator HoloLens ett Wi-Fi nätverk för att konfigurera den. Första gången du ansluter behöver du ett öppet eller lösenordsskyddat nätverk som inte kräver att du navigerar till en webbplats eller använder certifikat för att ansluta. [Läs mer om de webbplatser som HoloLens använder](hololens-offline.md).

**En Microsoft-konto eller ett arbetskonto**. Du måste också använda en Microsoft-konto (eller ett arbetskonto, om din organisation äger enheten) för att logga in på HoloLens. Om du inte har ett Microsoft-konto går du till [account.microsoft.com](https://account.microsoft.com) och ställer in ett kostnadsfritt.

**Ett säkert, välbelyst utrymme utan problem.** [Information om hälsa och säkerhet](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**De valfria** bekvämlighetsaccessoarerna som HoloLens för att hjälpa dig att få den mest bekväma passningen. [Mer om passning och bekvämlighet.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Första gången du använder din HoloLens [är Cortana](hololens-cortana.md) redan på och redo att vägleda dig (även om hon inte kan svara på dina frågor förrän efter att du har ställt din enhet). Du kan Cortana inaktivera när som helst Cortana inställningarna för .
> - Om du vill växla till den kinesiska eller japanska versionen av HoloLens måste du ladda ned versionen för språket på en dator och sedan installera den på din HoloLens. Mer information finns i [Installera lokaliserade versioner av HoloLens (första generationen).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Starta hololens och konfigurera Windows

Första gången du startar HoloLens är din första uppgift att konfigurera Windows Holographic på enheten.

1. Anslut till Internet (HoloLens dig att välja ett Wi-Fi nätverk).

1. Logga in på ditt användarkonto. Välj mellan **Mitt arbete eller min skola äger det** och jag äger **det**.
    - När du väljer **Mitt arbete eller min skola äger det** loggar du in med ett Azure AD-konto. Om din organisation använder Azure AD Premium och har konfigurerat automatisk MDM-HoloLens registreras automatiskt i MDM. Om din organisation inte använder Azure AD Premium är automatisk MDM-registrering inte tillgänglig, så du måste registrera HoloLens [i enhetshanteringen manuellt.](hololens-enroll-mdm.md#different-ways-to-enroll) Följ dessa steg om du vill logga in på enheten första gången med ett arbets- eller skolkonto:
        1. Ange din organisations kontoinformation.
        1. Godkänn sekretesspolicyn.
        1. Logga in med dina autentiseringsuppgifter för Azure AD. Detta kan omdirigeras till din organisations inloggningssida.
        1. Fortsätt att konfigurera enheten.
    - När du väljer **Jag äger den** loggar du in med en Microsoft-konto. När installationen är klar kan du [manuellt registrera HoloLens i enhetshanteringen.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Ange din Microsoft-konto information.
        1. Ange ditt lösenord. Om ditt Microsoft-konto [tvåstegsverifiering (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)slutför du verifieringsprocessen.

1. Enheten ställer in din tidszon baserat på information som den får från Wi-Fi nätverket.

## <a name="calibration"></a>Kalibrering

När Cortana introducerat sig själv är nästa konfigurationssteg kalibrering. För att få HoloLens bästa möjliga upplevelse bör du slutföra kalibreringsprocessen under installationen.

HoloLens (1:a gen) använder avståndet mellan dina pupiller (IPD eller [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) för att göra hologram tydliga och enkla att interagera med. Om IPD:t inte är korrekt kan hologram verka vara instabila eller på ett felaktigt avstånd.

Under kalibreringen HoloLens du att justera ditt finger med en serie med sex mål per ögon. HoloLens använder den här processen för att ange rätt IPD för dina ögon. Om kalibreringen behöver uppdateras eller justeras för en ny användare kan den nya användaren köra kalibreringsappen utanför konfigurationen.

![IPD-skärm för fingerjustering i det andra steget](./images/ipd-finger-alignment-300px.jpg)

*IPD-skärm för fingerjustering i det andra steget*

Grattis! Installationen är klar och du kan börja använda HoloLens.

## <a name="next-steps"></a>Nästa steg

> [!div class="nextstepaction"]
> [Kom igång med HoloLens (första generationen)](hololens1-basic-usage.md)
