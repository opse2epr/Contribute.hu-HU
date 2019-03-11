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
# <a name="no-space-in-h1"></a><span data-ttu-id="c1fd8-103">no-space-in-h1</span><span class="sxs-lookup"><span data-stu-id="c1fd8-103">no-space-in-h1</span></span>

## <a name="warning"></a><span data-ttu-id="c1fd8-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="c1fd8-104">Warning</span></span>

`A space is required after the hash (#) in H1.`

<span data-ttu-id="c1fd8-105">H1 a Markdown-fájl első fejlécét jelöli.</span><span class="sxs-lookup"><span data-stu-id="c1fd8-105">H1 refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="c1fd8-106">A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1fd8-106">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span> <span data-ttu-id="c1fd8-107">H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.</span><span class="sxs-lookup"><span data-stu-id="c1fd8-107">An H1 is created by beginning a line with a single hash (#) followed by a space, then the heading text.</span></span> <span data-ttu-id="c1fd8-108">A kettőskereszt utáni szóköz nélkül a Docs nem ismeri fel a H1 fejléceket.</span><span class="sxs-lookup"><span data-stu-id="c1fd8-108">Without the space after the hash, Docs will not recognize an H1.</span></span>

## <a name="resolution"></a><span data-ttu-id="c1fd8-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="c1fd8-109">Resolution</span></span>

<span data-ttu-id="c1fd8-110">A probléma megoldásához szúrjon be egy szóközt a kettőskereszt után a H1 fejlécbe.</span><span class="sxs-lookup"><span data-stu-id="c1fd8-110">To fix this error, add a space after the hash in your H1.</span></span>

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]