---
title: ms-service-and-subservice-invalid
description: Magyarázat és megoldás a Docs ms-service-and-subservice-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 7dee18e7b902b660a8071bcb4a0dee21c19f4f7f
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987643"
---
# <a name="ms-service-and-subservice-invalid"></a><span data-ttu-id="c64df-103">ms-service-and-subservice-invalid</span><span class="sxs-lookup"><span data-stu-id="c64df-103">ms-service-and-subservice-invalid</span></span>

<span data-ttu-id="c64df-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="c64df-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="c64df-105">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="c64df-105">Warning</span></span>

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

<span data-ttu-id="c64df-106">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="c64df-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="c64df-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="c64df-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="c64df-108">Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="c64df-108">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span> <span data-ttu-id="c64df-109">Vagy érvénytelen az `ms.service` értéke, vagy pedig az `ms.subservice` érték nem alkot érvényes párt az `ms.service` aktuális értékével.</span><span class="sxs-lookup"><span data-stu-id="c64df-109">Either your `ms.service` value is invalid, or your `ms.subservice` value is not a valid pair with your `ms.service`.</span></span>

## <a name="resolution"></a><span data-ttu-id="c64df-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="c64df-110">Resolution</span></span>

<span data-ttu-id="c64df-111">Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="c64df-111">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="c64df-112">majd válasszon egy érvényes `ms.subservice` értéket.</span><span class="sxs-lookup"><span data-stu-id="c64df-112">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="c64df-113">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="c64df-113">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
