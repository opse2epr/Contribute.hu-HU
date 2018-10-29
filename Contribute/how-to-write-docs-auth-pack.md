---
title: A Visual Studio Code-dal használható közreműködői csomag a Docs webhelyhez
description: Ez a cikk a Visual Studio Code-dal használható bővítménycsomagot ismerteti, amely a docs.microsoft.com webhely Markdown formázású tartalmainak szerkesztéséhez használható.
author: meganbradley
ms.author: mbradley
ms.date: 10/22/2018
ms.openlocfilehash: 00afafbbf16096ac6433c0ab276578d8d9084b51
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805654"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs-közreműködői csomag a VS Code alkalmazáshoz

A Docs-közreműködői csomag a Visual Studio Code-bővítmények egy olyan készlete, amely segítséget nyújt a docs.microsoft.com webhely Markdown formázású tartalmainak szerkesztéséhez. A csomagot a [VS Code piacteréről](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) töltheti le, és a következő bővítményeket tartalmazza:

- [markdownlint:](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) Egy népszerű Markdown-linter David Ansontól, mely figyelmezteti, ha a Markdown-kódja eltér az ajánlott eljárásoktól.
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): Egy teljes mértékben offline helyesírás-ellenőrző a Street Side Software-től.
- [Docs Preview](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): A docs.microsoft.com CSS használatával precízebben lehet megnézni a Markdown előnézetét, beleértve az egyéni Markdown-jelöléseket is.
- [Docs Markdown:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) Markdown-írási segítséget nyújt az Open Publishing System- (OPS-) alapú docs.microsoft.com-tartalmakhoz, ideértve a Markdown alapfunkcióinak támogatását, illetve az OPS egyedi Markdown-szintaxisának támogatását is. A jelen témakör további része a Docs Markdown bővítményt ismerteti.
- [Cikksablonok a Docshoz](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): Használatával Markdown-sablon alkalmazható az új fájlokra.

## <a name="prerequisites-and-assumptions"></a>Előfeltételek és feltételezések

A relatív hivatkozások, képek és más beágyazott tartalmak Docs Markdown bővítménnyel való precíz beillesztéséhez a VS Code alkalmazásbeli munkaterületét a klónozott Open Publishing System (OPS) tárház gyökerére kell beállítania.

A bővítmény által támogatott szintaxis bizonyos részei (például a figyelmeztetések és kódrészletek) OPS-alapú egyedi Markdown-kiterjesztések, melyek nem fognak megfelelően megjelenni a tartalomban, ha nem OPS-en keresztül teszi őket közzé.

## <a name="how-to-use-the-docs-markdown-extension"></a>A Docs Markdown bővítmény használata

A Docs Markdown menüjének eléréséhez nyomja le az `ALT+M` billentyűkombinációt. A menüben kattinthat vagy használhatja a fel/le nyílbillentyűket a kívánt funkció kijelöléséhez, vagy beírhatja a keresett funkció nevét a szűréshez. Ha kijelölte a kívánt funkciót a menüben, az `ENTER` billentyű lenyomásával hajthatja végre. Az alábbi funkciók érhetők el:

