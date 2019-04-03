---
title: A közreműködés folyamata .NET-dokumentumtárakban
description: Ez a cikk a .NET-dokumentumtárakban végzett közreműködést mutatja be tömören. Megismerheti az ehhez használt adattárakat, a tartalom szervezésnek folyamatát, és a kódminták és más objektumok kezelésére vonatkozó szabályzatokat.
ms.date: 11/07/2018
ms.openlocfilehash: 121f6c885ef6d292968e5bb3961cae8e9c22942b
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637506"
---
# <a name="process-for-contributing-to-net-docs"></a>A .NET-dokumentumokban való közreműködés folyamata

Szívesen fogadjuk a dokumentumokban való közösségi közreműködést. Az alábbi lista néhány olyan irányelvet sorol fel, amelyeket érdemes szem előtt tartani a .NET-dokumentációban való közreműködés során:

- **NE** lepjen meg minket nagy lekéréses kérelmekkel. Inkább vesse fel a témát, és kezdeményezzen párbeszédet, hogy megegyezhessünk egy irányvonalban, mielőtt sok időt áldozna rá.
- **TARTSA BE** ezeket az utasításokat, és a [stílusra és hangvételre](dotnet-voice-tone.md) vonatkozó irányelveket.
- **HASZNÁLJA** a [sablon](dotnet-style-guide.md) fájlt munkája kiindulási pontjaként.
- **HOZZON LÉTRE** külön ágat saját elágazásán belül, mielőtt dolgozni kezd a cikkeken.
- **KÖVESSE** a [GitHub Flow munkafolyamatot](https://guides.github.com/introduction/flow/).
- **ÍRJON** rendszeresen blogbejegyzést, tweetet, vagy bármi hasonlót közreműködéseiről.

Ezeknek az irányelveknek a betartása Önnek és nekünk is jobb élményt biztosít.

## <a name="make-a-contribution-to-net-docs"></a>Közreműködés készítése .NET-dokumentációhoz

**1 lépés:** Kisebb módosítások esetén hagyja ki ezt a lépést. Ha új tartalom megírása vagy meglévő tartalom alapos átdolgozása iránt érdeklődik, nyisson új [témát](https://github.com/dotnet/docs/issues), és írja le, hogy mit szeretne tenni.

A **docs** mappa tartalma a Tartalomjegyzék (TOC) által tükrözött szakaszokba van rendszerezve. Adja meg, hogy hol helyezkedik majd el a témakör a tartalomjegyzékben. Ajánlatáról visszajelzést kap.

-vagy-

Választhat a meglévő témák közül, amelyekhez szívesen fogadjuk a közösségi közreműködést. A [Projektek a .NET-közösség közreműködői számára](https://github.com/dotnet/docs/projects/35) számos olyan témát sorol fel, amelyeket a közösségi közreműködők elérhetnek. Érdeklődésétől és elkötelezettségétől függően az alábbi kategóriákba tartozó témák közül választhat:

- **Karbantartás**. Ebbe a kategóriába viszonylag egyszerű közreműködések tartoznak, amilyen egy érvénytelen vagy hibás hivatkozás kijavítása, hiányzó kódminták hozzáadása, vagy korlátozott tartalmi ügyek intézése. Ezek a témák esetenként sok fájlt érinthetnek. Ilyen esetben ajánlott tudatnia velünk, hogy mivel szeretne dolgozni, mielőtt hozzákezd. Fűzzön megjegyzést a témához, amelyben tudatja velünk, hogy azon dolgozik.

- **Tartalomfrissítések**. A dokumentumhalmaz hatalmas mérete miatt a tartalom könnyen elévülhet, és felülvizsgálatot igényel. Ezen kívül a tartalom egy része különféle okokból két vagy három példányban is létezhet. A tartalomfrissítés része az egyes témakörök naprakészségének ellenőrzése, az egy funkcióhoz tartozó tartalom felülvizsgálata a duplikáció kiküszöbölése érdekében, és annak biztosítása, hogy az egyedi tartalom meg lesz őrizve a kisebb dokumentumkészletben.

- **Új tartalom készítése**. Ha saját témakört szeretne írni, ezek a témák felsorolják azokat a témaköröket, amelyeket szívesen hozzáadnánk dokumentumkészletünkhöz. Mindenesetre értesítsen minket, mielőtt munkához lát egy témakörben. Ha itt fel nem tüntetett témakört szeretne írni, nyisson új témát.

Megtekintheti a [nyitott témák](https://github.com/dotnet/docs/issues) listáját is, és jelentkezhet egy olyanra, amely felkelti érdeklődését. A közösségi közreműködésre kijelölt témákat az [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) (elvihető) címkével jelöljük. Ezek általában minimális környezetet igényelnek, és kitűnően alkalmasak első témának. A közösség gyakorlott közreműködőit arra biztatjuk, hogy keressék az érdeklődésüknek megfelelő témákat. Ha ilyet talál, megjegyzésben kérdezze meg, hogy a téma nyitott-e.

Miután kiválasztotta a feladatot, amelyen dolgozni kíván, az [első lépések](get-started-setup-github.md) útmutatót követve hozzon létre egy GitHub-fiókot, és alakítsa ki saját környezetét.

**2 lépés:** Szükségleteinek megfelelően ágaztassa el a `/dotnet/docs`, `dotnet/samples`, `dotnet/dotnet-api-docs`, `dotnet/roslyn-api-docs` vagy `dotnet/ml-api-docs` adattárat, és hozzon létre ágat saját módosításaihoz.

Kisebb módosítások esetén igazodjon a GitHubon végzett szerkesztésre vonatkozó útmutatáshoz, amely a közreműködői útmutató [kezdőlapján](index.md#quick-edits-to-existing-documents) található.

**3 lépés:** Végezze el a módosításokat ebben az új ágban.

Ha a témakör új, akkor kiindulásként használhatja ezt a [sablon](dotnet-style-guide.md) fájlt. Ez tartalmazza az írásra vonatkozó irányelveket, és ismerteti az egyes cikkekhez szükséges olyan metaadatokat, mint a szerző adatai.

Lépjen a cikkéhez az 1. lépésben meghatározott tartalomjegyzékbeli helynek megfelelő mappába. Ez a mappa tartalmazza a szakasz összes cikkéhez tartozó Markdown-fájlokat. Szükség esetén hozzon létre új mappát a tartalomhoz tartozó fájlok elhelyezéséhez. A szakasz fő cikkének neve *index.md*. Ha még nem létezik, a képek és más statikus források számára hozzon létre egy **media** nevű almappát a cikkét tartalmazó mappában. A **media** mappában hozzon létre almappát a cikk nevével (kivéve az indexfájlt). A kódmintának a `dotnet/samples` adattárban kell lennie, a [minták](#contributing-to-samples) szakaszban leírtak szerint.

Mindenképpen kövesse a helyes Markdown-szintaxist. Gyakori példákat talál a [Sablon- és Markdown-segédlet](dotnet-style-guide.md) című cikkben.

## <a name="example-structure"></a>Példastruktúra

    docs
      /about
      /core
        /porting
          porting-overview.md
          /media
            /porting-overview
                portability_report.png

**4 lépés:** Küldjön lekéréses kérelmet (PR-t) saját ágából a főágba.

> [!IMPORTANT]
> Az [automatizált megjegyzések](how-to-write-workflows-major.md#review-and-sign-off) funkció jelenleg nem érhető el a .NET-dokumentumtárak egyikében sem. Lekéréses kérelmét a .NET-dokumentáció csapata fogja elbírálni és egyesíteni.

Általában minden lekéréses kérelemnek egyszerre egy témával kell foglalkoznia. A lekéréses kérelem egy vagy több fájlt is módosíthat. Ha több javítással foglalkozik különböző fájlokban, akkor előnyösebb külön lekéréses kérelmeket küldeni. Ha a Markdown frissítése mellett mintákat is létrehoz, akkor a mintákhoz külön lekéréses kérelmet kell létrehoznia.

Ha lekéréses kérelme meglévő problémát javít, a véglegesítési üzenethez vagy a lekéréses kérelem leírásához fűzze hozzá a `Fixes #Issue_Number` kulcsszót. A téma így automatikusan le lesz zárva a lekéréses kérelem egyesítésekor. További információ: [Témák lezárása véglegesítési üzenetekkel](https://help.github.com/articles/closing-issues-via-commit-messages/).

A .NET-csapat elbírálja lekéréses kérelmét, és értesíti önt, ha a jóváhagyásához további frissítésre/módosításra van szükség.

**5 lépés:** Végezzen el minden szükséges frissítést az ágában, a csapattal egyeztetett módon.

A karbantartók akkor egyesítik lekéréses kérelmét a főágba, ha a visszajelzés alkalmazva lett, és a módosítását jóváhagyták.

A véglegesítéseket rendszeresen leküldjük a főágból az élő ágba, és közreműködése ekkor élőben jelenik meg a https://docs.microsoft.com/dotnet/ oldalon. A közzétételt munkanapokon általában naponta hajtjuk végre. Karbantartási tevékenységek néhány nappal késleltethetik a közzétételt.

## <a name="contributing-to-samples"></a>Közreműködés mintákhoz

A [dotnet/samples](https://github.com/dotnet/samples) adattár az összes kódmintát tartalmazza, amely része a .NET-dokumentáció valamely témakörének. Néhány projekt almappákba van rendezve. Ezek az almappák a .NET-dokumentumokhoz hasonlóan vannak szervezve.

Az adattárunkban meglévő kódokat az alábbiak szerint különböztetjük meg:

- Minták: az olvasók letölthetik és futtathatják a mintákat. Minden mintának teljes alkalmazásnak vagy kódtárnak kell lennie. Ha a minta kódtárat hoz létre, annak egységteszteket, vagy olyan alkalmazást is magában kell foglalnia, amellyel az olvasók futtatni tudják a kódot. Gyakran több technológiát, funkciót vagy eszközkészletet is felhasználnak. Az egyes mintákhoz tartozó readme.md fájl hivatkozik a cikkre, így tovább tájékozódhat a minták által bemutatott fogalmakról.
- Kódrészletek: kisebb fogalmat vagy feladatot mutatnak be. Lefordíthatók, de nem teljes alkalmazásnak szánjuk őket. Helyesen kell futniuk, de nem egy jellemző helyzetre példát mutató alkalmazások. A tervezésük szempontja inkább az, hogy minél kisebb méretben mutassanak be egy fogalmat vagy funkciót. A kódnak el kell férnie egy képernyőn.

A teljes kód a [dotnet/samples](https://github.com/dotnet/samples) adattárban helyezkedik el. Dolgozunk egy olyan modellen, amelyben a minták mappastruktúrája megfeleltethető a dokumentumok mappastruktúrájával. A követett szabványok a következők:

- A legfelső szintű *snippets* (kódrészletek) mappa kicsi, célratörő minták kódrészleteit tartalmazza.
- Az API-referenciaminták a következő mappaszerkezetben vannak elhelyezve: *Snippets/\<nyelv>/api/\<névtér>/\<api neve>*.
- A többi legfelső szintű mappa a *docs* adattár legfelső szintű mappáival egyezik meg. A docs adattárban például van egy *machine-learning/tutorials* mappa, a gépi tanulási oktatóanyagok pedig a *samples/machine-learning/tutorials* mappában vannak.

Ezen felül a *core* és a *standard* mappák alatti összes mintának lefordíthatónak és futtathatónak kell lennie a .NET Core által támogatott összes platformon. Erről CI build-rendszerünk gondoskodik. A legfelső szintű *framework* (keretrendszer) mappa olyan mintákat tartalmaz, amelyek csak Windows rendszerre készültek, és azon lettek ellenőrizve.

A mintaprojekteknek a platformok adott minta esetén elképzelhető legszélesebb körén lefordíthatóknak és futtathatónak kell lenniük. A gyakorlatban ez .NET Core-alapú konzolalkalmazások készítését jelenti, ha csak lehetséges. A kimondottan webes, vagy egy felhasználói felülethez készült mintáknak a szükséges eszközöket is meg kell adniuk. Ilyenek például a webes alkalmazások, a mobilalkalmazások, a WPF- vagy WinForms-alkalmazások, és sok más.

Dolgozunk azon, hogy minden kódhoz rendelkezésre álljon CI-rendszer. Amikor mintákat frissít, gondoskodjon arról, hogy minden frissítés a lefordítható projekt része legyen. A legjobb, ha a helyes működést ellenőrző teszteket is ad a mintákhoz.

Minden létrehozott teljes mintának tartalmaznia kell egy *readme.md* fájlt. Ennek a fájlnak a minta rövid (egy-két bekezdés terjedelmű) leírását is tartalmaznia kell. Az olvasók a *readme.md* fájlból tudják meg, hogy mit ismerhetnek meg a minta vizsgálatával. A *readme.md* fájlnak egy hivatkozást is tartalmaznia kell a [.NET dokumentációjának webhelyén](https://docs.microsoft.com/dotnet/welcome) lévő élő dokumentumra. Azt, hogy egy adott fájl az adattárban erre a webhelyre lesz leképezve úgy ellenőrizheti, hogy az adattár elérési útjában a `http://docs.microsoft.com/dotnet` címet írja a `/docs` helyére.

A témakörnek a mintára mutató hivatkozásokat is tartalmaznia kell. Hivatkozzon közvetlenül a minták mappájára GitHubon.

### <a name="writing-a-new-snippet-or-sample"></a>Új kódrészlet vagy minta írása

1. A mintának egy **lefordítható projekt részének kell lennie**. Ha csak lehetséges, a projektek legyenek a .NET Core által támogatott összes platformon lefordíthatók. Ez alól csak a platformspecifikus funkciót vagy platformspecifikus eszközt bemutató minták kivételek.

2. A mintának a konzisztencia fenntartása érdekében meg kell felelnie a [corefx kódolási stílusnak](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md).

    - Példánymetódusok helyett előnyösebb `static` metódusokat használni, ha olyasmit mutat be, ami nem igényli új objektumpéldány létrehozását.

3. A mintának **megfelelő kivételkezelést** is tartalmaznia kell. Ennek minden olyan kivételt kezelnie kell, amely feltehetően előfordul a minta környezetében. A felhasználói adatbevitel bekérésére a [Console.ReadLine](https://docs.microsoft.com/dotnet/api/system.console.readline) metódust hívó mintának például a megfelelő kivételkezelést kell használnia, amikor a bemeneti sztring argumentumként át van adva a metódusnak. Ugyanígy, ha a mintában egy metódus sikertelen hívása várható, a keletkező kivételt is kezelni kell. Mindig a metódus által okozott adott kivételt kell kezelni, és nem az olyan, alaposztályokba tartozó kivételeket, mint az [Exception](https://docs.microsoft.com/dotnet/api/system.exception) vagy a [SystemException](https://docs.microsoft.com/dotnet/api/system.systemexception).

4. Ha a minta önálló csomagot készít, akkor a minta által használt futtatókörnyezeteken kívül a mi CI buildelési rendszerünk futtatókörnyezeteit is tartalmaznia kell:
    - `win7-x64`
    - `win8-x64`
    - `win81-x64`
    - `ubuntu.16.04-x64`

Hamarosan üzembe helyezzük az ilyen projektek fordítását végző CI-rendszert.

Minta létrehozása:

1. Jelentsen be egy [témát](https://github.com/dotnet/docs/issues), vagy fűzzön megjegyzést egy meglévőhöz arról, hogy azzal dolgozik.
2. Írja meg a témakört, amely a minta által bemutatott fogalmakat magyarázza el (például: `docs/standard/linq/where-clause.md`).
3. Írja meg a mintát (például: `WhereClause-Sample1.cs`).
4. Hozzon létre egy Program.cs fájlt, a mintáit meghívó Main belépési ponttal. Ha már van ilyen, akkor szúrja be a mintája hívását:

    ```csharp
    public class Program
    {
        public void Main(string[] args)
        {
            WhereClause1.QuerySyntaxExample();

            // Add the method syntax as an example.
            WhereClause1.MethodSyntaxExample();
        }
    }
    ```

.NET Core-kódrészletet vagy -mintát készít a [.NET Core SDK-val](https://www.microsoft.com/net/download) telepíthető .NET Core CLI használatával. A minta fordítása és futtatása:

1. Lépjen a minták mappájába, és hibakeresés céljából végezzen buildelést:

    ```console
    dotnet build
    ```
2. Futtassa le a kódot:

    ```console
    dotnet run
    ```

3. Adjon hozzá egy readme.md fájlt a minta gyökérmappájához. 

   Ennek tartalmaznia kell a kód tömör leírását, és meg kell adnia a kódra hivatkozó cikket.

Hacsak nincs másként jelezve, az összes mintának lefordíthatónak kell lennie a .NET Core által támogatott összes platformon. Néhány minta kimondottan a Visual Studióhoz készült, és a Visual Studio 2017 vagy újabb verzióját igényli. Néhány példa ezen felül platformspecifikus funkciókat is bemutat, és egy adott platformot igényel. Más minták és kódrészletek a .NET-keretrendszert igénylik, Windows-platformokon futnak, és szükség van hozzájuk a célzott keretrendszer-verzió fejlesztői csomagjára.

## <a name="the-c-interactive-experience"></a>Az interaktív C# felület

A cikkben szereplő összes minta a [nyelvi címkével](how-to-write-use-markdown.md#code-snippets) jelzi a forrásnyelvet. A C# nyelvű rövid kódminták a `csharp-interactive` nyelvi címkével azonosíthatók a böngészőben futó C#-mintákként. (Beágyazott kódmintákhoz a `csharp-interactive`, a forrásból befoglalt kódrészletekhez a `code-csharp-interactive` címke használható.) Ezekhez a kódmintákhoz a cikknek kódablakot és kimenet-ablakot is be kell mutatnia. A kimenet-ablakban annak a kimenetnek kell látszania, amely az interaktív kód végrehajtása után jelenik meg, ha a felhasználó lefuttatta a mintát.

Az interaktív C# felület megváltoztatja a mintákkal végzett munka jellegét. A mintát látogatók futtathatják, hogy tapasztalják az eredményt. Számos tényező segít eldönteni, hogy a minta, vagy az annak megfelelő szöveg tartalmazzon információt a kimenetről.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Mikor érdemes a várható kimenetet a minta futtatása nélkül bemutatni

- A kezdőknek szóló cikkekben érdemes megadni a kimenetet, hogy az olvasók összehasonlíthassák a munkájuk kimenetét az elvárható válasszal.
- Azokhoz a mintákhoz, ahol a kimenet a témakör szerves része, érdemes bemutatni ezt a kimenetet. A formázott szövegről szóló cikkekben például hasznos a szövegformátumot a minta futtatása nélkül is bemutatni.
- Ha a minta és a várható kimenet is rövid, fontolja meg a kimenet megmutatását. Ezzel időt takaríthat meg.
- A kimenetnek az aktuális vagy az invariáns kulturális környezet általi befolyásolásáról szóló cikkekben érdemes magyarázatot fűzni a várható kimenethez. Az interaktív REPL (Read Evaluate Print Loop) Linux-alapú gazdagépen fut. Az alapértelmezett kulturális környezet és az invariáns kulturális környezet különböző operációs rendszereken és számítógépeken más-más kimenetet eredményez. A cikknek a Windows, Linux és Mac rendszeren várható kimenetet is ismertetnie kell.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Mikor érdemes a várható kimenetet kihagyni a mintából

- Olyan cikkek, ahol a minta terjedelmes kimenetet generál, inkább ne tartalmazzák azt a megjegyzésekben. Így a minta lefutása után a kód háttérbe szorulna.
- Vannak cikkek amelyekben a minta egy témakört mutat be, de a kimenet nem nélkülözhetetlen annak megértéséhez. Ilyen például egy LINQ-lekérdezést futtató kód, amely a lekérdezés szintaxisát ismerteti, majd a kimeneti gyűjtemény minden elemét megjeleníti.

> [!NOTE]
> Észrevehette, hogy jelenleg nem minden témakör felel meg az összes itt ismertetett irányelvnek. Folyamatosan dolgozunk az egész webhelyre kiterjedő konzisztencia eléréséért. Megtekintheti azoknak a [nyitott témáknak](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3A%22%3Abookmark_tabs%3A+Information+Architecture%22) a listáját, amelyeket éppen e cél érdekében követünk nyomon.

## <a name="contributor-license-agreement"></a>Közreműködői licencszerződés

Lekéréses kérelme egyesítéséhez alá kell írnia a [.NET Foundation közreműködői licencszerződését (CLA)](https://cla.dotnetfoundation.org). Ez egyszeri követelmény a .NET Foundation projektjeihez. A [Közreműködői licencszerződésről (CLA)](http://en.wikipedia.org/wiki/Contributor_License_Agreement) a Wikipédia szócikke ír bővebben.

A szerződés: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

A szerződést nem kell előre aláírnia. Lekéréses kérelmét a szokásos módon klónozhatja, elágaztathatja és benyújthatja. A leküldéses kérelmet annak létrehozása után egy CLA-robot sorolja be. Ha a módosítás kis mértékű (például egy gépelési hiba javítása), akkor a lekéréses kérelem a `cla-not-required` címkével lesz ellátva. Más esetben a `cla-required` besorolást kapja. A CLA aláírása után jelenlegi és jövőbeli lekéréses kérelmei mindig a `cla-signed` címkével lesznek ellátva.
