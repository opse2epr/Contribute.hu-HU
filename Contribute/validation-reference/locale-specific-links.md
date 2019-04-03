---
author: meganbradley
ms.author: mbradley
ms.date: 03/29/2019
ms.openlocfilehash: a3b383021046412620c616882b19cb06f4dc59f8
ms.sourcegitcommit: af37d44eb67daa2841959817cd205ec95db18cec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653551"
---
# <a name="locale-specific-links"></a><span data-ttu-id="3604e-101">Területi beállításokhoz kötődő hivatkozások</span><span class="sxs-lookup"><span data-stu-id="3604e-101">Locale-specific links</span></span>

<span data-ttu-id="3604e-102">A nyelvterületkódok, például az `en-us` Microsoft bizonyos webhelyeire mutató hivatkozásokba történő belefoglalása nem javasolt.</span><span class="sxs-lookup"><span data-stu-id="3604e-102">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="3604e-103">Ha egy angol nyelvű tartalomban található hivatkozásba foglalja bele a nyelvterületkódot, akkor a honosított hivatkozásokban is meg fog jelenni, ami rontja a honosítás összhatását.</span><span class="sxs-lookup"><span data-stu-id="3604e-103">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="3604e-104">Például, ha egy német nyelvű honosított tartalomban szerepel az `en-us`, akkor a német ügyfeleket is az angol cikkhez fogja irányítani a hivatkozás, még akkor is, ha a cikk németül is elérhető.</span><span class="sxs-lookup"><span data-stu-id="3604e-104">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="3604e-105">Távolítsa el a Microsoft webhelyeire mutató hivatkozásokból a nyelvterületkódokat.</span><span class="sxs-lookup"><span data-stu-id="3604e-105">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="3604e-106">Például:</span><span class="sxs-lookup"><span data-stu-id="3604e-106">The following is an example.</span></span>

<span data-ttu-id="3604e-107">Előtte:</span><span class="sxs-lookup"><span data-stu-id="3604e-107">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="3604e-108">Utána:</span><span class="sxs-lookup"><span data-stu-id="3604e-108">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="3604e-109">A következő oldalak tartoznak az ellenőrzés hatáskörébe:</span><span class="sxs-lookup"><span data-stu-id="3604e-109">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="3604e-110">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3604e-110">azure.microsoft.com</span></span>
- <span data-ttu-id="3604e-111">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3604e-111">docs.microsoft.com</span></span>
- <span data-ttu-id="3604e-112">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3604e-112">msdn.microsoft.com</span></span>
- <span data-ttu-id="3604e-113">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3604e-113">technet.microsoft.com</span></span>