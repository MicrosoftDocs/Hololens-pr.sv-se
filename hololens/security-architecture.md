---
title: HoloLens-säkerhetsarkitektur
description: Säkerhetsarkitektur
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380023"
---
# <a name="security-overview-and-architecture"></a><span data-ttu-id="afb84-104">Säkerhetsöversikt och arkitektur</span><span class="sxs-lookup"><span data-stu-id="afb84-104">Security overview and architecture</span></span>

<span data-ttu-id="afb84-105">HoloLens 2-säkerhetsarkitekturen utformades och utformades från grunden för att vara fri från äldre säkerhetsproblem, samtidigt som man skapade en minimerad angreppsyta.</span><span class="sxs-lookup"><span data-stu-id="afb84-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="afb84-106">Den här nya, innovativa arkitekturen erbjuder säkra lagringsplatser och avancerade säkerhetselement, med mekanismer som kan avskärma operativsystem från potentiella hot och sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="afb84-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="afb84-107">HoloLens 2 kombinerar maskinvara, programvara, nätverk och tjänster för att leverera säkerhet från end-to-end till att ge användaren en optimal upplevelse.</span><span class="sxs-lookup"><span data-stu-id="afb84-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="afb84-108">Med HoloLens 2 aktiveras en stor majoritet av säkerhetsfunktionerna automatiskt, vilket minimerar det arbete som krävs för att konfigurera operativsystemet korrekt.</span><span class="sxs-lookup"><span data-stu-id="afb84-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="afb84-109">Windows HoloLens 2 och operativsystemarkitekturen erbjuder dessa innovativa säkerhetsfunktioner:</span><span class="sxs-lookup"><span data-stu-id="afb84-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="afb84-110">Tillståndsseparation och isolering: Den här nya arkitekturen skyddar kritiska delar av HoloLens 2-operativsystemet från ändringar – till exempel de som krävs för att kärnoperativsystemet ska kunna starta i ett betrott tillstånd.</span><span class="sxs-lookup"><span data-stu-id="afb84-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="afb84-111">Isoleringsteknik används för att begränsa ej betrodda appar i ett sandbox-område, så att de inte kan påverka systemsäkerheten.</span><span class="sxs-lookup"><span data-stu-id="afb84-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="afb84-112">Hela operativsystemet är indelade i säkra avsnitt, där varje avsnitt är avskärmat av en kombination av olika säkerhetstekniker.</span><span class="sxs-lookup"><span data-stu-id="afb84-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="afb84-113">**Dataskydd:** Om en användares enhet blir stulen eller borttappad, förhindrar HoloLens 2 att obehöriga program läser känslig information genom att förlita sig på BitLocker-kryptering av data.</span><span class="sxs-lookup"><span data-stu-id="afb84-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="afb84-114">**Lösenordslös operativsystem:** Äldre lösenordsbaserade operativsystem kan oavsiktligt exponera användare för nätfiskehot och var ofta ansvariga för komprometterade konton.</span><span class="sxs-lookup"><span data-stu-id="afb84-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="afb84-115">Windows Holographic for Business eliminerar användningen av lösenord för MSA- och Azure AD-inloggning och förstärker skyddet av användaridentiteter med Windows Hello™- och FIDO2-inloggning.</span><span class="sxs-lookup"><span data-stu-id="afb84-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="afb84-116">Om du vill ha FIDO2-stöd måste enheten vara på Version 19041 eller senare.</span><span class="sxs-lookup"><span data-stu-id="afb84-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="afb84-117">**Nätverkssäkerhet:** HoloLens 2 ger användaren ökad nätverkssäkerhet via förbättrade protokoll och standardinställningar.</span><span class="sxs-lookup"><span data-stu-id="afb84-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
