---
title: ms-prod-service-mismatch
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: a7de44e9930def2d2582194f28695e3ef3940541
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987615"
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

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
