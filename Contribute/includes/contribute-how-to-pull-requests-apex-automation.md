---
ms.openlocfilehash: b64e8dd4c62ca05b6e04ef404ebf98a618d0171e
ms.sourcegitcommit: 2563918217ba0760a4f3877af2272a0a4b2c3052
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66391454"
---
Az automatizált megjegyzések lehetővé teszik, hogy az olvasási szintű felhasználók (olyan felhasználók, akiknek nincs írási engedélye egy tárházban) írási műveletet hajthassanak végre a megfelelő címkét egy pull-kérelemhez csatolva. Amennyiben olyan tárházban dolgozik, amelyben implementálva vannak az automatizált megjegyzések, az alábbi táblázatban felsorolt hashtag-megjegyzéseket használhatja címkék hozzárendelésére, címkék megváltoztatására vagy egy pull-kérelem lezárására. A Microsoft alkalmazottai e-mailben is értesítést kapnak az áttekintendő és véglegesítendő nyilvános tárházbeli pull-kérelmekről, ha olyan cikkhez érkezik módosítási javaslat, amelynek a szerzői.

| Hashtag-megjegyzés | Hatása | Tárház rendelkezésre állása |
| --- | --- | --- |
| `#sign-off` |Amikor egy cikk szerzője begépeli a `#sign-off` megjegyzést a megjegyzések folyamatába, hozzárendelődik a **ready-to-merge** (egyesítésre kész) címke. Ez a címke tudatja a tárházbeli elbírálókkal, hogy a pull-kérelem véglegesítésre/egyesítésre kész. <br/><br/> Ha egy olyan közreműködő, aki *nem* a feltüntetett szerző, megpróbál a `#sign-off` megjegyzéssel véglegesíteni egy nyilvános tárházon egy pull-kérelmet, akkor egy üzenet íródik a kérelemhez, amely közli, hogy a címkét csak a szerző rendelheti hozzá. |Nyilvános és privát |
| `#hold-off` |A szerzők a `#hold-off` (visszatartás) pull-kérelem megjegyzés begépelésével távolíthatják el a **ready-to-merge** (egyesítésre kész) címkét – ha meggondolták magukat vagy hibát vétettek. A privát tárházban ez hozzárendeli a **do-not-merge** (nem egyesítendő) címkét. |Nyilvános és privát |
| `#please-close` |A szerzők a `#please-close` megjegyzést a megjegyzések folyamatába begépelve zárhatják le a pull-kérelmet ha úgy döntenek, hogy nem egyesíttetik a változásokat. |Nyilvános |
