---
title: Sablon és segédlet .NET-cikkekhez
description: Ez a cikk egy hasznos sablont tartalmaz, amelyet új cikkek létrehozására használhat a .NET-dokumentumtárakban
ms.date: 11/07/2018
ms.openlocfilehash: 08c8e19c858e7417d49cc2de543c67f330b93e89
ms.sourcegitcommit: b0556fc33803358009a030ac9efcaed23f562868
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53264502"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a>Metaadatok és Markdown-sablon .NET-dokumentumokhoz

Ez a dotnet/docs sablon példákat tartalmaz a Markdown szintaxisára, valamint útmutatást a metaadatok beállításához.

Markdown-fájl létrehozásakor át kell másolnia a megadott sablont az új fájlba, ki kell töltenie a metaadatokat az alább megadott módon, a fenti H1 címsorban pedig a cikk címét kell megadnia.

## <a name="metadata"></a>Metaadatok

A szükséges metaadatblokk a következő mintául megadott metaadatblokkban található:

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- A kettőspont (:) és a metaadatelem értéke között lennie **kell** szóköznek.
- Az értékben (például a címben) megadott kettőspontok a metaadat-elemző hibás működését eredményezik. Ebben az esetben foglalja a címet kettős idézőjelek közé (például: `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: Megjelenik a keresőmotorok keresési eredményeiben. A cím ne legyen azonos a H1 címsorban megadott címmel, és legfeljebb 60 karaktert tartalmazhat.
- **description**: Összefoglalja a cikk tartalmát. Általában megjelenik a keresési eredmények oldalán, de nem használatos a keresési eredmények rangsorolásához. A hossza 115–145 karakter legyen szóközökkel együtt.
- **author**: Az author (szerző) mezőnek tartalmaznia kell a szerző **GitHub-felhasználónevét**.
- **ms.date**: A legutóbbi jelentős frissítés dátuma. Frissítse ezt az értéket a meglévő cikkekben, ha áttekintette és átdolgozta a teljes cikket. A kisebb javítások, például az elírások és hasonlók miatt nem szükséges frissíteni az értékét.

Más metaadatok is kapcsolódnak minden cikkhez, de általában a legtöbb metaadatértéket a mappa szintjén alkalmazzuk **docfx.json** fájlként megadva.

## <a name="basic-markdown-gfm-and-special-characters"></a>Alapszintű Markdown, GFM és különleges karakterek

A Markdown, a GitHub Flavored Markdown (GFM) és az OPS-specifikus bővítmények alapjait a [Markdown](how-to-write-use-markdown.md) és a [Markdown-referencia](markdown-reference.md) általános cikkeiből sajátíthatja el.

A Markdown különleges karaktereket, például \* , \` és \# használ a formázáshoz. Ha ezek közül a karakterek közül valamelyiket szeretné belefoglalni a dokumentumba, tegye az alábbi két dolog közül valamelyiket:

- Írjon be egy fordított perjel karaktert a különleges karakter elé a „kikerüléséhez” (például a \* karakterhez `\*`)
- Használja a karakter [HTML-entitáskódját](http://www.ascii.cl/htmlcodes.htm) (például a &#42; karakterhez `&#42;`).

## <a name="file-names"></a>Fájlnevek

A fájlnevek a következő szabályokat használják:

* Csak kisbetűk, számok és kötőjelek használhatók.
* Szóköz és írásjelkarakter nem használható. A kötőjel a szavak és számok elválasztására használható.
* Konkrét műveleteket használjon, például develop (fejlesztés), buy (vásárlás), build (fordítás), troubleshoot (hibakeresés). Ne használja az angol igék -ing végződésű alakját.
* Ne használjon nem önálló szavakat (a, and, the, in, or, etc).
* Markdown-formátumot kell használni, .md kiterjesztéssel.
* Ésszerűen rövid fájlneveket használjon. Ezek a cikkek URL-címének részei.

## <a name="headings"></a>Fejlécek

Csak a mondat első betűje legyen nagybetű. A cím első betűje mindig nagybetű legyen.

## <a name="text-styling"></a>Szövegstílus

*Dőltbetű* Használja fájlokhoz, mappákhoz, elérési utakhoz (hosszú elemek esetén törje ezeket a saját külön sorukba) és új kifejezésekhez.

**Fékövér** Használja a felhasználói felület elemeihez.

`Code` Használja beágyazott kódokhoz, programnyelvi kulcsszavakhoz, NuGet-csomagok nevéhez, parancssori parancsokhoz, adatbázistábla és oszlopnevekhez, valamint olyan URL-címekhez, amelyekre nem lehet rákattintani.

## <a name="links"></a>Hivatkozások

A horgonyokra, belső hivatkozásokra, más dokumentumokra mutató hivatkozásokra, belefoglalt kódokra és külső hivatkozásokra vonatkozóan olvassa el a [Hivatkozások](how-to-write-links.md) általános cikket.

A .NET-dokumentumok csapata a következő konvenciókat használja:

- A legtöbbször relatív hivatkozásokat használunk, és nem javasoljuk `~/` használatát a hivatkozásokban, mert a relatív hivatkozások a forrásban lesznek feloldva a GitHubon. Ha azonban egy függő tárban lévő fájlra hivatkozunk, akkor a `~/` karaktert használjuk az elérési út megadásához. Mivel a függő tárban lévő fájlok más helyen vannak a GitHubon, a hivatkozások feloldása nem lesz megfelelő relatív hivatkozásokkal, függetlenül attól, hogyan írták őket.
- A C# nyelvi specifikációk és a Visual Basic nyelvi specifikációk .NET-dokumentumokba való belefoglalása a programnyelvi kódtárakból a forrás belefoglalásával történik. A Markdown-források kezelése a [csharplang](https://github.com/dotnet/csharplang) és a [vblang](https://github.com/dotnet/vblang) kódtárakban történik.

A specifikációkra mutató hivatkozásoknak azokra a forráskönyvtárakra kell mutatniuk, amelyekben ezek a specifikációk találhatók. C# esetén ez a **~/_csharplang/spec**, VB esetén pedig a **~/_vblang/spec**, a következő példához hasonlóan:

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a>API-kra mutató hivatkozások

A build rendszer rendelkezik néhány bővítménnyel, amelyek lehetővé teszik a .NET API-kra való hivatkozást, anélkül, hogy külső hivatkozásokat kellene használni. Az alábbi szintaxisok egyikét használhatja:

1. Automatikus hivatkozás: `<xref:UID>` vagy `<xref:UID?displayProperty=nameWithType>`

   A `displayProperty` lekérdezési paraméter teljesen minősített hivatkozási szöveget eredményez. Alapértelmezés szerint a hivatkozás szövegében csak a tag vagy a típus neve jelenik meg.

2. Markdown-hivatkozás: `[link text](xref:UID)`

   Akkor használja, ha testre szeretné szabni a megjelenített hivatkozási szöveget.

Példák:

- `<xref:System.String>`, megjelenítve [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>`, megjelenítve [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)`, megjelenítve [String class](https://docs.microsoft.com/dotnet/api/system.string)

Ezen jelölés használatával kapcsolatban a [Kereszthivatkozások használata](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference) című témakörben találhat további információt.

Ha néhány UID-azonosító \`, \# vagy \* speciális karaktert tartalmaz, akkor az UID-értéket a `%60`, a `%23`, illetőleg a `%2A` karakterrel kell HTML-kódolásban megadni. Időnként előfordul a zárójelek kódolása, de ez nem kötelező.

Példák:

- A System.Threading.Tasks.Task\`1 `System.Threading.Tasks.Task%601` lesz
- A System.Exception.\#ctor `System.Exception.%23ctor` lesz
- A System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` lesz

Az UID-típusokat, a tag túlterhelési listáját vagy az adott túlterhelt tagot a `https://xref.docs.microsoft.com/autocomplete` weblapon találja. A(z) `?text=*\<type-member-name>*` lekérdezési sztring azonosítja azt a tagtípust, amelyiknek az UID-jét látni szeretné. A `https://xref.docs.microsoft.com/autocomplete?text=string.format` például a [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) túlterheléseket kéri le. Az eszköz a megadott `text` lekérdezési paramétert az UID bármely részében keresi. Kereshet például a tagnévre (ToString), a tagnév egy részére (ToStri), a típusra és a tagnévre (Double.ToString) stb.

Ha beszúr egy \* szimbólumot (vagy `%2A`-t) az UID után, a hivatkozás a túlterhelések oldalát fogja jelölni, nem pedig egy konkrét API-t. Ezt használhatja például, ha a [List\<T>.BinarySearch metódusra](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) generikus módon szeretne hivatkozni egy adott túlterhelés, például a [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) helyett. A \* szimbólumot tagoldalra való hivatkozáshoz is használhatja, ha a tag nincs túlterhelve, így nem kell belefoglalnia a paraméterek listáját a UID-be.

Meghatározott metódus-túlterhelésre való hivatkozáshoz meg kell adnia a metódus összes paraméterének teljes típusnevét. Az \<xref:System.DateTime.ToString> például a paraméter nélküli [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) metódusra hivatkozik, míg az \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> a [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) metódusra.

Általános típusra, például a [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) típusra való hivatkozáshoz a \` (`%60`) karaktert használja, amelyet az általános típusú paraméterek számának kell követnie. A(z) `<xref:System.Nullable%601>` például a [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) típusra hivatkozik, míg a(z) `<xref:System.Func%602>` a [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegáltra.

## <a name="code"></a>Code

A kód belefoglalásának legjobb módja kódrészletek belefoglalása egy működő példányból. Hozza létre a mintát a [hozzájárulás a .NET-hez](dotnet-contribute-process.md#contributing-to-samples) cikk útmutatását követve. A kód belefoglalásának alapvető szabályait a [kódra](how-to-write-use-markdown.md#code-includes) vonatkozó általános útmutató tartalmazza.

A kódot az alábbi szintaxist követve foglalhatja bele:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*nem kötelező*, de *ajánlott*).
  * A hivatkozott kódrészlet nyelve. A támogatott értékek listáját a [Támogatott nyelvek](#supported-languages) szakaszban tekintheti meg.

* `<name>` (*választható*)
  * A kódtöredék neve. A megjelenő HTML-re ez nincs hatással, de olvashatóbbá teszi a Markdown-forrást.

* `<pathToFile>` (*kötelező*)
  * Relatív elérési út a fájlrendszerben, amely a hivatkozandó kódtöredék-fájlra mutat. Ez a .NET-dokumentációs készletet felépítő különféle tárak miatt bonyolult lehet. A .NET-minták a dotnet/samples tárban találhatók. Minden kódrészlet elérési útjának kezdete a `~/samples`, az elérési út többi része pedig a forrás elérési útja a tár gyökerétől.

* `<queryoption>` (*választható*)
  * Azt határozza meg, hogyan legyen beolvasva a kód a fájlból:
    * `#`:  `#{tagname}` (címkenév) *vagy* `#L{startlinenumber}-L{endlinenumber}` (sortartomány).
    Nem javasoljuk a sorok számának használatát, mert ezek változhatnak. A kódrészletekre való hivatkozás javasolt módja a címkenevekre való hivatkozás. Használjon értelemmel bíró címkeneveket. (Sok címke az előző platformról lett áttelepítve, és a címkéknek olyan neveik vannak, mint `Snippet1`, `Snippet2` stb. Ezt a gyakorlatot sokkal nehezebb folytatni.)
    * `range`: `?range=1,3-5` Sorokból álló tartomány. Ebben a példában az 1., a 3., a 4. és az 5. sor szerepel.

Javasoljuk a címkenév lehetőség használatát, amikor csak lehetséges. A címkenév a régió vagy kódhoz fűzött megjegyzés neve `Snippettagname` formátumban a forráskódban. A következő példa bemutatja, hogyan hivatkozzon a `BasicThrow` címkenévre:

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

A **dotnet/samples** tárban lévő forráshoz vezető relatív elérési út a `~/samples` mintát követi.

A kódrészletcímkék struktúráját pedig [ebben a forrásfájlban](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) tekintheti meg. További információt a kódtöredékek forrásfájljaiban szereplő címkenevek nyelv szerinti megjelenéséről a [DocFX-irányelvek](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file) című leírásban talál.

A következő példa bemutatja mindhárom .NET-nyelvben a belefoglalt kódot:

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

A teljes programok kódrészleteinek belefoglalása biztosítja, hogy minden kód futtatva legyen a Continuous Integration (CI) rendszerünkben. Ha azonban valami olyasmit kell bemutatnia, ami fordításkori vagy futásidejű hibákat okoz, akkor használhat beágyazott kódblokkokat.

## <a name="images"></a>Képek

### <a name="static-image-or-animated-gif"></a>Statikus képek vagy animált GIF-ek

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a>Hivatkozott kép

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a>Videók

Jelenleg a Channel 9 és a YouTube szolgáltatásokban elérhető videókat ágyazhatja be a következő szintaxissal:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

A videó megfelelő URL-címének beszerzéséhez válassza a **Beágyazás** lapfület a videókeret alatt, és másolja ki az URL-címet az `<iframe>` elemből. Példa:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

A videó megfelelő URL-címének beszerzéséhez kattintson a jobb gombbal a videóra, válassza a **Beágyazási kód másolása** lehetőséget, és másolja ki az URL-címet az `<iframe>` elemből.

```markdown
> [!VIDEO <youtube_video_link>]
```

Példa:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>A docs.microsoft bővítményei

A docs.microsoft néhány további bővítményt kínál a GitHub Flavored Markdown nyelvhez.

### <a name="checked-lists"></a>Listajeles listák

A listák készítéséhez egyéni stílus használható. A listák zöld pipákkal is megjeleníthetők.

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

Ez így jelenik meg:

> [!div class="checklist"]
> * .NET Core-alkalmazások létrehozásának módja
> * Hivatkozás hozzáadása a Microsoft.XmlSerializer.Generator csomaghoz
> * A MyApp.csproj szerkesztése függőségek hozzáadásához
> * Osztály és XmlSerializer hozzáadása
> * Alkalmazás fordítása és futtatása

A listajeles listákra gyakorlati példát a [.NET Core-dokumentációban](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator) talál.

### <a name="buttons"></a>Gombok

Gombhivatkozások:

```markdown
> [!div class="button"]
> [button links](dotnet-contribute.md)
```

Ez így jelenik meg:

> [!div class="button"]
> [gombhivatkozások](dotnet-contribute.md)

A gobokra gyakorlati példát a [Visual Studio dokumentációjában](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio) talál.

### <a name="step-by-steps"></a>Lépésről lépésre

```markdown
>[!div class="step-by-step"]
> [Pre](../docs/csharp/expression-trees-interpreting.md)
> [Next](../docs/csharp/expression-trees-translating.md)
```

A lépésről lépésre módszerre gyakorlati példát a [C# útmutatójában](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure) talál.
