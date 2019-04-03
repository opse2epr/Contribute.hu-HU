---
title: ms-prod-service-mismatch
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: a8d1698a4842ace0e5dd07db170f40a310c666a6
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636793"
---
# <a name="ms-prod-service-mismatch"></a><span data-ttu-id="a8fe9-103">ms-prod-service-mismatch</span><span class="sxs-lookup"><span data-stu-id="a8fe9-103">ms-prod-service-mismatch</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="a8fe9-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="a8fe9-104">Suggestion</span></span>

`Invalid attribute pair: ms.prod and ms.subservice. You can only pair ms.prod with ms.technology.`

`Invalid attribute pair: ms.service and ms.technology. You can only pair ms.service with ms.subservice.`

<span data-ttu-id="a8fe9-105">Helyszíni termékek megadására használja az `ms.prod`, felhőszolgáltatásokéra pedig az `ms.service` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-105">Use `ms.prod` to specify on-premises products; `ms.service` for cloud services.</span></span> <span data-ttu-id="a8fe9-106">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-106">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="a8fe9-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-107">To specify more detailed information about `ms.service`, you can specify `ms.subservice`.</span></span> <span data-ttu-id="a8fe9-108">Az `ms.prod` nem használható az `ms.subservice`, az `ms.service` vagy az `ms.technology` attribútumokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-108">You can't use `ms.prod` with `ms.subservice` or `ms.service` with `ms.technology`.</span></span>

## <a name="resolution"></a><span data-ttu-id="a8fe9-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="a8fe9-109">Resolution</span></span>

<span data-ttu-id="a8fe9-110">Először győződjön meg róla, hogy a megfelelő szülőattribútumot (`ms.prod` vagy `ms.service`) választotta a cikkhez,</span><span class="sxs-lookup"><span data-stu-id="a8fe9-110">First, verify that you have selected the correct parent attribute (`ms.prod` or `ms.service`) for your article.</span></span> <span data-ttu-id="a8fe9-111">majd adja hozzá a megfelelő gyermekmezőt egy érvényes párosított értékkel.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-111">Then, add the appropriate child field with a valid paired value.</span></span> <span data-ttu-id="a8fe9-112">Távolítsa el a további mezőket.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-112">Remove any extra fields.</span></span>

<span data-ttu-id="a8fe9-113">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="a8fe9-113">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
