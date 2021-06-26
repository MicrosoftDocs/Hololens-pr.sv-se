---
title: Kända problem för HoloLens (första generationen)
description: Håll dig uppdaterad med vår lista över kända problem och lösningar som kan påverka HoloLens-kunder och utvecklare som använder Unity och Windows Enhetsportalen.
keywords: troubleshoot, known issue, help
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923558"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="3a6f8-104">Kända problem för HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="3a6f8-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="3a6f8-105">Här är den aktuella listan över kända problem för HoloLens-enheter.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="3a6f8-106">Kontrollera här först om du ser ett udda beteende.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="3a6f8-107">Den här listan uppdateras när nya problem identifieras eller rapporteras, eller när problem åtgärdas i framtida HoloLens-programuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="3a6f8-108">Om du upptäcker ett problem som inte blockerar kan du rapportera det på din HoloLens-enhet via [Feedbackhubben](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="3a6f8-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="3a6f8-109">Om problemet blockerar dig kan du, förutom att skicka feedback, skicka [en supportbegäran.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="3a6f8-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="3a6f8-110">Kända problem för alla HoloLens-generationer</span><span class="sxs-lookup"><span data-stu-id="3a6f8-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="3a6f8-111">Kända problem för HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="3a6f8-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="3a6f8-112">Kända problem för alla HoloLens-generationer</span><span class="sxs-lookup"><span data-stu-id="3a6f8-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="3a6f8-113">Unity</span><span class="sxs-lookup"><span data-stu-id="3a6f8-113">Unity</span></span>

- <span data-ttu-id="3a6f8-114">Se [Installera verktygen för](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) den senaste versionen av Unity som rekommenderas för HoloLens-utveckling.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-114">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="3a6f8-115">Kända problem med Unity HoloLens Technical Preview dokumenteras i [HoloLens Unity-forumen](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="3a6f8-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="3a6f8-116">Windows Enhetsportalen</span><span class="sxs-lookup"><span data-stu-id="3a6f8-116">Windows Device Portal</span></span>

- <span data-ttu-id="3a6f8-117">Funktionen Förhandsgranskning i Mixed Reality kan uppvisa flera sekunders svarstid.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="3a6f8-118">På sidan Virtuella indata fungerar inte kontrollerna Gester och Rullning under avsnittet Virtuella gester.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="3a6f8-119">Att använda dem har ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-119">Using them will have no effect.</span></span> <span data-ttu-id="3a6f8-120">Det virtuella tangentbordet på den virtuella indatasidan fungerar korrekt.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="3a6f8-121">När du har aktiverat Utvecklarläge i Inställningar kan det ta några sekunder innan växlingen aktiveras så att Enhetsportalen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="3a6f8-122">Ladda upp OneDrive-kamera</span><span class="sxs-lookup"><span data-stu-id="3a6f8-122">OneDrive camera upload</span></span>

<span data-ttu-id="3a6f8-123">OneDrive-appen för HoloLens stöder inte automatisk kamerauppladdning för arbets- eller skolkonton.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="3a6f8-124">Workarounds:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-124">Workarounds:</span></span>

- <span data-ttu-id="3a6f8-125">Om det är praktiskt för ditt företag stöds automatisk kamerauppladdning på Microsoft-konsumentkonton.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="3a6f8-126">Du kan logga in på din Microsoft-konto utöver ditt arbets- eller skolkonto (OneDrive-appen stöder dubbel inloggning).</span><span class="sxs-lookup"><span data-stu-id="3a6f8-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="3a6f8-127">Från din Microsoft-konto i OneDrive kan du aktivera automatisk överföring av kamerarulle i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="3a6f8-128">Om du inte på ett säkert sätt kan använda en Microsoft-konto för att ladda upp dina foton automatiskt kan du manuellt ladda upp foton till ditt arbets- eller skolkonto från OneDrive-appen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="3a6f8-129">Det gör du genom att kontrollera att du är inloggad på ditt arbets- eller skolkonto i OneDrive-appen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="3a6f8-130">Välj knappen **+** och välj Ladda **upp.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="3a6f8-131">Hitta de foton eller videor som du vill ladda upp genom att gå till **Bilder > Kamerarulle**.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="3a6f8-132">Välj de foton eller videor som du vill ladda upp och välj sedan **knappen** Öppna.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="3a6f8-133">Kända problem för HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="3a6f8-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="3a6f8-134">Det går inte att ansluta och distribuera till HoloLens via Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a6f8-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="3a6f8-135">Senaste uppdatering: 8/8 @ 17:11 – Visual Studio har släppt VS 2019 version 16.2 som innehåller en korrigering av det här problemet.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="3a6f8-136">Vi rekommenderar att du uppdaterar till den senaste versionen för att undvika att det här felet uppstår.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="3a6f8-137">Visual Studio har släppt VS 2019 version 16.2, vilket innehåller en korrigering av det här problemet.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="3a6f8-138">Vi rekommenderar att du uppdaterar till den senaste versionen för att undvika att det här felet uppstår.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="3a6f8-139">Rotorsak till problemet: Användare som använde Visual Studio 2015 eller tidiga versioner av Visual Studio 2017 för att distribuera och felsöka program på sina HoloLens och sedan använde de senaste versionerna av Visual Studio 2017 eller Visual Studio 2019 med samma HoloLens kommer att påverkas.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="3a6f8-140">De nyare versionerna av Visual Studio distribuerar en ny version av en komponent, men filer från den äldre versionen lämnas kvar på enheten, vilket gör att den nyare versionen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="3a6f8-141">Detta orsakar följande felmeddelande: DEP0100: Kontrollera att målenheten har utvecklarläge aktiverat.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="3a6f8-142">Det gick inte att hämta någon utvecklarlicens \<ip\> på grund av felet 80004005.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="3a6f8-143">Lösning</span><span class="sxs-lookup"><span data-stu-id="3a6f8-143">Workaround</span></span>

<span data-ttu-id="3a6f8-144">Vårt team arbetar för närvarande med en korrigering.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="3a6f8-145">Under tiden kan du använda följande steg för att komma runt problemet och hjälpa till att avblockera distribution och felsökning:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="3a6f8-146">Öppna Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="3a6f8-147">Välj **Arkiv**  >  **Nytt**  >  **projekt.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="3a6f8-148">Välj **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="3a6f8-149">Ge projektet ett namn (till exempel "HoloLensDeploymentFix") och kontrollera att Ramverk är inställt på minst .NET Framework 4.5 och välj **sedan OK.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="3a6f8-150">Högerklicka på noden **Referenser** i Solution Explorer lägg till följande referenser (välj i **avsnittet Bläddra** och välj **Bläddra**):</span><span class="sxs-lookup"><span data-stu-id="3a6f8-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="3a6f8-151">Om du inte har 10.0.18362.0 installerat använder du den senaste versionen som du har.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="3a6f8-152">Högerklicka på projektet i Solution Explorer lägg till   >  **befintligt objekt.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="3a6f8-153">Bläddra till C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 och ändra filtret till **Alla filer ( . \* \* )**.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="3a6f8-154">Välj både SirepClient.dll och SshClient.dll och Välj Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="3a6f8-155">Leta upp och välj båda filerna i Solution Explorer (de bör finnas längst ned i listan  över filer) och ändra **Kopiera** till utdatakatalog i fönstret Egenskaper till **Kopiera alltid.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="3a6f8-156">Överst i filen lägger du till följande i den befintliga listan med `using` -instruktioner:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="3a6f8-157">I `static void Main(...)` lägger du till följande kod:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="3a6f8-158">Välj **Build**  >  **Build Solution (Skapa bygglösning).**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="3a6f8-159">Öppna ett kommandotolkfönster och cd till mappen som innehåller den kompilerade .exe-filen (till exempel C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="3a6f8-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="3a6f8-160">Kör den körbara filen och ange enhetens IP-adress som ett kommandoradsargument.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="3a6f8-161">(Om du är ansluten via USB kan du använda 127.0.0.1, annars kan du använda enhetens IPWi-Fi adress.)  Till exempel "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="3a6f8-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="3a6f8-162">När verktyget har avslutats utan meddelanden (detta bör bara ta några sekunder) kommer du nu att kunna distribuera och felsöka från Visual Studio 2017 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="3a6f8-163">Fortsatt användning av verktyget är inte nödvändigt.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="3a6f8-164">Vi kommer att tillhandahålla ytterligare uppdateringar när de blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="3a6f8-165">Problem med att starta Microsoft Store appar på HoloLens</span><span class="sxs-lookup"><span data-stu-id="3a6f8-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="3a6f8-166">Senaste uppdatering: 04.02 kl. 10:00 – Problemet har lösts.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="3a6f8-167">Du kan få problem när du försöker starta Microsoft Store appar på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="3a6f8-168">Vi har fastställt att problemet uppstår när uppdateringar av bakgrundsappen distribuerar en nyare version av ramverkspaket i specifika sekvenser medan en eller flera av deras beroende appar fortfarande körs.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="3a6f8-169">I det här fallet levererade en automatisk appuppdatering en ny version av .NET Native Framework (version 10.0.25531 till 10.0.27413) vilket gjorde att de appar som kördes inte uppdaterades korrekt för alla appar som kördes med den tidigare versionen av ramverket.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="3a6f8-170">Flödet för framework-uppdateringen är följande:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="3a6f8-171">Det nya ramverkspaketet laddas ned från arkivet och installeras.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="3a6f8-172">Alla appar äldre ramverket "uppdateras" för att använda den nyare versionen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="3a6f8-173">Om steg 2 avbryts innan det slutförs misslyckas alla appar som det nyare ramverket inte har registrerats för att starta från Start-menyn.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="3a6f8-174">Vi tror att alla appar på HoloLens kan påverkas av det här problemet.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="3a6f8-175">Vissa användare har rapporterat att stängning av låsta appar och start av andra appar som Feedbackhubben, 3D-visningsprogram eller Photos löser problemet för dem – men det fungerar inte 100 % av gångerna.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="3a6f8-176">Vi har rotorsaken till att det här problemet inte orsakade själva uppdateringen, men en bugg i operativsystemet som resulterade i att .NET Native framework-uppdateringen hanterades felaktigt.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="3a6f8-177">Vi är glada över att kunna meddela att vi har identifierat en korrigering och har släppt en uppdatering (OS-version 17763.380) som innehåller korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="3a6f8-178">Så här ser du om enheten kan ta uppdateringen:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="3a6f8-179">Gå till appen Inställningar och öppna **Update & Security**.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="3a6f8-180">Välj **Sök efter uppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="3a6f8-181">Om det finns en uppdatering till 17763.380 uppdaterar du till den här versionen för att få korrigeringen för buggen App Hang (Appen låser sig).</span><span class="sxs-lookup"><span data-stu-id="3a6f8-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="3a6f8-182">När du uppdaterar till den här versionen av operativsystemet bör apparna fungera som förväntat.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="3a6f8-183">Som vi gör med alla HoloLens OS-versioner har vi dessutom publicerat FFU-avbildningen till [Microsoft Download Center.](https://aka.ms/hololensdownload/10.0.17763.380)</span><span class="sxs-lookup"><span data-stu-id="3a6f8-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="3a6f8-184">Om du inte vill göra uppdateringen har vi släppt en ny version av Microsoft Store UWP-appen från och med 3/29.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="3a6f8-185">När du har den uppdaterade versionen av Store:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="3a6f8-186">Öppna Store och bekräfta att den läses in.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="3a6f8-187">Använd bloom-gesten för att öppna menyn.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="3a6f8-188">Försök att öppna tidigare brutna appar.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="3a6f8-189">Om det fortfarande inte går att startas trycker du på och håller ned ikonen för den brutna appen och väljer avinstallera.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="3a6f8-190">Installera om dessa appar från Store.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="3a6f8-191">Om enheten fortfarande inte kan läsa in appar kan du läsa in en version av .NET Native Framework och Runtime separat via download center genom att följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="3a6f8-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="3a6f8-192">Ladda ned [zip-filen](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) från Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="3a6f8-193">När du packar upp produceras två filer.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="3a6f8-194">Microsoft .NET.Native.Runtime.1.7.appx och Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="3a6f8-195">Kontrollera att enheten är upplåst från utveckling.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="3a6f8-196">Om du inte har gjort det tidigare kan du läsa [Använda Windows Enhetsportalen](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-196">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="3a6f8-197">Sedan vill du komma in i Windows Enhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="3a6f8-198">Vår rekommendation är att göra detta via USB och det gör du genom att http://127.0.0.1:10080 skriva i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="3a6f8-199">När du har Windows Enhetsportalen måste du "läsa in" de två filerna som du laddade ned.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="3a6f8-200">Om du vill göra det måste du gå nedåt i det vänstra sidofältet tills du kommer **till avsnittet Appar** och välja **Appar.**</span><span class="sxs-lookup"><span data-stu-id="3a6f8-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="3a6f8-201">Sedan visas en skärm som liknar nedanstående.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="3a6f8-202">Du vill gå till avsnittet Installera app och **bläddra till** den plats där du uppackade de två APPX-filerna.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="3a6f8-203">Du kan bara göra en i taget, så när du har valt den första klickar du på "Kör" under avsnittet Distribuera.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="3a6f8-204">Gör sedan detta för den andra APPX-filen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-204">Then do this for the second APPX file.</span></span>

   ![Windows Enhetsportalen till Installera Side-Loaded app](images/20190322-DevicePortal.png)

1. <span data-ttu-id="3a6f8-206">Nu tror vi att dina program bör börja fungera igen och att du även kan komma till Store.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="3a6f8-207">I vissa fall är det nödvändigt att köra det ytterligare steget för att starta 3D-visningsprogram innan berörda appar startas.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="3a6f8-208">Vi uppskattar ditt tålamod eftersom vi har gått igenom processen för att lösa problemet och vi ser fram emot att fortsätta arbeta med vår community för att skapa Mixed Reality upplevelser.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="3a6f8-209">Enhetsuppdatering</span><span class="sxs-lookup"><span data-stu-id="3a6f8-209">Device Update</span></span>

- <span data-ttu-id="3a6f8-210">30 sekunder efter en ny uppdatering kan gränssnittet försvinna en gång.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="3a6f8-211">Utför **bloom-gesten** för att återuppta sessionen.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="3a6f8-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a6f8-212">Visual Studio</span></span>

- <span data-ttu-id="3a6f8-213">Se [Installera verktygen för](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) den senaste versionen av Visual Studio som rekommenderas för HoloLens-utveckling.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-213">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="3a6f8-214">När du distribuerar en app Visual Studio till HoloLens kan du se felet: Den begärda åtgärden kan inte utföras på en fil med ett **användarmappat avsnitt öppet. (Undantag från HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="3a6f8-215">Om det händer kan du försöka igen så lyckas distributionen vanligtvis.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="3a6f8-216">API</span><span class="sxs-lookup"><span data-stu-id="3a6f8-216">API</span></span>

- <span data-ttu-id="3a6f8-217">Om programmet anger [fokuspunkten bakom](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) användaren eller det normala till camera.forward visas inte hologram i Inspelning av mixad verklighet foton eller videor.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-217">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="3a6f8-218">Om program aktivt ställer in fokuspunkten [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) tills den här buggen har åtgärdats bör de se till att planet normal ställs in motsatt kamera framåt (till exempel normal = -camera.forward).</span><span class="sxs-lookup"><span data-stu-id="3a6f8-218">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="3a6f8-219">Trådlös Xbox-styrenhet</span><span class="sxs-lookup"><span data-stu-id="3a6f8-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="3a6f8-220">Xbox Wireless Controller S måste uppdateras innan den kan användas med HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="3a6f8-221">Kontrollera att du [är uppdaterad innan](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) du försöker koppla kontrollanten till en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="3a6f8-222">Om du startar om HoloLens när den trådlösa Xbox-styrenheten är ansluten återansluter inte styrenheten automatiskt till HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="3a6f8-223">Guideknappen blinkar långsamt tills styrenheten stänger av efter 3 minuter.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="3a6f8-224">Om du vill återansluta kontrollanten omedelbart stänger du av styrenheten genom att hålla ned guideknappen tills lampan stängs av.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="3a6f8-225">När du ansluter styrenheten igen återansluter den till HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="3a6f8-226">Om hololens aktiveras i vänteläge när den trådlösa Xbox-styrenheten är ansluten kommer alla indata på styrenheten att väcka HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="3a6f8-227">Du kan förhindra detta genom att stänga av kontrollanten när du är klar med att använda den.</span><span class="sxs-lookup"><span data-stu-id="3a6f8-227">You can prevent this by powering off your controller when you are done using it.</span></span>

