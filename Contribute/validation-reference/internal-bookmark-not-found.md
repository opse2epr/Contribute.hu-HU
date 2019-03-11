---
title: internal-bookmark-not-found
description: Magyarázat és megoldás a Docs internal-bookmark-not-found buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 9073603d4e745db2f49b57a8901e00a03d8f570f
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427498"
---
# <a name="internal-bookmark-not-found"></a><span data-ttu-id="c05fe-103">internal-bookmark-not-found</span><span class="sxs-lookup"><span data-stu-id="c05fe-103">internal-bookmark-not-found</span></span>

<span data-ttu-id="c05fe-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="c05fe-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="c05fe-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="c05fe-105">Suggestion</span></span>

`Current file doesn't contain a bookmark named '{bookmark}'.`

<span data-ttu-id="c05fe-106">Nem létező fejlécre próbál hivatkozni az aktuális fájlban.</span><span class="sxs-lookup"><span data-stu-id="c05fe-106">You're trying to link to a heading in the current file that doesn't exist.</span></span>

## <a name="resolution"></a><span data-ttu-id="c05fe-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="c05fe-107">Resolution</span></span>

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

<span data-ttu-id="c05fe-108">Ellenőrizze a hivatkozni kívánt fejlécet, és frissítse a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="c05fe-108">Verify the heading you want to link to and update the link.</span></span>

<span data-ttu-id="c05fe-109">Az aktuális cikk egy szakaszára való hivatkozáshoz egy kettőskereszt jel után írja be a fejléc szövegét.</span><span class="sxs-lookup"><span data-stu-id="c05fe-109">To link to a section in the current article, use a hash symbol, followed by the words of the heading.</span></span> <span data-ttu-id="c05fe-110">Távolítsa el a fejléc írásjeleit, a szóközöket pedig cserélje kötőjelekre.</span><span class="sxs-lookup"><span data-stu-id="c05fe-110">Remove punctuation from the heading and replace spaces with dashes.</span></span> <span data-ttu-id="c05fe-111">Például:</span><span class="sxs-lookup"><span data-stu-id="c05fe-111">The following is an example:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
