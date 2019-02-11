---
title: ms-prod-missing
description: Magyarázat és megoldás a Docs ms-prod-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: ee29396a20345f6884a5bbc94aa25f48dafaff52
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713223"
---
# <a name="ms-prod-missing"></a><span data-ttu-id="a599d-103">ms-prod-missing</span><span class="sxs-lookup"><span data-stu-id="a599d-103">ms-prod-missing</span></span>

<span data-ttu-id="a599d-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="a599d-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="a599d-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="a599d-105">Suggestion</span></span>

`Missing attribute: ms.prod. If you specify ms.technology, you must also specify ms.prod.`

<span data-ttu-id="a599d-106">Helyszíni termékek megadására használja az `ms.prod` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="a599d-106">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="a599d-107">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is, de ha megadja az `ms.technology` attribútumot, az `ms.prod` megadása is kötelező.</span><span class="sxs-lookup"><span data-stu-id="a599d-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`, but if you specify `ms.technology`, you must also specify `ms.prod`.</span></span> <span data-ttu-id="a599d-108">Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="a599d-108">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="a599d-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="a599d-109">Resolution</span></span>

<span data-ttu-id="a599d-110">Győződjön meg arról, hogy az Ön által megadott `ms.technology` érték a cikkének megfelelő,</span><span class="sxs-lookup"><span data-stu-id="a599d-110">Confirm that the `ms.technology` value you've specified is correct for your article.</span></span> <span data-ttu-id="a599d-111">majd adja hozzá a megfelelő `ms.prod` értéket, amely érvényes szülőattribútum az `ms.technology` számára.</span><span class="sxs-lookup"><span data-stu-id="a599d-111">Then add the appropriate `ms.prod` value that is a valid parent for the `ms.technology`.</span></span>

<span data-ttu-id="a599d-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="a599d-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
