---
title: ms-prod-and-technology-invalid
description: Magyarázat és megoldás a Docs ms-prod-and-technology-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 92e8b17c3b5c96d544d12d394534a494ada3b901
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713269"
---
# <a name="ms-prod-and-technology-invalid"></a><span data-ttu-id="986f8-103">ms-prod-and-technology-invalid</span><span class="sxs-lookup"><span data-stu-id="986f8-103">ms-prod-and-technology-invalid</span></span>

<span data-ttu-id="986f8-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="986f8-104">**Coming soon!**</span></span>

## <a name="warning"></a><span data-ttu-id="986f8-105">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="986f8-105">Warning</span></span>

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

<span data-ttu-id="986f8-106">Helyszíni termékek megadására használja az `ms.prod` attribútumot.</span><span class="sxs-lookup"><span data-stu-id="986f8-106">Use `ms.prod` to specify on-premises products.</span></span> <span data-ttu-id="986f8-107">Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is.</span><span class="sxs-lookup"><span data-stu-id="986f8-107">To specify more detailed information about `ms.prod`, you can optionally specify `ms.technology`.</span></span> <span data-ttu-id="986f8-108">Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk.</span><span class="sxs-lookup"><span data-stu-id="986f8-108">The values for `ms.prod` and `ms.technology` must be a valid pair.</span></span> <span data-ttu-id="986f8-109">Vagy érvénytelen az `ms.prod` értéke, vagy pedig az `ms.technology` érték nem alkot érvényes párt az `ms.prod` aktuális értékével.</span><span class="sxs-lookup"><span data-stu-id="986f8-109">Either your `ms.prod` value is invalid, or your `ms.technology` value is not a valid pair with your `ms.prod`.</span></span>

## <a name="resolution"></a><span data-ttu-id="986f8-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="986f8-110">Resolution</span></span>

<span data-ttu-id="986f8-111">Győződjön meg arról, hogy cikkének `ms.prod` értéke megfelelő,</span><span class="sxs-lookup"><span data-stu-id="986f8-111">Confirm that your `ms.prod` value is correct for your article.</span></span> <span data-ttu-id="986f8-112">majd válasszon egy érvényes `ms.technology` értéket.</span><span class="sxs-lookup"><span data-stu-id="986f8-112">Then choose a valid `ms.technology` value.</span></span>

<span data-ttu-id="986f8-113">Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="986f8-113">Valid values can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/whitelists).</span></span>

<!-- Can we link to whitelist externally? -->

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
