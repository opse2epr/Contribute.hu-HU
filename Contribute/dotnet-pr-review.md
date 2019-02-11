---
title: .NET-dokumentumok lekéréses kérelmei elbírálásának folyamata
description: A .NET-dokumentumok esetében a PR Merger webhookok nincsenek engedélyezve. Ez a cikk a lekéréses kérelmek ilyen tárházak esetén használt folyamatát ismerteti
ms.date: 01/-4/2019
ms.openlocfilehash: d8f35e328beffcbd5bac9f0f7313d8127fbeffb0
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713568"
---
# <a name="pull-request-review-process-for-the-net-docs-repositories"></a>Lekéréses kérelem elbírálásának folyamata .NET-dokumentumtárak esetén

A PR Merger webhookok számos tárház esetében nincsenek engedélyezve, ami automatikusan egyesíti a kisebb lekéréses kérelmeket. Ez a cikk a lekéréses kérelmek ilyen tárházak esetén használt elbírálási folyamatát ismerteti. A lekéréses kérelmek elbírálási folyamata a következő célok szem előtt tartásával lett megtervezve:

1. A csapattól, a terméktámogatási csapat és a közösség tagjaitól származó kiváló minőségű tartalom közzététele.
1. Esedékes, gyakorlatban hasznosítható visszajelzés következetes biztosítása a szerzőknek.
1. A szerzők és az elbírálók közötti párbeszéd fenntartása.

A csapatok újításaival és a platform érésével a folyamat tovább fejlődik.

## <a name="reviewers"></a>Elbírálók

A tartalomért felelős csapat tagjainak egyike minden lekéréses kérelmet elbírál. A technikai pontosság érdekében a tartalomért felelős csapat tagjai kikérhetik az adott terméket támogató csapat tagjainak véleményét. A tartalomért felelős csapat a GitHub Code Ownership (kód tulajdonjoga) funkcióját használva automatikusan kéri tagjaitól az elbírálást. Ennek a folyamatnak a részeként az elbírálók más csapattagokat is megjelölhetnek a belső lekéréses kérelmek véleményezésére. A csapat tagjai ugyanabban a várakozási sorban látják a csapattagok és a közösség tagjai által benyújtott elbírálási kérelmeket.

A közösség tagjai is véleményezhetnek lekéréses kérelmeket, és küldhetnek visszajelzést. A tartalomért felelős csapat legalább egy tagjának azonban minden lekéréses kérelmet jóvá kell hagynia az egyesítés előtt.

## <a name="review-process"></a>Az elbírálás folyamata

Az elbírálás a lekéréses kérelem alapján háromféle módon történhet:

- **Kis lekéréses kérelem** – A kis lekéréses kérelmek egyszerű hibák, elírások és érvénytelen hivatkozások javításai vagy kisebb kódmódosítások vagy más változtatások.
- **Jelentős közreműködés** – A jelentős közreműködés meglévő cikk lényeges módosítását, új cikket vagy több cikk módosítását jelenti.
- **Folyamatban** – A szerzők a címében elhelyezett „[WIP]” címkével megnyitott lekéréses kérelemmel kérhetik egy folyamatban lévő munka elbírálását. A „WIP” betűszó jelentése „Work in Progress” (munka folyamatban). 

A Közreműködői licencszerződés (CLA) robot által használt eljárás jól szemlélteti a „kis” és „nagy” közreműködés közötti különbséget. Azok a lekéréses kérelmek, amelyekhez nem kell aláírni a közreműködői licencszerződést (CLA) valószínűleg „kicsik”. A CLA-t megkövetelő lekéréses kérelmek valószínűleg „nagyok”.

### <a name="small-prs"></a>Kis lekéréses kérelmek

A kis lekéréses kérelmek pontossága lesz elbírálva, a bírálati helyen lévő build használatával. Mivel kicsik, ezek a lekéréses kérelmek nem járnak együtt a teljes cikk elbírálásával. 

