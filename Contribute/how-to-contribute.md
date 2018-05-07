---
title: Hogyan működhet közre a docs.microsoft.com-tartalomban
description: Ez a cikk bemutatja, hogy milyen különböző módokon küldhet be tartalmat közreműködőként a docs.microsoft.com webhelyre.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 01/17/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: bc6f9c314eda5f0d950da049374a7a157f16782a
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-contribute-to-docsmicrosoftcom"></a>Hogyan működhet közre a docs.microsoft.com-tartalomban

Számos módon hozzájárulhat ahhoz, hogy a [docs.microsoft.com](https://docs.microsoft.com) tartalma egyre jobb legyen:

- [Téma létrehozásával](#create-issues) új cikket ajánlhat, vagy javíthatja a már meglévő cikkeket.
- [Gyors szerkesztéssel](#quick-edits) kisebb mértékben módosíthatja a cikkeket a GitHub online szerkesztőjében.
- [Lektorálhatja az új cikkek vázlatát](#review-new-articles) a megfelelő minőség és a technikai pontosság érdekében.
- [Új cikkeket hozhat létre](#create-new-articles) az egyes témákban, ha a tartalomhoz kíván hozzájárulni.
- Mintákat [frissíthet](#update-samples) vagy [hozhat létre](#create-samples) a fontos fogalmakat illusztráló kódminták javításához.

Ez a cikk leírja a közreműködés különböző módjait és az egyes konkrét feladatok elvégzését a részletesebb információkhoz mutató hivatkozások segítségével.

Minden nyilvános tárházunk a [GitHubon](https://wwww.GitHub.com) található.  A dokumentációs tárházakban való részvételhez fiókot kell létrehoznia a GitHubon.

Szövegszerkesztőre is szüksége lesz a dokumentumok frissítéséhez. A [Visual Studio Code](https://www.visualstudio.com/code) használatát javasoljuk. Alapfokon ismernie kell a [Markdown](https://daringfireball.net/projects/markdown/syntax) szintaxisát.

Minták hozzáadása vagy módosítása esetén fejlesztői környezetre lesz szüksége. Minden platformhoz a [Visual Studio Code](https://www.visualstudio.com/code), illetve PC és Mac esetén a [Visual Studio](https://www.visualstudio.com) használatát javasoljuk.

## <a name="create-issues"></a>Téma létrehozása

Ha egy cikkben hiányt vagy pontatlanságot talál, hozzon létre témát a probléma jelentésére. A pontos helyet úgy találja meg legkönnyebben, ha a böngészőben a „Szerkesztés” gombra kattintva eljut a cikk forrásához a megfelelő nyilvános GitHub-tárházban. Itt a címsorban megtalálhatja a cikk forrásának URL-címét. Kattintson a "Create Issue" elemre a téma létrehozásához.

> [!NOTE]
> Kis javítással helyrehozható, például helyesírási vagy nyelvtani hibák esetén időt takaríthat meg magának és nekünk, ha a forrást a böngészőben szerkeszti, és [így küldi be a javítást](#quick-edits).

A legtöbb nyilvános tárhelyünkön sablonok találhatók az új témákhoz a javításhoz szükséges információkkal.

De ha nem talál ilyen információt, akkor is megfogalmazhatja az új témákat. A folyamat ugyanaz: új téma létrehozása az egyik nyilvános docs-tárhelyen. Mondja el nekünk, mit keresett, mit kívánt tenni, és miért találta úgy, hogy a szóban forgó cikk nem adta meg a várt segítséget.

## <a name="review-new-articles"></a>Új cikkek lektorálása

Ha Ön új, esetleg CTP (közösségi technológiai előzetes) vagy bétaverziós szoftveren dolgozik, számítson rá, hogy a dokumentációt valószínűleg a fejlesztéssel párhuzamosan építjük. A készülőben lévő dokumentáció megtalálható a nyilvános tárházainkban. Ha észrevétele van, már a cikkek közzététele előtt segíthet a javításban.

Az új cikkek nyilvánosan lektorálhatók a [GitHub-folyamat](https://guides.github.com/introduction/flow/) segítségével. Keresse fel bármelyik dokumentációs tárházunkat, majd tekintse meg a nyitott lekéréses kérelmeket. Minden nyitott lekéréses kérelemhez szívesen látjuk az észrevételeket és a kritikákat. Ez segít abban, hogy már eleve jobb tartalmat tegyünk közzé ahelyett, hogy utólagos visszajelzésekre várnánk.

Igyekszünk többféleképpen javítani a technikai pontosságot, a leírások érthetőségét és a nyelvtani helyességet.

## <a name="quick-edits"></a>Gyors szerkesztés

A gyors szerkesztéssel kisebb javításokat végezhet a böngészőalapú szerkesztőben. Ha apróbb helyesírási vagy nyelvtani hibát, esetleg téves API-nevet talál, szerkesztéssel és lekéréses kérelem beküldésével jelezheti a problémát.

Bármely cikk szerkesztéséhez kattinthat az „Edit” (Szerkesztés) gombra (általában az oldal jobb felső sarkában), a beküldéshez pedig használhatja a „Submit PR” (lekéréses kérelem beküldése) gombot a lap alján. A napi ellenőrzés során megvizsgáljuk a kérelmet és elvégezzük a dokumentum egyesítését.

## <a name="create-new-articles"></a>Új cikk létrehozása

Ha vannak olyan izgalmas témák, amelyeket szívesen magyarázna el másoknak, Ön is létrehozhat új cikkeket, és beküldhet lekéréses kérelmeket.

Az új cikkek megírása időigényes feladat, és mi nagyra értékeljük az idejét és a hozzájárulását. Szeretnénk már a folyamat elején bekapcsolódni, hogy kezdettől fogva teljesüljenek az irányelvek és a stílusra vonatkozó követelmények. A következő lépéseket javasoljuk:

1. [Hozzon létre egy témát](#create-issues), írja le, mit hiányol, és hogyan szeretné megoldani.
1. Írja le a problémát és hogy szívesen dolgozna rajta, javasoljon vázlatot, és készítsen egy rövid összefoglalót.
1. Válaszunkban elküldjük a javaslatainkat. Ez tartalmazhat kapcsolódó cikkekre mutató hivatkozásokat és mintákra, valamint a cikk lehetséges felépítésére vonatkozó javaslatokat.
1. Miután megegyeztünk a vázlatban, leágaztathatja a tárházat, és megkezdheti a munkát.
1. A folyamat elején nyisson meg egy lekéréses kérelmet, amelynek a címe a „[WIP]" előtaggal kezdődik.
1. Ezt követően megkapja az első visszajelzést az egyik főmunkatársunktól.
1. Folytassa a munkát, és ha készen áll a további visszajelzésekre, @-mention segítségével jelölje meg az első vázlatot ellenőrző személyt.
1. Ha készen áll a végső lektorálásra, távolítsa el a „[WIP]" előtagot.
1. Válaszoljon a visszajelzésre.
1. Főmunkatársaink egyesíteni fogják a lekéréses kérelmet.

A listából érdemes részletezni néhány pontot. A cikkek minél gyorsabb lektorálásához általában a [GitHub-munkafolyamatot](https://guides.github.com/introduction/flow/) használjuk. Így tudjuk egyeztetni, hogy a cikk hova kerüljön a tartalomjegyzékben, milyen segítséget kaphat belőle az olvasó, és mire vonatkoznak a létrehozott minták. A munkamenet szükséges korrekcióit már akkor végrehajthatjuk, amikor még nem fordított rá túl sok időt.

## <a name="update-samples"></a>Minták frissítése

Egyes minták több kiadással ezelőtt készülhettek, és a használatuk ma már nem javasolt. Érdemes segítenie az ilyen elavult minták frissítésében. Más esetekben úgy találhatja, hogy egy változónév egyszerű módosítása világosabbá teheti a magyarázatot.

A cikkekben feltüntetett kódminták a Microsoft folyamatos integrációs (CI-) rendszerében fejlesztett, és gyakran ugyanitt tesztelt programokhoz tartoznak.

Kisebb frissítésekhez megkeresheti a forrást a megfelelő tárhelyen, majd a böngészőben módosíthatja a kódot, és beküldheti a lekéréses kérelmet. Miután a CI-rendszer végrehajtotta a változásokat, egyesítjük a lekéréses kérelmet.

Nagyobb mértékű módosítások esetén ágaztassa el a tárházat, és hajtsa végre a változtatást a kedvenc fejlesztői környezetében. Gondoskodjon a tesztelésről is, hogy a módosítások a szándékának megfelelően működjenek. Küldje be a lekéréses kérelmet ellenőrzésre.

Kód módosítása esetén mindig igazodjon a módosítani kívánt kód meglévő konvencióihoz. Mintatáraink kódolási szabványai megegyeznek a kapcsolódó termék munkacsoportja által használtakkal. A konkrét útmutatókat keresse az egyes tárházakban.

> [!NOTE]
> Mi magunk is ezeket az útmutatókat igyekszünk követni. Egyes mintáink még a jelenlegi szabványok előtt születtek, és nem frissültek mostanáig. Folyamatosan dolgozunk azon, hogy minden megjelenített kódmintánk működő és tesztelt mintákon alapuljon.

## <a name="create-samples"></a>Minták létrehozása

Az egyes fogalmak és helyzetek illusztrálására új mintákat is létrehozhat. Minden mintához cikket kell mellékelni, amely tartalmazza a mintára vonatkozó alapvető információkat.

Ha az új minta egy már meglévő cikket egészít ki, adjon hozzá hivatkozást a cikkben. Ha nincs még ilyen cikk, működjön együtt velünk, és [írja meg a cikket](#create-new-articles) a kód mellékleteként.

Mintáink kódolási szabványai minden esetben megegyeznek a kapcsolódó termék munkacsoportja által használtakkal. Kivételt jelent, ha a jobb érthetőség érdekében előnyben részesítjük az explicit módon beírt változókat az implicit (`var` segítségével deklarált) módon beírtakkal szemben, mert a deklarációk szerepelnek a cikkben.

Kövesse a fentebb leírt, [új cikkekre](#create-new-articles) vonatkozó mintafolyamatot, hogy a kódot már a fejlesztés korai szakaszában ellenőrizhessük.
