---
title: manager-missing
description: Magyarázat és megoldás a Docs manager-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 3/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 16da241a21d400d5a5dfb101e247e55d95567485
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427487"
---
# <a name="manager-missing"></a><span data-ttu-id="e4a52-103">manager-missing</span><span class="sxs-lookup"><span data-stu-id="e4a52-103">manager-missing</span></span>

<span data-ttu-id="e4a52-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="e4a52-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="e4a52-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="e4a52-105">Suggestion</span></span>

`Missing attribute: manager. Add a valid Microsoft alias for the author's manager.`

<span data-ttu-id="e4a52-106">Egyes tartalomcsoportok a szerző felettesének azonosításához megkövetelik a `manager` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="e4a52-106">Some content groups require the `manager` attribute to identify the author's manager.</span></span>

## <a name="resolution"></a><span data-ttu-id="e4a52-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="e4a52-107">Resolution</span></span>

<span data-ttu-id="e4a52-108">Adjon meg érvényes Microsoft-aliast a `manager` attribútumhoz:</span><span class="sxs-lookup"><span data-stu-id="e4a52-108">Add a valid Microsoft alias for `manager`:</span></span>

```yml
---
ms.author: mbradley
manager: jemash
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
