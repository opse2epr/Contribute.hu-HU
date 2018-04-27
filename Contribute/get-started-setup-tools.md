---
title: Tartalomkészítő eszközök telepítése
description: Ez a cikk azt ismerteti, hogyan tölthetők le azok az eszközök, amelyek a Git használatához és a Markdown-fájlok szerkesztéséhez szükségesek.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 01/04/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 62c4b234f23b470ffea33cacdfc469fbd7e526bd
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2018
---
# <a name="install-content-authoring-tools"></a>Tartalomkészítő eszközök telepítése

A cikk ismerteti a lépéseket, melyekkel interaktív módon telepíthetők a Git ügyféleszközei és a Visual Studio Code.
> [!div class="checklist"]
> * A [Git for Windows](https://git-scm.com/download/win) telepítése
> * A [Visual Studio Code](https://code.visualstudio.com/) telepítése

>[!IMPORTANT]
> Ha csak kisebb módosításokat végez egy cikken, akkor *nem szükséges* elvégeznie az itt ismertetett lépéseket, és továbbléphet a [kisebb/alkalmi módosítások munkafolyamatához](light-workflow.md).
>
> Javasoljuk azonban, hogy a nagyobb változtatásokat végző közreműködők végezzék el ezt a lépést is, hogy a [nagyobb/tartós változtatásokat](full-workflow.md) is el tudják végezni. Még ha van is írási engedélye a fő tárházban, akkor is *kifejezetten ajánljuk a tárház elágaztatását és klónozását (és ebben az útmutatóban feltételezzük is, hogy ezt megtette)*, hogy rendelkezzen írási és olvasási jogosultsággal a javasolt módosítások tárolásához az elágazásban.

## <a name="install-git-client-tools-on-windows"></a>A Git-ügyféleszközök telepítése Windows rendszeren

 Telepítse a [Software Freedom Conservancy Git-ügyféleszközeit](https://git-scm.com/download/). A telepítés tartalmazza a Git verziókövetési rendszert és a Git Bash parancssori alkalmazást, amely a helyi Git-tárházzal való kommunikációhoz használható.

Ha parancssori eszköz helyett inkább grafikus felhasználói felületet szeretne használni, a legnépszerűbb eszközöket megtalálja a [Software Freedom Conservancy elérhető GUI-eszközöket bemutató](https://git-scm.com/downloads/guis) oldalán, vagy próbálja ki a [GitHubon elérhető GitHub Desktopot](https://desktop.github.com/) vagy a [Visual Studio Code-ot](https://www.visualstudio.com/products/code-vs.aspx).

Kövesse a kiválasztott ügyfél telepítésére és konfigurálására vonatkozó utasításokat.

A következő cikk a [Helyi Git-tárház beállításával](get-started-setup-local.md) foglalkozik.

   További Git-források a következő helyeken állnak rendelkezésre: [Git-terminológia](https://help.github.com/articles/github-glossary) | [A Git alapjai](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Ismerkedés a Gittel és a GitHubbal](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>A Markdown-szerkesztők ismertetése

A Markdown egy egyszerűen használható jelölőnyelv, amely könnyen olvasható és könnyen elsajátítható. Így rövid idő alatt iparági szabvánnyá vált. Ha Markdown formátumban szeretne cikkeket írni, javasoljuk, hogy töltsön le és telepítsen egy Markdown-szerkesztőt.  A Microsoftnál a [Visual Studio Code](https://code.visualstudio.com/) a Markdown-szerkesztés elsődleges eszköze. Az [Atom](https://atom.io) egy másik népszerű, Markdown-szerkesztésre szolgáló eszköz.

A Markdown .md kiterjesztésű fájlokban mentett szöveg.

A [Markdown használata](how-to-write-use-markdown.md) szakaszban további információt talál, többek között bevezetőt a Markdownba, valamint az egyedi OPS Markdown-bővítmények által támogatott funkciókról.

## <a name="visual-studio-code"></a>Visual Studio Code

A [Visual Studio Code](https://code.visualstudio.com/), más néven VS Code, egy kis méretű szerkesztő, amely Windows, Linux és Mac rendszereken használható. Tartalmaz Git-integrációt és támogatja a bővítmények használatát.

Töltse le és telepítse a [VS Code](https://code.visualstudio.com/) eszközt. A VS Code kezdőlapja elvileg helyesen észleli az operációs rendszert.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> A VS Code elindításához és az aktuális mappa megnyitásához futtassa a következő parancsot a parancssorban vagy a Bash felületen: `code .`. Ha az aktuális mappa egy helyi Git-tárház része, a GitHub-integráció automatikusan megjelenik a Visual Studio Code-ban.

## <a name="next-steps"></a>Következő lépések

Most már készen áll a [Helyi Git-tárház beállítására](get-started-setup-local.md).