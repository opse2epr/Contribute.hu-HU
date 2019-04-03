---
title: ms-date-too-late
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4cb5da1da2fee59302791e729e5fcfb8e84170e5
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637391"
---
# <a name="ms-date-too-late"></a><span data-ttu-id="fbff2-103">ms-date-too-late</span><span class="sxs-lookup"><span data-stu-id="fbff2-103">ms-date-too-late</span></span>

## <a name="warning"></a><span data-ttu-id="fbff2-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="fbff2-104">Warning</span></span>

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

<span data-ttu-id="fbff2-105">Az `ms.date` attribútum a „frissesség” jelzésére szolgál, azaz, hogy mikor ellenőrizték utoljára a cikket a relevancia, a pontosság, a képernyőképek helyessége és a hivatkozások működése szempontjából.</span><span class="sxs-lookup"><span data-stu-id="fbff2-105">The `ms.date` attribute is used to indicate "freshness" - that is, when the article was last reviewed for relevance, accuracy, correct screen shots, and working links.</span></span> <span data-ttu-id="fbff2-106">Ezért nem lehet jövőbeli dátum.</span><span class="sxs-lookup"><span data-stu-id="fbff2-106">Therefore, it can't be in the future!</span></span> <span data-ttu-id="fbff2-107">A közzétételi idő figyelembe vétele érdekében öt nap ráhagyás megengedett, például a tartalom minőségbiztosítási célú rögzítésekor egy jelentős esemény előkészítése során.</span><span class="sxs-lookup"><span data-stu-id="fbff2-107">Five days are allowed to account for release time, such as when content is frozen for QA in preparation for a major event.</span></span>

## <a name="resolution"></a><span data-ttu-id="fbff2-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="fbff2-108">Resolution</span></span>

<span data-ttu-id="fbff2-109">Adjon meg egy, a mai naptól számított nem több, mint öt napon belüli `ms.date` dátumot HH/NN/ÉÉÉÉ formátumban:</span><span class="sxs-lookup"><span data-stu-id="fbff2-109">Specify an `ms.date` no more than five days from today, in format MM/DD/YYYY:</span></span>

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
