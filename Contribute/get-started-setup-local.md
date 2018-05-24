---
title: Git-tárház helyi beállítása
description: Ez a cikk útmutatást nyújt a helyi Git-tárház létrehozásához és a dokumentációban való közreműködéshez, beleértve a tárház elágaztatásának és klónozásának folyamatát is.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 01/18/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: f702d0d29ee7dc9c69cb26b79bf6283d91b6b6bc
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/22/2018
---
# <a name="set-up-git-repository-locally-for-documentation"></a>Git-tárház helyi beállítása dokumentációhoz

A cikk azokat a lépéseket ismerteti, melyekkel beállítható egy Git-tárház a helyi számítógépen a Microsoft dokumentációjának készítésében való közreműködés céljából. A közreműködők egy helyileg klónozott tárház használatával adhatnak hozzá új cikkeket, végezhetnek jelentős módosításokat a meglévő cikkeken, vagy módosíthatják a grafikus elemeket.

A közreműködés megkezdéséhez a következő egyszeri beállítási tevékenységeket kell végrehajtania:
> [!div class="checklist"]
> * A megfelelő tárház meghatározása
> * A tárház elágaztatása a GitHub-fiókban
> * Egy helyi mappa kiválasztása a klónozott fájlok számára
> * A tárház klónozása a helyi számítógépen
> * A felső (upstream) távoli érték konfigurálása

