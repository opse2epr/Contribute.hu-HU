---
title: ms-prod-and-technology-invalid
description: Magyarázat és megoldás a Docs ms-prod-and-technology-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 20706a44da0320c1a3fc85592a4636efba364dc7
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987583"
---
# <a name="ms-prod-and-technology-invalid"></a>ms-prod-and-technology-invalid

**Hamarosan elérhető**

## <a name="warning"></a>Figyelmeztetés

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

Helyszíni termékek megadására használja az `ms.prod` attribútumot. Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is. Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk. Vagy érvénytelen az `ms.prod` értéke, vagy pedig az `ms.technology` érték nem alkot érvényes párt az `ms.prod` aktuális értékével.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.prod` értéke megfelelő, majd válasszon egy érvényes `ms.technology` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
