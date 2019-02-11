---
title: ms-prod-and-technology-invalid
description: Magyarázat és megoldás a Docs ms-prod-and-technology-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 92e8b17c3b5c96d544d12d394534a494ada3b901
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713269"
---
# <a name="ms-prod-and-technology-invalid"></a>ms-prod-and-technology-invalid

**Hamarosan elérhető**

## <a name="warning"></a>Figyelmeztetés

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

Helyszíni termékek megadására használja az `ms.prod` attribútumot. Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is. Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk. Vagy érvénytelen az `ms.prod` értéke, vagy pedig az `ms.technology` érték nem alkot érvényes párt az `ms.prod` aktuális értékével.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.prod` értéke megfelelő, majd válasszon egy érvényes `ms.technology` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!-- Can we link to whitelist externally? -->

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
