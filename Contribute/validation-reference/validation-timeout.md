---
title: validation-timeout
description: Magyarázat és megoldás a Docs buildelési validation-timeout (ellenőrzés-időtúllépés) problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 6/5/2019
ms.prod: non-product-specific
ms.openlocfilehash: 00461768491c25b9bafaff6b117a356d9e291e22
ms.sourcegitcommit: 412ce4ab23e758d41947043f1463e96595ba3bfe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67033296"
---
# <a name="validation-timeout"></a><span data-ttu-id="4d043-103">validation-timeout</span><span class="sxs-lookup"><span data-stu-id="4d043-103">validation-timeout</span></span>

## <a name="warning"></a><span data-ttu-id="4d043-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="4d043-104">Warning</span></span>

`The call to the validation service timed out and validation was not completed. This happens when there's an issue with the service and continuing to retry the call could cause build delays. You might have content issues that were not reported. To retry validation, close and re-open your PR, or rebuild your branch via Docs Portal (requires admin permissions). If you need admin help or  If you continue to see this message, file an issue via https://SiteHelp.`

<span data-ttu-id="4d043-105">Néha előfordulhat, hogy az érvényesítési szolgáltatás átmeneti hibái (például a kiszolgáló nem megfelelő állapota) megakadályozza a Docs buildelését abban, hogy sikeresen meghívhassa a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="4d043-105">Sometimes transient issues in the validation service, such as a server in a bad state, prevent Docs Build from successfully calling the service.</span></span> <span data-ttu-id="4d043-106">Néhány próbálkozás után a hívás meghaladja az időkorlátot, és az érvényesítés leáll, hogy elkerülhetőek legyenek a buildelési késések és a buildelési folyamat feltorlódása.</span><span class="sxs-lookup"><span data-stu-id="4d043-106">After several tries, the call times out and validation is canceled to avoid build delays and clogging the build pipeline.</span></span>

## <a name="resolution"></a><span data-ttu-id="4d043-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="4d043-107">Resolution</span></span>

<span data-ttu-id="4d043-108">Ilyen esetben próbálja meg bezárni, majd újra megnyitni a lekéréses kérelmet, vagy manuálisan is újra futtathatja a buildelést a Docs portálon (ez csak a tárház adminisztrátorai számára érhető el).</span><span class="sxs-lookup"><span data-stu-id="4d043-108">Try closing and re-opening your PR, or re-running a manual build via Docs Portal (repo admins only).</span></span> <span data-ttu-id="4d043-109">Gyakran előfordul, hogy a szolgáltatásproblémák maguktól megoldódnak az első újrapróbálkozás után.</span><span class="sxs-lookup"><span data-stu-id="4d043-109">Often service issues clear themselves up after the initial retry.</span></span> <span data-ttu-id="4d043-110">Ha segítségre van szüksége egy rendszergazdától, vagy ha továbbra is hibaüzenet jelenik meg, küldje be a problémát a [https://SiteHelp](https://SiteHelp) oldalon, ha Ön Microsoft-alkalmazott; ha pedig külső közreműködő, akkor segítségkéréshez @ említse meg a szerzőt a lekéréses kérelemben.</span><span class="sxs-lookup"><span data-stu-id="4d043-110">If you need help from an admin or if you continue to get this message, file an issue via [https://SiteHelp](https://SiteHelp) if you're a Microsoft employee, or @ mention the author of an article in your PR for assistance if you're an external contributor.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
