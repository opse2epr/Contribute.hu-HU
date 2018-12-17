---
title: A Markdown használata Docs-tartalmak írásához
description: Ez a cikk alapvető információkat és tájékoztatást nyújt a docs.microsoft.com-cikkekben használt Markdown jelölőnyelvről.
ms.date: 07/13/2017
ms.openlocfilehash: 8613d525afc11caf9ec760c4f15ea44010781634
ms.sourcegitcommit: 21c9ac71e1abff946466cddf17a1ee97bc349ec5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245895"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="8c5d7-103">A Markdown használata Docs-tartalmak írásához</span><span class="sxs-lookup"><span data-stu-id="8c5d7-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="8c5d7-104">A [docs.microsoft.com](http://docs.microsoft.com) cikkei a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="8c5d7-105">Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="8c5d7-106">Mivel a Docs-tartalmak a GitHubon vannak tárolva, azokhoz használható a Markdown [GitHub-stílusú Markdown (GFM)](https://help.github.com/categories/writing-on-github/) nevű bővítése, amely további funkciókat biztosít a gyakori formázási igényekhez.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="8c5d7-107">Ezen kívül az Open Publishing Services (OPS) a Markdig Markdown Parsert implementálja.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="8c5d7-108">A Markdig nagy mértékben kompatibilis a GFM-mel, és további funkciókkal támogatja a Docs specifikus szolgáltatásainak használatát.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="8c5d7-109">A Markdig egy gyors, hatékony, CommonMark-megfelelőséggel rendelkező, bővíthető Markdown-feldolgozó .NET környezetekhez.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="8c5d7-110">Jobb közösségi támogatás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-110">Better community support</span></span>
* <span data-ttu-id="8c5d7-111">Jobb szabványtámogatás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="8c5d7-112">A Markdown alapjai</span><span class="sxs-lookup"><span data-stu-id="8c5d7-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="8c5d7-113">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="8c5d7-113">Headings</span></span>

<span data-ttu-id="8c5d7-114">Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="8c5d7-115">A címsorokat atx-stílussal kell megadni. Ez azt jelenti, hogy 1–6 kettőskereszt karaktert (#) kell a sor elejére írni, a számuk a H1–H6 HTML-címsorszintjét jelöli.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-115">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="8c5d7-116">Fent a címsorokra látható példa, az elsőtől a negyedik szintig.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-116">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="8c5d7-117">Egy témakörben **egy és csak egy** első szintű címsornak (H1) kell lennie, ez fog megjelenni a lapon címként.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-117">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="8c5d7-118">Ha `#` a cím az utolsó karaktere, akkor még egy `#` karaktert kell a cím végére írni ahhoz, hogy helyesen jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-118">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="8c5d7-119">Például így: `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-119">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="8c5d7-120">A második szintű címsorokból generálódik a lapon lévő tartalomjegyzék, ez jelenik meg a lap címe alatti „A cikk tartalma” szakaszban.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-120">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="8c5d7-121">Félkövér és dőlt szöveg</span><span class="sxs-lookup"><span data-stu-id="8c5d7-121">Bold and italic text</span></span>

<span data-ttu-id="8c5d7-122">A **félkövérként** formázandó szöveget zárja dupla csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-122">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="8c5d7-123">A *dőltként* formázandó szöveget zárja egyszeres csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-123">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="8c5d7-124">A ***félkövérként és dőltként*** is formázandó szöveget zárja háromszoros csillagjelek közé:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-124">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="8c5d7-125">Idézetblokkok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-125">Blockquotes</span></span>

<span data-ttu-id="8c5d7-126">Az idézetblokkok létrehozására a `>` karakter használatos:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-126">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="8c5d7-127">Az előző példa a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-127">The preceding example renders as follows:</span></span>

> <span data-ttu-id="8c5d7-128">Ekkorra már tízmillió éve aszályos volt az időjárás, és a rettentő gyíkok uralma már rég véget ért.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="8c5d7-129">Itt az egyenlítőnél, a később Afrika néven ismert kontinensen példátlan hevességű lett a létért folyó harc, a győztes pedig még fel sem tűnt a láthatáron.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="8c5d7-130">Ezen a sivár és kiszikkadt vidéken csak az apró, a gyors és a harcias tudott életben maradni, vagy akár csak reménykedni is benne.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="8c5d7-131">Listák</span><span class="sxs-lookup"><span data-stu-id="8c5d7-131">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="8c5d7-132">Rendezetlen listák</span><span class="sxs-lookup"><span data-stu-id="8c5d7-132">Unordered list</span></span>

<span data-ttu-id="8c5d7-133">Rendezetlen vagy listajeles listákat csillagokkal vagy kötőjelekkel formázhat.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-133">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="8c5d7-134">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-134">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="8c5d7-135">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-135">will be rendered as:</span></span>

- <span data-ttu-id="8c5d7-136">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-136">List item 1</span></span>
- <span data-ttu-id="8c5d7-137">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-137">List item 2</span></span>
- <span data-ttu-id="8c5d7-138">3. listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-138">List item 3</span></span>

<span data-ttu-id="8c5d7-139">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-139">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="8c5d7-140">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-140">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="8c5d7-141">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-141">will be rendered as:</span></span>

- <span data-ttu-id="8c5d7-142">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-142">List item 1</span></span>
  - <span data-ttu-id="8c5d7-143">A listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-143">List item A</span></span>
  - <span data-ttu-id="8c5d7-144">B listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-144">List item B</span></span>
- <span data-ttu-id="8c5d7-145">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="8c5d7-145">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="8c5d7-146">Rendezett lista</span><span class="sxs-lookup"><span data-stu-id="8c5d7-146">Ordered list</span></span>

<span data-ttu-id="8c5d7-147">Rendezett vagy lépéseket ismertető listákat a megfelelő számok használatával formázhat.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-147">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="8c5d7-148">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-148">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="8c5d7-149">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-149">will be rendered as:</span></span>

1. <span data-ttu-id="8c5d7-150">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-150">First instruction</span></span>
2. <span data-ttu-id="8c5d7-151">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-151">Second instruction</span></span>
3. <span data-ttu-id="8c5d7-152">Harmadik utasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-152">Third instruction</span></span>

<span data-ttu-id="8c5d7-153">Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-153">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="8c5d7-154">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-154">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="8c5d7-155">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-155">will be rendered as:</span></span>

1. <span data-ttu-id="8c5d7-156">Első utasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-156">First instruction</span></span>
   1. <span data-ttu-id="8c5d7-157">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-157">Sub-instruction</span></span>
   2. <span data-ttu-id="8c5d7-158">Alutasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-158">Sub-instruction</span></span>
2. <span data-ttu-id="8c5d7-159">Második utasítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-159">Second instruction</span></span>

<span data-ttu-id="8c5d7-160">Felhívjuk figyelmét, hogy minden bejegyzésnél az „1.”</span><span class="sxs-lookup"><span data-stu-id="8c5d7-160">Note that we use '1.'</span></span> <span data-ttu-id="8c5d7-161">jelölést használjuk.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-161">for all entries.</span></span> <span data-ttu-id="8c5d7-162">Ez megkönnyíti az eltérések ellenőrzését, ha a későbbi frissítésekbe új lépések kerülnek, vagy törlünk a lépések közül.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-162">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="8c5d7-163">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-163">Tables</span></span>

<span data-ttu-id="8c5d7-164">A táblázatok nem szerepelnek a Markdown alapspecifikációjában, de a GFM-ben támogatottak.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-164">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="8c5d7-165">Táblázatokat a függőleges vonal (|) és a kötőjel (-) karakterekkel hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-165">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="8c5d7-166">A kötőjelekkel hozhatja létre az egyes oszlopok fejléceit, a függőleges vonalakkal pedig az oszlopokat választja el egymástól.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-166">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="8c5d7-167">A táblázat elé szúrjon be egy üres sort, hogy az megfelelően jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-167">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="8c5d7-168">Például a következő Markdown-szöveg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-168">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="8c5d7-169">az alábbi módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-169">will be rendered as:</span></span>

| <span data-ttu-id="8c5d7-170">Így</span><span class="sxs-lookup"><span data-stu-id="8c5d7-170">Fun</span></span>                  | <span data-ttu-id="8c5d7-171">Néznek ki a</span><span class="sxs-lookup"><span data-stu-id="8c5d7-171">With</span></span>                 | <span data-ttu-id="8c5d7-172">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-172">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="8c5d7-173">balra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="8c5d7-173">left-aligned column</span></span>  | <span data-ttu-id="8c5d7-174">jobbra igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="8c5d7-174">right-aligned column</span></span> | <span data-ttu-id="8c5d7-175">középre igazított oszlop</span><span class="sxs-lookup"><span data-stu-id="8c5d7-175">centered column</span></span> |
| <span data-ttu-id="8c5d7-176">$100</span><span class="sxs-lookup"><span data-stu-id="8c5d7-176">$100</span></span>                 | <span data-ttu-id="8c5d7-177">$100</span><span class="sxs-lookup"><span data-stu-id="8c5d7-177">$100</span></span>                 | <span data-ttu-id="8c5d7-178">$100</span><span class="sxs-lookup"><span data-stu-id="8c5d7-178">$100</span></span>            |
| <span data-ttu-id="8c5d7-179">$10</span><span class="sxs-lookup"><span data-stu-id="8c5d7-179">$10</span></span>                  | <span data-ttu-id="8c5d7-180">$10</span><span class="sxs-lookup"><span data-stu-id="8c5d7-180">$10</span></span>                  | <span data-ttu-id="8c5d7-181">$10</span><span class="sxs-lookup"><span data-stu-id="8c5d7-181">$10</span></span>             |
| <span data-ttu-id="8c5d7-182">$1</span><span class="sxs-lookup"><span data-stu-id="8c5d7-182">$1</span></span>                   | <span data-ttu-id="8c5d7-183">$1</span><span class="sxs-lookup"><span data-stu-id="8c5d7-183">$1</span></span>                   | <span data-ttu-id="8c5d7-184">$1</span><span class="sxs-lookup"><span data-stu-id="8c5d7-184">$1</span></span>              |

<span data-ttu-id="8c5d7-185">További információ a táblázatok létrehozásáról:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-185">For more information on creating tables, see:</span></span>

- <span data-ttu-id="8c5d7-186">A Markdig széles táblázatok formázását segítő [táblázatbehatárolási funkcióját](#table-wrapping) ismertető szakasz.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-186">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="8c5d7-187">Az [Információk rendszerezése táblázatokkal](https://help.github.com/articles/organizing-information-with-tables/) című GitHub-cikk.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-187">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="8c5d7-188">A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-188">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="8c5d7-189">[Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet).</span><span class="sxs-lookup"><span data-stu-id="8c5d7-189">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="8c5d7-190">[Michel Fortin: Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="8c5d7-190">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="8c5d7-191">[HTML-táblázatok konvertálása Markdown-formátumra](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="8c5d7-191">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="8c5d7-192">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="8c5d7-192">Links</span></span>

<span data-ttu-id="8c5d7-193">A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-193">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="8c5d7-194">További információ a hivatkozások használatáról:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-194">For more information on linking, see:</span></span>

- <span data-ttu-id="8c5d7-195">A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-195">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="8c5d7-196">A Markdig által biztosított hivatkozási szintaxisról a jelen útmutató [Hivatkozások](how-to-write-links.md) című oldalán található részletesebb információ.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-196">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="8c5d7-197">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="8c5d7-197">Code snippets</span></span>

<span data-ttu-id="8c5d7-198">A Markdown támogatja a kódrészletek mondaton belüli, illetve mondatok közötti, „elkülönített” blokkban való elhelyezését is.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-198">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="8c5d7-199">További részletek:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-199">For details, see:</span></span>

- [<span data-ttu-id="8c5d7-200">A Markdown natív kódrészlet-támogatása</span><span class="sxs-lookup"><span data-stu-id="8c5d7-200">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="8c5d7-201">GFM-támogatás kód elkülönítéséhez és szintaxiskiemeléshez</span><span class="sxs-lookup"><span data-stu-id="8c5d7-201">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="8c5d7-202">Az elkülönített kódblokkokban egyszerűen kiemelhető a kódrészletek szintaxisa.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-202">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="8c5d7-203">Az elkülönített kódblokkok általános formátuma a következő:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-203">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="8c5d7-204">A három kezdő „\`” karakter utáni alias határozza meg a használni kívánt szintaxiskiemelést.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-204">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="8c5d7-205">Az alábbi lista felsorolja a Docs-tartalmakban gyakran használt programozási nyelveket és a hozzájuk tartozó címkét:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-205">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="8c5d7-206">Ezekhez a nyelvekhez a rendszer támogatja a névformázást, és legtöbbjük esetében szintaxiskiemelést is nyújt.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-206">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="8c5d7-207">Név</span><span class="sxs-lookup"><span data-stu-id="8c5d7-207">Name</span></span>|<span data-ttu-id="8c5d7-208">Markdown-címke</span><span class="sxs-lookup"><span data-stu-id="8c5d7-208">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="8c5d7-209">.NET-konzol</span><span class="sxs-lookup"><span data-stu-id="8c5d7-209">.NET Console</span></span>|<span data-ttu-id="8c5d7-210">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="8c5d7-210">dotnetcli</span></span>|
|<span data-ttu-id="8c5d7-211">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="8c5d7-211">ASP.NET (C#)</span></span>|<span data-ttu-id="8c5d7-212">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="8c5d7-212">aspx-csharp</span></span>|
|<span data-ttu-id="8c5d7-213">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="8c5d7-213">ASP.NET (VB)</span></span>|<span data-ttu-id="8c5d7-214">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="8c5d7-214">aspx-vb</span></span>|
|<span data-ttu-id="8c5d7-215">AzCopy</span><span class="sxs-lookup"><span data-stu-id="8c5d7-215">AzCopy</span></span>|<span data-ttu-id="8c5d7-216">azcopy</span><span class="sxs-lookup"><span data-stu-id="8c5d7-216">azcopy</span></span>|
|<span data-ttu-id="8c5d7-217">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="8c5d7-217">Azure CLI</span></span>|<span data-ttu-id="8c5d7-218">azurecli</span><span class="sxs-lookup"><span data-stu-id="8c5d7-218">azurecli</span></span>|
|<span data-ttu-id="8c5d7-219">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c5d7-219">Azure PowerShell</span></span>|<span data-ttu-id="8c5d7-220">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="8c5d7-220">azurepowershell</span></span>|
|<span data-ttu-id="8c5d7-221">C++</span><span class="sxs-lookup"><span data-stu-id="8c5d7-221">C++</span></span>|<span data-ttu-id="8c5d7-222">cpp</span><span class="sxs-lookup"><span data-stu-id="8c5d7-222">cpp</span></span>|
|<span data-ttu-id="8c5d7-223">C++/CX</span><span class="sxs-lookup"><span data-stu-id="8c5d7-223">C++/CX</span></span>|<span data-ttu-id="8c5d7-224">cppcx</span><span class="sxs-lookup"><span data-stu-id="8c5d7-224">cppcx</span></span>|
|<span data-ttu-id="8c5d7-225">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="8c5d7-225">C++/WinRT</span></span>|<span data-ttu-id="8c5d7-226">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="8c5d7-226">cppwinrt</span></span>|
|<span data-ttu-id="8c5d7-227">C#</span><span class="sxs-lookup"><span data-stu-id="8c5d7-227">C#</span></span>|<span data-ttu-id="8c5d7-228">csharp</span><span class="sxs-lookup"><span data-stu-id="8c5d7-228">csharp</span></span>|
|<span data-ttu-id="8c5d7-229">C# böngészőben</span><span class="sxs-lookup"><span data-stu-id="8c5d7-229">C# in browser</span></span>|<span data-ttu-id="8c5d7-230">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="8c5d7-230">csharp-interactive</span></span>|
|<span data-ttu-id="8c5d7-231">Konzol</span><span class="sxs-lookup"><span data-stu-id="8c5d7-231">Console</span></span>|<span data-ttu-id="8c5d7-232">console</span><span class="sxs-lookup"><span data-stu-id="8c5d7-232">console</span></span>|
|<span data-ttu-id="8c5d7-233">CSHTML</span><span class="sxs-lookup"><span data-stu-id="8c5d7-233">CSHTML</span></span>|<span data-ttu-id="8c5d7-234">cshtml</span><span class="sxs-lookup"><span data-stu-id="8c5d7-234">cshtml</span></span>|
|<span data-ttu-id="8c5d7-235">DAX</span><span class="sxs-lookup"><span data-stu-id="8c5d7-235">DAX</span></span>|<span data-ttu-id="8c5d7-236">dax</span><span class="sxs-lookup"><span data-stu-id="8c5d7-236">dax</span></span>|
|<span data-ttu-id="8c5d7-237">F#</span><span class="sxs-lookup"><span data-stu-id="8c5d7-237">F#</span></span>|<span data-ttu-id="8c5d7-238">fsharp</span><span class="sxs-lookup"><span data-stu-id="8c5d7-238">fsharp</span></span>|
|<span data-ttu-id="8c5d7-239">Go</span><span class="sxs-lookup"><span data-stu-id="8c5d7-239">Go</span></span>|<span data-ttu-id="8c5d7-240">go</span><span class="sxs-lookup"><span data-stu-id="8c5d7-240">go</span></span>|
|<span data-ttu-id="8c5d7-241">HTML</span><span class="sxs-lookup"><span data-stu-id="8c5d7-241">HTML</span></span>|<span data-ttu-id="8c5d7-242">html</span><span class="sxs-lookup"><span data-stu-id="8c5d7-242">html</span></span>|
|<span data-ttu-id="8c5d7-243">HTTP</span><span class="sxs-lookup"><span data-stu-id="8c5d7-243">HTTP</span></span>|<span data-ttu-id="8c5d7-244">http</span><span class="sxs-lookup"><span data-stu-id="8c5d7-244">http</span></span>|
|<span data-ttu-id="8c5d7-245">Java</span><span class="sxs-lookup"><span data-stu-id="8c5d7-245">Java</span></span>|<span data-ttu-id="8c5d7-246">java</span><span class="sxs-lookup"><span data-stu-id="8c5d7-246">java</span></span>|
|<span data-ttu-id="8c5d7-247">JavaScript</span><span class="sxs-lookup"><span data-stu-id="8c5d7-247">JavaScript</span></span>|<span data-ttu-id="8c5d7-248">javascript</span><span class="sxs-lookup"><span data-stu-id="8c5d7-248">javascript</span></span>|
|<span data-ttu-id="8c5d7-249">JSON</span><span class="sxs-lookup"><span data-stu-id="8c5d7-249">JSON</span></span>|<span data-ttu-id="8c5d7-250">json</span><span class="sxs-lookup"><span data-stu-id="8c5d7-250">json</span></span>|
|<span data-ttu-id="8c5d7-251">Markdown</span><span class="sxs-lookup"><span data-stu-id="8c5d7-251">Markdown</span></span>|<span data-ttu-id="8c5d7-252">md</span><span class="sxs-lookup"><span data-stu-id="8c5d7-252">md</span></span>|
|<span data-ttu-id="8c5d7-253">NodeJS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-253">NodeJS</span></span>|<span data-ttu-id="8c5d7-254">nodejs</span><span class="sxs-lookup"><span data-stu-id="8c5d7-254">nodejs</span></span>|
|<span data-ttu-id="8c5d7-255">Objective-C</span><span class="sxs-lookup"><span data-stu-id="8c5d7-255">Objective-C</span></span>|<span data-ttu-id="8c5d7-256">objc</span><span class="sxs-lookup"><span data-stu-id="8c5d7-256">objc</span></span>|
|<span data-ttu-id="8c5d7-257">OData</span><span class="sxs-lookup"><span data-stu-id="8c5d7-257">OData</span></span>|<span data-ttu-id="8c5d7-258">odata</span><span class="sxs-lookup"><span data-stu-id="8c5d7-258">odata</span></span>|
|<span data-ttu-id="8c5d7-259">PHP</span><span class="sxs-lookup"><span data-stu-id="8c5d7-259">PHP</span></span>|<span data-ttu-id="8c5d7-260">php</span><span class="sxs-lookup"><span data-stu-id="8c5d7-260">php</span></span>|
|<span data-ttu-id="8c5d7-261">PowerApps-képlet</span><span class="sxs-lookup"><span data-stu-id="8c5d7-261">Power Apps Formula</span></span>|<span data-ttu-id="8c5d7-262">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="8c5d7-262">powerappsfl</span></span>|
|<span data-ttu-id="8c5d7-263">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c5d7-263">PowerShell</span></span>|<span data-ttu-id="8c5d7-264">powershell</span><span class="sxs-lookup"><span data-stu-id="8c5d7-264">powershell</span></span>|
|<span data-ttu-id="8c5d7-265">Python</span><span class="sxs-lookup"><span data-stu-id="8c5d7-265">Python</span></span>|<span data-ttu-id="8c5d7-266">python</span><span class="sxs-lookup"><span data-stu-id="8c5d7-266">python</span></span>|
|<span data-ttu-id="8c5d7-267">Q#</span><span class="sxs-lookup"><span data-stu-id="8c5d7-267">Q#</span></span>|<span data-ttu-id="8c5d7-268">qsharp</span><span class="sxs-lookup"><span data-stu-id="8c5d7-268">qsharp</span></span>|
|<span data-ttu-id="8c5d7-269">R</span><span class="sxs-lookup"><span data-stu-id="8c5d7-269">R</span></span>|<span data-ttu-id="8c5d7-270">r</span><span class="sxs-lookup"><span data-stu-id="8c5d7-270">r</span></span>|
|<span data-ttu-id="8c5d7-271">Ruby</span><span class="sxs-lookup"><span data-stu-id="8c5d7-271">Ruby</span></span>|<span data-ttu-id="8c5d7-272">ruby</span><span class="sxs-lookup"><span data-stu-id="8c5d7-272">ruby</span></span>|
|<span data-ttu-id="8c5d7-273">SQL</span><span class="sxs-lookup"><span data-stu-id="8c5d7-273">SQL</span></span>|<span data-ttu-id="8c5d7-274">sql</span><span class="sxs-lookup"><span data-stu-id="8c5d7-274">sql</span></span>|
|<span data-ttu-id="8c5d7-275">Swift</span><span class="sxs-lookup"><span data-stu-id="8c5d7-275">Swift</span></span>|<span data-ttu-id="8c5d7-276">swift</span><span class="sxs-lookup"><span data-stu-id="8c5d7-276">swift</span></span>|
|<span data-ttu-id="8c5d7-277">TypeScript</span><span class="sxs-lookup"><span data-stu-id="8c5d7-277">TypeScript</span></span>|<span data-ttu-id="8c5d7-278">typescript</span><span class="sxs-lookup"><span data-stu-id="8c5d7-278">typescript</span></span>|
|<span data-ttu-id="8c5d7-279">VB</span><span class="sxs-lookup"><span data-stu-id="8c5d7-279">VB</span></span>|<span data-ttu-id="8c5d7-280">vb</span><span class="sxs-lookup"><span data-stu-id="8c5d7-280">vb</span></span>|
|<span data-ttu-id="8c5d7-281">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="8c5d7-281">VSTS CLI</span></span>|<span data-ttu-id="8c5d7-282">vstscli</span><span class="sxs-lookup"><span data-stu-id="8c5d7-282">vstscli</span></span>|
|<span data-ttu-id="8c5d7-283">XAML</span><span class="sxs-lookup"><span data-stu-id="8c5d7-283">XAML</span></span>|<span data-ttu-id="8c5d7-284">xaml</span><span class="sxs-lookup"><span data-stu-id="8c5d7-284">xaml</span></span>|
|<span data-ttu-id="8c5d7-285">XML</span><span class="sxs-lookup"><span data-stu-id="8c5d7-285">XML</span></span>|<span data-ttu-id="8c5d7-286">xml</span><span class="sxs-lookup"><span data-stu-id="8c5d7-286">xml</span></span>|

<span data-ttu-id="8c5d7-287">A `csharp-interactive` név a C# nyelvre utal, valamint arra, hogy a böngészőből futtathatók a minták.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-287">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="8c5d7-288">A kódrészletek lefordítása és végrehajtása egy Docker-tárolóban történik, és ennek a programvégrehajtásnak az eredménye jelenik meg a felhasználó böngészőablakában.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-288">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="8c5d7-289">Példa: C\#</span><span class="sxs-lookup"><span data-stu-id="8c5d7-289">Example: C\#</span></span>

<span data-ttu-id="8c5d7-290">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="8c5d7-290">__Markdown__</span></span>

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

<span data-ttu-id="8c5d7-291">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="8c5d7-291">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="8c5d7-292">Példa: SQL</span><span class="sxs-lookup"><span data-stu-id="8c5d7-292">Example: SQL</span></span>

<span data-ttu-id="8c5d7-293">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="8c5d7-293">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="8c5d7-294">__Megjelenítés__</span><span class="sxs-lookup"><span data-stu-id="8c5d7-294">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="8c5d7-295">Egyedi OPS Markdown-bővítmények</span><span class="sxs-lookup"><span data-stu-id="8c5d7-295">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="8c5d7-296">Az Open Publishing Services (OPS) a Markdig Parser Markdownt implementálja, amely nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM).</span><span class="sxs-lookup"><span data-stu-id="8c5d7-296">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="8c5d7-297">A Markdig néhány funkciót biztosít a Markdown-bővítmények révén.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-297">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="8c5d7-298">A jelen útmutatóban az OPS teljes szerzői útmutatójának kiválasztott témakörei szerepelnek referenciaként.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-298">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="8c5d7-299">(Például lásd a „Markdig- és Markdown-bővítmények” és a „Kódrészletek” címeket a tartalomjegyzékben.)</span><span class="sxs-lookup"><span data-stu-id="8c5d7-299">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="8c5d7-300">A Docs-cikkek formázásának nagy része, például a bekezdések, a hivatkozások, a listák és a fejlécek a GFM használatával készülnek.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-300">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="8c5d7-301">A kifinomultabb formázáshoz a cikkekben többek között az alábbi Markdig-funkciók használhatók:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-301">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="8c5d7-302">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-302">Note blocks</span></span>
- <span data-ttu-id="8c5d7-303">Beágyazott fájlok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-303">Include files</span></span>
- <span data-ttu-id="8c5d7-304">Választómezők</span><span class="sxs-lookup"><span data-stu-id="8c5d7-304">Selectors</span></span>
- <span data-ttu-id="8c5d7-305">Beágyazott videók</span><span class="sxs-lookup"><span data-stu-id="8c5d7-305">Embedded videos</span></span>
- <span data-ttu-id="8c5d7-306">Kódrészletek és -minták</span><span class="sxs-lookup"><span data-stu-id="8c5d7-306">Code snippets/samples</span></span>

<span data-ttu-id="8c5d7-307">A teljes listát a tartalomjegyzék „Markdig- és Markdown-bővítmények” és „Kódrészletek” fejezetcíme alatt találhatja.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-307">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="8c5d7-308">Megjegyzésblokkok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-308">Note blocks</span></span>

<span data-ttu-id="8c5d7-309">A megjegyzésblokkok 4 típusa közül választhat, hogy felhívja a figyelmet adott tartalomra:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-309">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="8c5d7-310">MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-310">NOTE</span></span>
- <span data-ttu-id="8c5d7-311">FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-311">WARNING</span></span>
- <span data-ttu-id="8c5d7-312">TIPP</span><span class="sxs-lookup"><span data-stu-id="8c5d7-312">TIP</span></span>
- <span data-ttu-id="8c5d7-313">FONTOS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-313">IMPORTANT</span></span>

<span data-ttu-id="8c5d7-314">Általánosságban elmondható, hogy a megjegyzésblokkokat ritkán szabad használni, mert megtörhetik a cikk folytonosságát.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-314">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="8c5d7-315">Bár a kódblokkok, képek, listák és hivatkozások használata a megjegyzésblokkokon belül is támogatott, törekedjen egyszerű és könnyen érthető megjegyzésblokkok írására.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-315">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="8c5d7-316">Példák:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-316">Examples:</span></span>

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

<span data-ttu-id="8c5d7-317">Ez a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-317">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="8c5d7-318">Ez egy MEGJEGYZÉS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-318">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="8c5d7-319">Ez egy FIGYELMEZTETÉS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-319">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="8c5d7-320">Ez egy TIPP</span><span class="sxs-lookup"><span data-stu-id="8c5d7-320">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c5d7-321">Ez FONTOS</span><span class="sxs-lookup"><span data-stu-id="8c5d7-321">This is IMPORTANT</span></span>

### <a name="include-files"></a><span data-ttu-id="8c5d7-322">Beágyazott fájlok</span><span class="sxs-lookup"><span data-stu-id="8c5d7-322">Include files</span></span>

<span data-ttu-id="8c5d7-323">Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a Markdig fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-323">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="8c5d7-324">Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-324">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="8c5d7-325">A tartalmak újrafelhasználását háromféle beágyazás segíti:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-325">Three types of include references are available to help you reuse content:</span></span>

- <span data-ttu-id="8c5d7-326">Beágyazott: Egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-326">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="8c5d7-327">Blokkszintű: Egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-327">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="8c5d7-328">Képek: Ez a képek normál beillesztésének megvalósítása a Docsban.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-328">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="8c5d7-329">A soron belüli és blokk típusú fájl egy egyszerű Markdown- (.md) fájl.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-329">An inline or block include file is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="8c5d7-330">Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-330">It can contain any valid Markdown.</span></span> <span data-ttu-id="8c5d7-331">Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-331">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="8c5d7-332">A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-332">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="8c5d7-333">Néhány követelmény és megfontolandó szempont a beágyazott fájlokhoz:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-333">Here are requirements and considerations for include files:</span></span>

- <span data-ttu-id="8c5d7-334">Bármikor használhat beágyazott fájlt, amikor ugyanazt a szöveget több cikkben is szeretné használni.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-334">Use an include file whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="8c5d7-335">A blokk típusú beágyazási hivatkozás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-335">Use a block include reference for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="8c5d7-336">Ne használja egy mondatnál kisebb terjedelmű szöveghez.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-336">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="8c5d7-337">A beágyazott hivatkozások a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok Markdig-bővítményeket igényelnek.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-337">Include references won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="8c5d7-338">Azok csak közzététel után jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-338">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="8c5d7-339">Ügyeljen rá, hogy a beágyazott fájl teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó fájlnak a beágyazást megelőző vagy azt követő szövegétől.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-339">Ensure that all the text in an include file is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include file.</span></span> <span data-ttu-id="8c5d7-340">Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan sztring jön létre a cikkben, amely megtöri a honosított felületet.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-340">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="8c5d7-341">Ne alkalmazzon beágyazási hivatkozást más beágyazott fájlokon belül.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-341">Don't embed include references within other include files.</span></span> <span data-ttu-id="8c5d7-342">Ez nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-342">They are not supported.</span></span>
- <span data-ttu-id="8c5d7-343">A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-343">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="8c5d7-344">A médiamappa gyökere nem tartalmazhat képfájlokat.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-344">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="8c5d7-345">Ha a beágyazott fájl nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-345">If the include file does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="8c5d7-346">A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-346">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="8c5d7-347">Minden egyes beágyazási fájlhoz és cikkhez használjon külön fájlt, egyedi névvel.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-347">Use a separate file with a unique name for each include file and article.</span></span> <span data-ttu-id="8c5d7-348">A médiafájlt tárolja a beágyazott fájlhoz társított médiamappában.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-348">Store the media file in the media folder that's associated with the include file.</span></span>
- <span data-ttu-id="8c5d7-349">A cikkek ne tartalmazzanak kizárólag beágyazott fájlt.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-349">Don't use an include file as the only content of an article.</span></span>  <span data-ttu-id="8c5d7-350">A beágyazott fájlok a cikk többi része tartalmának kiegészítésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-350">Include files are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="8c5d7-351">Példa:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-351">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="8c5d7-352">Választómezők</span><span class="sxs-lookup"><span data-stu-id="8c5d7-352">Selectors</span></span>

<span data-ttu-id="8c5d7-353">Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg az eltérő technológiák és platformok különbségeinek figyelembevételével.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-353">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="8c5d7-354">Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-354">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="8c5d7-355">A Markdigben jelenleg kétféle választómező van, az egyszerű és a többszintű.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-355">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="8c5d7-356">Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-356">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include file.</span></span> <span data-ttu-id="8c5d7-357">Később erre a beágyazott fájlra hivatkozhat az összes olyan témakörben, amely ugyanazt a választómezőt használja.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-357">Then you can reference that include file in all your articles that use the same selector.</span></span>

<span data-ttu-id="8c5d7-358">Ezen a példán egy választómező látható.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-358">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="8c5d7-359">Az [Azure dokumentációjában](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic) láthatja a választómezők működését.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-359">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-include-references"></a><span data-ttu-id="8c5d7-360">Kódbeágyazási hivatkozások</span><span class="sxs-lookup"><span data-stu-id="8c5d7-360">Code include references</span></span>

<span data-ttu-id="8c5d7-361">A Markdig a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-361">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="8c5d7-362">A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-362">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="8c5d7-363">Központosított kódminták vagy -részletek beágyazása külső tárházból.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-363">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="8c5d7-364">Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-364">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="8c5d7-365">Tipikus hibák és hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="8c5d7-365">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="8c5d7-366">Helyettesítő szöveg</span><span class="sxs-lookup"><span data-stu-id="8c5d7-366">Alt text</span></span>

<span data-ttu-id="8c5d7-367">Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-367">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="8c5d7-368">Például a következő szöveg helyett:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-368">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="8c5d7-369">Az aláhúzás jeleket így jelenítheti meg:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-369">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="8c5d7-370">Aposztrófok és idézőjelek</span><span class="sxs-lookup"><span data-stu-id="8c5d7-370">Apostrophes and quotation marks</span></span>

<span data-ttu-id="8c5d7-371">Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-371">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="8c5d7-372">Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni,</span><span class="sxs-lookup"><span data-stu-id="8c5d7-372">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="8c5d7-373">különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="8c5d7-373">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="8c5d7-374">Ezen írásjelek „intelligens” verzióinak kódolásai a következők:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-374">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="8c5d7-375">Bal oldali (nyitó) idézőjel: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="8c5d7-375">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="8c5d7-376">Jobb oldali (záró) idézőjel: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="8c5d7-376">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="8c5d7-377">Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="8c5d7-377">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="8c5d7-378">Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="8c5d7-378">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="8c5d7-379">Csúcsos zárójelek</span><span class="sxs-lookup"><span data-stu-id="8c5d7-379">Angle brackets</span></span>

<span data-ttu-id="8c5d7-380">Helyőrzők jelölésére általában csúcsos zárójeleket alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-380">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="8c5d7-381">Ha ezt szövegben használja (és nem kódban), a csúcsos zárójelet kódolnia kell.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-381">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="8c5d7-382">Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.</span><span class="sxs-lookup"><span data-stu-id="8c5d7-382">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="8c5d7-383">A `<script name>` kódolása például a következő: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="8c5d7-383">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="8c5d7-384">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8c5d7-384">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="8c5d7-385">Markdown-források</span><span class="sxs-lookup"><span data-stu-id="8c5d7-385">Markdown resources</span></span>

- <span data-ttu-id="8c5d7-386">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)</span><span class="sxs-lookup"><span data-stu-id="8c5d7-386">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="8c5d7-387">Markdown-segédlet a Docshoz</span><span class="sxs-lookup"><span data-stu-id="8c5d7-387">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="8c5d7-388">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)</span><span class="sxs-lookup"><span data-stu-id="8c5d7-388">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
- [<span data-ttu-id="8c5d7-389">Markdown-útmutató</span><span class="sxs-lookup"><span data-stu-id="8c5d7-389">The Markdown Guide</span></span>](https://www.markdownguide.org/)
