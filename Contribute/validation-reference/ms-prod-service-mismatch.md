---
title: ms-prod-service-mismatch
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: a7de44e9930def2d2582194f28695e3ef3940541
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987615"
---
# <a name="ms-prod-service-mismatch"></a><span data-ttu-id="87ac2-103">ms-prod-service-mismatch</span><span class="sxs-lookup"><span data-stu-id="87ac2-103">ms-prod-service-mismatch</span></span>

<span data-ttu-id="87ac2-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="87ac2-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="87ac2-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="87ac2-105">Suggestion</span></span>

`Invalid attribute pair: ms.prod and ms.subservice. You can only pair ms.prod with ms.technology.`

`Invalid attribute pair: ms.service and ms.technology. You can only pair ms.service with ms.subservice.`

<span data-ttu-id="87ac2-106">Helyszíni termékek megadására használja az `ms.prod`, felhőszolgáltatásokéra pedig az `ms.service` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="87ac2-106">Use `ms.prod` to specify on-premises products; `ms.service` for cloud services.</span></span> <span data-ttu-id="87ac2-107">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="87ac2-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="87ac2-108">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="87ac2-108">To specify more detailed information about `ms.service`, you can specify `ms.subservice`.</span></span> <span data-ttu-id="87ac2-109">Az `ms.prod` nem használható az `ms.subservice`, az `ms.service` vagy az `ms.technology` attribútumokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="87ac2-109">You can't use `ms.prod` with `ms.subservice` or `ms.service` with `ms.technology`.</span></span>

## <a name="resolution"></a><span data-ttu-id="87ac2-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="87ac2-110">Resolution</span></span>

<span data-ttu-id="87ac2-111">Először győződjön meg róla, hogy a megfelelő szülőattribútumot (`ms.prod` vagy `ms.service`) választotta a cikkhez,</span><span class="sxs-lookup"><span data-stu-id="87ac2-111">First, verify that you have selected the correct parent attribute (`ms.prod` or `ms.service`) for your article.</span></span> <span data-ttu-id="87ac2-112">majd adja hozzá a megfelelő gyermekmezőt egy érvényes párosított értékkel.</span><span class="sxs-lookup"><span data-stu-id="87ac2-112">Then, add the appropriate child field with a valid paired value.</span></span> <span data-ttu-id="87ac2-113">Távolítsa el a további mezőket.</span><span class="sxs-lookup"><span data-stu-id="87ac2-113">Remove any extra fields.</span></span>

<span data-ttu-id="87ac2-114">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="87ac2-114">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
