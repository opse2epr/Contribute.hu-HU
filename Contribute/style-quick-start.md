---
title: Docs stíluskalauz – gyorsútmutató
description: Ez a cikk röviden összefoglalja a stílusra vonatkozó legfontosabb megfontolásokat a docs.microsoft.com-on való közreműködés megkezdéséhez.
ms.date: 07/25/2017
ms.openlocfilehash: f5c32d3fb71ef3513c68b9c506c823997bfe4d8f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805582"
---
# <a name="docs-style-and-voice-quick-start"></a>Docs-stílus és hangvétel – gyorsútmutató

Ez a gyorsútmutató röviden bemutatja, hogyan lehet műszaki tartalmat írni a docs.microsoft.com webhelyen való publikáláshoz. Az itt ismertetett irányelvek egyaránt vonatkoznak új dokumentumok létrehozására és létező dokumentumok frissítésére.

Ajánlott eljárások:

- Ellenőrizze a cikkek helyesírását és nyelvtani helyességét, akár úgy is, hogy átmásolja a szöveget a Microsoft Wordbe.
- Használjon kötetlen, barátságos hangnemet, mintha kettesben beszélgetne valakivel.
- Használjon egyszerű mondatokat. A könnyen olvasható szövegnek köszönhetően az olvasó azonnal használhatja is az útmutatásokat.

## <a name="use-the-microsoft-voice-principles"></a>A Microsoft hangvételre vonatkozó alapelveinek betartása

