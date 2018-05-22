---
title: GitHub-közreműködői munkafolyamat nagyobb vagy hosszú távú módosításokhoz
description: Ez a cikk bemutatja, hogyan működhet közre a docs.microsoft.com cikkein a „nagy” közreműködői munkafolyamat követésével.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 08/30/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: e26b62923eed22d5b2005b1d84dc4ae240d262b1
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2018
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>GitHub-közreműködői munkafolyamat nagyobb vagy hosszú távú módosításokhoz

> [!IMPORTANT]
> A docs.microsoft.com felületen közzétételt végző tárházak mindegyike elfogadta a [Microsoft nyílt forráskódra vonatkozó viselkedési szabályzatát](https://opensource.microsoft.com/codeofconduct/) vagy a [.NET Foundation viselkedési szabályzatát](https://dotnetfoundation.org/code-of-conduct). További információkért keresse fel a [Viselkedési szabályzattal kapcsolatos gyakori kérdések](https://opensource.microsoft.com/codeofconduct/faq/) oldalát, illetve elküldheti kérdéseit és észrevételeit az [opencode@microsoft.com](mailto:opencode@microsoft.com) vagy a [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) címre.<br>
>
> A nyilvános tárházakban publikált dokumentációhoz és kódmintákhoz beküldött kisebb javításokra vagy pontosításokra a [docs.microsoft.com használati feltételei](https://docs.microsoft.com/legal/termsofuse) vonatkoznak. Új vagy jelentős módosítások esetén a lekéréses kérelemben megjelenik egy megjegyzés, amely arra szólítja fel, hogy ha nem Microsoft-alkalmazott, akkor küldje be az online Közreműködői Licencszerződést (CLA). A lekéréses kérelme csak akkor dolgozható fel, ha előzőleg kitöltötte az online űrlapot.

## <a name="overview"></a>Áttekintés

Ez a munkafolyamat olyan közreműködők számára alkalmas, akiknek nagyobb módosítást kell végeznie, vagy egy tárház rendszeres közreműködői lesznek. A rendszeres közreműködők általában folyamatos vagy hosszú távú módosításokat végeznek, amelyek több összeállítási, ellenőrzési és előkészítési cikluson is keresztülmennek, esetleg több napon át tartanak a lekéréses kérelem jóváhagyása és egyesítése előtt.

Ilyen típusú közreműködések többek között az alábbiak:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>Terminológia

Mindenekelőtt tekintse át a Git/GitHub néhány, a munkafolyamatban használt szaknyelvi és zsargonkifejezését. Nem elengedhetetlen, hogy most rögtön megértse őket. Elég tudnia, hogy meg fog ismerkedni velük, és ha ellenőriznie kell egy meghatározást, mindig visszatérhet ehhez a szakaszhoz.

| Név | Leírás |
|-----------|-------------|
|elágazás (fork)|Általában főnévként használják, egy fő GitHub-tárház másolatát értve alatta. Egy elágazás a gyakorlatban nem más, mint egy újabb tárház. Mégis különleges abban az értelemben, hogy a GitHub fenntartja annak kapcsolatát a fő/szülőtárházzal. Igeként is használják, a következő példához hasonlóan: „Először el kell ágaztatnia a tárházat.”.|
|távoli (remote)|Névvel rendelkező kapcsolat egy távoli tárházzal, amilyen a „forrás” vagy a „felső”. A Git azért nevezi ezeket távoliaknak, mert egy másik számítógépen üzemeltetett tárházra való hivatkozásra használják őket. Ebben a munkafolyamatban a távoli mindig GitHub-tárházat jelent.|
|forrás (origin)|Annak a kapcsolatnak a neve, amely a helyi tárház és azon tárház között áll fenn, amelyből azt klónozták. Ebben a munkafolyamatban a forrás mindig az elágazással való kapcsolatot jelenti. Előfordul, hogy magát a forrástárházat értik alatta, például a következőképpen: „Ne felejtse el leküldeni a változásokat a forrásba”.|
|felső (upstream)|A forrás távoli kapcsolathoz hasonlóan a felső is névvel rendelkező kapcsolatot jelent egy másik tárházzal. Ebben a munkafolyamatban a felső a helyi tárház és azon fő tárház közötti kapcsolatot jelenti, amelyből az elágazást létrehozták. Előfordul, hogy magát az felső tárházat értik alatta, például a következőképpen: „Ne felejtse el lekérni a változásokat a felsőből”.|

## <a name="workflow"></a>Munkafolyamat

>[!IMPORTANT]
> Ha még nem tette meg, akkor végre kell hajtania a [Beállítás](get-started-setup-github.md) szakaszban leírt lépéseket. Ez a szakasz végigvezeti a GitHub-fiók beállításán, a Git Bash és egy Markdown-szerkesztő telepítésén, egy elágazás létrehozásán és a helyi tárház kialakításán. Ha nincs tisztában a Git és a GitHub olyan fogalmaival, mint például a tárház vagy az ágak, akkor először tekintse át a [Git and GitHub fundamentals](git-github-fundamentals.md) (A Git és a GitHub alapjai) című cikket.

Ebben a munkafolyamatban a módosítások ismétlődő ciklusban zajlanak. Az eszköz helyi tárházából kiindulva haladnak vissza felfelé a GitHub-elágazáson a fő GitHub-tárházba, majd ismét lefelé helyben, amikor beépíti a más közreműködőktől származó változásokat.

### <a name="use-github-flow"></a>A GitHub-folyamat használata

Idézze fel a [Git and GitHub fundamentals](git-github-fundamentals.md#git) (A Git és a GitHub alapjai) című cikkből, hogy egy Git-tárház egy főágat (master branch) és az összes folyamatban lévő, a főágba be nem integrált munkaágat tartalmazza. Logikailag összefüggő változások alkalmazásakor mindig ajánlott létrehozni egy *munkaágat* a változásoknak az egész munkafolyamaton át tartó kezelésére. Azért nevezzük munkaágnak, mert ez az a munkaterület, ahol a változások iterálása és finomítása zajlik, amíg azok nem integrálhatók újra a főágba.

Az összefüggő változások egy adott ágba való elkülönítése lehetővé teszi a változások független irányítását és bevezetését, előirányozva őket a közzétételi ciklus egy megadott időpontjára. A valóságban a végzett munka típusától függően könnyen megtörténhet, hogy több munkaág is lesz a tárházában. Nem ritka, hogy egyszerre több munkaágon folyik munkavégzés úgy, hogy mindegyik más projekthez tartozik.

>[!TIP]
>A változások a főágban való bevezetése *nem* ajánlott gyakorlat. Tegyük fel, hogy a főágat használta egy funkció időzített kibocsátásához tartozó változáskészlet bevezetésére. Végzett a változtatásokkal, és a kibocsátásukra várt. Eközben sürgős hibajavítási kérést kapott, ezért végrehajtotta a változtatást a főág egy fájljában, és közzétette a változást. Ebben a példában szándéka ellenére közzétette a javítást *és* azt a változást is, amelynek kibocsátását egy adott időpontig vissza kívánta tartani.

Most hozzunk létre új munkaágat a helyi tárházban a javasolt változások rögzítésére. Minden Git-ügyfél más és más, ezért tanulmányozza a preferált ügyfél súgóját. A folyamat áttekintését a [GitHub-folyamatra](https://guides.github.com/introduction/flow/) vonatkozó GitHub-útmutatóban találhatja meg.

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Következő lépések

Ennyi az egész! Közreműködött a docs.microsoft.com tartalmának készítésében!

- Az olyan témák jobb megismeréséhez, mint a Markdown vagy a Markdown-bővítmények szintaxisa, olvassa el a szövegírás alapjaival foglalkozó szakaszt.
