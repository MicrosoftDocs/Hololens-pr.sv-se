---
title: Bidra med instruktioner
description: Lär dig hur du bidrar till HoloLens-dokument på docs.microsoft.com plattformen med GitHub-flavored Markdown.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378745"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="972d8-103">Bidra till HoloLens-dokumentationen</span><span class="sxs-lookup"><span data-stu-id="972d8-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="972d8-104">Välkommen till [HoloLens-dokumentationen!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="972d8-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="972d8-105">Alla artiklar som du skapar eller redigerar i den här **lagringsplatsen kommer att vara synliga för allmänheten.**</span><span class="sxs-lookup"><span data-stu-id="972d8-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="972d8-106">HoloLens-dokument visas på docs.microsoft.com plattformen som använder Markdown med GitHub-smak med Markdig-funktioner.</span><span class="sxs-lookup"><span data-stu-id="972d8-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="972d8-107">Det innehåll som du redigerar på den här lagringsplatsen formateras till formaterade sidor som visas på https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="972d8-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="972d8-108">Den här sidan beskriver de grundläggande stegen och riktlinjerna för att bidra och länkar till Grunderna i Markdown.</span><span class="sxs-lookup"><span data-stu-id="972d8-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="972d8-109">Tack för ditt bidrag!</span><span class="sxs-lookup"><span data-stu-id="972d8-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="972d8-110">Tillgängliga lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="972d8-110">Available repos</span></span>

| <span data-ttu-id="972d8-111">Namn på lagringsplats</span><span class="sxs-lookup"><span data-stu-id="972d8-111">Repository name</span></span> | <span data-ttu-id="972d8-112">URL</span><span class="sxs-lookup"><span data-stu-id="972d8-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="972d8-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="972d8-113">HoloLens</span></span> | [<span data-ttu-id="972d8-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="972d8-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="972d8-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="972d8-115">Mixed Reality</span></span> | [<span data-ttu-id="972d8-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="972d8-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="972d8-117">GUIDE för VR-entusiaster</span><span class="sxs-lookup"><span data-stu-id="972d8-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="972d8-118">MicrosoftDocs/mixed-reality/entusiastguide</span><span class="sxs-lookup"><span data-stu-id="972d8-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="972d8-119">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="972d8-119">Before you start</span></span>

<span data-ttu-id="972d8-120">Om du inte redan har ett måste du skapa ett [GitHub-konto.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="972d8-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="972d8-121">Om du är anställd på Microsoft länkar du ditt GitHub-konto till ditt Microsoft-alias på [Microsoft Open Source-portalen.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="972d8-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="972d8-122">Gå med **i organisationerna "Microsoft"** **och "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="972d8-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="972d8-123">När du ställer in ditt GitHub-konto rekommenderar vi även följande säkerhetsåtgärder:</span><span class="sxs-lookup"><span data-stu-id="972d8-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="972d8-124">Skapa ett [starkt lösenord för ditt GitHub-konto](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="972d8-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="972d8-125">Aktivera [tvåfaktorautentisering](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="972d8-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="972d8-126">Spara dina [återställningskoder](https://github.com/settings/auth/recovery-codes) på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="972d8-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="972d8-127">Uppdatera dina [offentliga profilinställningar](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="972d8-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="972d8-128">Ange ditt namn och överväg att ange Din *offentliga e-postadress* *till Visa inte min e-postadress.*</span><span class="sxs-lookup"><span data-stu-id="972d8-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="972d8-129">Vi rekommenderar att du laddar upp en profilbild eftersom en miniatyrbild visas på dokumentsidor som du bidrar till.</span><span class="sxs-lookup"><span data-stu-id="972d8-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="972d8-130">Om du planerar att använda kommandoraden bör du överväga att konfigurera [Git Autentiseringshanteraren för Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="972d8-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="972d8-131">På så sätt behöver du inte ange ditt lösenord varje gång du gör ett bidrag.</span><span class="sxs-lookup"><span data-stu-id="972d8-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="972d8-132">Publiceringssystemet är kopplat till GitHub, så de här stegen är viktiga.</span><span class="sxs-lookup"><span data-stu-id="972d8-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="972d8-133">Du visas antingen som författare eller deltagare i varje artikel med ditt GitHub-alias.</span><span class="sxs-lookup"><span data-stu-id="972d8-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="972d8-134">Redigera en befintlig artikel</span><span class="sxs-lookup"><span data-stu-id="972d8-134">Editing an existing article</span></span>

<span data-ttu-id="972d8-135">Använd följande arbetsflöde för att göra uppdateringar *av en befintlig artikel* via GitHub i en webbläsare:</span><span class="sxs-lookup"><span data-stu-id="972d8-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="972d8-136">Gå till den artikel som du vill redigera i mappen "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="972d8-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="972d8-137">Välj redigeringsknappen (pennikonen) längst upp till höger, som automatiskt förgrenar en disponibel gren från "master"-grenen.</span><span class="sxs-lookup"><span data-stu-id="972d8-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Redigera en artikel.](images/editpage.png)
   
3. <span data-ttu-id="972d8-139">Redigera innehållet i artikeln enligt ["Markdown-grunder".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="972d8-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="972d8-140">Uppdatera metadata överst i varje artikel:</span><span class="sxs-lookup"><span data-stu-id="972d8-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="972d8-141">**title**: Sidrubrik som visas på webbläsarfliken när artikeln visas.</span><span class="sxs-lookup"><span data-stu-id="972d8-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="972d8-142">Sidtitlar används för SEO och indexering, så ändra inte rubriken om det inte behövs (även om detta är mindre viktigt innan dokumentationen blir offentlig).</span><span class="sxs-lookup"><span data-stu-id="972d8-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="972d8-143">**description**: Skriv en kort beskrivning av artikelns innehåll, som förbättrar SEO och identifiering.</span><span class="sxs-lookup"><span data-stu-id="972d8-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="972d8-144">**författare:** Om du är den primära ägaren av sidan lägger du till ditt GitHub-alias här.</span><span class="sxs-lookup"><span data-stu-id="972d8-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="972d8-145">**ms.author:** Om du är den primära ägaren av sidan lägger du till ditt Microsoft-alias här (du behöver inte @microsoft.com , bara aliaset).</span><span class="sxs-lookup"><span data-stu-id="972d8-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="972d8-146">**ms.date:** Uppdatera datumet om du lägger till större innehåll på sidan, men inte för korrigeringar som förtydligande, formatering, grammatik eller stavning.</span><span class="sxs-lookup"><span data-stu-id="972d8-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="972d8-147">**nyckelord:** Nyckelord hjälper till i SEO (sökmotoroptimering).</span><span class="sxs-lookup"><span data-stu-id="972d8-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="972d8-148">Lägg till nyckelord, avgränsade med ett kommatecken och ett blanksteg, som är specifika för din artikel, men inga skiljetecken efter det sista nyckelordet i listan.</span><span class="sxs-lookup"><span data-stu-id="972d8-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="972d8-149">Du behöver inte lägga till globala nyckelord som gäller för alla artiklar, eftersom de hanteras någon annanstans.</span><span class="sxs-lookup"><span data-stu-id="972d8-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="972d8-150">När du har slutfört dina artikelredigeringar rullar du nedåt och väljer **Föreslå filändring.**</span><span class="sxs-lookup"><span data-stu-id="972d8-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="972d8-151">På nästa sida väljer du Skapa **pull-begäran för att** sammanslå den automatiskt skapade grenen till "master".</span><span class="sxs-lookup"><span data-stu-id="972d8-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="972d8-152">Upprepa stegen ovan för nästa artikel som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="972d8-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="972d8-153">Byta namn på eller ta bort en befintlig artikel</span><span class="sxs-lookup"><span data-stu-id="972d8-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="972d8-154">Om ändringen ska byta namn på eller ta bort en befintlig artikel måste du lägga till en omdirigering.</span><span class="sxs-lookup"><span data-stu-id="972d8-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="972d8-155">På så sätt hamnar alla med en länk till den befintliga artikeln fortfarande på rätt plats.</span><span class="sxs-lookup"><span data-stu-id="972d8-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="972d8-156">Omdirigeringar hanteras av .openpublishing.redirection.jspå filen i lagringsplatsens rot.</span><span class="sxs-lookup"><span data-stu-id="972d8-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="972d8-157">Lägg till en omdirigering .openpublishing.redirection.jspå genom att lägga till en post i `redirections` matrisen:</span><span class="sxs-lookup"><span data-stu-id="972d8-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="972d8-158">`source_path`är den relativa sökvägen till den gamla artikeln som du tar bort.</span><span class="sxs-lookup"><span data-stu-id="972d8-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="972d8-159">Se till att sökvägen börjar med `mixed-reality-docs` och slutar med `.md` .</span><span class="sxs-lookup"><span data-stu-id="972d8-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="972d8-160">är `redirect_url` den relativa offentliga URL:en från den gamla artikeln till den nya artikeln.</span><span class="sxs-lookup"><span data-stu-id="972d8-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="972d8-161">Se till att den här **URL:en inte innehåller** `mixed-reality-docs` eller , eftersom den `.md` refererar till den offentliga URL:en och inte sökvägen till lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="972d8-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="972d8-162">Länkning till ett avsnitt i den nya artikeln med `#section` hjälp av tillåts.</span><span class="sxs-lookup"><span data-stu-id="972d8-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="972d8-163">Du kan också använda en absolut sökväg till en annan plats här, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="972d8-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="972d8-164">`redirect_document_id` anger om du vill behålla dokument-ID:t från föregående fil.</span><span class="sxs-lookup"><span data-stu-id="972d8-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="972d8-165">Standardvärdet är `false`.</span><span class="sxs-lookup"><span data-stu-id="972d8-165">The default is `false`.</span></span> <span data-ttu-id="972d8-166">Använd `true` om du vill bevara `ms.documentid` attributvärdet från den omdirigerade artikeln.</span><span class="sxs-lookup"><span data-stu-id="972d8-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="972d8-167">Om du bevarar dokument-ID:t överförs data, till exempel sidvisningar och rangordningar, till målartikeln.</span><span class="sxs-lookup"><span data-stu-id="972d8-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="972d8-168">Gör detta om omdirigeringen främst är ett namnbyte och inte en pekare till en annan artikel som bara täcker en del av samma innehåll.</span><span class="sxs-lookup"><span data-stu-id="972d8-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="972d8-169">Om du lägger till en omdirigering måste du även ta bort den gamla filen.</span><span class="sxs-lookup"><span data-stu-id="972d8-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="972d8-170">Skapa en ny artikel</span><span class="sxs-lookup"><span data-stu-id="972d8-170">Creating a new article</span></span>

<span data-ttu-id="972d8-171">Använd följande arbetsflöde för att *skapa nya artiklar i* dokumentationsdatabasen via GitHub i en webbläsare:</span><span class="sxs-lookup"><span data-stu-id="972d8-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="972d8-172">Skapa en förgrening av "master"-grenen MicrosoftDocs/mixed-reality (med **knappen Förgrena** längst upp till höger).</span><span class="sxs-lookup"><span data-stu-id="972d8-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Förgrena huvudgrenen.](images/forkbranch.png)
   
2. <span data-ttu-id="972d8-174">I mappen "mixed-reality-docs" väljer du **Skapa ny fil** längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="972d8-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="972d8-175">Skapa ett sidnamn för artikeln (använd bindestreck i stället för blanksteg och använd inte skiljetecken eller apostrofer) och lägg till ".md"</span><span class="sxs-lookup"><span data-stu-id="972d8-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Ge den nya sidan ett namn.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="972d8-177">Se till att du skapar den nya artikeln från mappen "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="972d8-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="972d8-178">Du kan bekräfta detta genom att söka efter "/mixed-reality-docs/" på den nya filnamnsraden.</span><span class="sxs-lookup"><span data-stu-id="972d8-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="972d8-179">Längst upp på den nya sidan lägger du till följande metadatablock:</span><span class="sxs-lookup"><span data-stu-id="972d8-179">At the top of your new page, add the following metadata block:</span></span>

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. <span data-ttu-id="972d8-180">Fyll i relevanta metadatafält enligt instruktionerna i [avsnittet ovan.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="972d8-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="972d8-181">Skriva artikelinnehåll med [markdown-grunder.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="972d8-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="972d8-182">Lägg till `## See also` ett avsnitt längst ned i artikeln med länkar till andra relevanta artiklar.</span><span class="sxs-lookup"><span data-stu-id="972d8-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="972d8-183">När du är klar väljer **du Commit new file (Genomför ny fil).**</span><span class="sxs-lookup"><span data-stu-id="972d8-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="972d8-184">Välj **Ny pull-begäran** och sammanslå förgreningens "master"-gren till MicrosoftDocs/mixed-reality "master" (se till att pilen pekar på rätt sätt).</span><span class="sxs-lookup"><span data-stu-id="972d8-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Skapa en pull-begäran från din föring till MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="972d8-186">Grunderna i Markdown</span><span class="sxs-lookup"><span data-stu-id="972d8-186">Markdown basics</span></span>

<span data-ttu-id="972d8-187">Följande resurser hjälper dig att lära dig hur du redigerar dokumentation med hjälp av Markdown-språket:</span><span class="sxs-lookup"><span data-stu-id="972d8-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="972d8-188">Grunderna i Markdown</span><span class="sxs-lookup"><span data-stu-id="972d8-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="972d8-189">Ytterligare resurser för att skriva Markdown för docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="972d8-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="972d8-190">Lägga till tabeller</span><span class="sxs-lookup"><span data-stu-id="972d8-190">Adding tables</span></span>

<span data-ttu-id="972d8-191">På grund av docs.microsoft.com tabeller har de inga kantlinjer eller anpassade format, även om du provar infogade CSS.</span><span class="sxs-lookup"><span data-stu-id="972d8-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="972d8-192">Det verkar fungera under en kort tidsperiod, men så småningom kommer plattformen att ta bort formateringen från tabellen.</span><span class="sxs-lookup"><span data-stu-id="972d8-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="972d8-193">Så planera i förväg och håll dina tabeller enkla.</span><span class="sxs-lookup"><span data-stu-id="972d8-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="972d8-194">[Här är en webbplats som gör Markdown-tabeller enkla.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="972d8-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="972d8-195">[Docs Markdown-tillägget för Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) gör också tabellgenereringen enkel om du [använder Visual Studio Code (se nedan)](#using-visual-studio-code) för att redigera dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="972d8-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="972d8-196">Lägga till bilder</span><span class="sxs-lookup"><span data-stu-id="972d8-196">Adding images</span></span>

<span data-ttu-id="972d8-197">Du måste ladda upp dina bilder till mappen "mixed-reality-docs/images" i lagringsplatsen och sedan referera till dem på rätt sätt i artikeln.</span><span class="sxs-lookup"><span data-stu-id="972d8-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="972d8-198">Bilder visas automatiskt i full storlek, vilket innebär att stora bilder fyller hela artikelns bredd.</span><span class="sxs-lookup"><span data-stu-id="972d8-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="972d8-199">Vi rekommenderar att du förbestämer storlek på dina bilder innan du laddar upp dem.</span><span class="sxs-lookup"><span data-stu-id="972d8-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="972d8-200">Den rekommenderade bredden är mellan 600 och 700 bildpunkter, men du bör ändra storlek uppåt eller nedåt om det är en kompakt skärmbild eller en bråkdel av en skärmbild.</span><span class="sxs-lookup"><span data-stu-id="972d8-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="972d8-201">Du kan bara ladda upp bilder till din förked lagringsplatsen innan du sammanfogar.</span><span class="sxs-lookup"><span data-stu-id="972d8-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="972d8-202">Så om du planerar att lägga till bilder i en artikel måste du använda [Visual Studio Code](#using-visual-studio-code) för att först lägga till bilderna i fördelens mapp "images" eller kontrollera att du har gjort följande i en webbläsare:</span><span class="sxs-lookup"><span data-stu-id="972d8-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="972d8-203">Fördelade lagringsplatsen MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="972d8-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="972d8-204">Redigerade artikeln i din föring.</span><span class="sxs-lookup"><span data-stu-id="972d8-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="972d8-205">Laddade upp bilderna som du refererar till i din artikel till mappen "mixed-reality-docs/images" i din föring.</span><span class="sxs-lookup"><span data-stu-id="972d8-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="972d8-206">Skapade en **pull-begäran** för att sammanslå din förgrening till "master"-grenen MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="972d8-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="972d8-207">Om du vill lära dig att konfigurera en egen fördelade lagringsplatsen följer du anvisningarna för [att skapa en ny artikel.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="972d8-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="972d8-208">Förhandsgranska ditt arbete</span><span class="sxs-lookup"><span data-stu-id="972d8-208">Previewing your work</span></span>

<span data-ttu-id="972d8-209">När du redigerar i GitHub via en  webbläsare kan du välja fliken Förhandsgranska längst upp på sidan för att förhandsgranska ditt arbete innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="972d8-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="972d8-210">Förhandsversionen av dina ändringar på review.docs.microsoft.com är endast tillgänglig för Microsoft-anställda</span><span class="sxs-lookup"><span data-stu-id="972d8-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="972d8-211">Microsoft-anställda: När dina bidrag har slagits samman till "master"-grenen kan du granska innehållet innan det blir offentligt på https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="972d8-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="972d8-212">Hitta din artikel med hjälp av innehållsförteckningen i den vänstra kolumnen.</span><span class="sxs-lookup"><span data-stu-id="972d8-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="972d8-213">Redigera i webbläsaren jämfört med att redigera med en skrivbordsklient</span><span class="sxs-lookup"><span data-stu-id="972d8-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="972d8-214">Redigering i webbläsaren är det enklaste sättet att göra snabba ändringar, men det finns några nackdelar:</span><span class="sxs-lookup"><span data-stu-id="972d8-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="972d8-215">Du får ingen stavningskontroll.</span><span class="sxs-lookup"><span data-stu-id="972d8-215">You don't get spell-check.</span></span>
- <span data-ttu-id="972d8-216">Du får ingen smartlänkning till andra artiklar (du måste skriva artikelns filnamn manuellt).</span><span class="sxs-lookup"><span data-stu-id="972d8-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="972d8-217">Det kan vara besvärligt att ladda upp och referera till bilder.</span><span class="sxs-lookup"><span data-stu-id="972d8-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="972d8-218">Om du inte vill hantera de här problemen kan du använda en skrivbordsklient som [Visual Studio Code](https://code.visualstudio.com/) med några användbara [tillägg när](#useful-extensions) du bidrar.</span><span class="sxs-lookup"><span data-stu-id="972d8-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="972d8-219">Använda Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="972d8-219">Using Visual Studio Code</span></span>

<span data-ttu-id="972d8-220">Av de orsaker som [anges ovan](#editing-in-the-browser-vs-editing-with-a-desktop-client)kanske du föredrar att använda en skrivbordsklient för att redigera dokumentation i stället för en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="972d8-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="972d8-221">Vi rekommenderar att [du använder Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="972d8-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="972d8-222">Installation</span><span class="sxs-lookup"><span data-stu-id="972d8-222">Setup</span></span>

<span data-ttu-id="972d8-223">Följ de här stegen för att konfigurera Visual Studio Code så att det fungerar med den här lagringsplatsen:</span><span class="sxs-lookup"><span data-stu-id="972d8-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="972d8-224">I en webbläsare:</span><span class="sxs-lookup"><span data-stu-id="972d8-224">In a web browser:</span></span>
    1. <span data-ttu-id="972d8-225">Installera [Git för din dator.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="972d8-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="972d8-226">Installera [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="972d8-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="972d8-227">[Förk MicrosoftDocs/mixed-reality](#creating-a-new-article) om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="972d8-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="972d8-228">I din föring väljer du **Klona eller laddar ned** och kopierar URL:en.</span><span class="sxs-lookup"><span data-stu-id="972d8-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="972d8-229">Skapa en lokal klon av din förk i Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="972d8-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="972d8-230">I menyn **Visa** väljer du **Kommandopalett.**</span><span class="sxs-lookup"><span data-stu-id="972d8-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="972d8-231">Skriv "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="972d8-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="972d8-232">Klistra in den URL som du kopierade.</span><span class="sxs-lookup"><span data-stu-id="972d8-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="972d8-233">Välj var klonen ska sparas på datorn.</span><span class="sxs-lookup"><span data-stu-id="972d8-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="972d8-234">Välj **Öppna lagringsplatsen** i popup-menyn.</span><span class="sxs-lookup"><span data-stu-id="972d8-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="972d8-235">Redigera dokumentation</span><span class="sxs-lookup"><span data-stu-id="972d8-235">Editing documentation</span></span>

<span data-ttu-id="972d8-236">Använd följande arbetsflöde för att göra ändringar i dokumentationen med Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="972d8-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="972d8-237">All vägledning för [att redigera](#editing-an-existing-article) [och](#creating-a-new-article) skapa artiklar och grunderna för att redigera [Markdown](#markdown-basics)från ovan gäller även när du Visual Studio kod.</span><span class="sxs-lookup"><span data-stu-id="972d8-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="972d8-238">Kontrollera att din klonade förk är uppdaterad med den officiella lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="972d8-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="972d8-239">I en webbläsare skapar du en pull-begäran för att synkronisera de senaste ändringarna från andra deltagare i MicrosoftDocs/mixed-reality "master" till din föring (se till att pilen pekar åt rätt håll).</span><span class="sxs-lookup"><span data-stu-id="972d8-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synkronisera ändringar från MicrosoftDocs/mixed-reality till din föring](images/sync-repos.png)
      
   2. <span data-ttu-id="972d8-241">I Visual Studio Code väljer du synkroniseringsknappen för att synkronisera din nyligen uppdaterade föring till den lokala klonen.</span><span class="sxs-lookup"><span data-stu-id="972d8-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Klicka på bild med synkroniseringsknappen](images/sync-clone.png)
      
2. <span data-ttu-id="972d8-243">Skapa eller redigera artiklar i din klonade lagringsplatsen med Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="972d8-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="972d8-244">Redigera en eller flera artiklar (lägg till bilder i mappen "images" om det behövs).</span><span class="sxs-lookup"><span data-stu-id="972d8-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="972d8-245">**Spara** ändringarna i **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="972d8-245">**Save** changes in **Explorer**.</span></span>
      
      ![Välj "Spara alla" i Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="972d8-247">**Genomför alla** ändringar i **källkontrollen** (skriv commit message när du uppmanas till det).</span><span class="sxs-lookup"><span data-stu-id="972d8-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Välj "Genomför alla" i Källkontroll](images/source-control-commit.png)
      
   4. <span data-ttu-id="972d8-249">Välj **synkroniseringsknappen** för att synkronisera dina ändringar tillbaka till ursprunget (din föring på GitHub).</span><span class="sxs-lookup"><span data-stu-id="972d8-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Klicka på synkroniseringsknappen](images/sync-back.png)
      
3. <span data-ttu-id="972d8-251">I en webbläsare skapar du en pull-begäran för att synkronisera nya ändringar i din föring tillbaka till MicrosoftDocs/mixed-reality "master" (se till att pilen pekar på rätt sätt).</span><span class="sxs-lookup"><span data-stu-id="972d8-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Skapa en pull-begäran från din föring till MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="972d8-253">Användbara tillägg</span><span class="sxs-lookup"><span data-stu-id="972d8-253">Useful extensions</span></span>

<span data-ttu-id="972d8-254">Följande tillägg Visual Studio Code är användbara när du redigerar dokumentationen:</span><span class="sxs-lookup"><span data-stu-id="972d8-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="972d8-255">[Docs Markdown-tillägg för Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – Använd **Alt + M för** att öppna en meny med redigeringsalternativ för dokument som:</span><span class="sxs-lookup"><span data-stu-id="972d8-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="972d8-256">Sök efter och referera till bilder som du har laddat upp.</span><span class="sxs-lookup"><span data-stu-id="972d8-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="972d8-257">Lägg till formatering som listor, tabeller och dokumentspecifika anrop som `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="972d8-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="972d8-258">Sök efter och referera till interna länkar och bokmärken (länkar till specifika avsnitt på en sida).</span><span class="sxs-lookup"><span data-stu-id="972d8-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="972d8-259">Formateringsfel är markerade (hovra med musen över felet om du vill veta mer).</span><span class="sxs-lookup"><span data-stu-id="972d8-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="972d8-260">[Stavningskontroll i kod –](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) felstavade ord kommer att understrukits. högerklicka på ett felstavat ord för att ändra det eller spara det i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="972d8-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
