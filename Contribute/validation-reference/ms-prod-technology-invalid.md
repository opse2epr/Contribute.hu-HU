---
title: ms-prod-and-technology-invalid
description: Magyarázat és megoldás a Docs ms-prod-and-technology-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 8c6f12629cf4b8cf7fd2471ef4d1287562435696
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58636839"
---
# <a name="ms-prod-and-technology-invalid"></a>ms-prod-and-technology-invalid

## <a name="warning"></a>Figyelmeztetés

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

Helyszíni termékek megadására használja az `ms.prod` attribútumot. Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is. Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk. Vagy érvénytelen az `ms.prod` értéke, vagy pedig az `ms.technology` érték nem alkot érvényes párt az `ms.prod` aktuális értékével.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.prod` értéke megfelelő, majd válasszon egy érvényes `ms.technology` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
