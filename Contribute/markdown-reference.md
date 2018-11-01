---
title: Markdown-referencia az OPS-hez és a docs.microsoft.com webhelyhez
description: Útmutató OPS-platformra a Markdown és a DocFX-stílusú Markdown- (DFM-) bővítményekhez.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
audience: internal,external
ms.openlocfilehash: e248eafb0247b200313ba198f2545eca947f5627
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805911"
---
# <a name="markdown-reference-for-ops"></a><span data-ttu-id="fcb36-103">Markdown-referencia az OPS-hez</span><span class="sxs-lookup"><span data-stu-id="fcb36-103">Markdown Reference for OPS</span></span>

<span data-ttu-id="fcb36-104">A Markdown egy egyszerűen kezelhető jelölőnyelv, amely a formázatlan szövegek formázására alkalmas szintaxist használ.</span><span class="sxs-lookup"><span data-stu-id="fcb36-104">Markdown is a lightweight markup language with plain text formatting syntax.</span></span> <span data-ttu-id="fcb36-105">Az OPS támogatja a Markdown CommonMark szabványát, és emellett számos olyan egyéni Markdown-bővítményt is, amelyekkel sokrétűbbé tehetők a docs.microsoft.com webhelyen található tartalmak.</span><span class="sxs-lookup"><span data-stu-id="fcb36-105">OPS supports the CommonMark standard for Markdown, plus some custom Markdown extensions designed to provide richer content on docs.microsoft.com.</span></span> <span data-ttu-id="fcb36-106">A cikk betűrendbe szedett referenciát nyújt a Markdown OPS-ben történő és docs.microsoft.com-tartalmak létrehozásához való használatához.</span><span class="sxs-lookup"><span data-stu-id="fcb36-106">This article provides an alphabetical reference for using Markdown in OPS for docs.microsoft.com.</span></span>

