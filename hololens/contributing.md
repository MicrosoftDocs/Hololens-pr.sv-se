---
title: Bidra med instruktioner
description: Lär dig hur du bidrar till HoloLens dokument på docs.microsoft.com-plattformen med hjälp GitHub markdown med olika varianter.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427560"
---
# <a name="contributing-to-the-hololens-documentation"></a>Bidra till HoloLens dokumentationen

Välkommen till [HoloLens dokumentation!](https://github.com/MicrosoftDocs/Hololens) Alla artiklar som du skapar eller redigerar i den här **lagringsplatsen kommer att vara synliga för allmänheten.** 

HoloLens dokument visas på docs.microsoft.com plattformen, som använder GitHub markdown med Markdig-funktioner. Det innehåll som du redigerar på den här lagringsplatsen formateras till sized pages som visas på /hololens.

Den här sidan beskriver de grundläggande stegen och riktlinjerna för att bidra och länkar till Grunderna i Markdown. Tack för ditt bidrag!

## <a name="available-repos"></a>Tillgängliga lagringsplatsen

| Namn på lagringsplats | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-reality](/windows/mixed-reality) |
| GUIDE för VR-entusiaster | [MicrosoftDocs/mixed-reality/entusiastguide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Innan du börjar

Om du inte redan har ett måste du skapa ett [GitHub konto](https://github.com/join).

>[!NOTE]
>Om du är anställd på Microsoft länkar du ditt GitHub till ditt Microsoft-alias på [Microsoft Open Source-portalen.](https://repos.opensource.microsoft.com/) Gå med **i organisationerna "Microsoft"** **och "MicrosoftDocs".**

När du GitHub ditt konto rekommenderar vi även följande säkerhetsåtgärder:
- Skapa ett [starkt lösenord för ditt GitHub konto](https://github.com/settings/admin).
- Aktivera [tvåfaktorautentisering](https://github.com/settings/two_factor_authentication/configure).
- Spara dina [återställningskoder](https://github.com/settings/auth/recovery-codes) på en säker plats.
- Uppdatera dina [offentliga profilinställningar](https://github.com/settings/profile).
   - Ange ditt namn och överväg att ange Din *offentliga e-postadress* *till Visa inte min e-postadress.*
   - Vi rekommenderar att du laddar upp en profilbild eftersom en miniatyrbild visas på dokumentsidor som du bidrar till.
- Om du planerar att använda kommandoraden bör du överväga att konfigurera [Git Autentiseringshanteraren för Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). På så sätt behöver du inte ange ditt lösenord varje gång du gör ett bidrag.

Publiceringssystemet är kopplat till GitHub, så de här stegen är viktiga. Du visas antingen som författare eller deltagare i varje artikel med hjälp av ditt GitHub alias.

## <a name="editing-an-existing-article"></a>Redigera en befintlig artikel

Använd följande arbetsflöde för att göra uppdateringar *av en befintlig* artikel via GitHub i en webbläsare:

1. Gå till den artikel som du vill redigera i mappen "mixed-reality-docs".

2. Välj redigeringsknappen (pennikonen) längst upp till höger.

   ![Redigera en artikel.](images/editpage.png)

   Detta förgrenar automatiskt en disponibel gren från _standardgrenen_ Master .

   > [!NOTE]
   > Den här artikeln innehåller referenser _till master_, en term som Microsoft inte längre använder. När termen tas bort från programvaran tar vi bort den från den här artikeln.
   
3. Redigera innehållet i artikeln enligt [grunderna i Markdown.](#markdown-basics)

4. Uppdatera metadata överst i varje artikel:

   * **title**: Sidrubrik som visas på webbläsarfliken när artikeln visas. Sidtitlar används för SEO och indexering, så ändra inte rubriken om det inte behövs (även om detta är mindre viktigt innan dokumentationen blir offentlig).
   * **description**: Skriv en kort beskrivning av artikelns innehåll, som förbättrar SEO och identifiering.
   * **författare:** Om du är den primära ägaren av sidan lägger du till GitHub alias här.
   * **ms.author:** Om du är den primära ägaren av sidan lägger du till ditt Microsoft-alias här (du behöver @microsoft.com inte , bara aliaset).
   * **ms.date:** Uppdatera datumet om du lägger till större innehåll på sidan, men inte för korrigeringar som förtydligande, formatering, grammatik eller stavning.
   * **nyckelord:** Nyckelord hjälper till i SEO (sökmotoroptimering). Lägg till nyckelord, avgränsade med ett kommatecken och ett blanksteg, som är specifika för din artikel, men inga skiljetecken efter det sista nyckelordet i listan. Du behöver inte lägga till globala nyckelord som gäller för alla artiklar, eftersom de hanteras någon annanstans. 
   
5. När du har slutfört dina artikelredigeringar rullar du nedåt och väljer **Föreslå filändring.**

6. På nästa sida väljer du Skapa **pull-begäran för att** sammanslå den automatiskt skapade grenen till standardgrenen, _master_.

7. Upprepa stegen ovan för nästa artikel som du vill redigera.

## <a name="renaming-or-deleting-an-existing-article"></a>Byta namn på eller ta bort en befintlig artikel

Om ändringen ska byta namn på eller ta bort en befintlig artikel måste du lägga till en omdirigering. På så sätt hamnar alla med en länk till den befintliga artikeln fortfarande på rätt plats. Omdirigeringar hanteras av .openpublishing.redirection.jspå filen i lagringsplatsens rot.

Lägg till en omdirigering .openpublishing.redirection.jspå genom att lägga till en post i `redirections` matrisen:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`är den relativa sökvägen till den gamla artikeln som du tar bort. Se till att sökvägen börjar med `mixed-reality-docs` och slutar med `.md` .

- är `redirect_url` den relativa offentliga URL:en från den gamla artikeln till den nya artikeln. Se till att den här **URL:en inte innehåller** `mixed-reality-docs` eller , eftersom den `.md` refererar till den offentliga URL:en och inte sökvägen till lagringsplatsen. Länkning till ett avsnitt i den nya artikeln med `#section` hjälp av tillåts. Du kan också använda en absolut sökväg till en annan plats här, om det behövs.

- `redirect_document_id` anger om du vill behålla dokument-ID:t från föregående fil. Standardvärdet är `false`. Använd `true` om du vill bevara `ms.documentid` attributvärdet från den omdirigerade artikeln. Om du bevarar dokument-ID:t överförs data, till exempel sidvisningar och rangordningar, till målartikeln. Gör detta om omdirigeringen främst är ett namnbyte och inte en pekare till en annan artikel som bara täcker en del av samma innehåll.

Om du lägger till en omdirigering måste du även ta bort den gamla filen.

## <a name="creating-a-new-article"></a>Skapa en ny artikel

Använd följande arbetsflöde för att *skapa nya artiklar* i dokumentationsdatabasen via GitHub i en webbläsare:

1. Skapa en förgrening från standardgrenen _Master_, för MicrosoftDocs/mixed-reality med knappen **Förgrena** längst upp till höger.

   ![Förgrena standardgrenen, som för närvarande heter "master".](images/forkbranch.png)

   > [!NOTE]
   > Den här artikeln innehåller referenser _till master_, en term som Microsoft inte längre använder. När termen tas bort från programvaran tar vi bort den från den här artikeln.
   
2. I mappen "mixed-reality-docs" väljer du **Skapa ny fil** längst upp till höger.

3. Skapa ett sidnamn för artikeln (använd bindestreck i stället för blanksteg och använd inte skiljetecken eller apostrofer) och lägg till ".md"

   ![Ge den nya sidan ett namn.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Se till att du skapar den nya artikeln från mappen "mixed-reality-docs". Du kan bekräfta detta genom att söka efter "/mixed-reality-docs/" på den nya filnamnsraden.

4. Längst upp på den nya sidan lägger du till följande metadatablock:

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

5. Fyll i de relevanta metadatafälten enligt beskrivningen tidigare i [Redigera en befintlig artikel](#editing-an-existing-article).

6. Skriva artikelinnehåll med [markdown-grunder.](#markdown-basics)

7. Lägg till `## See also` ett avsnitt längst ned i artikeln med länkar till andra relevanta artiklar.

8. När du är klar väljer **du Commit new file (Genomför ny fil).**

9. Välj **Ny pull-begäran** och sammanslå din förgrenings _huvudgren_ till MicrosoftDocs/mixed-reality  master (se till att pilen pekar på rätt mål).

   ![Skapa en pull-begäran från din föring till MicrosoftDocs/mixed-reality.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Grunderna i Markdown

Följande resurser hjälper dig att lära dig hur du redigerar dokumentation med hjälp av Markdown-språket:

- [Grunderna i Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Ytterligare resurser för att skriva Markdown för docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Lägga till tabeller

På grund av docs.microsoft.com tabeller har de inte kantlinjer eller anpassade format, även om du provar infogade CSS. Det verkar fungera under en kort tidsperiod, men så småningom kommer plattformen att ta bort formateringen från tabellen. Så planera i förväg och håll dina tabeller enkla. Här är en webbplats som gör Markdown-tabeller enkla: [Tables Generator]]( https://www.tablesgenerator.com/markdown_tables) .

[Docs Markdown-tillägget för Visual Studio Code](/teamblog/docs-extension) gör också tabellgenereringen enkel om du använder [Visual Studio Code (se nedan)](#using-visual-studio-code) för att redigera dokumentationen.

### <a name="adding-images"></a>Lägga till bilder

Du måste ladda upp dina bilder till mappen "mixed-reality-docs/images" i lagringsplatsen och sedan referera till dem på rätt sätt i artikeln. Bilder visas automatiskt i full storlek, vilket innebär att stora bilder fyller hela artikelns bredd. Vi rekommenderar att du förbestämer storlek på dina bilder innan du laddar upp dem. Den rekommenderade bredden är mellan 600 och 700 bildpunkter, men du bör ändra storlek uppåt eller nedåt om det är en kompakt skärmbild eller en bråkdel av en skärmbild.

>[!IMPORTANT]
>Du kan bara ladda upp bilder till din förked lagringsplatsen innan du sammanfogar. Så om du planerar att lägga till bilder i en artikel måste du använda [Visual Studio Code](#using-visual-studio-code) för att lägga till bilderna i din förings mapp "images" först eller kontrollera att du har gjort följande i en webbläsare:
>
>1. Fördelade lagringsplatsen MicrosoftDocs/mixed-reality.
>2. Redigerade artikeln i din föring.
>3. Laddade upp de bilder som du refererar till i din artikel till mappen "mixed-reality-docs/images" i din föring.
>4. Skapade en **pull-begäran** för att sammanslå din  förgrening till huvudgrenen MicrosoftDocs/mixed-reality.
>
>Om du vill lära dig hur du ställer in en egen förked lagringsplatsen följer du anvisningarna för [att skapa en ny artikel.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Förhandsgranska ditt arbete

När du redigerar GitHub via en webbläsare kan  du välja fliken Förhandsgranska längst upp på sidan för att förhandsgranska ditt arbete innan du gör det. 

>[!NOTE]
>Förhandsversionen av ändringarna på review.docs.microsoft.com är endast tillgänglig för Microsoft-anställda

Microsoft-anställda: När dina bidrag har sammanfogats med standardgrenen _master_ kan du granska innehållet innan det blir offentligt på </hololens?branch=master>. Hitta din artikel med hjälp av innehållsförteckningen i den vänstra kolumnen.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Redigera i webbläsaren jämfört med att redigera med en skrivbordsklient

Redigering i webbläsaren är det enklaste sättet att göra snabba ändringar, men det finns några nackdelar:

- Du får inte stavningskontroll.
- Du får ingen smart länkning till andra artiklar (du måste ange artikelns filnamn manuellt).
- Det kan vara besvärligt att ladda upp och referera till bilder.

Om du inte vill hantera dessa problem kan du använda en skrivbordsklient som [Visual Studio Code](https://code.visualstudio.com/) med några användbara [tillägg när](#useful-extensions) du bidrar.

## <a name="using-visual-studio-code"></a>Använda Visual Studio Code

Av de orsaker som [anges ovan](#editing-in-the-browser-vs-editing-with-a-desktop-client)kanske du föredrar att använda en skrivbordsklient för att redigera dokumentation i stället för en webbläsare. Vi rekommenderar att [du använder Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Installation

Följ de här stegen för att konfigurera Visual Studio Code så att det fungerar med den här lagringsplatsen:

1. I en webbläsare:
    1. Installera [Git för din dator](https://git-scm.com/downloads).
    2. Installera [Visual Studio Code](https://code.visualstudio.com/).
    3. [Förk MicrosoftDocs/mixed-reality](#creating-a-new-article) om du inte redan har gjort det.
    4. Välj Klona eller ladda **ned och kopiera URL:en** i din förk.
2. Skapa en lokal klon av din föring i Visual Studio Code:
    1. I menyn **Visa** väljer du **Kommandopalett.**
    2. Skriv "Git: Clone".
    3. Klistra in den URL som du kopierade.
    4. Välj var klonen ska sparas på datorn.
    5. Välj **Öppna lagringsplatsen** i popup-menyn.

### <a name="editing-documentation"></a>Redigera dokumentation

Använd följande arbetsflöde för att göra ändringar i dokumentationen med Visual Studio Code:

>[!NOTE]
>All vägledning för [att redigera](#editing-an-existing-article) [och](#creating-a-new-article) skapa artiklar och grunderna för att redigera [Markdown](#markdown-basics)från ovan gäller även när du Visual Studio kod.

1. Kontrollera att din klonade föring är uppdaterad med den officiella lagringsplatsen.

   1. I en webbläsare skapar du en pull-begäran för att synkronisera de senaste ändringarna från andra deltagare i standardgrenen MicrosoftDocs/mixed-reality, _master_, till din förgrening (se till att pilen pekar på rätt mål).
      
      ![Synkronisera ändringar från MicrosoftDocs/mixed-reality till din föring.](images/sync-repos.png)
      
   2. I Visual Studio Code väljer du synkroniseringsknappen för att synkronisera din nyligen uppdaterade föring till den lokala klonen.
      
      ![Klicka på bild med synkroniseringsknappen.](images/sync-clone.png)
      
2. Skapa eller redigera artiklar i din klonade lagringsplatsen med Visual Studio Kod.

   1. Redigera en eller flera artiklar (lägg till bilder i mappen "images" om det behövs).
   
   2. **Spara** ändringarna i **Explorer.**
      
      ![Välj "Spara alla" i Explorer](images/explorer-save.png)
      
   3. **Genomför alla ändringar** i **Källkontroll** (skriv commit message när du uppmanas att göra det).
   
      ![Välj "Genomför alla" i Källkontroll](images/source-control-commit.png)
      
   4. Välj **synkroniseringsknappen** för att synkronisera ändringarna tillbaka till ursprunget (din föring på GitHub).
      
      ![Klicka på synkroniseringsknappen.](images/sync-back.png)
      
3. I en webbläsare skapar du en pull-begäran för att synkronisera nya ändringar  i din föring tillbaka till MicrosoftDocs/mixed-reality master (se till att pilen pekar på rätt mål).

   ![Skapa en pull-begäran från din föring till MicrosoftDocs/mixed-reality.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Användbara tillägg

Följande kodtillägg Visual Studio användbara när du redigerar dokumentationen:

- [Docs Markdown-tillägg för Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – Använd **Alt + M för** att öppna en meny med redigeringsalternativ för dokument som:
   - Sök och referera till bilder som du har laddat upp.
   - Lägg till formatering som listor, tabeller och dokumentspecifika anrop som `>[!NOTE]` .
   - Sök och referera till interna länkar och bokmärken (länkar till specifika avsnitt på en sida).
   - Formateringsfel är markerade (hovra med musen över felet om du vill veta mer).
- [Stavningskontroll för kod –](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) felstavade ord kommer att understrukits. högerklicka på ett felstavat ord för att ändra det eller spara det i ordlistan.
