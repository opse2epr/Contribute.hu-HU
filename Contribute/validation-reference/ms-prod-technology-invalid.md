---
title: ms-prod-and-technology-invalid
description: Magyarázat és megoldás a Docs ms-prod-and-technology-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 8c6f12629cf4b8cf7fd2471ef4d1287562435696
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636839"
---
# <a name="ms-prod-and-technology-invalid"></a><span data-ttu-id="b034e-103">ms-prod-and-technology-invalid</span><span class="sxs-lookup"><span data-stu-id="b034e-103">ms-prod-and-technology-invalid</span></span>

## <a name="warning"></a><span data-ttu-id="b034e-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="b034e-104">Warning</span></span>

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

<span data-ttu-id="b034e-105">Helyszíni termékek megadására használja az `ms.prod` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="b034e-105">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="b034e-106">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="b034e-106">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="b034e-107">Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="b034e-107">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span> <span data-ttu-id="b034e-108">Vagy érvénytelen az `ms.prod` értéke, vagy pedig az `ms.technology` érték nem alkot érvényes párt az `ms.prod` aktuális értékével.</span><span class="sxs-lookup"><span data-stu-id="b034e-108">Either your `ms.prod` value is invalid, or your `ms.technology` value is not a valid pair with your `ms.prod`.</span></span>

## <a name="resolution"></a><span data-ttu-id="b034e-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="b034e-109">Resolution</span></span>

<span data-ttu-id="b034e-110">Győződjön meg arról, hogy cikkének `ms.prod` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="b034e-110">Confirm that your `ms.prod` value is correct for your article.</span></span> <span data-ttu-id="b034e-111">majd válasszon egy érvényes `ms.technology` értéket.</span><span class="sxs-lookup"><span data-stu-id="b034e-111">Then choose a valid `ms.technology` value.</span></span>

<span data-ttu-id="b034e-112">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="b034e-112">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