<span data-ttu-id="fcb36-107">Markdown-szintaxist bármilyen szövegszerkesztő használatával írhat.</span><span class="sxs-lookup"><span data-stu-id="fcb36-107">You can use any text editor to author Markdown.</span></span> <span data-ttu-id="fcb36-108">Ha olyan szövegszerkesztőt keres, amely a szabványos Markdown-szintaxis mellett támogatja az egyéni OPS-bővítményeket is, javasoljuk a [VS Code](https://code.visualstudio.com/) alkalmazás a [Docs Authoring Pack (Docs-közreműködői csomag)](https://aka.ms/DocsAuthoringPack) bővítmény telepítésével való használatát.</span><span class="sxs-lookup"><span data-stu-id="fcb36-108">For an editor that facilitates inserting both standard Markdown syntax and custom OPS extensions, we recommend [VS Code](https://code.visualstudio.com/) with the [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) installed.</span></span>

<span data-ttu-id="fcb36-109">Az OPS már minden újonnan létrehozott adattárhoz szabványos módon a Markdig feldolgozót használja, és a korábban létrehozott adattárak Markdigbe való migrálása is folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="fcb36-109">OPS has standardized on Markdig for all new repos, and older repos are migrating to Markdig.</span></span> <span data-ttu-id="fcb36-110">A [https://babelmark.github.io/](https://babelmark.github.io/) címen tesztelheti, hogyan jelennek meg a Markdown-szövegek a Markdigben más szövegrenderelő motorok képességeivel összevetve.</span><span class="sxs-lookup"><span data-stu-id="fcb36-110">You can test the rendering of Markdown in Markdig vs. other engines at [https://babelmark.github.io/](https://babelmark.github.io/).</span></span>

## <a name="alerts-note-tip-important-caution-warning"></a><span data-ttu-id="fcb36-111">Riasztások (Megjegyzés, Tipp, Fontos, Figyelem, Figyelmeztetés)</span><span class="sxs-lookup"><span data-stu-id="fcb36-111">Alerts (Note, Tip, Important, Caution, Warning)</span></span>

<span data-ttu-id="fcb36-112">Az Alerts (Riasztások) egy OPS-hez készült Markdown-bővítmény, amely olyan szövegblokkok létrehozására szolgál, amelyek a tartalom fontosságát jelző különböző színekkel és ikonokkal jelennek meg a docs.microsoft.com webhelyen.</span><span class="sxs-lookup"><span data-stu-id="fcb36-112">Alerts an OPS-specific Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="fcb36-113">A következő riasztási típusok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="fcb36-113">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="fcb36-114">Ezek a riasztások a következőképpen jelennek meg a docs.microsoft.com webhelyen:</span><span class="sxs-lookup"><span data-stu-id="fcb36-114">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="fcb36-115">Olyan információk, amelyeket a felhasználónak akkor is észre kell vennie, ha csak átfutja a szöveget.</span><span class="sxs-lookup"><span data-stu-id="fcb36-115">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="fcb36-116">Olyan kiegészítő információk, amelyek segítenek a felhasználónak sikeresebben végezni a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="fcb36-116">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb36-117">Alapvető információk, amelyek feltétlenül szükségesek a sikeres végrehajtáshoz.</span><span class="sxs-lookup"><span data-stu-id="fcb36-117">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="fcb36-118">Egy művelet potenciális negatív következményei.</span><span class="sxs-lookup"><span data-stu-id="fcb36-118">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="fcb36-119">Egy művelet meghatározott veszélyes következményei.</span><span class="sxs-lookup"><span data-stu-id="fcb36-119">Dangerous certain consequences of an action.</span></span>

## <a name="code-snippets"></a><span data-ttu-id="fcb36-120">Kódrészletek</span><span class="sxs-lookup"><span data-stu-id="fcb36-120">Code snippets</span></span>

<span data-ttu-id="fcb36-121">A Markdown-fájlokba kódrészletek is beágyazhatók:</span><span class="sxs-lookup"><span data-stu-id="fcb36-121">You can embed code snippets in your Markdown files:</span></span>

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a><span data-ttu-id="fcb36-122">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="fcb36-122">Headings</span></span>

<span data-ttu-id="fcb36-123">Az OPS a Markdown-fejlécek hat szintjét támogatja:</span><span class="sxs-lookup"><span data-stu-id="fcb36-123">OPS supports six levels of Markdown headings:</span></span>

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- <span data-ttu-id="fcb36-124">A legutolsó `#` szimbólum és a címsor szövege között szóköznek kell szerepelnie.</span><span class="sxs-lookup"><span data-stu-id="fcb36-124">There must be a space between the last `#` and heading text.</span></span>
- <span data-ttu-id="fcb36-125">Minden egyes Markdown-fájlnak tartalmaznia kell pontosan egy H1 fejlécet.</span><span class="sxs-lookup"><span data-stu-id="fcb36-125">Each Markdown file must have one and only one H1.</span></span>
- <span data-ttu-id="fcb36-126">A H1 fejlécnek az első tartalomnak kell lennie közvetlenül a YML-metaadatblokk után.</span><span class="sxs-lookup"><span data-stu-id="fcb36-126">The H1 must be the first content in the file after the YML metadata block.</span></span>
- <span data-ttu-id="fcb36-127">A H2 fejlécek megjelennek a közzétett fájl jobb oldali navigációs menüjében.</span><span class="sxs-lookup"><span data-stu-id="fcb36-127">H2s automatically appear in the right-hand navigating menu of the published file.</span></span> <span data-ttu-id="fcb36-128">Az alacsonyabb szintű fejlécek esetében ez nem történik meg, ezért a H2 fejléceket használja stratégiai pontokon, hogy megkönnyítse a navigációt a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="fcb36-128">Lower-level headings do not, so use H2s strategically to help readers navigate your content.</span></span>
- <span data-ttu-id="fcb36-129">A HTML-fejlécek (mint például a `<h1>`) használata nem ajánlott, és bizonyos esetekben figyelmeztetéseket eredményezhet a buildelési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="fcb36-129">HMTL headings, such as `<h1>`, are not recommended and in some cases will cause build warnings.</span></span>
- <span data-ttu-id="fcb36-130">A fájlokban található egyes fejlécekre [könyvjelzőkkel](#bookmark-links) hivatkozhat.</span><span class="sxs-lookup"><span data-stu-id="fcb36-130">You can link to individual headings in a file via [bookmarks](#bookmark-links).</span></span>

## <a name="html"></a><span data-ttu-id="fcb36-131">HTML</span><span class="sxs-lookup"><span data-stu-id="fcb36-131">HTML</span></span>

<span data-ttu-id="fcb36-132">Bár a Markdown támogatja a beágyazott HTML használatát, az OPS-sel való közzététel esetén nem ajánljuk a HTML használatát, mert néhány, korlátozott számú értéket kivéve általában buildelési hibákat és figyelmeztetéseket váltanak ki.</span><span class="sxs-lookup"><span data-stu-id="fcb36-132">Although Markdown supports inline HTML, HTML is not recommended for publishing via OPS, and except for a limited list of values will cause build errors or warnings.</span></span> <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a><span data-ttu-id="fcb36-133">Képek</span><span class="sxs-lookup"><span data-stu-id="fcb36-133">Images</span></span>

<span data-ttu-id="fcb36-134">Kép beágyazásának szintaxisa:</span><span class="sxs-lookup"><span data-stu-id="fcb36-134">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

<span data-ttu-id="fcb36-135">Ahol az `alt text` (helyettesítő szöveg) a kép rövid leírása, a `<folder path>` (mappa elérési útja) pedig a kép relatív elérési útja.</span><span class="sxs-lookup"><span data-stu-id="fcb36-135">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="fcb36-136">A helyettesítő szövegek a gyengén látó felhasználók által használt képernyőolvasó programokhoz szükségesek.</span><span class="sxs-lookup"><span data-stu-id="fcb36-136">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="fcb36-137">Ezen kívül hasznosak lehetnek akkor is, ha hiba lép fel az oldal megjelenítésekor, és nem jelennek meg a képek.</span><span class="sxs-lookup"><span data-stu-id="fcb36-137">It is also useful if there is a site bug where the image cannot render.</span></span>

<span data-ttu-id="fcb36-138">A képeket egy `/media` elnevezésű mappában kell tárolni a dokumentumkészleten belül.</span><span class="sxs-lookup"><span data-stu-id="fcb36-138">Images should be stored in a `/media` folder within your doc set.</span></span> <span data-ttu-id="fcb36-139">Alapértelmezés szerint a következő képfájltípusok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="fcb36-139">The following file types are supported by default for images:</span></span>

- <span data-ttu-id="fcb36-140">.jpg</span><span class="sxs-lookup"><span data-stu-id="fcb36-140">.jpg</span></span>
- <span data-ttu-id="fcb36-141">.png</span><span class="sxs-lookup"><span data-stu-id="fcb36-141">.png</span></span>

<span data-ttu-id="fcb36-142">Más képtípusok támogatását is biztosíthatja, ha erőforrásként hozzáadja őket a dokumentumkészlet docfx.json fájljához <!--add link to reference when available-->.</span><span class="sxs-lookup"><span data-stu-id="fcb36-142">You can add support for other image types by adding them as resources to the docfx.json file<!--add link to reference when available--> for your doc set.</span></span>

## <a name="links"></a><span data-ttu-id="fcb36-143">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fcb36-143">Links</span></span>

<span data-ttu-id="fcb36-144">A legtöbb esetben az OPS hagyományos Markdown-hivatkozásokat használ a más fájlokra vagy oldalakra történő hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="fcb36-144">In most cases, OPS uses standard Markdown links to other files and pages.</span></span> <span data-ttu-id="fcb36-145">A különböző hivatkozástípusokat a következő alfejezetekben mutatjuk be.</span><span class="sxs-lookup"><span data-stu-id="fcb36-145">The types of links are described in subsections below.</span></span>

> [!TIP]
> <span data-ttu-id="fcb36-146">A VS Code alkalmazáshoz készült Docs-közreműködői csomag anélkül segíti a relatív hivatkozások és könyvjelzők helyes beszúrását, hogy az elérési utakkal kellene bajlódnia.</span><span class="sxs-lookup"><span data-stu-id="fcb36-146">The Docs Authoring Pack for VS Code can help insert relative links and bookmarks correctly without the tedium of figuring out the paths!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb36-147">Microsoft-oldalakra mutató hivatkozás készítésekor ne használjon olyan területibeállítás-kódokat, mint például a hu-HU.</span><span class="sxs-lookup"><span data-stu-id="fcb36-147">Do not include locale codes, such as en-us, in your links to Microsoft sites.</span></span> <span data-ttu-id="fcb36-148">A kódban explicit módon megadott területi beállítások megakadályozhatják a honosított tartalmak megjelenítését, ez pedig rontja a más területi beállítást használók felhasználói élményét, és jelentős honosítási költségeket vonhat maga után.</span><span class="sxs-lookup"><span data-stu-id="fcb36-148">Hard-coded locale codes prevent localized content from rendering, which is a bad customer experience for users in other locales and incurs significant localization costs.</span></span> <span data-ttu-id="fcb36-149">Amikor kimásol egy URL-címet a böngészőből, alapértelmezetten hozzáadásra kerül a területi beállítás kódja is, ezért azt saját kezűleg kell törölnie, amikor a hivatkozást létrehozza.</span><span class="sxs-lookup"><span data-stu-id="fcb36-149">When you copy a URL from a browser, the locale code is included by default, so you need to manually delete in when you create your link.</span></span> <span data-ttu-id="fcb36-150">Használja például így:</span><span class="sxs-lookup"><span data-stu-id="fcb36-150">For example, use:</span></span>
>
> `[Microsoft](https://www.microsoft.com)`
>
> <span data-ttu-id="fcb36-151">Nem pedig így:</span><span class="sxs-lookup"><span data-stu-id="fcb36-151">Not:</span></span>
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a><span data-ttu-id="fcb36-152">Ugyanazon dokumentumkészlet más fájljaira mutató relatív hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fcb36-152">Relative links to files in the same doc set</span></span>

<span data-ttu-id="fcb36-153">A relatív elérési út a célfájl az aktuális fájlhoz viszonyított elérési útja.</span><span class="sxs-lookup"><span data-stu-id="fcb36-153">A relative path is the path to the target file relative to the current file.</span></span> <span data-ttu-id="fcb36-154">Az OPS-ben lehetősége van relatív elérési út használatával hivatkozni egy másik fájlra ugyanazon a dokumentumkészleten belül.</span><span class="sxs-lookup"><span data-stu-id="fcb36-154">In OPS, you can use a relative path to link to another file within the same doc set.</span></span> <span data-ttu-id="fcb36-155">A relatív elérési utak szintaxisa a következő:</span><span class="sxs-lookup"><span data-stu-id="fcb36-155">The syntax for a relative path is as follows:</span></span>

```markdown
[link text](../../folder/filename.md)
```

<span data-ttu-id="fcb36-156">Ahol a `../` a hierarchia eggyel magasabb szintjét jelzi.</span><span class="sxs-lookup"><span data-stu-id="fcb36-156">Where `../` indicates one level above in the hierarchy.</span></span>

- <span data-ttu-id="fcb36-157">A relatív elérési utat a buildelési folyamat során oldja fel a rendszer, beleértve az .md kiterjesztés eltávolítását is.</span><span class="sxs-lookup"><span data-stu-id="fcb36-157">The relative path will be resolved during the build, including removal of the .md extension.</span></span>
- <span data-ttu-id="fcb36-158">A „../” használatával hivatkozhat a szülőmappában található fájlokra, de az adott fájlnak ugyanabban a dokumentumkészletben kell lennie.</span><span class="sxs-lookup"><span data-stu-id="fcb36-158">You can use "../" to link to a file in the parent folder, but that file has to be in the same doc set.</span></span> <span data-ttu-id="fcb36-159">A „../” nem használható másik dokumentumkészlet fájljaira való hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="fcb36-159">You cannot use "../" to link to a file in another doc set folder.</span></span>
- <span data-ttu-id="fcb36-160">Az OPS a relatív elérési utak egy speciális formájának használatát is lehetővé teszi, amelyeknél az elérési út a „~” szimbólummal kezdődik (például ~/foo/bar.md).</span><span class="sxs-lookup"><span data-stu-id="fcb36-160">OPS also supports a special form of relative path that starts with "~" (for example, ~/foo/bar.md).</span></span> <span data-ttu-id="fcb36-161">Ezzel a szintaxissal egy dokumentumkészlet gyökérmappájához képest határozhatók meg a fájlok.</span><span class="sxs-lookup"><span data-stu-id="fcb36-161">This syntax indicates a file relative to the root folder of a doc set.</span></span> <span data-ttu-id="fcb36-162">Az ilyen útvonal feloldása és ellenőrzése is megtörténik az összeállítás során.</span><span class="sxs-lookup"><span data-stu-id="fcb36-162">This kind of path is also validated and resolved during the build.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb36-163">A relatív útvonalakban adja meg a fájlnévkiterjesztéseket is.</span><span class="sxs-lookup"><span data-stu-id="fcb36-163">Include the file extension in the relative path.</span></span> <span data-ttu-id="fcb36-164">A rendszer a buildelés során ellenőrzi, hogy létezik-e a relatív elérési úttal hivatkozott fájl.</span><span class="sxs-lookup"><span data-stu-id="fcb36-164">Build validates the existence of the target file of that relative path.</span></span> <span data-ttu-id="fcb36-165">Ha a relatív elérési út nem tartalmaz fájlnévkiterjesztést, a buildelési folyamat valószínűleg figyelmeztetni fogja, hogy a hivatkozás hibás.</span><span class="sxs-lookup"><span data-stu-id="fcb36-165">If relative path does not include file extension, it is likely build will report a warning of broken link.</span></span> <span data-ttu-id="fcb36-166">Használja például így:</span><span class="sxs-lookup"><span data-stu-id="fcb36-166">For example, use:</span></span>
>
> `[link text](../../folder/filename.md)`
>
> <span data-ttu-id="fcb36-167">Nem pedig így:</span><span class="sxs-lookup"><span data-stu-id="fcb36-167">Not:</span></span>
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a><span data-ttu-id="fcb36-168">Abszolút hivatkozások más fájlokra az OPS-ben</span><span class="sxs-lookup"><span data-stu-id="fcb36-168">Absolute links to other files in OPS</span></span>

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

<span data-ttu-id="fcb36-169">A fájlnévkiterjesztést (.md) ne adja meg.</span><span class="sxs-lookup"><span data-stu-id="fcb36-169">Do not include the file extension (.md).</span></span> <span data-ttu-id="fcb36-170">Ez az Azure „articles” („cikkek”) dokumentumkészletén kívüli Linux-áttekintési fájlra mutat.</span><span class="sxs-lookup"><span data-stu-id="fcb36-170">This links to the Linux overview file from outside the Azure "articles" doc set.</span></span>

### <a name="links-to-external-sites"></a><span data-ttu-id="fcb36-171">Külső webhelyekre mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fcb36-171">Links to external sites</span></span>

```markdown
[Microsoft](https://www.microsoft.com)
```

<span data-ttu-id="fcb36-172">Másik weblapra mutató URL-alapú hivatkozás (tartalmaznia kell a https:// előtagot).</span><span class="sxs-lookup"><span data-stu-id="fcb36-172">URL-based link to another web page (must include https://).</span></span>

### <a name="bookmark-links"></a><span data-ttu-id="fcb36-173">Könyvjelző-hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fcb36-173">Bookmark links</span></span>

<span data-ttu-id="fcb36-174">Könyvjelző-hivatkozás egy másik, ugyanabban az adattárban lévő fájl egyik fejlécére:</span><span class="sxs-lookup"><span data-stu-id="fcb36-174">Bookmark link to a heading in another file in the same repo:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<span data-ttu-id="fcb36-175">Könyvjelző-hivatkozás az aktuális fájl egyik fejlécére:</span><span class="sxs-lookup"><span data-stu-id="fcb36-175">Bookmark link to a heading in the current file:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<span data-ttu-id="fcb36-176">Használja a kettőskeresztet, majd írja be a fejléc szövegét, írásjelek nélkül és a szóközöket alulvonásokkal helyettesítve.</span><span class="sxs-lookup"><span data-stu-id="fcb36-176">Use a hash tag followed by the words of the heading with punctuation removed and spaces replaced with dashes.</span></span>

### <a name="explicit-anchor-links"></a><span data-ttu-id="fcb36-177">Explicit horgonyhivatkozások</span><span class="sxs-lookup"><span data-stu-id="fcb36-177">Explicit anchor links</span></span>

<span data-ttu-id="fcb36-178">Az `<a>` HTML-címkével készíthető explicit horgonyhivatkozások alkalmazása **nem szükséges és nem is ajánlott**, csak a főoldalak és kezdőlapok esetében.</span><span class="sxs-lookup"><span data-stu-id="fcb36-178">Explicit anchor links using the `<a>` HTML tag are **not required or recommended** except in hub and landing pages.</span></span> <span data-ttu-id="fcb36-179">Az általános Markdown-fájlok esetén inkább használjon könyvjelzőket a fentebb leírt módon.</span><span class="sxs-lookup"><span data-stu-id="fcb36-179">Use bookmarks as described above in general Markdown files.</span></span> <span data-ttu-id="fcb36-180">A főoldalaknál és kezdőlapoknál a következő módon használhatja a horgonyokat:</span><span class="sxs-lookup"><span data-stu-id="fcb36-180">For hub and landing pages, use anchors as follows:</span></span>

<span data-ttu-id="fcb36-181">`## <a id="AnchorText"> </a>Header text` vagy `## <a name="AnchorText"> </a>Header text`</span><span class="sxs-lookup"><span data-stu-id="fcb36-181">`## <a id="AnchorText"> </a>Header text` or `## <a name="AnchorText"> </a>Header text`</span></span>

<span data-ttu-id="fcb36-182">Explicit horgonyra mutató hivatkozás létrehozásához a következő szintaxist használhatja:</span><span class="sxs-lookup"><span data-stu-id="fcb36-182">To link to explicit anchors, use the following syntax:</span></span>

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a><span data-ttu-id="fcb36-183">XREF-hivatkozások (kereszthivatkozások)</span><span class="sxs-lookup"><span data-stu-id="fcb36-183">XREF (cross reference) links</span></span>

<span data-ttu-id="fcb36-184">Az aktuális dokumentumkészletben vagy más dokumentumkészletekben szereplő, automatikusan generált API-referenciaoldalakra mutató hivatkozás létrehozásához használjon XREF-hivatkozásokat az egyedi azonosítóval (UID).</span><span class="sxs-lookup"><span data-stu-id="fcb36-184">To link to auto-generated API references pages in the current doc set or other doc sets, use XREF links with the unique ID (UID).</span></span>

> [!NOTE]
> <span data-ttu-id="fcb36-185">A más dokumentumkészletek API-referenciaoldalaira mutató hivatkozások készítéséhez hozzá kell adnia az `xrefService` beállítást a `docfx.json` fájlhoz.</span><span class="sxs-lookup"><span data-stu-id="fcb36-185">To reference API reference pages in other docsets, you need to add `xrefService` configuration in `docfx.json` file.</span></span>
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

<span data-ttu-id="fcb36-186">A UID a teljes osztály- és tagnévnek felel meg.</span><span class="sxs-lookup"><span data-stu-id="fcb36-186">The UID equates to the fully qualified class and member name.</span></span> <span data-ttu-id="fcb36-187">Ha beszúr egy \* szimbólumot az UID után, a hivatkozás a túlterhelések oldalát fogja jelölni, nem pedig egy konkrét API-t.</span><span class="sxs-lookup"><span data-stu-id="fcb36-187">If you add a \* after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="fcb36-188">A `List<T>.BinarySearch*` használatával például a BinarySearch metódus oldalára fog hivatkozni, nem pedig egy adott túlterhelésre, mint például a `List<T>.BinarySearch(T, IComparer<T>)`.</span><span class="sxs-lookup"><span data-stu-id="fcb36-188">For example, use `List<T>.BinarySearch*` to link to the BinarySearch Method page instead of linking to a specific overload such as `List<T>.BinarySearch(T, IComparer<T>)`.</span></span>

<span data-ttu-id="fcb36-189">Az következő szintaxisok egyikét használhatja:</span><span class="sxs-lookup"><span data-stu-id="fcb36-189">You can use one of the following syntaxes:</span></span>

- <span data-ttu-id="fcb36-190">Automatikus hivatkozás: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="fcb36-190">Auto-link: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span></span>

  <span data-ttu-id="fcb36-191">A nem kötelező `displayProperty` lekérdezési paraméter teljesen minősített hivatkozási szöveget eredményez.</span><span class="sxs-lookup"><span data-stu-id="fcb36-191">The optional `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="fcb36-192">Alapértelmezés szerint a hivatkozás szövegében csak a tag vagy a típus neve jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fcb36-192">By default, link text shows only the member or type name.</span></span>

- <span data-ttu-id="fcb36-193">Markdown-hivatkozás: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="fcb36-193">Markdown link: `[link text](xref:UID)`</span></span>
  
  <span data-ttu-id="fcb36-194">Akkor használja, ha testre szeretné szabni a megjelenített hivatkozási szöveget.</span><span class="sxs-lookup"><span data-stu-id="fcb36-194">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="fcb36-195">Példák:</span><span class="sxs-lookup"><span data-stu-id="fcb36-195">Examples:</span></span>

- <span data-ttu-id="fcb36-196">`<xref:System.String>`, megjelenítve „String”.</span><span class="sxs-lookup"><span data-stu-id="fcb36-196">`<xref:System.String>` renders as "String".</span></span>
- <span data-ttu-id="fcb36-197">`<xref:System.String?displayProperty=nameWithType>`, megjelenítve „System.String”.</span><span class="sxs-lookup"><span data-stu-id="fcb36-197">`<xref:System.String?displayProperty=nameWithType>` renders as "System.String".</span></span>
- <span data-ttu-id="fcb36-198">`[String class](xref:System.String)`, megjelenítve „String class”.</span><span class="sxs-lookup"><span data-stu-id="fcb36-198">`[String class](xref:System.String)` renders as "String class".</span></span>

<span data-ttu-id="fcb36-199">Jelenleg a UID azonosítók megkeresésének nincs könnyű módszere.</span><span class="sxs-lookup"><span data-stu-id="fcb36-199">Right now, there is no easy way to find the UIDs.</span></span> <span data-ttu-id="fcb36-200"><!-- ? -->Egy API UID-azonosítójának megkeresésére a legjobb módszer, hogy megtekinti a hivatkozni kívánt API-lap forrását, és megkeresi az API-hoz tartozó ms.assetid-értéket.</span><span class="sxs-lookup"><span data-stu-id="fcb36-200"><!-- ? -->The best way to find the UID for an API is to view the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="fcb36-201">A forrásban az egyes túlterhelési értékek nem jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="fcb36-201">Individual overload values are not shown in the source.</span></span> <span data-ttu-id="fcb36-202">Dolgozunk rajta, hogy a jövőben jobb rendszer álljon rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="fcb36-202">We're working on having a better system in the future.</span></span>

<span data-ttu-id="fcb36-203">Ha az UID-azonosító \`, \# vagy \* speciális karaktert tartalmaz, akkor az UID-értéket a `%60`, a `%23`, illetőleg a `%2A` karakterrel kell HTML-kódolásban megadni.</span><span class="sxs-lookup"><span data-stu-id="fcb36-203">When the UID contains the special characters \`, \#, or \*, the UID value needs to be HTML encoded as `%60`, `%23`, and `%2A`, respectively.</span></span> <span data-ttu-id="fcb36-204">Időnként előfordul a zárójelek kódolása, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="fcb36-204">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="fcb36-205">Példák:</span><span class="sxs-lookup"><span data-stu-id="fcb36-205">Examples:</span></span>

- <span data-ttu-id="fcb36-206">A System.Threading.Tasks.Task\`1 `System.Threading.Tasks.Task%601` lesz</span><span class="sxs-lookup"><span data-stu-id="fcb36-206">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="fcb36-207">A System.Exception.\#ctor `System.Exception.%23ctor` lesz</span><span class="sxs-lookup"><span data-stu-id="fcb36-207">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="fcb36-208">A System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` lesz</span><span class="sxs-lookup"><span data-stu-id="fcb36-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a><span data-ttu-id="fcb36-209">Listák (Számozott lista, Listajeles lista, Ellenőrzőlista)</span><span class="sxs-lookup"><span data-stu-id="fcb36-209">Lists (Numbered, Bulleted, Checklist)</span></span>

### <a name="numbered-list"></a><span data-ttu-id="fcb36-210">Numbered list</span><span class="sxs-lookup"><span data-stu-id="fcb36-210">Numbered list</span></span>

<span data-ttu-id="fcb36-211">Számozott lista létrehozásához nyugodtan használhat mindegyik listaelemnél 1-eseket, az elemek a közzététel után sorszámozott listaként fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="fcb36-211">To create a numbered list, you can use all 1s, which are rendered as a sequential list when published.</span></span> <span data-ttu-id="fcb36-212">A forrásfájl olvashatóságának javítása érdekében azonban használhat emelkedő számozást is listáiban.</span><span class="sxs-lookup"><span data-stu-id="fcb36-212">For increased source readability, you can increment your lists.</span></span>

<span data-ttu-id="fcb36-213">Ne használjon betűket, még egymásba ágyazott listákban sem.</span><span class="sxs-lookup"><span data-stu-id="fcb36-213">Do not use letters in lists, including nested lists.</span></span> <span data-ttu-id="fcb36-214">Ezek hibásan jelennek meg az OPS-ben való közzététel után.</span><span class="sxs-lookup"><span data-stu-id="fcb36-214">They do not render correctly when published via OPS.</span></span> <span data-ttu-id="fcb36-215">A számokat használó egymásba ágyazott listák közzététel után kisbetűs sorszámozással jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="fcb36-215">Nested lists using numbers will render as lowercase letters when published.</span></span> <span data-ttu-id="fcb36-216">Példa:</span><span class="sxs-lookup"><span data-stu-id="fcb36-216">For example:</span></span>

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

<span data-ttu-id="fcb36-217">Ez a következőképp jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-217">This renders as follows:</span></span>

1. <span data-ttu-id="fcb36-218">Ez a</span><span class="sxs-lookup"><span data-stu-id="fcb36-218">This is</span></span>
1. <span data-ttu-id="fcb36-219">szülő számozott lista</span><span class="sxs-lookup"><span data-stu-id="fcb36-219">a parent numbered list</span></span>
   1. <span data-ttu-id="fcb36-220">ez pedig a</span><span class="sxs-lookup"><span data-stu-id="fcb36-220">and this is</span></span>
   1. <span data-ttu-id="fcb36-221">beágyazott számozott lista</span><span class="sxs-lookup"><span data-stu-id="fcb36-221">a nested numbered list</span></span>
1. <span data-ttu-id="fcb36-222">(vége)</span><span class="sxs-lookup"><span data-stu-id="fcb36-222">(fin)</span></span>

### <a name="bulleted-list"></a><span data-ttu-id="fcb36-223">Bulleted list</span><span class="sxs-lookup"><span data-stu-id="fcb36-223">Bulleted list</span></span>

<span data-ttu-id="fcb36-224">Listajeles lista létrehozásához az egyes sorok elején használjon `-` írásjelet és egy szóközt:</span><span class="sxs-lookup"><span data-stu-id="fcb36-224">To create a bulleted list, use `-` followed by a space at the beginning of each line:</span></span>

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

<span data-ttu-id="fcb36-225">Ez a következőképp jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-225">This renders as follows:</span></span>

- <span data-ttu-id="fcb36-226">Ez a</span><span class="sxs-lookup"><span data-stu-id="fcb36-226">This is</span></span>
- <span data-ttu-id="fcb36-227">szülő listajeles lista</span><span class="sxs-lookup"><span data-stu-id="fcb36-227">a parent bulleted list</span></span>
  - <span data-ttu-id="fcb36-228">ez pedig a</span><span class="sxs-lookup"><span data-stu-id="fcb36-228">and this is</span></span>
  - <span data-ttu-id="fcb36-229">beágyazott listajeles lista</span><span class="sxs-lookup"><span data-stu-id="fcb36-229">a nested bulleted list</span></span>
- <span data-ttu-id="fcb36-230">Kész!</span><span class="sxs-lookup"><span data-stu-id="fcb36-230">All done!</span></span>

### <a name="checklist"></a><span data-ttu-id="fcb36-231">Ellenőrzőlista</span><span class="sxs-lookup"><span data-stu-id="fcb36-231">Checklist</span></span>

<span data-ttu-id="fcb36-232">Ellenőrzőlistákat (kizárólag) egy egyedi Markdown-bővítménnyel használhat a docs.microsoft.com webhelyen:</span><span class="sxs-lookup"><span data-stu-id="fcb36-232">Checklists are available for use on docs.microsoft.com (only) via a custom Markdown extension:</span></span>

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

<span data-ttu-id="fcb36-233">A következő példa ekképpen jelenik meg a docs.microsoft.com webhelyen:</span><span class="sxs-lookup"><span data-stu-id="fcb36-233">This example renders on docs.microsoft.com like this:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fcb36-234">1. listaelem</span><span class="sxs-lookup"><span data-stu-id="fcb36-234">List item 1</span></span>
> * <span data-ttu-id="fcb36-235">2. listaelem</span><span class="sxs-lookup"><span data-stu-id="fcb36-235">List item 2</span></span>
> * <span data-ttu-id="fcb36-236">3. listaelem</span><span class="sxs-lookup"><span data-stu-id="fcb36-236">List item 3</span></span>

<span data-ttu-id="fcb36-237">Ellenőrzőlistákat a cikkek elején vagy végén használhat annak összefoglalására, hogy „mit fogunk megtanulni” vagy „mit tanultunk meg”.</span><span class="sxs-lookup"><span data-stu-id="fcb36-237">Use checklits at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content.</span></span> <span data-ttu-id="fcb36-238">Ne adjon hozzá cikkeihez a tartalmak közt véletlenszerűen elszórt ellenőrzőlistákat.</span><span class="sxs-lookup"><span data-stu-id="fcb36-238">Do not add random checklists throughout your articles.</span></span>
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a><span data-ttu-id="fcb36-239">Következő lépés művelet</span><span class="sxs-lookup"><span data-stu-id="fcb36-239">Next step action</span></span>

<span data-ttu-id="fcb36-240">Egy egyedi bővítménnyel a Következő lépés művelet gombját is hozzáadhatja (kizárólag) a docs.microsoft.com oldalaihoz.</span><span class="sxs-lookup"><span data-stu-id="fcb36-240">You can use a custom extension to add a next step action button to pages on docs.microsoft.com (only).</span></span>

<span data-ttu-id="fcb36-241">A szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="fcb36-241">The syntax is as follows:</span></span>

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

<span data-ttu-id="fcb36-242">Példa:</span><span class="sxs-lookup"><span data-stu-id="fcb36-242">For example:</span></span>

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

<span data-ttu-id="fcb36-243">Ez a következőképp jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-243">This renders as follows:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcb36-244">Tudnivalók az alapvető stílusról</span><span class="sxs-lookup"><span data-stu-id="fcb36-244">Learn about basic style</span></span>](style-quick-start.md)

<span data-ttu-id="fcb36-245">A Következő lépés műveletekben bármilyen támogatott hivatkozásformát használhat, beleértve a más oldalakra mutató Markdown-hivatkozásokat is.</span><span class="sxs-lookup"><span data-stu-id="fcb36-245">You can use any supported link in a next step action, including a Markdown link to another web page.</span></span> <span data-ttu-id="fcb36-246">A legtöbb esetben a Következő lépés művelet egy relatív hivatkozást tartalmaz, amely egy másik fájlra mutat ugyanazon a dokumentumkészleten belül.</span><span class="sxs-lookup"><span data-stu-id="fcb36-246">In most cases, the next action link will be a relative link to another file in the same doc set.</span></span>

## <a name="section-definition"></a><span data-ttu-id="fcb36-247">Szakaszdefiníció</span><span class="sxs-lookup"><span data-stu-id="fcb36-247">Section definition</span></span>

<span data-ttu-id="fcb36-248"><!-- more info about this would be helpful! -->Előfordulhat, hogy szakaszokat kell definiálnia.</span><span class="sxs-lookup"><span data-stu-id="fcb36-248"><!-- more info about this would be helpful! --> You might need to define a section.</span></span> <span data-ttu-id="fcb36-249">Ezt a szintaxist többnyire kódtáblázatokhoz használják.</span><span class="sxs-lookup"><span data-stu-id="fcb36-249">This syntax is mostly used for code tables.</span></span>
<span data-ttu-id="fcb36-250">Tekintse meg az alábbi példát:</span><span class="sxs-lookup"><span data-stu-id="fcb36-250">See the following example:</span></span>

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

<span data-ttu-id="fcb36-251">A fenti idézetblokk Markdown-szövege így jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-251">The preceding blockquote Markdown text will be rendered as:</span></span>
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a><span data-ttu-id="fcb36-252">Választómezők</span><span class="sxs-lookup"><span data-stu-id="fcb36-252">Selectors</span></span>

<span data-ttu-id="fcb36-253"><!-- could be more clear! -->Ha ugyanahhoz a cikkhez különböző oldalakat szeretne kapcsolni, használjon választókat.</span><span class="sxs-lookup"><span data-stu-id="fcb36-253"><!-- could be more clear! --> You can use a selector when you want to connect different pages for the same article.</span></span> <span data-ttu-id="fcb36-254">Így az olvasók szabadon lépkedhetnek az oldalak között.</span><span class="sxs-lookup"><span data-stu-id="fcb36-254">Readers can then switch between those pages.</span></span>

> [!NOTE]
> <span data-ttu-id="fcb36-255">Ez a bővítmény nem egyformán működik a docs.microsoft.com és az MSDN esetében.</span><span class="sxs-lookup"><span data-stu-id="fcb36-255">This extension works differently between docs.microsoft.com and MSDN.</span></span> <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a><span data-ttu-id="fcb36-256">Egyszerű választómező</span><span class="sxs-lookup"><span data-stu-id="fcb36-256">Single selector</span></span>

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

<span data-ttu-id="fcb36-257">...így fog megjelenni:</span><span class="sxs-lookup"><span data-stu-id="fcb36-257">... will be rendered like this:</span></span>

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a><span data-ttu-id="fcb36-266">Többszintű választómező</span><span class="sxs-lookup"><span data-stu-id="fcb36-266">Multi-selector</span></span>

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

<span data-ttu-id="fcb36-267">...így fog megjelenni:</span><span class="sxs-lookup"><span data-stu-id="fcb36-267">... will be rendered like this:</span></span>

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)

<!-- uncomment and link when Cory's topic is live
## Tabbed content

Tabs are a Markdown extension for docs.microsoft.com that allow us to present different versions of content, such as procedural steps to accomplish the same task on different platforms, in a tabbed format.

Because the syntax and requirements for tabbed content are fairly complex, they are documented separately in Tabbed Content.
-->

## <a name="tables"></a><span data-ttu-id="fcb36-278">Táblázatok</span><span class="sxs-lookup"><span data-stu-id="fcb36-278">Tables</span></span>

<span data-ttu-id="fcb36-279">A Markdown-szintaxissal táblázat a legegyszerűbben függőleges vonal és kötőjel karakterekkel alakítható ki.</span><span class="sxs-lookup"><span data-stu-id="fcb36-279">The simplest way to create a table in Markdown is to use pipes and lines.</span></span> <span data-ttu-id="fcb36-280">Normál fejléccel rendelkező táblázatok létrehozásához az első sor után szúrjon be szaggatott vonalat:</span><span class="sxs-lookup"><span data-stu-id="fcb36-280">To create a standard table with a header, follow the first line with dashed line:</span></span>

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

<span data-ttu-id="fcb36-281">Ez a következőképp jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-281">This renders as follows:</span></span>

|<span data-ttu-id="fcb36-282">Ez</span><span class="sxs-lookup"><span data-stu-id="fcb36-282">This is</span></span>   |<span data-ttu-id="fcb36-283">egy egyszerű</span><span class="sxs-lookup"><span data-stu-id="fcb36-283">a simple</span></span>   |<span data-ttu-id="fcb36-284">táblafejléc</span><span class="sxs-lookup"><span data-stu-id="fcb36-284">table header</span></span>|
|----------|-----------|------------|
|<span data-ttu-id="fcb36-285">itt</span><span class="sxs-lookup"><span data-stu-id="fcb36-285">table</span></span>     |<span data-ttu-id="fcb36-286">vannak</span><span class="sxs-lookup"><span data-stu-id="fcb36-286">data</span></span>       |<span data-ttu-id="fcb36-287">az adatok</span><span class="sxs-lookup"><span data-stu-id="fcb36-287">here</span></span>        |
|<span data-ttu-id="fcb36-288">nem kell</span><span class="sxs-lookup"><span data-stu-id="fcb36-288">it doesn't</span></span>|<span data-ttu-id="fcb36-289">mindennek</span><span class="sxs-lookup"><span data-stu-id="fcb36-289">actually</span></span>   |<span data-ttu-id="fcb36-290">szépen sorba rendezve lennie!</span><span class="sxs-lookup"><span data-stu-id="fcb36-290">have to line up nicely!</span></span>||

<span data-ttu-id="fcb36-291">Fejléc nélküli táblázatot is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="fcb36-291">You can also create a table without a header.</span></span> <span data-ttu-id="fcb36-292">Többoszlopos listát például így készíthet:</span><span class="sxs-lookup"><span data-stu-id="fcb36-292">For example, to create a multiple-column list:</span></span>

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

<span data-ttu-id="fcb36-293">Ez a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-293">This renders like this:</span></span>

|   |   |
| - | - |
| <span data-ttu-id="fcb36-294">Ez a</span><span class="sxs-lookup"><span data-stu-id="fcb36-294">This</span></span> | <span data-ttu-id="fcb36-295">táblázat</span><span class="sxs-lookup"><span data-stu-id="fcb36-295">table</span></span> |
| <span data-ttu-id="fcb36-296">nem tartalmaz</span><span class="sxs-lookup"><span data-stu-id="fcb36-296">has no</span></span> | <span data-ttu-id="fcb36-297">fejlécet</span><span class="sxs-lookup"><span data-stu-id="fcb36-297">header</span></span> |

<span data-ttu-id="fcb36-298">Az oszlopokat kettőspontokkal igazíthatja:</span><span class="sxs-lookup"><span data-stu-id="fcb36-298">You can align the columns by using colons:</span></span>

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

<span data-ttu-id="fcb36-299">A következőképp jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-299">Renders as follows:</span></span>

|                  |
|------------------|
|    <span data-ttu-id="fcb36-300">jobbra igazított:</span><span class="sxs-lookup"><span data-stu-id="fcb36-300">right aligned:</span></span>|
|<span data-ttu-id="fcb36-301">:balra igazított</span><span class="sxs-lookup"><span data-stu-id="fcb36-301">:left aligned</span></span>     |
|<span data-ttu-id="fcb36-302">:középre zárt        :</span><span class="sxs-lookup"><span data-stu-id="fcb36-302">:centered        :</span></span>|

> [!TIP]
> A VS Code alkalmazáshoz készült Docs-közreműködői csomaggal könnyedén adhat tartalmaihoz egyszerű Markdown-táblázatokat!
>
> Használhat ugyanakkor akár [online táblázatkészítő](http://www.tablesgenerator.com/markdown_tables) megoldást is.

### <a name="mx-tdbreakall"></a><span data-ttu-id="fcb36-305">mx-tdBreakAll</span><span class="sxs-lookup"><span data-stu-id="fcb36-305">mx-tdBreakAll</span></span>

> [!IMPORTANT]
> Ez a funkció csak a docs.microsoft.com webhelyen működik.

<span data-ttu-id="fcb36-307">A Markdownnal létrehozott táblázatok olykor túlnyúlnak a jobb oldali navigációs sávon, ezáltal olvashatatlanná válnak.</span><span class="sxs-lookup"><span data-stu-id="fcb36-307">If you create a table in Markdown, the table might expand to the right navigation and become unreadable.</span></span> <span data-ttu-id="fcb36-308">Ez orvosolható a táblázat szükség szerinti tördelésének engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="fcb36-308">You can solve that by allowing Docs rendering to break the table when needed.</span></span> <span data-ttu-id="fcb36-309">Ehhez elég a táblázatot belefoglalni az egyéni `[!div class="mx-tdBreakAll"]` osztályba.</span><span class="sxs-lookup"><span data-stu-id="fcb36-309">Just wrap up the table with the custom class `[!div class="mx-tdBreakAll"]`.</span></span>

<span data-ttu-id="fcb36-310">A következő Markdown-példában szereplő táblázat az `mx-tdBreakAll` nevű osztályba van besorolva egy `div` címke segítségével.</span><span class="sxs-lookup"><span data-stu-id="fcb36-310">Here is a Markdown sample of a table with three rows that will be wrapped by a `div` with the class name `mx-tdBreakAll`.</span></span>

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

<span data-ttu-id="fcb36-311">Így fog megjelenni:</span><span class="sxs-lookup"><span data-stu-id="fcb36-311">It will be rendered like this:</span></span>

> [!div class="mx-tdBreakAll"]
> |<span data-ttu-id="fcb36-312">Név</span><span class="sxs-lookup"><span data-stu-id="fcb36-312">Name</span></span>|<span data-ttu-id="fcb36-313">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcb36-313">Syntax</span></span>|<span data-ttu-id="fcb36-314">Mandatory for silent installation?</span><span class="sxs-lookup"><span data-stu-id="fcb36-314">Mandatory for silent installation?</span></span>|<span data-ttu-id="fcb36-315">Description</span><span class="sxs-lookup"><span data-stu-id="fcb36-315">Description</span></span>|
> |-------------|----------|---------|---------|
> |<span data-ttu-id="fcb36-316">Quiet</span><span class="sxs-lookup"><span data-stu-id="fcb36-316">Quiet</span></span>|<span data-ttu-id="fcb36-317">/quiet</span><span class="sxs-lookup"><span data-stu-id="fcb36-317">/quiet</span></span>|<span data-ttu-id="fcb36-318">Yes</span><span class="sxs-lookup"><span data-stu-id="fcb36-318">Yes</span></span>|<span data-ttu-id="fcb36-319">Felhasználói felület és utasítások megjelenítése nélkül futtatja a telepítőt.</span><span class="sxs-lookup"><span data-stu-id="fcb36-319">Runs the installer, displaying no UI and no prompts.</span></span>|
> |<span data-ttu-id="fcb36-320">NoRestart</span><span class="sxs-lookup"><span data-stu-id="fcb36-320">NoRestart</span></span>|<span data-ttu-id="fcb36-321">/norestart</span><span class="sxs-lookup"><span data-stu-id="fcb36-321">/norestart</span></span>|<span data-ttu-id="fcb36-322">No</span><span class="sxs-lookup"><span data-stu-id="fcb36-322">No</span></span>|<span data-ttu-id="fcb36-323">Suppresses any attempts to restart.</span><span class="sxs-lookup"><span data-stu-id="fcb36-323">Suppresses any attempts to restart.</span></span> <span data-ttu-id="fcb36-324">A felhasználó felület alapértelmezés szerint rákérdez az újraindításra.</span><span class="sxs-lookup"><span data-stu-id="fcb36-324">By default, the UI will prompt before restart.</span></span>|
> |<span data-ttu-id="fcb36-325">Help</span><span class="sxs-lookup"><span data-stu-id="fcb36-325">Help</span></span>|<span data-ttu-id="fcb36-326">/help</span><span class="sxs-lookup"><span data-stu-id="fcb36-326">/help</span></span>|<span data-ttu-id="fcb36-327">No</span><span class="sxs-lookup"><span data-stu-id="fcb36-327">No</span></span>|<span data-ttu-id="fcb36-328">Provides help and quick reference.</span><span class="sxs-lookup"><span data-stu-id="fcb36-328">Provides help and quick reference.</span></span> <span data-ttu-id="fcb36-329">Megmutatja a telepítési parancs helyes használatát, felsorolva minden beállítást és azok működését.</span><span class="sxs-lookup"><span data-stu-id="fcb36-329">Displays the correct use of the setup command, including a list of all options and behaviors.</span></span>|

### <a name="mx-tdcol2breakall"></a><span data-ttu-id="fcb36-330">mx-tdCol2BreakAll</span><span class="sxs-lookup"><span data-stu-id="fcb36-330">mx-tdCol2BreakAll</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb36-331">Ez a funkció csak a docs.microsoft.com webhelyen működik.</span><span class="sxs-lookup"><span data-stu-id="fcb36-331">This only works on the docs.microsoft.com site.</span></span>

<span data-ttu-id="fcb36-332">Előfordulhat, hogy nagyon hosszú szavak szerepelnek a táblázat második oszlopában.</span><span class="sxs-lookup"><span data-stu-id="fcb36-332">From time to time, you might have very long words in the second column of a table.</span></span> <span data-ttu-id="fcb36-333">Ha megfelelően szeretné tördelni őket, akkor a `div` burkolószintaxissal alkalmazza az `mx-tdCol2BreakAll` osztályt, ahogy ezt korábban bemutattuk.</span><span class="sxs-lookup"><span data-stu-id="fcb36-333">To ensure they are broken apart nicely, you can apply the class `mx-tdCol2BreakAll` by using the `div` wrapper syntax as shown earlier.</span></span>

### <a name="html-tables"></a><span data-ttu-id="fcb36-334">HTML-táblázatok</span><span class="sxs-lookup"><span data-stu-id="fcb36-334">HTML Tables</span></span>

<span data-ttu-id="fcb36-335">A HTML-táblázatok használata nem ajánlott a docs.microsoft.com webhelyen.</span><span class="sxs-lookup"><span data-stu-id="fcb36-335">HTML tables are not recommended for docs.microsoft.com.</span></span> <span data-ttu-id="fcb36-336">Ennek oka, hogy a forrásfájlban olvashatatlanul jelennek meg, az olvashatóság pedig a Markdown egyik fő alapelve.</span><span class="sxs-lookup"><span data-stu-id="fcb36-336">They are not human readable in the source - which is a key principle of Markdown.</span></span>

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a><span data-ttu-id="fcb36-337">Videók</span><span class="sxs-lookup"><span data-stu-id="fcb36-337">Videos</span></span>

### <a name="embedding-videos-into-a-markdown-page"></a><span data-ttu-id="fcb36-338">Videók beágyazása Markdown-oldalakba</span><span class="sxs-lookup"><span data-stu-id="fcb36-338">Embedding videos into a Markdown page</span></span>

<span data-ttu-id="fcb36-339">Az OPS jelenleg a következő három helyen közzétett videók beágyazását támogatja:</span><span class="sxs-lookup"><span data-stu-id="fcb36-339">Currently, OPS can support videos published to one of three locations:</span></span>

- <span data-ttu-id="fcb36-340">YouTube</span><span class="sxs-lookup"><span data-stu-id="fcb36-340">YouTube</span></span>
- <span data-ttu-id="fcb36-341">Channel 9</span><span class="sxs-lookup"><span data-stu-id="fcb36-341">Channel 9</span></span>
- <span data-ttu-id="fcb36-342">A Microsoft saját „One Player” rendszere</span><span class="sxs-lookup"><span data-stu-id="fcb36-342">Microsoft's own 'One Player' system</span></span>

<span data-ttu-id="fcb36-343">Videót az alábbi, az OPS által feldolgozott szintaxissal lehet beágyazni.</span><span class="sxs-lookup"><span data-stu-id="fcb36-343">You can embed a video with the following syntax, and OPS will render it.</span></span>

```markdown
> [!VIDEO <embedded_video_link>]
```

<span data-ttu-id="fcb36-344">Példa:</span><span class="sxs-lookup"><span data-stu-id="fcb36-344">Example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

<span data-ttu-id="fcb36-345">...a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="fcb36-345">... will be rendered as:</span></span>

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

<span data-ttu-id="fcb36-346">A közzétett oldalakon pedig így lesz látható:</span><span class="sxs-lookup"><span data-stu-id="fcb36-346">And it will be displayed like this on published pages:</span></span>

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> <span data-ttu-id="fcb36-347">A CH9-videó URL-hivatkozásának eleje legyen `https`, a vége pedig `/player`.</span><span class="sxs-lookup"><span data-stu-id="fcb36-347">The CH9 video URL should start with `https` and end with `/player`.</span></span> <span data-ttu-id="fcb36-348">Ellenkező esetben a videó helyett az egész oldalt ágyazná be.</span><span class="sxs-lookup"><span data-stu-id="fcb36-348">Otherwise, it will embed the whole page instead of the video only.</span></span>

### <a name="uploading-new-videos"></a><span data-ttu-id="fcb36-349">Új videók feltöltése</span><span class="sxs-lookup"><span data-stu-id="fcb36-349">Uploading new videos</span></span>

<span data-ttu-id="fcb36-350">Az új videók feltöltésének folyamata a következő:</span><span class="sxs-lookup"><span data-stu-id="fcb36-350">Any new videos should be uploaded using the following process:</span></span>

1. <span data-ttu-id="fcb36-351">Csatlakozzon a **docs_video_users** csoporthoz az IDWEB-en.</span><span class="sxs-lookup"><span data-stu-id="fcb36-351">Join the **docs_video_users** group on IDWEB.</span></span>
1. <span data-ttu-id="fcb36-352">Nyissa meg a https://aka.ms/VideoUploadRequest oldalt, és adja meg a videó adatait.</span><span class="sxs-lookup"><span data-stu-id="fcb36-352">Go to https://aka.ms/VideoUploadRequest and fill in the details for your video.</span></span> <span data-ttu-id="fcb36-353">A következőkre lesz szüksége (fontos megjegyezni, hogy ezek az elemek nyilvánosan nem fognak megjelenni):</span><span class="sxs-lookup"><span data-stu-id="fcb36-353">You will need (note that none of these items will be visible to the public):</span></span>
    1. <span data-ttu-id="fcb36-354">A videó címe.</span><span class="sxs-lookup"><span data-stu-id="fcb36-354">A title for your video.</span></span>
    1. <span data-ttu-id="fcb36-355">Azoknak a termékeknek vagy szolgáltatásoknak a listája, amelyekkel a videó kapcsolatos.</span><span class="sxs-lookup"><span data-stu-id="fcb36-355">A list of products/services that your video is related to.</span></span>
    1. <span data-ttu-id="fcb36-356">A céloldal vagy (ha még nincs készen az oldal) a dokumentumkészlet, amelybe a videót ágyazni kívánja.</span><span class="sxs-lookup"><span data-stu-id="fcb36-356">The target page or (if you don’t have the page yet) doc set that your video will be hosted on.</span></span>
    1. <span data-ttu-id="fcb36-357">A videó MP4-fájljára mutató hivatkozás (ha még nincs hely, ahol elhelyezheti a fájlt, ideiglenesen használhatja a `\\scratch2\scratch\apex` helyet).</span><span class="sxs-lookup"><span data-stu-id="fcb36-357">A link to the MP4 file for your video (if you don’t have a location to put the file, you can put it here temporarily:   `\\scratch2\scratch\apex`).</span></span> <span data-ttu-id="fcb36-358">Az MP4-fájlnak 720p vagy nagyobb felbontásúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="fcb36-358">MP4 files should be 720p or higher.</span></span>
    1. <span data-ttu-id="fcb36-359">A videó leírása.</span><span class="sxs-lookup"><span data-stu-id="fcb36-359">A description of the video.</span></span>
1. <span data-ttu-id="fcb36-360">Küldje el (mentse) az elemet.</span><span class="sxs-lookup"><span data-stu-id="fcb36-360">Submit (save) that item.</span></span>
1. <span data-ttu-id="fcb36-361">A videó két munkanapon belül fel lesz töltve.</span><span class="sxs-lookup"><span data-stu-id="fcb36-361">Within two business days, the video will get uploaded.</span></span> <span data-ttu-id="fcb36-362">A beágyazáshoz szükséges hivatkozás a munkaelembe kerül, és címfeloldás után *visszakerül Önhöz*.</span><span class="sxs-lookup"><span data-stu-id="fcb36-362">The link you need for embedding will be placed into the work item, and it will be resolved *back to you*.</span></span>
1. <span data-ttu-id="fcb36-363">Miután megkapta a videó címét, bezárhatja a munkaelemet.</span><span class="sxs-lookup"><span data-stu-id="fcb36-363">Once you have grabbed the video link, close the work item.</span></span>
1. <span data-ttu-id="fcb36-364">A videóra mutató hivatkozást a következő szintaxissal szúrhatja be a bejegyzésbe:</span><span class="sxs-lookup"><span data-stu-id="fcb36-364">The video link can then be added to your post, using this syntax:</span></span>

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
