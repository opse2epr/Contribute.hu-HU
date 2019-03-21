---
title: deprecated-attribute
description: Magyarázat és megoldás a Docs deprecated-attribute buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 564bd35c418fb9def6bf20240fca64265a477f46
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987790"
---
# <a name="deprecated-attribute"></a><span data-ttu-id="1d9da-103">deprecated-attribute</span><span class="sxs-lookup"><span data-stu-id="1d9da-103">deprecated-attribute</span></span>

<span data-ttu-id="1d9da-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="1d9da-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="1d9da-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="1d9da-105">Suggestion</span></span>

`Deprecated attribute: ms.component. Use ms.subservice instead.`

<span data-ttu-id="1d9da-106">Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja.</span><span class="sxs-lookup"><span data-stu-id="1d9da-106">Use `ms.service` to specify cloud services.</span></span> <span data-ttu-id="1d9da-107">Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="1d9da-107">To specify more detailed information about `ms.service`, you can optionally specify `ms.subservice`.</span></span> <span data-ttu-id="1d9da-108">Ne használja az `ms.component` attribútumot, mert az a jelen tartalom esetében elavult.</span><span class="sxs-lookup"><span data-stu-id="1d9da-108">Don't use `ms.component`; it's deprecated for this content.</span></span>

## <a name="resolution"></a><span data-ttu-id="1d9da-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="1d9da-109">Resolution</span></span>

<span data-ttu-id="1d9da-110">Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="1d9da-110">Confirm that your `ms.service` value is correct for your article.</span></span> <span data-ttu-id="1d9da-111">majd válasszon egy érvényes `ms.subservice` értéket.</span><span class="sxs-lookup"><span data-stu-id="1d9da-111">Then choose a valid `ms.subservice` value.</span></span>

<span data-ttu-id="1d9da-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="1d9da-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
