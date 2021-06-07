---
title: Begränsa lösenordsanvändning
description: begränsa lösenordsanvändning för HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limiting password use, password, hololens password, sign-in, sign in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WEOLTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6233e9f422022dc3fb4f3e615261504b9686f501
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380032"
---
# <a name="limiting-password-use"></a>Begränsa lösenordsanvändning

De flesta datorsystem använder idag användarautentiseringsuppgifter som grund för säkerhet, vilket gör dem beroende av återanvändbara, användarskapade lösenord. Detta har lett till att lösenord också blivit den vanligaste orsaken till kontokompromettering och dataintrång. Som ett exempel på detta kan lösenord fångas upp vid överföring eller stjälas från en server (genom nätfiske- eller lösenordsattacker) och komprometteras för att få åtkomst till ett användarkonto.

För att förbättra säkerheten och kontoskyddet har HoloLens 2 möjlighet att aktivera starka, maskinvarubaserade "lösenordslös" autentiseringsuppgifter (inklusive Windows Hello) för enhetsinloggning, vilket ger sömlös åtkomst till Microsoft-molnet.

## <a name="signing-in-from-another-device"></a>Logga in från en annan enhet

HoloLens 2 erbjuder alternativ för fjärrenhetsinloggning för Azure Active Directory-arbetskonton under den första enhetskonfigurationen och användarsinloggningen för att minska behovet av att skriva komplexa lösenord och minimera behovet av lösenord som autentiseringsuppgifter. Användare och organisationer som använder smartkort för att autentisera har svårt att använda dessa autentiseringsuppgifter på enheter som HoloLens 2, och ofta utvecklar organisationer komplicerade system och kostsamma processer för att lösa problemet. För att lösa det här problemet erbjuder Azure AD två alternativ för lösenordslös inloggning på HoloLens 2.

Den första autentiseringsmetoden förlitar sig på nya funktioner i Microsoft Authenticator-appen för att tillhandahålla nyckelbaserad autentisering som gör det möjligt för en användare att ange autentiseringsuppgifter som är knutna till en enhet. När administratören har aktiverat detta på en klientorganisation visas ett meddelande under HoloLens-enhetskonfigurationen som uppmanar dem att trycka på ett nummer i appen. De måste sedan matcha numret i sin autentiseringsapp, välja Godkänn, ange sin PIN-kod eller en biometrisk och fullständig autentisering för att HoloLens-konfigurationen ska fortsätta. Detta beskrivs mer detaljerat i [lösenordsfri inloggning.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)

Det andra är ett enhetskodflöde som är intuitivt för användarna och som inte kräver någon ytterligare infrastruktur.  Det här beteendet för fjärr inloggning förlitar sig på en annan betrodd enhet som stöder organisationens önskade autentiseringsmekanism och när det är klart utfärdas token tillbaka till HoloLens för att slutföra inloggningen eller enhetskonfigurationen. Stegen i det här flödet är:

  1. En användare som går igenom de första enhetskonfigurations- eller inloggningsflödena i OOBE ser länken "Logga in från en annan enhet" och trycker på den. Detta initierar en fjärrsession för inloggning.
  1. Användaren visas sedan en avsökningssida som innehåller en kort URI ( ) som pekar på slutpunkten för enhetsautentisering i [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) Azure AD Secure Token Service (STS). Användaren får också en enda kod som genereras på ett säkert sätt i molnet och som har en maximal livslängd på 15 minuter. Tillsammans med kodgenereringen skapar Azure AD även en krypterad session när begäran om fjärrin inloggning initieras i föregående steg och tillsammans används URI och kod för att godkänna begäran om fjärrin inloggning.
  1. Användaren navigerar sedan till URI:en från en annan enhet och uppmanas att ange koden som visas på hololens 2-enheten.
  1. När användaren anger koden visar Azure AD STS en sida som anger användarens HoloLens 2-enhet som utlöste fjärrindatabegäran och begärde generering av koden. Användaren uppmanas sedan att bekräfta för att förhindra nätfiskeattacker.
  1. Om användaren väljer att fortsätta att logga in på det visade programmet uppmanar Azure AD STS användaren att ange sina autentiseringsuppgifter. Vid lyckad autentisering uppdaterar Azure AD STS den cachelagrade fjärrsessionen som "godkänd" tillsammans med en auktoriseringskod.
  1. Slutligen tar avsökningssidan på användarens HoloLens 2-enhet emot ett "auktoriserat" svar från Azure AD och fortsätter med att verifiera användarkoden, dess associerade lagrade auktoriseringskod och genererar OAuth-tokens på begäran för att slutföra enhetskonfigurationen. Den skapade autentiseringstoken är giltig i 1 timme och uppdateringstoken har en livslängd på 90 dagar.

