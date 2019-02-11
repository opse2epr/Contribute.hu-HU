---
title: ms-prod-service-mismatch
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4a3cf8bc5435972f0442ca1d41d4147e1ea00d78
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713177"
---
# <a name="ms-prod-service-mismatch"></a>ms-prod-service-mismatch

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Invalid attribute pair: ms.prod and ms.subservice. You can only pair ms.prod with ms.technology.`

`Invalid attribute pair: ms.service and ms.technology. You can only pair ms.service with ms.subservice.`

Helyszíni termékek megadására használja az `ms.prod`, felhőszolgáltatásokéra pedig az `ms.service` attribútumot. Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is. Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is. Az `ms.prod` nem használható az `ms.subservice`, az `ms.service` vagy az `ms.technology` attribútumokkal együtt.

## <a name="resolution"></a>Megoldás

Először győződjön meg róla, hogy a megfelelő szülőattribútumot (`ms.prod` vagy `ms.service`) választotta a cikkhez, majd adja hozzá a megfelelő gyermekmezőt egy érvényes párosított értékkel. Távolítsa el a további mezőket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
