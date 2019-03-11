---
title: internal-bookmark-not-found
description: Magyarázat és megoldás a Docs internal-bookmark-not-found buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 9073603d4e745db2f49b57a8901e00a03d8f570f
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427498"
---
# <a name="internal-bookmark-not-found"></a>internal-bookmark-not-found

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Current file doesn't contain a bookmark named '{bookmark}'.`

Nem létező fejlécre próbál hivatkozni az aktuális fájlban.

## <a name="resolution"></a>Megoldás

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

Ellenőrizze a hivatkozni kívánt fejlécet, és frissítse a hivatkozást.

Az aktuális cikk egy szakaszára való hivatkozáshoz egy kettőskereszt jel után írja be a fejléc szövegét. Távolítsa el a fejléc írásjeleit, a szóközöket pedig cserélje kötőjelekre. Például:

```markdown
[Managed Disks](#managed-disks)
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
