---
title: A Markdown használata Docs-tartalmak írásához
description: Ez a cikk alapvető információkat és tájékoztatást nyújt a docs.microsoft.com-cikkekben használt Markdown jelölőnyelvről.
ms.date: 07/13/2017
ms.openlocfilehash: ef75ffd59b75db5757822642f651d863906cf14c
ms.sourcegitcommit: 18c271ebec920bb976a4bc901f4ab8c1d36b02fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53615835"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="d069c-103">A Markdown használata Docs-tartalmak írásához</span><span class="sxs-lookup"><span data-stu-id="d069c-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="d069c-104">A [docs.microsoft.com](http://docs.microsoft.com) cikkei a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="d069c-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="d069c-105">Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="d069c-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="d069c-106">Mivel a Docs-tartalmak a GitHubon vannak tárolva, azokhoz használható a Markdown [GitHub-stílusú Markdown (GFM)](https://help.github.com/categories/writing-on-github/) nevű bővítése, amely további funkciókat biztosít a gyakori formázási igényekhez.</span><span class="sxs-lookup"><span data-stu-id="d069c-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="d069c-107">Ezen kívül az Open Publishing Services (OPS) a Markdig Markdown Parsert implementálja.</span><span class="sxs-lookup"><span data-stu-id="d069c-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="d069c-108">A Markdig nagy mértékben kompatibilis a GFM-mel, és további funkciókkal támogatja a Docs specifikus szolgáltatásainak használatát.</span><span class="sxs-lookup"><span data-stu-id="d069c-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="d069c-109">A Markdig egy gyors, hatékony, CommonMark-megfelelőséggel rendelkező, bővíthető Markdown-feldolgozó .NET környezetekhez.</span><span class="sxs-lookup"><span data-stu-id="d069c-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="d069c-110">Jobb közösségi támogatás</span><span class="sxs-lookup"><span data-stu-id="d069c-110">Better community support</span></span>
* <span data-ttu-id="d069c-111">Jobb szabványtámogatás</span><span class="sxs-lookup"><span data-stu-id="d069c-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="d069c-112">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="d069c-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="d069c-113">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="d069c-113">Headings</span></span>

<span data-ttu-id="d069c-114">Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="d069c-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="d069c-115">A címsorokat atx-stílussal kell megadni. Ez azt jelenti, hogy 1–6 kettőskereszt karaktert (#) kell a sor elejére írni, a számuk a H1–H6 HTML-címsorszintjét jelöli.</span><span class="sxs-lookup"><span data-stu-id="d069c-115">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="d069c-116">Fent a címsorokra látható példa, az elsőtől a negyedik szintig.</span><span class="sxs-lookup"><span data-stu-id="d069c-116">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="d069c-117">Egy témakörben **egy és csak egy** első szintű címsornak (H1) kell lennie, ez fog megjelenni a lapon címként.</span><span class="sxs-lookup"><span data-stu-id="d069c-117">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="d069c-118">Ha `#` a cím az utolsó karaktere, akkor még egy `#` karaktert kell a cím végére írni ahhoz, hogy helyesen jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="d069c-118">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="d069c-119">Például így: `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="d069c-119">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="d069c-120">A második szintű címsorokból generálódik a lapon lévő tartalomjegyzék, ez jelenik meg a lap címe alatti „A cikk tartalma” szakaszban.</span><span class="sxs-lookup"><span data-stu-id="d069c-120">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="d069c-121">Félkövér és dőlt szöveg</span><span class="sxs-lookup"><span data-stu-id="d069c-121">Bold and italic text</span></span>

<span data-ttu-id="d069c-122">A **félkövérként** formázandó szöveget zárja dupla csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="d069c-122">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="d069c-123">A *dőltként* formázandó szöveget zárja egyszeres csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="d069c-123">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="d069c-124">A ***félkövérként és dőltként*** is formázandó szöveget zárja háromszoros csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="d069c-124">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="d069c-125">Idézetblokkok</span><span class="sxs-lookup"><span data-stu-id="d069c-125">Blockquotes</span></span>

<span data-ttu-id="d069c-126">Az idézetblokkok létrehozására a `>` karakter használatos:</span><span class="sxs-lookup"><span data-stu-id="d069c-126">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="d069c-127">Az előző példa a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-127">The preceding example renders as follows:</span></span>

> <span data-ttu-id="d069c-128">Ekkorra már tízmillió éve aszályos volt az időjárás, és a rettentő gyíkok uralma már rég véget ért.</span><span class="sxs-lookup"><span data-stu-id="d069c-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="d069c-129">Itt az egyenlítőnél, a később Afrika néven ismert kontinensen példátlan hevességű lett a létért folyó harc, a győztes pedig még fel sem tűnt a láthatáron.</span><span class="sxs-lookup"><span data-stu-id="d069c-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="d069c-130">Ezen a sivár és kiszikkadt vidéken csak az apró, a gyors és a harcias tudott életben maradni, vagy akár csak reménykedni is benne.</span><span class="sxs-lookup"><span data-stu-id="d069c-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="d069c-131">Listák</span><span class="sxs-lookup"><span data-stu-id="d069c-131">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="d069c-132">Rendezetlen listák</span><span class="sxs-lookup"><span data-stu-id="d069c-132">Unordered list</span></span>

<span data-ttu-id="d069c-133">Rendezetlen vagy listajeles listákat csillagokkal vagy kötőjelekkel formázhat.</span><span class="sxs-lookup"><span data-stu-id="d069c-133">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="d069c-134">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="d069c-134">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="d069c-135">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-135">will be rendered as:</span></span>

- <span data-ttu-id="d069c-136">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-136">List item 1</span></span>
- <span data-ttu-id="d069c-137">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-137">List item 2</span></span>
- <span data-ttu-id="d069c-138">3. listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-138">List item 3</span></span>

<span data-ttu-id="d069c-139">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="d069c-139">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="d069c-140">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="d069c-140">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="d069c-141">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-141">will be rendered as:</span></span>

- <span data-ttu-id="d069c-142">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-142">List item 1</span></span>
  - <span data-ttu-id="d069c-143">A listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-143">List item A</span></span>
  - <span data-ttu-id="d069c-144">B listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-144">List item B</span></span>
- <span data-ttu-id="d069c-145">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="d069c-145">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="d069c-146">Rendezett lista</span><span class="sxs-lookup"><span data-stu-id="d069c-146">Ordered list</span></span>

<span data-ttu-id="d069c-147">Rendezett vagy lépéseket ismertető listákat a megfelelő számok használatával formázhat.</span><span class="sxs-lookup"><span data-stu-id="d069c-147">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="d069c-148">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="d069c-148">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="d069c-149">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-149">will be rendered as:</span></span>

1. <span data-ttu-id="d069c-150">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-150">First instruction</span></span>
2. <span data-ttu-id="d069c-151">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-151">Second instruction</span></span>
3. <span data-ttu-id="d069c-152">Harmadik utasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-152">Third instruction</span></span>

<span data-ttu-id="d069c-153">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="d069c-153">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="d069c-154">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="d069c-154">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="d069c-155">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-155">will be rendered as:</span></span>

1. <span data-ttu-id="d069c-156">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-156">First instruction</span></span>
   1. <span data-ttu-id="d069c-157">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-157">Sub-instruction</span></span>
   2. <span data-ttu-id="d069c-158">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-158">Sub-instruction</span></span>
2. <span data-ttu-id="d069c-159">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="d069c-159">Second instruction</span></span>

<span data-ttu-id="d069c-160">Felhívjuk figyelmét, hogy minden bejegyzésnél az „1.”</span><span class="sxs-lookup"><span data-stu-id="d069c-160">Note that we use '1.'</span></span> <span data-ttu-id="d069c-161">jelölést használjuk.</span><span class="sxs-lookup"><span data-stu-id="d069c-161">for all entries.</span></span> <span data-ttu-id="d069c-162">Ez megkönnyíti az eltérések ellenőrzését, ha a későbbi frissítésekbe új lépések kerülnek, vagy törlünk a lépések közül.</span><span class="sxs-lookup"><span data-stu-id="d069c-162">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="d069c-163">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="d069c-163">Tables</span></span>

<span data-ttu-id="d069c-164">A táblázatok nem szerepelnek a Markdown alapspecifikációjában, de a GFM-ben támogatottak.</span><span class="sxs-lookup"><span data-stu-id="d069c-164">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="d069c-165">Táblázatokat a függőleges vonal (|) és a kötőjel (-) karakterekkel hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="d069c-165">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="d069c-166">A kötőjelekkel hozhatja létre az egyes oszlopok fejléceit, a függőleges vonalakkal pedig az oszlopokat választja el egymástól.</span><span class="sxs-lookup"><span data-stu-id="d069c-166">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="d069c-167">A táblázat elé szúrjon be egy üres sort, hogy az megfelelően jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="d069c-167">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="d069c-168">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="d069c-168">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="d069c-169">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-169">will be rendered as:</span></span>

| <span data-ttu-id="d069c-170">Így</span><span class="sxs-lookup"><span data-stu-id="d069c-170">Fun</span></span>                  | <span data-ttu-id="d069c-171">Néznek ki a</span><span class="sxs-lookup"><span data-stu-id="d069c-171">With</span></span>                 | <span data-ttu-id="d069c-172">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="d069c-172">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="d069c-173">balra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="d069c-173">left-aligned column</span></span>  | <span data-ttu-id="d069c-174">jobbra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="d069c-174">right-aligned column</span></span> | <span data-ttu-id="d069c-175">középre igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="d069c-175">centered column</span></span> |
| <span data-ttu-id="d069c-176">$100</span><span class="sxs-lookup"><span data-stu-id="d069c-176">$100</span></span>                 | <span data-ttu-id="d069c-177">$100</span><span class="sxs-lookup"><span data-stu-id="d069c-177">$100</span></span>                 | <span data-ttu-id="d069c-178">$100</span><span class="sxs-lookup"><span data-stu-id="d069c-178">$100</span></span>            |
| <span data-ttu-id="d069c-179">$10</span><span class="sxs-lookup"><span data-stu-id="d069c-179">$10</span></span>                  | <span data-ttu-id="d069c-180">$10</span><span class="sxs-lookup"><span data-stu-id="d069c-180">$10</span></span>                  | <span data-ttu-id="d069c-181">$10</span><span class="sxs-lookup"><span data-stu-id="d069c-181">$10</span></span>             |
| <span data-ttu-id="d069c-182">$1</span><span class="sxs-lookup"><span data-stu-id="d069c-182">$1</span></span>                   | <span data-ttu-id="d069c-183">$1</span><span class="sxs-lookup"><span data-stu-id="d069c-183">$1</span></span>                   | <span data-ttu-id="d069c-184">$1</span><span class="sxs-lookup"><span data-stu-id="d069c-184">$1</span></span>              |

<span data-ttu-id="d069c-185">További információ a táblázatok létrehozásáról:</span><span class="sxs-lookup"><span data-stu-id="d069c-185">For more information on creating tables, see:</span></span>

- <span data-ttu-id="d069c-186">A Markdig széles táblázatok formázását segítő [táblázatbehatárolási funkcióját](#table-wrapping) ismertető szakasz.</span><span class="sxs-lookup"><span data-stu-id="d069c-186">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="d069c-187">Az [Információk rendszerezése táblázatokkal](https://help.github.com/articles/organizing-information-with-tables/) című GitHub-cikk.</span><span class="sxs-lookup"><span data-stu-id="d069c-187">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="d069c-188">A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás.</span><span class="sxs-lookup"><span data-stu-id="d069c-188">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="d069c-189">[Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet).</span><span class="sxs-lookup"><span data-stu-id="d069c-189">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="d069c-190">[Michel Fortin: Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="d069c-190">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="d069c-191">[HTML-táblázatok konvertálása Markdown-formátumra](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="d069c-191">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="d069c-192">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="d069c-192">Links</span></span>

<span data-ttu-id="d069c-193">A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:</span><span class="sxs-lookup"><span data-stu-id="d069c-193">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="d069c-194">További információ a hivatkozások használatáról:</span><span class="sxs-lookup"><span data-stu-id="d069c-194">For more information on linking, see:</span></span>

- <span data-ttu-id="d069c-195">A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.</span><span class="sxs-lookup"><span data-stu-id="d069c-195">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="d069c-196">A Markdig által biztosított hivatkozási szintaxisról a jelen útmutató [Hivatkozások](how-to-write-links.md) című oldalán található részletesebb információ.</span><span class="sxs-lookup"><span data-stu-id="d069c-196">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="d069c-197">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="d069c-197">Code snippets</span></span>

<span data-ttu-id="d069c-198">A Markdown támogatja a kódrészletek mondaton belüli, illetve mondatok közötti, „elkülönített” blokkban való elhelyezését is.</span><span class="sxs-lookup"><span data-stu-id="d069c-198">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="d069c-199">További részletek:</span><span class="sxs-lookup"><span data-stu-id="d069c-199">For details, see:</span></span>

- [<span data-ttu-id="d069c-200">A Markdown natív kódrészlet-támogatása</span><span class="sxs-lookup"><span data-stu-id="d069c-200">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="d069c-201">GFM-támogatás kód elkülönítéséhez és szintaxiskiemeléshez</span><span class="sxs-lookup"><span data-stu-id="d069c-201">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="d069c-202">Az elkülönített kódblokkokban egyszerűen kiemelhető a kódrészletek szintaxisa.</span><span class="sxs-lookup"><span data-stu-id="d069c-202">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="d069c-203">Az elkülönített kódblokkok általános formátuma a következő:</span><span class="sxs-lookup"><span data-stu-id="d069c-203">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="d069c-204">A három kezdő „\`” karakter utáni alias határozza meg a használni kívánt szintaxiskiemelést.</span><span class="sxs-lookup"><span data-stu-id="d069c-204">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="d069c-205">Az alábbi lista felsorolja a Docs-tartalmakban gyakran használt programozási nyelveket és a hozzájuk tartozó címkét:</span><span class="sxs-lookup"><span data-stu-id="d069c-205">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="d069c-206">Ezekhez a nyelvekhez a rendszer támogatja a névformázást, és legtöbbjük esetében szintaxiskiemelést is nyújt.</span><span class="sxs-lookup"><span data-stu-id="d069c-206">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="d069c-207">Név</span><span class="sxs-lookup"><span data-stu-id="d069c-207">Name</span></span>|<span data-ttu-id="d069c-208">Markdown-címke</span><span class="sxs-lookup"><span data-stu-id="d069c-208">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="d069c-209">.NET-konzol</span><span class="sxs-lookup"><span data-stu-id="d069c-209">.NET Console</span></span>|<span data-ttu-id="d069c-210">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="d069c-210">dotnetcli</span></span>|
|<span data-ttu-id="d069c-211">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="d069c-211">ASP.NET (C#)</span></span>|<span data-ttu-id="d069c-212">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="d069c-212">aspx-csharp</span></span>|
|<span data-ttu-id="d069c-213">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="d069c-213">ASP.NET (VB)</span></span>|<span data-ttu-id="d069c-214">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="d069c-214">aspx-vb</span></span>|
|<span data-ttu-id="d069c-215">AzCopy</span><span class="sxs-lookup"><span data-stu-id="d069c-215">AzCopy</span></span>|<span data-ttu-id="d069c-216">azcopy</span><span class="sxs-lookup"><span data-stu-id="d069c-216">azcopy</span></span>|
|<span data-ttu-id="d069c-217">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="d069c-217">Azure CLI</span></span>|<span data-ttu-id="d069c-218">azurecli</span><span class="sxs-lookup"><span data-stu-id="d069c-218">azurecli</span></span>|
|<span data-ttu-id="d069c-219">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d069c-219">Azure PowerShell</span></span>|<span data-ttu-id="d069c-220">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="d069c-220">azurepowershell</span></span>|
|<span data-ttu-id="d069c-221">C++</span><span class="sxs-lookup"><span data-stu-id="d069c-221">C++</span></span>|<span data-ttu-id="d069c-222">cpp</span><span class="sxs-lookup"><span data-stu-id="d069c-222">cpp</span></span>|
|<span data-ttu-id="d069c-223">C++/CX</span><span class="sxs-lookup"><span data-stu-id="d069c-223">C++/CX</span></span>|<span data-ttu-id="d069c-224">cppcx</span><span class="sxs-lookup"><span data-stu-id="d069c-224">cppcx</span></span>|
|<span data-ttu-id="d069c-225">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="d069c-225">C++/WinRT</span></span>|<span data-ttu-id="d069c-226">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="d069c-226">cppwinrt</span></span>|
|<span data-ttu-id="d069c-227">C#</span><span class="sxs-lookup"><span data-stu-id="d069c-227">C#</span></span>|<span data-ttu-id="d069c-228">csharp</span><span class="sxs-lookup"><span data-stu-id="d069c-228">csharp</span></span>|
|<span data-ttu-id="d069c-229">C# böngészőben</span><span class="sxs-lookup"><span data-stu-id="d069c-229">C# in browser</span></span>|<span data-ttu-id="d069c-230">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="d069c-230">csharp-interactive</span></span>|
|<span data-ttu-id="d069c-231">Konzol</span><span class="sxs-lookup"><span data-stu-id="d069c-231">Console</span></span>|<span data-ttu-id="d069c-232">console</span><span class="sxs-lookup"><span data-stu-id="d069c-232">console</span></span>|
|<span data-ttu-id="d069c-233">CSHTML</span><span class="sxs-lookup"><span data-stu-id="d069c-233">CSHTML</span></span>|<span data-ttu-id="d069c-234">cshtml</span><span class="sxs-lookup"><span data-stu-id="d069c-234">cshtml</span></span>|
|<span data-ttu-id="d069c-235">DAX</span><span class="sxs-lookup"><span data-stu-id="d069c-235">DAX</span></span>|<span data-ttu-id="d069c-236">dax</span><span class="sxs-lookup"><span data-stu-id="d069c-236">dax</span></span>|
|<span data-ttu-id="d069c-237">F#</span><span class="sxs-lookup"><span data-stu-id="d069c-237">F#</span></span>|<span data-ttu-id="d069c-238">fsharp</span><span class="sxs-lookup"><span data-stu-id="d069c-238">fsharp</span></span>|
|<span data-ttu-id="d069c-239">Go</span><span class="sxs-lookup"><span data-stu-id="d069c-239">Go</span></span>|<span data-ttu-id="d069c-240">go</span><span class="sxs-lookup"><span data-stu-id="d069c-240">go</span></span>|
|<span data-ttu-id="d069c-241">HTML</span><span class="sxs-lookup"><span data-stu-id="d069c-241">HTML</span></span>|<span data-ttu-id="d069c-242">html</span><span class="sxs-lookup"><span data-stu-id="d069c-242">html</span></span>|
|<span data-ttu-id="d069c-243">HTTP</span><span class="sxs-lookup"><span data-stu-id="d069c-243">HTTP</span></span>|<span data-ttu-id="d069c-244">http</span><span class="sxs-lookup"><span data-stu-id="d069c-244">http</span></span>|
|<span data-ttu-id="d069c-245">Java</span><span class="sxs-lookup"><span data-stu-id="d069c-245">Java</span></span>|<span data-ttu-id="d069c-246">java</span><span class="sxs-lookup"><span data-stu-id="d069c-246">java</span></span>|
|<span data-ttu-id="d069c-247">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d069c-247">JavaScript</span></span>|<span data-ttu-id="d069c-248">javascript</span><span class="sxs-lookup"><span data-stu-id="d069c-248">javascript</span></span>|
|<span data-ttu-id="d069c-249">JSON</span><span class="sxs-lookup"><span data-stu-id="d069c-249">JSON</span></span>|<span data-ttu-id="d069c-250">json</span><span class="sxs-lookup"><span data-stu-id="d069c-250">json</span></span>|
|<span data-ttu-id="d069c-251">Markdown</span><span class="sxs-lookup"><span data-stu-id="d069c-251">Markdown</span></span>|<span data-ttu-id="d069c-252">md</span><span class="sxs-lookup"><span data-stu-id="d069c-252">md</span></span>|
|<span data-ttu-id="d069c-253">NodeJS</span><span class="sxs-lookup"><span data-stu-id="d069c-253">NodeJS</span></span>|<span data-ttu-id="d069c-254">nodejs</span><span class="sxs-lookup"><span data-stu-id="d069c-254">nodejs</span></span>|
|<span data-ttu-id="d069c-255">Objective-C</span><span class="sxs-lookup"><span data-stu-id="d069c-255">Objective-C</span></span>|<span data-ttu-id="d069c-256">objc</span><span class="sxs-lookup"><span data-stu-id="d069c-256">objc</span></span>|
|<span data-ttu-id="d069c-257">OData</span><span class="sxs-lookup"><span data-stu-id="d069c-257">OData</span></span>|<span data-ttu-id="d069c-258">odata</span><span class="sxs-lookup"><span data-stu-id="d069c-258">odata</span></span>|
|<span data-ttu-id="d069c-259">PHP</span><span class="sxs-lookup"><span data-stu-id="d069c-259">PHP</span></span>|<span data-ttu-id="d069c-260">php</span><span class="sxs-lookup"><span data-stu-id="d069c-260">php</span></span>|
|<span data-ttu-id="d069c-261">PowerApps (pont a tizedes elválasztó)</span><span class="sxs-lookup"><span data-stu-id="d069c-261">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="d069c-262">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="d069c-262">powerapps-dot</span></span>|
|<span data-ttu-id="d069c-263">PowerApps (vessző a tizedes elválasztó)</span><span class="sxs-lookup"><span data-stu-id="d069c-263">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="d069c-264">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="d069c-264">powerapps-comma</span></span>|
|<span data-ttu-id="d069c-265">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d069c-265">PowerShell</span></span>|<span data-ttu-id="d069c-266">powershell</span><span class="sxs-lookup"><span data-stu-id="d069c-266">powershell</span></span>|
|<span data-ttu-id="d069c-267">Python</span><span class="sxs-lookup"><span data-stu-id="d069c-267">Python</span></span>|<span data-ttu-id="d069c-268">python</span><span class="sxs-lookup"><span data-stu-id="d069c-268">python</span></span>|
|<span data-ttu-id="d069c-269">Q#</span><span class="sxs-lookup"><span data-stu-id="d069c-269">Q#</span></span>|<span data-ttu-id="d069c-270">qsharp</span><span class="sxs-lookup"><span data-stu-id="d069c-270">qsharp</span></span>|
|<span data-ttu-id="d069c-271">R</span><span class="sxs-lookup"><span data-stu-id="d069c-271">R</span></span>|<span data-ttu-id="d069c-272">r</span><span class="sxs-lookup"><span data-stu-id="d069c-272">r</span></span>|
|<span data-ttu-id="d069c-273">Ruby</span><span class="sxs-lookup"><span data-stu-id="d069c-273">Ruby</span></span>|<span data-ttu-id="d069c-274">ruby</span><span class="sxs-lookup"><span data-stu-id="d069c-274">ruby</span></span>|
|<span data-ttu-id="d069c-275">SQL</span><span class="sxs-lookup"><span data-stu-id="d069c-275">SQL</span></span>|<span data-ttu-id="d069c-276">sql</span><span class="sxs-lookup"><span data-stu-id="d069c-276">sql</span></span>|
|<span data-ttu-id="d069c-277">Swift</span><span class="sxs-lookup"><span data-stu-id="d069c-277">Swift</span></span>|<span data-ttu-id="d069c-278">swift</span><span class="sxs-lookup"><span data-stu-id="d069c-278">swift</span></span>|
|<span data-ttu-id="d069c-279">TypeScript</span><span class="sxs-lookup"><span data-stu-id="d069c-279">TypeScript</span></span>|<span data-ttu-id="d069c-280">typescript</span><span class="sxs-lookup"><span data-stu-id="d069c-280">typescript</span></span>|
|<span data-ttu-id="d069c-281">VB</span><span class="sxs-lookup"><span data-stu-id="d069c-281">VB</span></span>|<span data-ttu-id="d069c-282">vb</span><span class="sxs-lookup"><span data-stu-id="d069c-282">vb</span></span>|
|<span data-ttu-id="d069c-283">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="d069c-283">VSTS CLI</span></span>|<span data-ttu-id="d069c-284">vstscli</span><span class="sxs-lookup"><span data-stu-id="d069c-284">vstscli</span></span>|
|<span data-ttu-id="d069c-285">XAML</span><span class="sxs-lookup"><span data-stu-id="d069c-285">XAML</span></span>|<span data-ttu-id="d069c-286">xaml</span><span class="sxs-lookup"><span data-stu-id="d069c-286">xaml</span></span>|
|<span data-ttu-id="d069c-287">XML</span><span class="sxs-lookup"><span data-stu-id="d069c-287">XML</span></span>|<span data-ttu-id="d069c-288">xml</span><span class="sxs-lookup"><span data-stu-id="d069c-288">xml</span></span>|

<span data-ttu-id="d069c-289">A `csharp-interactive` név a C# nyelvre utal, valamint arra, hogy a böngészőből futtathatók a minták.</span><span class="sxs-lookup"><span data-stu-id="d069c-289">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="d069c-290">A kódrészletek lefordítása és végrehajtása egy Docker-tárolóban történik, és ennek a programvégrehajtásnak az eredménye jelenik meg a felhasználó böngészőablakában.</span><span class="sxs-lookup"><span data-stu-id="d069c-290">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="d069c-291">Példa: C\#</span><span class="sxs-lookup"><span data-stu-id="d069c-291">Example: C\#</span></span>

<span data-ttu-id="d069c-292">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="d069c-292">__Markdown__</span></span>

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

<span data-ttu-id="d069c-293">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="d069c-293">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="d069c-294">Példa: SQL</span><span class="sxs-lookup"><span data-stu-id="d069c-294">Example: SQL</span></span>

<span data-ttu-id="d069c-295">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="d069c-295">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="d069c-296">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="d069c-296">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="d069c-297">Egyedi OPS Markdown-bővítmények</span><span class="sxs-lookup"><span data-stu-id="d069c-297">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="d069c-298">Az Open Publishing Services (OPS) a Markdig Parser Markdownt implementálja, amely nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM).</span><span class="sxs-lookup"><span data-stu-id="d069c-298">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="d069c-299">A Markdig néhány funkciót biztosít a Markdown-bővítmények révén.</span><span class="sxs-lookup"><span data-stu-id="d069c-299">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="d069c-300">A jelen útmutatóban az OPS teljes szerzői útmutatójának kiválasztott témakörei szerepelnek referenciaként.</span><span class="sxs-lookup"><span data-stu-id="d069c-300">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="d069c-301">(Például lásd a „Markdig- és Markdown-bővítmények” és a „Kódrészletek” címeket a tartalomjegyzékben.)</span><span class="sxs-lookup"><span data-stu-id="d069c-301">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="d069c-302">A Docs-cikkek formázásának nagy része, például a bekezdések, a hivatkozások, a listák és a fejlécek a GFM használatával készülnek.</span><span class="sxs-lookup"><span data-stu-id="d069c-302">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="d069c-303">A kifinomultabb formázáshoz a cikkekben többek között az alábbi Markdig-funkciók használhatók:</span><span class="sxs-lookup"><span data-stu-id="d069c-303">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="d069c-304">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="d069c-304">Note blocks</span></span>
- <span data-ttu-id="d069c-305">Beágyazott fájlok</span><span class="sxs-lookup"><span data-stu-id="d069c-305">Include files</span></span>
- <span data-ttu-id="d069c-306">Választómezők</span><span class="sxs-lookup"><span data-stu-id="d069c-306">Selectors</span></span>
- <span data-ttu-id="d069c-307">Beágyazott videók</span><span class="sxs-lookup"><span data-stu-id="d069c-307">Embedded videos</span></span>
- <span data-ttu-id="d069c-308">Kódrészletek és -minták</span><span class="sxs-lookup"><span data-stu-id="d069c-308">Code snippets/samples</span></span>

<span data-ttu-id="d069c-309">A teljes listát a tartalomjegyzék „Markdig- és Markdown-bővítmények” és „Kódrészletek” fejezetcíme alatt találhatja.</span><span class="sxs-lookup"><span data-stu-id="d069c-309">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="d069c-310">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="d069c-310">Note blocks</span></span>

<span data-ttu-id="d069c-311">A megjegyzésblokkok 4 típusa közül választhat, hogy felhívja a figyelmet adott tartalomra:</span><span class="sxs-lookup"><span data-stu-id="d069c-311">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="d069c-312">MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="d069c-312">NOTE</span></span>
- <span data-ttu-id="d069c-313">FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="d069c-313">WARNING</span></span>
- <span data-ttu-id="d069c-314">TIPP</span><span class="sxs-lookup"><span data-stu-id="d069c-314">TIP</span></span>
- <span data-ttu-id="d069c-315">FONTOS</span><span class="sxs-lookup"><span data-stu-id="d069c-315">IMPORTANT</span></span>

<span data-ttu-id="d069c-316">Általánosságban elmondható, hogy a megjegyzésblokkokat ritkán szabad használni, mert megtörhetik a cikk folytonosságát.</span><span class="sxs-lookup"><span data-stu-id="d069c-316">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="d069c-317">Bár a kódblokkok, képek, listák és hivatkozások használata a megjegyzésblokkokon belül is támogatott, törekedjen egyszerű és könnyen érthető megjegyzésblokkok írására.</span><span class="sxs-lookup"><span data-stu-id="d069c-317">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="d069c-318">Példák:</span><span class="sxs-lookup"><span data-stu-id="d069c-318">Examples:</span></span>

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

<span data-ttu-id="d069c-319">Ez a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-319">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="d069c-320">Ez egy MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="d069c-320">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="d069c-321">Ez egy FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="d069c-321">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="d069c-322">Ez egy TIPP</span><span class="sxs-lookup"><span data-stu-id="d069c-322">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d069c-323">Ez FONTOS</span><span class="sxs-lookup"><span data-stu-id="d069c-323">This is IMPORTANT</span></span>

### <a name="include-files"></a><span data-ttu-id="d069c-324">Beágyazott fájlok</span><span class="sxs-lookup"><span data-stu-id="d069c-324">Include files</span></span>

<span data-ttu-id="d069c-325">Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a Markdig fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra.</span><span class="sxs-lookup"><span data-stu-id="d069c-325">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="d069c-326">Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben.</span><span class="sxs-lookup"><span data-stu-id="d069c-326">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="d069c-327">A tartalmak újrafelhasználását háromféle beágyazás segíti:</span><span class="sxs-lookup"><span data-stu-id="d069c-327">Three types of include references are available to help you reuse content:</span></span>

- <span data-ttu-id="d069c-328">Beágyazott: Egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d069c-328">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="d069c-329">Blokkszintű: Egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d069c-329">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="d069c-330">Képek: Ez a képek normál beillesztésének megvalósítása a Docsban.</span><span class="sxs-lookup"><span data-stu-id="d069c-330">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="d069c-331">A soron belüli és blokk típusú fájl egy egyszerű Markdown- (.md) fájl.</span><span class="sxs-lookup"><span data-stu-id="d069c-331">An inline or block include file is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="d069c-332">Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="d069c-332">It can contain any valid Markdown.</span></span> <span data-ttu-id="d069c-333">Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="d069c-333">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="d069c-334">A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.</span><span class="sxs-lookup"><span data-stu-id="d069c-334">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="d069c-335">Néhány követelmény és megfontolandó szempont a beágyazott fájlokhoz:</span><span class="sxs-lookup"><span data-stu-id="d069c-335">Here are requirements and considerations for include files:</span></span>

- <span data-ttu-id="d069c-336">Bármikor használhat beágyazott fájlt, amikor ugyanazt a szöveget több cikkben is szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="d069c-336">Use an include file whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="d069c-337">A blokk típusú beágyazási hivatkozás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott.</span><span class="sxs-lookup"><span data-stu-id="d069c-337">Use a block include reference for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="d069c-338">Ne használja egy mondatnál kisebb terjedelmű szöveghez.</span><span class="sxs-lookup"><span data-stu-id="d069c-338">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="d069c-339">A beágyazott hivatkozások a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok Markdig-bővítményeket igényelnek.</span><span class="sxs-lookup"><span data-stu-id="d069c-339">Include references won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="d069c-340">Azok csak közzététel után jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="d069c-340">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="d069c-341">Ügyeljen rá, hogy a beágyazott fájl teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó fájlnak a beágyazást megelőző vagy azt követő szövegétől.</span><span class="sxs-lookup"><span data-stu-id="d069c-341">Ensure that all the text in an include file is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include file.</span></span> <span data-ttu-id="d069c-342">Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan sztring jön létre a cikkben, amely megtöri a honosított felületet.</span><span class="sxs-lookup"><span data-stu-id="d069c-342">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="d069c-343">Ne alkalmazzon beágyazási hivatkozást más beágyazott fájlokon belül.</span><span class="sxs-lookup"><span data-stu-id="d069c-343">Don't embed include references within other include files.</span></span> <span data-ttu-id="d069c-344">Ez nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="d069c-344">They are not supported.</span></span>
- <span data-ttu-id="d069c-345">A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa.</span><span class="sxs-lookup"><span data-stu-id="d069c-345">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="d069c-346">A médiamappa gyökere nem tartalmazhat képfájlokat.</span><span class="sxs-lookup"><span data-stu-id="d069c-346">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="d069c-347">Ha a beágyazott fájl nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="d069c-347">If the include file does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="d069c-348">A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között.</span><span class="sxs-lookup"><span data-stu-id="d069c-348">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="d069c-349">Minden egyes beágyazási fájlhoz és cikkhez használjon külön fájlt, egyedi névvel.</span><span class="sxs-lookup"><span data-stu-id="d069c-349">Use a separate file with a unique name for each include file and article.</span></span> <span data-ttu-id="d069c-350">A médiafájlt tárolja a beágyazott fájlhoz társított médiamappában.</span><span class="sxs-lookup"><span data-stu-id="d069c-350">Store the media file in the media folder that's associated with the include file.</span></span>
- <span data-ttu-id="d069c-351">A cikkek ne tartalmazzanak kizárólag beágyazott fájlt.</span><span class="sxs-lookup"><span data-stu-id="d069c-351">Don't use an include file as the only content of an article.</span></span>  <span data-ttu-id="d069c-352">A beágyazott fájlok a cikk többi része tartalmának kiegészítésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="d069c-352">Include files are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="d069c-353">Példa:</span><span class="sxs-lookup"><span data-stu-id="d069c-353">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="d069c-354">Választómezők</span><span class="sxs-lookup"><span data-stu-id="d069c-354">Selectors</span></span>

<span data-ttu-id="d069c-355">Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg az eltérő technológiák és platformok különbségeinek figyelembevételével.</span><span class="sxs-lookup"><span data-stu-id="d069c-355">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="d069c-356">Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb.</span><span class="sxs-lookup"><span data-stu-id="d069c-356">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="d069c-357">A Markdigben jelenleg kétféle választómező van, az egyszerű és a többszintű.</span><span class="sxs-lookup"><span data-stu-id="d069c-357">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="d069c-358">Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="d069c-358">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include file.</span></span> <span data-ttu-id="d069c-359">Később erre a beágyazott fájlra hivatkozhat az összes olyan témakörben, amely ugyanazt a választómezőt használja.</span><span class="sxs-lookup"><span data-stu-id="d069c-359">Then you can reference that include file in all your articles that use the same selector.</span></span>

<span data-ttu-id="d069c-360">Ezen a példán egy választómező látható.</span><span class="sxs-lookup"><span data-stu-id="d069c-360">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="d069c-361">Az [Azure dokumentációjában](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic) láthatja a választómezők működését.</span><span class="sxs-lookup"><span data-stu-id="d069c-361">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-include-references"></a><span data-ttu-id="d069c-362">Kódbeágyazási hivatkozások</span><span class="sxs-lookup"><span data-stu-id="d069c-362">Code include references</span></span>

<span data-ttu-id="d069c-363">A Markdig a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="d069c-363">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="d069c-364">A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:</span><span class="sxs-lookup"><span data-stu-id="d069c-364">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="d069c-365">Központosított kódminták vagy -részletek beágyazása külső tárházból.</span><span class="sxs-lookup"><span data-stu-id="d069c-365">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="d069c-366">Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d069c-366">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="d069c-367">Tipikus hibák és hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="d069c-367">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="d069c-368">Helyettesítő szöveg</span><span class="sxs-lookup"><span data-stu-id="d069c-368">Alt text</span></span>

<span data-ttu-id="d069c-369">Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen.</span><span class="sxs-lookup"><span data-stu-id="d069c-369">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="d069c-370">Például a következő szöveg helyett:</span><span class="sxs-lookup"><span data-stu-id="d069c-370">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="d069c-371">Az aláhúzás jeleket így jelenítheti meg:</span><span class="sxs-lookup"><span data-stu-id="d069c-371">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="d069c-372">Aposztrófok és idézőjelek</span><span class="sxs-lookup"><span data-stu-id="d069c-372">Apostrophes and quotation marks</span></span>

<span data-ttu-id="d069c-373">Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="d069c-373">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="d069c-374">Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni,</span><span class="sxs-lookup"><span data-stu-id="d069c-374">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="d069c-375">különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="d069c-375">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="d069c-376">Ezen írásjelek „intelligens” verzióinak kódolásai a következők:</span><span class="sxs-lookup"><span data-stu-id="d069c-376">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="d069c-377">Bal oldali (nyitó) idézőjel: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="d069c-377">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="d069c-378">Jobb oldali (záró) idézőjel: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="d069c-378">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="d069c-379">Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="d069c-379">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="d069c-380">Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="d069c-380">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="d069c-381">Csúcsos zárójelek</span><span class="sxs-lookup"><span data-stu-id="d069c-381">Angle brackets</span></span>

<span data-ttu-id="d069c-382">Helyőrzők jelölésére általában csúcsos zárójeleket alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="d069c-382">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="d069c-383">Ha ezt szövegben használja (és nem kódban), a csúcsos zárójelet kódolnia kell.</span><span class="sxs-lookup"><span data-stu-id="d069c-383">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="d069c-384">Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.</span><span class="sxs-lookup"><span data-stu-id="d069c-384">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="d069c-385">A `<script name>` kódolása például a következő: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="d069c-385">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="d069c-386">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d069c-386">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="d069c-387">Markdown-források</span><span class="sxs-lookup"><span data-stu-id="d069c-387">Markdown resources</span></span>

- <span data-ttu-id="d069c-388">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)</span><span class="sxs-lookup"><span data-stu-id="d069c-388">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="d069c-389">Markdown-segédlet a Docshoz</span><span class="sxs-lookup"><span data-stu-id="d069c-389">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="d069c-390">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)</span><span class="sxs-lookup"><span data-stu-id="d069c-390">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
- [<span data-ttu-id="d069c-391">Markdown-útmutató</span><span class="sxs-lookup"><span data-stu-id="d069c-391">The Markdown Guide</span></span>](https://www.markdownguide.org/)
