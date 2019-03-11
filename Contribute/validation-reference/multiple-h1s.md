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
# <a name="multiple-h1"></a><span data-ttu-id="565ed-103">multiple-h1</span><span class="sxs-lookup"><span data-stu-id="565ed-103">multiple-h1</span></span>

## <a name="warning"></a><span data-ttu-id="565ed-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="565ed-104">Warning</span></span>

`Multiple H1s are not allowed. You can only have one top-level heading.`

<span data-ttu-id="565ed-105">H1 a Markdown-fájl első fejlécét jelöli.</span><span class="sxs-lookup"><span data-stu-id="565ed-105">H1 refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="565ed-106">A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="565ed-106">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span> <span data-ttu-id="565ed-107">H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.</span><span class="sxs-lookup"><span data-stu-id="565ed-107">An H1 is created by beginning a line with a single hash (#) followed by a space, then the heading text.</span></span> <span data-ttu-id="565ed-108">Egy fájlban csak egy H1 fejléc lehet.</span><span class="sxs-lookup"><span data-stu-id="565ed-108">You can only have one H1 in each file.</span></span>

## <a name="resolution"></a><span data-ttu-id="565ed-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="565ed-109">Resolution</span></span>

<span data-ttu-id="565ed-110">A hiba kijavításához változtassa meg a többi H1 fejléc szintjét H2-re (`##`), vagy más módon rendezze át a fájlt.</span><span class="sxs-lookup"><span data-stu-id="565ed-110">To fix this issue, change the heading level of subsequent H1s to H2 (`##`), or otherwise reorganize your file.</span></span> <span data-ttu-id="565ed-111">Fontos, hogy a fejlécszintek átugrása, például hogy H1 után H3 következzen, nem megengedett.</span><span class="sxs-lookup"><span data-stu-id="565ed-111">Note that skipping heading levels, such as following H1 with H3, is not allowed.</span></span>

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