---
title: author-missing
description: Magyarázat és megoldás a Docs author-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 89725dcfbd4ec266071c45a003748021b480bbc2
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431530"
---
# <a name="author-missing"></a><span data-ttu-id="b12ec-103">author-missing</span><span class="sxs-lookup"><span data-stu-id="b12ec-103">author-missing</span></span>

<span data-ttu-id="b12ec-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="b12ec-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="b12ec-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="b12ec-105">Suggestion</span></span>

`Missing attribute: author. Add a valid GitHub ID.`

<span data-ttu-id="b12ec-106">Az `author` attribútum a cikk szerzőjét azonosítja a GitHubon.</span><span class="sxs-lookup"><span data-stu-id="b12ec-106">The `author` attribute identifies the author of the article by GitHub ID.</span></span> 

## <a name="resolution"></a><span data-ttu-id="b12ec-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="b12ec-107">Resolution</span></span>

<span data-ttu-id="b12ec-108">Adja hozzá a szerző GitHub-azonosítóját az YML-fejléchez:</span><span class="sxs-lookup"><span data-stu-id="b12ec-108">Add the author's GitHub ID to the YML header:</span></span>

```yml
---
author: meganbradley
ms.author: mbradley
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]