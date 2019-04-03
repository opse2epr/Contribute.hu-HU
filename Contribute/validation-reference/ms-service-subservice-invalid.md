---
title: ms-service-and-subservice-invalid
description: Magyarázat és megoldás a Docs ms-service-and-subservice-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 3f165d16eed7e937c7db912a9c5e0ee0809e3031
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637299"
---
# <a name="ms-service-and-subservice-invalid"></a>ms-service-and-subservice-invalid

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja. Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is. Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk. Vagy érvénytelen az `ms.service` értéke, vagy pedig az `ms.subservice` érték nem alkot érvényes párt az `ms.service` aktuális értékével.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő, majd válasszon egy érvényes `ms.subservice` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
