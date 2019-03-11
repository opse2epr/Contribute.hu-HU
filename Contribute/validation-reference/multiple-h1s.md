---
title: multiple-h1
description: Magyarázat és megoldás a Docs multiple-h1 buildelési problémájára.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 55ce6260cb4d1e09f63e0540528576ed3fa165f8
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427904"
---
# <a name="multiple-h1"></a>multiple-h1

## <a name="warning"></a>Figyelmeztetés

`Multiple H1s are not allowed. You can only have one top-level heading.`

H1 a Markdown-fájl első fejlécét jelöli. A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg. H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét. Egy fájlban csak egy H1 fejléc lehet.

## <a name="resolution"></a>Megoldás

A hiba kijavításához változtassa meg a többi H1 fejléc szintjét H2-re (`##`), vagy más módon rendezze át a fájlt. Fontos, hogy a fejlécszintek átugrása, például hogy H1 után H3 következzen, nem megengedett.

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1

Some content...

## This is an H2
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]