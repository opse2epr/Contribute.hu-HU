---
title: ms-service-missing
description: Magyarázat és megoldás a Docs ms-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 2bc425726f82840565978072b2efdf13a1284ec0
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713085"
---
# <a name="ms-service-missing"></a><span data-ttu-id="62482-103">ms-service-missing</span><span class="sxs-lookup"><span data-stu-id="62482-103">ms-service-missing</span></span>

<span data-ttu-id="62482-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="62482-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="62482-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="62482-105">Suggestion</span></span>

`Missing attribute: ms.service. If you specify ms.subservice, you must also specify ms.service.`

<span data-ttu-id="62482-106">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="62482-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="62482-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is, de ha megadja az `ms.subservice` attribútumot, az `ms.service` megadása is kötelező.</span><span class="sxs-lookup"><span data-stu-id="62482-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`, but if you specify `ms.subservice`, you must also specify `ms.service`.</span></span> <span data-ttu-id="62482-108">Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="62482-108">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="62482-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="62482-109">Resolution</span></span>

<span data-ttu-id="62482-110">Győződjön meg arról, hogy az Ön által megadott `ms.subservice` érték a cikkének megfelelő,</span><span class="sxs-lookup"><span data-stu-id="62482-110">Confirm that the `ms.subservice` value you've specified is correct for your article.</span></span> <span data-ttu-id="62482-111">majd adja hozzá a megfelelő `ms.service` értéket, amely érvényes szülőattribútum az `ms.subservice` számára.</span><span class="sxs-lookup"><span data-stu-id="62482-111">Then add the appropriate `ms.service` value that is a valid parent for the `ms.subservice`.</span></span>

<span data-ttu-id="62482-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="62482-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
