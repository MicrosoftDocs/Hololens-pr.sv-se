---
title: Företagsregistrering av HoloLens MAC-adress begränsad Wi-Fi miljö
description: Mac-adress för nätverk på HoloLens 2 enheter
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639445"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="d3f83-103">Företagsregistrering av HoloLens MAC-adress begränsad Wi-Fi miljö</span><span class="sxs-lookup"><span data-stu-id="d3f83-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="d3f83-104">Det här dokumentet beskriver ett vanligt scenario som vi har identifierat i kundmiljöer där Wi-Fi av MAC-adresser eller certifikat krävs för att ansluta trådlösa nätverk.</span><span class="sxs-lookup"><span data-stu-id="d3f83-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="d3f83-105">Exempel på ett scenario</span><span class="sxs-lookup"><span data-stu-id="d3f83-105">Example Scenario</span></span>

<span data-ttu-id="d3f83-106">Många kunder i säkra miljöer har begränsningar för sina trådlösa eller kabelanslutna nätverk som endast tillåter att godkända enheter (baserat på MAC-adresser) kan ansluta korrekt.</span><span class="sxs-lookup"><span data-stu-id="d3f83-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="d3f83-107">Detta kan framtvingas via MAC-adressfiltrering på en trådlös åtkomstpunkt eller via en DHCP-server.</span><span class="sxs-lookup"><span data-stu-id="d3f83-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="d3f83-108">Dessutom kan vissa trådlösa nätverk skyddas med PEAP, vilket kräver att ett certifikat tillämpas på enheten innan autentisering i det trådlösa nätverket.</span><span class="sxs-lookup"><span data-stu-id="d3f83-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="d3f83-109">I det här scenariot kan två viktiga krav leda till fördröjningar eller kräva manuella åtgärder vid HoloLens ansluta enheter till nätverket:</span><span class="sxs-lookup"><span data-stu-id="d3f83-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="d3f83-110">Det trådlösa PEAP-certifikatet måste tillämpas på enheten innan enheten kan ansluta till det trådlösa nätverket.</span><span class="sxs-lookup"><span data-stu-id="d3f83-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="d3f83-111">MAC-adressen för HoloLens Wi-Fi adaptern måste vara registrerad.</span><span class="sxs-lookup"><span data-stu-id="d3f83-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="d3f83-112">De viktigaste utmaningarna med kraven ovan är:</span><span class="sxs-lookup"><span data-stu-id="d3f83-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="d3f83-113">MAC-adressen kan för närvarande bara identifieras från Inställningar på enheten eller från Intune efter en lyckad registrering.</span><span class="sxs-lookup"><span data-stu-id="d3f83-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="d3f83-114">Utan MAC-adressen kan enheten inte ansluta till Wi-Fi Network för att påbörja registreringen.</span><span class="sxs-lookup"><span data-stu-id="d3f83-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="d3f83-115">Manuella lösningar på dessa utmaningar kräver att en tekniker interagerar med enheten.</span><span class="sxs-lookup"><span data-stu-id="d3f83-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="d3f83-116">Lösningar</span><span class="sxs-lookup"><span data-stu-id="d3f83-116">Solutions</span></span>

