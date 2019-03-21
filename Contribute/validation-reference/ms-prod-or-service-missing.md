---
title: ms-prod-or-service-missing
description: Magyarázat és megoldás a Docs ms-prod-or-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/20/2018
ms.prod: non-product-specific
ms.openlocfilehash: 6eeb4a95e4d4aeba527b1078bc646fcbc56898a2
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987560"
---
# <a name="ms-prod-or-service-missing"></a><span data-ttu-id="8d45f-103">ms-prod-or-service-missing</span><span class="sxs-lookup"><span data-stu-id="8d45f-103">ms-prod-or-service-missing</span></span>

<span data-ttu-id="8d45f-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="8d45f-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="8d45f-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="8d45f-105">Suggestion</span></span>

`Missing attribute: either ms.prod or ms.service is required. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a><span data-ttu-id="8d45f-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="8d45f-106">Resolution</span></span>

<span data-ttu-id="8d45f-107">Az `ms.prod` vagy az `ms.service` attribútum kötelező, és együtt nem használhatók: az `ms.prod` a helyszíni termékekhez használatos, az `ms.service` pedig felhőszolgáltatásokhoz.</span><span class="sxs-lookup"><span data-stu-id="8d45f-107">Either `ms.prod` or `ms.service` is required, and they can't both be present: `ms.prod` is used for on-premises products; `ms.service` is used for cloud services.</span></span> <span data-ttu-id="8d45f-108">Határozza meg, hogy melyik megfelelő a cikkéhez, ellenőrizze, hogy az érték helyes-e, és távolítsa el a másik mezőt.</span><span class="sxs-lookup"><span data-stu-id="8d45f-108">Determine which is appropriate for your article, verify that the value is correct, and remove the other field.</span></span>

<span data-ttu-id="8d45f-109">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="8d45f-109">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]