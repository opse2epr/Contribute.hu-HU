---
title: 'A GitHub közreműködői munkafolyamata: kisebb vagy alkalmi módosítások'
description: Ez a cikk bemutatja, hogyan működhet közre a docs.microsoft.com cikkein a „kis” közreműködői munkafolyamat követésével.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 10/06/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 8bde44d502e1942b0870df9dd546a97705c2bb4f
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
---
# <a name="github-contribution-workflow-for-minor-or-infrequent-changes"></a>A GitHub közreműködői munkafolyamata: kisebb vagy alkalmi módosítások

> [!IMPORTANT]
> A docs.microsoft.com felületen közzétételt végző tárházak mindegyike elfogadta a [Microsoft nyílt forráskódra vonatkozó viselkedési szabályzatát](https://opensource.microsoft.com/codeofconduct/) vagy a [.NET Foundation viselkedési szabályzatát](https://dotnetfoundation.org/code-of-conduct). További információkért keresse fel a [Viselkedési szabályzattal kapcsolatos gyakori kérdések](https://opensource.microsoft.com/codeofconduct/faq/) oldalát, illetve elküldheti kérdéseit és észrevételeit az [opencode@microsoft.com](mailto:opencode@microsoft.com) vagy a [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) címre.<br>
>
> A nyilvános tárházakban publikált dokumentációhoz és kódmintákhoz beküldött kisebb javításokra vagy pontosításokra a [docs.microsoft.com használati feltételei](https://docs.microsoft.com/legal/termsofuse) vonatkoznak. Új vagy jelentős módosítások esetén a lekéréses kérelemben megjelenik egy megjegyzés, amely arra szólítja fel, hogy ha nem Microsoft-alkalmazott, akkor küldje be az online Közreműködői Licencszerződést (CLA). A pull-kérelmet csak akkor fogadhatjuk el, ha előzőleg kitöltötte az online űrlapot.

## <a name="overview"></a>Áttekintés

Ez a munkafolyamat a GitHub webalapú Markdown-szerkesztőjével végzett kisebb vagy alkalmi módosításokhoz alkalmas. Mivel a felhasználói felület nem minden Git-műveletet és szerzői forgatókönyvet támogat, a GitHub szerkesztője korlátozottan használható. Ha nagyobb terjedelmű szövegeket kell írnia, vagy támogatást igényel a GitHub speciális funkcióihoz (mint amilyen például az elágaztatáskezelés, vagy az ütközések feloldásának haladó szintű egyesítése), tekintse meg a [nagyobb vagy hosszan futó módosítások munkafolyamatának](full-workflow.md) leírását.

## <a name="procedure-for-using-the-github-editor-to-propose-your-changes"></a>Módosítási javaslat beküldése a GitHub-szerkesztő használatával

1. Tallózással keresse meg a cikkhez tartozó GitHub-tárházat és Markdown-fájlt. Az alábbi módszerek bármelyikét használhatja:

   - Keresse meg a cikket a kapcsolódó GitHub-tárházban, a Markdown-fájlok között tallózva.
   - Keresse meg a cikket a [https://docs.microsoft.com/](https://docs.microsoft.com/) webhelyen, és kattintson a jobb felső sarokban látható **Edit** (Szerkesztés) hivatkozásra.

     ![Az Edit (Szerkesztés) hivatkozás helye](./media/light-workflow/contributetogit.png)

2. Az **Edit this file** (Fájl szerkesztése) ceruzaikonra kattintva váltson szerkesztőmódra:

    ![A ceruzaikon helye](./media/light-workflow/editicon.png)

3. A Markdown használatával hajtsa végre a módosításokat az **Edit file** (Fájl szerkesztése) lapon, majd a **Preview changes** (Módosítások előnézetének megtekintése) lapon ellenőrizze az eredményt. A szerkesztő használata viszonylag egyszerű, de ha segítségre van szüksége, tekintse meg az alábbi útmutatókat:

   - [A Markdown használata](how-to-write-use-markdown.md)
   - [Fájlok létrehozása a GitHubon](https://github.com/blog/1327-creating-files-on-github)
   - [Fájlok feltöltése a tárházakba](https://github.com/blog/2105-upload-files-to-your-repositories)

4. Görgessen a lap aljára, ahol a következő lehetőségek egyikét találja:

   - **Propose file change** (Javaslat fájl cseréjére): akkor jelenik meg, ha csak olvasási hozzáférése van a tárházhoz, például [Editing files in another user's repository](https://help.github.com/articles/editing-files-in-another-user-s-repository/) (Fájlok szerkesztése más felhasználó tárházában). Ebben az esetben a GitHub létrehoz egy javítást a tárházbeli elágazáshoz (és automatikusan létrehoz egy elágazást, ha még nem létezik). Miután a **Propose file change** elemre kattint, egy **Comparing changes** (Módosítások összehasonlítása) oldal jelenik meg, ahol ellenőrizheti a módosításokat. Ezután a **Create pull request** (Pull-kérelem létrehozása) gombra kattintva küldje el a módosításokat a pull-kérelmek várólistájára, majd lépjen tovább a [következő szakaszra](#pull-request-processing).

   - **Commit changes** (Módosítások véglegesítése): akkor jelenik meg, ha írási engedéllyel rendelkezik a tárházhoz, például [Editing files in your own repository](https://help.github.com/articles/editing-files-in-your-repository/) (Fájlok szerkesztése saját tárházban). Ebben az esetben a GitHub két lehetőséget kínál fel a módosítások mentéséhez:

     - **Commit directly to the `<branch-name>` branch** (Véglegesítés közvetlenül a `<branch-name>` ágra), ahol a `<branch-name>` annak az ágnak a neve, amelyiken az **Edit** (Szerkesztés) gombra való kattintáskor tartózkodott. Ez a művelet pull-kérelem indítása helyett közvetlenül az ágra alkalmazza a módosításokat. És már kész is van!

     - A **Create a new branch for this commit and start a pull request** (Új ág létrehozása a véglegesítéshez és pull-kérelem indítása) lehetőség egy alapértelmezett név felkínálásával új ág létrehozására szólít fel. Miután a **Propose file change** elemre kattint, egy **Comparing changes** (Módosítások összehasonlítása) oldal jelenik meg, ahol ellenőrizheti a módosításokat. Ezután a **Create pull request** (Pull-kérelem létrehozása) gombra kattintva küldje el a módosításokat a pull-kérelmek várólistájára, majd lépjen tovább a [következő szakaszra](#pull-request-processing).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Következő lépések

- A Markdownnal, a Markdown-bővítmények szintaxisával stb. kapcsolatosan olvassa el a szövegírás alapjaival foglalkozó cikkeket.
