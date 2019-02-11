---
title: Sablon és segédlet .NET-cikkekhez
description: Ez a cikk egy hasznos sablont tartalmaz, amelyet új cikkek létrehozására használhat a .NET-dokumentumtárakban
ms.date: 11/07/2018
ms.openlocfilehash: e342373a09b623dc71aadd63e8d8627d154ec8b6
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55712924"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a><span data-ttu-id="664cb-103">Metaadatok és Markdown-sablon .NET-dokumentumokhoz</span><span class="sxs-lookup"><span data-stu-id="664cb-103">Metadata and Markdown template for .NET docs</span></span>

<span data-ttu-id="664cb-104">Ez a dotnet/docs sablon példákat tartalmaz a Markdown szintaxisára, valamint útmutatást a metaadatok beállításához.</span><span class="sxs-lookup"><span data-stu-id="664cb-104">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span>

<span data-ttu-id="664cb-105">Markdown-fájl létrehozásakor át kell másolnia a megadott sablont az új fájlba, ki kell töltenie a metaadatokat az alább megadott módon, a fenti H1 címsorban pedig a cikk címét kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="664cb-105">When creating a Markdown file, you should copy the included template to a new file, fill out the metadata as specified below, and set the H1 heading above to the title of the article.</span></span>

## <a name="metadata"></a><span data-ttu-id="664cb-106">Metaadatok</span><span class="sxs-lookup"><span data-stu-id="664cb-106">Metadata</span></span>

