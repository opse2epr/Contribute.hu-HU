---
title: hard-coded-locale
description: Magyarázat és megoldás a Docs hard-coded-locale buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 1862014076fa4cbff18535095b244e8f94a17b0f
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427408"
---
# <a name="hard-coded-locale"></a><span data-ttu-id="64ddd-103">hard-coded-locale</span><span class="sxs-lookup"><span data-stu-id="64ddd-103">hard-coded-locale</span></span>

## <a name="warning"></a><span data-ttu-id="64ddd-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="64ddd-104">Warning</span></span>

`Link {URL} contains locale code {code}. For localizability, remove {code} from links to Microsoft sites.`

<span data-ttu-id="64ddd-105">A nyelvterületkódok, például az `en-us` Microsoft bizonyos webhelyeire mutató hivatkozásokba történő belefoglalása nem javasolt.</span><span class="sxs-lookup"><span data-stu-id="64ddd-105">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="64ddd-106">Ha egy angol nyelvű tartalomban található hivatkozásba foglalja bele a nyelvterületkódot, akkor a honosított hivatkozásokban is meg fog jelenni, ami rontja a honosítás összhatását.</span><span class="sxs-lookup"><span data-stu-id="64ddd-106">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="64ddd-107">Például, ha egy német nyelvű honosított tartalomban szerepel az `en-us`, akkor a német ügyfeleket is az angol cikkhez fogja irányítani a hivatkozás, még akkor is, ha a cikk németül is elérhető.</span><span class="sxs-lookup"><span data-stu-id="64ddd-107">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="64ddd-108">A következő oldalak tartoznak az ellenőrzés hatáskörébe:</span><span class="sxs-lookup"><span data-stu-id="64ddd-108">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="64ddd-109">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="64ddd-109">azure.microsoft.com</span></span>
- <span data-ttu-id="64ddd-110">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="64ddd-110">docs.microsoft.com</span></span>
- <span data-ttu-id="64ddd-111">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="64ddd-111">msdn.microsoft.com</span></span>
- <span data-ttu-id="64ddd-112">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="64ddd-112">technet.microsoft.com</span></span>

## <a name="resolution"></a><span data-ttu-id="64ddd-113">Megoldás</span><span class="sxs-lookup"><span data-stu-id="64ddd-113">Resolution</span></span>

<span data-ttu-id="64ddd-114">Távolítsa el a Microsoft webhelyeire mutató hivatkozásokból a nyelvterületkódokat.</span><span class="sxs-lookup"><span data-stu-id="64ddd-114">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="64ddd-115">Például:</span><span class="sxs-lookup"><span data-stu-id="64ddd-115">The following is an example.</span></span>

<span data-ttu-id="64ddd-116">Előtte:</span><span class="sxs-lookup"><span data-stu-id="64ddd-116">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="64ddd-117">Utána:</span><span class="sxs-lookup"><span data-stu-id="64ddd-117">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]