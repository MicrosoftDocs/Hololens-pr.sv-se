---
title: Tillståndsseparation och isolering
description: Lär dig mer om tillståndsseparation, isolering, kodsignering och defender-program på din HoloLens 2-enhet med mixad verklighet.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, State separation, State separation and isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 18c30b4edd649c088f71e479a401c8b286ddfd592f57a5659c3c15b3ec9c854f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665377"
---
# <a name="state-separation-and-isolation"></a>Tillståndsseparation och isolering

Tillståndsseparation och isolering skyddar kritiska delar av Hololens 2-operativsystemet från ändringar – till exempel de som krävs för att operativsystemet ska kunna starta i ett betrott tillstånd. Med isoleringsteknik flyttas ej betrodda appar till en isolerad sandbox-miljö för att säkerställa att de inte påverkar systemsäkerheten.

## <a name="state-separation"></a>Tillståndsseparation

Tillståndsseparation HoloLens 2 förbättrar säkerheten och servicebarheten (uppdatering) avsevärt och skyddar dina programdata.  Tillståndsavseparation fungerar på följande sätt:
  * Kärnoperativsystemet lagras på kärnoperativsystemets volym (betrott eller verifierat Microsoft OS som uppdaterar operativsystemet).
  * De delar av operativsystemet som kan ändras vid körning (till exempel nedladdningsbara drivrutiner och konfigurationer), använder ytterligare tillståndsavseparation för att partitionera data och lagra dem på säkra, separata lagringsplatser.
  * Varje säker lagringsplats har olika associerade säkerhetsprinciper, vilket ger olika säkerhetsfördelar enligt beskrivningen i följande avsnitt.

## <a name="state-separation-benefits"></a>Fördelar med uppdelning av delstat

  * Säkerhet: Tillståndsavskiljningen i HoloLens 2 förbättrar plattformens integritet, motståndskraft mot skadlig kod och skydd mot användardata avsevärt. Genom att separera den oföränderliga delen av operativsystemet och göra det skrivskyddat eller integritetsskyddat, gör tillståndsavgränsning det mycket svårt för skadlig kod att bevaras under en kall omstart. 
  * Uppdateringar: Med HoloLens 2 blir uppdateringar enkla och tillförlitliga när kärnoperativsystemet är oföränderligt och har separerats från resten av data på enheten.  Dessutom lägger tillståndsseparation grunden för avsevärt snabbare uppdateringar, vilket gör att operativsystemet kan ersättas i ett enda steg (atomisk enhet).
  * Enhetsåterställning: HoloLens 2 rensar användargenererade data och användarappdata på enheten – inklusive interna och externa lagringsplatser. Den bevarar de aktuella OS-apparna och säkerhetskritiska appar och de aktuella anpassade Microsoft- och OEM-apparna (förinstallerade). Dessa förinstallerade appar kan återhydreras på enheten när återställningen är klar

### <a name="state-separation-states"></a>Tillstånd för tillståndsavskiljning

Tillståndsseparation säkerställer att operativsystemet endast kan ändras av Microsofts betrodda enhetskomponenter och att endast högt värde-tillstånd tillåts bevaras vid omstarter. annat systemtillstånd finns bara under startsessionen och tas bort efter en omstart. Med tillståndsseparation återgår enheten snabbt till fabrikstillståndet. Windows Holographic for Business delstater kan delas in i följande distinkta kategorier:
  * Kärnoperativsystemet – oföränderligt tillstånd
  * Operativsystemdata – ändringsbart tillstånd 
  * Användardata – ändringsbart tillstånd

Var och en HoloLens två drifts tillstånd beskrivs i följande avsnitt.

#### <a name="core-operating-system"></a>Kärnoperativsystemet

Ett oföränderligt tillstånd består av körbara filer och data som inte kan ändras och som endast kan ändras av Microsoft under installationen av uppdateringar. Under en sådan uppdatering av kärnoperativsystemet aktiveras en ny avbildning som innehåller det senaste önskade driftstillståndet.
Det oföränderliga tillståndet markeras som skrivskyddat (eller på annat sätt integritetsskyddat), vilket förhindrar beständighet av skadlig kod med utökade privilegier. Följande körbara filer och data skyddas i oföränderligt tillstånd:
  * Windows Holographic Inbox-drivrutiner
  * Binärfiler för operativsystem
  * Windows inkorgsdrivrutiner
  * Statiska Windows Holographic-inställningar som lagras Windows registreringsdatafil (HKLM)
    * Exempel: HKLM lagrar konfigurationsinformationen för de appar som är installerade på en dator. Den lagrar också information för att identifiera maskinvara och motsvarande drivrutiner.
