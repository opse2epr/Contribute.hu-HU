---
title: ms-author-invalid
description: Magyarázat és megoldás a Docs ms-author-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 210ff6a18bd12585c81f461a87238aa8d20c0530
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427860"
---
# <a name="ms-author-invalid"></a><span data-ttu-id="ac795-103">ms-author-invalid</span><span class="sxs-lookup"><span data-stu-id="ac795-103">ms-author-invalid</span></span>

<span data-ttu-id="ac795-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="ac795-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="ac795-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="ac795-105">Suggestion</span></span>

`Invalid value for ms.author: '{value}' is not a valid Microsoft alias, or is not a whitelisted distribution list.`

## <a name="resolution"></a><span data-ttu-id="ac795-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="ac795-106">Resolution</span></span>

<span data-ttu-id="ac795-107">Ellenőrizze, hogy az `ms.author` értéke egy érvényes Microsoft-alias.</span><span class="sxs-lookup"><span data-stu-id="ac795-107">Verify that the `ms.author` value is a valid Microsoft alias.</span></span> <span data-ttu-id="ac795-108">Ha az alias egy terjesztési lista, akkor engedélyezési listán kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ac795-108">If the alias is a distribution list, it must also be whitelisted.</span></span>

<span data-ttu-id="ac795-109">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="ac795-109">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
