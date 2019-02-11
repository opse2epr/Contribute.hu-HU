---
title: ms-component-deprecated
description: Magyarázat és megoldás a Docs ms-component-deprecated buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4f89571e2d4c50439806fb26b9967a4b7588f4a9
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713154"
---
# <a name="ms-component-deprecated"></a><span data-ttu-id="5f099-103">ms-component-deprecated</span><span class="sxs-lookup"><span data-stu-id="5f099-103">ms-component-deprecated</span></span>

<span data-ttu-id="5f099-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="5f099-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="5f099-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="5f099-105">Suggestion</span></span>

`Deprecated attribute: ms.component. Use ms.subservice instead.`

<span data-ttu-id="5f099-106">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="5f099-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="5f099-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="5f099-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="5f099-108">Ne használja az `ms.component` attribútumot, mert az a jelen tartalom esetében elavult.</span><span class="sxs-lookup"><span data-stu-id="5f099-108">Don't use `ms.component`; it's deprecated for this content.</span></span>

## <a name="resolution"></a><span data-ttu-id="5f099-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="5f099-109">Resolution</span></span>

<span data-ttu-id="5f099-110">Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="5f099-110">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="5f099-111">majd válasszon egy érvényes `ms.subservice` értéket.</span><span class="sxs-lookup"><span data-stu-id="5f099-111">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="5f099-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="5f099-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
