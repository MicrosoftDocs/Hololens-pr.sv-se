---
title: Vanliga frågor och svar om HoloLens-enheter och hologram
description: Har du en snabb fråga om HoloLens eller hur du interagerar med hologram?  Den här artikeln innehåller ett snabbt svar och fler resurser.
keywords: hololens, faq, known issue, help
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 660c3b4d3a35a7794de5e3e2fb18f2a4aba03c0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378735"
---
# <a name="frequently-asked-questions-about-hololens-devices-and-holograms"></a>Vanliga frågor och svar om HoloLens-enheter och hologram

Den här artikeln besvarar några frågor som du kan ha om hur du använder HoloLens, inklusive hur du placerar hologram, arbetar med utrymmen med mera.

När du har problem kontrollerar du att HoloLens [debiteras.](https://support.microsoft.com/help/12627/hololens-charge-your-hololens) Prova [att starta om den](hololens-restart-recover.md) för att se om det åtgärdar något. Och använd feedbackappen för att skicka information om problemet till oss. Du hittar appen Feedback på [ **Start-menyn.**](holographic-home.md)

Tips om hur du använder HoloLens finns i Vanliga frågor och svar om [HoloLens (första generationens)](hololens1-fit-comfort-faq.md)form och bekvämlighet.

Den här artikeln tar upp följande frågor och problem: <a id="list"></a>

- [Mina hologram ser inte rätt ut eller flyttas runt](#my-holograms-dont-look-right-or-are-moving-around)
- [Jag ser ett meddelande som säger "Hitta ditt utrymme"](#i-see-a-message-that-says-finding-your-space)
- [Jag ser inte de hologram som jag förväntar mig att se i mitt utrymme](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [Jag kan inte placera hologram där jag vill](#i-cant-place-holograms-where-i-want-to)
- [Hologram försvinner eller är omslutna i andra hologram eller objekt](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Jag kan se hologram som finns på andra sidan av en vägg](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [När jag placerar ett hologram på en vägg verkar hologrammet flyta](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [Appar visas för nära mig när jag försöker flytta dem](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [Jag får ett felmeddelande om för lite diskutrymme](#im-getting-a-low-disk-space-error)
- [HoloLens svarar inte på mina gester](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens svarar inte på min röst](#hololens-doesnt-respond-to-my-voice)
- [Jag har problem med att koppla eller använda en Bluetooth-enhet](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [HoloLens-inställningar visar en lista över enheter som tillgängliga, men enheterna fungerar inte](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [Jag har problem med att använda HoloLens-klickaren](#im-having-problems-using-the-hololens-clicker)
- [Jag kan inte ansluta till Wi-Fi](#i-cant-connect-to-wi-fi)
- [Min HoloLens fungerar inte bra, svarar inte eller startar inte](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [Jag kan inte logga in på en HoloLens-enhet eftersom den tidigare har ställts in för någon annan](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [Frågor om att hantera HoloLens-enheter](#questions-about-managing-hololens-devices)
- [Frågor om att skydda HoloLens-enheter](#questions-about-securing-hololens-devices)
- [Hur gör jag för att du ta bort alla blanksteg?](#how-do-i-delete-all-spaces)
- [Jag kan inte hitta eller använda tangentbordet för att skriva HoloLens 2-emulatorn](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## <a name="my-holograms-dont-look-right-or-are-moving-around"></a>Mina hologram ser inte rätt ut eller flyttas runt

Om dina hologram inte ser rätt ut (till exempel om de är jitteriga eller skakiga, eller om du ser svarta korrigeringar ovanpå dem) kan du prova någon av följande korrigeringar:

- [Rensa enhetsvisorn och](hololens1-hardware.md#care-and-cleaning) kontrollera att inget blockerar sensorerna.
- Se till att du är i ett välbelyst rum som inte har så många direkta hotell.
- Prova att gå runt och titta på din miljö så att HoloLens kan genomsöka dem mer fullständigt.
- Om du har placerat många hologram kan du prova att ta bort några.

Om du fortfarande har problem kan du prova att köra appen Kalibrering. Den här appen kalibrerar HoloLens så att du kan hålla dina hologram så bra som möjligt. Det gör du genom att gå **till**  >  **Inställningar**  >  **SystemVerktyg.** Under **Kalibrering** väljer du **Öppna kalibrering.**

[Tillbaka till listan](#list)

## <a name="i-see-a-message-that-says-finding-your-space"></a>Jag ser ett meddelande som säger "Hitta ditt utrymme"

När HoloLens lär sig eller läser in ett utrymme kan du se ett kort meddelande som säger "Hitta ditt utrymme". Om det här meddelandet visas i mer än några sekunder visas ett annat meddelande under Start-menyn där det står "Letar fortfarande efter ditt utrymme".

Dessa meddelanden innebär att HoloLens har problem med att mappa ditt utrymme. När detta inträffar kan du öppna appar, men du kan inte placera hologram i din miljö.

Om du ser dessa meddelanden ofta kan du prova en eller flera av följande korrigeringar:

- Se till att du är i ett välbelyst rum som inte har så många direkta hotell.
- Kontrollera att enhetsvisorn är ren. [Lär dig hur du rensar din visor.](hololens1-hardware.md#care-and-cleaning)
- Kontrollera att du har en stark Wi-Fi signal. Om du anger en ny miljö som inte har Wi-Fi eller en svag Wi-Fi signal kan HoloLens inte hitta ditt utrymme. Kontrollera din Wi-Fi genom att gå till **Inställningar**  >  **&amp; Nätverkets**  >  **Internet-Wi-Fi.**
- Försök att flytta långsammare.

[Tillbaka till listan](#list)

## <a name="im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space"></a>Jag ser inte de hologram som jag förväntar mig att se i mitt utrymme

Om du inte ser de hologram som du har placerat, eller om du ser några som du inte förväntar dig, kan du prova en eller flera av följande korrigeringar:

- Sätt på några lampor. HoloLens fungerar bäst i välbelysta utrymmen.
- Ta bort hologram som du inte behöver genom att gå till **Inställningar**  >  **System**  >  **Hologram Ta** bort  >  **hologram i närheten.** Eller, om det behövs, väljer **du Ta bort alla hologram**.

  > [!NOTE]
  > Om layouten eller belysningen i utrymmet ändras avsevärt kan enheten ha problem med att identifiera ditt utrymme och visa dina hologram.

[Tillbaka till listan](#list)

## <a name="i-cant-place-holograms-where-i-want-to"></a>Jag kan inte placera hologram där jag vill

Här är några saker att prova om du har problem med att placera hologram:

- Ställ dig mellan en och tre meter från den plats där du försöker placera hologrammet.
- Placera inte hologram på svarta eller reflektiva ytor.
- Se till att du är i ett välbelyst rum som inte har så många direkta hotell.
- Gå igenom rum så att HoloLens kan genomsöka din miljö igen. Om du vill se vad som redan har genomsökts trycker du i luften för att visa kartnätsgrafiken.

[Tillbaka till listan](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologram försvinner eller är omslutna i andra hologram eller objekt

Om du är för nära ett hologram försvinner det tillfälligt för att återställa hologrammet. Det är bara &mdash; att flytta från det. Och om du har placerat flera hologram nära varandra kan vissa försvinna. Prova att ta bort några.

Hologram kan också blockeras eller vara omslutna av andra hologram eller av objekt som väggar. Om detta inträffar kan du prova någon av följande korrigeringar:

- Om hologrammet är omslutet i ett annat hologram flyttar du det omslutna hologrammet till en annan plats. Det gör du genom att **välja Justera** och sedan trycka och hålla kvar för att placera den.
- Om hologrammet är omslutet på en vägg väljer du Justera **och** går sedan mot väggen tills hologrammet visas. Tryck och håll ned och dra hologrammet framåt och från väggen.
- Om du inte kan flytta hologrammet med hjälp av gester kan du använda rösten för att ta bort det. Titta på hologrammet och säg sedan "Ta bort". Öppna hologrammet igen och placera det på en ny plats.

[Tillbaka till listan](#list)

## <a name="i-can-see-holograms-that-are-on-the-other-side-of-a-wall"></a>Jag kan se hologram som finns på andra sidan av en vägg

Om du är mycket nära en vägg, eller om HoloLens inte har skannat väggen ännu, kan du se hologram som finns i nästa rum. Om du vill genomsöka vägg ska du stå mellan en och tre meter från väggen och titta på den.

Ett svart eller reflektivt objekt (till exempel en svartoffa eller ett kylskåp av metall) nära väggen kan orsaka problem när HoloLens försöker genomsöka väggen. Om det finns ett sådant objekt genomsöker du den andra sidan av väggen.

[Tillbaka till listan](#list)

## <a name="when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float"></a>När jag placerar ett hologram på en vägg verkar hologrammet flyta

Ett hologram som du placerar på en vägg verkar vanligtvis vara en tum eller så från väggen. Om det verkar vara längre bort kan du prova en eller flera av följande korrigeringar:

- När du placerar ett hologram på en vägg ska du stå mellan en och tre meter från väggen och ansiktet mot väggen direkt på.
- Tryck i luften på vägg för att visa kartnätsgrafiken. Se till att näten är justerade mot väggen. Om den inte gör det tar du bort hologrammet, genomsökar vägg igen och försöker sedan igen.
- Om problemet kvarstår kör du kalibreringsappen. Du hittar den i **Inställningar**  >    >  **SystemVerktyg**.

[Tillbaka till listan](#list)

## <a name="apps-appear-too-close-to-me-when-im-trying-to-move-them"></a>Appar visas för nära mig när jag försöker flytta dem

Prova att gå runt och titta på det område där du placerar appen så att HoloLens genomsöker området från olika vinklar. [Att rensa enhetsvisor-programmet](hololens1-hardware.md#care-and-cleaning) kan också vara till hjälp.

[Tillbaka till listan](#list)

## <a name="im-getting-a-low-disk-space-error"></a>Jag får ett felmeddelande om för lite diskutrymme

Frigör lite lagringsutrymme genom att göra något av följande:

- Ta bort några av de hologram som du har placerat eller ta bort vissa sparade data från appar. [Hur gör jag för att hitta mina data?](holographic-data.md)
- Ta bort några bilder och videor i appen Foton.
- Avinstallera några appar från HoloLens. I listan **Alla appar** trycker du på och håller ned den app som du vill avinstallera och väljer sedan **Avinstallera.** (När du avinstallerar appen tas även alla data som appen lagrar på enheten bort.)

[Tillbaka till listan](#list)

## <a name="hololens-doesnt-respond-to-my-gestures"></a>HoloLens svarar inte på mina gester

Se till att HoloLens kan se dina gester genom att hålla din hand i gestramen. Gesterramen sträcker sig ett par meter på endera sidan av dig. HoloLens kan också bäst se din hand när du håller den cirka 18 tum framför din brödtext (även om du inte behöver vara exakt med detta). När HoloLens kan se din hand ändras markören från en punkt till en ring. Läs mer om [att använda gester i HoloLens 2](hololens2-basic-usage.md) eller använda [gester i HoloLens (första gen).](hololens1-basic-usage.md)

[Tillbaka till listan](#list)

## <a name="hololens-doesnt-respond-to-my-voice"></a>HoloLens svarar inte på min röst

HoloLens (1:a gen) och HoloLens 2 har inbyggd taligenkänning och stöder även Cortana (taligenkänning online).

### <a name="built-in-voice-commands-do-not-work"></a>Inbyggda röstkommandon fungerar inte

På HoloLens (1:a gen) går det inte att konfigurera inbyggd taligenkänning. Den är alltid aktiverad. På HoloLens 2 kan du välja om du vill aktivera både taligenkänning och Cortana under enhetskonfigurationen.

Om HoloLens 2 inte svarar på din röst kontrollerar du att Taligenkänning är aktiverat. Gå till  >  **Startinställningar**  >    >  **Sekretesstal** och aktivera **Taligenkänning.**

### <a name="cortana-or-dictation-doesnt-work"></a>Cortana eller diktering fungerar inte

Om Cortana eller diktering inte svarar på din röst kontrollerar du att taligenkänning online är aktiverat. Gå till  >  **Startinställningar**  >    >  **Sekretesstal och** verifiera inställningarna **för Taligenkänning online.** 

Om Cortana fortfarande inte svarar gör du något av följande för att kontrollera att själva Cortana är aktiverat:

- I **Alla appar** väljer du **Cortana och** > **notebook-menyinställningar**  >    >  **för** att göra ändringar.
- På HoloLens 2 väljer du **knappen Talinställningar** eller säger "Talinställningar".

Mer information om vad du kan säga finns i [Använda din röst med HoloLens](hololens-cortana.md).

[Tillbaka till listan](#list)

## <a name="im-having-problems-pairing-or-using-a-bluetooth-device"></a>Jag har problem med att koppla eller använda en Bluetooth-enhet

Om du har problem med att [koppla en Bluetooth-enhet](hololens-connect-devices.md)kan du prova följande:

- Gå till  >  **Inställningar Enheter** och kontrollera att Bluetooth är aktiverat. Om det är det inaktiverar du det och aktiverar det igen.
- Kontrollera att Bluetooth-enheten är helt laddad eller har nya batterier.
- Om du fortfarande inte kan ansluta startar [du om HoloLens](hololens-recovery.md).

[Tillbaka till listan](#list)

## <a name="hololens-settings-lists-devices-as-available-but-the-devices-dont-work"></a>HoloLens-inställningar visar en lista över enheter som tillgängliga, men enheterna fungerar inte

HoloLens (1:a gen) stöder inte Bluetooth-ljudprofiler. Bluetooth-ljudenheter, till exempel högtalare och headset, kan visas som tillgängliga i HoloLens-inställningar, men de stöds inte.

HoloLens 2 stöder Bluetooth A2DP-ljudprofilen för stereouppspelning. Profilen Bluetooth Hands Free som aktiverar mikrofoninfångning från Bluetooth-kringutrustning stöds inte på HoloLens 2.

Om du har problem med att använda en Bluetooth-enhet kontrollerar du att den är en enhet som stöds. Enheter som stöds är följande:

- QWERTY Bluetooth-tangentbord på engelska (du kan använda dem var som helst där du använder det holografiska tangentbordet).
- Bluetooth-mice.
- [HoloLens-klickern](hololens1-clicker.md).

Du kan koppla ihop andra Bluetooth HID- och GATT-enheter med dina HoloLens. Du kan dock behöva installera motsvarande tillhörande appar från Microsoft Store att använda enheterna.

[Tillbaka till listan](#list)

## <a name="im-having-problems-using-the-hololens-clicker"></a>Jag har problem med att använda HoloLens-klickaren

Använd [klickaren för att](hololens1-clicker.md) välja, bläddra, flytta och ändra storlek på hologram. Enskilda appar kan ha stöd för ytterligare klickgester.

Om du har problem med att använda klickern kontrollerar du att den debiteras och kopplas till din HoloLens. Om batteriet är lågt blinkar indikatorn gult. Kontrollera att klickaren är parkopplad genom att gå till **Inställningar**  >  **Enheter** och se om den visas där. Mer information finns i [Parkoppla klickaren](hololens1-clicker.md).

Om klickaren debiteras och parkopplas och du fortfarande har problem kan du återställa den genom att hålla ned huvudknappen och parkopplingsknappen i 15 sekunder. Koppla sedan klickaren till hololens igen.

Om det inte hjälper att återställa klickaren kan du se [Starta om eller återställa HoloLens-klickaren](hololens1-clicker.md#restart-or-recover-the-clicker).

[Tillbaka till listan](#list)

## <a name="i-cant-connect-to-wi-fi"></a>Jag kan inte ansluta till Wi-Fi

Här är några saker att prova om du inte kan ansluta din HoloLens till ett Wi-Fi nätverk:

- Kontrollera att Wi-Fi är aktiverat. Om du vill kontrollera det använder du gesten Start och väljer **sedan**  >  **Inställningar &amp; Nätverkets**  >  **Internet-Wi-Fi.** Om Wi-Fi är på kan du prova att stänga av det och sedan på igen.
- Flytta datorn närmare routern eller åtkomstpunkten.
- Starta om Wi-Fi router och starta [sedan om HoloLens](hololens-recovery.md). Försök att ansluta igen.
- Om inget av dessa fungerar kontrollerar du att routern använder den senaste inbyggda programvaran. Du hittar den här informationen på tillverkarens webbplats.

[Tillbaka till listan](#list)

## <a name="my-hololens-isnt-running-well-is-unresponsive-or-wont-start"></a>Min HoloLens fungerar inte bra, svarar inte eller startar inte

Om enheten inte fungerar korrekt kan du se Starta [om, återställa eller återställa HoloLens](hololens-recovery.md).

[Tillbaka till listan](#list)

## <a name="i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else"></a>Jag kan inte logga in på en HoloLens-enhet eftersom den tidigare har ställts in för någon annan

Om enheten tidigare har ställts in för någon annan, antingen för en klient eller för en tidigare anställd och du inte har lösenordet för att låsa upp enheten, kan du göra något av följande:

- För en enhet som har registrerats i Intunes hantering av mobila enheter (MDM) kan du använda Intune för [att fjärrensa](https://docs.microsoft.com/intune/remote-actions/devices-wipe) enheten. Enheten blinkar sedan igen.  
   > [!IMPORTANT]  
   > När du rensar enheten ska du lämna **Behåll registreringstillstånd och användarkonto** avmarkerat.
- För en icke-MDM-enhet kan du placera enheten i [ **flashingläge**](hololens-recovery.md#clean-reflash-the-device) och använda Advanced Recovery Companion för att återställa enheten.

[Tillbaka till listan](#list)

## <a name="questions-about-managing-hololens-devices"></a>Frågor om att hantera HoloLens-enheter

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kan jag använda System Center Konfigurationshanteraren (SCCM) för att hantera HoloLens-enheter?

Nej. Du måste använda ett MDM-system för att hantera HoloLens-enheter.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kan jag använda Active Directory Domain Services (AD DS) för att hantera HoloLens-användarkonton?

Nej. Du måste använda Azure Active Directory (Azure AD) för att hantera användarkonton för HoloLens-enheter.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Kan HoloLens automatisk registrering av DATA Capture Systems (ADCS)?

Nej.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kan HoloLens delta i Integrerad Windows-autentisering?

Nej.

### <a name="does-hololens-support-branding"></a>Stöder HoloLens profilering?

Nej. Du kan dock komma runt det här problemet med någon av följande metoder:

- Skapa en anpassad app och aktivera [sedan Helskärmsläge](hololens-kiosk.md). Den anpassade appen kan ha varumärkesanpassad anpassning och kan starta andra appar (till exempel Remote Assist).  
- Ändra alla användarprofilbilder i Azure AD till företagets logotyp. Detta kanske dock inte är önskvärt för alla scenarier.

### <a name="what-logging-capabilities-do-hololens-1st-gen-and-hololens-2-offer"></a>Vilka loggningsfunktioner erbjuder HoloLens (första generationen) och HoloLens 2?

Loggning är begränsad till spårningar som kan avbildas i utvecklings- eller felsökningsscenarier, eller telemetri som enheterna skickar till Microsoft-servrar.

[Tillbaka till listan](#list)

## <a name="questions-about-securing-hololens-devices"></a>Frågor om att skydda HoloLens-enheter

Se [vår HoloLens 2-säkerhetsinformation.](security-overview.md)
För HoloLens 1st Gen-enheter kan du läsa dessa [vanliga frågor och svar.](hololens1-faq-security.md)

[Tillbaka till listan](#list)

## <a name="how-do-i-delete-all-spaces"></a>Hur gör jag för att ta bort alla blanksteg?

*Kommer snart*

[Tillbaka till listan](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Jag kan inte hitta eller använda tangentbordet för att skriva i HoloLens 2-emulatorn

*Kommer snart*

[Tillbaka till listan](#list)
