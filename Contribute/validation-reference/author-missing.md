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
# <a name="author-missing"></a><span data-ttu-id="6c594-103">author-missing</span><span class="sxs-lookup"><span data-stu-id="6c594-103">author-missing</span></span>

<span data-ttu-id="6c594-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="6c594-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="6c594-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="6c594-105">Suggestion</span></span>

`Missing attribute: author. Add a valid GitHub ID.`

<span data-ttu-id="6c594-106">Az `author` attribútum a cikk szerzőjét azonosítja a GitHubon.</span><span class="sxs-lookup"><span data-stu-id="6c594-106">The `author` attribute identifies the author of the article by GitHub ID.</span></span> 

## <a name="resolution"></a><span data-ttu-id="6c594-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="6c594-107">Resolution</span></span>

<span data-ttu-id="6c594-108">Adja hozzá a szerző GitHub-azonosítóját az YML-fejléchez:</span><span class="sxs-lookup"><span data-stu-id="6c594-108">Add the author's GitHub ID to the YML header:</span></span>

```markdown
---
author: meganbradley
ms.author: mbradley
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]