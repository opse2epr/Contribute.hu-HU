---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084530"
---
# <a name="docs-pr-validation-service"></a>Dokumentumok PR-érvényesítési szolgáltatása

A Dokumentumok PR-érvényesítési szolgáltatása egy olyan GitHub-alkalmazás, amely érvényesítési szabályokat futtat egy PR-ben szereplő fájlokon.

Ha az érvényesítési szolgáltatás engedélyezve van egy adattáron, az alábbi működés figyelhető meg:

1. Ön elküld egy PR-t.
1. A PR állapotát jelző GitHub-hozzászólásban az adattáron engedélyezett „ellenőrzések” állapota látható. Ebben a példában kétféle ellenőrzés van engedélyezve: a „Commit Validation” és az „OpenPublishing.Build”:

   ![egyes ellenőrzések sikertelenek](media/validation-failed.png)

   A build akkor is megfelelhet az ellenőrzésen, ha a véglegesítés érvényesítése nem sikerül.

1. További információkért kattintson a **Részletek** gombra.
1. A Részletek lapon megjelenik az összes érvényesítési ellenőrzés, azok mellett pedig a problémák kijavításával kapcsolatos információk szerepelnek:

   ![érvényesítési üzenet](media/validation-details.png)

A szolgáltatásban aktuálisan engedélyezett érvényesítési műveletek listája a cikk bal oldali tartalomjegyzékében található.