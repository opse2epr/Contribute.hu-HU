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
# <a name="h1-empty"></a><span data-ttu-id="f4e01-103">h1-empty</span><span class="sxs-lookup"><span data-stu-id="f4e01-103">h1-empty</span></span>

## <a name="warning"></a><span data-ttu-id="f4e01-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="f4e01-104">Warning</span></span>

`H1 is required. Add content to your top-level heading.`

<span data-ttu-id="f4e01-105">H1 a Markdown-fájl első fejlécét jelöli.</span><span class="sxs-lookup"><span data-stu-id="f4e01-105">H1 refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="f4e01-106">A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="f4e01-106">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span> <span data-ttu-id="f4e01-107">H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.</span><span class="sxs-lookup"><span data-stu-id="f4e01-107">An H1 is created by beginning a line with a single hash (#) followed by a space, then the heading text.</span></span>

## <a name="resolution"></a><span data-ttu-id="f4e01-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="f4e01-108">Resolution</span></span>

<span data-ttu-id="f4e01-109">A probléma megoldásához gondoskodjon arról, hogy a H1 fejlécnek a kettős kereszten kívül is legyen tartalma.</span><span class="sxs-lookup"><span data-stu-id="f4e01-109">To fix this issue, make sure your H1 includes content, not just a hash.</span></span>

<span data-ttu-id="f4e01-110">Rossz:</span><span class="sxs-lookup"><span data-stu-id="f4e01-110">Bad:</span></span>

```markdown
---
author: meganbradley
ms.author: mbradley
---
#
This is not an H1
```

<span data-ttu-id="f4e01-111">Jó:</span><span class="sxs-lookup"><span data-stu-id="f4e01-111">Good:</span></span>

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]