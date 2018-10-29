---
title: A Markdown használata Docs-tartalmak írásához
description: Ez a cikk alapvető információkat és tájékoztatást nyújt a docs.microsoft.com-cikkekben használt Markdown jelölőnyelvről.
ms.date: 07/13/2017
ms.openlocfilehash: 6bb8a1fa20957512addb07dda0e68abec4b0a83f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805725"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="17192-103">A Markdown használata Docs-tartalmak írásához</span><span class="sxs-lookup"><span data-stu-id="17192-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="17192-104">A [docs.microsoft.com](http://docs.microsoft.com) cikkei a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="17192-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="17192-105">Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="17192-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="17192-106">Mivel a Docs-tartalmak a GitHubon vannak tárolva, azokhoz használható a Markdown [GitHub-stílusú Markdown (GFM)](https://help.github.com/categories/writing-on-github/) nevű bővítése, amely további funkciókat biztosít a gyakori formázási igényekhez.</span><span class="sxs-lookup"><span data-stu-id="17192-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="17192-107">Ezen kívül az Open Publishing Services (OPS) a Markdig Markdown Parsert implementálja.</span><span class="sxs-lookup"><span data-stu-id="17192-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="17192-108">A Markdig nagy mértékben kompatibilis a GFM-mel, és további funkciókkal támogatja a Docs specifikus szolgáltatásainak használatát.</span><span class="sxs-lookup"><span data-stu-id="17192-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="17192-109">A Markdig egy gyors, hatékony, CommonMark-megfelelőséggel rendelkező, bővíthető Markdown-feldolgozó .NET környezetekhez.</span><span class="sxs-lookup"><span data-stu-id="17192-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="17192-110">Jobb közösségi támogatás</span><span class="sxs-lookup"><span data-stu-id="17192-110">Better community support</span></span>
* <span data-ttu-id="17192-111">Jobb szabványtámogatás</span><span class="sxs-lookup"><span data-stu-id="17192-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="17192-112">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="17192-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="17192-113">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="17192-113">Headings</span></span>

<span data-ttu-id="17192-114">Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="17192-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="17192-115">Félkövér és dőlt szöveg</span><span class="sxs-lookup"><span data-stu-id="17192-115">Bold and italic text</span></span>

<span data-ttu-id="17192-116">A **félkövérként** formázandó szöveget zárja dupla csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="17192-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="17192-117">A *dőltként* formázandó szöveget zárja egyszeres csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="17192-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="17192-118">A ***félkövérként és dőltként*** is formázandó szöveget zárja háromszoros csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="17192-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="17192-119">Listák</span><span class="sxs-lookup"><span data-stu-id="17192-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="17192-120">Rendezetlen listák</span><span class="sxs-lookup"><span data-stu-id="17192-120">Unordered list</span></span>

<span data-ttu-id="17192-121">Rendezetlen vagy listajeles listákat csillagokkal vagy kötőjelekkel formázhat.</span><span class="sxs-lookup"><span data-stu-id="17192-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="17192-122">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="17192-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="17192-123">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="17192-123">will be rendered as:</span></span>

- <span data-ttu-id="17192-124">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-124">List item 1</span></span>
- <span data-ttu-id="17192-125">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-125">List item 2</span></span>
- <span data-ttu-id="17192-126">3. listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-126">List item 3</span></span>

<span data-ttu-id="17192-127">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="17192-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="17192-128">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="17192-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="17192-129">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="17192-129">will be rendered as:</span></span>

- <span data-ttu-id="17192-130">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-130">List item 1</span></span>
  - <span data-ttu-id="17192-131">A listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-131">List item A</span></span>
  - <span data-ttu-id="17192-132">B listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-132">List item B</span></span>
- <span data-ttu-id="17192-133">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="17192-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="17192-134">Rendezett lista</span><span class="sxs-lookup"><span data-stu-id="17192-134">Ordered list</span></span>

<span data-ttu-id="17192-135">Rendezett vagy lépéseket ismertető listákat a megfelelő számok használatával formázhat.</span><span class="sxs-lookup"><span data-stu-id="17192-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="17192-136">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="17192-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="17192-137">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="17192-137">will be rendered as:</span></span>

1. <span data-ttu-id="17192-138">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="17192-138">First instruction</span></span>
2. <span data-ttu-id="17192-139">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="17192-139">Second instruction</span></span>
3. <span data-ttu-id="17192-140">Harmadik utasítás</span><span class="sxs-lookup"><span data-stu-id="17192-140">Third instruction</span></span>

<span data-ttu-id="17192-141">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="17192-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="17192-142">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="17192-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="17192-143">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="17192-143">will be rendered as:</span></span>

1. <span data-ttu-id="17192-144">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="17192-144">First instruction</span></span>
   1. <span data-ttu-id="17192-145">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="17192-145">Sub-instruction</span></span>
   2. <span data-ttu-id="17192-146">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="17192-146">Sub-instruction</span></span>
2. <span data-ttu-id="17192-147">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="17192-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="17192-148">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="17192-148">Tables</span></span>

<span data-ttu-id="17192-149">A táblázatok nem szerepelnek a Markdown alapspecifikációjában, de a GFM-ben támogatottak.</span><span class="sxs-lookup"><span data-stu-id="17192-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="17192-150">Táblázatokat a függőleges vonal (|) és a kötőjel (-) karakterekkel hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="17192-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="17192-151">A kötőjelekkel hozhatja létre az egyes oszlopok fejléceit, a függőleges vonalakkal pedig az oszlopokat választja el egymástól.</span><span class="sxs-lookup"><span data-stu-id="17192-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="17192-152">A táblázat elé szúrjon be egy üres sort, hogy az megfelelően jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="17192-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="17192-153">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="17192-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="17192-154">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="17192-154">will be rendered as:</span></span>

| <span data-ttu-id="17192-155">Így</span><span class="sxs-lookup"><span data-stu-id="17192-155">Fun</span></span>                  | <span data-ttu-id="17192-156">Néznek ki a</span><span class="sxs-lookup"><span data-stu-id="17192-156">With</span></span>                 | <span data-ttu-id="17192-157">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="17192-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="17192-158">balra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="17192-158">left-aligned column</span></span>  | <span data-ttu-id="17192-159">jobbra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="17192-159">right-aligned column</span></span> | <span data-ttu-id="17192-160">középre igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="17192-160">centered column</span></span> |
| <span data-ttu-id="17192-161">$100</span><span class="sxs-lookup"><span data-stu-id="17192-161">$100</span></span>                 | <span data-ttu-id="17192-162">$100</span><span class="sxs-lookup"><span data-stu-id="17192-162">$100</span></span>                 | <span data-ttu-id="17192-163">$100</span><span class="sxs-lookup"><span data-stu-id="17192-163">$100</span></span>            |
| <span data-ttu-id="17192-164">$10</span><span class="sxs-lookup"><span data-stu-id="17192-164">$10</span></span>                  | <span data-ttu-id="17192-165">$10</span><span class="sxs-lookup"><span data-stu-id="17192-165">$10</span></span>                  | <span data-ttu-id="17192-166">$10</span><span class="sxs-lookup"><span data-stu-id="17192-166">$10</span></span>             |
| <span data-ttu-id="17192-167">$1</span><span class="sxs-lookup"><span data-stu-id="17192-167">$1</span></span>                   | <span data-ttu-id="17192-168">$1</span><span class="sxs-lookup"><span data-stu-id="17192-168">$1</span></span>                   | <span data-ttu-id="17192-169">$1</span><span class="sxs-lookup"><span data-stu-id="17192-169">$1</span></span>              |

<span data-ttu-id="17192-170">További információ a táblázatok létrehozásáról:</span><span class="sxs-lookup"><span data-stu-id="17192-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="17192-171">A Markdig széles táblázatok formázását segítő [táblázatbehatárolási funkcióját](#table-wrapping) ismertető szakasz.</span><span class="sxs-lookup"><span data-stu-id="17192-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="17192-172">Az [Információk rendszerezése táblázatokkal](https://help.github.com/articles/organizing-information-with-tables/) című GitHub-cikk.</span><span class="sxs-lookup"><span data-stu-id="17192-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="17192-173">A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás.</span><span class="sxs-lookup"><span data-stu-id="17192-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="17192-174">[Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet).</span><span class="sxs-lookup"><span data-stu-id="17192-174">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="17192-175">[Michel Fortin: Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="17192-175">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="17192-176">[HTML-táblázatok konvertálása Markdown-formátumra](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="17192-176">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="17192-177">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="17192-177">Links</span></span>

<span data-ttu-id="17192-178">A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:</span><span class="sxs-lookup"><span data-stu-id="17192-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="17192-179">További információ a hivatkozások használatáról:</span><span class="sxs-lookup"><span data-stu-id="17192-179">For more information on linking, see:</span></span>

- <span data-ttu-id="17192-180">A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.</span><span class="sxs-lookup"><span data-stu-id="17192-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="17192-181">A Markdig által biztosított hivatkozási szintaxisról a jelen útmutató [Hivatkozások](how-to-write-links.md) című oldalán található részletesebb információ.</span><span class="sxs-lookup"><span data-stu-id="17192-181">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="17192-182">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="17192-182">Code snippets</span></span>

<span data-ttu-id="17192-183">A Markdown támogatja a kódrészletek mondaton belüli, illetve mondatok közötti, „elkülönített” blokkban való elhelyezését is.</span><span class="sxs-lookup"><span data-stu-id="17192-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="17192-184">További részletek:</span><span class="sxs-lookup"><span data-stu-id="17192-184">For details, see:</span></span>

- [<span data-ttu-id="17192-185">A Markdown natív kódrészlet-támogatása</span><span class="sxs-lookup"><span data-stu-id="17192-185">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="17192-186">GFM-támogatás kód elkülönítéséhez és szintaxiskiemeléshez</span><span class="sxs-lookup"><span data-stu-id="17192-186">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="17192-187">Az elkülönített kódblokkokban egyszerűen kiemelhető a kódrészletek szintaxisa.</span><span class="sxs-lookup"><span data-stu-id="17192-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="17192-188">Az elkülönített kódblokkok általános formátuma a következő:</span><span class="sxs-lookup"><span data-stu-id="17192-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="17192-189">A három kezdő „\`” karakter utáni alias határozza meg a használni kívánt szintaxiskiemelést.</span><span class="sxs-lookup"><span data-stu-id="17192-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="17192-190">Az alábbi lista felsorolja a Docs-tartalmakban gyakran használt programozási nyelveket és a hozzájuk tartozó címkét:</span><span class="sxs-lookup"><span data-stu-id="17192-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="17192-191">Ezekhez a nyelvekhez a rendszer támogatja a névformázást, és legtöbbjük esetében szintaxiskiemelést is nyújt.</span><span class="sxs-lookup"><span data-stu-id="17192-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="17192-192">Név</span><span class="sxs-lookup"><span data-stu-id="17192-192">Name</span></span>|<span data-ttu-id="17192-193">Markdown-címke</span><span class="sxs-lookup"><span data-stu-id="17192-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="17192-194">.NET-konzol</span><span class="sxs-lookup"><span data-stu-id="17192-194">.NET Console</span></span>|<span data-ttu-id="17192-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="17192-195">dotnetcli</span></span>|
|<span data-ttu-id="17192-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="17192-196">ASP.NET (C#)</span></span>|<span data-ttu-id="17192-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="17192-197">aspx-csharp</span></span>|
|<span data-ttu-id="17192-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="17192-198">ASP.NET (VB)</span></span>|<span data-ttu-id="17192-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="17192-199">aspx-vb</span></span>|
|<span data-ttu-id="17192-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="17192-200">AzCopy</span></span>|<span data-ttu-id="17192-201">azcopy</span><span class="sxs-lookup"><span data-stu-id="17192-201">azcopy</span></span>|
|<span data-ttu-id="17192-202">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="17192-202">Azure CLI</span></span>|<span data-ttu-id="17192-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="17192-203">azurecli</span></span>|
|<span data-ttu-id="17192-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="17192-204">Azure PowerShell</span></span>|<span data-ttu-id="17192-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="17192-205">azurepowershell</span></span>|
|<span data-ttu-id="17192-206">C++</span><span class="sxs-lookup"><span data-stu-id="17192-206">C++</span></span>|<span data-ttu-id="17192-207">cpp</span><span class="sxs-lookup"><span data-stu-id="17192-207">cpp</span></span>|
|<span data-ttu-id="17192-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="17192-208">C++/CX</span></span>|<span data-ttu-id="17192-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="17192-209">cppcx</span></span>|
|<span data-ttu-id="17192-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="17192-210">C++/WinRT</span></span>|<span data-ttu-id="17192-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="17192-211">cppwinrt</span></span>|
|<span data-ttu-id="17192-212">C#</span><span class="sxs-lookup"><span data-stu-id="17192-212">C#</span></span>|<span data-ttu-id="17192-213">csharp</span><span class="sxs-lookup"><span data-stu-id="17192-213">csharp</span></span>|
|<span data-ttu-id="17192-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="17192-214">CSHTML</span></span>|<span data-ttu-id="17192-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="17192-215">cshtml</span></span>|
|<span data-ttu-id="17192-216">DAX</span><span class="sxs-lookup"><span data-stu-id="17192-216">DAX</span></span>|<span data-ttu-id="17192-217">dax</span><span class="sxs-lookup"><span data-stu-id="17192-217">dax</span></span>|
|<span data-ttu-id="17192-218">F#</span><span class="sxs-lookup"><span data-stu-id="17192-218">F#</span></span>|<span data-ttu-id="17192-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="17192-219">fsharp</span></span>|
|<span data-ttu-id="17192-220">Go</span><span class="sxs-lookup"><span data-stu-id="17192-220">Go</span></span>|<span data-ttu-id="17192-221">go</span><span class="sxs-lookup"><span data-stu-id="17192-221">go</span></span>|
|<span data-ttu-id="17192-222">HTML</span><span class="sxs-lookup"><span data-stu-id="17192-222">HTML</span></span>|<span data-ttu-id="17192-223">html</span><span class="sxs-lookup"><span data-stu-id="17192-223">html</span></span>|
|<span data-ttu-id="17192-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="17192-224">HTTP</span></span>|<span data-ttu-id="17192-225">http</span><span class="sxs-lookup"><span data-stu-id="17192-225">http</span></span>|
|<span data-ttu-id="17192-226">Java</span><span class="sxs-lookup"><span data-stu-id="17192-226">Java</span></span>|<span data-ttu-id="17192-227">java</span><span class="sxs-lookup"><span data-stu-id="17192-227">java</span></span>|
|<span data-ttu-id="17192-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="17192-228">JavaScript</span></span>|<span data-ttu-id="17192-229">javascript</span><span class="sxs-lookup"><span data-stu-id="17192-229">javascript</span></span>|
|<span data-ttu-id="17192-230">JSON</span><span class="sxs-lookup"><span data-stu-id="17192-230">JSON</span></span>|<span data-ttu-id="17192-231">json</span><span class="sxs-lookup"><span data-stu-id="17192-231">json</span></span>|
|<span data-ttu-id="17192-232">Markdown</span><span class="sxs-lookup"><span data-stu-id="17192-232">Markdown</span></span>|<span data-ttu-id="17192-233">md</span><span class="sxs-lookup"><span data-stu-id="17192-233">md</span></span>|
|<span data-ttu-id="17192-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="17192-234">NodeJS</span></span>|<span data-ttu-id="17192-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="17192-235">nodejs</span></span>|
|<span data-ttu-id="17192-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="17192-236">Objective-C</span></span>|<span data-ttu-id="17192-237">objc</span><span class="sxs-lookup"><span data-stu-id="17192-237">objc</span></span>|
|<span data-ttu-id="17192-238">OData</span><span class="sxs-lookup"><span data-stu-id="17192-238">OData</span></span>|<span data-ttu-id="17192-239">odata</span><span class="sxs-lookup"><span data-stu-id="17192-239">odata</span></span>|
|<span data-ttu-id="17192-240">PHP</span><span class="sxs-lookup"><span data-stu-id="17192-240">PHP</span></span>|<span data-ttu-id="17192-241">php</span><span class="sxs-lookup"><span data-stu-id="17192-241">php</span></span>|
|<span data-ttu-id="17192-242">PowerApps-képlet</span><span class="sxs-lookup"><span data-stu-id="17192-242">Power Apps Formula</span></span>|<span data-ttu-id="17192-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="17192-243">powerappsfl</span></span>|
|<span data-ttu-id="17192-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="17192-244">PowerShell</span></span>|<span data-ttu-id="17192-245">powershell</span><span class="sxs-lookup"><span data-stu-id="17192-245">powershell</span></span>|
|<span data-ttu-id="17192-246">Python</span><span class="sxs-lookup"><span data-stu-id="17192-246">Python</span></span>|<span data-ttu-id="17192-247">python</span><span class="sxs-lookup"><span data-stu-id="17192-247">python</span></span>|
|<span data-ttu-id="17192-248">Q#</span><span class="sxs-lookup"><span data-stu-id="17192-248">Q#</span></span>|<span data-ttu-id="17192-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="17192-249">qsharp</span></span>|
|<span data-ttu-id="17192-250">R</span><span class="sxs-lookup"><span data-stu-id="17192-250">R</span></span>|<span data-ttu-id="17192-251">r</span><span class="sxs-lookup"><span data-stu-id="17192-251">r</span></span>|
|<span data-ttu-id="17192-252">Ruby</span><span class="sxs-lookup"><span data-stu-id="17192-252">Ruby</span></span>|<span data-ttu-id="17192-253">ruby</span><span class="sxs-lookup"><span data-stu-id="17192-253">ruby</span></span>|
|<span data-ttu-id="17192-254">SQL</span><span class="sxs-lookup"><span data-stu-id="17192-254">SQL</span></span>|<span data-ttu-id="17192-255">sql</span><span class="sxs-lookup"><span data-stu-id="17192-255">sql</span></span>|
|<span data-ttu-id="17192-256">Swift</span><span class="sxs-lookup"><span data-stu-id="17192-256">Swift</span></span>|<span data-ttu-id="17192-257">swift</span><span class="sxs-lookup"><span data-stu-id="17192-257">swift</span></span>|
|<span data-ttu-id="17192-258">TypeScript</span><span class="sxs-lookup"><span data-stu-id="17192-258">TypeScript</span></span>|<span data-ttu-id="17192-259">typescript</span><span class="sxs-lookup"><span data-stu-id="17192-259">typescript</span></span>|
|<span data-ttu-id="17192-260">VB</span><span class="sxs-lookup"><span data-stu-id="17192-260">VB</span></span>|<span data-ttu-id="17192-261">vb</span><span class="sxs-lookup"><span data-stu-id="17192-261">vb</span></span>|
|<span data-ttu-id="17192-262">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="17192-262">VSTS CLI</span></span>|<span data-ttu-id="17192-263">vstscli</span><span class="sxs-lookup"><span data-stu-id="17192-263">vstscli</span></span>|
|<span data-ttu-id="17192-264">XAML</span><span class="sxs-lookup"><span data-stu-id="17192-264">XAML</span></span>|<span data-ttu-id="17192-265">xaml</span><span class="sxs-lookup"><span data-stu-id="17192-265">xaml</span></span>|
|<span data-ttu-id="17192-266">XML</span><span class="sxs-lookup"><span data-stu-id="17192-266">XML</span></span>|<span data-ttu-id="17192-267">xml</span><span class="sxs-lookup"><span data-stu-id="17192-267">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="17192-268">C\#-példa:</span><span class="sxs-lookup"><span data-stu-id="17192-268">Example: C\#</span></span>

<span data-ttu-id="17192-269">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="17192-269">__Markdown__</span></span>

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

<span data-ttu-id="17192-270">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="17192-270">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="17192-271">SQL-példa:</span><span class="sxs-lookup"><span data-stu-id="17192-271">Example: SQL</span></span>

<span data-ttu-id="17192-272">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="17192-272">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="17192-273">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="17192-273">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="17192-274">Egyedi OPS Markdown-bővítmények</span><span class="sxs-lookup"><span data-stu-id="17192-274">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="17192-275">Az Open Publishing Services (OPS) a Markdig Parser Markdownt implementálja, amely nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM).</span><span class="sxs-lookup"><span data-stu-id="17192-275">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="17192-276">A Markdig néhány funkciót biztosít a Markdown-bővítmények révén.</span><span class="sxs-lookup"><span data-stu-id="17192-276">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="17192-277">A jelen útmutatóban az OPS teljes szerzői útmutatójának kiválasztott témakörei szerepelnek referenciaként.</span><span class="sxs-lookup"><span data-stu-id="17192-277">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="17192-278">(Például lásd a „Markdig- és Markdown-bővítmények” és a „Kódrészletek” címeket a tartalomjegyzékben.)</span><span class="sxs-lookup"><span data-stu-id="17192-278">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="17192-279">A Docs-cikkek formázásának nagy része, például a bekezdések, a hivatkozások, a listák és a fejlécek a GFM használatával készülnek.</span><span class="sxs-lookup"><span data-stu-id="17192-279">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="17192-280">A kifinomultabb formázáshoz a cikkekben többek között az alábbi Markdig-funkciók használhatók:</span><span class="sxs-lookup"><span data-stu-id="17192-280">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="17192-281">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="17192-281">Note blocks</span></span>
- <span data-ttu-id="17192-282">Beágyazások</span><span class="sxs-lookup"><span data-stu-id="17192-282">Includes</span></span>
- <span data-ttu-id="17192-283">Választómezők</span><span class="sxs-lookup"><span data-stu-id="17192-283">Selectors</span></span>
- <span data-ttu-id="17192-284">Beágyazott videók</span><span class="sxs-lookup"><span data-stu-id="17192-284">Embedded videos</span></span>
- <span data-ttu-id="17192-285">Kódrészletek és -minták</span><span class="sxs-lookup"><span data-stu-id="17192-285">Code snippets/samples</span></span>

<span data-ttu-id="17192-286">A teljes listát a tartalomjegyzék „Markdig- és Markdown-bővítmények” és „Kódrészletek” fejezetcíme alatt találhatja.</span><span class="sxs-lookup"><span data-stu-id="17192-286">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="17192-287">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="17192-287">Note blocks</span></span>

<span data-ttu-id="17192-288">A megjegyzésblokkok 4 típusa közül választhat, hogy felhívja a figyelmet adott tartalomra:</span><span class="sxs-lookup"><span data-stu-id="17192-288">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="17192-289">MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="17192-289">NOTE</span></span>
- <span data-ttu-id="17192-290">FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="17192-290">WARNING</span></span>
- <span data-ttu-id="17192-291">TIPP</span><span class="sxs-lookup"><span data-stu-id="17192-291">TIP</span></span>
- <span data-ttu-id="17192-292">FONTOS</span><span class="sxs-lookup"><span data-stu-id="17192-292">IMPORTANT</span></span>

<span data-ttu-id="17192-293">Általánosságban elmondható, hogy a megjegyzésblokkokat ritkán szabad használni, mert megtörhetik a cikk folytonosságát.</span><span class="sxs-lookup"><span data-stu-id="17192-293">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="17192-294">Bár a kódblokkok, képek, listák és hivatkozások használata a megjegyzésblokkokon belül is támogatott, törekedjen egyszerű és könnyen érthető megjegyzésblokkok írására.</span><span class="sxs-lookup"><span data-stu-id="17192-294">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="17192-295">Beágyazások</span><span class="sxs-lookup"><span data-stu-id="17192-295">Includes</span></span>

<span data-ttu-id="17192-296">Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a Markdig fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra.</span><span class="sxs-lookup"><span data-stu-id="17192-296">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="17192-297">Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben.</span><span class="sxs-lookup"><span data-stu-id="17192-297">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="17192-298">A tartalmak újrafelhasználását háromféle beágyazás segíti:</span><span class="sxs-lookup"><span data-stu-id="17192-298">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="17192-299">Soron belüli: egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="17192-299">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="17192-300">Blokk: egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="17192-300">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="17192-301">Képek: ez a képek normál beillesztésének megvalósítása a Docsban.</span><span class="sxs-lookup"><span data-stu-id="17192-301">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="17192-302">A soron belüli és blokk típusú beágyazás egy egyszerű Markdown- (.md) fájlt használ.</span><span class="sxs-lookup"><span data-stu-id="17192-302">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="17192-303">Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="17192-303">It can contain any valid Markdown.</span></span> <span data-ttu-id="17192-304">Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="17192-304">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="17192-305">A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.</span><span class="sxs-lookup"><span data-stu-id="17192-305">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="17192-306">Néhány követelmény és megfontolandó szempont a beágyazásokhoz:</span><span class="sxs-lookup"><span data-stu-id="17192-306">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="17192-307">Bármikor használhat beágyazást, amikor ugyanazt a szöveget több cikkben is szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="17192-307">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="17192-308">A blokk típusú beágyazás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott.</span><span class="sxs-lookup"><span data-stu-id="17192-308">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="17192-309">Ne használja egy mondatnál kisebb terjedelmű szöveghez.</span><span class="sxs-lookup"><span data-stu-id="17192-309">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="17192-310">A beágyazott tartalmak a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok Markdig-bővítményeket igényelnek.</span><span class="sxs-lookup"><span data-stu-id="17192-310">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="17192-311">Azok csak közzététel után jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="17192-311">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="17192-312">Ügyeljen rá, hogy a beágyazott szöveg teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó cikknek a beágyazást megelőző vagy azt követő szövegétől.</span><span class="sxs-lookup"><span data-stu-id="17192-312">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="17192-313">Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan sztring jön létre a cikkben, amely megtöri a honosított felületet.</span><span class="sxs-lookup"><span data-stu-id="17192-313">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="17192-314">Ne alkalmazzon beágyazást más beágyazásokon belül.</span><span class="sxs-lookup"><span data-stu-id="17192-314">Don't embed includes within other includes.</span></span> <span data-ttu-id="17192-315">Ez nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="17192-315">They are not supported.</span></span>
- <span data-ttu-id="17192-316">A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa.</span><span class="sxs-lookup"><span data-stu-id="17192-316">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="17192-317">A médiamappa gyökere nem tartalmazhat képfájlokat.</span><span class="sxs-lookup"><span data-stu-id="17192-317">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="17192-318">Ha a beágyazás nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="17192-318">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="17192-319">A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között.</span><span class="sxs-lookup"><span data-stu-id="17192-319">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="17192-320">Minden egyes beágyazáshoz és cikkhez használjon külön fájlt, egyedi névvel.</span><span class="sxs-lookup"><span data-stu-id="17192-320">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="17192-321">A médiafájlt tárolja a beágyazáshoz társított médiamappában.</span><span class="sxs-lookup"><span data-stu-id="17192-321">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="17192-322">A cikkek ne tartalmazzanak kizárólag egy beágyazást.</span><span class="sxs-lookup"><span data-stu-id="17192-322">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="17192-323">A beágyazások a cikk többi része tartalmának kiegészítésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="17192-323">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="17192-324">Választómezők</span><span class="sxs-lookup"><span data-stu-id="17192-324">Selectors</span></span>

<span data-ttu-id="17192-325">Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg a különböző technológiák és platformok különbségeinek figyelembe vételével.</span><span class="sxs-lookup"><span data-stu-id="17192-325">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="17192-326">Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb.</span><span class="sxs-lookup"><span data-stu-id="17192-326">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="17192-327">A Markdigben jelenleg kétféle választómező van, az egyszerű és a többszintű.</span><span class="sxs-lookup"><span data-stu-id="17192-327">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="17192-328">Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni,</span><span class="sxs-lookup"><span data-stu-id="17192-328">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="17192-329">majd erre hivatkozni az összes olyan témakörben, amely ugyanazt a választómezőt használja.</span><span class="sxs-lookup"><span data-stu-id="17192-329">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="17192-330">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="17192-330">Code snippets</span></span>

<span data-ttu-id="17192-331">A Markdig a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="17192-331">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="17192-332">A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:</span><span class="sxs-lookup"><span data-stu-id="17192-332">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="17192-333">Központosított kódminták vagy -részletek beágyazása külső tárházból.</span><span class="sxs-lookup"><span data-stu-id="17192-333">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="17192-334">Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="17192-334">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="17192-335">Tipikus hibák és hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="17192-335">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="17192-336">Helyettesítő szöveg</span><span class="sxs-lookup"><span data-stu-id="17192-336">Alt text</span></span>

<span data-ttu-id="17192-337">Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen.</span><span class="sxs-lookup"><span data-stu-id="17192-337">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="17192-338">Például a következő szöveg helyett:</span><span class="sxs-lookup"><span data-stu-id="17192-338">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="17192-339">Az aláhúzás jeleket így jelenítheti meg:</span><span class="sxs-lookup"><span data-stu-id="17192-339">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="17192-340">Aposztrófok és idézőjelek</span><span class="sxs-lookup"><span data-stu-id="17192-340">Apostrophes and quotation marks</span></span>

<span data-ttu-id="17192-341">Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="17192-341">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="17192-342">Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni,</span><span class="sxs-lookup"><span data-stu-id="17192-342">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span>
<span data-ttu-id="17192-343">különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="17192-343">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="17192-344">Ezen írásjelek „intelligens” verzióinak kódolásai a következők:</span><span class="sxs-lookup"><span data-stu-id="17192-344">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="17192-345">Bal oldali (nyitó) idézőjel: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="17192-345">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="17192-346">Jobb oldali (záró) idézőjel: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="17192-346">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="17192-347">Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="17192-347">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="17192-348">Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="17192-348">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="17192-349">Csúcsos zárójelek</span><span class="sxs-lookup"><span data-stu-id="17192-349">Angle brackets</span></span>

<span data-ttu-id="17192-350">Helyőrzők jelölésére általában csúcsos zárójeleket alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="17192-350">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="17192-351">Ha ezt szövegben használja (és nem kódban), a csúcsos zárójelet kódolnia kell.</span><span class="sxs-lookup"><span data-stu-id="17192-351">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="17192-352">Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.</span><span class="sxs-lookup"><span data-stu-id="17192-352">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="17192-353">A `<script name>` kódolása például a következő: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="17192-353">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="17192-354">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="17192-354">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="17192-355">Markdown-források</span><span class="sxs-lookup"><span data-stu-id="17192-355">Markdown resources</span></span>

- <span data-ttu-id="17192-356">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)</span><span class="sxs-lookup"><span data-stu-id="17192-356">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="17192-357">Markdown-segédlet a Docshoz</span><span class="sxs-lookup"><span data-stu-id="17192-357">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="17192-358">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)</span><span class="sxs-lookup"><span data-stu-id="17192-358">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
- [<span data-ttu-id="17192-359">Markdown-útmutató</span><span class="sxs-lookup"><span data-stu-id="17192-359">The Markdown Guide</span></span>](https://www.markdownguide.org/)
