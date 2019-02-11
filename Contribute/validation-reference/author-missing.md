---
title: author-missing
description: Magyarázat és megoldás a Docs author-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: cba9788c113101fc93bffa674702b2bed95afbcb
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713039"
---
# <a name="author-missing"></a>author-missing

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Missing attribute: author. Add a valid GitHub ID.`

Az `author` attribútum a cikk szerzőjét azonosítja a GitHubon. 

## <a name="resolution"></a>Megoldás

Adja hozzá a szerző GitHub-azonosítóját az YML-fejléchez:

```markdown
---
author: meganbradley
ms.author: mbradley
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]