---
title: Tartalomkészítő eszközök telepítése
description: Ez a cikk azt ismerteti, hogyan tölthetők le azok az eszközök, amelyek a Git használatához és a Markdown-fájlok szerkesztéséhez szükségesek.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.openlocfilehash: 715634a9a2342311eb1d358cb8379f90a7074d80
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609391"
---
# <a name="install-content-authoring-tools"></a>Tartalomkészítő eszközök telepítése

A cikk ismerteti a lépéseket, melyekkel interaktív módon telepíthetők a Git ügyféleszközei és a Visual Studio Code.
> [!div class="checklist"]
> * A [Git](https://git-scm.com/) telepítése
> * A [Visual Studio Code](https://code.visualstudio.com/) telepítése
> * A [Közreműködői csomag a Docs webhelyhez](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) telepítése

>[!IMPORTANT]
> Ha csak kisebb módosításokat végez egy cikken, akkor *nem szükséges* elvégeznie az itt ismertetett lépéseket, és továbbléphet a [kisebb módosítások munkafolyamatához](index.md#quick-edits-to-existing-documents).
>
> Javasoljuk azonban, hogy a nagyobb változtatásokat végző közreműködők végezzék el ezt a lépést is, hogy a [nagyobb/tartós változtatásokat](how-to-write-workflows-major.md) is el tudják végezni. Még ha van is írási engedélye a fő tárházban, akkor is *kifejezetten ajánljuk a tárház elágaztatását és klónozását (és ebben az útmutatóban feltételezzük is, hogy ezt megtette)*, hogy rendelkezzen írási és olvasási jogosultsággal a javasolt módosítások tárolásához az elágazásban.

## <a name="install-git-client-tools"></a>A Git-ügyféleszközök telepítése 

 Telepítse a [Software Freedom Conservancy Git-ügyféleszközeit](https://git-scm.com/download/) saját platformjához. 

* [Git for Windows](https://git-scm.com/download/win). A telepítés tartalmazza a Git verziókövetési rendszert és a Git Bash parancssori alkalmazást, amely a helyi Git-tárházzal való kommunikációhoz használható.
* A Git for Mac az Xcode parancssori eszközök részeként érhető el. Egyszerűen futtassa a parancssorból a következő parancsot: `git`. Ha szükséges, a rendszer kérni fogja, hogy telepítse a parancssori eszközöket. A [Git for Mac](https://git-scm.com/download/mac) a Software Freedom Conservancy webhelyéről is letölthető.
* [Git Linuxhoz és Unixhoz](https://git-scm.com/download/linux)

Ha parancssori eszköz helyett inkább grafikus felhasználói felületet szeretne használni, a legnépszerűbb eszközöket megtalálja a [Software Freedom Conservancy elérhető GUI-eszközöket bemutató](https://git-scm.com/downloads/guis) oldalán, vagy próbálja ki a [GitHubon elérhető GitHub Desktopot](https://desktop.github.com/) vagy a [Visual Studio Code-ot](https://www.visualstudio.com/products/code-vs.aspx).

Kövesse a kiválasztott ügyfél telepítésére és konfigurálására vonatkozó utasításokat.

A következő cikk a [Helyi Git-tárház beállításával](get-started-setup-local.md) foglalkozik.

   További Git-források a következő helyeken állnak rendelkezésre: [Git-terminológia](https://help.github.com/articles/github-glossary) | [A Git alapjai](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Ismerkedés a Gittel és a GitHubbal](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>A Markdown-szerkesztők ismertetése

A Markdown egy egyszerűen használható jelölőnyelv, amely könnyen olvasható és könnyen elsajátítható. Így rövid idő alatt iparági szabvánnyá vált. Ha Markdown formátumban szeretne cikkeket írni, javasoljuk, hogy töltsön le és telepítsen egy Markdown-szerkesztőt.  A Microsoftnál a [Visual Studio Code](https://code.visualstudio.com/) a Markdown-szerkesztés elsődleges eszköze. Az [Atom](https://atom.io) egy másik népszerű, Markdown-szerkesztésre szolgáló eszköz.

A Markdown .md kiterjesztésű fájlokban mentett szöveg.

A [Markdown használata Docs-tartalmak írásához](how-to-write-use-markdown.md) és a [Markdown-referencia OPS-hez](markdown-reference.md) című cikkben további információt talál a Markdown használatáról, többek között bevezetőt a Markdownba, valamint tájékoztatást az Open Publishing Services (OPS) egyedi Markdown-bővítményei által támogatott funkciókról.

## <a name="visual-studio-code"></a>Visual Studio Code

A [Visual Studio Code](https://code.visualstudio.com/), más néven VS Code, egy kis méretű szerkesztő, amely Windows, Linux és Mac rendszereken használható. Tartalmaz Git-integrációt és támogatja a bővítmények használatát.

Töltse le és telepítse a [VS Code](https://code.visualstudio.com/) eszközt. A VS Code kezdőlapja elvileg helyesen észleli az operációs rendszert.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> A VS Code elindításához és az aktuális mappa megnyitásához futtassa a következő parancsot a parancssorban vagy a Bash felületen: `code .`. Ha az aktuális mappa egy helyi Git-tárház része, a GitHub-integráció automatikusan megjelenik a Visual Studio Code-ban.

## <a name="docs-authoring-pack"></a>Közreműködői csomag a Docs webhelyhez
Telepítse a Visual Studio Code-hoz használható Közreműködői csomagot a Docs webhelyhez. Ez a bővítménycsomag alapszintű segítséget nyújt a közreműködői tevékenységhez Markdown-formátumban való íráshoz, és előnézeti funkciót is tartalmaz, így megnézheti, hogyan néz majd ki a Markdown-szöveg a docs.microsoft.com webhely stílusával.

   Keresse fel a [Marketplace-webhelyet](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack), majd válassza a **Telepítés** lehetőséget, vagy keresse meg a `docsmsft.docs-authoring-pack` elemet a VS Code-ablak bővítménylistájában. 

   A Közreműködői csomag a Docs webhelyhez az Alt+M billentyűkombinációval érhető el a VS Code-ban. Az eszköztár alapbeállítás szerint el van rejtve, de megjeleníthető. Az eszköztár megjelenítéséhez módosítsa a VS Code beállításait (Control+vessző) `"markdown.showToolbar": true` felhasználói beállítások hozzáadásával.

   További információt a [Közreműködői csomag a Docs webhelyhez](how-to-write-docs-auth-pack.md) oldalán találhat.


## <a name="next-steps"></a>Következő lépések

Most már készen áll a [Helyi Git-tárház beállítására](get-started-setup-local.md).
