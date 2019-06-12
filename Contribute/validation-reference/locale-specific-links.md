---
author: meganbradley
ms.author: mbradley
ms.date: 03/29/2019
title: Területi beállításokhoz kötődő hivatkozások
ms.openlocfilehash: f42a26da45b48972bfc595cb26c67ab0acfe8603
ms.sourcegitcommit: 1e53d17639277bebd89b2e7cabeb45bdad526354
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2019
ms.locfileid: "66841256"
---
# <a name="locale-specific-links"></a>Területi beállításokhoz kötődő hivatkozások

A nyelvterületkódok, például az `en-us` Microsoft bizonyos webhelyeire mutató hivatkozásokba történő belefoglalása nem javasolt. Ha egy angol nyelvű tartalomban található hivatkozásba foglalja bele a nyelvterületkódot, akkor a honosított hivatkozásokban is meg fog jelenni, ami rontja a honosítás összhatását. Például, ha egy német nyelvű honosított tartalomban szerepel az `en-us`, akkor a német ügyfeleket is az angol cikkhez fogja irányítani a hivatkozás, még akkor is, ha a cikk németül is elérhető.

Távolítsa el a Microsoft webhelyeire mutató hivatkozásokból a nyelvterületkódokat. Például:

Előtte:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

Utána:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

A következő oldalak tartoznak az ellenőrzés hatáskörébe:

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com