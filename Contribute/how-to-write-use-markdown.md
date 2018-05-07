---
title: A Markdown használata Docs-tartalmak írásához
description: Ez a cikk alapvető információkat és tájékoztatást nyújt a docs.microsoft.com-cikkekben használt Markdown jelölőnyelvről.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 07/13/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 96d00abc052c3b23ca62201dccdbe590a927e72d
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="b90c4-103">A Markdown használata Docs-tartalmak írásához</span><span class="sxs-lookup"><span data-stu-id="b90c4-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="b90c4-104">A docs.microsoft.com-cikkek a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="b90c4-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="b90c4-105">Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="b90c4-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="b90c4-106">Mivel a Docs-tartalmak a GitHubon vannak tárolva, azokhoz használható a Markdown [GitHub-stílusú Markdown (GFM)](https://help.github.com/categories/writing-on-github/) nevű bővítése, amely további funkciókat biztosít a gyakori formázási igényekhez.</span><span class="sxs-lookup"><span data-stu-id="b90c4-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="b90c4-107">Ezen kívül az Open Publishing Services (OPS) a DocFX-stílusú Markdownt (DFM) implementálja.</span><span class="sxs-lookup"><span data-stu-id="b90c4-107">Additionally, Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="b90c4-108">A DFM nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM), és további funkciókkal támogatja a Docs specifikus szolgáltatásainak használatát.</span><span class="sxs-lookup"><span data-stu-id="b90c4-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="b90c4-109">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="b90c4-109">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="b90c4-110">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="b90c4-110">Headings</span></span>

<span data-ttu-id="b90c4-111">Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="b90c4-111">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="b90c4-112">Félkövér és dőlt szöveg</span><span class="sxs-lookup"><span data-stu-id="b90c4-112">Bold and italic text</span></span>

<span data-ttu-id="b90c4-113">A **félkövérként** formázandó szöveget zárja dupla csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="b90c4-113">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="b90c4-114">A *dőltként* formázandó szöveget zárja egyszeres csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="b90c4-114">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="b90c4-115">A ***félkövérként és dőltként*** is formázandó szöveget zárja háromszoros csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="b90c4-115">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="b90c4-116">Listák</span><span class="sxs-lookup"><span data-stu-id="b90c4-116">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="b90c4-117">Rendezetlen listák</span><span class="sxs-lookup"><span data-stu-id="b90c4-117">Unordered list</span></span>

<span data-ttu-id="b90c4-118">Rendezetlen vagy listajeles listákat csillagokkal vagy kötőjelekkel formázhat.</span><span class="sxs-lookup"><span data-stu-id="b90c4-118">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="b90c4-119">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-119">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="b90c4-120">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-120">will be rendered as:</span></span>

- <span data-ttu-id="b90c4-121">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-121">List item 1</span></span>
- <span data-ttu-id="b90c4-122">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-122">List item 2</span></span>
- <span data-ttu-id="b90c4-123">3. listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-123">List item 3</span></span>

<span data-ttu-id="b90c4-124">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="b90c4-124">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="b90c4-125">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-125">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="b90c4-126">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-126">will be rendered as:</span></span>

- <span data-ttu-id="b90c4-127">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-127">List item 1</span></span>
  - <span data-ttu-id="b90c4-128">A listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-128">List item A</span></span>
  - <span data-ttu-id="b90c4-129">B listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-129">List item B</span></span>
- <span data-ttu-id="b90c4-130">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="b90c4-130">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="b90c4-131">Rendezett lista</span><span class="sxs-lookup"><span data-stu-id="b90c4-131">Ordered list</span></span>

<span data-ttu-id="b90c4-132">Rendezett vagy lépéseket ismertető listákat a megfelelő számok használatával formázhat.</span><span class="sxs-lookup"><span data-stu-id="b90c4-132">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="b90c4-133">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-133">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="b90c4-134">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-134">will be rendered as:</span></span>

1. <span data-ttu-id="b90c4-135">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-135">First instruction</span></span>
2. <span data-ttu-id="b90c4-136">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-136">Second instruction</span></span>
3. <span data-ttu-id="b90c4-137">Harmadik utasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-137">Third instruction</span></span>

<span data-ttu-id="b90c4-138">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="b90c4-138">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="b90c4-139">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-139">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="b90c4-140">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-140">will be rendered as:</span></span>