<span data-ttu-id="664cb-107">A szükséges metaadatblokk a következő mintául megadott metaadatblokkban található:</span><span class="sxs-lookup"><span data-stu-id="664cb-107">The required metadata block is in the following sample metadata block:</span></span>

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- <span data-ttu-id="664cb-108">A kettőspont (:) és a metaadatelem értéke között lennie **kell** szóköznek.</span><span class="sxs-lookup"><span data-stu-id="664cb-108">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="664cb-109">Az értékben (például a címben) megadott kettőspontok a metaadat-elemző hibás működését eredményezik.</span><span class="sxs-lookup"><span data-stu-id="664cb-109">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="664cb-110">Ebben az esetben foglalja a címet kettős idézőjelek közé (például: `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="664cb-110">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="664cb-111">**title**: Megjelenik a keresőmotorok keresési eredményeiben.</span><span class="sxs-lookup"><span data-stu-id="664cb-111">**title**: Appears in search engine results.</span></span> <span data-ttu-id="664cb-112">A cím ne legyen azonos a H1 címsorban megadott címmel, és legfeljebb 60 karaktert tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="664cb-112">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="664cb-113">**description**: Összefoglalja a cikk tartalmát.</span><span class="sxs-lookup"><span data-stu-id="664cb-113">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="664cb-114">Általában megjelenik a keresési eredmények oldalán, de nem használatos a keresési eredmények rangsorolásához.</span><span class="sxs-lookup"><span data-stu-id="664cb-114">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="664cb-115">A hossza 115–145 karakter legyen szóközökkel együtt.</span><span class="sxs-lookup"><span data-stu-id="664cb-115">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="664cb-116">**author**: Az author (szerző) mezőnek tartalmaznia kell a szerző **GitHub-felhasználónevét**.</span><span class="sxs-lookup"><span data-stu-id="664cb-116">**author**: The author field should contain the **GitHub username** of the author.</span></span>
- <span data-ttu-id="664cb-117">**ms.date**: A legutóbbi jelentős frissítés dátuma.</span><span class="sxs-lookup"><span data-stu-id="664cb-117">**ms.date**: The date of the last significant update.</span></span> <span data-ttu-id="664cb-118">Frissítse ezt az értéket a meglévő cikkekben, ha áttekintette és átdolgozta a teljes cikket.</span><span class="sxs-lookup"><span data-stu-id="664cb-118">Update this on existing articles if you reviewed and updated the entire article.</span></span> <span data-ttu-id="664cb-119">A kisebb javítások, például az elírások és hasonlók miatt nem szükséges frissíteni az értékét.</span><span class="sxs-lookup"><span data-stu-id="664cb-119">Small fixes, such as typos or similar do not warrant an update.</span></span>

<span data-ttu-id="664cb-120">Más metaadatok is kapcsolódnak minden cikkhez, de általában a legtöbb metaadatértéket a mappa szintjén alkalmazzuk **docfx.json** fájlként megadva.</span><span class="sxs-lookup"><span data-stu-id="664cb-120">Other metadata is attached to each article, but we typically apply most metadata values at the folder level, specified in **docfx.json**.</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="664cb-121">Alapszintű Markdown, GFM és különleges karakterek</span><span class="sxs-lookup"><span data-stu-id="664cb-121">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="664cb-122">A Markdown, a GitHub Flavored Markdown (GFM) és az OPS-specifikus bővítmények alapjait a [Markdown](how-to-write-use-markdown.md) és a [Markdown-referencia](markdown-reference.md) általános cikkeiből sajátíthatja el.</span><span class="sxs-lookup"><span data-stu-id="664cb-122">You can learn the basics of Markdown, GitHub Flavored Markdown (GFM), and OPS specific extensions in the general articles on [Markdown](how-to-write-use-markdown.md) and [Markdown reference](markdown-reference.md).</span></span>

<span data-ttu-id="664cb-123">A Markdown különleges karaktereket, például \* , \` és \# használ a formázáshoz.</span><span class="sxs-lookup"><span data-stu-id="664cb-123">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="664cb-124">Ha ezek közül a karakterek közül valamelyiket szeretné belefoglalni a dokumentumba, tegye az alábbi két dolog közül valamelyiket:</span><span class="sxs-lookup"><span data-stu-id="664cb-124">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="664cb-125">Írjon be egy fordított perjel karaktert a különleges karakter elé a „kikerüléséhez” (például a \* karakterhez `\*`)</span><span class="sxs-lookup"><span data-stu-id="664cb-125">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="664cb-126">Használja a karakter [HTML-entitáskódját](http://www.ascii.cl/htmlcodes.htm) (például a &#42; karakterhez `&#42;`).</span><span class="sxs-lookup"><span data-stu-id="664cb-126">Use the [HTML entity code](http://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-names"></a><span data-ttu-id="664cb-127">Fájlnevek</span><span class="sxs-lookup"><span data-stu-id="664cb-127">File names</span></span>

<span data-ttu-id="664cb-128">A fájlnevek a következő szabályokat használják:</span><span class="sxs-lookup"><span data-stu-id="664cb-128">File names use the following rules:</span></span>

* <span data-ttu-id="664cb-129">Csak kisbetűk, számok és kötőjelek használhatók.</span><span class="sxs-lookup"><span data-stu-id="664cb-129">Contain only lowercase letters, numbers, and hyphens.</span></span>
* <span data-ttu-id="664cb-130">Szóköz és írásjelkarakter nem használható.</span><span class="sxs-lookup"><span data-stu-id="664cb-130">No spaces or punctuation characters.</span></span> <span data-ttu-id="664cb-131">A kötőjel a szavak és számok elválasztására használható.</span><span class="sxs-lookup"><span data-stu-id="664cb-131">Use the hyphens to separate words and numbers in the file name.</span></span>
* <span data-ttu-id="664cb-132">Konkrét műveleteket használjon, például develop (fejlesztés), buy (vásárlás), build (fordítás), troubleshoot (hibakeresés).</span><span class="sxs-lookup"><span data-stu-id="664cb-132">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="664cb-133">Ne használja az angol igék -ing végződésű alakját.</span><span class="sxs-lookup"><span data-stu-id="664cb-133">No -ing words.</span></span>
* <span data-ttu-id="664cb-134">Ne használjon nem önálló szavakat (a, and, the, in, or, etc).</span><span class="sxs-lookup"><span data-stu-id="664cb-134">No small words - don't include a, and, the, in, or, etc.</span></span>
* <span data-ttu-id="664cb-135">Markdown-formátumot kell használni, .md kiterjesztéssel.</span><span class="sxs-lookup"><span data-stu-id="664cb-135">Must be in Markdown and use the .md file extension.</span></span>
* <span data-ttu-id="664cb-136">Ésszerűen rövid fájlneveket használjon.</span><span class="sxs-lookup"><span data-stu-id="664cb-136">Keep file names reasonably short.</span></span> <span data-ttu-id="664cb-137">Ezek a cikkek URL-címének részei.</span><span class="sxs-lookup"><span data-stu-id="664cb-137">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="664cb-138">Fejlécek</span><span class="sxs-lookup"><span data-stu-id="664cb-138">Headings</span></span>

<span data-ttu-id="664cb-139">Csak a mondat első betűje legyen nagybetű.</span><span class="sxs-lookup"><span data-stu-id="664cb-139">Use sentence-style capitalization.</span></span> <span data-ttu-id="664cb-140">A cím első betűje mindig nagybetű legyen.</span><span class="sxs-lookup"><span data-stu-id="664cb-140">Always capitalize the first word of a heading.</span></span>

## <a name="text-styling"></a><span data-ttu-id="664cb-141">Szövegstílus</span><span class="sxs-lookup"><span data-stu-id="664cb-141">Text styling</span></span>

<span data-ttu-id="664cb-142">*Dőltbetű* Használja fájlokhoz, mappákhoz, elérési utakhoz (hosszú elemek esetén törje ezeket a saját külön sorukba) és új kifejezésekhez.</span><span class="sxs-lookup"><span data-stu-id="664cb-142">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="664cb-143">**Fékövér** Használja a felhasználói felület elemeihez.</span><span class="sxs-lookup"><span data-stu-id="664cb-143">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="664cb-144">`Code` Használja beágyazott kódokhoz, programnyelvi kulcsszavakhoz, NuGet-csomagok nevéhez, parancssori parancsokhoz, adatbázistábla és oszlopnevekhez, valamint olyan URL-címekhez, amelyekre nem lehet rákattintani.</span><span class="sxs-lookup"><span data-stu-id="664cb-144">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="664cb-145">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="664cb-145">Links</span></span>

<span data-ttu-id="664cb-146">A horgonyokra, belső hivatkozásokra, más dokumentumokra mutató hivatkozásokra, belefoglalt kódokra és külső hivatkozásokra vonatkozóan olvassa el a [Hivatkozások](how-to-write-links.md) általános cikket.</span><span class="sxs-lookup"><span data-stu-id="664cb-146">See the general article on [Links](how-to-write-links.md) for information about anchors, internal links, links to other documents, code includes, and external links.</span></span>

<span data-ttu-id="664cb-147">A .NET-dokumentumok csapata a következő konvenciókat használja:</span><span class="sxs-lookup"><span data-stu-id="664cb-147">The .NET docs team uses the following conventions:</span></span>

- <span data-ttu-id="664cb-148">A legtöbbször relatív hivatkozásokat használunk, és nem javasoljuk `~/` használatát a hivatkozásokban, mert a relatív hivatkozások a forrásban lesznek feloldva a GitHubon.</span><span class="sxs-lookup"><span data-stu-id="664cb-148">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="664cb-149">Ha azonban egy függő tárban lévő fájlra hivatkozunk, akkor a `~/` karaktert használjuk az elérési út megadásához.</span><span class="sxs-lookup"><span data-stu-id="664cb-149">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="664cb-150">Mivel a függő tárban lévő fájlok más helyen vannak a GitHubon, a hivatkozások feloldása nem lesz megfelelő relatív hivatkozásokkal, függetlenül attól, hogyan írták őket.</span><span class="sxs-lookup"><span data-stu-id="664cb-150">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>
- <span data-ttu-id="664cb-151">A C# nyelvi specifikációk és a Visual Basic nyelvi specifikációk .NET-dokumentumokba való belefoglalása a programnyelvi kódtárakból a forrás belefoglalásával történik.</span><span class="sxs-lookup"><span data-stu-id="664cb-151">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="664cb-152">A Markdown-források kezelése a [csharplang](https://github.com/dotnet/csharplang) és a [vblang](https://github.com/dotnet/vblang) kódtárakban történik.</span><span class="sxs-lookup"><span data-stu-id="664cb-152">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [vblang](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="664cb-153">A specifikációkra mutató hivatkozásoknak azokra a forráskönyvtárakra kell mutatniuk, amelyekben ezek a specifikációk találhatók.</span><span class="sxs-lookup"><span data-stu-id="664cb-153">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="664cb-154">C# esetén ez a **~/_csharplang/spec**, VB esetén pedig a **~/_vblang/spec**, a következő példához hasonlóan:</span><span class="sxs-lookup"><span data-stu-id="664cb-154">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**, as in the following example:</span></span>

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a><span data-ttu-id="664cb-155">API-kra mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="664cb-155">Links to APIs</span></span>

<span data-ttu-id="664cb-156">A build rendszer rendelkezik néhány bővítménnyel, amelyek lehetővé teszik a .NET API-kra való hivatkozást, anélkül, hogy külső hivatkozásokat kellene használni.</span><span class="sxs-lookup"><span data-stu-id="664cb-156">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span> <span data-ttu-id="664cb-157">Az alábbi szintaxisok egyikét használhatja:</span><span class="sxs-lookup"><span data-stu-id="664cb-157">You use one of the following syntax:</span></span>

1. <span data-ttu-id="664cb-158">Automatikus hivatkozás: `<xref:UID>` vagy `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="664cb-158">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="664cb-159">A `displayProperty` lekérdezési paraméter teljesen minősített hivatkozási szöveget eredményez.</span><span class="sxs-lookup"><span data-stu-id="664cb-159">The `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="664cb-160">Alapértelmezés szerint a hivatkozás szövegében csak a tag vagy a típus neve jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="664cb-160">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="664cb-161">Markdown-hivatkozás: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="664cb-161">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="664cb-162">Akkor használja, ha testre szeretné szabni a megjelenített hivatkozási szöveget.</span><span class="sxs-lookup"><span data-stu-id="664cb-162">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="664cb-163">Példák:</span><span class="sxs-lookup"><span data-stu-id="664cb-163">Examples:</span></span>

- <span data-ttu-id="664cb-164">`<xref:System.String>`, megjelenítve [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="664cb-164">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="664cb-165">`<xref:System.String?displayProperty=nameWithType>`, megjelenítve [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="664cb-165">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="664cb-166">`[String class](xref:System.String)`, megjelenítve [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="664cb-166">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="664cb-167">Ezen jelölés használatával kapcsolatban a [Kereszthivatkozások használata](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference) című témakörben találhat további információt.</span><span class="sxs-lookup"><span data-stu-id="664cb-167">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="664cb-168">Ha néhány UID-azonosító \`, \# vagy \* speciális karaktert tartalmaz, akkor az UID-értéket a `%60`, a `%23`, illetőleg a `%2A` karakterrel kell HTML-kódolásban megadni.</span><span class="sxs-lookup"><span data-stu-id="664cb-168">Some UIDs contain the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="664cb-169">Időnként előfordul a zárójelek kódolása, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="664cb-169">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="664cb-170">Példák:</span><span class="sxs-lookup"><span data-stu-id="664cb-170">Examples:</span></span>

- <span data-ttu-id="664cb-171">A System.Threading.Tasks.Task\`1 `System.Threading.Tasks.Task%601` lesz</span><span class="sxs-lookup"><span data-stu-id="664cb-171">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="664cb-172">A System.Exception.\#ctor `System.Exception.%23ctor` lesz</span><span class="sxs-lookup"><span data-stu-id="664cb-172">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="664cb-173">A System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` lesz</span><span class="sxs-lookup"><span data-stu-id="664cb-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<span data-ttu-id="664cb-174">Az UID-típusokat, a tag túlterhelési listáját vagy az adott túlterhelt tagot a `https://xref.docs.microsoft.com/autocomplete` weblapon találja.</span><span class="sxs-lookup"><span data-stu-id="664cb-174">You can find the UIDs of types, a member overload list, or a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="664cb-175">A(z) `?text=*\<type-member-name>*` lekérdezési sztring azonosítja azt a tagtípust, amelyiknek az UID-jét látni szeretné.</span><span class="sxs-lookup"><span data-stu-id="664cb-175">The query string `?text=*\<type-member-name>*` identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="664cb-176">A `https://xref.docs.microsoft.com/autocomplete?text=string.format` például a [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) túlterheléseket kéri le.</span><span class="sxs-lookup"><span data-stu-id="664cb-176">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span> <span data-ttu-id="664cb-177">Az eszköz a megadott `text` lekérdezési paramétert az UID bármely részében keresi.</span><span class="sxs-lookup"><span data-stu-id="664cb-177">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="664cb-178">Kereshet például a tagnévre (ToString), a tagnév egy részére (ToStri), a típusra és a tagnévre (Double.ToString) stb.</span><span class="sxs-lookup"><span data-stu-id="664cb-178">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="664cb-179">Ha beszúr egy \* szimbólumot (vagy `%2A`-t) az UID után, a hivatkozás a túlterhelések oldalát fogja jelölni, nem pedig egy konkrét API-t.</span><span class="sxs-lookup"><span data-stu-id="664cb-179">If you add a \* (or `%2A`) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="664cb-180">Ezt használhatja például, ha a [List\<T>.BinarySearch metódusra](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) generikus módon szeretne hivatkozni egy adott túlterhelés, például a [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) helyett.</span><span class="sxs-lookup"><span data-stu-id="664cb-180">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="664cb-181">A \* szimbólumot tagoldalra való hivatkozáshoz is használhatja, ha a tag nincs túlterhelve, így nem kell belefoglalnia a paraméterek listáját a UID-be.</span><span class="sxs-lookup"><span data-stu-id="664cb-181">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="664cb-182">Meghatározott metódus-túlterhelésre való hivatkozáshoz meg kell adnia a metódus összes paraméterének teljes típusnevét.</span><span class="sxs-lookup"><span data-stu-id="664cb-182">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="664cb-183">Az \<xref:System.DateTime.ToString> például a paraméter nélküli [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) metódusra hivatkozik, míg az \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> a [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) metódusra.</span><span class="sxs-lookup"><span data-stu-id="664cb-183">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span>

<span data-ttu-id="664cb-184">Általános típusra, például a [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) típusra való hivatkozáshoz a \` (`%60`) karaktert használja, amelyet az általános típusú paraméterek számának kell követnie.</span><span class="sxs-lookup"><span data-stu-id="664cb-184">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (`%60`) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="664cb-185">A(z) `<xref:System.Nullable%601>` például a [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) típusra hivatkozik, míg a(z) `<xref:System.Func%602>` a [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegáltra.</span><span class="sxs-lookup"><span data-stu-id="664cb-185">For example, `<xref:System.Nullable%601>` links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while `<xref:System.Func%602>` links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

## <a name="code"></a><span data-ttu-id="664cb-186">Code</span><span class="sxs-lookup"><span data-stu-id="664cb-186">Code</span></span>

<span data-ttu-id="664cb-187">A kód belefoglalásának legjobb módja kódrészletek belefoglalása egy működő példányból.</span><span class="sxs-lookup"><span data-stu-id="664cb-187">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="664cb-188">Hozza létre a mintát a [hozzájárulás a .NET-hez](dotnet-contribute-process.md#contributing-to-samples) cikk útmutatását követve.</span><span class="sxs-lookup"><span data-stu-id="664cb-188">Create your sample following the instructions in the [contributing to .NET](dotnet-contribute-process.md#contributing-to-samples) article.</span></span> <span data-ttu-id="664cb-189">A kód belefoglalásának alapvető szabályait a [kódra](how-to-write-use-markdown.md#code-snippets) vonatkozó általános útmutató tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="664cb-189">The basic rules for including code are located in the general guidance on [code](how-to-write-use-markdown.md#code-snippets).</span></span>

<span data-ttu-id="664cb-190">A kódot az alábbi szintaxist követve foglalhatja bele:</span><span class="sxs-lookup"><span data-stu-id="664cb-190">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* <span data-ttu-id="664cb-191">`-<language>` (*nem kötelező*, de *ajánlott*).</span><span class="sxs-lookup"><span data-stu-id="664cb-191">`-<language>` (*optional* but *recommended*)</span></span>
  * <span data-ttu-id="664cb-192">A hivatkozott kódrészlet nyelve.</span><span class="sxs-lookup"><span data-stu-id="664cb-192">Language of the code snippet being referenced.</span></span> <span data-ttu-id="664cb-193">A támogatott értékek listáját a [Támogatott nyelvek](#supported-languages) szakaszban tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="664cb-193">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

* <span data-ttu-id="664cb-194">`<name>` (*választható*)</span><span class="sxs-lookup"><span data-stu-id="664cb-194">`<name>` (*optional*)</span></span>
  * <span data-ttu-id="664cb-195">A kódtöredék neve.</span><span class="sxs-lookup"><span data-stu-id="664cb-195">Name for the code snippet.</span></span> <span data-ttu-id="664cb-196">A megjelenő HTML-re ez nincs hatással, de olvashatóbbá teszi a Markdown-forrást.</span><span class="sxs-lookup"><span data-stu-id="664cb-196">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

* <span data-ttu-id="664cb-197">`<pathToFile>` (*kötelező*)</span><span class="sxs-lookup"><span data-stu-id="664cb-197">`<pathToFile>` (*mandatory*)</span></span>
  * <span data-ttu-id="664cb-198">Relatív elérési út a fájlrendszerben, amely a hivatkozandó kódtöredék-fájlra mutat.</span><span class="sxs-lookup"><span data-stu-id="664cb-198">Relative path in the file system that indicates the code snippet file to reference.</span></span> <span data-ttu-id="664cb-199">Ez a .NET-dokumentációs készletet felépítő különféle tárak miatt bonyolult lehet.</span><span class="sxs-lookup"><span data-stu-id="664cb-199">This can be complicated by the different repos that make up the .NET doc set.</span></span> <span data-ttu-id="664cb-200">A .NET-minták a dotnet/samples tárban találhatók.</span><span class="sxs-lookup"><span data-stu-id="664cb-200">The .NET samples are in the dotnet/samples repo.</span></span> <span data-ttu-id="664cb-201">Minden kódrészlet elérési útjának kezdete a `~/samples`, az elérési út többi része pedig a forrás elérési útja a tár gyökerétől.</span><span class="sxs-lookup"><span data-stu-id="664cb-201">All snippet paths would start with `~/samples`, the rest of the path being the path to the source from the root of that repo.</span></span>

* <span data-ttu-id="664cb-202">`<queryoption>` (*választható*)</span><span class="sxs-lookup"><span data-stu-id="664cb-202">`<queryoption>` (*optional*)</span></span>
  * <span data-ttu-id="664cb-203">Azt határozza meg, hogyan legyen beolvasva a kód a fájlból:</span><span class="sxs-lookup"><span data-stu-id="664cb-203">Used to specify how the code should be retrieved from the file:</span></span>
    * <span data-ttu-id="664cb-204">`#`:  `#{tagname}` (címkenév) *vagy* `#L{startlinenumber}-L{endlinenumber}` (sortartomány).</span><span class="sxs-lookup"><span data-stu-id="664cb-204">`#`:  `#{tagname}` (tag name) *or* `#L{startlinenumber}-L{endlinenumber}` (line range).</span></span>
    <span data-ttu-id="664cb-205">Nem javasoljuk a sorok számának használatát, mert ezek változhatnak.</span><span class="sxs-lookup"><span data-stu-id="664cb-205">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="664cb-206">A kódrészletekre való hivatkozás javasolt módja a címkenevekre való hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="664cb-206">Tag name is the preferred way of referencing code snippets.</span></span> <span data-ttu-id="664cb-207">Használjon értelemmel bíró címkeneveket.</span><span class="sxs-lookup"><span data-stu-id="664cb-207">Use meaningful tag names.</span></span> <span data-ttu-id="664cb-208">(Sok címke az előző platformról lett áttelepítve, és a címkéknek olyan neveik vannak, mint `Snippet1`, `Snippet2` stb. Ezt a gyakorlatot sokkal nehezebb folytatni.)</span><span class="sxs-lookup"><span data-stu-id="664cb-208">(Many snippets were migrated from a previous platform and the tags have names such as `Snippet1`, `Snippet2` etc. That practice is much harder to maintain.)</span></span>
    * <span data-ttu-id="664cb-209">`range`: `?range=1,3-5` Sorokból álló tartomány.</span><span class="sxs-lookup"><span data-stu-id="664cb-209">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="664cb-210">Ebben a példában az 1., a 3., a 4. és az 5. sor szerepel.</span><span class="sxs-lookup"><span data-stu-id="664cb-210">This example includes lines 1, 3, 4, and 5.</span></span>

<span data-ttu-id="664cb-211">Javasoljuk a címkenév lehetőség használatát, amikor csak lehetséges.</span><span class="sxs-lookup"><span data-stu-id="664cb-211">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="664cb-212">A címkenév a régió vagy kódhoz fűzött megjegyzés neve `Snippettagname` formátumban a forráskódban.</span><span class="sxs-lookup"><span data-stu-id="664cb-212">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="664cb-213">A következő példa bemutatja, hogyan hivatkozzon a `BasicThrow` címkenévre:</span><span class="sxs-lookup"><span data-stu-id="664cb-213">The following example shows how to refer to the tag name `BasicThrow`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

<span data-ttu-id="664cb-214">A **dotnet/samples** tárban lévő forráshoz vezető relatív elérési út a `~/samples` mintát követi.</span><span class="sxs-lookup"><span data-stu-id="664cb-214">The relative path to the source in the **dotnet/samples** repo follows the `~/samples` path.</span></span>

<span data-ttu-id="664cb-215">A kódrészletcímkék struktúráját pedig [ebben a forrásfájlban](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="664cb-215">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span></span> <span data-ttu-id="664cb-216">További információt a kódtöredékek forrásfájljaiban szereplő címkenevek nyelv szerinti megjelenéséről a [DocFX-irányelvek](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file) című leírásban talál.</span><span class="sxs-lookup"><span data-stu-id="664cb-216">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="664cb-217">A következő példa bemutatja mindhárom .NET-nyelvben a belefoglalt kódot:</span><span class="sxs-lookup"><span data-stu-id="664cb-217">The following example shows code included in all three .NET languages:</span></span>

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

<span data-ttu-id="664cb-218">A teljes programok kódrészleteinek belefoglalása biztosítja, hogy minden kód futtatva legyen a Continuous Integration (CI) rendszerünkben.</span><span class="sxs-lookup"><span data-stu-id="664cb-218">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="664cb-219">Ha azonban valami olyasmit kell bemutatnia, ami fordításkori vagy futásidejű hibákat okoz, akkor használhat beágyazott kódblokkokat.</span><span class="sxs-lookup"><span data-stu-id="664cb-219">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

## <a name="images"></a><span data-ttu-id="664cb-220">Képek</span><span class="sxs-lookup"><span data-stu-id="664cb-220">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="664cb-221">Statikus képek vagy animált GIF-ek</span><span class="sxs-lookup"><span data-stu-id="664cb-221">Static image or animated GIF</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a><span data-ttu-id="664cb-222">Hivatkozott kép</span><span class="sxs-lookup"><span data-stu-id="664cb-222">Linked image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a><span data-ttu-id="664cb-223">Videók</span><span class="sxs-lookup"><span data-stu-id="664cb-223">Videos</span></span>

<span data-ttu-id="664cb-224">Jelenleg a Channel 9 és a YouTube szolgáltatásokban elérhető videókat ágyazhatja be a következő szintaxissal:</span><span class="sxs-lookup"><span data-stu-id="664cb-224">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="664cb-225">Channel 9</span><span class="sxs-lookup"><span data-stu-id="664cb-225">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="664cb-226">A videó megfelelő URL-címének beszerzéséhez válassza a **Beágyazás** lapfület a videókeret alatt, és másolja ki az URL-címet az `<iframe>` elemből.</span><span class="sxs-lookup"><span data-stu-id="664cb-226">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="664cb-227">Példa:</span><span class="sxs-lookup"><span data-stu-id="664cb-227">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="664cb-228">YouTube</span><span class="sxs-lookup"><span data-stu-id="664cb-228">YouTube</span></span>

<span data-ttu-id="664cb-229">A videó megfelelő URL-címének beszerzéséhez kattintson a jobb gombbal a videóra, válassza a **Beágyazási kód másolása** lehetőséget, és másolja ki az URL-címet az `<iframe>` elemből.</span><span class="sxs-lookup"><span data-stu-id="664cb-229">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="664cb-230">Példa:</span><span class="sxs-lookup"><span data-stu-id="664cb-230">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="664cb-231">A docs.microsoft bővítményei</span><span class="sxs-lookup"><span data-stu-id="664cb-231">docs.microsoft extensions</span></span>

<span data-ttu-id="664cb-232">A docs.microsoft néhány további bővítményt kínál a GitHub Flavored Markdown nyelvhez.</span><span class="sxs-lookup"><span data-stu-id="664cb-232">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="checked-lists"></a><span data-ttu-id="664cb-233">Listajeles listák</span><span class="sxs-lookup"><span data-stu-id="664cb-233">Checked lists</span></span>

<span data-ttu-id="664cb-234">A listák készítéséhez egyéni stílus használható.</span><span class="sxs-lookup"><span data-stu-id="664cb-234">A custom style is available for lists.</span></span> <span data-ttu-id="664cb-235">A listák zöld pipákkal is megjeleníthetők.</span><span class="sxs-lookup"><span data-stu-id="664cb-235">You can render lists with green check marks.</span></span>

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

<span data-ttu-id="664cb-236">Ez így jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="664cb-236">This renders as:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="664cb-237">.NET Core-alkalmazások létrehozásának módja</span><span class="sxs-lookup"><span data-stu-id="664cb-237">How to create a .NET Core app</span></span>
> * <span data-ttu-id="664cb-238">Hivatkozás hozzáadása a Microsoft.XmlSerializer.Generator csomaghoz</span><span class="sxs-lookup"><span data-stu-id="664cb-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="664cb-239">A MyApp.csproj szerkesztése függőségek hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="664cb-239">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="664cb-240">Osztály és XmlSerializer hozzáadása</span><span class="sxs-lookup"><span data-stu-id="664cb-240">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="664cb-241">Alkalmazás fordítása és futtatása</span><span class="sxs-lookup"><span data-stu-id="664cb-241">How to build and run the application</span></span>

<span data-ttu-id="664cb-242">A listajeles listákra gyakorlati példát a [.NET Core-dokumentációban](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator) talál.</span><span class="sxs-lookup"><span data-stu-id="664cb-242">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="664cb-243">Gombok</span><span class="sxs-lookup"><span data-stu-id="664cb-243">Buttons</span></span>

<span data-ttu-id="664cb-244">Gombhivatkozások:</span><span class="sxs-lookup"><span data-stu-id="664cb-244">Button links:</span></span>

```markdown
> [!div class="button"]
> [button links](dotnet-contribute.md)
```

<span data-ttu-id="664cb-245">Ez így jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="664cb-245">This renders as:</span></span>

> [!div class="button"]
> [<span data-ttu-id="664cb-246">gombhivatkozások</span><span class="sxs-lookup"><span data-stu-id="664cb-246">button links</span></span>](dotnet-contribute.md)

<span data-ttu-id="664cb-247">A gobokra gyakorlati példát a [Visual Studio dokumentációjában](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio) talál.</span><span class="sxs-lookup"><span data-stu-id="664cb-247">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="664cb-248">Lépésről lépésre</span><span class="sxs-lookup"><span data-stu-id="664cb-248">Step-by-steps</span></span>

```markdown
>[!div class="step-by-step"]
> [Pre](../docs/csharp/expression-trees-interpreting.md)
> [Next](../docs/csharp/expression-trees-translating.md)
```

<span data-ttu-id="664cb-249">A lépésről lépésre módszerre gyakorlati példát a [C# útmutatójában](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure) talál.</span><span class="sxs-lookup"><span data-stu-id="664cb-249">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