<span data-ttu-id="d3f83-117">Det finns många sätt att förbättra den här situationen, beroende på vilken infrastruktur som är tillgänglig i miljön.</span><span class="sxs-lookup"><span data-stu-id="d3f83-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="d3f83-118">Lösning</span><span class="sxs-lookup"><span data-stu-id="d3f83-118">Solution</span></span> | <span data-ttu-id="d3f83-119">Fördelar</span><span class="sxs-lookup"><span data-stu-id="d3f83-119">Benefits</span></span> | <span data-ttu-id="d3f83-120">Krav</span><span class="sxs-lookup"><span data-stu-id="d3f83-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d3f83-121">Etableringspaket med Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="d3f83-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="d3f83-122">Förbättrar OOBE-upplevelsen och ger en snabbare reparatörsupplevelse.</span><span class="sxs-lookup"><span data-stu-id="d3f83-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="d3f83-123">HoloLens USB-C Hub + Ethernet-adapter och teknikern behöver fortfarande interagera med enheten för MAC-avskiljning och OOBE-slutförande</span><span class="sxs-lookup"><span data-stu-id="d3f83-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="d3f83-124">Autopilot med Intune-registrering över Ethernet</span><span class="sxs-lookup"><span data-stu-id="d3f83-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="d3f83-125">Det här är en enkelstegsanslutning och registrering av enheten till kundmiljön.</span><span class="sxs-lookup"><span data-stu-id="d3f83-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="d3f83-126">MAC-avskiljning kan slutföras utan att du behöver interagera med enheten</span><span class="sxs-lookup"><span data-stu-id="d3f83-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="d3f83-127">Intune aktiverat för kundens AAD-klientorganisation och en HoloLens USB-C Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="d3f83-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="d3f83-128">Automatisk rapportering av MAC-adresser</span><span class="sxs-lookup"><span data-stu-id="d3f83-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="d3f83-129">När enheter registreras med Intune-klienten kan ett skript rapportera MAC-adressen till teknikern.</span><span class="sxs-lookup"><span data-stu-id="d3f83-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="d3f83-130">Intune PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="d3f83-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="d3f83-131">Etableringspaket med Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="d3f83-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="d3f83-132">Om det kabelanslutna nätverket också omfattas av MAC-begränsningar måste MAC-adressen för USB-C Hub + Ethernet-adaptern också vara förhandsgodkänd.</span><span class="sxs-lookup"><span data-stu-id="d3f83-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="d3f83-133">Var försiktig med det här kortet eftersom det tillåter åtkomst till nätverket från andra enheter.</span><span class="sxs-lookup"><span data-stu-id="d3f83-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="d3f83-134">Krav</span><span class="sxs-lookup"><span data-stu-id="d3f83-134">Requirements</span></span>

- <span data-ttu-id="d3f83-135">Kabelansluten nätverksport med åtkomst till kundnätverket</span><span class="sxs-lookup"><span data-stu-id="d3f83-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="d3f83-136">HoloLens Kompatibel USB-C Hub med Ethernet-adapter – Alla nätverkskort som inte kräver några ytterligare drivrutiner eller programinstallationer bör vara lämpliga.</span><span class="sxs-lookup"><span data-stu-id="d3f83-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="d3f83-137">Etableringspaket som innehåller:</span><span class="sxs-lookup"><span data-stu-id="d3f83-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="d3f83-138">Innehåller information om trådlöst nätverk och certifikat</span><span class="sxs-lookup"><span data-stu-id="d3f83-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="d3f83-139">Du kan också ange registreringsinformation för organisationens Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3f83-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="d3f83-140">Innehåller andra nödvändiga etableringsinställningar</span><span class="sxs-lookup"><span data-stu-id="d3f83-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="d3f83-141">Process</span><span class="sxs-lookup"><span data-stu-id="d3f83-141">Process</span></span>