Kodgenereringen och krypteringsalgoritmerna som används i det här flödet är båda FIPS-kompatibla. HoloLens 2-enheter använder TPM för att skydda enhetsnycklar och kryptera token som genereras efter användarautentisering med hjälp av maskinvaruskyddade nycklar. Mer information om tokensäkerhet på HoloLens 2 finns i [Vad är en primär uppdateringstoken (PRT).](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Enhets inloggning med Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) erbjuder lösenordsfria alternativ som är inbyggda direkt i operativsystemet, så att användarna kan logga in på enheten med Iris eller PIN-kod. PIN-koden är alltid tillgänglig som autentiseringsuppgifter och krävs för enhetskonfiguration, medan Iris är valfritt och kan hoppas över. Användare kan logga in på HoloLens-enheter med sina personliga Microsoft-konto eller [Azure Active Directory utan *att* ange ett lösenord.](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) Alternativ som dessa ger användare snabb och säker åtkomst till deras fullständiga Windows-upplevelse, appar, data, webbplatser och tjänster. Microsofts strategi för lösenordslösa upplevelser beskrivs här.

När en Windows Hello autentiseringsuppgifter skapas upprättar den en betrodd relation med en identitetsprovider och skapar ett asymmetriskt nyckelpar för autentisering. En Windows Hello gest (till exempel iris eller PIN) ger entropi för att dekryptera en privat nyckel som backas upp av enhetens Trusted Platform Module(TPM)-chip. Den privata nyckeln används sedan för att signera begäranden som skickas till en autentiseringsserver och vid lyckad autentisering beviljas användaren åtkomst till sin e-post, sina bilder och andra kontoinställningar.

Mer information finns i följande informationsgrafik:

  ![Windows Hello inloggning](images/security-hello-sign-in.png)
  
