---
title: ms-service-missing
description: Magyarázat és megoldás a Docs ms-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 17e2e272e3a21e14e038e27ff68866afe28bee60
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636701"
---
# <a name="ms-service-missing"></a><span data-ttu-id="3c832-103">ms-service-missing</span><span class="sxs-lookup"><span data-stu-id="3c832-103">ms-service-missing</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="3c832-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="3c832-104">Suggestion</span></span>

`Missing attribute: ms.service. If you specify ms.subservice, you must also specify ms.service.`

<span data-ttu-id="3c832-105">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="3c832-105">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="3c832-106">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is, de ha megadja az `ms.subservice` attribútumot, az `ms.service` megadása is kötelező.</span><span class="sxs-lookup"><span data-stu-id="3c832-106">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`, but if you specify `ms.subservice`, you must also specify `ms.service`.</span></span> <span data-ttu-id="3c832-107">Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="3c832-107">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="3c832-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="3c832-108">Resolution</span></span>

<span data-ttu-id="3c832-109">Győződjön meg arról, hogy az Ön által megadott `ms.subservice` érték a cikkének megfelelő,</span><span class="sxs-lookup"><span data-stu-id="3c832-109">Confirm that the `ms.subservice` value you've specified is correct for your article.</span></span> <span data-ttu-id="3c832-110">majd adja hozzá a megfelelő `ms.service` értéket, amely érvényes szülőattribútum az `ms.subservice` számára.</span><span class="sxs-lookup"><span data-stu-id="3c832-110">Then add the appropriate `ms.service` value that is a valid parent for the `ms.subservice`.</span></span>

<span data-ttu-id="3c832-111">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="3c832-111">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
