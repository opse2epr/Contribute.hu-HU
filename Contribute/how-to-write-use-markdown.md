---
title: A Markdown használata Docs-tartalmak írásához
description: Ez a cikk alapvető információkat és tájékoztatást nyújt a docs.microsoft.com-cikkekben használt Markdown jelölőnyelvről.
ms.date: 03/26/2019
ms.openlocfilehash: eeb49961fbf530676b55ae4e42d4fca7b8d7edf7
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637483"
---
# <a name="how-to-use-markdown-for-writing-docs"></a>A Markdown használata Docs-tartalmak írásához

A [docs.microsoft.com](http://docs.microsoft.com) cikkei a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható. Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált. A Docs-webhely a Markdown [Markdig változatát](#markdown-flavor) használja.


## <a name="markdown-basics"></a>A Markdown alapjai

### <a name="headings"></a>Fejlécek

Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

A címsorokat atx-stílussal kell megadni. Ez azt jelenti, hogy 1–6 kettőskereszt karaktert (#) kell a sor elejére írni, a számuk a H1–H6 HTML-címsorszintjét jelöli. Fent a címsorokra látható példa, az elsőtől a negyedik szintig.

Egy témakörben **egy és csak egy** első szintű címsornak (H1) kell lennie, ez fog megjelenni a lapon címként.

Ha `#` a cím az utolsó karaktere, akkor még egy `#` karaktert kell a cím végére írni ahhoz, hogy helyesen jelenjen meg. Például így: `# Async Programming in F# #`.

A második szintű címsorokból generálódik a lapon lévő tartalomjegyzék, ez jelenik meg a lap címe alatti „A cikk tartalma” szakaszban.

### <a name="bold-and-italic-text"></a>Félkövér és dőlt szöveg

A **félkövérként** formázandó szöveget zárja dupla csillagjelek közé:

```markdown
This text is **bold**.
```

A *dőltként* formázandó szöveget zárja egyszeres csillagjelek közé:

```markdown
This text is *italic*.
```

A ***félkövérként és dőltként*** is formázandó szöveget zárja háromszoros csillagjelek közé:

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a>Idézetblokkok

Az idézetblokkok létrehozására a `>` karakter használatos:

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

Az előző példa a következőképpen jelenik meg:

> Ekkorra már tízmillió éve aszályos volt az időjárás, és a rettentő gyíkok uralma már rég véget ért. Itt az egyenlítőnél, a később Afrika néven ismert kontinensen példátlan hevességű lett a létért folyó harc, a győztes pedig még fel sem tűnt a láthatáron. Ezen a sivár és kiszikkadt vidéken csak az apró, a gyors és a harcias tudott életben maradni, vagy akár csak reménykedni is benne.

### <a name="lists"></a>Listák

#### <a name="unordered-list"></a>Rendezetlen listák

Rendezetlen vagy listajeles listákat csillagokkal vagy kötőjelekkel formázhat. Például a következő Markdown-szöveg:

```markdown
- List item 1
- List item 2
- List item 3
```

az alábbi módon jelenik meg:

- 1. listaelem
- 2. listaelem
- 3. listaelem

Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait. Például a következő Markdown-szöveg:

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

az alábbi módon jelenik meg:

- 1. listaelem
  - A listaelem
  - B listaelem
- 2. listaelem

#### <a name="ordered-list"></a>Rendezett lista

Rendezett vagy lépéseket ismertető listákat a megfelelő számok használatával formázhat. Például a következő Markdown-szöveg:

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

az alábbi módon jelenik meg:

1. Első utasítás
2. Második utasítás
3. Harmadik utasítás

Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait. Például a következő Markdown-szöveg:

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

az alábbi módon jelenik meg:

1. Első utasítás
   1. Alutasítás
   2. Alutasítás
2. Második utasítás

Felhívjuk figyelmét, hogy minden bejegyzésnél az „1.” jelölést használjuk. Ez megkönnyíti az eltérések ellenőrzését, ha a későbbi frissítésekbe új lépések kerülnek, vagy törlünk a lépések közül.

### <a name="tables"></a>Táblázatok

A táblázatok nem szerepelnek a Markdown alapspecifikációjában, de a GFM-ben támogatottak. Táblázatokat a függőleges vonal (|) és a kötőjel (-) karakterekkel hozhat létre. A kötőjelekkel hozhatja létre az egyes oszlopok fejléceit, a függőleges vonalakkal pedig az oszlopokat választja el egymástól. A táblázat elé szúrjon be egy üres sort, hogy az megfelelően jelenjen meg.

Például a következő Markdown-szöveg:

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

az alábbi módon jelenik meg:

| Így                  | Néznek ki a                 | Táblázatok          |
| :------------------- | -------------------: |:---------------:|
| balra igazított oszlop  | jobbra igazított oszlop | középre igazított oszlop |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |

További információ a táblázatok létrehozásáról:

- Az [Információk rendszerezése táblázatokkal](https://help.github.com/articles/organizing-information-with-tables/) című GitHub-cikk.
- A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás.
- [Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet).
- [Michel Fortin: Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).
- [HTML-táblázatok konvertálása Markdown-formátumra](https://jmalarcon.github.io/markdowntables/).

### <a name="links"></a>Hivatkozások

A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:

 `[link text](file-name.md)`

További információ a hivatkozások használatáról:

- A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.
- A Markdig által biztosított hivatkozási szintaxisról a jelen útmutató [Hivatkozások](how-to-write-links.md) című oldalán található részletesebb információ.

### <a name="code-snippets"></a>Kódrészletek

A Markdown támogatja a kódrészletek mondaton belüli, illetve mondatok közötti, „elkülönített” blokkban való elhelyezését is. További részletek:

- [A Markdown natív kódrészlet-támogatása](https://daringfireball.net/projects/markdown/syntax#precode)
- [GFM-támogatás kód elkülönítéséhez és szintaxiskiemeléshez](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Az elkülönített kódblokkokban egyszerűen kiemelhető a kódrészletek szintaxisa. Az elkülönített kódblokkok általános formátuma a következő:

    ```alias
    ...
    your code goes in here
    ...
    ```

A három kezdő „`” karakter utáni alias határozza meg a használni kívánt szintaxiskiemelést. Az alábbi lista felsorolja a Docs-tartalmakban gyakran használt programozási nyelveket és a hozzájuk tartozó címkét:

Ezekhez a nyelvekhez a rendszer támogatja a névformázást, és legtöbbjük esetében szintaxiskiemelést is nyújt.

|Név|Markdown-címke|
|-----|-------|
|.NET-konzol|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|azcopy|
|Azure CLI|azurecli|
|Azure PowerShell|azurepowershell|
|Bash|bash|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|C# böngészőben|csharp-interactive|
|Konzol|console|
|CSHTML|cshtml|
|DAX|dax|
|Docker|dockerfile|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Kusto lekérdezőnyelv|kusto|
|Markdown|md|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|PowerApps (pont a tizedes elválasztó)|powerapps-dot|
|PowerApps (vessző a tizedes elválasztó)|powerapps-comma|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|R|r|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|XAML|xaml|
|XML|xml|

A `csharp-interactive` név a C# nyelvre utal, valamint arra, hogy a böngészőből futtathatók a minták. A kódrészletek lefordítása és végrehajtása egy Docker-tárolóban történik, és ennek a programvégrehajtásnak az eredménye jelenik meg a felhasználó böngészőablakában.

#### <a name="example-c"></a>Példa: C\#

__Markdown__

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

__Megjelenítés__

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

#### <a name="example-sql"></a>Példa: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Megjelenítés__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a>Egyedi OPS Markdown-bővítmények

> [!NOTE]
> Az Open Publishing Services (OPS) a Markdig Parser Markdownt implementálja, amely nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM). A Markdig néhány funkciót biztosít a Markdown-bővítmények révén. A jelen útmutatóban az OPS teljes szerzői útmutatójának kiválasztott témakörei szerepelnek referenciaként. (Például lásd a „Markdig- és Markdown-bővítmények” és a „Kódrészletek” címeket a tartalomjegyzékben.)

A Docs-cikkek formázásának nagy része, például a bekezdések, a hivatkozások, a listák és a fejlécek a GFM használatával készülnek. A kifinomultabb formázáshoz a cikkekben többek között az alábbi Markdig-funkciók használhatók:

- Megjegyzésblokkok
- Beágyazott fájlok
- Választómezők
- Beágyazott videók
- Kódrészletek és -minták

A teljes listát a tartalomjegyzék „Markdig- és Markdown-bővítmények” és „Kódrészletek” fejezetcíme alatt találhatja.

### <a name="note-blocks"></a>Megjegyzésblokkok

A megjegyzésblokkok 4 típusa közül választhat, hogy felhívja a figyelmet adott tartalomra:

- MEGJEGYZÉS
- FIGYELMEZTETÉS
- TIPP
- FONTOS

Általánosságban elmondható, hogy a megjegyzésblokkokat ritkán szabad használni, mert megtörhetik a cikk folytonosságát. Bár a kódblokkok, képek, listák és hivatkozások használata a megjegyzésblokkokon belül is támogatott, törekedjen egyszerű és könnyen érthető megjegyzésblokkok írására.

Példák:

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

Ez a következőképpen jelenik meg:

> [!NOTE]
> Ez egy MEGJEGYZÉS

> [!WARNING]
> Ez egy FIGYELMEZTETÉS

> [!TIP]
> Ez egy TIPP

> [!IMPORTANT]
> Ez FONTOS

### <a name="include-files"></a>Beágyazott fájlok

Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a Markdig fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra. Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben. A tartalmak újrafelhasználását háromféle beágyazás segíti:

- Beágyazott: Egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.
- Blokkszintű: Egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.
- Képek: Ez a képek normál beillesztésének megvalósítása a Docsban.

A soron belüli és blokk típusú fájl egy egyszerű Markdown- (.md) fájl. Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat. Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni. A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.

Néhány követelmény és megfontolandó szempont a beágyazott fájlokhoz:

- Bármikor használhat beágyazott fájlt, amikor ugyanazt a szöveget több cikkben is szeretné használni.
- A blokk típusú beágyazási hivatkozás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott. Ne használja egy mondatnál kisebb terjedelmű szöveghez.
- A beágyazott hivatkozások a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok Markdig-bővítményeket igényelnek. Azok csak közzététel után jelennek meg.
- Ügyeljen rá, hogy a beágyazott fájl teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó fájlnak a beágyazást megelőző vagy azt követő szövegétől. Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan sztring jön létre a cikkben, amely megtöri a honosított felületet.
- Ne alkalmazzon beágyazási hivatkozást más beágyazott fájlokon belül. Ez nem támogatott.
- A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa. A médiamappa gyökere nem tartalmazhat képfájlokat. Ha a beágyazott fájl nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.
- A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között. Minden egyes beágyazási fájlhoz és cikkhez használjon külön fájlt, egyedi névvel. A médiafájlt tárolja a beágyazott fájlhoz társított médiamappában.
- A cikkek ne tartalmazzanak kizárólag beágyazott fájlt.  A beágyazott fájlok a cikk többi része tartalmának kiegészítésére szolgálnak.

Példa:

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a>Választómezők

Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg az eltérő technológiák és platformok különbségeinek figyelembevételével. Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb. A Markdigben jelenleg kétféle választómező van, az egyszerű és a többszintű.

Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni. Később erre a beágyazott fájlra hivatkozhat az összes olyan témakörben, amely ugyanazt a választómezőt használja.

Ezen a példán egy választómező látható.

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

Az [Azure dokumentációjában](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic) láthatja a választómezők működését.

### <a name="code-include-references"></a>Kódbeágyazási hivatkozások

A Markdig a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja. A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:

- Központosított kódminták vagy -részletek beágyazása külső tárházból.
- Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.

## <a name="gotchas-and-troubleshooting"></a>Tipikus hibák és hibaelhárítás

### <a name="alt-text"></a>Helyettesítő szöveg

Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen. Például a következő szöveg helyett:

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Az aláhúzás jeleket így jelenítheti meg:

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Aposztrófok és idézőjelek

Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat. Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni, különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s

Ezen írásjelek „intelligens” verzióinak kódolásai a következők:

- Bal oldali (nyitó) idézőjel: `&#8220;`
- Jobb oldali (záró) idézőjel: `&#8221;`
- Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`
- Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`

### <a name="angle-brackets"></a>Csúcsos zárójelek

Helyőrzők jelölésére általában csúcsos zárójeleket alkalmazunk. Ha ezt szövegben használja (és nem kódban), a csúcsos zárójelet kódolnia kell. Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.

A `<script name>` kódolása például a következő: `&lt;script name&gt;`

## <a name="markdown-flavor"></a>Markdown-változat

A docs.microsoft.com webhely háttérrendszere Open Publishing Services (OPS) szolgáltatást használ, mely támogatja a [Markdig](https://github.com/lunet-io/markdig) elemzési motoron keresztül értelmezett [CommonMark](https://commonmark.org/)-kompatibilis jelölőnyelvet. Ez a jelölőnyelv-változat nagyrészt kompatibilis a [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) jelölőnyelvvel, mivel a legtöbb dokumentum a GitHubon van tárolva, és ott szerkeszthető. Ez néhány Markdown-bővítményeken keresztül hozzáadott funkcióval egészül ki.

## <a name="see-also"></a>Lásd még:

### <a name="markdown-resources"></a>Markdown-források

- [Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)
- [Markdown-segédlet a Docshoz](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)
- [Markdown-útmutató](https://www.markdownguide.org/)
