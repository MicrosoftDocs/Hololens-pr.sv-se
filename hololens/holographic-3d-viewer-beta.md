---
title: Använda 3D-visningsprogram Beta på HoloLens (första generationen)
description: Beskriver de typer av filer och funktioner som 3D-visningsprogram Beta på HoloLens (1:a gen) stöder samt hur du använder och felsöker appen.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380018"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="ac005-103">Använda 3D-visningsprogram Beta på HoloLens (första generationen)</span><span class="sxs-lookup"><span data-stu-id="ac005-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="ac005-104">3D-visningsprogram Beta kan du visa 3D-modeller på HoloLens (första generationen).</span><span class="sxs-lookup"><span data-stu-id="ac005-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="ac005-105">Du kan öppna  och visa .fbx-filer som stöds från Microsoft Edge, OneDrive och andra appar.</span><span class="sxs-lookup"><span data-stu-id="ac005-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="ac005-106">Den här artikeln gäller för den integrerande Unity **3D-visningsprogram Beta-appen,** som stöder .fbx-filer och endast är tillgänglig på HoloLens (första generationen).</span><span class="sxs-lookup"><span data-stu-id="ac005-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="ac005-107">Den förinstallerade **3D-visningsprogram** på HoloLens 2 har stöd för att öppna anpassade 3D-modeller i 3D-modeller i Mixed Reality (mer information finns i Översikt över tillgångskrav. [](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)</span><span class="sxs-lookup"><span data-stu-id="ac005-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ac005-108">Även 3D-visningsprogram Beta kan finnas kvar i Microsoft Store för HoloLens (första generationen), är den inte längre i aktiv utveckling och stöds inte längre.</span><span class="sxs-lookup"><span data-stu-id="ac005-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="ac005-109">Om du har problem med att öppna en 3D-modell i 3D-visningsprogram Beta, eller om vissa funktioner i 3D-modellen inte stöds, kan du gå till [Innehållsspecifikationer som stöds](#supported-content-specifications) nedan.</span><span class="sxs-lookup"><span data-stu-id="ac005-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="ac005-110">Om du vill skapa eller optimera 3D-modeller för användning med 3D-visningsprogram Beta kan du se [Optimera 3D-modeller för 3D-visningsprogram Beta](#optimizing-3d-models-for-3d-viewer-beta) nedan.</span><span class="sxs-lookup"><span data-stu-id="ac005-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="ac005-111">Det finns två sätt att öppna en 3D-modell på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="ac005-112">Mer [information finns i Visa FBX-filer på HoloLens](#viewing-fbx-files-on-hololens) nedan.</span><span class="sxs-lookup"><span data-stu-id="ac005-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="ac005-113">Om du har problem med att läsa de här ämnena kan du läsa [Felsökning](#troubleshooting) nedan.</span><span class="sxs-lookup"><span data-stu-id="ac005-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="ac005-114">Innehållsspecifikationer som stöds</span><span class="sxs-lookup"><span data-stu-id="ac005-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="ac005-115">Filformat</span><span class="sxs-lookup"><span data-stu-id="ac005-115">File format</span></span>

- <span data-ttu-id="ac005-116">FBX-format</span><span class="sxs-lookup"><span data-stu-id="ac005-116">FBX format</span></span>
- <span data-ttu-id="ac005-117">Högsta FBX-version 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="ac005-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="ac005-118">Filstorlek</span><span class="sxs-lookup"><span data-stu-id="ac005-118">File size</span></span>

- <span data-ttu-id="ac005-119">Minst 5 kB</span><span class="sxs-lookup"><span data-stu-id="ac005-119">Minimum 5 KB</span></span>
- <span data-ttu-id="ac005-120">Maximalt 500 MB</span><span class="sxs-lookup"><span data-stu-id="ac005-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="ac005-121">Geometri</span><span class="sxs-lookup"><span data-stu-id="ac005-121">Geometry</span></span>

- <span data-ttu-id="ac005-122">Endast polygonala modeller.</span><span class="sxs-lookup"><span data-stu-id="ac005-122">Polygonal models only.</span></span> <span data-ttu-id="ac005-123">Inga indelningsytor eller NURB</span><span class="sxs-lookup"><span data-stu-id="ac005-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="ac005-124">Högerhänt koordinatsystem</span><span class="sxs-lookup"><span data-stu-id="ac005-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="ac005-125">Shear i transformeringsmatriser stöds inte</span><span class="sxs-lookup"><span data-stu-id="ac005-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="ac005-126">Bakgrunder</span><span class="sxs-lookup"><span data-stu-id="ac005-126">Textures</span></span>

- <span data-ttu-id="ac005-127">Strukturkartor måste bäddas in i FBX-filen</span><span class="sxs-lookup"><span data-stu-id="ac005-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="ac005-128">Bildformat som stöds</span><span class="sxs-lookup"><span data-stu-id="ac005-128">Supported image formats</span></span>
  - <span data-ttu-id="ac005-129">JPEG- och PNG-bilder</span><span class="sxs-lookup"><span data-stu-id="ac005-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="ac005-130">BMP-bilder (24-bitars RGB true-color)</span><span class="sxs-lookup"><span data-stu-id="ac005-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="ac005-131">TGA-bilder (24-bitars RGB och 32-bitars RGBQ true-color)</span><span class="sxs-lookup"><span data-stu-id="ac005-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="ac005-132">Maximal upplösning på 2 048 x 2 048</span><span class="sxs-lookup"><span data-stu-id="ac005-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="ac005-133">Maximalt en mappning, en normal karta och en reflektionskubkarta per nät</span><span class="sxs-lookup"><span data-stu-id="ac005-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="ac005-134">Alfakanal i sporadiska strukturer gör att bildpunkter tas bort om de är lägre än 50 %</span><span class="sxs-lookup"><span data-stu-id="ac005-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="ac005-135">Animering</span><span class="sxs-lookup"><span data-stu-id="ac005-135">Animation</span></span>

- <span data-ttu-id="ac005-136">Animering av skalning/rotation/översättning på enskilda objekt</span><span class="sxs-lookup"><span data-stu-id="ac005-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="ac005-137">Skeletal (trederad) animering med hudning</span><span class="sxs-lookup"><span data-stu-id="ac005-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="ac005-138">Maximalt 4 påverkan per hörn</span><span class="sxs-lookup"><span data-stu-id="ac005-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="ac005-139">Material</span><span class="sxs-lookup"><span data-stu-id="ac005-139">Materials</span></span>

- <span data-ttu-id="ac005-140">Det finns stöd för Material från String och Prems, med justerbara parametrar</span><span class="sxs-lookup"><span data-stu-id="ac005-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="ac005-141">Materialegenskaper som stöds för Properties</span><span class="sxs-lookup"><span data-stu-id="ac005-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="ac005-142">Main Texture (RGB + Alpha Test)</span><span class="sxs-lookup"><span data-stu-id="ac005-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="ac005-143">Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="ac005-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="ac005-144">Omgivande färg (RGB)</span><span class="sxs-lookup"><span data-stu-id="ac005-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="ac005-145">Materialegenskaper som stöds för Prem</span><span class="sxs-lookup"><span data-stu-id="ac005-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="ac005-146">Main Texture (RGB + Alpha Test)</span><span class="sxs-lookup"><span data-stu-id="ac005-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="ac005-147">Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="ac005-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="ac005-148">Omgivande färg (RGB)</span><span class="sxs-lookup"><span data-stu-id="ac005-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="ac005-149">Specular Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="ac005-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="ac005-150">Storhet</span><span class="sxs-lookup"><span data-stu-id="ac005-150">Shininess</span></span>
  - <span data-ttu-id="ac005-151">Reflektionsförmåga</span><span class="sxs-lookup"><span data-stu-id="ac005-151">Reflectivity</span></span>
- <span data-ttu-id="ac005-152">Anpassat material stöds inte</span><span class="sxs-lookup"><span data-stu-id="ac005-152">Custom materials are not supported</span></span>
- <span data-ttu-id="ac005-153">Maximalt ett material per nät</span><span class="sxs-lookup"><span data-stu-id="ac005-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="ac005-154">Högst ett materialskikt</span><span class="sxs-lookup"><span data-stu-id="ac005-154">Maximum of one material layer</span></span>
- <span data-ttu-id="ac005-155">Högst 8 material per fil</span><span class="sxs-lookup"><span data-stu-id="ac005-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="ac005-156">Fil- och modellbegränsningar</span><span class="sxs-lookup"><span data-stu-id="ac005-156">File and model limitations</span></span>

<span data-ttu-id="ac005-157">Det finns hårda gränser för storleken på filer, samt antalet modeller, hörn och nät som kan öppnas samtidigt i 3D-visningsprogram Beta:</span><span class="sxs-lookup"><span data-stu-id="ac005-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="ac005-158">Maximal filstorlek på 500 MB per modell</span><span class="sxs-lookup"><span data-stu-id="ac005-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="ac005-159">Hörn: 600 000 kombinerat på alla öppna modeller</span><span class="sxs-lookup"><span data-stu-id="ac005-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="ac005-160">Nät: 1 600 kombineras på alla öppna modeller</span><span class="sxs-lookup"><span data-stu-id="ac005-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="ac005-161">Högst 40 modeller öppna samtidigt</span><span class="sxs-lookup"><span data-stu-id="ac005-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="ac005-162">Optimera 3D-modeller för 3D-visningsprogram Beta</span><span class="sxs-lookup"><span data-stu-id="ac005-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="ac005-163">Särskilda överväganden</span><span class="sxs-lookup"><span data-stu-id="ac005-163">Special considerations</span></span>

- <span data-ttu-id="ac005-164">Undvik svarta material eller svarta områden i strukturkartor.</span><span class="sxs-lookup"><span data-stu-id="ac005-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="ac005-165">Hologram består av ljus, vilket innebär att HoloLens återger svart (avsaknad av ljus) som transparent.</span><span class="sxs-lookup"><span data-stu-id="ac005-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="ac005-166">Innan du exporterar till FBX från ditt verktyg ska du se till att all geometri är synlig och olåst och att inga skikt som innehåller geometri är avstängda eller mallade.</span><span class="sxs-lookup"><span data-stu-id="ac005-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="ac005-167">Synligheten respekteras inte.</span><span class="sxs-lookup"><span data-stu-id="ac005-167">Visibility is not respected.</span></span>
- <span data-ttu-id="ac005-168">Undvik mycket stora översättningsförskjutningar mellan noder (till exempel 100 000 enheter).</span><span class="sxs-lookup"><span data-stu-id="ac005-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="ac005-169">Detta kan göra att modellen jitter när den flyttas/skalas/roteras.</span><span class="sxs-lookup"><span data-stu-id="ac005-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="ac005-170">Prestandaoptimering</span><span class="sxs-lookup"><span data-stu-id="ac005-170">Performance optimization</span></span>

<span data-ttu-id="ac005-171">Ha prestanda i åtanke när du skapar innehåll och validerar i 3D-visningsprogram Beta-appen på HoloLens under redigeringsprocessen för bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="ac005-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="ac005-172">3D-visningsprogram Beta återger innehåll i realtid och prestanda omfattas av HoloLens maskinvarufunktioner.</span><span class="sxs-lookup"><span data-stu-id="ac005-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="ac005-173">Det finns många variabler i en 3D-modell som kan påverka prestanda.</span><span class="sxs-lookup"><span data-stu-id="ac005-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="ac005-174">3D-visningsprogram Beta visar en varning vid inläsning om det finns fler än 150 000 hörn eller fler än 400 nät.</span><span class="sxs-lookup"><span data-stu-id="ac005-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="ac005-175">Animeringar kan påverka prestanda för andra öppna modeller.</span><span class="sxs-lookup"><span data-stu-id="ac005-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="ac005-176">Det finns också hårda gränser för det totala antalet modeller, hörn och nät som kan öppnas samtidigt i 3D-visningsprogram Beta (se Fil- och [modellbegränsningar).](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="ac005-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="ac005-177">Om 3D-modellen inte fungerar bra på grund av modellens komplexitet bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="ac005-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="ac005-178">Minska antalet polygoner</span><span class="sxs-lookup"><span data-stu-id="ac005-178">Reducing polygon count</span></span>
- <span data-ttu-id="ac005-179">Minska antalet snor i animerad animering</span><span class="sxs-lookup"><span data-stu-id="ac005-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="ac005-180">Undvika självocklusion</span><span class="sxs-lookup"><span data-stu-id="ac005-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="ac005-181">Dubbelsidig rendering stöds i 3D-visningsprogram Beta, även om det är inaktiverat som standard av prestandaskäl.</span><span class="sxs-lookup"><span data-stu-id="ac005-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="ac005-182">Detta kan aktiveras via knappen **Dubbelsidig** på **sidan** Information.</span><span class="sxs-lookup"><span data-stu-id="ac005-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="ac005-183">Undvik behovet av dubbelsidig rendering i ditt innehåll för bästa prestanda.</span><span class="sxs-lookup"><span data-stu-id="ac005-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="ac005-184">Verifiera din 3D-modell</span><span class="sxs-lookup"><span data-stu-id="ac005-184">Validating your 3D model</span></span>

<span data-ttu-id="ac005-185">Verifiera din modell genom att öppna den i 3D-visningsprogram Beta på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="ac005-186">Välj knappen **Information** för att visa modellens egenskaper och varningar om innehåll som inte stöds (om det finns).</span><span class="sxs-lookup"><span data-stu-id="ac005-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="ac005-187">Återgivning av 3D-modeller med verkliga dimensioner</span><span class="sxs-lookup"><span data-stu-id="ac005-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="ac005-188">Som standard visar 3D-visningsprogram Beta 3D-modeller med en bekväm storlek och position i förhållande till användaren.</span><span class="sxs-lookup"><span data-stu-id="ac005-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="ac005-189">Men om det är viktigt att återge en 3D-modell med verkliga mått (till exempel vid utvärdering av modeller i ett rum) kan innehållsskaparen ange en flagga i filens metadata för att förhindra storleksändring av modellen av både programmet och användaren.</span><span class="sxs-lookup"><span data-stu-id="ac005-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="ac005-190">För att förhindra skalning av modellen lägger du till ett booleskt anpassat attribut i alla objekt i scenen med Microsoft_DisableScale och anger det till true.</span><span class="sxs-lookup"><span data-stu-id="ac005-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="ac005-191">3D-visningsprogram Beta respekterar sedan FbxSystemUnit-informationen som ingår i FBX-filen.</span><span class="sxs-lookup"><span data-stu-id="ac005-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="ac005-192">Skala in 3D-visningsprogram Beta är 1 mätare per FBX-enhet.</span><span class="sxs-lookup"><span data-stu-id="ac005-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="ac005-193">Visa FBX-filer på HoloLens</span><span class="sxs-lookup"><span data-stu-id="ac005-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="ac005-194">Öppna en FBX-fil från Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ac005-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="ac005-195">FBX-filer kan öppnas direkt från en webbplats med hjälp Microsoft Edge på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="ac005-196">I Microsoft Edge du till webbsidan som innehåller FBX-filen som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="ac005-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="ac005-197">Välj filen för att ladda ned den.</span><span class="sxs-lookup"><span data-stu-id="ac005-197">Select the file to download it.</span></span>
1. <span data-ttu-id="ac005-198">När nedladdningen är klar väljer du knappen **Öppna** i Microsoft Edge för att öppna filen i 3D-visningsprogram Beta.</span><span class="sxs-lookup"><span data-stu-id="ac005-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="ac005-199">Den nedladdade filen kan nås och öppnas igen senare med hjälp av Nedladdningar i Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ac005-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="ac005-200">Om du vill spara en 3D-modell och säkerställa fortsatt åtkomst laddar du ned filen på datorn och sparar den till ditt OneDrive-konto.</span><span class="sxs-lookup"><span data-stu-id="ac005-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="ac005-201">Filen kan sedan öppnas från OneDrive-appen på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="ac005-202">Vissa webbplatser med nedladdningsbara FBX-modeller tillhandahåller dem i komprimerat ZIP-format.</span><span class="sxs-lookup"><span data-stu-id="ac005-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="ac005-203">3D-visningsprogram Beta kan inte öppna ZIP-filer direkt.</span><span class="sxs-lookup"><span data-stu-id="ac005-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="ac005-204">Använd i stället datorn för att extrahera FBX-filen och spara den på ditt OneDrive-konto.</span><span class="sxs-lookup"><span data-stu-id="ac005-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="ac005-205">Filen kan sedan öppnas från OneDrive-appen på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="ac005-206">Öppna en FBX-fil från OneDrive</span><span class="sxs-lookup"><span data-stu-id="ac005-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="ac005-207">FBX-filer kan öppnas från OneDrive med hjälp av OneDrive-appen på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="ac005-208">Kontrollera att du har installerat OneDrive med Microsoft Store på HoloLens och att du redan har laddat upp FBX-filen till OneDrive på datorn.</span><span class="sxs-lookup"><span data-stu-id="ac005-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="ac005-209">Väl i OneDrive kan FBX-filer öppnas på HoloLens med 3D-visningsprogram Beta på något av två sätt:</span><span class="sxs-lookup"><span data-stu-id="ac005-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="ac005-210">Starta OneDrive på HoloLens och välj FBX-filen för att öppna den i 3D-visningsprogram Beta.</span><span class="sxs-lookup"><span data-stu-id="ac005-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="ac005-211">Starta 3D-visningsprogram Beta, tryck i luften för att visa verktygsfältet och välj **Öppna fil.**</span><span class="sxs-lookup"><span data-stu-id="ac005-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="ac005-212">OneDrive startar så att du kan välja en FBX-fil.</span><span class="sxs-lookup"><span data-stu-id="ac005-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ac005-213">Felsökning</span><span class="sxs-lookup"><span data-stu-id="ac005-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="ac005-214">Jag ser en varning när jag öppnar en 3D-modell</span><span class="sxs-lookup"><span data-stu-id="ac005-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="ac005-215">En varning visas om du försöker öppna en 3D-modell som innehåller funktioner som inte stöds av 3D-visningsprogram Beta, eller om modellen är för komplex och prestanda kan påverkas.</span><span class="sxs-lookup"><span data-stu-id="ac005-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="ac005-216">3D-visningsprogram Beta läser fortfarande in 3D-modellen, men prestanda eller visuell återgivning kan komprometteras.</span><span class="sxs-lookup"><span data-stu-id="ac005-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="ac005-217">Mer information finns i [Innehållsspecifikationer som stöds](#supported-content-specifications) och [Optimera 3D-modeller för 3D-visningsprogram Beta.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="ac005-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="ac005-218">Jag ser en varning och 3D-modellen läses inte in</span><span class="sxs-lookup"><span data-stu-id="ac005-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="ac005-219">Ett felmeddelande visas när 3D-visningsprogram Beta inte kan läsa in en 3D-modell på grund av komplexitet eller filstorlek, eller om FBX-filen är skadad eller ogiltig.</span><span class="sxs-lookup"><span data-stu-id="ac005-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="ac005-220">Du får också ett felmeddelande om du har nått gränsen för det totala antalet modeller, hörn eller nät som kan vara öppna samtidigt.</span><span class="sxs-lookup"><span data-stu-id="ac005-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="ac005-221">Mer information finns i [Innehållsspecifikationer som stöds och](#supported-content-specifications) [Fil- och modellbegränsningar.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="ac005-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="ac005-222">Min 3D-modell läses in, men visas inte som förväntat</span><span class="sxs-lookup"><span data-stu-id="ac005-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="ac005-223">Om din 3D-modell inte ser ut som förväntat i 3D-visningsprogram Beta trycker du i luften för att visa verktygsfältet och väljer sedan **Information.**</span><span class="sxs-lookup"><span data-stu-id="ac005-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="ac005-224">Aspekter av filen som inte stöds av 3D-visningsprogram Beta markeras som varningar.</span><span class="sxs-lookup"><span data-stu-id="ac005-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="ac005-225">Det vanligaste problemet du kan se är att det saknas struktur, troligen eftersom de inte är inbäddade i FBX-filen.</span><span class="sxs-lookup"><span data-stu-id="ac005-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="ac005-226">I det här fallet visas modellen som vit.</span><span class="sxs-lookup"><span data-stu-id="ac005-226">In this case, the model will appear white.</span></span> <span data-ttu-id="ac005-227">Det här problemet kan åtgärdas i skapandeprocessen genom att exportera från ditt skapandeverktyg till FBX med alternativet bädda in struktur valt.</span><span class="sxs-lookup"><span data-stu-id="ac005-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="ac005-228">Mer information finns i [Innehållsspecifikationer som stöds](#supported-content-specifications) och [Optimera 3D-modeller för 3D-visningsprogram Beta.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="ac005-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="ac005-229">Jag upplever att prestandan sjunker när jag visar min 3D-modell</span><span class="sxs-lookup"><span data-stu-id="ac005-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="ac005-230">Prestanda vid inläsning och visning av en 3D-modell kan påverkas av modellens komplexitet, antalet modeller som öppnas samtidigt eller antalet modeller med aktiva animeringar.</span><span class="sxs-lookup"><span data-stu-id="ac005-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="ac005-231">Mer information finns i Optimera [3D-modeller för 3D-visningsprogram beta-](#optimizing-3d-models-for-3d-viewer-beta) och [fil- och modellbegränsningar.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="ac005-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="ac005-232">När jag öppnar en FBX-fil på HoloLens öppnas den inte i 3D-visningsprogram Beta</span><span class="sxs-lookup"><span data-stu-id="ac005-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="ac005-233">3D-visningsprogram Beta associeras automatiskt med filnamnstillägget .fbx när det installeras.</span><span class="sxs-lookup"><span data-stu-id="ac005-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="ac005-234">Om du försöker öppna en FBX-fil och ser en dialogruta som leder dig till Microsoft Store har du för närvarande inte någon app som är associerad med filnamnstillägget .fbx på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="ac005-235">Kontrollera att 3D-visningsprogram Beta är installerat.</span><span class="sxs-lookup"><span data-stu-id="ac005-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="ac005-236">Om den inte är installerad laddar du ned den från Microsoft Store på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="ac005-237">Om 3D-visningsprogram Beta redan är installerat startar du 3D-visningsprogram Beta och försöker sedan öppna filen igen.</span><span class="sxs-lookup"><span data-stu-id="ac005-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="ac005-238">Om problemet kvarstår avinstallerar och installerar du om 3D-visningsprogram Beta.</span><span class="sxs-lookup"><span data-stu-id="ac005-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="ac005-239">Detta associerar filnamnstillägget .fbx med 3D-visningsprogram Beta.</span><span class="sxs-lookup"><span data-stu-id="ac005-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="ac005-240">Om försök att öppna en FBX-fil öppnar en annan app än 3D-visningsprogram Beta, installerades förmodligen den appen efter 3D-visningsprogram Beta och har tagit över associationen med filnamnstillägget .fbx.</span><span class="sxs-lookup"><span data-stu-id="ac005-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="ac005-241">Om du föredrar 3D-visningsprogram Beta ska associeras med filnamnstillägget .fbx avinstallerar du och 3D-visningsprogram Beta.</span><span class="sxs-lookup"><span data-stu-id="ac005-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="ac005-242">Knappen Öppna fil i 3D-visningsprogram Beta startar inte en app</span><span class="sxs-lookup"><span data-stu-id="ac005-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="ac005-243">Knappen **Öppna fil** öppnar appen som är associerad med filväljarfunktionen på HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ac005-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="ac005-244">Om OneDrive är installerat ska **knappen Öppna** fil starta OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ac005-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="ac005-245">Men om det för närvarande inte finns någon app som är associerad med filväljarfunktionen installerad på HoloLens dirigeras du till Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ac005-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="ac005-246">Om knappen **Öppna fil** startar en annan app än OneDrive installerades förmodligen den appen efter OneDrive och har tagit över kopplingen till filväljarfunktionen.</span><span class="sxs-lookup"><span data-stu-id="ac005-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="ac005-247">Om du föredrar att OneDrive startas när du väljer **knappen Öppna fil** i 3D-visningsprogram Beta avinstallerar du och installerar om OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ac005-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="ac005-248">Om knappen **Öppna** fil inte är aktiv är det möjligt att du har nått gränsen för modeller som kan vara öppna i 3D-visningsprogram Beta på en gång.</span><span class="sxs-lookup"><span data-stu-id="ac005-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="ac005-249">Om du har 40 modeller öppna i 3D-visningsprogram Beta måste du stänga några innan du kan öppna ytterligare modeller.</span><span class="sxs-lookup"><span data-stu-id="ac005-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac005-250">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ac005-250">Additional resources</span></span>

- <span data-ttu-id="ac005-251">[Supportforum](http://forums.hololens.com/categories/3d-viewer-beta) – endast för arkivering.</span><span class="sxs-lookup"><span data-stu-id="ac005-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="ac005-252">Det här forumet är inte längre aktivt.</span><span class="sxs-lookup"><span data-stu-id="ac005-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="ac005-253">Meddelanden från tredje part</span><span class="sxs-lookup"><span data-stu-id="ac005-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
