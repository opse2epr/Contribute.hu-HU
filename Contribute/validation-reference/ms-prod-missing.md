---
title: ms-prod-missing
description: Magyarázat és megoldás a Docs ms-prod-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 2578ab47dab315a446529d24357e9489d7fd0bad
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987698"
---
# <a name="ms-prod-missing"></a><span data-ttu-id="cc10f-103">ms-prod-missing</span><span class="sxs-lookup"><span data-stu-id="cc10f-103">ms-prod-missing</span></span>

<span data-ttu-id="cc10f-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="cc10f-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="cc10f-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="cc10f-105">Suggestion</span></span>

`Missing attribute: ms.prod. If you specify ms.technology, you must also specify ms.prod.`

<span data-ttu-id="cc10f-106">Helyszíni termékek megadására használja az `ms.prod` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="cc10f-106">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="cc10f-107">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is, de ha megadja az `ms.technology` attribútumot, az `ms.prod` megadása is kötelező.</span><span class="sxs-lookup"><span data-stu-id="cc10f-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`, but if you specify `ms.technology`, you must also specify `ms.prod`.</span></span> <span data-ttu-id="cc10f-108">Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="cc10f-108">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span>

## <a name="resolution"></a><span data-ttu-id="cc10f-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="cc10f-109">Resolution</span></span>

<span data-ttu-id="cc10f-110">Győződjön meg arról, hogy az Ön által megadott `ms.technology` érték a cikkének megfelelő,</span><span class="sxs-lookup"><span data-stu-id="cc10f-110">Confirm that the `ms.technology` value you've specified is correct for your article.</span></span> <span data-ttu-id="cc10f-111">majd adja hozzá a megfelelő `ms.prod` értéket, amely érvényes szülőattribútum az `ms.technology` számára.</span><span class="sxs-lookup"><span data-stu-id="cc10f-111">Then add the appropriate `ms.prod` value that is a valid parent for the `ms.technology`.</span></span>

<span data-ttu-id="cc10f-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="cc10f-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
