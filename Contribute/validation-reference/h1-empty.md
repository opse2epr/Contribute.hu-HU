---
title: h1-empty
description: Magyarázat és megoldás a Docs h1-empty buildelési problémájára.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: bb07235f7cd1ba6d45418c48a4190255bdd9a428
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427409"
---
# <a name="h1-empty"></a>h1-empty

## <a name="warning"></a>Figyelmeztetés

`H1 is required. Add content to your top-level heading.`

H1 a Markdown-fájl első fejlécét jelöli. A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg. H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.

## <a name="resolution"></a>Megoldás

A probléma megoldásához gondoskodjon arról, hogy a H1 fejlécnek a kettős kereszten kívül is legyen tartalma.

Rossz:

```markdown
---
author: meganbradley
ms.author: mbradley
---
#
This is not an H1
```

Jó:

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]