Genom att skydda dessa i det oföränderliga (integritets- och skrivskyddade) tillståndet ser vi till att kärnoperativsystemet alltid startar i ett betrott tillstånd. När en enhet återställs kan vi dessutom se till att enheten endast startar i de komponenter som finns i det här oföränderliga avsnittet. 

#### <a name="operating-system-data"></a>Operativsystemdata 

Det är viktigt att observera att körbara filer och data som kan ändras vid körning (och som inte är viktiga för operativsystemets funktion) kan tas bort och skapas igen när data skadas eller komprometteras. Ett värdefullt ändringsbart tillstånd krävs antingen funktionellt för att bevaras av operativsystemet eller förväntas finnas kvar vid avstängning av operativsystemet och/eller mellan omstarter av Windows operativsystem och enhetsscenarier. Exempel på ett föränderligt tillstånd med högt värde är:
  * Inställningar för globala enheter som KONFIGURERATs av IT-administratören, till exempel inaktivering av platsen för alla användare.
  * Wi-Fi-nätverksanslutning får åtkomst till nätverk som sparas av enheten och tillhörande anslutningslösenord.
  * Kraschdumpar, inklusive inställningar, loggar.
  * Drivrutiner som laddats ned på begäran för nyligen identifierade enheter.
Ett värdefullt ändringsbart tillstånd HoloLens 2 finns på operativsystemets datasäkerhetsplats, antingen som en sparad fil på disken eller i en ständiga registreringsdatafil.

#### <a name="user-data"></a>Användardata

Den sista tillståndskategorin representerar användardata som skapas eller bevaras av UWP-program eller operativsystemet. Alla kända användarmappar, till exempel nedladdningar, dokument, videor, användarprofiler och HKEY_CURRENT_USER hive lagras också på den här platsen. Dessa data kan inte extraheras utan rätt autentiseringsuppgifter. Mer information om hur dina data skyddas finns i [Kryptering och dataskydd.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Isolering

För att uppnå den här balansen HoloLens 2 ett kärnoperativsystemet som används för primära funktioner som att starta upp, maskinvarukontroll, logga in osv. Det finns bara två uppsättningar program som körs på kärnoperativsystemet – förinstallerade program och UWP-appar.

## <a name="code-signing"></a>Kodsignering

Med digital signeringskod kan du underförstända att körbara filer och skript inte har ändrats eftersom de har signerats av en betrodd källa, vilket ger äkthet och integritet. De myndigheter som HoloLens 2 förtroenden som standard är Microsoft och Microsoft Store. IT-administratörer kan lägga till nya certifikat till enheten via CSK:erna [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) och [RootCATrustedCertificates.](/windows/client-management/mdm/rootcacertificates-csp) De kan också använda [principen AllowAllTrustedApps för](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) att lita på ytterligare separat inlästa appar eller [verksamhetsapplikationer.](/intune/apps/lob-apps-windows) Certifikat finns i den lokala datorns certifikatarkiv som lagras i HKLM/Root om du använder "Enhet" eller i HKCU om du använder "Användare".

## <a name="defender-protections"></a>Defender-skydd
HoloLens 2 använder Microsoft-tjänster för att ge användarna en avancerad säkerhetsnivå:

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aktiveras automatiskt på Windows Holographic av operativsystemet och skyddar mot nätfiske och skadlig kod, samt nedladdning av potentiellt skadliga filer, på Edge. Den kan inte inaktiveras av användaren men kan inaktiveras via en princip.

* [Defender-brandväggen](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blockerar obehörig nätverkstrafik från att flöda till och från din enhet. Den är aktiverad som standard och kan inte konfigureras av kunden via lokala åtgärder eller policyer. 

* [Windows Defender Application Control:](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2 stöder WDAC som gör att IT-administratören kan skicka principer för programkontroll till enheten. Mer information finns i Använda [WDAC på HoloLens 2 enheter med MSFT Intune.](/mem/intune/configuration/custom-profile-hololens) 

IT-administratörer kan hantera SmartScreen-beteende via [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) och webbläsarbeteende genom [dessa principer.](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

