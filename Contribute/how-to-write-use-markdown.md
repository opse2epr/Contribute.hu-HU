---
title: A Markdown használata Docs-tartalmak írásához
description: Ez a cikk alapvető információkat és tájékoztatást nyújt a docs.microsoft.com-cikkekben használt Markdown jelölőnyelvről.
ms.date: 01/29/2019
ms.openlocfilehash: 5235189d11c8c20ac20c91572d8bafcf525fb7c0
ms.sourcegitcommit: fbdd61ae4fb3761aec072732eefcbf2c2dca8011
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55887298"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="e2cac-103">A Markdown használata Docs-tartalmak írásához</span><span class="sxs-lookup"><span data-stu-id="e2cac-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="e2cac-104">A [docs.microsoft.com](http://docs.microsoft.com) cikkei a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="e2cac-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="e2cac-105">Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="e2cac-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="e2cac-106">A docs.microsoft.com webhely háttérrendszere Open Publishing Services (OPS) szolgáltatást használ, mely támogatja a [Markdigen](https://github.com/lunet-io/markdig) keresztül értelmezett [CommonMark](https://commonmark.org/)-kompatibilis jelölőnyelvet, valamint a [DocFX Flavored Markdown (DFM)](https://dotnet.github.io/docfx/) jelölőnyelvet.</span><span class="sxs-lookup"><span data-stu-id="e2cac-106">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which supports [CommonMark](https://commonmark.org/) compliant markdown parsed through [Markdig](https://github.com/lunet-io/markdig) and also supports [DocFX Flavored Markdown (DFM)](https://dotnet.github.io/docfx/).</span></span> <span data-ttu-id="e2cac-107">Ezek a jelölőnyelv-változatok nagyrészt kompatibilisek a [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) jelölőnyelvvel, mivel a legtöbb dokumentum a GitHubon van tárolva, és ott szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="e2cac-107">These markdown flavors are mostly compatible with [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), as most docs are stored in GitHub and can be edited there.</span></span> <span data-ttu-id="e2cac-108">Ez néhány Markdown-bővítményeken keresztül hozzáadott funkcióval egészül ki.</span><span class="sxs-lookup"><span data-stu-id="e2cac-108">Additional functionality is added through Markdown extensions.</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="e2cac-109">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="e2cac-109">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="e2cac-110">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="e2cac-110">Headings</span></span>

<span data-ttu-id="e2cac-111">Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="e2cac-111">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="e2cac-112">A címsorokat atx-stílussal kell megadni. Ez azt jelenti, hogy 1–6 kettőskereszt karaktert (#) kell a sor elejére írni, a számuk a H1–H6 HTML-címsorszintjét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e2cac-112">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="e2cac-113">Fent a címsorokra látható példa, az elsőtől a negyedik szintig.</span><span class="sxs-lookup"><span data-stu-id="e2cac-113">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="e2cac-114">Egy témakörben **egy és csak egy** első szintű címsornak (H1) kell lennie, ez fog megjelenni a lapon címként.</span><span class="sxs-lookup"><span data-stu-id="e2cac-114">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="e2cac-115">Ha `#` a cím az utolsó karaktere, akkor még egy `#` karaktert kell a cím végére írni ahhoz, hogy helyesen jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="e2cac-115">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="e2cac-116">Például így: `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="e2cac-116">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="e2cac-117">A második szintű címsorokból generálódik a lapon lévő tartalomjegyzék, ez jelenik meg a lap címe alatti „A cikk tartalma” szakaszban.</span><span class="sxs-lookup"><span data-stu-id="e2cac-117">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="e2cac-118">Félkövér és dőlt szöveg</span><span class="sxs-lookup"><span data-stu-id="e2cac-118">Bold and italic text</span></span>

<span data-ttu-id="e2cac-119">A **félkövérként** formázandó szöveget zárja dupla csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="e2cac-119">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="e2cac-120">A *dőltként* formázandó szöveget zárja egyszeres csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="e2cac-120">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="e2cac-121">A ***félkövérként és dőltként*** is formázandó szöveget zárja háromszoros csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="e2cac-121">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="e2cac-122">Idézetblokkok</span><span class="sxs-lookup"><span data-stu-id="e2cac-122">Blockquotes</span></span>

<span data-ttu-id="e2cac-123">Az idézetblokkok létrehozására a `>` karakter használatos:</span><span class="sxs-lookup"><span data-stu-id="e2cac-123">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="e2cac-124">Az előző példa a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-124">The preceding example renders as follows:</span></span>

> <span data-ttu-id="e2cac-125">Ekkorra már tízmillió éve aszályos volt az időjárás, és a rettentő gyíkok uralma már rég véget ért.</span><span class="sxs-lookup"><span data-stu-id="e2cac-125">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="e2cac-126">Itt az egyenlítőnél, a később Afrika néven ismert kontinensen példátlan hevességű lett a létért folyó harc, a győztes pedig még fel sem tűnt a láthatáron.</span><span class="sxs-lookup"><span data-stu-id="e2cac-126">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="e2cac-127">Ezen a sivár és kiszikkadt vidéken csak az apró, a gyors és a harcias tudott életben maradni, vagy akár csak reménykedni is benne.</span><span class="sxs-lookup"><span data-stu-id="e2cac-127">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="e2cac-128">Listák</span><span class="sxs-lookup"><span data-stu-id="e2cac-128">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="e2cac-129">Rendezetlen listák</span><span class="sxs-lookup"><span data-stu-id="e2cac-129">Unordered list</span></span>

<span data-ttu-id="e2cac-130">Rendezetlen vagy listajeles listákat csillagokkal vagy kötőjelekkel formázhat.</span><span class="sxs-lookup"><span data-stu-id="e2cac-130">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="e2cac-131">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-131">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="e2cac-132">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-132">will be rendered as:</span></span>

- <span data-ttu-id="e2cac-133">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-133">List item 1</span></span>
- <span data-ttu-id="e2cac-134">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-134">List item 2</span></span>
- <span data-ttu-id="e2cac-135">3. listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-135">List item 3</span></span>

<span data-ttu-id="e2cac-136">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="e2cac-136">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="e2cac-137">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-137">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="e2cac-138">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-138">will be rendered as:</span></span>

- <span data-ttu-id="e2cac-139">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-139">List item 1</span></span>
  - <span data-ttu-id="e2cac-140">A listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-140">List item A</span></span>
  - <span data-ttu-id="e2cac-141">B listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-141">List item B</span></span>
- <span data-ttu-id="e2cac-142">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="e2cac-142">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="e2cac-143">Rendezett lista</span><span class="sxs-lookup"><span data-stu-id="e2cac-143">Ordered list</span></span>

<span data-ttu-id="e2cac-144">Rendezett vagy lépéseket ismertető listákat a megfelelő számok használatával formázhat.</span><span class="sxs-lookup"><span data-stu-id="e2cac-144">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="e2cac-145">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-145">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="e2cac-146">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-146">will be rendered as:</span></span>

1. <span data-ttu-id="e2cac-147">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-147">First instruction</span></span>
2. <span data-ttu-id="e2cac-148">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-148">Second instruction</span></span>
3. <span data-ttu-id="e2cac-149">Harmadik utasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-149">Third instruction</span></span>

<span data-ttu-id="e2cac-150">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="e2cac-150">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="e2cac-151">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-151">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="e2cac-152">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-152">will be rendered as:</span></span>

1. <span data-ttu-id="e2cac-153">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-153">First instruction</span></span>
   1. <span data-ttu-id="e2cac-154">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-154">Sub-instruction</span></span>
   2. <span data-ttu-id="e2cac-155">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-155">Sub-instruction</span></span>
2. <span data-ttu-id="e2cac-156">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-156">Second instruction</span></span>

<span data-ttu-id="e2cac-157">Felhívjuk figyelmét, hogy minden bejegyzésnél az „1.”</span><span class="sxs-lookup"><span data-stu-id="e2cac-157">Note that we use '1.'</span></span> <span data-ttu-id="e2cac-158">jelölést használjuk.</span><span class="sxs-lookup"><span data-stu-id="e2cac-158">for all entries.</span></span> <span data-ttu-id="e2cac-159">Ez megkönnyíti az eltérések ellenőrzését, ha a későbbi frissítésekbe új lépések kerülnek, vagy törlünk a lépések közül.</span><span class="sxs-lookup"><span data-stu-id="e2cac-159">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="e2cac-160">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="e2cac-160">Tables</span></span>

<span data-ttu-id="e2cac-161">A táblázatok nem szerepelnek a Markdown alapspecifikációjában, de a GFM-ben támogatottak.</span><span class="sxs-lookup"><span data-stu-id="e2cac-161">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="e2cac-162">Táblázatokat a függőleges vonal (|) és a kötőjel (-) karakterekkel hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="e2cac-162">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="e2cac-163">A kötőjelekkel hozhatja létre az egyes oszlopok fejléceit, a függőleges vonalakkal pedig az oszlopokat választja el egymástól.</span><span class="sxs-lookup"><span data-stu-id="e2cac-163">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="e2cac-164">A táblázat elé szúrjon be egy üres sort, hogy az megfelelően jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="e2cac-164">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="e2cac-165">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-165">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="e2cac-166">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-166">will be rendered as:</span></span>

| <span data-ttu-id="e2cac-167">Így</span><span class="sxs-lookup"><span data-stu-id="e2cac-167">Fun</span></span>                  | <span data-ttu-id="e2cac-168">Néznek ki a</span><span class="sxs-lookup"><span data-stu-id="e2cac-168">With</span></span>                 | <span data-ttu-id="e2cac-169">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="e2cac-169">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="e2cac-170">balra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="e2cac-170">left-aligned column</span></span>  | <span data-ttu-id="e2cac-171">jobbra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="e2cac-171">right-aligned column</span></span> | <span data-ttu-id="e2cac-172">középre igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="e2cac-172">centered column</span></span> |
| <span data-ttu-id="e2cac-173">$100</span><span class="sxs-lookup"><span data-stu-id="e2cac-173">$100</span></span>                 | <span data-ttu-id="e2cac-174">$100</span><span class="sxs-lookup"><span data-stu-id="e2cac-174">$100</span></span>                 | <span data-ttu-id="e2cac-175">$100</span><span class="sxs-lookup"><span data-stu-id="e2cac-175">$100</span></span>            |
| <span data-ttu-id="e2cac-176">$10</span><span class="sxs-lookup"><span data-stu-id="e2cac-176">$10</span></span>                  | <span data-ttu-id="e2cac-177">$10</span><span class="sxs-lookup"><span data-stu-id="e2cac-177">$10</span></span>                  | <span data-ttu-id="e2cac-178">$10</span><span class="sxs-lookup"><span data-stu-id="e2cac-178">$10</span></span>             |
| <span data-ttu-id="e2cac-179">$1</span><span class="sxs-lookup"><span data-stu-id="e2cac-179">$1</span></span>                   | <span data-ttu-id="e2cac-180">$1</span><span class="sxs-lookup"><span data-stu-id="e2cac-180">$1</span></span>                   | <span data-ttu-id="e2cac-181">$1</span><span class="sxs-lookup"><span data-stu-id="e2cac-181">$1</span></span>              |

<span data-ttu-id="e2cac-182">További információ a táblázatok létrehozásáról:</span><span class="sxs-lookup"><span data-stu-id="e2cac-182">For more information on creating tables, see:</span></span>

- <span data-ttu-id="e2cac-183">A Markdig széles táblázatok formázását segítő [táblázatbehatárolási funkcióját](#table-wrapping) ismertető szakasz.</span><span class="sxs-lookup"><span data-stu-id="e2cac-183">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="e2cac-184">Az [Információk rendszerezése táblázatokkal](https://help.github.com/articles/organizing-information-with-tables/) című GitHub-cikk.</span><span class="sxs-lookup"><span data-stu-id="e2cac-184">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="e2cac-185">A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás.</span><span class="sxs-lookup"><span data-stu-id="e2cac-185">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="e2cac-186">[Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet).</span><span class="sxs-lookup"><span data-stu-id="e2cac-186">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="e2cac-187">[Michel Fortin: Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="e2cac-187">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="e2cac-188">[HTML-táblázatok konvertálása Markdown-formátumra](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="e2cac-188">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="e2cac-189">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="e2cac-189">Links</span></span>

<span data-ttu-id="e2cac-190">A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:</span><span class="sxs-lookup"><span data-stu-id="e2cac-190">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="e2cac-191">További információ a hivatkozások használatáról:</span><span class="sxs-lookup"><span data-stu-id="e2cac-191">For more information on linking, see:</span></span>

- <span data-ttu-id="e2cac-192">A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.</span><span class="sxs-lookup"><span data-stu-id="e2cac-192">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="e2cac-193">A Markdig által biztosított hivatkozási szintaxisról a jelen útmutató [Hivatkozások](how-to-write-links.md) című oldalán található részletesebb információ.</span><span class="sxs-lookup"><span data-stu-id="e2cac-193">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="e2cac-194">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="e2cac-194">Code snippets</span></span>

<span data-ttu-id="e2cac-195">A Markdown támogatja a kódrészletek mondaton belüli, illetve mondatok közötti, „elkülönített” blokkban való elhelyezését is.</span><span class="sxs-lookup"><span data-stu-id="e2cac-195">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="e2cac-196">További részletek:</span><span class="sxs-lookup"><span data-stu-id="e2cac-196">For details, see:</span></span>

- [<span data-ttu-id="e2cac-197">A Markdown natív kódrészlet-támogatása</span><span class="sxs-lookup"><span data-stu-id="e2cac-197">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="e2cac-198">GFM-támogatás kód elkülönítéséhez és szintaxiskiemeléshez</span><span class="sxs-lookup"><span data-stu-id="e2cac-198">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="e2cac-199">Az elkülönített kódblokkokban egyszerűen kiemelhető a kódrészletek szintaxisa.</span><span class="sxs-lookup"><span data-stu-id="e2cac-199">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="e2cac-200">Az elkülönített kódblokkok általános formátuma a következő:</span><span class="sxs-lookup"><span data-stu-id="e2cac-200">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="e2cac-201">A három kezdő „\`” karakter utáni alias határozza meg a használni kívánt szintaxiskiemelést.</span><span class="sxs-lookup"><span data-stu-id="e2cac-201">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="e2cac-202">Az alábbi lista felsorolja a Docs-tartalmakban gyakran használt programozási nyelveket és a hozzájuk tartozó címkét:</span><span class="sxs-lookup"><span data-stu-id="e2cac-202">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="e2cac-203">Ezekhez a nyelvekhez a rendszer támogatja a névformázást, és legtöbbjük esetében szintaxiskiemelést is nyújt.</span><span class="sxs-lookup"><span data-stu-id="e2cac-203">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="e2cac-204">Név</span><span class="sxs-lookup"><span data-stu-id="e2cac-204">Name</span></span>|<span data-ttu-id="e2cac-205">Markdown-címke</span><span class="sxs-lookup"><span data-stu-id="e2cac-205">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="e2cac-206">.NET-konzol</span><span class="sxs-lookup"><span data-stu-id="e2cac-206">.NET Console</span></span>|<span data-ttu-id="e2cac-207">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="e2cac-207">dotnetcli</span></span>|
|<span data-ttu-id="e2cac-208">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="e2cac-208">ASP.NET (C#)</span></span>|<span data-ttu-id="e2cac-209">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="e2cac-209">aspx-csharp</span></span>|
|<span data-ttu-id="e2cac-210">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="e2cac-210">ASP.NET (VB)</span></span>|<span data-ttu-id="e2cac-211">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="e2cac-211">aspx-vb</span></span>|
|<span data-ttu-id="e2cac-212">AzCopy</span><span class="sxs-lookup"><span data-stu-id="e2cac-212">AzCopy</span></span>|<span data-ttu-id="e2cac-213">azcopy</span><span class="sxs-lookup"><span data-stu-id="e2cac-213">azcopy</span></span>|
|<span data-ttu-id="e2cac-214">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="e2cac-214">Azure CLI</span></span>|<span data-ttu-id="e2cac-215">azurecli</span><span class="sxs-lookup"><span data-stu-id="e2cac-215">azurecli</span></span>|
|<span data-ttu-id="e2cac-216">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2cac-216">Azure PowerShell</span></span>|<span data-ttu-id="e2cac-217">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="e2cac-217">azurepowershell</span></span>|
|<span data-ttu-id="e2cac-218">C++</span><span class="sxs-lookup"><span data-stu-id="e2cac-218">C++</span></span>|<span data-ttu-id="e2cac-219">cpp</span><span class="sxs-lookup"><span data-stu-id="e2cac-219">cpp</span></span>|
|<span data-ttu-id="e2cac-220">C++/CX</span><span class="sxs-lookup"><span data-stu-id="e2cac-220">C++/CX</span></span>|<span data-ttu-id="e2cac-221">cppcx</span><span class="sxs-lookup"><span data-stu-id="e2cac-221">cppcx</span></span>|
|<span data-ttu-id="e2cac-222">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="e2cac-222">C++/WinRT</span></span>|<span data-ttu-id="e2cac-223">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="e2cac-223">cppwinrt</span></span>|
|<span data-ttu-id="e2cac-224">C#</span><span class="sxs-lookup"><span data-stu-id="e2cac-224">C#</span></span>|<span data-ttu-id="e2cac-225">csharp</span><span class="sxs-lookup"><span data-stu-id="e2cac-225">csharp</span></span>|
|<span data-ttu-id="e2cac-226">C# böngészőben</span><span class="sxs-lookup"><span data-stu-id="e2cac-226">C# in browser</span></span>|<span data-ttu-id="e2cac-227">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="e2cac-227">csharp-interactive</span></span>|
|<span data-ttu-id="e2cac-228">Konzol</span><span class="sxs-lookup"><span data-stu-id="e2cac-228">Console</span></span>|<span data-ttu-id="e2cac-229">console</span><span class="sxs-lookup"><span data-stu-id="e2cac-229">console</span></span>|
|<span data-ttu-id="e2cac-230">CSHTML</span><span class="sxs-lookup"><span data-stu-id="e2cac-230">CSHTML</span></span>|<span data-ttu-id="e2cac-231">cshtml</span><span class="sxs-lookup"><span data-stu-id="e2cac-231">cshtml</span></span>|
|<span data-ttu-id="e2cac-232">DAX</span><span class="sxs-lookup"><span data-stu-id="e2cac-232">DAX</span></span>|<span data-ttu-id="e2cac-233">dax</span><span class="sxs-lookup"><span data-stu-id="e2cac-233">dax</span></span>|
|<span data-ttu-id="e2cac-234">Docker</span><span class="sxs-lookup"><span data-stu-id="e2cac-234">Docker</span></span>|<span data-ttu-id="e2cac-235">dockerfile</span><span class="sxs-lookup"><span data-stu-id="e2cac-235">dockerfile</span></span>|
|<span data-ttu-id="e2cac-236">F#</span><span class="sxs-lookup"><span data-stu-id="e2cac-236">F#</span></span>|<span data-ttu-id="e2cac-237">fsharp</span><span class="sxs-lookup"><span data-stu-id="e2cac-237">fsharp</span></span>|
|<span data-ttu-id="e2cac-238">Go</span><span class="sxs-lookup"><span data-stu-id="e2cac-238">Go</span></span>|<span data-ttu-id="e2cac-239">go</span><span class="sxs-lookup"><span data-stu-id="e2cac-239">go</span></span>|
|<span data-ttu-id="e2cac-240">HTML</span><span class="sxs-lookup"><span data-stu-id="e2cac-240">HTML</span></span>|<span data-ttu-id="e2cac-241">html</span><span class="sxs-lookup"><span data-stu-id="e2cac-241">html</span></span>|
|<span data-ttu-id="e2cac-242">HTTP</span><span class="sxs-lookup"><span data-stu-id="e2cac-242">HTTP</span></span>|<span data-ttu-id="e2cac-243">http</span><span class="sxs-lookup"><span data-stu-id="e2cac-243">http</span></span>|
|<span data-ttu-id="e2cac-244">Java</span><span class="sxs-lookup"><span data-stu-id="e2cac-244">Java</span></span>|<span data-ttu-id="e2cac-245">java</span><span class="sxs-lookup"><span data-stu-id="e2cac-245">java</span></span>|
|<span data-ttu-id="e2cac-246">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e2cac-246">JavaScript</span></span>|<span data-ttu-id="e2cac-247">javascript</span><span class="sxs-lookup"><span data-stu-id="e2cac-247">javascript</span></span>|
|<span data-ttu-id="e2cac-248">JSON</span><span class="sxs-lookup"><span data-stu-id="e2cac-248">JSON</span></span>|<span data-ttu-id="e2cac-249">json</span><span class="sxs-lookup"><span data-stu-id="e2cac-249">json</span></span>|
|<span data-ttu-id="e2cac-250">Kusto lekérdezőnyelv</span><span class="sxs-lookup"><span data-stu-id="e2cac-250">Kusto Query Language</span></span>|<span data-ttu-id="e2cac-251">kusto</span><span class="sxs-lookup"><span data-stu-id="e2cac-251">kusto</span></span>|
|<span data-ttu-id="e2cac-252">Markdown</span><span class="sxs-lookup"><span data-stu-id="e2cac-252">Markdown</span></span>|<span data-ttu-id="e2cac-253">md</span><span class="sxs-lookup"><span data-stu-id="e2cac-253">md</span></span>|
|<span data-ttu-id="e2cac-254">Objective-C</span><span class="sxs-lookup"><span data-stu-id="e2cac-254">Objective-C</span></span>|<span data-ttu-id="e2cac-255">objc</span><span class="sxs-lookup"><span data-stu-id="e2cac-255">objc</span></span>|
|<span data-ttu-id="e2cac-256">OData</span><span class="sxs-lookup"><span data-stu-id="e2cac-256">OData</span></span>|<span data-ttu-id="e2cac-257">odata</span><span class="sxs-lookup"><span data-stu-id="e2cac-257">odata</span></span>|
|<span data-ttu-id="e2cac-258">PHP</span><span class="sxs-lookup"><span data-stu-id="e2cac-258">PHP</span></span>|<span data-ttu-id="e2cac-259">php</span><span class="sxs-lookup"><span data-stu-id="e2cac-259">php</span></span>|
|<span data-ttu-id="e2cac-260">PowerApps (pont a tizedes elválasztó)</span><span class="sxs-lookup"><span data-stu-id="e2cac-260">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="e2cac-261">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="e2cac-261">powerapps-dot</span></span>|
|<span data-ttu-id="e2cac-262">PowerApps (vessző a tizedes elválasztó)</span><span class="sxs-lookup"><span data-stu-id="e2cac-262">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="e2cac-263">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="e2cac-263">powerapps-comma</span></span>|
|<span data-ttu-id="e2cac-264">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2cac-264">PowerShell</span></span>|<span data-ttu-id="e2cac-265">powershell</span><span class="sxs-lookup"><span data-stu-id="e2cac-265">powershell</span></span>|
|<span data-ttu-id="e2cac-266">Python</span><span class="sxs-lookup"><span data-stu-id="e2cac-266">Python</span></span>|<span data-ttu-id="e2cac-267">python</span><span class="sxs-lookup"><span data-stu-id="e2cac-267">python</span></span>|
|<span data-ttu-id="e2cac-268">Q#</span><span class="sxs-lookup"><span data-stu-id="e2cac-268">Q#</span></span>|<span data-ttu-id="e2cac-269">qsharp</span><span class="sxs-lookup"><span data-stu-id="e2cac-269">qsharp</span></span>|
|<span data-ttu-id="e2cac-270">R</span><span class="sxs-lookup"><span data-stu-id="e2cac-270">R</span></span>|<span data-ttu-id="e2cac-271">r</span><span class="sxs-lookup"><span data-stu-id="e2cac-271">r</span></span>|
|<span data-ttu-id="e2cac-272">Ruby</span><span class="sxs-lookup"><span data-stu-id="e2cac-272">Ruby</span></span>|<span data-ttu-id="e2cac-273">ruby</span><span class="sxs-lookup"><span data-stu-id="e2cac-273">ruby</span></span>|
|<span data-ttu-id="e2cac-274">SQL</span><span class="sxs-lookup"><span data-stu-id="e2cac-274">SQL</span></span>|<span data-ttu-id="e2cac-275">sql</span><span class="sxs-lookup"><span data-stu-id="e2cac-275">sql</span></span>|
|<span data-ttu-id="e2cac-276">Swift</span><span class="sxs-lookup"><span data-stu-id="e2cac-276">Swift</span></span>|<span data-ttu-id="e2cac-277">swift</span><span class="sxs-lookup"><span data-stu-id="e2cac-277">swift</span></span>|
|<span data-ttu-id="e2cac-278">TypeScript</span><span class="sxs-lookup"><span data-stu-id="e2cac-278">TypeScript</span></span>|<span data-ttu-id="e2cac-279">typescript</span><span class="sxs-lookup"><span data-stu-id="e2cac-279">typescript</span></span>|
|<span data-ttu-id="e2cac-280">VB</span><span class="sxs-lookup"><span data-stu-id="e2cac-280">VB</span></span>|<span data-ttu-id="e2cac-281">vb</span><span class="sxs-lookup"><span data-stu-id="e2cac-281">vb</span></span>|
|<span data-ttu-id="e2cac-282">XAML</span><span class="sxs-lookup"><span data-stu-id="e2cac-282">XAML</span></span>|<span data-ttu-id="e2cac-283">xaml</span><span class="sxs-lookup"><span data-stu-id="e2cac-283">xaml</span></span>|
|<span data-ttu-id="e2cac-284">XML</span><span class="sxs-lookup"><span data-stu-id="e2cac-284">XML</span></span>|<span data-ttu-id="e2cac-285">xml</span><span class="sxs-lookup"><span data-stu-id="e2cac-285">xml</span></span>|

<span data-ttu-id="e2cac-286">A `csharp-interactive` név a C# nyelvre utal, valamint arra, hogy a böngészőből futtathatók a minták.</span><span class="sxs-lookup"><span data-stu-id="e2cac-286">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="e2cac-287">A kódrészletek lefordítása és végrehajtása egy Docker-tárolóban történik, és ennek a programvégrehajtásnak az eredménye jelenik meg a felhasználó böngészőablakában.</span><span class="sxs-lookup"><span data-stu-id="e2cac-287">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="e2cac-288">Példa: C\#</span><span class="sxs-lookup"><span data-stu-id="e2cac-288">Example: C\#</span></span>

<span data-ttu-id="e2cac-289">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="e2cac-289">__Markdown__</span></span>

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

<span data-ttu-id="e2cac-290">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="e2cac-290">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="e2cac-291">Példa: SQL</span><span class="sxs-lookup"><span data-stu-id="e2cac-291">Example: SQL</span></span>

<span data-ttu-id="e2cac-292">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="e2cac-292">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="e2cac-293">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="e2cac-293">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="e2cac-294">Egyedi OPS Markdown-bővítmények</span><span class="sxs-lookup"><span data-stu-id="e2cac-294">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="e2cac-295">Az Open Publishing Services (OPS) a Markdig Parser Markdownt implementálja, amely nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM).</span><span class="sxs-lookup"><span data-stu-id="e2cac-295">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="e2cac-296">A Markdig néhány funkciót biztosít a Markdown-bővítmények révén.</span><span class="sxs-lookup"><span data-stu-id="e2cac-296">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="e2cac-297">A jelen útmutatóban az OPS teljes szerzői útmutatójának kiválasztott témakörei szerepelnek referenciaként.</span><span class="sxs-lookup"><span data-stu-id="e2cac-297">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="e2cac-298">(Például lásd a „Markdig- és Markdown-bővítmények” és a „Kódrészletek” címeket a tartalomjegyzékben.)</span><span class="sxs-lookup"><span data-stu-id="e2cac-298">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="e2cac-299">A Docs-cikkek formázásának nagy része, például a bekezdések, a hivatkozások, a listák és a fejlécek a GFM használatával készülnek.</span><span class="sxs-lookup"><span data-stu-id="e2cac-299">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="e2cac-300">A kifinomultabb formázáshoz a cikkekben többek között az alábbi Markdig-funkciók használhatók:</span><span class="sxs-lookup"><span data-stu-id="e2cac-300">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="e2cac-301">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="e2cac-301">Note blocks</span></span>
- <span data-ttu-id="e2cac-302">Beágyazott fájlok</span><span class="sxs-lookup"><span data-stu-id="e2cac-302">Include files</span></span>
- <span data-ttu-id="e2cac-303">Választómezők</span><span class="sxs-lookup"><span data-stu-id="e2cac-303">Selectors</span></span>
- <span data-ttu-id="e2cac-304">Beágyazott videók</span><span class="sxs-lookup"><span data-stu-id="e2cac-304">Embedded videos</span></span>
- <span data-ttu-id="e2cac-305">Kódrészletek és -minták</span><span class="sxs-lookup"><span data-stu-id="e2cac-305">Code snippets/samples</span></span>

<span data-ttu-id="e2cac-306">A teljes listát a tartalomjegyzék „Markdig- és Markdown-bővítmények” és „Kódrészletek” fejezetcíme alatt találhatja.</span><span class="sxs-lookup"><span data-stu-id="e2cac-306">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="e2cac-307">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="e2cac-307">Note blocks</span></span>

<span data-ttu-id="e2cac-308">A megjegyzésblokkok 4 típusa közül választhat, hogy felhívja a figyelmet adott tartalomra:</span><span class="sxs-lookup"><span data-stu-id="e2cac-308">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="e2cac-309">MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="e2cac-309">NOTE</span></span>
- <span data-ttu-id="e2cac-310">FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="e2cac-310">WARNING</span></span>
- <span data-ttu-id="e2cac-311">TIPP</span><span class="sxs-lookup"><span data-stu-id="e2cac-311">TIP</span></span>
- <span data-ttu-id="e2cac-312">FONTOS</span><span class="sxs-lookup"><span data-stu-id="e2cac-312">IMPORTANT</span></span>

<span data-ttu-id="e2cac-313">Általánosságban elmondható, hogy a megjegyzésblokkokat ritkán szabad használni, mert megtörhetik a cikk folytonosságát.</span><span class="sxs-lookup"><span data-stu-id="e2cac-313">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="e2cac-314">Bár a kódblokkok, képek, listák és hivatkozások használata a megjegyzésblokkokon belül is támogatott, törekedjen egyszerű és könnyen érthető megjegyzésblokkok írására.</span><span class="sxs-lookup"><span data-stu-id="e2cac-314">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="e2cac-315">Példák:</span><span class="sxs-lookup"><span data-stu-id="e2cac-315">Examples:</span></span>

```markdown
> [!NOTE]
> This is a NOTE

> [!WARNING]
> This is a WARNING

> [!TIP]
> This is a TIP

> [!IMPORTANT]
> This is IMPORTANT
```

<span data-ttu-id="e2cac-316">Ez a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-316">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="e2cac-317">Ez egy MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="e2cac-317">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="e2cac-318">Ez egy FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="e2cac-318">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="e2cac-319">Ez egy TIPP</span><span class="sxs-lookup"><span data-stu-id="e2cac-319">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2cac-320">Ez FONTOS</span><span class="sxs-lookup"><span data-stu-id="e2cac-320">This is IMPORTANT</span></span>

### <a name="include-files"></a><span data-ttu-id="e2cac-321">Beágyazott fájlok</span><span class="sxs-lookup"><span data-stu-id="e2cac-321">Include files</span></span>

<span data-ttu-id="e2cac-322">Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a Markdig fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra.</span><span class="sxs-lookup"><span data-stu-id="e2cac-322">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="e2cac-323">Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben.</span><span class="sxs-lookup"><span data-stu-id="e2cac-323">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="e2cac-324">A tartalmak újrafelhasználását háromféle beágyazás segíti:</span><span class="sxs-lookup"><span data-stu-id="e2cac-324">Three types of include references are available to help you reuse content:</span></span>

- <span data-ttu-id="e2cac-325">Beágyazott: Egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="e2cac-325">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="e2cac-326">Blokkszintű: Egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="e2cac-326">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="e2cac-327">Képek: Ez a képek normál beillesztésének megvalósítása a Docsban.</span><span class="sxs-lookup"><span data-stu-id="e2cac-327">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="e2cac-328">A soron belüli és blokk típusú fájl egy egyszerű Markdown- (.md) fájl.</span><span class="sxs-lookup"><span data-stu-id="e2cac-328">An inline or block include file is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="e2cac-329">Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="e2cac-329">It can contain any valid Markdown.</span></span> <span data-ttu-id="e2cac-330">Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="e2cac-330">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="e2cac-331">A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.</span><span class="sxs-lookup"><span data-stu-id="e2cac-331">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="e2cac-332">Néhány követelmény és megfontolandó szempont a beágyazott fájlokhoz:</span><span class="sxs-lookup"><span data-stu-id="e2cac-332">Here are requirements and considerations for include files:</span></span>

- <span data-ttu-id="e2cac-333">Bármikor használhat beágyazott fájlt, amikor ugyanazt a szöveget több cikkben is szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="e2cac-333">Use an include file whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="e2cac-334">A blokk típusú beágyazási hivatkozás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott.</span><span class="sxs-lookup"><span data-stu-id="e2cac-334">Use a block include reference for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="e2cac-335">Ne használja egy mondatnál kisebb terjedelmű szöveghez.</span><span class="sxs-lookup"><span data-stu-id="e2cac-335">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="e2cac-336">A beágyazott hivatkozások a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok Markdig-bővítményeket igényelnek.</span><span class="sxs-lookup"><span data-stu-id="e2cac-336">Include references won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="e2cac-337">Azok csak közzététel után jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e2cac-337">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="e2cac-338">Ügyeljen rá, hogy a beágyazott fájl teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó fájlnak a beágyazást megelőző vagy azt követő szövegétől.</span><span class="sxs-lookup"><span data-stu-id="e2cac-338">Ensure that all the text in an include file is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include file.</span></span> <span data-ttu-id="e2cac-339">Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan sztring jön létre a cikkben, amely megtöri a honosított felületet.</span><span class="sxs-lookup"><span data-stu-id="e2cac-339">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="e2cac-340">Ne alkalmazzon beágyazási hivatkozást más beágyazott fájlokon belül.</span><span class="sxs-lookup"><span data-stu-id="e2cac-340">Don't embed include references within other include files.</span></span> <span data-ttu-id="e2cac-341">Ez nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="e2cac-341">They are not supported.</span></span>
- <span data-ttu-id="e2cac-342">A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa.</span><span class="sxs-lookup"><span data-stu-id="e2cac-342">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="e2cac-343">A médiamappa gyökere nem tartalmazhat képfájlokat.</span><span class="sxs-lookup"><span data-stu-id="e2cac-343">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="e2cac-344">Ha a beágyazott fájl nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="e2cac-344">If the include file does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="e2cac-345">A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között.</span><span class="sxs-lookup"><span data-stu-id="e2cac-345">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="e2cac-346">Minden egyes beágyazási fájlhoz és cikkhez használjon külön fájlt, egyedi névvel.</span><span class="sxs-lookup"><span data-stu-id="e2cac-346">Use a separate file with a unique name for each include file and article.</span></span> <span data-ttu-id="e2cac-347">A médiafájlt tárolja a beágyazott fájlhoz társított médiamappában.</span><span class="sxs-lookup"><span data-stu-id="e2cac-347">Store the media file in the media folder that's associated with the include file.</span></span>
- <span data-ttu-id="e2cac-348">A cikkek ne tartalmazzanak kizárólag beágyazott fájlt.</span><span class="sxs-lookup"><span data-stu-id="e2cac-348">Don't use an include file as the only content of an article.</span></span>  <span data-ttu-id="e2cac-349">A beágyazott fájlok a cikk többi része tartalmának kiegészítésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="e2cac-349">Include files are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="e2cac-350">Példa:</span><span class="sxs-lookup"><span data-stu-id="e2cac-350">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="e2cac-351">Választómezők</span><span class="sxs-lookup"><span data-stu-id="e2cac-351">Selectors</span></span>

<span data-ttu-id="e2cac-352">Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg az eltérő technológiák és platformok különbségeinek figyelembevételével.</span><span class="sxs-lookup"><span data-stu-id="e2cac-352">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="e2cac-353">Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb.</span><span class="sxs-lookup"><span data-stu-id="e2cac-353">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="e2cac-354">A Markdigben jelenleg kétféle választómező van, az egyszerű és a többszintű.</span><span class="sxs-lookup"><span data-stu-id="e2cac-354">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="e2cac-355">Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="e2cac-355">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include file.</span></span> <span data-ttu-id="e2cac-356">Később erre a beágyazott fájlra hivatkozhat az összes olyan témakörben, amely ugyanazt a választómezőt használja.</span><span class="sxs-lookup"><span data-stu-id="e2cac-356">Then you can reference that include file in all your articles that use the same selector.</span></span>

<span data-ttu-id="e2cac-357">Ezen a példán egy választómező látható.</span><span class="sxs-lookup"><span data-stu-id="e2cac-357">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="e2cac-358">Az [Azure dokumentációjában](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic) láthatja a választómezők működését.</span><span class="sxs-lookup"><span data-stu-id="e2cac-358">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-include-references"></a><span data-ttu-id="e2cac-359">Kódbeágyazási hivatkozások</span><span class="sxs-lookup"><span data-stu-id="e2cac-359">Code include references</span></span>

<span data-ttu-id="e2cac-360">A Markdig a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="e2cac-360">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="e2cac-361">A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:</span><span class="sxs-lookup"><span data-stu-id="e2cac-361">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="e2cac-362">Központosított kódminták vagy -részletek beágyazása külső tárházból.</span><span class="sxs-lookup"><span data-stu-id="e2cac-362">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="e2cac-363">Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e2cac-363">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="e2cac-364">Tipikus hibák és hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="e2cac-364">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="e2cac-365">Helyettesítő szöveg</span><span class="sxs-lookup"><span data-stu-id="e2cac-365">Alt text</span></span>

<span data-ttu-id="e2cac-366">Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen.</span><span class="sxs-lookup"><span data-stu-id="e2cac-366">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="e2cac-367">Például a következő szöveg helyett:</span><span class="sxs-lookup"><span data-stu-id="e2cac-367">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="e2cac-368">Az aláhúzás jeleket így jelenítheti meg:</span><span class="sxs-lookup"><span data-stu-id="e2cac-368">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="e2cac-369">Aposztrófok és idézőjelek</span><span class="sxs-lookup"><span data-stu-id="e2cac-369">Apostrophes and quotation marks</span></span>

<span data-ttu-id="e2cac-370">Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="e2cac-370">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="e2cac-371">Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni,</span><span class="sxs-lookup"><span data-stu-id="e2cac-371">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="e2cac-372">különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="e2cac-372">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="e2cac-373">Ezen írásjelek „intelligens” verzióinak kódolásai a következők:</span><span class="sxs-lookup"><span data-stu-id="e2cac-373">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="e2cac-374">Bal oldali (nyitó) idézőjel: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="e2cac-374">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="e2cac-375">Jobb oldali (záró) idézőjel: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="e2cac-375">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="e2cac-376">Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="e2cac-376">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="e2cac-377">Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="e2cac-377">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="e2cac-378">Csúcsos zárójelek</span><span class="sxs-lookup"><span data-stu-id="e2cac-378">Angle brackets</span></span>

<span data-ttu-id="e2cac-379">Helyőrzők jelölésére általában csúcsos zárójeleket alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="e2cac-379">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="e2cac-380">Ha ezt szövegben használja (és nem kódban), a csúcsos zárójelet kódolnia kell.</span><span class="sxs-lookup"><span data-stu-id="e2cac-380">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="e2cac-381">Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.</span><span class="sxs-lookup"><span data-stu-id="e2cac-381">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="e2cac-382">A `<script name>` kódolása például a következő: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="e2cac-382">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="e2cac-383">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e2cac-383">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="e2cac-384">Markdown-források</span><span class="sxs-lookup"><span data-stu-id="e2cac-384">Markdown resources</span></span>

- <span data-ttu-id="e2cac-385">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)</span><span class="sxs-lookup"><span data-stu-id="e2cac-385">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="e2cac-386">Markdown-segédlet a Docshoz</span><span class="sxs-lookup"><span data-stu-id="e2cac-386">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="e2cac-387">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)</span><span class="sxs-lookup"><span data-stu-id="e2cac-387">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
- [<span data-ttu-id="e2cac-388">Markdown-útmutató</span><span class="sxs-lookup"><span data-stu-id="e2cac-388">The Markdown Guide</span></span>](https://www.markdownguide.org/)
