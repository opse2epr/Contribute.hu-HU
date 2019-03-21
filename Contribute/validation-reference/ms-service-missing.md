---
title: ms-service-missing
description: Magyarázat és megoldás a Docs ms-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 7c5860d9ef50598ad5b3e9546100af0ba436e69f
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987721"
---
# <a name="ms-service-missing"></a><span data-ttu-id="fc72b-103">ms-service-missing</span><span class="sxs-lookup"><span data-stu-id="fc72b-103">ms-service-missing</span></span>

<span data-ttu-id="fc72b-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="fc72b-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="fc72b-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="fc72b-105">Suggestion</span></span>

`Missing attribute: ms.service. If you specify ms.subservice, you must also specify ms.service.`

<span data-ttu-id="fc72b-106">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="fc72b-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="fc72b-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is, de ha megadja az `ms.subservice` attribútumot, az `ms.service` megadása is kötelező.</span><span class="sxs-lookup"><span data-stu-id="fc72b-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`, but if you specify `ms.subservice`, you must also specify `ms.service`.</span></span> <span data-ttu-id="fc72b-108">Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="fc72b-108">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="fc72b-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="fc72b-109">Resolution</span></span>

<span data-ttu-id="fc72b-110">Győződjön meg arról, hogy az Ön által megadott `ms.subservice` érték a cikkének megfelelő,</span><span class="sxs-lookup"><span data-stu-id="fc72b-110">Confirm that the `ms.subservice` value you've specified is correct for your article.</span></span> <span data-ttu-id="fc72b-111">majd adja hozzá a megfelelő `ms.service` értéket, amely érvényes szülőattribútum az `ms.subservice` számára.</span><span class="sxs-lookup"><span data-stu-id="fc72b-111">Then add the appropriate `ms.service` value that is a valid parent for the `ms.subservice`.</span></span>

<span data-ttu-id="fc72b-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="fc72b-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
