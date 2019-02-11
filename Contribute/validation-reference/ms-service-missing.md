---
title: ms-service-missing
description: Magyarázat és megoldás a Docs ms-service-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: 2bc425726f82840565978072b2efdf13a1284ec0
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713085"
---
# <a name="ms-service-missing"></a>ms-service-missing

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Missing attribute: ms.service. If you specify ms.subservice, you must also specify ms.service.`

Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja. Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is, de ha megadja az `ms.subservice` attribútumot, az `ms.service` megadása is kötelező. Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy az Ön által megadott `ms.subservice` érték a cikkének megfelelő, majd adja hozzá a megfelelő `ms.service` értéket, amely érvényes szülőattribútum az `ms.subservice` számára.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
