---
title: ms-date-invalid
description: Magyarázat és megoldás a Docs ms-date-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: e960bc2d8e9013e480f2bb391cdfa0c1da043b8b
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431507"
---
# <a name="ms-date-invalid"></a><span data-ttu-id="30062-103">ms-date-invalid</span><span class="sxs-lookup"><span data-stu-id="30062-103">ms-date-invalid</span></span>

<span data-ttu-id="30062-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="30062-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="30062-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="30062-105">Suggestion</span></span>

`Invalid value for ms.date: '{value}'. Must be a date in format MM/DD/YYYY.`

## <a name="resolution"></a><span data-ttu-id="30062-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="30062-106">Resolution</span></span>

<span data-ttu-id="30062-107">Ellenőrizze a cikk naprakészségét és a tartalom helyességét, majd adjon hozzá érvényes dátumot HH/NN/ÉÉÉÉ formátumban:</span><span class="sxs-lookup"><span data-stu-id="30062-107">Confirm that the article is up-to-date with no broken content, then add a valid date in the format MM/DD/YYYY:</span></span>

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
