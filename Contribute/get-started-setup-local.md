---
title: Git-tárház helyi beállítása
description: Ez a cikk útmutatást nyújt a helyi Git-tárház létrehozásához és a dokumentációban való közreműködéshez, beleértve a tárház elágaztatásának és klónozásának folyamatát is.
author: jasonwhowell
ms.author: jasonh
ms.date: 01/18/2018
ms.openlocfilehash: 5373bf34399105c15caabe0abdc1ea0692c46a4a
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609499"
---
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="3991e-103">Git-tárház helyi beállítása dokumentációhoz</span><span class="sxs-lookup"><span data-stu-id="3991e-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="3991e-104">A cikk azokat a lépéseket ismerteti, melyekkel beállítható egy Git-tárház a helyi számítógépen a Microsoft dokumentációjának készítésében való közreműködés céljából.</span><span class="sxs-lookup"><span data-stu-id="3991e-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="3991e-105">A közreműködők egy helyileg klónozott tárház használatával adhatnak hozzá új cikkeket, végezhetnek jelentős módosításokat a meglévő cikkeken, vagy módosíthatják a grafikus elemeket.</span><span class="sxs-lookup"><span data-stu-id="3991e-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="3991e-106">A közreműködés megkezdéséhez a következő egyszeri beállítási tevékenységeket kell végrehajtania:</span><span class="sxs-lookup"><span data-stu-id="3991e-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3991e-107">A megfelelő tárház meghatározása</span><span class="sxs-lookup"><span data-stu-id="3991e-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="3991e-108">A tárház elágaztatása a GitHub-fiókban</span><span class="sxs-lookup"><span data-stu-id="3991e-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="3991e-109">Egy helyi mappa kiválasztása a klónozott fájlok számára</span><span class="sxs-lookup"><span data-stu-id="3991e-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="3991e-110">A tárház klónozása a helyi számítógépen</span><span class="sxs-lookup"><span data-stu-id="3991e-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="3991e-111">A felső (upstream) távoli érték konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3991e-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3991e-112">Ha csak apró változtatásokat végez egy cikken, *nem* kell elvégeznie a cikkben szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3991e-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="3991e-113">Folytathatja közvetlenül a [gyorsmódosítások munkafolyamattal](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="3991e-113">You can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>

## <a name="overview"></a><span data-ttu-id="3991e-114">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="3991e-114">Overview</span></span>

<span data-ttu-id="3991e-115">A Microsoft dokumentációs webhelyének készítésében való közreműködéshez helyileg hozhat létre és szerkeszthet Markdown-fájlokat a megfelelő dokumentációs tárház klónozásával.</span><span class="sxs-lookup"><span data-stu-id="3991e-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="3991e-116">A Microsoft megköveteli, hogy létrehozza a megfelelő tárház elágazását a saját GitHub-fiókjában annak érdekében, hogy abban rendelkezzen olvasási és írási jogosultságokkal a javasolt módosításainak tárolásához.</span><span class="sxs-lookup"><span data-stu-id="3991e-116">Microsoft requires you to fork the appropriate repository into your own GitHub account so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="3991e-117">Ezután lekéréses kérelmekkel egyesítheti a módosításokat a csak olvasható központi megosztott tárházzal.</span><span class="sxs-lookup"><span data-stu-id="3991e-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![A GitHub-háromszög](./media/git-and-github-initial-setup.png)

<span data-ttu-id="3991e-119">Ha most ismerkedik a GitHubbal, tekintse meg az alábbi videót, amelyben megismerkedhet az elágaztatás és a klónozás alapjaival:</span><span class="sxs-lookup"><span data-stu-id="3991e-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="3991e-120">A tárház meghatározása</span><span class="sxs-lookup"><span data-stu-id="3991e-120">Determine the repository</span></span>

<span data-ttu-id="3991e-121">A [docs.microsoft.com](https://docs.microsoft.com) webhelyen szolgáltatott dokumentáció a [github.com](https://www.github.com) számos különböző tárhelyén található.</span><span class="sxs-lookup"><span data-stu-id="3991e-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="3991e-122">Ha nem biztos benne, hogy melyik tárházat kell használnia, nyissa meg a cikket a [docs.microsoft.com](https://docs.microsoft.com) webhelyen a webböngészővel.</span><span class="sxs-lookup"><span data-stu-id="3991e-122">If you are unsure of which repository to use, then visit the article on [docs.microsoft.com](https://docs.microsoft.com) using your web browser.</span></span> <span data-ttu-id="3991e-123">Válassza a **Szerkesztés** hivatkozást (a ceruza ikont) a cikk jobb felső sarkában.</span><span class="sxs-lookup"><span data-stu-id="3991e-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![A tárház és a fájl helyének meghatározásához kattintson a Szerkesztés lehetőségre.](media/index/edit-article.png)

2. <span data-ttu-id="3991e-125">A hivatkozás a megfelelő tárházban található kapcsolódó Markdown-fájl github.com-beli helyét nyitja meg.</span><span class="sxs-lookup"><span data-stu-id="3991e-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="3991e-126">A tárház nevének megtekintéséhez figyelje meg az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="3991e-126">Note the URL to view the repository name.</span></span>

   ![A tárház helyének meghatározásához figyelje meg az URL-címet.](media/public-repo.png)

   <span data-ttu-id="3991e-128">Például a következő népszerű tárházakban végezhető nyilvános közreműködés:</span><span class="sxs-lookup"><span data-stu-id="3991e-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="3991e-129">Azure-dokumentáció [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="3991e-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="3991e-130">SQL Server-dokumentáció [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="3991e-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="3991e-131">Visual Studio-dokumentáció [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="3991e-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="3991e-132">.NET-dokumentáció [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="3991e-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="3991e-133">Azure .Net SDK-dokumentáció [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="3991e-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="3991e-134">A tárház elágaztatása</span><span class="sxs-lookup"><span data-stu-id="3991e-134">Fork the repository</span></span>
<span data-ttu-id="3991e-135">Készítsen egy elágaztatott példányt a megfelelő tárházról a saját GitHub-fiókjába a GitHub webhelyen keresztül.</span><span class="sxs-lookup"><span data-stu-id="3991e-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="3991e-136">A személyes elágazás használata azért kötelező, mert minden fő dokumentáció csak olvasható hozzáférést engedélyez.</span><span class="sxs-lookup"><span data-stu-id="3991e-136">A personal fork is required since all main documentation repositories provide read-only access.</span></span> <span data-ttu-id="3991e-137">A tartalom módosításához [pull-kérelmet](git-github-fundamentals.md#pull-requests) kell küldenie a fő tárházba az Ön saját elágaztatott példányából.</span><span class="sxs-lookup"><span data-stu-id="3991e-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="3991e-138">Ehhez először létre kell hoznia a tárház saját példányát, amelyben írási engedéllyel is rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="3991e-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="3991e-139">A GitHub *elágazás (fork)* erre a célra szolgál.</span><span class="sxs-lookup"><span data-stu-id="3991e-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="3991e-140">Nyissa meg a fő tárház GitHub-oldalát, és a jobb első sarokban kattintson a **Fork** (elágaztatás) gombra.</span><span class="sxs-lookup"><span data-stu-id="3991e-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![Példa GitHub-profilra](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="3991e-142">Amikor a rendszer kéri, válassza ki azt a GitHub-fiókot, amelyet a létrehozandó elágazás céljaként szeretne használni.</span><span class="sxs-lookup"><span data-stu-id="3991e-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="3991e-143">Ez létrehozza a tárház egy úgynevezett „elágaztatott” példányát az Ön GitHub-fiókján belül.</span><span class="sxs-lookup"><span data-stu-id="3991e-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="3991e-144">Helyi mappa választása</span><span class="sxs-lookup"><span data-stu-id="3991e-144">Choose a local folder</span></span>
<span data-ttu-id="3991e-145">Hozzon létre egy mappát a számítógépén a tárház helyi példányának.</span><span class="sxs-lookup"><span data-stu-id="3991e-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="3991e-146">Egyes tárházak mérete nagy lehet; akár 5 GB is, például az azure-docs tárház esetében.</span><span class="sxs-lookup"><span data-stu-id="3991e-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="3991e-147">Válasszon elegendő tárterülettel rendelkező helyet.</span><span class="sxs-lookup"><span data-stu-id="3991e-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="3991e-148">Válasszon egy olyan mappanevet, amely könnyen megjegyezhető és begépelhető.</span><span class="sxs-lookup"><span data-stu-id="3991e-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="3991e-149">Használhatja például a `C:\docs\` gyökérmappát, vagy a felhasználói profilja mappáján belüli `~/Documents/docs/` mappát.</span><span class="sxs-lookup"><span data-stu-id="3991e-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3991e-150">Ne válasszon olyan helyi mappaútvonalat, amely egy másik Git-tárház mappáján belülre mutat.</span><span class="sxs-lookup"><span data-stu-id="3991e-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="3991e-151">Míg a klónozott Git-mappákat gond nélkül tárolhatja egymás mellett, ha egymásba ágyazza őket, az fájlkövetési hibákhoz vezet.</span><span class="sxs-lookup"><span data-stu-id="3991e-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="3991e-152">A Git Bash megnyitása</span><span class="sxs-lookup"><span data-stu-id="3991e-152">Launch Git Bash</span></span>

   ![A Git Bash megnyitása](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="3991e-154">A Git Bash alapértelmezés szerint jellemzően a kezdőkönyvtárral (~) vagy Windows rendszeren a `/c/users/<Windows-user-account>/` könyvtárral nyílik meg.</span><span class="sxs-lookup"><span data-stu-id="3991e-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="3991e-155">Az aktuális könyvtár ellenőrzéséhez írja be a `pwd` parancsot a $ parancssorba.</span><span class="sxs-lookup"><span data-stu-id="3991e-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="3991e-156">Váltson a cd paranccsal abba a mappába, amelyet a tárház helyi példányának létrehozott.</span><span class="sxs-lookup"><span data-stu-id="3991e-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="3991e-157">Ne feledje, hogy a Git Bash a Linux rendszer konvencióját követve nem fordított perjelet, hanem perjelet használ a mappaútvonalakban.</span><span class="sxs-lookup"><span data-stu-id="3991e-157">Note that Git Bash uses the Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="3991e-158">Például: `cd /c/docs/ ` vagy `cd ~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="3991e-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="3991e-159">Helyi klón létrehozása</span><span class="sxs-lookup"><span data-stu-id="3991e-159">Create a local clone</span></span>

<span data-ttu-id="3991e-160">Készüljön fel a Git Bash segítségével a **clone** parancs futtatására, mellyel a tárház saját használatú példányát az eszköze aktuális könyvtárába fogja másolni.</span><span class="sxs-lookup"><span data-stu-id="3991e-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="3991e-161">Hitelesítés a Git Credential Manager használatával</span><span class="sxs-lookup"><span data-stu-id="3991e-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="3991e-162">Ha a Git for Windows legújabb verziójával rendelkezik, és annak telepítésénél az alapértelmezés szerinti beállításokat fogadta el, akkor a Git Credential Manager alapértelmezés szerint engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="3991e-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="3991e-163">A Git Credential Manager jelentősen leegyszerűsíti a hitelesítést, hiszen így nem szükséges majd előkeresnie a személyes hozzáférési tokent minden alkalommal, amikor újraindítja a GitHubbal létesített hitelesített kapcsolatot vagy a távoli kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="3991e-163">Git Credential Manager makes authentication much easier because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="3991e-164">Futtassa a **clone** parancsot a tárház nevének megadásával.</span><span class="sxs-lookup"><span data-stu-id="3991e-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="3991e-165">A klónozás letölti (klónozza) az elágaztatott tárházat a helyi számítógépére.</span><span class="sxs-lookup"><span data-stu-id="3991e-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="3991e-166">Az elágazás GitHubos URL-címét úgy szerezheti meg egyszerűen, ha a GitHub webhelyen a **Clone or download** (Klónozás vagy letöltés) gombra kattint:</span><span class="sxs-lookup"><span data-stu-id="3991e-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![Clone or download (Klónozás vagy letöltés)](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="3991e-168">Ügyeljen rá, hogy a klónozási folyamat során a *saját elágazása* útvonalát adja meg, ne pedig a fő tárházért, amelyből az elágazást létrehozta.</span><span class="sxs-lookup"><span data-stu-id="3991e-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="3991e-169">Ellenkező esetben nem fogja tudni közzétenni a módosításait.</span><span class="sxs-lookup"><span data-stu-id="3991e-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="3991e-170">A saját elágazására a személyes GitHub-fiókján keresztül hivatkozhat, például: `github.com/<github-username>/<repo>`.</span><span class="sxs-lookup"><span data-stu-id="3991e-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="3991e-171">A klónozási parancsának az alábbihoz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="3991e-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="3991e-172">Ha a rendszer kéri, adja meg a GitHubhoz használt hitelesítő adatait.</span><span class="sxs-lookup"><span data-stu-id="3991e-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![GitHub – bejelentkezés](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="3991e-174">Ha a rendszer kéri, adja meg a kéttényezős hitelesítő kódját.</span><span class="sxs-lookup"><span data-stu-id="3991e-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![GitHub – kéttényezős hitelesítés](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="3991e-176">A bejelentkezési adatokat a rendszer menti, és a későbbiekben ezeket használja a GitHub-kérések hitelesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3991e-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="3991e-177">Ezt a hitelesítést számítógépenként csak egyszer kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="3991e-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="3991e-178">Ekkor lefut a clone parancs, és letölti a tárház fájljainak egy példányát az Ön elágaztatott tárházából a helyi lemez egy új mappájába.</span><span class="sxs-lookup"><span data-stu-id="3991e-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="3991e-179">Az új mappa az aktuális mappán belül jön létre.</span><span class="sxs-lookup"><span data-stu-id="3991e-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="3991e-180">A művelet akár néhány percig is eltarthat, a tárház méretétől függően.</span><span class="sxs-lookup"><span data-stu-id="3991e-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="3991e-181">Miután befejeződött, megnyithatja a mappát, és ellenőrizheti annak tartalmát.</span><span class="sxs-lookup"><span data-stu-id="3991e-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="3991e-182">A távoli felső tárház konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3991e-182">Configure remote upstream</span></span>
<span data-ttu-id="3991e-183">Miután klónozta a tárházat, állítson be egy csak olvasható távoli kapcsolatot a fő tárházhoz **upstream** néven.</span><span class="sxs-lookup"><span data-stu-id="3991e-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="3991e-184">Az upstream URL segítségével biztosíthatja, hogy a mások által végrehajtott módosítások mindig szinkronizálva legyenek a saját helyi tárházában is.</span><span class="sxs-lookup"><span data-stu-id="3991e-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="3991e-185">Ezt a beállítást a **git remote** paranccsal tudja elvégezni.</span><span class="sxs-lookup"><span data-stu-id="3991e-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="3991e-186">A **fetch** paranccsal frissítheti az ágadatokat az upstream tárházból.</span><span class="sxs-lookup"><span data-stu-id="3991e-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="3991e-187">Ha a **Git Credential Managert** használja, hajtsa végre az alábbi parancsokat:</span><span class="sxs-lookup"><span data-stu-id="3991e-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="3991e-188">Cserélje a \<repo\> és az \<organization\> helyőrzőt a megfelelő értékre.</span><span class="sxs-lookup"><span data-stu-id="3991e-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="3991e-189">Tekintse meg a beállított értékeket, és győződjön meg róla, hogy az URL-ek helyesek.</span><span class="sxs-lookup"><span data-stu-id="3991e-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="3991e-190">Az **origin** URL-eknek a személyes, elágaztatott tárházára kell mutatniuk.</span><span class="sxs-lookup"><span data-stu-id="3991e-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="3991e-191">Az **upstream** URL-eknek a fő tárházra kell mutatniuk, például a MicrosoftDocs vagy az Azure tárházra.</span><span class="sxs-lookup"><span data-stu-id="3991e-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="3991e-192">Az alábbi példában láthatja a remote parancs kimenetét.</span><span class="sxs-lookup"><span data-stu-id="3991e-192">Example remote output is shown.</span></span> <span data-ttu-id="3991e-193">Egy „MyGitAccount” nevű fiktív Git-fiókot konfiguráltunk személyes hozzáférési jogkivonattal az azure-docs tárház eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="3991e-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="3991e-194">Ha nem megfelelő értéket állított be, eltávolíthatja azt a remote parancs ismételt futtatásával.</span><span class="sxs-lookup"><span data-stu-id="3991e-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="3991e-195">Az upstream érték eltávolításához használja a `git remote remove upstream` parancsot.</span><span class="sxs-lookup"><span data-stu-id="3991e-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3991e-196">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="3991e-196">Next steps</span></span>
- <span data-ttu-id="3991e-197">Ha szeretne többet megtudni a tartalmak hozzáadásáról és frissítéséről, folytassa a [GitHub-alapú közreműködést ismertető témakörrel](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="3991e-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>
