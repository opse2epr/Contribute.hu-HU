---
title: manager-invalid
description: Magyarázat és megoldás a Docs manager-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 3/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 7eac188b16b402767bbec551a6dec8b5877680af
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427398"
---
# <a name="manager-invalid"></a><span data-ttu-id="26e50-103">manager-invalid</span><span class="sxs-lookup"><span data-stu-id="26e50-103">manager-invalid</span></span>

<span data-ttu-id="26e50-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="26e50-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="26e50-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="26e50-105">Suggestion</span></span>

`Invalid value for manager: '{value}' is not a valid Microsoft alias.`

<span data-ttu-id="26e50-106">Egyes tartalomcsoportok a szerző felettesének azonosításához megkövetelik a `manager` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="26e50-106">Some content groups require the `manager` attribute to identify the author's manager.</span></span>

## <a name="resolution"></a><span data-ttu-id="26e50-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="26e50-107">Resolution</span></span>

<span data-ttu-id="26e50-108">A `manager` értékének egy Microsoft-alkalmazott érvényes aliasával kell egyeznie.</span><span class="sxs-lookup"><span data-stu-id="26e50-108">The value of `manager` must be a valid alias for an individual Microsoft employee.</span></span> <span data-ttu-id="26e50-109">Ellenőrizze a szerző felettesének aliasát, és módosítsa az értéket.</span><span class="sxs-lookup"><span data-stu-id="26e50-109">Verify the author's manager's alias and update the value.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