Az elbírálók felfigyelhetnek egyéb apró módosításokra, amelyek javítanának a cikken. Ha ezek a módosítások is kicsik, akkor bírálati megjegyzés formájában tesznek rájuk javaslatot. Ha a javasolt módosítások nagyobb elbírálást vonnának maguk után, akkor később kezelendő ügyként nyitják meg. 

### <a name="larger-changes"></a>Nagyobb módosítások

A nagyobb lekéréses kérelmek alaposabb elbíráláson mennek keresztül. A következőket ellenőrzik:

- A lekéréses kérelemnek kódmintát is kell tartalmaznia forrásnyelven és letölthető tömörített fájlként.
- A kódminta fordítása sikeres és helyesen fut.
- A cikk egyértelműen ismerteti az olvasóval a célokat, és azokat el is éri.
- A cikk eleget tesz a [stílusbeli és nyelvtani irányelveknek](dotnet-style-guide.md), és követi [a szöveg hangnemére vonatkozó alapelveinket](dotnet-voice-tone.md).
- Minden hivatkozásnak megfelelően meg kell nyílnia.

A tartalomért felelős csapat tagjai elbírálják a lekéréses kérelmet, és a bírálatot megjegyzésekkel ellátva nyújtják be. Ha csak kisebb módosításokat kérnek, akkor a csapat tagjai a visszajelzésekkel együtt „jóváhagyhatják” a lekéréses kérelmet. A szerző ezután a visszajelzések szerint jár el, majd egyesíti a lekéréses kérelmet. Az elbírálók többsége változtatásokat kér, és azok elvégzése után újabb bírálatot végez.

Ha a módosítások technikai elbírálást kívánnak, akkor a tartalomért felelős csapat a megfelelő termék csapatának egy tagját kéri fel bírálatra.

### <a name="review-wip-pull-requests"></a>„WIP” lekéréses kérelmek bírálata

Az új szerzők esetleg már a folyamat korábbi szakaszában is szeretnének visszajelzést kapni. Ilyenkor megnyithatnak egy lekéréses kérelmet, amelynek a címében elhelyezik a „WIP” címkét. Egy megjegyzésben kérhetik az előzetes elbírálást.

Ezek az előzetes elbírálások nem olyan alaposak, mint egy teljes lekéréses kérelem bírálata. A tartalomért felelős csapat megjegyzéseket tesz, de nem „hagy jóvá” vagy „kér változtatásokat” a GitHub bírálati funkciójával. Ezek az előzetes bírálatok a cikk felépítésére: a vázlatra, az általános tartalomra és a mintákra összpontosítanak. Az ilyen bírálatoknak nem része a nyelvtan vagy a hivatkozások helyességének vizsgálata.

## <a name="respond-to-reviews"></a>Válasz a bírálatokra

A szerző a lekéréses kérelmet frissítve válaszol a megjegyzésekre. Amelyekkel már foglalkozott, azokat a „+1” kiegészítéssel jelöli meg. Ha a szerző nem ért egyet a megjegyzéssel, vagy más módon oldja meg a megjegyzésben leírtakat, akkor új megjegyzésben ismerteti a módosítást.

A szerző megjegyzésben @-mentions az eredeti elbírálót, hogy új bírálatot kér. 

## <a name="response-time-expectations"></a>Várható válaszidők

A tartalomért felelős csapat az új lekéréses kérelmeket általában két munkanapon belül bírálja el. Ha az elbírálás ennél tovább tart, akkor a csapat tagjainak egyike egy hozzáfűzött megjegyzésben jelzi a lekéréses kérelem tudomásul vételét és a várható válaszidőt.

A kérelem beküldése után a szerzők lehetőleg törekedjenek egy héten belül megválaszolni a megjegyzéseket. Az önkéntesek más elkötelezettségeik miatt esetleg nem tudják teljesíteni ezeket az elvárásokat. Ilyen esetben a csapat tagjai a közösségbeli szerzőt kérik meg a lekéréses kérelem frissítésére. Ha ez nem történik meg, akkor helyette a csapat tagja frissíti és egyesíti a lekéréses kérelmet.
