---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084530"
---
# <a name="docs-pr-validation-service"></a><span data-ttu-id="c8a40-101">Dokumentumok PR-érvényesítési szolgáltatása</span><span class="sxs-lookup"><span data-stu-id="c8a40-101">Docs PR validation service</span></span>

<span data-ttu-id="c8a40-102">A Dokumentumok PR-érvényesítési szolgáltatása egy olyan GitHub-alkalmazás, amely érvényesítési szabályokat futtat egy PR-ben szereplő fájlokon.</span><span class="sxs-lookup"><span data-stu-id="c8a40-102">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span>

<span data-ttu-id="c8a40-103">Ha az érvényesítési szolgáltatás engedélyezve van egy adattáron, az alábbi működés figyelhető meg:</span><span class="sxs-lookup"><span data-stu-id="c8a40-103">When the validation service is enabled on a repo, you'll see the following behavior:</span></span>

1. <span data-ttu-id="c8a40-104">Ön elküld egy PR-t.</span><span class="sxs-lookup"><span data-stu-id="c8a40-104">You submit a PR.</span></span>
1. <span data-ttu-id="c8a40-105">A PR állapotát jelző GitHub-hozzászólásban az adattáron engedélyezett „ellenőrzések” állapota látható.</span><span class="sxs-lookup"><span data-stu-id="c8a40-105">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="c8a40-106">Ebben a példában kétféle ellenőrzés van engedélyezve: a „Commit Validation” és az „OpenPublishing.Build”:</span><span class="sxs-lookup"><span data-stu-id="c8a40-106">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![egyes ellenőrzések sikertelenek](media/validation-failed.png)

   <span data-ttu-id="c8a40-108">A build akkor is megfelelhet az ellenőrzésen, ha a véglegesítés érvényesítése nem sikerül.</span><span class="sxs-lookup"><span data-stu-id="c8a40-108">Build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="c8a40-109">További információkért kattintson a **Részletek** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8a40-109">Click **Details** for more information.</span></span>
1. <span data-ttu-id="c8a40-110">A Részletek lapon megjelenik az összes érvényesítési ellenőrzés, azok mellett pedig a problémák kijavításával kapcsolatos információk szerepelnek:</span><span class="sxs-lookup"><span data-stu-id="c8a40-110">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues:</span></span>

   ![érvényesítési üzenet](media/validation-details.png)

<span data-ttu-id="c8a40-112">A szolgáltatásban aktuálisan engedélyezett érvényesítési műveletek listája a cikk bal oldali tartalomjegyzékében található.</span><span class="sxs-lookup"><span data-stu-id="c8a40-112">See the left-hand TOC of this article for the list of validations currently in the service.</span></span>