1. <span data-ttu-id="b90c4-141">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-141">First instruction</span></span>
    1. <span data-ttu-id="b90c4-142">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-142">Sub-instruction</span></span>
    2. <span data-ttu-id="b90c4-143">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-143">Sub-instruction</span></span>
2. <span data-ttu-id="b90c4-144">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-144">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="b90c4-145">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="b90c4-145">Tables</span></span>

<span data-ttu-id="b90c4-146">A táblázatok nem szerepelnek a Markdown alapspecifikációjában, de a GFM-ben támogatottak.</span><span class="sxs-lookup"><span data-stu-id="b90c4-146">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="b90c4-147">Táblázatokat a függőleges vonal (|) és a kötőjel (-) karakterekkel hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="b90c4-147">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="b90c4-148">A kötőjelekkel hozhatja létre az egyes oszlopok fejléceit, a függőleges vonalakkal pedig az oszlopokat választja el egymástól.</span><span class="sxs-lookup"><span data-stu-id="b90c4-148">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="b90c4-149">A táblázat elé szúrjon be egy üres sort, hogy az megfelelően jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="b90c4-149">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="b90c4-150">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-150">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="b90c4-151">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-151">will be rendered as:</span></span>

| <span data-ttu-id="b90c4-152">Így</span><span class="sxs-lookup"><span data-stu-id="b90c4-152">Fun</span></span>                  | <span data-ttu-id="b90c4-153">Néznek ki a</span><span class="sxs-lookup"><span data-stu-id="b90c4-153">With</span></span>                 | <span data-ttu-id="b90c4-154">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="b90c4-154">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="b90c4-155">balra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="b90c4-155">left-aligned column</span></span>  | <span data-ttu-id="b90c4-156">jobbra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="b90c4-156">right-aligned column</span></span> | <span data-ttu-id="b90c4-157">középre igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="b90c4-157">centered column</span></span> |
| <span data-ttu-id="b90c4-158">$100</span><span class="sxs-lookup"><span data-stu-id="b90c4-158">$100</span></span>                 | <span data-ttu-id="b90c4-159">$100</span><span class="sxs-lookup"><span data-stu-id="b90c4-159">$100</span></span>                 | <span data-ttu-id="b90c4-160">$100</span><span class="sxs-lookup"><span data-stu-id="b90c4-160">$100</span></span>            |
| <span data-ttu-id="b90c4-161">$10</span><span class="sxs-lookup"><span data-stu-id="b90c4-161">$10</span></span>                  | <span data-ttu-id="b90c4-162">$10</span><span class="sxs-lookup"><span data-stu-id="b90c4-162">$10</span></span>                  | <span data-ttu-id="b90c4-163">$10</span><span class="sxs-lookup"><span data-stu-id="b90c4-163">$10</span></span>             |
| <span data-ttu-id="b90c4-164">$1</span><span class="sxs-lookup"><span data-stu-id="b90c4-164">$1</span></span>                   | <span data-ttu-id="b90c4-165">$1</span><span class="sxs-lookup"><span data-stu-id="b90c4-165">$1</span></span>                   | <span data-ttu-id="b90c4-166">$1</span><span class="sxs-lookup"><span data-stu-id="b90c4-166">$1</span></span>              |

<span data-ttu-id="b90c4-167">További információ a táblázatok létrehozásáról:</span><span class="sxs-lookup"><span data-stu-id="b90c4-167">For more information on creating tables, see:</span></span>