|Funkció     |Leírás           |
|-------------|----------------------|
|Preview      |Megjeleníti az aktuális témakör formázott előnézetét a Docs Preview bővítmény segítségével a tartalom mellett megjelenő ablakban. Ez a funkció csak akkor érhető el, ha telepítve van a Docs Preview.|
|Félkövér         |**Félkövér** formázást alkalmaz a szövegre.|
|Italic       |*Dőlt* formázást alkalmaz a szövegre.|
|Code         |Ha egy sornyi vagy annál rövidebb szöveg van kijelölve, `inline code` formázást alkalmaz a szövegre.<br><br>Ha több sornyi szöveg van kijelölve, különválasztott kódblokként formázza azt, és lehetővé teszi az OPS által támogatott programnyelvek egyikének megadását.|
|Alert        |Beszúr egy Megjegyzés, Fontos, Figyelmeztetés vagy Tipp típusú blokkot.<br><br>Válassza a menüben az Alert parancsot, majd válassza ki a tartalom kívánt típusát. Ha a parancs végrehajtásakor jelölt ki szöveget, akkor a program a kijelölt szöveg köré szúrja be a választott szintaxist. Ha nincs szöveg kijelölve, akkor egy új, helyőrző szöveget tartalmazó tartalomblokkot szúr be a program.|
|Numbered list|Számozott listát szúr be a szövegbe.<br><br> Ha több sor van kijelölve, minden egyes sorból listaelem lesz. Hasznos tudnia, hogy a Markdown formázású szövegben az összes listaelemnél „1” fog szerepelni, de a docs.microsoft.com webhelyen már növekvő számok lesznek láthatók (vagy betűk, beágyazott listák esetében). Beágyazott számozott lista létrehozásához helyezzen el tabulátorkaraktereket a szülőlistán belül.|
|Bulleted list|Listajeles listát szúr be a szövegbe.|
|Table        |Markdown formázású táblázatstruktúrát szúr be a szövegbe.<br><br>A Table parancs választása után adja meg az oszlopok és a sorok számát oszlop:sor formátumban, például „3:4”. Vegye figyelembe, hogy legfeljebb 5 oszlopot tud beállítani ezzel a bővítménnyel, és ennél több oszlop használata nem is javasolt, mert rontaná az olvashatóságot.|
|Hivatkozás tárházbeli fájlra|Az aktuális tárházban lévő másik fájlra mutató relatív hivatkozás beszúrása. E lehetőség választása után a parancsablakba gépelve szűrhet a fájlnévre, majd kiválaszthatja a kívánt fájlt. Ha korábban kiválasztott szöveget, akkor az lesz a hivatkozás szövege. Más esetben a célfájl H1 címsorának szövege lesz a hivatkozás szövege.|
|Hivatkozás webhelyre    |Webhelyre mutató hivatkozást szúr be. Ennek a lehetőségnek a kiválasztása után illessze be vagy írja be az URI-t a parancsablakba. A `https://` használata kötelező. Ha korábban kiválasztott szöveget, akkor az lesz a hivatkozás szövege. Más esetben az URI lesz használva a hivatkozás szövegeként.|
|Hivatkozás címsorra     |Hivatkozást szúr be az aktuális fájl vagy a tárház egy másik fájljában lévő könyvjelzőre.<br>`Bookmark in this file`: Választhat egyet az aktuális fájl címsorai közül, és a bővítmény beszúrja azt megfelelően formázott könyvjelzőként.<br>`Bookmark in another file`: Először szűrjön a fájlnévre, és válassza ki a hivatkozni kívánt fájlt, majd válasszon egyet az adott fájlon belüli címsorok közül.|
|Image        |Gépelje be a helyettesítő szöveget (akadálymentességi okokból szükséges), jelölje azt ki, futtassa ezt a parancsot a tárházban lévő támogatott képfájlok listázásához, szűrje a listát, majd válassza ki a kívánt képfájlt. Ha a parancs végrehajtásakor nincs helyettesítő szöveg kijelölve, akkor a program kérni fogja a helyettesítő szöveg megadását, mielőtt képfájlt választhatna.|
|Include      |Megkereshet és beágyazhat egy fájlt az aktuális fájlba.|
|Snippet      |Megkeresheti a tárház egyik kódrészletét, és beágyazhatja azt az aktuális fájlba.|
|Videó        |Hozzáad egy beágyazott videót a szöveghez.|
|Sablon     |Egy új fájlt hozhat létre, és alkalmazhat egy Markdown-sablont. További információt az alább található [Sablonok](#how-to-use-docs-templates) szakaszban talál.|

## <a name="how-to-assign-keyboard-shortcuts"></a>Billentyűparancsok társítása

1. Nyomja le a `CTRL+K`, majd a `CTRL+S` billentyűkombinációt a Keyboard Shortcuts (Billentyűparancsok) lista megjelenítéséhez.
1. Keresse meg azt a parancsot, például `formatBold`, amelyhez egyéni billentyűparancsot kíván létrehozni.
1. Kattintson a pluszjelre, amely a parancs neve mellett jelenik meg, amikor az egérmutatót a sor fölé viszi.
1. Miután megjelent az új beviteli mező, írja be az adott parancshoz társítani kívánt billentyűparancsot. Például a félkövér formázás megszokott billentyűparancsának használatához írja be a következőt: `ctrl+b`.
1. Javasolt `when` záradékot beilleszteni a billentyűparancs-társításába, hogy az csak a Markdown-fájlokban legyen elérhető. Ehhez nyissa meg a *keybindings.json* fájlt, és szúrja be az alábbi sort a parancs neve alá (fontos, hogy tegyen egy vesszőt a megelőző sor végére):
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    A kész billentyűparancs-társításnak az alábbihoz hasonlóan kell kinéznie a keybindings.json fájlban:

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. Mentse a keybindings.json fájlt.

További információt a VS Code dokumentációjának [Keybindings](https://code.visualstudio.com/docs/getstarted/keybindings) című témakörében találhat.

## <a name="how-to-show-the-legacy-toolbar"></a>A régi eszköztár megjelenítése

A bővítmény előzetes kiadású verzióját ismerő felhasználók észrevehetik, hogy a szerzői eszköztár nem jelenik meg többé a VS Code ablakának alján a Docs Markdown bővítmény telepítésekor. Ennek az oka az, hogy az eszköztár túl sok helyet foglalt el a VS Code állapotsávján, és nem követte a bővítmények felhasználói élményre vonatkozó ajánlásait, ezért az új bővítményben ezt a funkciót kivontuk a használatból. De ha szeretné, továbbra is megjelenítheti ezt az eszköztárat úgy, hogy frissíti a VS Code alkalmazás settings.json fájlját a következő módon:

1. A VS Code alkalmazásban válassza a Fájl -> Beállítások -> Beállítások (`CTRL+Comma`) lehetőséget.
1. Válassza a „Felhasználói beállítások” lehetőséget az összes VS Code-munkaterület beállításainak módosításához, vagy a „Munkaterület-beállítások” lehetőséget, ha csak az aktuális munkaterület beállításait szeretné módosítani.
1. Az „Alapértelmezett beállítások” panelen keresse meg a „Docs Authoring Extension Configuration” nevű szakaszt, és válassza a ceruzaikont a megfelelő beállítás mellett. A program kérni fogja, hogy adja meg a `true` vagy a `false` beállítást. Ezután a VS Code automatikusan hozzáadja az új értéket a settings.json fájlhoz, majd felkéri Önt az ablak újratöltésére a módosítások érvénybe léptetéséhez.

## <a name="how-to-use-docs-templates"></a>Docs-sablonok használata

A Docs Article Templates (Docs-cikksablonok) bővítmény használatával a VS Code-ot használó szerzők egy központi tárból kérhetnek le egy Markdown-sablont, és azt a fájlra alkalmazhatják. A sablonokkal egyszerűbben biztosítható sok más mellet például az, hogy a szükséges metaadatok szerepeljenek a cikkben, vagy hogy a tartalmi követelményeknek eleget tegyünk. A sablonok Markdown-fájlként vannak tárolva és kezelve egy nyilvános GitHub-tárházban.

### <a name="to-apply-a-template-in-vs-code"></a>Sablon alkalmazása a VS Code-ban

1. Ha még nincs telepítve a Docs Markdown bővítmény, nyomja le az F1 billentyűt a parancspaletta megnyitásához, és kezdje el beírni a „template” (sablon) szót a szűréshez, majd kattintson a `Docs: Template` elemre. Ha már telepítve van a Docs Markdown bővítmény, használhatja a parancspalettát is, vagy az `Alt+M` billentyűkkel megjelenítheti a Docs Markdown QuickPick menüjét, majd válassza a listából a `Template` elemet.
1. A megjelenő listából válassza ki a kívánt sablont.

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>A GitHub-azonosító és/vagy a Microsoft-alias hozzáadása a VS Code-beállításokhoz

A Templates bővítmény a következő három dinamikus metaadat-mezőt támogatja: author, ms.author és ms.date. Ez azt jelenti, hogy ha egy sablon létrehozója használja ezeket a mezőket Markdown-sablon metaadat-fejlécében, akkor a sablon alkalmazásakor ezek automatikusan ki lesznek töltve a fájlban az alábbiak szerint:

|Metaadatok  |Érték|
|----------|---------------|
|author    |Az Ön GitHub-azonosítója, ha meg van adva a VS Code-beállítások fájljában.|
|ms.author |Az Ön Microsoft-aliasa, ha meg van adva a VS Code-beállítások fájljában. Ha Ön nem Microsoft-alkalmazott, akkor hagyja ezt üresen.|
|ms.date   |Az aktuális dátum a Docs által támogatott formátumban: HH/NN/ÉÉÉÉ. Vegye figyelembe, hogy a későbbi fájlmódosításoknál a dátum nem frissül automatikusan. Az ms.date értékét ezért manuálisan kell frissítenie, hogy jelezni tudja a docs.microsoft.com webhelyen a fájl utolsó módosításának dátumát.|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>Az author (GitHub-azonosító) és/vagy az ms.author (Microsoft-alias) beállítása

1. A VS Code alkalmazásban válassza a Fájl -> Beállítások -> Beállítások (`CTRL+Comma`) lehetőséget.
1. Válassza a „Felhasználói beállítások” lehetőséget az összes VS Code-munkaterület beállításainak módosításához, vagy a „Munkaterület-beállítások” lehetőséget, ha csak az aktuális munkaterület beállításait szeretné módosítani.
1. A bal oldali Alapértelmezett beállítások panelen keresse meg a Docs Article Templates bővítmény konfigurációját, kattintson a kívánt beállítás melletti ceruza ikonra, majd a Beállításokban kattintson a Csere lehetőségre.
1. A Felhasználói beállítások oldal mellette jelenik majd meg, az alján egy új tétellel.
1. Adja hozzá a GitHub-azonosítóját vagy a Microsoft-aliasát, és mentse a fájlt.
1. Előfordulhat, hogy a módosítások életbe lépése érdekében be kell zárnia, majd újra el kell indítania a VS Code-ot.
1. Ha most dinamikus mezőket használó sablont alkalmaz, a metaadatok fejléc automatikusan ki lesz töltve a GitHub-azonosítójával vagy a Microsoft-aliasával.
