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
ms.openlocfilehash: 64921bacf48e638221048db4b24e1a941f1d2777
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609545"
---
# <a name="markdown-reference-for-ops"></a>Markdown-referencia az OPS-hez

A Markdown egy egyszerűen kezelhető jelölőnyelv, amely a formázatlan szövegek formázására alkalmas szintaxist használ. Az Open Publishing Services (OPS) támogatja a Markdown CommonMark szabványát, és emellett számos olyan egyéni Markdown-bővítményt is, amelyekkel sokrétűbbé tehetők a docs.microsoft.com webhelyen található tartalmak. A cikk betűrendbe szedett referenciát nyújt a Markdown OPS-ben történő és docs.microsoft.com-tartalmak létrehozásához való használatához.

Markdown-szintaxist bármilyen szövegszerkesztő használatával írhat. Ha olyan szövegszerkesztőt keres, amely a szabványos Markdown-szintaxis mellett támogatja az egyéni OPS-bővítményeket is, javasoljuk a [VS Code](https://code.visualstudio.com/) alkalmazás a [Docs Authoring Pack (Docs-közreműködői csomag)](https://aka.ms/DocsAuthoringPack) bővítmény telepítésével való használatát.

Az OPS már minden újonnan létrehozott adattárhoz szabványos módon a Markdig feldolgozót használja, és a korábban létrehozott adattárak Markdigbe való migrálása is folyamatban van. A [https://babelmark.github.io/](https://babelmark.github.io/) címen tesztelheti, hogyan jelennek meg a Markdown-szövegek a Markdigben más szövegrenderelő motorok képességeivel összevetve.

## <a name="alerts-note-tip-important-caution-warning"></a>Riasztások (Megjegyzés, Tipp, Fontos, Figyelem, Figyelmeztetés)

Az Alerts (Riasztások) egy OPS-hez készült Markdown-bővítmény, amely olyan szövegblokkok létrehozására szolgál, amelyek a tartalom fontosságát jelző különböző színekkel és ikonokkal jelennek meg a docs.microsoft.com webhelyen. A következő riasztási típusok támogatottak:

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

Ezek a riasztások a következőképpen jelennek meg a docs.microsoft.com webhelyen:

> [!NOTE]
> Olyan információk, amelyeket a felhasználónak akkor is észre kell vennie, ha csak átfutja a szöveget.

> [!TIP]
> Olyan kiegészítő információk, amelyek segítenek a felhasználónak sikeresebben végezni a munkafolyamatot.

> [!IMPORTANT]
> Alapvető információk, amelyek feltétlenül szükségesek a sikeres végrehajtáshoz.

> [!CAUTION]
> Egy művelet potenciális negatív következményei.

> [!WARNING]
> Egy művelet meghatározott veszélyes következményei.

## <a name="code-snippets"></a>Kódrészletek

A Markdown-fájlokba kódrészletek is beágyazhatók:

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a>Fejlécek

Az OPS a Markdown-fejlécek hat szintjét támogatja:

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- A legutolsó `#` szimbólum és a címsor szövege között szóköznek kell szerepelnie.
- Minden egyes Markdown-fájlnak tartalmaznia kell pontosan egy H1 fejlécet.
- A H1 fejlécnek az első tartalomnak kell lennie közvetlenül a YML-metaadatblokk után.
- A H2 fejlécek megjelennek a közzétett fájl jobb oldali navigációs menüjében. Az alacsonyabb szintű fejlécek esetében ez nem történik meg, ezért a H2 fejléceket használja stratégiai pontokon, hogy megkönnyítse a navigációt a felhasználók számára.
- A HTML-fejlécek (mint például a `<h1>`) használata nem ajánlott, és bizonyos esetekben figyelmeztetéseket eredményezhet a buildelési folyamat során.
- A fájlokban található egyes fejlécekre [könyvjelzőkkel](#bookmark-links) hivatkozhat.

## <a name="html"></a>HTML

Bár a Markdown támogatja a beágyazott HTML használatát, az OPS-sel való közzététel esetén nem ajánljuk a HTML használatát, mert néhány, korlátozott számú értéket kivéve általában buildelési hibákat és figyelmeztetéseket váltanak ki. <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a>Képek

Kép beágyazásának szintaxisa:

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

Ahol az `alt text` (helyettesítő szöveg) a kép rövid leírása, a `<folder path>` (mappa elérési útja) pedig a kép relatív elérési útja. A helyettesítő szövegek a gyengén látó felhasználók által használt képernyőolvasó programokhoz szükségesek. Ezen kívül hasznosak lehetnek akkor is, ha hiba lép fel az oldal megjelenítésekor, és nem jelennek meg a képek.

A képeket egy `/media` elnevezésű mappában kell tárolni a dokumentumkészleten belül. Alapértelmezés szerint a következő képfájltípusok támogatottak:

- .jpg
- .png

Más képtípusok támogatását is biztosíthatja, ha erőforrásként hozzáadja őket a dokumentumkészlet docfx.json fájljához <!--add link to reference when available-->.

## <a name="links"></a>Hivatkozások

A legtöbb esetben az OPS hagyományos Markdown-hivatkozásokat használ a más fájlokra vagy oldalakra történő hivatkozáshoz. A különböző hivatkozástípusokat a következő alfejezetekben mutatjuk be.

> [!TIP]
> A VS Code alkalmazáshoz készült Docs-közreműködői csomag anélkül segíti a relatív hivatkozások és könyvjelzők helyes beszúrását, hogy az elérési utakkal kellene bajlódnia.

> [!IMPORTANT]
> Microsoft-oldalakra mutató hivatkozás készítésekor ne használjon olyan területibeállítás-kódokat, mint például a hu-HU. A kódban explicit módon megadott területi beállítások megakadályozhatják a honosított tartalmak megjelenítését, ez pedig rontja a más területi beállítást használók felhasználói élményét, és jelentős honosítási költségeket vonhat maga után. Amikor kimásol egy URL-címet a böngészőből, a rendszer alapértelmezetten hozzáadja a területi beállítás kódját is, ezért azt saját kezűleg kell törölnie, amikor a hivatkozást létrehozza. Használja például így:
>
> `[Microsoft](https://www.microsoft.com)`
>
> Nem pedig így:
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a>Ugyanazon dokumentumkészlet más fájljaira mutató relatív hivatkozások

A relatív elérési út a célfájl az aktuális fájlhoz viszonyított elérési útja. Az OPS-ben lehetősége van relatív elérési út használatával hivatkozni egy másik fájlra ugyanazon a dokumentumkészleten belül. A relatív elérési utak szintaxisa a következő:

```markdown
[link text](../../folder/filename.md)
```

Ahol a `../` a hierarchia eggyel magasabb szintjét jelzi.

- A relatív elérési utat a buildelési folyamat során oldja fel a rendszer, beleértve az .md kiterjesztés eltávolítását is.
- A „../” használatával hivatkozhat a szülőmappában található fájlokra, de az adott fájlnak ugyanabban a dokumentumkészletben kell lennie. A „../” nem használható másik dokumentumkészlet fájljaira való hivatkozásra.
- Az OPS a relatív elérési utak egy speciális formájának használatát is lehetővé teszi, amelyeknél az elérési út a „~” szimbólummal kezdődik (például ~/foo/bar.md). Ezzel a szintaxissal egy dokumentumkészlet gyökérmappájához képest határozhatók meg a fájlok. Az ilyen útvonal feloldása és ellenőrzése is megtörténik az összeállítás során.

> [!IMPORTANT]
> A relatív útvonalakban adja meg a fájlnévkiterjesztéseket is. A rendszer a buildelés során ellenőrzi, hogy létezik-e a relatív elérési úttal hivatkozott fájl. Ha a relatív elérési út nem tartalmaz fájlnévkiterjesztést, a buildelési folyamat valószínűleg figyelmeztetni fogja, hogy a hivatkozás hibás. Használja például így:
>
> `[link text](../../folder/filename.md)`
>
> Nem pedig így:
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a>Abszolút hivatkozások más fájlokra az OPS-ben

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

A fájlnévkiterjesztést (.md) ne adja meg. Ez az Azure „articles” („cikkek”) dokumentumkészletén kívüli Linux-áttekintési fájlra mutat.

### <a name="links-to-external-sites"></a>Külső webhelyekre mutató hivatkozások

```markdown
[Microsoft](https://www.microsoft.com)
```

Másik weblapra mutató URL-alapú hivatkozás (tartalmaznia kell a https:// előtagot).

### <a name="bookmark-links"></a>Könyvjelző-hivatkozások

Könyvjelző-hivatkozás egy másik, ugyanabban az adattárban lévő fájl egyik fejlécére:

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

Könyvjelző-hivatkozás az aktuális fájl egyik fejlécére:

```markdown
[Managed Disks](#managed-disks)
```

Használja a kettőskeresztet, majd írja be a fejléc szövegét, írásjelek nélkül és a szóközöket alulvonásokkal helyettesítve.

### <a name="explicit-anchor-links"></a>Explicit horgonyhivatkozások

Az `<a>` HTML-címkével készíthető explicit horgonyhivatkozások alkalmazása **nem szükséges és nem is ajánlott**, csak a főoldalak és kezdőlapok esetében. Az általános Markdown-fájlok esetén inkább használjon könyvjelzőket a fentebb leírt módon. A főoldalaknál és kezdőlapoknál a következő módon használhatja a horgonyokat:

`## <a id="AnchorText"> </a>Header text` vagy `## <a name="AnchorText"> </a>Header text`

Explicit horgonyra mutató hivatkozás létrehozásához a következő szintaxist használhatja:

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a>XREF-hivatkozások (kereszthivatkozások)

Az aktuális dokumentumkészletben vagy más dokumentumkészletekben szereplő, automatikusan generált API-referenciaoldalakra mutató hivatkozás létrehozásához használjon XREF-hivatkozásokat az egyedi azonosítóval (UID).

> [!NOTE]
> A más dokumentumkészletek API-referenciaoldalaira mutató hivatkozások készítéséhez hozzá kell adnia az `xrefService` konfigurációt a `docfx.json` fájlhoz.
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

A UID a teljes osztály- és tagnévnek felel meg. Ha beszúr egy * szimbólumot az UID után, a hivatkozás a túlterhelések oldalát fogja jelölni, nem pedig egy konkrét API-t. A `List<T>.BinarySearch*` használatával például a BinarySearch metódus oldalára fog hivatkozni, nem pedig egy adott túlterhelésre, mint például a `List<T>.BinarySearch(T, IComparer<T>)`.

Az következő szintaxisok egyikét használhatja:

- Automatikus hivatkozás: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`

  A nem kötelező `displayProperty` lekérdezési paraméter teljesen minősített hivatkozási szöveget eredményez. Alapértelmezés szerint a hivatkozás szövegében csak a tag vagy a típus neve jelenik meg.

- Markdown-hivatkozás: `[link text](xref:UID)`
  
  Akkor használja, ha testre szeretné szabni a megjelenített hivatkozási szöveget.

Példák:

- `<xref:System.String>`, megjelenítve „String”.
- `<xref:System.String?displayProperty=nameWithType>`, megjelenítve „System.String”.
- `[String class](xref:System.String)`, megjelenítve „String class”.

Jelenleg a UID azonosítók megkeresésének nincs könnyű módszere. <!-- ? -->Egy API UID-azonosítójának megkeresésére a legjobb módszer, hogy megtekinti a hivatkozni kívánt API-lap forrását, és megkeresi az API-hoz tartozó ms.assetid-értéket. A forrásban az egyes túlterhelési értékek nem jelennek meg. Dolgozunk rajta, hogy a jövőben jobb rendszer álljon rendelkezésre.

Ha az UID-azonosító \`, \# vagy \* speciális karaktert tartalmaz, akkor az UID-értéket a `%60`, a `%23`, illetőleg a `%2A` karakterrel kell HTML-kódolásban megadni. Időnként előfordul a zárójelek kódolása, de ez nem kötelező.

Példák:

- A System.Threading.Tasks.Task\`1 `System.Threading.Tasks.Task%601` lesz
- A System.Exception.\#ctor `System.Exception.%23ctor` lesz
- A System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` lesz

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a>Listák (Számozott lista, Listajeles lista, Ellenőrzőlista)

### <a name="numbered-list"></a>Numbered list

Számozott lista létrehozásához nyugodtan használhat mindegyik listaelemnél 1-eseket, az elemek a közzététel után sorszámozott listaként fognak megjelenni. A forrásfájl olvashatóságának javítása érdekében azonban használhat emelkedő számozást is listáiban.

Ne használjon betűket, még egymásba ágyazott listákban sem. Ezek hibásan jelennek meg az OPS-ben való közzététel után. A számokat használó egymásba ágyazott listák közzététel után kisbetűs sorszámozással jelennek meg. Példa:

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

Ez a következőképp jelenik meg:

1. Ez a
1. szülő számozott lista
   1. ez pedig a
   1. beágyazott számozott lista
1. (vége)

### <a name="bulleted-list"></a>Bulleted list

Listajeles lista létrehozásához az egyes sorok elején használjon `-` írásjelet és egy szóközt:

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

Ez a következőképp jelenik meg:

- Ez a
- szülő listajeles lista
  - ez pedig a
  - beágyazott listajeles lista
- Kész!

### <a name="checklist"></a>Ellenőrzőlista

Ellenőrzőlistákat (kizárólag) egy egyedi Markdown-bővítménnyel használhat a docs.microsoft.com webhelyen:

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

A következő példa ekképpen jelenik meg a docs.microsoft.com webhelyen:

> [!div class="checklist"]
> * 1. listaelem
> * 2. listaelem
> * 3. listaelem

Ellenőrzőlistákat a cikkek elején vagy végén használhat annak összefoglalására, hogy „mit fogunk megtanulni” vagy „mit tanultunk meg”. Ne adjon hozzá cikkeihez a tartalmak közt véletlenszerűen elszórt ellenőrzőlistákat.
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a>Következő lépés művelet

Egy egyedi bővítménnyel a Következő lépés művelet gombját is hozzáadhatja (kizárólag) a docs.microsoft.com oldalaihoz.

A szintaxis a következő:

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

Példa:

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

Ez a következőképp jelenik meg:

> [!div class="nextstepaction"]
> [Tudnivalók az alapvető stílusról](style-quick-start.md)

A Következő lépés műveletekben bármilyen támogatott hivatkozásformát használhat, beleértve a más oldalakra mutató Markdown-hivatkozásokat is. A legtöbb esetben a Következő lépés művelet egy relatív hivatkozást tartalmaz, amely egy másik fájlra mutat ugyanazon a dokumentumkészleten belül.

## <a name="section-definition"></a>Szakaszdefiníció

<!-- more info about this would be helpful! -->Előfordulhat, hogy szakaszokat kell definiálnia. Ezt a szintaxist többnyire kódtáblázatokhoz használják.
Tekintse meg az alábbi példát:

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

A fenti idézetblokk Markdown-szövege így jelenik meg:
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a>Választómezők

<!-- could be more clear! -->Ha ugyanahhoz a cikkhez különböző oldalakat szeretne kapcsolni, használjon választókat. Így az olvasók szabadon lépkedhetnek az oldalak között.

> [!NOTE]
> Ez a bővítmény nem egyformán működik a docs.microsoft.com és az MSDN esetében. <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a>Egyszerű választómező

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

...így fog megjelenni:

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a>Többszintű választómező

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

...így fog megjelenni:

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

## <a name="tables"></a>Táblázatok

A Markdown-szintaxissal táblázat a legegyszerűbben függőleges vonal és kötőjel karakterekkel alakítható ki. Normál fejléccel rendelkező táblázatok létrehozásához az első sor után szúrjon be szaggatott vonalat:

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

Ez a következőképp jelenik meg:

|Ez   |egy egyszerű   |táblafejléc|
|----------|-----------|------------|
|itt     |vannak       |az adatok        |
|nem kell|mindennek   |szépen sorba rendezve lennie!||

Fejléc nélküli táblázatot is létrehozhat. Többoszlopos listát például így készíthet:

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

Ez a következőképpen jelenik meg:

|   |   |
| - | - |
| Ez a | táblázat |
| nem tartalmaz | fejlécet |

Az oszlopokat kettőspontokkal igazíthatja:

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

A következőképp jelenik meg:

|                  |
|------------------|
|    jobbra igazított:|
|:balra igazított     |
|:középre zárt        :|

> [!TIP]
> A VS Code alkalmazáshoz készült Docs-közreműködői csomaggal könnyedén adhat tartalmaihoz egyszerű Markdown-táblázatokat!
>
> Használhat ugyanakkor akár [online táblázatkészítő](http://www.tablesgenerator.com/markdown_tables) megoldást is.

### <a name="mx-tdbreakall"></a>mx-tdBreakAll

> [!IMPORTANT]
> Ez a funkció csak a docs.microsoft.com webhelyen működik.

A Markdownnal létrehozott táblázatok olykor túlnyúlnak a jobb oldali navigációs sávon, ezáltal olvashatatlanná válnak. Ez orvosolható a táblázat szükség szerinti tördelésének engedélyezésével. Ehhez elég a táblázatot belefoglalni az egyéni `[!div class="mx-tdBreakAll"]` osztályba.

A következő Markdown-példában szereplő táblázat az `mx-tdBreakAll` nevű osztályba van besorolva egy `div` címke segítségével.

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

Így fog megjelenni:

> [!div class="mx-tdBreakAll"]
> |Név|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Felhasználói felület és utasítások megjelenítése nélkül futtatja a telepítőt.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. A felhasználó felület alapértelmezés szerint rákérdez az újraindításra.|
> |Help|/help|No|Provides help and quick reference. Megmutatja a telepítési parancs helyes használatát, felsorolva minden beállítást és azok működését.|

### <a name="mx-tdcol2breakall"></a>mx-tdCol2BreakAll

> [!IMPORTANT]
> Ez a funkció csak a docs.microsoft.com webhelyen működik.

Előfordulhat, hogy nagyon hosszú szavak szerepelnek a táblázat második oszlopában. Ha megfelelően szeretné tördelni őket, akkor a `div` burkolószintaxissal alkalmazza az `mx-tdCol2BreakAll` osztályt, ahogy ezt korábban bemutattuk.

### <a name="html-tables"></a>HTML-táblázatok

A HTML-táblázatok használata nem ajánlott a docs.microsoft.com webhelyen. Ennek oka, hogy a forrásfájlban olvashatatlanul jelennek meg, az olvashatóság pedig a Markdown egyik fő alapelve.

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a>Videók

### <a name="embedding-videos-into-a-markdown-page"></a>Videók beágyazása Markdown-oldalakba

Az OPS jelenleg a következő három helyen közzétett videók beágyazását támogatja:

- YouTube
- Channel 9
- A Microsoft saját „One Player” rendszere

Videót az alábbi, az OPS által feldolgozott szintaxissal lehet beágyazni.

```markdown
> [!VIDEO <embedded_video_link>]
```

Példa:

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

...a következő módon jelenik meg:

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

A közzétett oldalakon pedig így lesz látható:

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> A CH9-videó URL-hivatkozásának eleje legyen `https`, a vége pedig `/player`. Ellenkező esetben a videó helyett az egész oldalt ágyazná be.

### <a name="uploading-new-videos"></a>Új videók feltöltése

Az új videók feltöltésének folyamata a következő:

1. Csatlakozzon a **docs_video_users** csoporthoz az IDWEB-en.
1. Nyissa meg a https://aka.ms/VideoUploadRequest oldalt, és adja meg a videó adatait. A következőkre lesz szüksége (fontos megjegyezni, hogy ezek az elemek nyilvánosan nem fognak megjelenni):
    1. A videó címe.
    1. Azoknak a termékeknek vagy szolgáltatásoknak a listája, amelyekkel a videó kapcsolatos.
    1. A céloldal vagy (ha még nincs készen az oldal) a dokumentumkészlet, amelybe a videót ágyazni kívánja.
    1. A videó MP4-fájljára mutató hivatkozás (ha még nincs hely, ahol elhelyezheti a fájlt, ideiglenesen használhatja a `\\scratch2\scratch\apex` helyet). Az MP4-fájlnak 720p vagy nagyobb felbontásúnak kell lennie.
    1. A videó leírása.
1. Küldje el (mentse) az elemet.
1. A videó két munkanapon belül fel lesz töltve. A beágyazáshoz szükséges hivatkozás a munkaelembe kerül, és címfeloldás után *visszakerül Önhöz*.
1. Miután megkapta a videó címét, bezárhatja a munkaelemet.
1. A videóra mutató hivatkozást a következő szintaxissal szúrhatja be a bejegyzésbe:

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
