---
title: Docs-közreműködői csomag a VS Code alkalmazáshoz
description: Ez a cikk ismerteti a VS Code-bővítmény a docs.microsoft.com webhely Markdown formázású tartalmainak szerkesztéséhez.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: d0d61db2faf88598ecd2c800fb5fbe8df8ec44f5
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/22/2018
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs-közreműködői csomag a VS Code alkalmazáshoz

A Docs-közreműködői csomag a VS Code-bővítmények egy olyan készlete, amely segítséget nyújt a docs.microsoft.com webhely Markdown formázású tartalmainak szerkesztéséhez. A csomagot a [VS Code piacteréről](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) töltheti le, és a következő bővítményeket tartalmazza:

- **DocFx:** Megjeleníti a docs.microsoft.com-specifikus Markdown formázású tartalmak előnézetét. További információért lásd: [DocFx](https://marketplace.visualstudio.com/items?itemName=ms-docfx.DocFX).
- **markdownlint:** Egy népszerű Markdown-linter David Ansontól, mely figyelmezteti, ha a Markdown-kódja eltér az ajánlott eljárásoktól. További információért lásd: [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint).
- **Docs Markdown:** Markdown-írási segítséget nyújt az Open Publishing System- (OPS) alapú docs.microsoft.com-tartalmakhoz, ideértve a Markdown alapfunkcióinak támogatását, illetve az OPS egyedi Markdown-szintaxisának támogatását. A jelen témakör további része a Docs Markdown bővítményt ismerteti.

## <a name="prerequisites-and-assumptions"></a>Előfeltételek és feltételezések

A relatív hivatkozások, képek és más beágyazott tartalmak Docs Markdown bővítménnyel való precíz beillesztéséhez a VS Code alkalmazásbeli munkaterületét a klónozott OPS-tárház gyökerére kell beállítania.

A bővítmény által támogatott szintaxis bizonyos részei (például a figyelmeztetések és kódrészletek) OPS-alapú egyedi Markdown-kiterjesztések, melyek nem fognak megfelelően megjelenni a tartalomban, ha nem OPS-en keresztül teszi őket közzé.

## <a name="how-to-use-the-docs-markdown-extension"></a>A Docs Markdown bővítmény használata

A Docs Markdown menüjének eléréséhez nyomja le az `ALT+M` billentyűkombinációt. A menüben kattinthat vagy használhatja a fel/le nyílbillentyűket a kívánt funkció kijelöléséhez, vagy beírhatja a keresett funkció nevét a szűréshez. Ha kijelölte a kívánt funkciót a menüben, az `ENTER` billentyű lenyomásával hajthatja végre. Az alábbi funkciók érhetők el:

|Funkció     |Parancs             |Leírás           |
|-------------|--------------------|----------------------|
|Félkövér         |`formatBold`        |**Félkövér** formázást alkalmaz a szövegre.|
|Italic       |`formatItalic`      |*Dőlt* formázást alkalmaz a szövegre.|
|Code         |`formatCode`        |Ha egy sornyi vagy annál rövidebb szöveg van kijelölve, `inline code` formázást alkalmaz a szövegre.<br><br>Ha több sornyi szöveg van kijelölve, különválasztott kódblokként formázza azt, és lehetővé teszi az OPS által támogatott programnyelvek egyikének megadását.|
|Alert        |`insertAlert`       |Beszúr egy Megjegyzés, Fontos, Figyelmeztetés vagy Tipp típusú blokkot.<br><br>Válassza a menüben az Alert parancsot, majd válassza ki a tartalom kívánt típusát. Ha a parancs végrehajtásakor jelölt ki szöveget, akkor a program a kijelölt szöveg köré szúrja be a választott szintaxist. Ha nincs szöveg kijelölve, akkor egy új, helyőrző szöveget tartalmazó tartalomblokkot szúr be a program.|
|Numbered list|`insertNumberedList` |Számozott listát szúr be a szövegbe.<br><br> Ha több sor van kijelölve, minden egyes sorból listaelem lesz. Hasznos tudnia, hogy a Markdown formázású szövegben az összes listaelemnél „1” fog szerepelni, de a docs.microsoft.com webhelyen már növekvő számok lesznek láthatók (vagy betűk, beágyazott listák esetében). Beágyazott számozott lista létrehozásához helyezzen el tabulátorkaraktereket a szülőlistán belül.|
|Bulleted list|`insertBulletedList` |Listajeles listát szúr be a szövegbe.|
|Table        |`insertTable`        |Markdown formázású táblázatstruktúrát szúr be a szövegbe.<br><br>A Table parancs választása után adja meg az oszlopok és a sorok számát oszlop:sor formátumban, például „3:4”. Vegye figyelembe, hogy legfeljebb 5 oszlopot tud beállítani ezzel a bővítménnyel, és ennél több oszlop használata nem is javasolt, mert rontaná az olvashatóságot.|
|Link         |`selectLinkType`      |Beszúr egy hivatkozást a szövegbe. A parancs választásakor a következő almenü jelenik meg.<br><br>`External`: Hivatkozás egy weblapra URI használatával. Tartalmaznia kell a „http” vagy a „https” előtagot.<br>`Internal`: Azonos tárházban lévő másik fájlra mutató relatív hivatkozás beszúrása. E lehetőség választása után a parancsablakba gépelve szűrhet a fájlnévre, majd kiválaszthatja a kívánt fájlt. <br>`Bookmark in this file`: Választhat egyet az aktuális fájl címsorai közül, és a bővítmény beszúrja azt megfelelően formázott könyvjelzőként.<br>`Bookmark in another file`: Először szűrjön a fájlnévre, és válassza ki a hivatkozni kívánt fájlt, majd válasszon egyet az adott fájlon belüli címsorok közül.|
|Image        |`insertImage`     |Gépelje be a helyettesítő szöveget (akadálymentességi okokból szükséges), jelölje azt ki, futtassa ezt a parancsot a tárházban lévő támogatott képfájlok listázásához, szűrje a listát, majd válassza ki a kívánt képfájlt. Ha a parancs végrehajtásakor nincs helyettesítő szöveg kijelölve, akkor a program kérni fogja a helyettesítő szöveg megadását, mielőtt képfájlt választhatna.|
|Include      |`insertInclude`   |Megkereshet és beágyazhat egy fájlt az aktuális fájlba.|
|Snippet      |`insertSnippet`   |Megkeresheti a tárház egyik kódrészletét, és beágyazhatja azt az aktuális fájlba.|
|Videó        |`insertVideo`     |Hozzáad egy beágyazott videót a szöveghez.|
|Preview      |`previewTopic`    |Megjeleníti az aktuális témakör formázott előnézetét a DocFX bővítmény segítségével egy, a tartalom mellett megjelenő ablakban.  Ha a DocFX bővítmény nincs telepítve vagy le van tiltva, akkor a témakör előnézete nem jelenik meg.


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

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>A régi „Gauntlet” eszköztár megjelenítése

A korábbi „Gauntlet” kódnevű bővítményt ismerő felhasználók észrevehetik, hogy a szerzői eszköztár nem jelenik meg többé a VS Code ablakának alján a Docs Markdown bővítmény telepítésekor. Ennek az oka az, hogy az eszköztár túl sok helyet foglalt el a VS Code állapotsávján, és nem követte a bővítmények felhasználói élményre vonatkozó ajánlásait, ezért az új bővítményben ezt a funkciót kivontuk a használatból. De ha szeretné, továbbra is megjelenítheti ezt az eszköztárat úgy, hogy frissíti a VS Code alkalmazás settings.json fájlját a következő módon:

1. A VS Code alkalmazásban válassza a Fájl -> Beállítások -> Beállítások (`CTRL+Comma`) lehetőséget.
1. Válassza a „Felhasználói beállítások” lehetőséget az összes VS Code-munkaterület beállításainak módosításához, vagy a „Munkaterület-beállítások” lehetőséget, ha csak az aktuális munkaterület beállításait szeretné módosítani.
1. Az „Alapértelmezett beállítások” panelen keresse meg a „Docs Authoring Extension Configuration” nevű szakaszt, és válassza a ceruzaikont a megfelelő beállítás mellett. A program kérni fogja, hogy adja meg a `true` vagy a `false` beállítást. Ezután a VS Code automatikusan hozzáadja az új értéket a settings.json fájlhoz, majd felkéri Önt az ablak újratöltésére a módosítások érvénybe léptetéséhez.

## <a name="known-issues"></a>Ismert problémák

- DocFX Preview: MacOS és Linux: A DocFX Preview nem nyitja meg megfelelően az előnézetet (az előnézet a VS Code Markdown-előnézetét jeleníti meg alapértelmezés szerint e platformokon).
- DocFx Preview: Összes platform: Bizonyos szintaxisok, például az API-kra mutató xref kereszthivatkozások, nem jelennek meg megfelelően az előnézetben, és esetenként hézagokat láthat a tartalomban.
- Külső könyvjelzők: Linuxon a fájllista megjelenik, de nem tartalmaz egyetlen kiválasztható címsort sem.
- Fájlbelefoglalások: Linuxon a fájllista megjelenik, de a fájl kiválasztása után nem szúr be a program hivatkozást.
