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
ms.openlocfilehash: 0ca942e557640db1ba36d3f5b1064656ed3dea8d
ms.sourcegitcommit: 3ec397fab57ea582edb03a59609f62d886410ee8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="8e98f-103">Tartalomkészítő eszközök telepítése</span><span class="sxs-lookup"><span data-stu-id="8e98f-103">Install content authoring tools</span></span>

<span data-ttu-id="8e98f-104">A cikk ismerteti a lépéseket, melyekkel interaktív módon telepíthetők a Git ügyféleszközei és a Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8e98f-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="8e98f-105">A [Git for Windows](https://git-scm.com/download/win) telepítése</span><span class="sxs-lookup"><span data-stu-id="8e98f-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="8e98f-106">A [Visual Studio Code](https://code.visualstudio.com/) telepítése</span><span class="sxs-lookup"><span data-stu-id="8e98f-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8e98f-107">Ha csak kisebb módosításokat végez egy cikken, akkor *nem szükséges* elvégeznie az itt ismertetett lépéseket, és továbbléphet a [kisebb módosítások munkafolyamatához](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="8e98f-107">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="8e98f-108">Javasoljuk azonban, hogy a nagyobb változtatásokat végző közreműködők végezzék el ezt a lépést is, hogy a [nagyobb/tartós változtatásokat](how-to-write-workflows-major.md) is el tudják végezni.</span><span class="sxs-lookup"><span data-stu-id="8e98f-108">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="8e98f-109">Még ha van is írási engedélye a fő tárházban, akkor is *kifejezetten ajánljuk a tárház elágaztatását és klónozását (és ebben az útmutatóban feltételezzük is, hogy ezt megtette)*, hogy rendelkezzen írási és olvasási jogosultsággal a javasolt módosítások tárolásához az elágazásban.</span><span class="sxs-lookup"><span data-stu-id="8e98f-109">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="8e98f-110">A Git-ügyféleszközök telepítése Windows rendszeren</span><span class="sxs-lookup"><span data-stu-id="8e98f-110">Install Git client tools on Windows</span></span>

 <span data-ttu-id="8e98f-111">Telepítse a [Software Freedom Conservancy Git-ügyféleszközeit](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="8e98f-111">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="8e98f-112">A telepítés tartalmazza a Git verziókövetési rendszert és a Git Bash parancssori alkalmazást, amely a helyi Git-tárházzal való kommunikációhoz használható.</span><span class="sxs-lookup"><span data-stu-id="8e98f-112">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="8e98f-113">Ha parancssori eszköz helyett inkább grafikus felhasználói felületet szeretne használni, a legnépszerűbb eszközöket megtalálja a [Software Freedom Conservancy elérhető GUI-eszközöket bemutató](https://git-scm.com/downloads/guis) oldalán, vagy próbálja ki a [GitHubon elérhető GitHub Desktopot](https://desktop.github.com/) vagy a [Visual Studio Code-ot](https://www.visualstudio.com/products/code-vs.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e98f-113">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="8e98f-114">Kövesse a kiválasztott ügyfél telepítésére és konfigurálására vonatkozó utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8e98f-114">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="8e98f-115">A következő cikk a [Helyi Git-tárház beállításával](get-started-setup-local.md) foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="8e98f-115">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="8e98f-116">További Git-források a következő helyeken állnak rendelkezésre: [Git-terminológia](https://help.github.com/articles/github-glossary) | [A Git alapjai](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Ismerkedés a Gittel és a GitHubbal](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="8e98f-116">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="8e98f-117">A Markdown-szerkesztők ismertetése</span><span class="sxs-lookup"><span data-stu-id="8e98f-117">Understand Markdown editors</span></span>

<span data-ttu-id="8e98f-118">A Markdown egy egyszerűen használható jelölőnyelv, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="8e98f-118">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="8e98f-119">Így rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="8e98f-119">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="8e98f-120">Ha Markdown formátumban szeretne cikkeket írni, javasoljuk, hogy töltsön le és telepítsen egy Markdown-szerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="8e98f-120">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="8e98f-121">A Microsoftnál a [Visual Studio Code](https://code.visualstudio.com/) a Markdown-szerkesztés elsődleges eszköze.</span><span class="sxs-lookup"><span data-stu-id="8e98f-121">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="8e98f-122">Az [Atom](https://atom.io) egy másik népszerű, Markdown-szerkesztésre szolgáló eszköz.</span><span class="sxs-lookup"><span data-stu-id="8e98f-122">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="8e98f-123">A Markdown .md kiterjesztésű fájlokban mentett szöveg.</span><span class="sxs-lookup"><span data-stu-id="8e98f-123">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="8e98f-124">A [Markdown használata](how-to-write-use-markdown.md) szakaszban további információt talál, többek között bevezetőt a Markdownba, valamint az egyedi OPS Markdown-bővítmények által támogatott funkciókról.</span><span class="sxs-lookup"><span data-stu-id="8e98f-124">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="8e98f-125">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8e98f-125">Visual Studio Code</span></span>

<span data-ttu-id="8e98f-126">A [Visual Studio Code](https://code.visualstudio.com/), más néven VS Code, egy kis méretű szerkesztő, amely Windows, Linux és Mac rendszereken használható.</span><span class="sxs-lookup"><span data-stu-id="8e98f-126">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="8e98f-127">Tartalmaz Git-integrációt és támogatja a bővítmények használatát.</span><span class="sxs-lookup"><span data-stu-id="8e98f-127">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="8e98f-128">Töltse le és telepítse a [VS Code](https://code.visualstudio.com/) eszközt.</span><span class="sxs-lookup"><span data-stu-id="8e98f-128">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="8e98f-129">A VS Code kezdőlapja elvileg helyesen észleli az operációs rendszert.</span><span class="sxs-lookup"><span data-stu-id="8e98f-129">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="8e98f-130">Windows</span><span class="sxs-lookup"><span data-stu-id="8e98f-130">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="8e98f-131">Mac</span><span class="sxs-lookup"><span data-stu-id="8e98f-131">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="8e98f-132">Linux</span><span class="sxs-lookup"><span data-stu-id="8e98f-132">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="8e98f-133">A VS Code elindításához és az aktuális mappa megnyitásához futtassa a következő parancsot a parancssorban vagy a Bash felületen: `code .`.</span><span class="sxs-lookup"><span data-stu-id="8e98f-133">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="8e98f-134">Ha az aktuális mappa egy helyi Git-tárház része, a GitHub-integráció automatikusan megjelenik a Visual Studio Code-ban.</span><span class="sxs-lookup"><span data-stu-id="8e98f-134">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e98f-135">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="8e98f-135">Next steps</span></span>

<span data-ttu-id="8e98f-136">Most már készen áll a [Helyi Git-tárház beállítására](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="8e98f-136">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
