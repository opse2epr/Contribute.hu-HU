---
title: ms-prod-or-service-missing
description: Magyarázat és megoldás a Docs ms-prod-or-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/20/2018
ms.prod: non-product-specific
ms.openlocfilehash: 6eeb4a95e4d4aeba527b1078bc646fcbc56898a2
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987560"
---
# <a name="ms-prod-or-service-missing"></a>ms-prod-or-service-missing

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Missing attribute: either ms.prod or ms.service is required. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a>Megoldás

Az `ms.prod` vagy az `ms.service` attribútum kötelező, és együtt nem használhatók: az `ms.prod` a helyszíni termékekhez használatos, az `ms.service` pedig felhőszolgáltatásokhoz. Határozza meg, hogy melyik megfelelő a cikkéhez, ellenőrizze, hogy az érték helyes-e, és távolítsa el a másik mezőt.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]