---
title: Microsoft Docs-közreműködői útmutató – áttekintés
description: Ez az útmutató bemutatja, hogyan működhet közre a Microsoft dokumentációs webhelyén, a docs.microsoft.com-on.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 04/17/2018
ms.openlocfilehash: 94fad6f4b2faeefff687eb57cd2de8a0fb5bbbf3
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308893"
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Microsoft Docs-közreműködői útmutató – áttekintés

Üdvözöljük a [docs.microsoft.com](https://docs.microsoft.com) (más néven Docs) Közreműködői útmutatójában!!

A dokumentumkészleteink közül több nyílt forrású, és a GitHub üzemelteti. A Microsoftnál mindig egyre több csapat adaptálja ezt a modellt. Még a nem teljesen nyílt forrású dokumentumkészletek is rendelkeznek nyilvánosan elérhető adattárakkal, ahol lekéréses kérelmeket indíthat. Ez leegyszerűsíti és javítja a termékfejlesztő mérnökök, a tartalomkészítő csapatok és az ügyfelek közötti kommunikációt. A nyílt munkavégzésnek több előnye is van:

- A nyílt forrású adattáraknál a tervezés nyílt, hogy visszajelzést kapjanak, milyen dokumentumokra van a leginkább szükség.
- A nyílt forrású adattáraknál az áttekintés nyílt, hogy már az első kiadásban a leghasznosabb tartalom jelenhessen meg.
- Az nyílt forrású adattáraknál a frissítés nyílt, hogy egyszerűbb legyen a tartalom folyamatos javítása.

A [docs.microsoft.com](https://docs.microsoft.com) felhasználói felületén a [GitHub](https://github.com)-munkafolyamatok közvetlen integrációja ezt még egyszerűbbé teszi. Kezdje a [megtekintett dokumentum szerkesztésével](#quick-edits-to-existing-documents). Vagy segítsen [új témakörök áttekintésével](#review-open-prs) vagy [minőségi problémák jelentésével](#create-quality-issues).

> [!IMPORTANT]
> A docs.microsoft.com felületen közzétevő tárházak mindegyike elfogadta a [Microsoft nyílt forráskódra vonatkozó viselkedési szabályzatát](https://opensource.microsoft.com/codeofconduct/) vagy a [.NET Foundation viselkedési szabályzatát](https://dotnetfoundation.org/code-of-conduct). További információkért keresse fel a [Viselkedési szabályzattal kapcsolatos gyakori kérdések](https://opensource.microsoft.com/codeofconduct/faq/) oldalát, illetve elküldheti kérdéseit és észrevételeit az [opencode@microsoft.com](mailto:opencode@microsoft.com) vagy a [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) címre.<br>
>
> A nyilvános tárházakban publikált dokumentációhoz és kódmintákhoz beküldött kisebb javításokra vagy pontosításokra a [docs.microsoft.com használati feltételei](https://docs.microsoft.com/legal/termsofuse) vonatkoznak. Új vagy jelentős módosítások esetén a lekéréses kérelemben megjelenik egy megjegyzés, amely arra szólítja fel, hogy ha nem Microsoft-alkalmazott, akkor küldje be az online Közreműködői Licencszerződést (CLA). A lekéréses kérelmet csak akkor tekinthetjük át vagy fogadhatjuk el, ha előzőleg kitöltötte az online űrlapot.

## <a name="quick-edits-to-existing-documents"></a>Meglévő dokumentumok gyors szerkesztése

A gyors szerkesztésekkel leegyszerűsítő a jelentési folyamat, és javíthatók a dokumentum kisebb hibái és kihagyásai. Minden erőfeszítés ellenére kisebb nyelvtani vagy helyesírási hibák előfordulhatnak a közzétett dokumentumokban. Problémák jelzésével jelentheti a hibákat, de gyorsabb és egyszerűbb a probléma megoldásához lekéréses kérelmet (PR) létrehozni. Majdnem minden cikk mellett megjelenik a Szerkesztés gomb, amint az az alább ábrán látható. Ha rákattint a **Szerkesztés** (vagy más nyelven ugyanilyen) gombra, akkor megnyílik a forrásfájl a GitHubon.

![Az Edit (Szerkesztés) hivatkozás helye](./media/index/edit-article.png)

Ez után a cikk szerkesztéséhez kattintson a ceruza ikonra, amely a következő ábrán látható.

> [!NOTE]
> Ha a ceruza ikon kiszürkítve látható, akkor jelentkezzen be a GitHub-fiókjába, vagy hozzon létre egy új fiókot. Végezze el a módosításokat a webszerkesztőben. A módosítás formázásának ellenőrzéséhez rákattinthat a **Preview changes** (Módosítások előnézete) fülre.

![A ceruzaikon helye](./media/index/editicon.png)

Miután elvégezte a módosításokat görgessen a lap aljára. Adja meg a lekéréses kérelem címét és leírását, majd kattintson a **Propose file change** (Fájlmódosítás javasolása) elemre az alábbi ábrának megfelelően:

![módosítás javasolása](./media/index/submit-pull-request.png)

A módosításjavaslat után arra kell kérnie a tárház tulajdonosait, hogy „kérjék le” (angolul pull) a módosításokat a tárházukba. Ezt a lekéréses kérelem (angolul pull request) használatával teheti meg. Amikor a fenti **Fájlmódosítás javasolása** lehetősége kattintott, akkor az alábbi képen láthatóhoz hasonló oldalra került:

![lekéréses kérelem létrehozása](media/index/create-pull-request.png)

Kattintson a **Lekéréses kérelem létrehozása** lehetőségre, a lekéréses kérelemhez adjon meg egy címet (és ha szeretné, leírást is), majd kattintson újra a **Lekéréses kérelem létrehozása** elemre.

Ennyi az egész! A tartalomcsapat tagjai át fogják tekinteni és egyesíteni fogják a lekéréses kérelmet. Ha nagyobb módosításokat végzett változtatásokat kérő visszajelzést kaphat.

A GitHub szerkesztői felhasználói felülete az adattárban meglévő engedélyeinek megfelelő választ ad. Az előző képek olyan közreműködő esetén pontosak, akinek nincsenek írási jogosultságai a céladatbázisban. A GitHub automatikusan létrehoz egy adattármásolatot a céladattárról a fiókjában. Ha írási engedélye van a céladattárban, a GitHub létrehoz egy új ágat a céladattárban. Az ág nevének formátuma **\<GitHubAzonosító\>-javítás-n** a GitHub-azonosítót és egy számazonosítót használva a javítóághoz.

Minden módosításhoz lekéréses kérelmeket használunk, még az írási engedéllyel rendelkező közreműködőknél is. A legtöbb adattárban a `master` ág védett, ezért a frissítéseket lekéréses kérelemként kell beküldeni.

A böngészőn belüli szerkesztési környezet kisebb vagy ritka módosítások esetén a legjobb. Ha nagyobb terjedelmű szövegeket ír, vagy speciális Git-funkciókat (például ágkezelést vagy fejlett egyesítéskori ütközésfeloldást) használ, akkor [adattármásolatot kell készítenie, és a helyi számítógépen kell dolgoznia](how-to-write-workflows-major.md).

> [!NOTE]
> Ha ez a lehetőség engedélyezve van, akkor **bármilyen nyelvű** cikket módosíthat, és a szerkesztés típusától függően a következő történik majd:
> 1. minden jóváhagyott nyelvi módosítás hozzájárul a gépi fordítási motorunk fejlesztéséhez is
> 2. az olyan módosítások, amelyek jelentős mértékben megváltoztatják a cikk tartalmát, belsőleg lesznek kezelve, melynek során a módosítást ugyanannak a cikknek az angol nyelvű változatához is elküldjük, így az minden nyelvre lokalizálva lesz, ha a módosítást jóváhagyják.
> Így a javasolt módosítások nem csak a saját nyelvén, de minden elérhető nyelven is megjelennek, és javítják a cikkeket.

## <a name="review-open-prs"></a>Nyitott lekéréses kérelmek áttekintése

A jelenleg nyitott lekéréses kérelmek átnézésével elolvashatja az új témaköröket, még mielőtt közzétennék őket. Az áttekintések a [GitHub-folyamatot](https://guides.github.com/introduction/flow/) követik. Megtekintheti a javasolt frissítéseket és az új cikkeket a nyilvános adattárakban. Tekintse át őket, és fűzzön hozzájuk megjegyzéseket. Keresse fel bármelyik dokumentációs adattárunkat, majd tekintse meg a nyitott lekéréses kérelmeket az Önt érdeklő területeken. A javasolt frissítéseket illető közösségi visszajelzések az egész közösséget segítik.

## <a name="create-quality-issues"></a>Minőségi problémák jelzése

Dokumentumainkat folyamatosan fejlesztjük. A jelzett problémák segítenek, hogy erőfeszítéseinket a közösség számára legfontosabb dolgokra összpontosítsuk. Minél több részletet meg tud adni, annál nagyobb segítségünkre lesz a probléma. Mondja el, milyen információt keresett. Írja le a használt keresési kifejezéseket. Ha nem tudta megtenni az első lépéseket, mondja el, hogyan szeretné elkezdeni egy új technológia felfedezését.

A problémák jelzésével elindul a párbeszéd arról, hogy mire van szükség. A tartalomcsapat ezekre a jelzett problémákra a dokumentáció bővítésére vonatkozó ötletekkel fog válaszolni, és megkérdezi a véleményét. Vázlat létrehozásakor megkérjük, hogy [tekintse át a lekéréses kérelmet](#review-open-prs).

## <a name="get-more-involved"></a>Vegyen részt még több mindenben

Más témakörök segítenek, hogy termelékenyen hozzájárulhasson a Microsoft Docs tartalmainak bővítéséhez. Elmagyarázzák a Microsoft Docs platformon használt GitHub-tárházakkal, Markdown-eszközökkel és bővítményekkel való munkavégzést.
