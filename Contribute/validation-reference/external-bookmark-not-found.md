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
# <a name="external-bookmark-not-found"></a><span data-ttu-id="87475-103">external-bookmark-not-found</span><span class="sxs-lookup"><span data-stu-id="87475-103">external-bookmark-not-found</span></span>

## <a name="warning"></a><span data-ttu-id="87475-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="87475-104">Warning</span></span>

`File '{file name}' doesn't contain a bookmark named '{bookmark text}'.`

<span data-ttu-id="87475-105">Nem létező fejlécre próbál hivatkozni egy másik fájlban.</span><span class="sxs-lookup"><span data-stu-id="87475-105">You're trying to link to a heading in another file that doesn't exist.</span></span>

## <a name="resolution"></a><span data-ttu-id="87475-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="87475-106">Resolution</span></span>

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

<span data-ttu-id="87475-107">Vizsgálja át a fájlt, amelyre hivatkozik, és módosítsa a könyvjelzőhivatkozást, hogy a fájl egy érvényes szakaszára mutasson.</span><span class="sxs-lookup"><span data-stu-id="87475-107">Review the file you're linking to and update your bookmark link to point to a valid section in the file.</span></span>

<span data-ttu-id="87475-108">Egy másik cikk szakaszfejlécére való hivatkozást kezdje a fájlra vagy webhelyre mutató relatív hivatkozással és a kettőskereszt jellel, majd folytassa a fejléc szövegével.</span><span class="sxs-lookup"><span data-stu-id="87475-108">To link to a section heading in another article, use the file-relative or site-relative link plus a hash symbol, followed by the words of the heading.</span></span> <span data-ttu-id="87475-109">Távolítsa el a fejléc írásjeleit, a szóközöket pedig cserélje kötőjelekre.</span><span class="sxs-lookup"><span data-stu-id="87475-109">Remove punctuation from the heading and replace spaces with dashes.</span></span> <span data-ttu-id="87475-110">Például:</span><span class="sxs-lookup"><span data-stu-id="87475-110">The following is an example:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
