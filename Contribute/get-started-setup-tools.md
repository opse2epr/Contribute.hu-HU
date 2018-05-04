---
title: Tartalomkészítő eszközök telepítése
description: Ez a cikk azt ismerteti, hogyan tölthetők le azok az eszközök, amelyek a Git használatához és a Markdown-fájlok szerkesztéséhez szükségesek.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1011c3fc829202a3df134ddc80eb05b8959b7bf6
ms.sourcegitcommit: 7b668124f25b8ad0442937a3ad05b19a47af5970
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2018
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="3e6ec-103">Tartalomkészítő eszközök telepítése</span><span class="sxs-lookup"><span data-stu-id="3e6ec-103">Install content authoring tools</span></span>

<span data-ttu-id="3e6ec-104">A cikk ismerteti a lépéseket, melyekkel interaktív módon telepíthetők a Git ügyféleszközei és a Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3e6ec-105">A [Git for Windows](https://git-scm.com/download/win) telepítése</span><span class="sxs-lookup"><span data-stu-id="3e6ec-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="3e6ec-106">A [Visual Studio Code](https://code.visualstudio.com/) telepítése</span><span class="sxs-lookup"><span data-stu-id="3e6ec-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>
> * <span data-ttu-id="3e6ec-107">A [Közreműködői csomag a Docs webhelyhez](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) telepítése</span><span class="sxs-lookup"><span data-stu-id="3e6ec-107">Install [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3e6ec-108">Ha csak kisebb módosításokat végez egy cikken, akkor *nem szükséges* elvégeznie az itt ismertetett lépéseket, és továbbléphet a [kisebb módosítások munkafolyamatához](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="3e6ec-108">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="3e6ec-109">Javasoljuk azonban, hogy a nagyobb változtatásokat végző közreműködők végezzék el ezt a lépést is, hogy a [nagyobb/tartós változtatásokat](how-to-write-workflows-major.md) is el tudják végezni.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-109">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="3e6ec-110">Még ha van is írási engedélye a fő tárházban, akkor is *kifejezetten ajánljuk a tárház elágaztatását és klónozását (és ebben az útmutatóban feltételezzük is, hogy ezt megtette)*, hogy rendelkezzen írási és olvasási jogosultsággal a javasolt módosítások tárolásához az elágazásban.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-110">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="3e6ec-111">A Git-ügyféleszközök telepítése Windows rendszeren</span><span class="sxs-lookup"><span data-stu-id="3e6ec-111">Install Git client tools on Windows</span></span>

 <span data-ttu-id="3e6ec-112">Telepítse a [Software Freedom Conservancy Git-ügyféleszközeit](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="3e6ec-112">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="3e6ec-113">A telepítés tartalmazza a Git verziókövetési rendszert és a Git Bash parancssori alkalmazást, amely a helyi Git-tárházzal való kommunikációhoz használható.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-113">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="3e6ec-114">Ha parancssori eszköz helyett inkább grafikus felhasználói felületet szeretne használni, a legnépszerűbb eszközöket megtalálja a [Software Freedom Conservancy elérhető GUI-eszközöket bemutató](https://git-scm.com/downloads/guis) oldalán, vagy próbálja ki a [GitHubon elérhető GitHub Desktopot](https://desktop.github.com/) vagy a [Visual Studio Code-ot](https://www.visualstudio.com/products/code-vs.aspx).</span><span class="sxs-lookup"><span data-stu-id="3e6ec-114">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="3e6ec-115">Kövesse a kiválasztott ügyfél telepítésére és konfigurálására vonatkozó utasításokat.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-115">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="3e6ec-116">A következő cikk a [Helyi Git-tárház beállításával](get-started-setup-local.md) foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-116">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="3e6ec-117">További Git-források a következő helyeken állnak rendelkezésre: [Git-terminológia](https://help.github.com/articles/github-glossary) | [A Git alapjai](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Ismerkedés a Gittel és a GitHubbal](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="3e6ec-117">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="3e6ec-118">A Markdown-szerkesztők ismertetése</span><span class="sxs-lookup"><span data-stu-id="3e6ec-118">Understand Markdown editors</span></span>

<span data-ttu-id="3e6ec-119">A Markdown egy egyszerűen használható jelölőnyelv, amely könnyen olvasható és könnyen elsajátítható.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-119">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="3e6ec-120">Így rövid idő alatt iparági szabvánnyá vált.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-120">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="3e6ec-121">Ha Markdown formátumban szeretne cikkeket írni, javasoljuk, hogy töltsön le és telepítsen egy Markdown-szerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-121">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="3e6ec-122">A Microsoftnál a [Visual Studio Code](https://code.visualstudio.com/) a Markdown-szerkesztés elsődleges eszköze.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-122">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="3e6ec-123">Az [Atom](https://atom.io) egy másik népszerű, Markdown-szerkesztésre szolgáló eszköz.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-123">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="3e6ec-124">A Markdown .md kiterjesztésű fájlokban mentett szöveg.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-124">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="3e6ec-125">A [Markdown használata](how-to-write-use-markdown.md) szakaszban további információt talál, többek között bevezetőt a Markdownba, valamint az egyedi OPS Markdown-bővítmények által támogatott funkciókról.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-125">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="3e6ec-126">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3e6ec-126">Visual Studio Code</span></span>

<span data-ttu-id="3e6ec-127">A [Visual Studio Code](https://code.visualstudio.com/), más néven VS Code, egy kis méretű szerkesztő, amely Windows, Linux és Mac rendszereken használható.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-127">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="3e6ec-128">Tartalmaz Git-integrációt és támogatja a bővítmények használatát.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-128">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="3e6ec-129">Töltse le és telepítse a [VS Code](https://code.visualstudio.com/) eszközt.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-129">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="3e6ec-130">A VS Code kezdőlapja elvileg helyesen észleli az operációs rendszert.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-130">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="3e6ec-131">Windows</span><span class="sxs-lookup"><span data-stu-id="3e6ec-131">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="3e6ec-132">Mac</span><span class="sxs-lookup"><span data-stu-id="3e6ec-132">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="3e6ec-133">Linux</span><span class="sxs-lookup"><span data-stu-id="3e6ec-133">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="3e6ec-134">A VS Code elindításához és az aktuális mappa megnyitásához futtassa a következő parancsot a parancssorban vagy a Bash felületen: `code .`.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-134">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="3e6ec-135">Ha az aktuális mappa egy helyi Git-tárház része, a GitHub-integráció automatikusan megjelenik a Visual Studio Code-ban.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-135">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="docs-authoring-pack"></a><span data-ttu-id="3e6ec-136">Közreműködői csomag a Docs webhelyhez</span><span class="sxs-lookup"><span data-stu-id="3e6ec-136">Docs Authoring Pack</span></span>
<span data-ttu-id="3e6ec-137">Telepítse a Visual Studio Code-hoz használható Közreműködői csomagot a Docs webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-137">Install the Docs Authoring Pack for Visual Studio Code.</span></span> <span data-ttu-id="3e6ec-138">Ez a bővítménycsomag alapszintű segítséget nyújt a közreműködői tevékenységhez Markdown-formátumban való íráshoz, és előnézeti funkciót is tartalmaz, így megnézheti, hogyan néz majd ki a Markdown-szöveg a docs.microsoft.com webhely stílusával.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-138">This set of extensions includes basic authoring assistance for help when writing Markdown, and a preview feature, so that you can see what the Markdown looks like in the style of the docs.microsoft.com site.</span></span>

   <span data-ttu-id="3e6ec-139">Keresse fel a [Marketplace-webhelyet](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack), majd válassza a **Telepítés** lehetőséget, vagy keresse meg a `docsmsft.docs-authoring-pack` elemet a VS Code-ablak bővítménylistájában.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-139">Visit this [marketplace page](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) and select **Install**, or search for `docsmsft.docs-authoring-pack` in your extensions list in the VS Code window.</span></span> 

   <span data-ttu-id="3e6ec-140">A Közreműködői csomag a Docs webhelyhez az Alt+M billentyűkombinációval érhető el a VS Code-ban.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-140">The Docs Authoring Pack is accessible by pressing Alt+M inside of VS Code.</span></span> <span data-ttu-id="3e6ec-141">Az eszköztár alapbeállítás szerint el van rejtve, de megjeleníthető.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-141">The toolbar is hidden by default but can be shown.</span></span> <span data-ttu-id="3e6ec-142">Az eszköztár megjelenítéséhez módosítsa a VS Code beállításait (Control+vessző) `"markdown.showToolbar": true` felhasználói beállítások hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-142">Edit the VS Code settings (Control+comma) and adding user setting `"markdown.showToolbar": true` to show the toolbar.</span></span>

   <span data-ttu-id="3e6ec-143">További információt a [Közreműködői csomag a Docs webhelyhez](how-to-write-docs-auth-pack.md) oldalán találhat.</span><span class="sxs-lookup"><span data-stu-id="3e6ec-143">For more information, see the [Docs Authoring Pack](how-to-write-docs-auth-pack.md) page.</span></span>


## <a name="next-steps"></a><span data-ttu-id="3e6ec-144">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="3e6ec-144">Next steps</span></span>

<span data-ttu-id="3e6ec-145">Most már készen áll a [Helyi Git-tárház beállítására](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="3e6ec-145">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
