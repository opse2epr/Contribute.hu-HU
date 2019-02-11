---
title: ms-prod-or-service-missing
description: Magyarázat és megoldás a Docs ms-prod-or-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/20/2018
ms.prod: non-product-specific
ms.openlocfilehash: f4d5bc7537ec851ce7ac1de3be2208fd74cbe37f
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713545"
---
# <a name="ms-prod-or-service-missing"></a><span data-ttu-id="c9efd-103">ms-prod-or-service-missing</span><span class="sxs-lookup"><span data-stu-id="c9efd-103">ms-prod-or-service-missing</span></span>

<span data-ttu-id="c9efd-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="c9efd-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="c9efd-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="c9efd-105">Suggestion</span></span>

`Missing attribute: either ms.prod or ms.service is required. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a><span data-ttu-id="c9efd-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="c9efd-106">Resolution</span></span>

<span data-ttu-id="c9efd-107">Az `ms.prod` vagy az `ms.service` attribútum kötelező, és együtt nem használhatók: az `ms.prod` a helyszíni termékekhez használatos, az `ms.service` pedig felhőszolgáltatásokhoz.</span><span class="sxs-lookup"><span data-stu-id="c9efd-107">Either `ms.prod` or `ms.service` is required, and they can't both be present: `ms.prod` is used for on-premises products; `ms.service` is used for cloud services.</span></span> <span data-ttu-id="c9efd-108">Határozza meg, hogy melyik megfelelő a cikkéhez, ellenőrizze, hogy az érték helyes-e, és távolítsa el a másik mezőt.</span><span class="sxs-lookup"><span data-stu-id="c9efd-108">Determine which is appropriate for your article, verify that the value is correct, and remove the other field.</span></span>

<span data-ttu-id="c9efd-109">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="c9efd-109">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]