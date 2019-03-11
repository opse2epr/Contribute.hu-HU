---
title: snippet-not-found
description: Magyarázat és megoldás a Docs snippet-not-found buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: 82fc2926f5bc2ec01577670b066b88fb59d7ea11
ms.sourcegitcommit: 89eb357721b26710e00d9b8fdab3e7628c34bdb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459096"
---
# <a name="snippet-not-found"></a><span data-ttu-id="59ec1-103">snippet-not-found</span><span class="sxs-lookup"><span data-stu-id="59ec1-103">snippet-not-found</span></span>

## <a name="warning"></a><span data-ttu-id="59ec1-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="59ec1-104">Warning</span></span>

`Code snippet '{snippet path}' not found.`

<span data-ttu-id="59ec1-105">A hivatkozott kódrészlet nem létezik a megadott útvonalon, vagy az útvonal nem érhető el az aktuális fájlból.</span><span class="sxs-lookup"><span data-stu-id="59ec1-105">The code snippet references doesn't exist at the specified path, or the path isn't available from the current file.</span></span>

## <a name="resolution"></a><span data-ttu-id="59ec1-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="59ec1-106">Resolution</span></span>

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

<span data-ttu-id="59ec1-107">Győződjön meg a kódrészlet elérési útjának helyességéről.</span><span class="sxs-lookup"><span data-stu-id="59ec1-107">Ensure that your snippet path is correct.</span></span> <span data-ttu-id="59ec1-108">Ha a kódrészlet az aktuális adattáron kívül van tárolva, akkor ellenőrizze, hogy az adattár függő adattárként van-e konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="59ec1-108">If the snippet is stored outside the current repo, make sure the repo is configured ase a dependent repo.</span></span> <span data-ttu-id="59ec1-109">További információt a Microsoft belső használatára fenntartott, [kódrészletekről szóló cikkben](https://review.docs.microsoft.com/en-us/help/contribute/code-in-docs?branch=master) találhat.</span><span class="sxs-lookup"><span data-stu-id="59ec1-109">For more information, see the Microsoft-internal [code snippet article](https://review.docs.microsoft.com/en-us/help/contribute/code-in-docs?branch=master).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
