---
title: ms-prod-missing
description: Magyarázat és megoldás a Docs ms-prod-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 9b3f209ca2300735210490ffd58c3ac423c44fef
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636770"
---
# <a name="ms-prod-missing"></a><span data-ttu-id="eb0f7-103">ms-prod-missing</span><span class="sxs-lookup"><span data-stu-id="eb0f7-103">ms-prod-missing</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="eb0f7-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="eb0f7-104">Suggestion</span></span>

`Missing attribute: ms.prod. If you specify ms.technology, you must also specify ms.prod.`

<span data-ttu-id="eb0f7-105">Helyszíni termékek megadására használja az `ms.prod` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-105">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="eb0f7-106">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is, de ha megadja az `ms.technology` attribútumot, az `ms.prod` megadása is kötelező.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-106">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`, but if you specify `ms.technology`, you must also specify `ms.prod`.</span></span> <span data-ttu-id="eb0f7-107">Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-107">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="eb0f7-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="eb0f7-108">Resolution</span></span>

<span data-ttu-id="eb0f7-109">Győződjön meg arról, hogy az Ön által megadott `ms.technology` érték a cikkének megfelelő,</span><span class="sxs-lookup"><span data-stu-id="eb0f7-109">Confirm that the `ms.technology` value you've specified is correct for your article.</span></span> <span data-ttu-id="eb0f7-110">majd adja hozzá a megfelelő `ms.prod` értéket, amely érvényes szülőattribútum az `ms.technology` számára.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-110">Then add the appropriate `ms.prod` value that is a valid parent for the `ms.technology`.</span></span>

<span data-ttu-id="eb0f7-111">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-111">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
