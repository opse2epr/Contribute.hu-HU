---
title: ms-service-and-subservice-invalid
description: Magyarázat és megoldás a Docs ms-service-and-subservice-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 7dee18e7b902b660a8071bcb4a0dee21c19f4f7f
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987643"
---
# <a name="ms-service-and-subservice-invalid"></a>ms-service-and-subservice-invalid

**Hamarosan elérhető**

## <a name="warning"></a>Figyelmeztetés

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja. Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is. Az `ms.service` és az `ms.subservice` értékeinek érvényes párt kell alkotniuk. Vagy érvénytelen az `ms.service` értéke, vagy pedig az `ms.subservice` érték nem alkot érvényes párt az `ms.service` aktuális értékével.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő, majd válasszon egy érvényes `ms.subservice` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
