---
title: ms-prod-service-mismatch
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4a3cf8bc5435972f0442ca1d41d4147e1ea00d78
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713177"
---
# <a name="ms-prod-service-mismatch"></a><span data-ttu-id="50790-103">ms-prod-service-mismatch</span><span class="sxs-lookup"><span data-stu-id="50790-103">ms-prod-service-mismatch</span></span>

<span data-ttu-id="50790-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="50790-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="50790-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="50790-105">Suggestion</span></span>

`Invalid attribute pair: ms.prod and ms.subservice. You can only pair ms.prod with ms.technology.`

`Invalid attribute pair: ms.service and ms.technology. You can only pair ms.service with ms.subservice.`

<span data-ttu-id="50790-106">Helyszíni termékek megadására használja az `ms.prod`, felhőszolgáltatásokéra pedig az `ms.service` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="50790-106">Use `ms.prod` to specify on-premises products; `ms.service` for cloud services.</span></span> <span data-ttu-id="50790-107">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="50790-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="50790-108">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="50790-108">To specify more detailed information about `ms.service`, you can specify `ms.subservice`.</span></span> <span data-ttu-id="50790-109">Az `ms.prod` nem használható az `ms.subservice`, az `ms.service` vagy az `ms.technology` attribútumokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="50790-109">You can't use `ms.prod` with `ms.subservice` or `ms.service` with `ms.technology`.</span></span>

## <a name="resolution"></a><span data-ttu-id="50790-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="50790-110">Resolution</span></span>

<span data-ttu-id="50790-111">Először győződjön meg róla, hogy a megfelelő szülőattribútumot (`ms.prod` vagy `ms.service`) választotta a cikkhez,</span><span class="sxs-lookup"><span data-stu-id="50790-111">First, verify that you have selected the correct parent attribute (`ms.prod` or `ms.service`) for your article.</span></span> <span data-ttu-id="50790-112">majd adja hozzá a megfelelő gyermekmezőt egy érvényes párosított értékkel.</span><span class="sxs-lookup"><span data-stu-id="50790-112">Then, add the appropriate child field with a valid paired value.</span></span> <span data-ttu-id="50790-113">Távolítsa el a további mezőket.</span><span class="sxs-lookup"><span data-stu-id="50790-113">Remove any extra fields.</span></span>

<span data-ttu-id="50790-114">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="50790-114">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
