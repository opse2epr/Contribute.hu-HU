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
ms.openlocfilehash: 041398361aef90c44bdf3a0dad4aaa2d40a38289
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469946"
---
# <a name="how-to-use-markdown-for-writing-docs"></a>A Markdown használata Docs-tartalmak írásához

A docs.microsoft.com-cikkek a rendkívül egyszerű [Markdown](https://daringfireball.net/projects/markdown/) jelölőnyelv használatával készülnek, amely könnyen olvasható és könnyen elsajátítható. Ez az oka, hogy rövid idő alatt iparági szabvánnyá vált.

Mivel a Docs-tartalmak a GitHubon vannak tárolva, azokhoz használható a Markdown [GitHub-stílusú Markdown (GFM)](https://help.github.com/categories/writing-on-github/) nevű bővítése, amely további funkciókat biztosít a gyakori formázási igényekhez. Ezen kívül az Open Publishing Services (OPS) a Markdig Markdown Parsert implementálja. A Markdig nagy mértékben kompatibilis a GitHub-stílusú Markdownnal (GFM), és további funkciókkal támogatja a Docs specifikus szolgáltatásainak használatát.

* A Markdig egy gyors, hatékony, CommonMark-megfelelőséggel rendelkező, bővíthető Markdown-feldolgozó .NET környezetekhez.
* https://github.com/lunet-io/markdig
* Jobb közösségi támogatás
* Jobb szabványtámogatás

## <a name="markdown-basics"></a>A Markdown alapjai

### <a name="headings"></a>Fejlécek

Fejlécek a kettőskereszt karakterrel (#) hozhatók létre, a következőképpen:

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

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
2. Second instruction
3. Third instruction
```

az alábbi módon jelenik meg:

1. Első utasítás
2. Második utasítás
3. Harmadik utasítás

Listák egymásba ágyazásához behúzással írja le a gyermeklista sorait. Például a következő Markdown-szöveg:

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

az alábbi módon jelenik meg:

1. Első utasítás
    1. Alutasítás
    2. Alutasítás
2. Második utasítás

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

- A Markdig széles táblázatok formázását segítő [táblázatbehatárolási funkcióját](#table-wrapping) ismertető szakasz
- Az [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/) (Információk rendszerezése táblázatokkal) című GitHub-cikk
- A [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) webalkalmazás
- [Adam Pritchard: Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Markdown-segédlet)
- [Michel Fortin: Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table)
- [HTML-táblázatok konvertálása Markdown-formátumra](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a>Hivatkozások

A soron belül elhelyezett hivatkozások Markdown-szintaxisa a hivatkozásként használt szövegét tartalmazó `[link text]` részből, illetve az azt követő `(file-name.md)` részből áll, amely a hivatkozandó URL-cím vagy fájlnév:

 `[link text](file-name.md)`

További információ a hivatkozások használatáról:

- A Markdown alapvető hivatkozástámogatásáról a [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) (Útmutató a Markdown-szintaxishoz) című oldalon található további információ.
- A Markdig által biztosított hivatkozási szintaxisról a jelen útmutató [Links](how-to-write-links.md) (Hivatkozások) című oldalán található részletesebb információ.

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
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|CSHTML|cshtml|
|DAX|dax|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|PowerApps-képlet|powerappsfl|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

#### <a name="example-c"></a>C\#-példa:

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

#### <a name="example-sql"></a>SQL-példa:

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
- Beágyazások
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

### <a name="includes"></a>Beágyazások

Ha újrafelhasználható szöveg- vagy képfájlokat kell „beágyaznia” a cikkek fájljaiba, akkor a Markdig fájlbeágyazási funkciójával hivatkozhat a beágyazandó fájlra. Ez a funkció arra utasítja az OPS-t, hogy az összeállítás során az adott fájlt is foglalja bele a cikkbe, így annak tartalma már szerepelni fog a közzétett cikkben. A tartalmak újrafelhasználását háromféle beágyazás segíti:

- Soron belüli: egy egyszerű szövegrészlet egy másik mondatban való újrafelhasználását teszi lehetővé.
- Blokk: egy teljes Markdown-fájl egy cikk egy szakaszába beágyazva való újrafelhasználását teszi lehetővé.
- Képek: ez a képek normál beillesztésének megvalósítása a Docsban.

A soron belüli és blokk típusú beágyazás egy egyszerű Markdown- (.md) fájlt használ. Ez tetszőleges érvényes Markdown-szintaxist tartalmazhat. Minden beágyazott Markdown-fájlt a tárház gyökerében található [közös `/includes` almappában](git-github-fundamentals.md#includes-subdirectory) kell elhelyezni. A cikk közzétételekor a beágyazott fájl tartalma átmenet nélkül beépül a közzétett témakörbe.

Néhány követelmény és megfontolandó szempont a beágyazásokhoz:

- Bármikor használhat beágyazást, amikor ugyanazt a szöveget több cikkben is szeretné használni.
- A blokk típusú beágyazás használata nagyobb mennyiségű tartalomhoz – egy-két bekezdéshez, egy közös eljáráshoz vagy egy közös szakaszhoz – ajánlott. Ne használja egy mondatnál kisebb terjedelmű szöveghez.
- A beágyazott tartalmak a cikk GitHub által előállított nézetében nem jelennek meg, ugyanis azok Markdig-bővítményeket igényelnek. Azok csak közzététel után jelennek meg.
- Ügyeljen rá, hogy a beágyazott szöveg teljes mondatokból vagy kifejezésekből álljon, amelyek nem függnek a hivatkozást tartalmazó cikknek a beágyazást megelőző vagy azt követő szövegétől. Ezt az ajánlást figyelmen kívül hagyva lefordíthatatlan szövegrészlet jön létre a cikkben, amely megtöri a honosított felületet.
- Ne alkalmazzon beágyazást más beágyazásokon belül. Ez nem támogatott.
- A médiafájlokat a beágyazási almappában megadott médiamappában kell elhelyezni. Ez lehet például a `<repo>`/includes/media mappa. A médiamappa gyökere nem tartalmazhat képfájlokat. Ha a beágyazás nem tartalmaz képeket, akkor a hozzá tartozó médiamappára nincs szükség.
- A hagyományos cikkekhez hasonlóan itt se osszon meg médiát a beágyazott fájlok között. Minden egyes beágyazáshoz és cikkhez használjon külön fájlt, egyedi névvel. A médiafájlt tárolja a beágyazáshoz társított médiamappában.
- A cikkek ne tartalmazzanak kizárólag egy beágyazást.  A beágyazások a cikk többi része tartalmának kiegészítésére szolgálnak.

### <a name="selectors"></a>Választómezők

Technikai cikkekben akkor használjon választómezőket, ha ugyanannak a cikknek többféle változatát írja meg a különböző technológiák és platformok különbségeinek figyelembe vételével. Ez általában a fejlesztőknek szánt, mobilplatformokkal kapcsolatos tartalom esetében a legjellemzőbb. A Markdigben jelenleg kétféle választómező van, az egyszerű és a többszintű.

Mivel a választott témakörök mindegyikébe ugyanaz a választómezőhöz tartozó Markdown kerül, javasolt a választómezőt egy beágyazható fájlban elhelyezni, majd erre hivatkozni az összes olyan témakörben, amely ugyanazt a választómezőt használja.

### <a name="code-snippets"></a>Kódrészletek

A Markdig a kódrészlet-bővítményével programkódok a cikkekben való speciális megjelenítését is támogatja. A speciális megjelenítés a GFM olyan funkciói mellett, mint például a programozási nyelv kiválasztása és a szintaxisszínek használata, többek között a következő további hasznos lehetőségekre épül:

- Központosított kódminták vagy -részletek beágyazása külső tárházból.
- Lapokra osztott felhasználói felület a kódminták különböző verzióinak különböző nyelveken való megjelenítéséhez.

## <a name="gotchas-and-troubleshooting"></a>Tipikus hibák és hibaelhárítás

### <a name="alt-text"></a>Helyettesítő szöveg

Az aláhúzásjeleket tartalmazó helyettesítő szövegek nem jelennek meg helyesen. Például a következő szöveg helyett:

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Az aláhúzás jeleket így jelenítheti meg:

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Aposztrófok és idézőjelek

Ha a Wordből másol a Markdown-szerkesztőbe, akkor a szöveg „intelligens” (íves) aposztrófokat és időzőjeleket tartalmazhat. Ezeket kódolni kell, vagy pedig egyszerű aposztrófokra, illetve idézőjelekre kell cserélni, különben a fájl közzétételekor a következőhöz hasonló eredményt kaphat: Itâ€™s

Ezen írásjelek „intelligens” verzióinak kódolásai a következők:

- Bal oldali (nyitó) idézőjel: `&#8220;`
- Jobb oldali (záró) idézőjel: `&#8221;`
- Jobb oldali (záró) egyszeres idézőjel vagy aposztróf: `&#8217;`
- Bal oldali (nyitó) egyszeres idézőjel vagy aposztróf (ritkán használt): `&#8216;`

### <a name="angle-brackets"></a>Csúcsos zárójelek

Ha csúcsos zárójeleket használ a fájl szövegében (nem a kódban), például egy helyőrző jelölésére, akkor a csúcsos zárójeleket manuálisan kell kódolnia. Ellenkező esetben a Markdown úgy fogja értelmezni, hogy HTML-címkének szánták őket.

A `<script name>` kódolása például a következő: `&lt;script name&gt;`

## <a name="see-also"></a>Lásd még:

### <a name="markdown-resources"></a>Markdown-források

- [Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Bevezetés a Markdown használatába)
- [Markdown-segédlet a Docshoz](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (A GitHub a Markdown alapjait ismertető cikke)