<span data-ttu-id="d3f83-142">Processen kan variera beroende på enhetens programvarunivå.</span><span class="sxs-lookup"><span data-stu-id="d3f83-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="d3f83-143">Om enheten har uppdateringen [från maj 2004](hololens-release-notes.md#windows-holographic-version-2004)följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="d3f83-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="d3f83-144">Placera etableringspaketet på roten av ett USB-minne och anslut det till hubben.</span><span class="sxs-lookup"><span data-stu-id="d3f83-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="d3f83-145">Anslut Ethernet-kabel till Hub + Ethernet-adaptern.</span><span class="sxs-lookup"><span data-stu-id="d3f83-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="d3f83-146">Anslut USB-C Hub till HoloLens enhet.</span><span class="sxs-lookup"><span data-stu-id="d3f83-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="d3f83-147">Aktivera HoloLens och sätt på enheten.</span><span class="sxs-lookup"><span data-stu-id="d3f83-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="d3f83-148">Tryck på **knappen Volym ned och Ström för** att tillämpa etableringspaketet.</span><span class="sxs-lookup"><span data-stu-id="d3f83-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="d3f83-149">Teknikern kan nu följa OOBE och när det är klart öppnar du Inställningar appen för att hämta MAC-adressen för enheten.</span><span class="sxs-lookup"><span data-stu-id="d3f83-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="d3f83-150">Om enheten har en version av operativsystemet före [uppdateringen från maj 2004](hololens-release-notes.md#windows-holographic-version-2004)följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="d3f83-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="d3f83-151">Sätt på HoloLens och anslut enheten till en dator.</span><span class="sxs-lookup"><span data-stu-id="d3f83-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="d3f83-152">Enheten bör visas på datorn som en fillagringsenhet.</span><span class="sxs-lookup"><span data-stu-id="d3f83-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="d3f83-153">Kopiera etableringspaketet till enheten</span><span class="sxs-lookup"><span data-stu-id="d3f83-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="d3f83-154">Anslut Ethernet-kabel till hubben.</span><span class="sxs-lookup"><span data-stu-id="d3f83-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="d3f83-155">Anslut USB-C Hub till HoloLens enhet.</span><span class="sxs-lookup"><span data-stu-id="d3f83-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="d3f83-156">Placera på HoloLens</span><span class="sxs-lookup"><span data-stu-id="d3f83-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="d3f83-157">Tryck på **knappen Volym ned och Ström** för att tillämpa etableringspaketet.</span><span class="sxs-lookup"><span data-stu-id="d3f83-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="d3f83-158">Teknikern kan nu följa OOBE och när det är klart öppnar du Inställningar appen för att hämta MAC-adressen för enheten.</span><span class="sxs-lookup"><span data-stu-id="d3f83-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="d3f83-159">Fördelar</span><span class="sxs-lookup"><span data-stu-id="d3f83-159">Benefits</span></span>

<span data-ttu-id="d3f83-160">På så sätt kan enheten ha en "enkel tryckning" för att tillämpa rätt etableringspaket och samla in MAC-adressen för enheten.</span><span class="sxs-lookup"><span data-stu-id="d3f83-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="d3f83-161">Du kan skapa etableringspaket genom att följa riktlinjerna här.</span><span class="sxs-lookup"><span data-stu-id="d3f83-161">Provisioning packages can be created following the guidance here.</span></span>](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="d3f83-162">Autopilot med Intune-registrering</span><span class="sxs-lookup"><span data-stu-id="d3f83-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="d3f83-163">Krav</span><span class="sxs-lookup"><span data-stu-id="d3f83-163">Requirements</span></span>

- <span data-ttu-id="d3f83-164">Kabelansluten nätverksport med åtkomst till kundnätverket</span><span class="sxs-lookup"><span data-stu-id="d3f83-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="d3f83-165">HoloLens enheter som kör Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="d3f83-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="d3f83-166">HoloLens Kompatibel USB-C Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="d3f83-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="d3f83-167">Intune konfigurerad och aktiverad för kundens klientorganisation</span><span class="sxs-lookup"><span data-stu-id="d3f83-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="d3f83-168">Enheten är registrerad för Autopilot och importeras till kundklientorganisationen</span><span class="sxs-lookup"><span data-stu-id="d3f83-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="d3f83-169">Intune-principer som definierats för enheten:</span><span class="sxs-lookup"><span data-stu-id="d3f83-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="d3f83-170">Innehåller information om trådlöst nätverk och certifikat</span><span class="sxs-lookup"><span data-stu-id="d3f83-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="d3f83-171">Innehåller andra nödvändiga etableringsinställningar</span><span class="sxs-lookup"><span data-stu-id="d3f83-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="d3f83-172">Detta gör det möjligt för en kund med avancerade nätverkskrav att registrera enheterna i en skalbar hands-off-metod</span><span class="sxs-lookup"><span data-stu-id="d3f83-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="d3f83-173">Ytterligare förutsättningar kommer att behövas enligt nedan:</span><span class="sxs-lookup"><span data-stu-id="d3f83-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="d3f83-174">[Aktivera klientorganisationen för Autopilot-förhandsgranskningen](hololens2-autopilot.md).</span><span class="sxs-lookup"><span data-stu-id="d3f83-174">[Enable the Tenant for the Autopilot preview](hololens2-autopilot.md).</span></span>
1. <span data-ttu-id="d3f83-175">Skapa HoloLens för att ersätta etableringspaketet i Intune.</span><span class="sxs-lookup"><span data-stu-id="d3f83-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="d3f83-176">Skapa HoloLens Intune-principer.</span><span class="sxs-lookup"><span data-stu-id="d3f83-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="d3f83-177">Tilldela enheterna till rätt grupp.</span><span class="sxs-lookup"><span data-stu-id="d3f83-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="d3f83-178">Process</span><span class="sxs-lookup"><span data-stu-id="d3f83-178">Process</span></span>

1. <span data-ttu-id="d3f83-179">Anslut ethernet-kabeln till adaptern och anslut adaptern till USB-C-porten på HoloLens 2-enheten.</span><span class="sxs-lookup"><span data-stu-id="d3f83-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="d3f83-180">Aktivera HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d3f83-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="d3f83-181">Enheten bör automatiskt ansluta till Internet under OOBE via Ethernet-adaptern.</span><span class="sxs-lookup"><span data-stu-id="d3f83-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="d3f83-182">Den bör identifiera Autopilot-konfigurationen och automatiskt registreras med Azure AD och Intune.</span><span class="sxs-lookup"><span data-stu-id="d3f83-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="d3f83-183">Enheten tillämpar de nödvändiga Wi-Fi certifikat och annan konfiguration efter behov via Intune.</span><span class="sxs-lookup"><span data-stu-id="d3f83-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="d3f83-184">När det är klart kan teknikern läsa in Intune-portalen (Endpoint Manager) och gå in på sidan med enhetsegenskaper på **Start ->-enheter -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="d3f83-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="d3f83-185">Den Wi-Fi MAC-adressen visas i Intune-portalen.</span><span class="sxs-lookup"><span data-stu-id="d3f83-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![MAC-adress via Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="d3f83-187">Teknikern lägger till den här MAC-adressen som en tillåten enhet.</span><span class="sxs-lookup"><span data-stu-id="d3f83-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="d3f83-188">Fördelar</span><span class="sxs-lookup"><span data-stu-id="d3f83-188">Benefits</span></span>

<span data-ttu-id="d3f83-189">Detta gör det möjligt för teknikern att distribuera "huvuden" där enheten kan registreras i Azure AD och Intune utan att teknikern behöver ha på sig enheten eller interagera manuellt med HoloLens-miljön.</span><span class="sxs-lookup"><span data-stu-id="d3f83-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="d3f83-190">Rapportering av MAC-adresser till teknikern</span><span class="sxs-lookup"><span data-stu-id="d3f83-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="d3f83-191">Krav</span><span class="sxs-lookup"><span data-stu-id="d3f83-191">Requirements</span></span>

- <span data-ttu-id="d3f83-192">Auktorisering av "Intune Graph PowerShell" mot kundens klientorganisation</span><span class="sxs-lookup"><span data-stu-id="d3f83-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="d3f83-193">Installation av Intune Graph PowerShell på teknikerdatorn.</span><span class="sxs-lookup"><span data-stu-id="d3f83-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="d3f83-194">Läsåtkomst till elementen "Hanterade enheter" i Intune.</span><span class="sxs-lookup"><span data-stu-id="d3f83-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="d3f83-195">(Supportansvarig eller högre, eller en anpassad roll)</span><span class="sxs-lookup"><span data-stu-id="d3f83-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="d3f83-196">För närvarande finns det inget "enkelt" sätt att utlösa ett automationskommando baserat på registreringen av en ny enhet i Intune.</span><span class="sxs-lookup"><span data-stu-id="d3f83-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="d3f83-197">Därför ger det här kommandot teknikern ett enkelt sätt att hämta MAC-adressen utan att behöva logga in på portalen och hämta den manuellt.</span><span class="sxs-lookup"><span data-stu-id="d3f83-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="d3f83-198">Detta returnerar namn och MAC-adress för alla HoloLens som har registrerats under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="d3f83-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![MAC-adress via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="d3f83-200">Process</span><span class="sxs-lookup"><span data-stu-id="d3f83-200">Process</span></span>

<span data-ttu-id="d3f83-201">När Intune-registreringen har slutförts kör teknikern skriptet ovan för att hämta MAC-adressen.</span><span class="sxs-lookup"><span data-stu-id="d3f83-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
