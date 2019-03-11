---
title: hard-coded-locale
description: Magyarázat és megoldás a Docs hard-coded-locale buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 1862014076fa4cbff18535095b244e8f94a17b0f
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427408"
---
# <a name="hard-coded-locale"></a>hard-coded-locale

## <a name="warning"></a>Figyelmeztetés

`Link {URL} contains locale code {code}. For localizability, remove {code} from links to Microsoft sites.`

A nyelvterületkódok, például az `en-us` Microsoft bizonyos webhelyeire mutató hivatkozásokba történő belefoglalása nem javasolt. Ha egy angol nyelvű tartalomban található hivatkozásba foglalja bele a nyelvterületkódot, akkor a honosított hivatkozásokban is meg fog jelenni, ami rontja a honosítás összhatását. Például, ha egy német nyelvű honosított tartalomban szerepel az `en-us`, akkor a német ügyfeleket is az angol cikkhez fogja irányítani a hivatkozás, még akkor is, ha a cikk németül is elérhető.

A következő oldalak tartoznak az ellenőrzés hatáskörébe:

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com

## <a name="resolution"></a>Megoldás

Távolítsa el a Microsoft webhelyeire mutató hivatkozásokból a nyelvterületkódokat. Például:

Előtte:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

Utána:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]