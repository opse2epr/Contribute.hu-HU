---
title: ms-date-too-late
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 863b13e55c2aaa2057920e3bd77ec75ab5945277
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713108"
---
# <a name="ms-date-too-late"></a><span data-ttu-id="fa546-103">ms-date-too-late</span><span class="sxs-lookup"><span data-stu-id="fa546-103">ms-date-too-late</span></span>

<span data-ttu-id="fa546-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="fa546-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="fa546-105">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="fa546-105">Warning</span></span>

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

<span data-ttu-id="fa546-106">Az `ms.date` attribútum a „frissesség” jelzésére szolgál, azaz, hogy mikor ellenőrizték utoljára a cikket a relevancia, a pontosság, a képernyőképek helyessége és a hivatkozások működése szempontjából.</span><span class="sxs-lookup"><span data-stu-id="fa546-106">The `ms.date` attribute is used to indicate "freshness" - that is, when the article was last reviewed for relevance, accuracy, correct screen shots, and working links.</span></span> <span data-ttu-id="fa546-107">Ezért nem lehet jövőbeli dátum.</span><span class="sxs-lookup"><span data-stu-id="fa546-107">Therefore, it can't be in the future!</span></span> <span data-ttu-id="fa546-108">A közzétételi idő figyelembe vétele érdekében öt nap ráhagyás megengedett, például a tartalom minőségbiztosítási célú rögzítésekor egy jelentős esemény előkészítése során.</span><span class="sxs-lookup"><span data-stu-id="fa546-108">Five days are allowed to account for release time, such as when content is frozen for QA in preparation for a major event.</span></span>

## <a name="resolution"></a><span data-ttu-id="fa546-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="fa546-109">Resolution</span></span>

<span data-ttu-id="fa546-110">Adjon meg egy, a mai naptól számított nem több, mint öt napon belüli `ms.date` dátumot HH/NN/ÉÉÉÉ formátumban.</span><span class="sxs-lookup"><span data-stu-id="fa546-110">Specify an `ms.date` no more than five days from today, in format MM/DD/YYYY.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
