---
title: circular-reference
description: Magyarázat és megoldás a Docs circular-reference buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4600465cf940efa82c61bcbac4a1d912c16e6903
ms.sourcegitcommit: 89eb357721b26710e00d9b8fdab3e7628c34bdb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459211"
---
# <a name="circular-reference"></a><span data-ttu-id="642ef-103">circular-reference</span><span class="sxs-lookup"><span data-stu-id="642ef-103">circular-reference</span></span>

## <a name="error"></a><span data-ttu-id="642ef-104">Hiba</span><span class="sxs-lookup"><span data-stu-id="642ef-104">Error</span></span>

`Files '{file name 1}' and '{file name 2}' reference each other.`

<span data-ttu-id="642ef-105">Ez lehet például egy beágyazott fájl, amely az aktuális fájlra hivatkozik, vagy egy olyan fájlra mutató hivatkozás, amely az aktuális fájlra lett átirányítva.</span><span class="sxs-lookup"><span data-stu-id="642ef-105">For example, this might be an included file that links to the current file, or a link to a file that's been redirected to the current file.</span></span>

## <a name="resolution"></a><span data-ttu-id="642ef-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="642ef-106">Resolution</span></span>

<span data-ttu-id="642ef-107">Vizsgálja meg a fájlokban lévő hivatkozásokat, és végezze el az ahhoz szükséges módosításokat, hogy egy fájl se hivatkozzon önmagára, vagy tartalmazza önmagát.</span><span class="sxs-lookup"><span data-stu-id="642ef-107">Review the links in the files and make necessary edits so no file links to or includes itself.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