Ezeket az alapelveket tartjuk szem előtt, amikor technikai szövegeket írunk a [docs.microsoft.com](https://docs.microsoft.com) számára. Talán nem mindig járunk sikerrel, de törekednünk kell rá!

- **A szándék legyen a középpontban**: Az ügyfelek adott céllal fordulnak a dokumentációnkhoz. Mielőtt hozzákezd az íráshoz, határozza meg világosan, ki az ügyfél, és milyen feladatot próbál végrehajtani. Ezt követően írja meg úgy a cikket, hogy ennek a bizonyos ügyfélnek segítsen végrehajtani az adott feladatot.
- **Használjon köznapi szavakat**: Törekedjen a természetes nyelv és az ügyfelek által ismert szavak használatára. Ne legyen túl hivatalos, de maradjon szakszerű. Az új fogalmakat példákkal világítsa meg.
- **Fogalmazzon tömören**: Kerülje a dagályosságot. Használjon állító mondatokat, kerülje a fölösleges szavakat és jelzőket. Használjon rövid és tömör mondatokat. Ne térjen el a cikk témájától. Ha a feladatnak van egy kulcsfontosságú jellemzője, ez kerüljön a mondat vagy bekezdés elejére. A lehető legkevesebb jegyzetet csatolja a szöveghez. Használjon képernyőképet, ha ezzel szöveget takaríthat meg.
- **Tegye a cikket áttekinthetővé**: A legfontosabb témák kerüljenek előre. Használjon szakaszokat a hosszú eljárások lépéseinek egyszerűbben kezelhető csoportokba rendezéséhez. (A több, mint 12 lépésből álló eljárások valószínűleg túl hosszúak.) Használjon képernyőképet, ha ez világosabbá teszi a mondanivalót.
- **Mutasson együttérzést**: A cikk hangvétele legyen támogató, és ne tartalmazzon a szükségesnél több, felelősséget kizáró nyilatkozatot. Őszintén nevezze meg az ügyfelek számára nehézséget jelentő területeket. Ügyeljen rá, hogy a cikk az ügyfél által keresett válaszra összpontosítson, és ne csupán technikai jellegű oktatóanyag legyen.

## <a name="consider-localization-and-machine-translation"></a>A honosítás és a gépi fordítás szempontjainak figyelembevétele

Technikai témájú cikkeinket több nyelvre lefordítják, némelyiket módosítják is bizonyos piacok és földrajzi területek számára. A felhasználók a cikkek elolvasásához a weben található gépi fordításokat is igénybe vehetik. Erre való tekintettel az írásnál vegye figyelembe a következő szempontokat:

- **Ügyeljen rá, hogy a cikkben ne legyen nyelvtani, helyesírási és központozási hiba**: Erre egyébként is törekedni kell. Egyes Markdown-szerkesztők, mint a Markdown Pad 2.0, rendelkeznek alapszintű helyesírás-ellenőrzővel, de a javasolt eljárás szerint a cikkben szereplő (megjeleníthető HTML-formátumú) tartalmat érdemes beilleszteni a robusztusabb helyesírás- és nyelvtani ellenőrzőeszközzel rendelkező Wordbe.
- **Használjon minél rövidebb mondatokat**: Az összetett mondatok és a többszörös szószerkezetek megnehezítik a fordítást. Bontsa szét a mondatokat, ha ez nem eredményez felesleges ismétléseket vagy szokatlan megfogalmazást. Nem látjuk szívesen a mesterkélt stílusú cikkeket sem.
- **Használjon egyszerű és következetes mondatszerkezetet**: A következetes szerkezet alkalmasabb a fordításra. Kerülje a zárójelezést és a közbeékelt mellékmondatokat, az alanyt helyezze minél közelebb a mondat elejéhez. Olvasson el néhány közzétett cikket. Ha a cikk rövid, olvasmányos stílusú, használja követendő példaként.
- **Legyen következetes a szavak és a kis- és nagybetűk használatában**: Itt is a következetesség a fontos. Csak a mondat elején és a tulajdonneveknél használjon nagybetűt.
- **Ne hagyja ki a „kisebb szavakat”**: Az angol nyelvű szövegkörnyezetbe automatikusan beleértett, jelentéktelennek tartott szavak (mint például az „a”, „the”, „that” vagy „is”) nélkülözhetetlenek a gépi fordítás számára, így feltétlenül foglalja bele őket a szövegbe.

## <a name="other-style-and-voice-issues-to-watch-for"></a>Stílussal és hangvétellel kapcsolatos egyéb fontos problémák

- Ne törje meg az egyes lépéseket megjegyzésekkel vagy közbeékelt mellékmondatokkal.
- A kódtöredékeket tartalmazó lépésekhez megjegyzések formájában adja hozzá a kiegészítő információt. Ez csökkenti az átolvasandó szöveg terjedelmét. A kódprojektbe bemásolt kulcsinformáció emlékezteti a kód működésére azokat, akik később hivatkoznak rá.
- Használjon nagybetűzést minden címben és fejlécben.
- A „bejelentkezés” kifejezésre a „log-in” helyett a „sign-in” alakot használja.
- További irányelvekért lásd a [ Microsoft írásstílusra vonatkozó útmutatóját](https://docs.microsoft.com/style-guide/welcome).

## <a name="localized-documentation"></a>Honosított dokumentáció

- Ha honosított dokumentációban működik közre, használja a [Microsoft Language Portalt](https://www.microsoft.com/Language/Default.aspx).
- A honosítási stíluskalauzok, a technikai publikációk stílusára és nyelvhasználatára vonatkozó információk, valamint az adott piacokon érvényes adatformátumok a célnyelven letölthető [Stíluskalauzban](https://www.microsoft.com/Language/StyleGuides) érhetők el.
- A honosított Microsoft-terminológiát keresse a [termékspecifikus jóváhagyott terminológiát](https://www.microsoft.com/Language/Default.aspx) tartalmazó oldalon, vagy töltse le a [Microsoft terminológiai gyűjteményét](https://www.microsoft.com/language/Terminology) a célnyelven.
- A honosításról részletesen a [Microsoft írásstílusra vonatkozó útmutatójának](https://docs.microsoft.com/style-guide/global-communications) globális kommunikációról szóló szakaszában olvashat.
