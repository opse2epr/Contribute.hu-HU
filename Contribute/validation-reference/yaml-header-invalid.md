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
# <a name="yaml-header-invalid"></a><span data-ttu-id="359ae-103">yaml-header-invalid</span><span class="sxs-lookup"><span data-stu-id="359ae-103">yaml-header-invalid</span></span>

## <a name="warning"></a><span data-ttu-id="359ae-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="359ae-104">Warning</span></span>

`Invalid YAML header: Improper use of a colon in a metadata entry.`

<span data-ttu-id="359ae-105">Ez általában azt jelenti, hogy egy YAML-fejlécben egy idézőjelek nélküli metaadat értéke kettőspontot vagy más speciális karaktert tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="359ae-105">Usually this means an unquoted metadata value in a YAML header includes a colon or another special character.</span></span> <span data-ttu-id="359ae-106">Arra is utalhat, hogy egy kulcs/érték párban hiányzik egy kettőspont utáni szóköz.</span><span class="sxs-lookup"><span data-stu-id="359ae-106">It can also mean that a space is missing after the colon in a key/value pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="359ae-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="359ae-107">Resolution</span></span>

<span data-ttu-id="359ae-108">Vizsgálja át a YAML-fejlécet.</span><span class="sxs-lookup"><span data-stu-id="359ae-108">Review your YAML header.</span></span> <span data-ttu-id="359ae-109">Keresse a következő hibákat.</span><span class="sxs-lookup"><span data-stu-id="359ae-109">Look for the following mistakes.</span></span>

<span data-ttu-id="359ae-110">Kettőspont egy idézőjelek nélküli értékben:</span><span class="sxs-lookup"><span data-stu-id="359ae-110">Colon in unquoted value:</span></span>

```yml
---
title: Common mistake: I included a colon in my unquoted value.
---
```

<span data-ttu-id="359ae-111">Módosítsa a következőre:</span><span class="sxs-lookup"><span data-stu-id="359ae-111">Change to:</span></span>

```yml
---
title: 'Common mistake: I included a colon in my unquoted value.'
---
```

<span data-ttu-id="359ae-112">Egy kulcs/érték párban hiányzik egy kettőspont utáni szóköz:</span><span class="sxs-lookup"><span data-stu-id="359ae-112">No space after colon in key/value pair:</span></span>

```yml
---
title:I omitted a space.
---
```

<span data-ttu-id="359ae-113">Módosítsa a következőre:</span><span class="sxs-lookup"><span data-stu-id="359ae-113">Change to:</span></span>

```yml
---
title: I omitted a space.
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
