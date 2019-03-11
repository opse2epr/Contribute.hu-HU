---
title: external-bookmark-not-found
description: Magyarázat és megoldás a Docs external-bookmark-not-found buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: b533a463ac38d6445ab84c74bf14b2065a0a63f3
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427462"
---
# <a name="external-bookmark-not-found"></a>external-bookmark-not-found

## <a name="warning"></a>Figyelmeztetés

`File '{file name}' doesn't contain a bookmark named '{bookmark text}'.`

Nem létező fejlécre próbál hivatkozni egy másik fájlban.

## <a name="resolution"></a>Megoldás

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

Vizsgálja át a fájlt, amelyre hivatkozik, és módosítsa a könyvjelzőhivatkozást, hogy a fájl egy érvényes szakaszára mutasson.

Egy másik cikk szakaszfejlécére való hivatkozást kezdje a fájlra vagy webhelyre mutató relatív hivatkozással és a kettőskereszt jellel, majd folytassa a fejléc szövegével. Távolítsa el a fejléc írásjeleit, a szóközöket pedig cserélje kötőjelekre. Például:

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
