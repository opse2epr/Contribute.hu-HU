---
title: ms-prod-or-service-missing
description: Magyarázat és megoldás a Docs ms-prod-or-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/20/2018
ms.prod: non-product-specific
ms.openlocfilehash: f4d5bc7537ec851ce7ac1de3be2208fd74cbe37f
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713545"
---
# <a name="ms-prod-or-service-missing"></a>ms-prod-or-service-missing

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Missing attribute: either ms.prod or ms.service is required. Use ms.prod for on-premise products, or ms.service for cloud services.`

## <a name="resolution"></a>Megoldás

Az `ms.prod` vagy az `ms.service` attribútum kötelező, és együtt nem használhatók: az `ms.prod` a helyszíni termékekhez használatos, az `ms.service` pedig felhőszolgáltatásokhoz. Határozza meg, hogy melyik megfelelő a cikkéhez, ellenőrizze, hogy az érték helyes-e, és távolítsa el a másik mezőt.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]