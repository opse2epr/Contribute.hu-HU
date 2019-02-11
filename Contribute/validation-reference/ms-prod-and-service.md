---
title: ms-prod-and-service
description: Magyarázat és megoldás a Docs ms-prod-and-service buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 42e6f063c8b3d97386b2655b49a19a3e103d6b3b
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713200"
---
# <a name="ms-prod-and-service"></a>ms-prod-and-service

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Both ms.prod and ms.service can't be specified. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a>Megoldás

Az `ms.prod` vagy az `ms.service` attribútum kötelező, és együtt nem használhatók: az `ms.prod` a helyszíni termékekhez használatos, az `ms.service` pedig felhőszolgáltatásokhoz. Határozza meg, hogy melyik megfelelő a cikkéhez, ellenőrizze, hogy az érték helyes-e, és távolítsa el a másik mezőt.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