Observera i bilden ovan att nonce står för "number once" (tal en gång) och är ett slumpmässigt eller halvs slumpgenererat tal. När Windows Hello biometriska autentiseringsuppgifter eller PIN-autentiseringsuppgifter har ställts in lämnar den aldrig enheten där den har etablerats. Även om användarens PIN Windows Hello blir stulen, till exempel via en nätfiskeattack, är den oanvändbar utan [användarens fysiska enhet](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

För ökad säkerhet skyddas Windows Hello-autentiseringsuppgifter av Trusted Platform Module (TPM) för att göra autentiseringsuppgifterna manipulering motståndskraftiga och skyddas med skydd mot flera felaktiga poster och skydd mot skadlig programvara för att förhindra exponering. Mer information om enkel inloggning Sign-On (SSO) finns i den här [översikten över SSO-metoder.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)

Irisautentisering faller tillbaka till PIN-koden. För att kunna konfigurera en ny PIN-kod (en stark autentisering) på enheten måste användaren nyligen ha gått igenom multifaktorautentisering [(MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) för att slutföra processen.

## <a name="single-sign-on-with-web-account-manager"></a>Enkel inloggning med Webbkontohanterare

Med enkel inloggning (SSO) kan lösenordslös användare logga in på enheten med användarens personliga konto eller sitt arbets- eller skolkonto. Användaren auktoriserats automatiskt med enkel inloggning för alla integrerade appar och tjänster via de Webbkontohanterare [API:erna](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

När en identitet har lagts till via ett program kan den, med användarmedgivande, bli tillgänglig för alla appar och tjänster som använder integrering på systemnivå. Detta minskar appens inloggningsbelastning avsevärt och ger användarna en sömlös identitetsupplevelse.

Mer information om hur du implementerar Webbkontohanterare-API:er finns i [Implementera Webbkontohanterare API:er](https://docs.microsoft.com/windows/uwp/security/web-account-manager).

  ![API för säkerhet](images/security-api-img.png)
  
För appaket med särskilda autentiseringskrav kan Webbkontohanterare (WAM) utökas till anpassade identitetsproviders. Användare kan ladda ned den anpassade identitetsprovidern, paketerad som en Universell Windows-plattform-app (UWP) från Microsoft Store för att aktivera enkel inloggning på andra appar som är integrerade med identitetsprovidern.

Mer information om hur du implementerar anpassade WAM-identitetsproviders finns i API-referens för anpassad [WAM-identitetsprovider.](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello- och FIDO2-inloggning med WebAuthn

HoloLens 2 kan använda lösenordslös användarautentisering (till exempel Windows Hello- eller FIDO2-säkerhetsnycklar) för att på ett säkert sätt logga in på webben via Microsoft Edge och på webbplatser som stöder WebAuthn. FIDO2 gör att användarens autentiseringsuppgifter kan dra nytta av standardbaserade enheter för att autentisera till onlinetjänster.

> [!Note]
> Specifikationerna [för WebAuthn](https://www.w3.org/TR/webauthn/) och FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) implementeras i tjänster. De signerade metadata som anges av WebAuthn och FIDO2 innehåller information – till exempel om användaren var närvarande – och verifierar autentiseringen via den lokala gesten.

Precis som med Windows Hello skapar och registrerar en FIDO2-autentiseringsperson när användaren skapar och registrerar en FIDO2-autentiseringsnyckel genererar enheten (HoloLens 2 eller FIDO2-säkerhetsnyckeln) en privat och offentlig nyckel på enheten. Den privata nyckeln lagras säkert på enheten och kan bara användas när den har låsts upp med en lokal gest, till exempel en biometrik eller PIN-kod. När den privata nyckeln lagras skickas den offentliga nyckeln till Microsoft-konto i molnet och registreras med det associerade användarkontot.

När du har loggat in med ett MSA- och Azure AD-konto skickar systemet ett genererat nummer eller en datavariabel till HoloLens 2- eller FIDO2-enheten. HoloLens 2 eller enheten använder den privata nyckeln för att signera identifieringen. Den signerade identifieringen och metadata skickas tillbaka till Microsoft-konto och verifieras med hjälp av den offentliga nyckeln.

Windows Hello- och FIDO2-enheter implementerar autentiseringsuppgifter baserat på HoloLens-enheten, särskilt den inbyggda Trusted Platform Module säkra enklaven. TPM-enklaven lagrar den privata nyckeln och kräver antingen en biometrik eller PIN-kod för att låsa upp den. På samma sätt är en FIDO2-säkerhetsnyckel en liten extern enhet med en inbyggd säker enklav som lagrar den privata nyckeln och kräver en biometrik eller PIN-kod för att låsa upp den.

Båda alternativen erbjuder tvåfaktorsautentisering i ett steg, vilket kräver både en registrerad enhet och en biometrik eller PIN-kod för att logga in. Mer information finns i bilden och processen för stark autentisering med FIDO2-säkerhetsnyckel, som följer.

### <a name="strong-authentication-with-fido2-security-key"></a>Stark autentisering med FIDO2-säkerhetsnyckel

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. Användaren ansluter FIDO2-säkerhetsnyckeln till HoloLens 2
1. Windows identifierar FIDO2-säkerhetsnyckel
1. HoloLens skickar auth-begäran
1. Azure AD skickar tillbaka nonce
1. Användaren slutför gesten för att låsa upp privata nyckellager i säkerhetsnyckelns säkra enklav
1. FIDO2-säkerhetsnyckel signerar nonce med privat nyckel
1. PRT-tokenbegäran med signerad nonce skickas till Azure AD
1. Azure AD verifierar FIDO-nyckel
1. Azure AD returnerar PRT och TGT för att ge åtkomst till resurser

MSA och Azure AD är bland de första förlitande parterna som stöder lösenordslös autentisering genom att implementera WebAuthn.

Mer information om hur du använder WebAuthn med program och/eller SDK:er finns i [WebAuthn-API:er](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis)för lösenordslös autentisering på Windows 10 .

HoloLens 2 stöder FIDO2-säkerhetsenheter som implementeras för att uppfylla kraven som anges i [Azure Active Directory lösenordsfri inloggning – FIDO2-säkerhetsnycklar](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) bör stödjas.

## <a name="local-accounts"></a>Lokala konton

Ett enda lokalt konto kan konfigureras för distributioner i offlineläge. Lokala konton är inte aktiverade som standard och måste konfigureras under enhetsetablering. De måste logga in med ett lösenord och de stöder inte alternativa autentiseringsmetoder (till exempel [Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) eller [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)).

Mer information om HoloLens-användarkonton finns på [HoloLens Identity](https://docs.microsoft.com/hololens/hololens-identity).

IT-administratörer justerar om användaren tillåts använda ett MSA-konto för icke-e-postrelaterad anslutningsautentisering och tjänster via [AllowMicrosoftAccountConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) Information om lösenordskonfigurationsprinciper, introutningsprinciper och principer för låsskärm finns [i Enhetslås.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)
