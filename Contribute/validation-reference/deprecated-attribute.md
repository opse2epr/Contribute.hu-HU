---
title: deprecated-attribute
description: Magyarázat és megoldás a Docs deprecated-attribute buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 113ca759af1765a2a51cadc721fa59743b699475
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636885"
---
# <a name="deprecated-attribute"></a><span data-ttu-id="a5839-103">deprecated-attribute</span><span class="sxs-lookup"><span data-stu-id="a5839-103">deprecated-attribute</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="a5839-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="a5839-104">Suggestion</span></span>

`Deprecated attribute: ms.component. Use ms.subservice instead.`

<span data-ttu-id="a5839-105">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="a5839-105">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="a5839-106">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="a5839-106">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="a5839-107">Ne használja az `ms.component` attribútumot, mert az a jelen tartalom esetében elavult.</span><span class="sxs-lookup"><span data-stu-id="a5839-107">Don't use `ms.component`; it's deprecated for this content.</span></span>

## <a name="resolution"></a><span data-ttu-id="a5839-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="a5839-108">Resolution</span></span>

<span data-ttu-id="a5839-109">Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="a5839-109">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="a5839-110">majd válasszon egy érvényes `ms.subservice` értéket.</span><span class="sxs-lookup"><span data-stu-id="a5839-110">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="a5839-111">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="a5839-111">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
