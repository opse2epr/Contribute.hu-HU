---
author: meganbradley
ms.author: mbradley
ms.date: 03/29/2019
title: Területi beállításokhoz kötődő hivatkozások
ms.openlocfilehash: f42a26da45b48972bfc595cb26c67ab0acfe8603
ms.sourcegitcommit: 1e53d17639277bebd89b2e7cabeb45bdad526354
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2019
ms.locfileid: "66841256"
---
# <a name="locale-specific-links"></a><span data-ttu-id="cdce0-102">Területi beállításokhoz kötődő hivatkozások</span><span class="sxs-lookup"><span data-stu-id="cdce0-102">Locale-specific links</span></span>

<span data-ttu-id="cdce0-103">A nyelvterületkódok, például az `en-us` Microsoft bizonyos webhelyeire mutató hivatkozásokba történő belefoglalása nem javasolt.</span><span class="sxs-lookup"><span data-stu-id="cdce0-103">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="cdce0-104">Ha egy angol nyelvű tartalomban található hivatkozásba foglalja bele a nyelvterületkódot, akkor a honosított hivatkozásokban is meg fog jelenni, ami rontja a honosítás összhatását.</span><span class="sxs-lookup"><span data-stu-id="cdce0-104">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="cdce0-105">Például, ha egy német nyelvű honosított tartalomban szerepel az `en-us`, akkor a német ügyfeleket is az angol cikkhez fogja irányítani a hivatkozás, még akkor is, ha a cikk németül is elérhető.</span><span class="sxs-lookup"><span data-stu-id="cdce0-105">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="cdce0-106">Távolítsa el a Microsoft webhelyeire mutató hivatkozásokból a nyelvterületkódokat.</span><span class="sxs-lookup"><span data-stu-id="cdce0-106">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="cdce0-107">Például:</span><span class="sxs-lookup"><span data-stu-id="cdce0-107">The following is an example.</span></span>

<span data-ttu-id="cdce0-108">Előtte:</span><span class="sxs-lookup"><span data-stu-id="cdce0-108">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="cdce0-109">Utána:</span><span class="sxs-lookup"><span data-stu-id="cdce0-109">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="cdce0-110">A következő oldalak tartoznak az ellenőrzés hatáskörébe:</span><span class="sxs-lookup"><span data-stu-id="cdce0-110">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="cdce0-111">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdce0-111">azure.microsoft.com</span></span>
- <span data-ttu-id="cdce0-112">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdce0-112">docs.microsoft.com</span></span>
- <span data-ttu-id="cdce0-113">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdce0-113">msdn.microsoft.com</span></span>
- <span data-ttu-id="cdce0-114">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdce0-114">technet.microsoft.com</span></span>