> [!IMPORTANT]
> Ha csak apró változtatásokat végez egy cikken, *nem* kell elvégeznie a cikkben szereplő lépéseket. Folytathatja közvetlenül a [gyorsmódosítások munkafolyamattal](index.md#quick-edits-to-existing-documents).
>

## <a name="overview"></a>Áttekintés

A Microsoft dokumentációs webhelyének készítésében való közreműködéshez helyileg hozhat létre és szerkeszthet Markdown-fájlokat a megfelelő dokumentációs tárház klónozásával. A Microsoft megköveteli, hogy létrehozza a megfelelő tárház elágazását a saját GitHub-fiókjában annak érdekében, hogy rendelkezzen olvasási és írási jogosultságokkal abban a javasolt módosításainak tárolásához. Ezután lekéréses kérelmekkel egyesítheti a módosításokat a csak olvasható központi megosztott tárházzal.

![A GitHub-háromszög](./media/git-and-github-initial-setup.png)

Ha most ismerkedik a GitHubbal, tekintse meg az alábbi videót, amelyben megismerkedhet az elágaztatás és a klónozás alapjaival:

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>A tárház meghatározása

A [docs.microsoft.com](https://docs.microsoft.com) webhelyen szolgáltatott dokumentáció a [github.com](https://www.github.com) számos különböző tárhelyén található.

1. Ha nem biztos benne, hogy melyik tárházat kell használnia, nyissa meg a cikket a docs.microsoft.com webhelyen a webböngészővel. Válassza a **Szerkesztés** hivatkozást (a ceruza ikont) a cikk jobb felső sarkában.

   ![A tárház és a fájl helyének meghatározásához kattintson a Szerkesztés lehetőségre.](media/index/edit-article.png)

2. A hivatkozás a megfelelő tárházban található kapcsolódó Markdown-fájl github.com-beli helyét nyitja meg. A tárház nevének megtekintéséhez figyelje meg az URL-címet.

   ![A tárház helyének meghatározásához figyelje meg az URL-címet.](media/public-repo.png)

   Például a következő népszerű tárházakban végezhető nyilvános közreműködés:
   - Azure-dokumentáció [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - SQL Server-dokumentáció [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Visual Studio-dokumentáció [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - .NET-dokumentáció [https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Azure .Net SDK-dokumentáció [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)

## <a name="fork-the-repository"></a>A tárház elágaztatása
Készítsen egy elágaztatott példányt a megfelelő tárházról a saját GitHub-fiókjába a GitHub webhelyen keresztül.

Erre a személyes elágaztatott tárházra mindenképp szüksége lesz, mert az összes fő dokumentációs tárház csak olvasási engedélyt biztosít, azaz közvetlenül a tárházban nem végezhet tartalmi módosításokat. A tartalom módosításához [pull-kérelmet](git-github-fundamentals.md#pull-requests) kell küldenie a fő tárházba az Ön saját elágaztatott példányából. Ehhez először létre kell hoznia a tárház saját példányát, amelyben írási engedéllyel is rendelkezik. A GitHub *elágazás (fork)* erre a célra szolgál.

1. Nyissa meg a fő tárház GitHub-oldalát, és a jobb első sarokban kattintson a **Fork** (elágaztatás) gombra.

   ![Példa GitHub-profilra](./media/contribute-get-started-setup-local/fork.png)

2. Amikor a rendszer kéri, válassza ki azt a GitHub-fiókot, amelyet a létrehozandó elágazás céljaként szeretne használni. Ez létrehozza a tárház egy úgynevezett „elágaztatott” példányát az Ön GitHub-fiókján belül.

## <a name="choose-a-local-folder"></a>Helyi mappa választása
Hozzon létre egy mappát a számítógépén a tárház helyi példányának. Egyes tárházak mérete nagy lehet; akár 5 GB is, például az azure-docs tárház esetében. Válasszon elegendő tárterülettel rendelkező helyet.

1. Válasszon egy olyan mappanevet, amely könnyen megjegyezhető és begépelhető. Használhatja például a `C:\docs\` gyökérmappát, vagy a felhasználói profilja mappáján belüli `~/Documents/docs/` mappát.

   > [!IMPORTANT]
   > Ne válasszon olyan helyi mappaútvonalat, amely egy másik Git-tárház mappáján belülre mutat. Míg a klónozott Git-mappákat gond nélkül tárolhatja egymás mellett, ha egymásba ágyazza őket, az fájlkövetési hibákhoz vezet.

2. A Git Bash megnyitása

   ![A Git Bash megnyitása](./media/contribute-get-started-setup-local/gitbash-start.png)

   A Git Bash alapértelmezés szerint jellemzően a kezdőkönyvtárral (~) vagy Windows rendszeren a `/c/users/<Windows-user-account>/` könyvtárral nyílik meg.

   Az aktuális könyvtár ellenőrzéséhez írja be a `pwd` parancsot a $ parancssorba. 

3. Váltson a cd paranccsal abba a mappába, amelyet a tárház helyi példányának létrehozott. Ne feledje, hogy a Git Bash a Linux rendszer konvencióját követve nem fordított perjelet, hanem perjelet használ a mappaútvonalakban.

   Például: `cd /c/docs/ ` vagy `cd ~/Documents/docs/`

## <a name="create-a-local-clone"></a>Helyi klón létrehozása

Készüljön fel a Git Bash segítségével a **clone** parancs futtatására, mellyel a tárház saját használatú példányát az eszköze aktuális könyvtárába fogja másolni. 

### <a name="authenticate-by-using-git-credential-manager"></a>Hitelesítés a Git Credential Manager használatával
Ha a Git for Windows legújabb verziójával rendelkezik, és annak telepítésénél az alapértelmezés szerinti beállításokat fogadta el, akkor a Git Credential Manager alapértelmezés szerint engedélyezve van. A Git Credential Manager jelentősen leegyszerűsíti a hitelesítést, hiszen így nem szükséges majd előkeresnie a személyes hozzáférési tokent minden olyan alkalommal, amikor a hitelesített GitHub-kapcsolatot vagy a távoli kapcsolatot újraindítja.

1. Futtassa a **clone** parancsot a tárház nevének megadásával. A klónozás letölti (klónozza) az elágaztatott tárházat a helyi számítógépére. 

    > [!Tip]
    > Az elágazás GitHubos URL-címét úgy szerezheti meg egyszerűen, ha a GitHub webhelyen a **Clone or download** (Klónozás vagy letöltés) gombra kattint:
    >
    > ![Clone or download (Klónozás vagy letöltés)](./media/contribute-get-started-setup-local/clone-or-download.png)

    Ügyeljen rá, hogy a klónozási folyamat során a *saját elágazása* útvonalát adja meg, ne pedig a fő tárházért, amelyből az elágazást létrehozta. Ellenkező esetben nem fogja tudni közzétenni a módosításait. A saját elágazására a személyes GitHub-fiókján keresztül hivatkozhat, például: `github.com/<github-username>/<repo>`.

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    A klónozási parancsának az alábbihoz hasonlóan kell kinéznie:

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. Ha a rendszer kéri, adja meg a GitHubhoz használt hitelesítő adatait.

    ![GitHub – bejelentkezés](./media/contribute-get-started-setup-local/github-login.png)

3. Ha a rendszer kéri, adja meg a kéttényezős hitelesítő kódját.

    ![GitHub – kéttényezős hitelesítés](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > A bejelentkezési adatokat a rendszer menti, és a későbbiekben ezeket használja a GitHub-kérések hitelesítéséhez. Ezt a hitelesítést számítógépenként csak egyszer kell elvégeznie. 

4. Ekkor lefut a clone parancs, és letölti a tárház fájljainak egy példányát az Ön elágaztatott tárházából a helyi lemez egy új mappájába. Az új mappa az aktuális mappán belül jön létre. A művelet akár néhány percig is eltarthat, a tárház méretétől függően. Miután befejeződött, megnyithatja a mappát, és ellenőrizheti annak tartalmát.

## <a name="configure-remote-upstream"></a>A távoli felső tárház konfigurálása
Miután klónozta a tárházat, állítson be egy csak olvasható távoli kapcsolatot a fő tárházhoz **upstream** néven. Az upstream URL segítségével biztosíthatja, hogy a mások által végrehajtott módosítások mindig szinkronizálva legyenek a saját helyi tárházában is. Ezt a beállítást a **git remote** paranccsal tudja elvégezni. A **fetch** paranccsal frissítheti az ágadatokat az upstream tárházból.

1. Ha a **Git Credential Managert** használja, hajtsa végre az alábbi parancsokat: Cserélje a \<repo\> és az \<organization\> helyőrzőt a megfelelő értékre.
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. Tekintse meg a beállított értékeket, és győződjön meg róla, hogy az URL-ek helyesek. Az **origin** URL-eknek a személyes, elágaztatott tárházára kell mutatniuk. Az **upstream** URL-eknek a fő tárházra kell mutatniuk, például a MicrosoftDocs vagy az Azure tárházra. 
   ```bash
   git remote -v 
   ```

   Az alábbi példában láthatja a remote parancs kimenetét. Egy „MyGitAccount” nevű fiktív Git-fiókot konfiguráltunk személyes hozzáférési jogkivonattal az azure-docs tárház eléréséhez:
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. Ha nem megfelelő értéket állított be, eltávolíthatja azt a remote parancs ismételt futtatásával. Az upstream érték eltávolításához használja a `git remote remove upstream` parancsot.

## <a name="next-steps"></a>Következő lépések
- Ha szeretne többet megtudni a tartalmak hozzáadásáról és frissítéséről, folytassa a [GitHub-alapú közreműködést ismertető témakörrel](how-to-write-workflows-major.md).