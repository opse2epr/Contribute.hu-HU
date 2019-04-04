---
title: ms-date-missing
description: Magyarázat és megoldás a Docs ms-date-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: ae2a28993671255a9ffd4503eebdbee404e52373
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637276"
---
# <a name="ms-date-missing"></a><span data-ttu-id="26cec-103">ms-date-missing</span><span class="sxs-lookup"><span data-stu-id="26cec-103">ms-date-missing</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="26cec-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="26cec-104">Suggestion</span></span>

`Missing attribute: ms.date. A freshness date is required for this content. Add a date in format MM/DD/YYYY.`

<span data-ttu-id="26cec-105">Egyes tartalomcsoportok esetén az `ms.date` a „frissesség” jelzésére szolgál, azaz, hogy mikor ellenőrizték utoljára a cikket a relevancia, a pontosság, a képernyőképek helyessége és a hivatkozások működése szempontjából.</span><span class="sxs-lookup"><span data-stu-id="26cec-105">Some content groups require `ms.date` to indicate "freshness" - that is, when the article was last reviewed for relevance, accuracy, correct screen shots, and working links.</span></span> <span data-ttu-id="26cec-106">Ez nem ugyanaz, mint a cikk *közzétételének* utolsó dátuma, amely akkor jelenik meg az oldalon, ha az `ms.date` nincs explicit módon megadva.</span><span class="sxs-lookup"><span data-stu-id="26cec-106">This is not the same as the last date the article was *published*, which will show on the page if `ms.date` is not explicitly specified.</span></span>

## <a name="resolution"></a><span data-ttu-id="26cec-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="26cec-107">Resolution</span></span>

<span data-ttu-id="26cec-108">Ellenőrizze a cikk naprakészségét és a tartalom helyességét, majd adjon hozzá érvényes dátumot HH/NN/ÉÉÉÉ formátumban:</span><span class="sxs-lookup"><span data-stu-id="26cec-108">Confirm that the article is up-to-date with no broken content, then add a valid date in the format MM/DD/YYYY:</span></span>

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
