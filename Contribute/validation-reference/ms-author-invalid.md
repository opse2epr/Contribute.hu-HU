---
title: ms-author-invalid
description: Magyarázat és megoldás a Docs ms-author-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 5d4cc6a08c6e70824ee3f7117d58be9c75aa7fa4
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987767"
---
# <a name="ms-author-invalid"></a><span data-ttu-id="599d1-103">ms-author-invalid</span><span class="sxs-lookup"><span data-stu-id="599d1-103">ms-author-invalid</span></span>

<span data-ttu-id="599d1-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="599d1-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="599d1-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="599d1-105">Suggestion</span></span>

`Invalid value for ms.author: '{value}' is not a valid Microsoft alias, or is not an allowed distribution list.`

## <a name="resolution"></a><span data-ttu-id="599d1-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="599d1-106">Resolution</span></span>

<span data-ttu-id="599d1-107">Ellenőrizze, hogy az `ms.author` értéke egy érvényes Microsoft-alias.</span><span class="sxs-lookup"><span data-stu-id="599d1-107">Verify that the `ms.author` value is a valid Microsoft alias.</span></span> <span data-ttu-id="599d1-108">Ha az alias egy terjesztési lista, akkor engedélyezési listán kell lennie.</span><span class="sxs-lookup"><span data-stu-id="599d1-108">If the alias is a distribution list, it must also be on the allow list.</span></span>

<span data-ttu-id="599d1-109">A terjesztési listák érvényes értékeiről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="599d1-109">Valid values for DLs can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
