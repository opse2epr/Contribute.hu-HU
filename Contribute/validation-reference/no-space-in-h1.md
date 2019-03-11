---
title: no-space-in-h1
description: Magyarázat és megoldás a Docs no-space-in-h1 buildelési problémájára.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 8c719a89e6373fb960f216a5b4ec01c6d1739a28
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427499"
---
# <a name="no-space-in-h1"></a>no-space-in-h1

## <a name="warning"></a>Figyelmeztetés

`A space is required after the hash (#) in H1.`

H1 a Markdown-fájl első fejlécét jelöli. A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg. H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét. A kettőskereszt utáni szóköz nélkül a Docs nem ismeri fel a H1 fejléceket.

## <a name="resolution"></a>Megoldás

A probléma megoldásához szúrjon be egy szóközt a kettőskereszt után a H1 fejlécbe.

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]