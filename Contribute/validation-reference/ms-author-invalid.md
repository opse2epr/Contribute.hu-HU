---
title: ms-author-invalid
description: Magyarázat és megoldás a Docs ms-author-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 6d6c77b9b378865913e2055abf2b64ccba8ca482
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636724"
---
# <a name="ms-author-invalid"></a><span data-ttu-id="9b3f7-103">ms-author-invalid</span><span class="sxs-lookup"><span data-stu-id="9b3f7-103">ms-author-invalid</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="9b3f7-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="9b3f7-104">Suggestion</span></span>

`Invalid value for ms.author: '{value}' is not a valid Microsoft alias, or is not an allowed distribution list.`

## <a name="resolution"></a><span data-ttu-id="9b3f7-105">Megoldás</span><span class="sxs-lookup"><span data-stu-id="9b3f7-105">Resolution</span></span>

<span data-ttu-id="9b3f7-106">Ellenőrizze, hogy az `ms.author` értéke egy érvényes Microsoft-alias.</span><span class="sxs-lookup"><span data-stu-id="9b3f7-106">Verify that the `ms.author` value is a valid Microsoft alias.</span></span> <span data-ttu-id="9b3f7-107">Ha az alias egy terjesztési lista, akkor engedélyezési listán kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9b3f7-107">If the alias is a distribution list, it must also be on the allow list.</span></span>

<span data-ttu-id="9b3f7-108">A terjesztési listák érvényes értékeiről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="9b3f7-108">Valid values for DLs can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
