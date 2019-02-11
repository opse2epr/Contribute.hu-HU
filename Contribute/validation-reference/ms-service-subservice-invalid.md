---
title: ms-service-and-subservice-invalid
description: Magyarázat és megoldás a Docs ms-service-and-subservice-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 6a2efc5cee04d7721e7a8fe1602ca24dc09ca7fd
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713131"
---
# <a name="ms-service-and-subservice-invalid"></a><span data-ttu-id="7cf61-103">ms-service-and-subservice-invalid</span><span class="sxs-lookup"><span data-stu-id="7cf61-103">ms-service-and-subservice-invalid</span></span>

<span data-ttu-id="7cf61-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="7cf61-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="7cf61-105">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="7cf61-105">Warning</span></span>

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

<span data-ttu-id="7cf61-106">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="7cf61-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="7cf61-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="7cf61-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="7cf61-108">Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="7cf61-108">The values for `ms.service` and `ms.subservice` must be a valid pair.</span></span> <span data-ttu-id="7cf61-109">Vagy érvénytelen az `ms.service` értéke, vagy pedig az `ms.subservice` érték nem alkot érvényes párt az `ms.service` aktuális értékével.</span><span class="sxs-lookup"><span data-stu-id="7cf61-109">Either your `ms.service` value is invalid, or your `ms.subservice` value is not a valid pair with your `ms.service`.</span></span>

## <a name="resolution"></a><span data-ttu-id="7cf61-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="7cf61-110">Resolution</span></span>

<span data-ttu-id="7cf61-111">Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="7cf61-111">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="7cf61-112">majd válasszon egy érvényes `ms.subservice` értéket.</span><span class="sxs-lookup"><span data-stu-id="7cf61-112">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="7cf61-113">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="7cf61-113">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
