---
title: manager-invalid
description: Magyarázat és megoldás a Docs manager-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 3/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 44174bde29b63bffe709596f9c2d6be994f252a3
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637230"
---
# <a name="manager-invalid"></a><span data-ttu-id="c0d7f-103">manager-invalid</span><span class="sxs-lookup"><span data-stu-id="c0d7f-103">manager-invalid</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="c0d7f-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="c0d7f-104">Suggestion</span></span>

`Invalid value for manager: '{value}' is not a valid Microsoft alias.`

<span data-ttu-id="c0d7f-105">Egyes tartalomcsoportok a szerző felettesének azonosításához megkövetelik a `manager` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="c0d7f-105">Some content groups require the `manager` attribute to identify the author's manager.</span></span>

## <a name="resolution"></a><span data-ttu-id="c0d7f-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="c0d7f-106">Resolution</span></span>

<span data-ttu-id="c0d7f-107">A `manager` értékének egy Microsoft-alkalmazott érvényes aliasával kell egyeznie.</span><span class="sxs-lookup"><span data-stu-id="c0d7f-107">The value of `manager` must be a valid alias for an individual Microsoft employee.</span></span> <span data-ttu-id="c0d7f-108">Ellenőrizze a szerző felettesének aliasát, és módosítsa az értéket.</span><span class="sxs-lookup"><span data-stu-id="c0d7f-108">Verify the author's manager's alias and update the value.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
