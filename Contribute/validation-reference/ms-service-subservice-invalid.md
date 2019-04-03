---
title: ms-service-and-subservice-invalid
description: Magyarázat és megoldás a Docs ms-service-and-subservice-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 3f165d16eed7e937c7db912a9c5e0ee0809e3031
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637299"
---
# <a name="ms-service-and-subservice-invalid"></a><span data-ttu-id="1ca95-103">ms-service-and-subservice-invalid</span><span class="sxs-lookup"><span data-stu-id="1ca95-103">ms-service-and-subservice-invalid</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="1ca95-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="1ca95-104">Suggestion</span></span>

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

<span data-ttu-id="1ca95-105">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="1ca95-105">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="1ca95-106">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="1ca95-106">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="1ca95-107">Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="1ca95-107">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span> <span data-ttu-id="1ca95-108">Vagy érvénytelen az `ms.service` értéke, vagy pedig az `ms.subservice` érték nem alkot érvényes párt az `ms.service` aktuális értékével.</span><span class="sxs-lookup"><span data-stu-id="1ca95-108">Either your `ms.service` value is invalid, or your `ms.subservice` value is not a valid pair with your `ms.service`.</span></span>

## <a name="resolution"></a><span data-ttu-id="1ca95-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="1ca95-109">Resolution</span></span>

<span data-ttu-id="1ca95-110">Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="1ca95-110">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="1ca95-111">majd válasszon egy érvényes `ms.subservice` értéket.</span><span class="sxs-lookup"><span data-stu-id="1ca95-111">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="1ca95-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="1ca95-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