- <span data-ttu-id="b90c4-168">A DFM széles táblázatok formázását segítő [táblázatbehatárolási funkcióját](#table-wrapping) ismertető szakasz</span><span class="sxs-lookup"><span data-stu-id="b90c4-168">The DFM [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="b90c4-169">Az [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/) (Információk rendszerezése táblázatokkal) című GitHub-cikk</span><span class="sxs-lookup"><span data-stu-id="b90c4-169">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="b90c4-170">A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás</span><span class="sxs-lookup"><span data-stu-id="b90c4-170">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- <span data-ttu-id="b90c4-171">[Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet)</span><span class="sxs-lookup"><span data-stu-id="b90c4-171">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)</span></span>
- [<span data-ttu-id="b90c4-172">Michel Fortin: Markdown Extra</span><span class="sxs-lookup"><span data-stu-id="b90c4-172">Michel Fortin's Markdown Extra</span></span>](https://michelf.ca/projects/php-markdown/extra/#table)
- [<span data-ttu-id="b90c4-173">HTML-táblázatok konvertálása Markdown-formátumra</span><span class="sxs-lookup"><span data-stu-id="b90c4-173">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="b90c4-174">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="b90c4-174">Links</span></span>

<span data-ttu-id="b90c4-175">A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:</span><span class="sxs-lookup"><span data-stu-id="b90c4-175">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="b90c4-176">További információ a hivatkozások használatáról:</span><span class="sxs-lookup"><span data-stu-id="b90c4-176">For more information on linking, see:</span></span>

- <span data-ttu-id="b90c4-177">A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.</span><span class="sxs-lookup"><span data-stu-id="b90c4-177">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="b90c4-178">A DFM által biztosított hivatkozási szintaxisról a jelen útmutató [Links](how-to-write-links.md) (Hivatkozások) című oldalán található részletesebb információ.</span><span class="sxs-lookup"><span data-stu-id="b90c4-178">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that DFM provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="b90c4-179">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="b90c4-179">Code snippets</span></span>

<span data-ttu-id="b90c4-180">A Markdown támogatja a kódrészletek mondaton belüli, illetve mondatok közötti, „elkülönített” blokkban való elhelyezését is.</span><span class="sxs-lookup"><span data-stu-id="b90c4-180">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="b90c4-181">További részletek:</span><span class="sxs-lookup"><span data-stu-id="b90c4-181">For details, see:</span></span>

- [<span data-ttu-id="b90c4-182">A Markdown natív kódrészlet-támogatása</span><span class="sxs-lookup"><span data-stu-id="b90c4-182">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="b90c4-183">GFM-támogatás kód elkülönítéséhez és szintaxiskiemeléshez</span><span class="sxs-lookup"><span data-stu-id="b90c4-183">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="b90c4-184">Az elkülönített kódblokkokban egyszerűen kiemelhető a kódrészletek szintaxisa.</span><span class="sxs-lookup"><span data-stu-id="b90c4-184">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="b90c4-185">Az elkülönített kódblokkok általános formátuma a következő:</span><span class="sxs-lookup"><span data-stu-id="b90c4-185">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="b90c4-186">A három kezdő „\`” karakter utáni alias határozza meg a használni kívánt szintaxiskiemelést.</span><span class="sxs-lookup"><span data-stu-id="b90c4-186">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="b90c4-187">Az alábbi lista felsorolja a Docs-tartalmakban gyakran használt programozási nyelveket és a hozzájuk tartozó címkét:</span><span class="sxs-lookup"><span data-stu-id="b90c4-187">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="b90c4-188">Ezekhez a nyelvekhez a rendszer támogatja a névformázást, és legtöbbjük esetében szintaxiskiemelést is nyújt.</span><span class="sxs-lookup"><span data-stu-id="b90c4-188">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="b90c4-189">Név</span><span class="sxs-lookup"><span data-stu-id="b90c4-189">Name</span></span>|<span data-ttu-id="b90c4-190">Markdown-címke</span><span class="sxs-lookup"><span data-stu-id="b90c4-190">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="b90c4-191">.NET-konzol</span><span class="sxs-lookup"><span data-stu-id="b90c4-191">.NET Console</span></span>|<span data-ttu-id="b90c4-192">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="b90c4-192">dotnetcli</span></span>|
|<span data-ttu-id="b90c4-193">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="b90c4-193">ASP.NET (C#)</span></span>|<span data-ttu-id="b90c4-194">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="b90c4-194">aspx-csharp</span></span>|
|<span data-ttu-id="b90c4-195">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="b90c4-195">ASP.NET (VB)</span></span>|<span data-ttu-id="b90c4-196">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="b90c4-196">aspx-vb</span></span>|
|<span data-ttu-id="b90c4-197">AzCopy</span><span class="sxs-lookup"><span data-stu-id="b90c4-197">AzCopy</span></span>|<span data-ttu-id="b90c4-198">azcopy</span><span class="sxs-lookup"><span data-stu-id="b90c4-198">azcopy</span></span>|
|<span data-ttu-id="b90c4-199">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="b90c4-199">Azure CLI</span></span>|<span data-ttu-id="b90c4-200">azurecli</span><span class="sxs-lookup"><span data-stu-id="b90c4-200">azurecli</span></span>|
|<span data-ttu-id="b90c4-201">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b90c4-201">Azure PowerShell</span></span>|<span data-ttu-id="b90c4-202">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="b90c4-202">azurepowershell</span></span>|
|<span data-ttu-id="b90c4-203">C++</span><span class="sxs-lookup"><span data-stu-id="b90c4-203">C++</span></span>|<span data-ttu-id="b90c4-204">cpp</span><span class="sxs-lookup"><span data-stu-id="b90c4-204">cpp</span></span>|
|<span data-ttu-id="b90c4-205">C++/CX</span><span class="sxs-lookup"><span data-stu-id="b90c4-205">C++/CX</span></span>|<span data-ttu-id="b90c4-206">cppcx</span><span class="sxs-lookup"><span data-stu-id="b90c4-206">cppcx</span></span>|
|<span data-ttu-id="b90c4-207">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="b90c4-207">C++/WinRT</span></span>|<span data-ttu-id="b90c4-208">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="b90c4-208">cppwinrt</span></span>|
|<span data-ttu-id="b90c4-209">C#</span><span class="sxs-lookup"><span data-stu-id="b90c4-209">C#</span></span>|<span data-ttu-id="b90c4-210">csharp</span><span class="sxs-lookup"><span data-stu-id="b90c4-210">csharp</span></span>|
|<span data-ttu-id="b90c4-211">CSHTML</span><span class="sxs-lookup"><span data-stu-id="b90c4-211">CSHTML</span></span>|<span data-ttu-id="b90c4-212">cshtml</span><span class="sxs-lookup"><span data-stu-id="b90c4-212">cshtml</span></span>|
|<span data-ttu-id="b90c4-213">DAX</span><span class="sxs-lookup"><span data-stu-id="b90c4-213">DAX</span></span>|<span data-ttu-id="b90c4-214">dax</span><span class="sxs-lookup"><span data-stu-id="b90c4-214">dax</span></span>|
|<span data-ttu-id="b90c4-215">F#</span><span class="sxs-lookup"><span data-stu-id="b90c4-215">F#</span></span>|<span data-ttu-id="b90c4-216">fsharp</span><span class="sxs-lookup"><span data-stu-id="b90c4-216">fsharp</span></span>|
|<span data-ttu-id="b90c4-217">Go</span><span class="sxs-lookup"><span data-stu-id="b90c4-217">Go</span></span>|<span data-ttu-id="b90c4-218">go</span><span class="sxs-lookup"><span data-stu-id="b90c4-218">go</span></span>|
|<span data-ttu-id="b90c4-219">HTML</span><span class="sxs-lookup"><span data-stu-id="b90c4-219">HTML</span></span>|<span data-ttu-id="b90c4-220">html</span><span class="sxs-lookup"><span data-stu-id="b90c4-220">html</span></span>|
|<span data-ttu-id="b90c4-221">HTTP</span><span class="sxs-lookup"><span data-stu-id="b90c4-221">HTTP</span></span>|<span data-ttu-id="b90c4-222">http</span><span class="sxs-lookup"><span data-stu-id="b90c4-222">http</span></span>|
|<span data-ttu-id="b90c4-223">Java</span><span class="sxs-lookup"><span data-stu-id="b90c4-223">Java</span></span>|<span data-ttu-id="b90c4-224">java</span><span class="sxs-lookup"><span data-stu-id="b90c4-224">java</span></span>|
|<span data-ttu-id="b90c4-225">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b90c4-225">JavaScript</span></span>|<span data-ttu-id="b90c4-226">javascript</span><span class="sxs-lookup"><span data-stu-id="b90c4-226">javascript</span></span>|
|<span data-ttu-id="b90c4-227">JSON</span><span class="sxs-lookup"><span data-stu-id="b90c4-227">JSON</span></span>|<span data-ttu-id="b90c4-228">json</span><span class="sxs-lookup"><span data-stu-id="b90c4-228">json</span></span>|
|<span data-ttu-id="b90c4-229">Markdown</span><span class="sxs-lookup"><span data-stu-id="b90c4-229">Markdown</span></span>|<span data-ttu-id="b90c4-230">md</span><span class="sxs-lookup"><span data-stu-id="b90c4-230">md</span></span>|
|<span data-ttu-id="b90c4-231">NodeJS</span><span class="sxs-lookup"><span data-stu-id="b90c4-231">NodeJS</span></span>|<span data-ttu-id="b90c4-232">nodejs</span><span class="sxs-lookup"><span data-stu-id="b90c4-232">nodejs</span></span>|
|<span data-ttu-id="b90c4-233">Objective-C</span><span class="sxs-lookup"><span data-stu-id="b90c4-233">Objective-C</span></span>|<span data-ttu-id="b90c4-234">objc</span><span class="sxs-lookup"><span data-stu-id="b90c4-234">objc</span></span>|
|<span data-ttu-id="b90c4-235">OData</span><span class="sxs-lookup"><span data-stu-id="b90c4-235">OData</span></span>|<span data-ttu-id="b90c4-236">odata</span><span class="sxs-lookup"><span data-stu-id="b90c4-236">odata</span></span>|
|<span data-ttu-id="b90c4-237">PHP</span><span class="sxs-lookup"><span data-stu-id="b90c4-237">PHP</span></span>|<span data-ttu-id="b90c4-238">php</span><span class="sxs-lookup"><span data-stu-id="b90c4-238">php</span></span>|
|<span data-ttu-id="b90c4-239">PowerApps-képlet</span><span class="sxs-lookup"><span data-stu-id="b90c4-239">Power Apps Formula</span></span>|<span data-ttu-id="b90c4-240">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="b90c4-240">powerappsfl</span></span>|
|<span data-ttu-id="b90c4-241">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b90c4-241">PowerShell</span></span>|<span data-ttu-id="b90c4-242">powershell</span><span class="sxs-lookup"><span data-stu-id="b90c4-242">powershell</span></span>|
|<span data-ttu-id="b90c4-243">Python</span><span class="sxs-lookup"><span data-stu-id="b90c4-243">Python</span></span>|<span data-ttu-id="b90c4-244">python</span><span class="sxs-lookup"><span data-stu-id="b90c4-244">python</span></span>|
|<span data-ttu-id="b90c4-245">Q#</span><span class="sxs-lookup"><span data-stu-id="b90c4-245">Q#</span></span>|<span data-ttu-id="b90c4-246">qsharp</span><span class="sxs-lookup"><span data-stu-id="b90c4-246">qsharp</span></span>|
|<span data-ttu-id="b90c4-247">Ruby</span><span class="sxs-lookup"><span data-stu-id="b90c4-247">Ruby</span></span>|<span data-ttu-id="b90c4-248">ruby</span><span class="sxs-lookup"><span data-stu-id="b90c4-248">ruby</span></span>|
|<span data-ttu-id="b90c4-249">SQL</span><span class="sxs-lookup"><span data-stu-id="b90c4-249">SQL</span></span>|<span data-ttu-id="b90c4-250">sql</span><span class="sxs-lookup"><span data-stu-id="b90c4-250">sql</span></span>|
|<span data-ttu-id="b90c4-251">Swift</span><span class="sxs-lookup"><span data-stu-id="b90c4-251">Swift</span></span>|<span data-ttu-id="b90c4-252">swift</span><span class="sxs-lookup"><span data-stu-id="b90c4-252">swift</span></span>|
|<span data-ttu-id="b90c4-253">TypeScript</span><span class="sxs-lookup"><span data-stu-id="b90c4-253">TypeScript</span></span>|<span data-ttu-id="b90c4-254">typescript</span><span class="sxs-lookup"><span data-stu-id="b90c4-254">typescript</span></span>|
|<span data-ttu-id="b90c4-255">VB</span><span class="sxs-lookup"><span data-stu-id="b90c4-255">VB</span></span>|<span data-ttu-id="b90c4-256">vb</span><span class="sxs-lookup"><span data-stu-id="b90c4-256">vb</span></span>|
|<span data-ttu-id="b90c4-257">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="b90c4-257">VSTS CLI</span></span>|<span data-ttu-id="b90c4-258">vstscli</span><span class="sxs-lookup"><span data-stu-id="b90c4-258">vstscli</span></span>|
|<span data-ttu-id="b90c4-259">XAML</span><span class="sxs-lookup"><span data-stu-id="b90c4-259">XAML</span></span>|<span data-ttu-id="b90c4-260">xaml</span><span class="sxs-lookup"><span data-stu-id="b90c4-260">xaml</span></span>|
|<span data-ttu-id="b90c4-261">XML</span><span class="sxs-lookup"><span data-stu-id="b90c4-261">XML</span></span>|<span data-ttu-id="b90c4-262">xml</span><span class="sxs-lookup"><span data-stu-id="b90c4-262">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="b90c4-263">C\#-példa:</span><span class="sxs-lookup"><span data-stu-id="b90c4-263">Example: C\#</span></span>

<span data-ttu-id="b90c4-264">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="b90c4-264">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="b90c4-265">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="b90c4-265">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="b90c4-266">SQL-példa:</span><span class="sxs-lookup"><span data-stu-id="b90c4-266">Example: SQL</span></span>

<span data-ttu-id="b90c4-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="b90c4-267">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="b90c4-268">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="b90c4-268">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="b90c4-269">Egyedi OPS Markdown-bővítmények</span><span class="sxs-lookup"><span data-stu-id="b90c4-269">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="b90c4-270">Az Open Publishing Services (OPS) a DocFX-stílusú Markdownt (DFM) implementálja, amely nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM).</span><span class="sxs-lookup"><span data-stu-id="b90c4-270">Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM), which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="b90c4-271">A DFM néhány funkciót biztosít a Markdown-bővítmények révén.</span><span class="sxs-lookup"><span data-stu-id="b90c4-271">DFM adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="b90c4-272">A jelen útmutatóban az OPS teljes szerzői útmutatójának kiválasztott témakörei szerepelnek referenciaként.</span><span class="sxs-lookup"><span data-stu-id="b90c4-272">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="b90c4-273">(Például lásd a „DFM- és Markdown-bővítmények” és a „Kódrészletek” címeket a tartalomjegyzékben.)</span><span class="sxs-lookup"><span data-stu-id="b90c4-273">(For example, see "DFM and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="b90c4-274">A Docs-cikkek formázásának nagy része, például a bekezdések, a hivatkozások, a listák és a fejlécek a GFM használatával készülnek.</span><span class="sxs-lookup"><span data-stu-id="b90c4-274">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="b90c4-275">A kifinomultabb formázáshoz a cikkekben többek között az alábbi DFM-funkciók használhatók:</span><span class="sxs-lookup"><span data-stu-id="b90c4-275">For richer formatting, articles can use DFM features such as:</span></span>

- <span data-ttu-id="b90c4-276">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="b90c4-276">Note blocks</span></span>
- <span data-ttu-id="b90c4-277">Beágyazások</span><span class="sxs-lookup"><span data-stu-id="b90c4-277">Includes</span></span>
- <span data-ttu-id="b90c4-278">Választómezők</span><span class="sxs-lookup"><span data-stu-id="b90c4-278">Selectors</span></span>
- <span data-ttu-id="b90c4-279">Beágyazott videók</span><span class="sxs-lookup"><span data-stu-id="b90c4-279">Embedded videos</span></span>
- <span data-ttu-id="b90c4-280">Kódrészletek és -minták</span><span class="sxs-lookup"><span data-stu-id="b90c4-280">Code snippets/samples</span></span>

<span data-ttu-id="b90c4-281">A teljes listát a tartalomjegyzék „DFM- és Markdown-bővítmények” és „Kódrészletek” fejezetcíme alatt találhatja.</span><span class="sxs-lookup"><span data-stu-id="b90c4-281">For the complete list, refer to "DFM and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="b90c4-282">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="b90c4-282">Note blocks</span></span>

<span data-ttu-id="b90c4-283">A megjegyzésblokkok 4 típusa közül választhat, hogy felhívja a figyelmet adott tartalomra:</span><span class="sxs-lookup"><span data-stu-id="b90c4-283">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="b90c4-284">MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="b90c4-284">NOTE</span></span>
- <span data-ttu-id="b90c4-285">FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="b90c4-285">WARNING</span></span>
- <span data-ttu-id="b90c4-286">TIPP</span><span class="sxs-lookup"><span data-stu-id="b90c4-286">TIP</span></span>
- <span data-ttu-id="b90c4-287">FONTOS</span><span class="sxs-lookup"><span data-stu-id="b90c4-287">IMPORTANT</span></span>

<span data-ttu-id="b90c4-288">Általánosságban elmondható, hogy a megjegyzésblokkokat ritkán szabad használni, mert megtörhetik a cikk folytonosságát.</span><span class="sxs-lookup"><span data-stu-id="b90c4-288">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="b90c4-289">Bár a kódblokkok, képek, listák és hivatkozások használata a megjegyzésblokkokon belül is támogatott, törekedjen egyszerű és könnyen érthető megjegyzésblokkok írására.</span><span class="sxs-lookup"><span data-stu-id="b90c4-289">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="b90c4-290">Beágyazások</span><span class="sxs-lookup"><span data-stu-id="b90c4-290">Includes</span></span>

<span data-ttu-id="b90c4-291">Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a DFM fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra.</span><span class="sxs-lookup"><span data-stu-id="b90c4-291">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the DFM file include feature.</span></span> <span data-ttu-id="b90c4-292">Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben.</span><span class="sxs-lookup"><span data-stu-id="b90c4-292">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="b90c4-293">A tartalmak újrafelhasználását háromféle beágyazás segíti:</span><span class="sxs-lookup"><span data-stu-id="b90c4-293">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="b90c4-294">Soron belüli: egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="b90c4-294">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="b90c4-295">Blokk: egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="b90c4-295">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="b90c4-296">Képek: ez a képek normál beillesztésének megvalósítása a Docsban.</span><span class="sxs-lookup"><span data-stu-id="b90c4-296">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="b90c4-297">A soron belüli és blokk típusú beágyazás egy egyszerű Markdown- (.md) fájlt használ.</span><span class="sxs-lookup"><span data-stu-id="b90c4-297">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="b90c4-298">Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="b90c4-298">It can contain any valid Markdown.</span></span> <span data-ttu-id="b90c4-299">Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="b90c4-299">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="b90c4-300">A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.</span><span class="sxs-lookup"><span data-stu-id="b90c4-300">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="b90c4-301">Néhány követelmény és megfontolandó szempont a beágyazásokhoz:</span><span class="sxs-lookup"><span data-stu-id="b90c4-301">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="b90c4-302">Bármikor használhat beágyazást, amikor ugyanazt a szöveget több cikkben is szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="b90c4-302">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="b90c4-303">A blokk típusú beágyazás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott.</span><span class="sxs-lookup"><span data-stu-id="b90c4-303">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="b90c4-304">Ne használja egy mondatnál kisebb terjedelmű szöveghez.</span><span class="sxs-lookup"><span data-stu-id="b90c4-304">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="b90c4-305">A beágyazott tartalmak a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok DFM-bővítményeket igényelnek.</span><span class="sxs-lookup"><span data-stu-id="b90c4-305">Includes won't be rendered in the GitHub rendered view of your article, because they rely on DFM extensions.</span></span> <span data-ttu-id="b90c4-306">Azok csak közzététel után jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="b90c4-306">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="b90c4-307">Ügyeljen rá, hogy a beágyazott szöveg teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó cikknek a beágyazást megelőző vagy azt követő szövegétől.</span><span class="sxs-lookup"><span data-stu-id="b90c4-307">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="b90c4-308">Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan szövegrészlet jön létre a cikkben, amely megtöri a honosított felületet.</span><span class="sxs-lookup"><span data-stu-id="b90c4-308">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="b90c4-309">Ne alkalmazzon beágyazást más beágyazásokon belül.</span><span class="sxs-lookup"><span data-stu-id="b90c4-309">Don't embed includes within other includes.</span></span> <span data-ttu-id="b90c4-310">Ez nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="b90c4-310">They are not supported.</span></span>
- <span data-ttu-id="b90c4-311">A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa.</span><span class="sxs-lookup"><span data-stu-id="b90c4-311">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="b90c4-312">A médiamappa gyökere nem tartalmazhat képfájlokat.</span><span class="sxs-lookup"><span data-stu-id="b90c4-312">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="b90c4-313">Ha a beágyazás nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="b90c4-313">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="b90c4-314">A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között.</span><span class="sxs-lookup"><span data-stu-id="b90c4-314">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="b90c4-315">Minden egyes beágyazáshoz és cikkhez használjon külön fájlt, egyedi névvel.</span><span class="sxs-lookup"><span data-stu-id="b90c4-315">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="b90c4-316">A médiafájlt tárolja a beágyazáshoz társított médiamappában.</span><span class="sxs-lookup"><span data-stu-id="b90c4-316">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="b90c4-317">A cikkek ne tartalmazzanak kizárólag egy beágyazást.</span><span class="sxs-lookup"><span data-stu-id="b90c4-317">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="b90c4-318">A beágyazások a cikk többi része tartalmának kiegészítésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="b90c4-318">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="b90c4-319">Választómezők</span><span class="sxs-lookup"><span data-stu-id="b90c4-319">Selectors</span></span>

<span data-ttu-id="b90c4-320">Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg a különböző technológiák és platformok különbségeinek figyelembe vételével.</span><span class="sxs-lookup"><span data-stu-id="b90c4-320">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="b90c4-321">Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb.</span><span class="sxs-lookup"><span data-stu-id="b90c4-321">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="b90c4-322">A DFM-ben jelenleg kétféle választómező van, az egyszerű és a többszintű.</span><span class="sxs-lookup"><span data-stu-id="b90c4-322">There are currently two different types of selectors in DFM, a single selector and a multi-selector.</span></span>

<span data-ttu-id="b90c4-323">Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni,</span><span class="sxs-lookup"><span data-stu-id="b90c4-323">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="b90c4-324">majd erre hivatkozni az összes olyan témakörben, amely ugyanazt a választómezőt használja.</span><span class="sxs-lookup"><span data-stu-id="b90c4-324">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="b90c4-325">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="b90c4-325">Code snippets</span></span>

<span data-ttu-id="b90c4-326">A DFM a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="b90c4-326">DFM supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="b90c4-327">A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:</span><span class="sxs-lookup"><span data-stu-id="b90c4-327">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="b90c4-328">Központosított kódminták vagy -részletek beágyazása külső tárházból.</span><span class="sxs-lookup"><span data-stu-id="b90c4-328">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="b90c4-329">Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b90c4-329">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="b90c4-330">Tipikus hibák és hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="b90c4-330">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="b90c4-331">Helyettesítő szöveg</span><span class="sxs-lookup"><span data-stu-id="b90c4-331">Alt text</span></span>

<span data-ttu-id="b90c4-332">Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen.</span><span class="sxs-lookup"><span data-stu-id="b90c4-332">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="b90c4-333">Például a következő szöveg helyett:</span><span class="sxs-lookup"><span data-stu-id="b90c4-333">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="b90c4-334">Az aláhúzás jeleket így jelenítheti meg:</span><span class="sxs-lookup"><span data-stu-id="b90c4-334">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="b90c4-335">Aposztrófok és idézőjelek</span><span class="sxs-lookup"><span data-stu-id="b90c4-335">Apostrophes and quotation marks</span></span>

<span data-ttu-id="b90c4-336">Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="b90c4-336">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="b90c4-337">Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni,</span><span class="sxs-lookup"><span data-stu-id="b90c4-337">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="b90c4-338">különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="b90c4-338">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="b90c4-339">Ezen írásjelek „intelligens” verzióinak kódolásai a következők:</span><span class="sxs-lookup"><span data-stu-id="b90c4-339">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="b90c4-340">Bal oldali (nyitó) idézőjel: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="b90c4-340">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="b90c4-341">Jobb oldali (záró) idézőjel: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="b90c4-341">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="b90c4-342">Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="b90c4-342">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="b90c4-343">Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="b90c4-343">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="b90c4-344">Csúcsos zárójelek</span><span class="sxs-lookup"><span data-stu-id="b90c4-344">Angle brackets</span></span>

<span data-ttu-id="b90c4-345">Ha csúcsos zárójeleket használ a fájl szövegében (nem a kódban), például egy helyőrző jelölésére, akkor a csúcsos zárójeleket manuálisan kell kódolnia.</span><span class="sxs-lookup"><span data-stu-id="b90c4-345">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="b90c4-346">Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.</span><span class="sxs-lookup"><span data-stu-id="b90c4-346">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="b90c4-347">A `<script name>` kódolása például a következő: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="b90c4-347">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="b90c4-348">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b90c4-348">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="b90c4-349">Markdown-források</span><span class="sxs-lookup"><span data-stu-id="b90c4-349">Markdown resources</span></span>

- <span data-ttu-id="b90c4-350">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)</span><span class="sxs-lookup"><span data-stu-id="b90c4-350">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="b90c4-351">Markdown-segédlet a Docshoz</span><span class="sxs-lookup"><span data-stu-id="b90c4-351">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="b90c4-352">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)</span><span class="sxs-lookup"><span data-stu-id="b90c4-352">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
