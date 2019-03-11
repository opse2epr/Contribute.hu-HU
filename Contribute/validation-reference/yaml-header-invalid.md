---
title: yaml-header-invalid
description: Magyarázat és megoldás a Docs yaml-header-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: 62b3b2c2aa47525cae5dd5c0955eb88463124359
ms.sourcegitcommit: 89eb357721b26710e00d9b8fdab3e7628c34bdb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459027"
---
# <a name="yaml-header-invalid"></a>yaml-header-invalid

## <a name="warning"></a>Figyelmeztetés

`Invalid YAML header: Improper use of a colon in a metadata entry.`

Ez általában azt jelenti, hogy egy YAML-fejlécben egy idézőjelek nélküli metaadat értéke kettőspontot vagy más speciális karaktert tartalmaz. Arra is utalhat, hogy egy kulcs/érték párban hiányzik egy kettőspont utáni szóköz.

## <a name="resolution"></a>Megoldás

Vizsgálja át a YAML-fejlécet. Keresse a következő hibákat.

Kettőspont egy idézőjelek nélküli értékben:

```yml
---
title: Common mistake: I included a colon in my unquoted value.
---
```

Módosítsa a következőre:

```yml
---
title: 'Common mistake: I included a colon in my unquoted value.'
---
```

Egy kulcs/érték párban hiányzik egy kettőspont utáni szóköz:

```yml
---
title:I omitted a space.
---
```

Módosítsa a következőre:

```yml
---
title: I omitted a space.
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
