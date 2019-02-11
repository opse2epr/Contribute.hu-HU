---
title: ms-component-deprecated
description: Magyarázat és megoldás a Docs ms-component-deprecated buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4f89571e2d4c50439806fb26b9967a4b7588f4a9
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713154"
---
# <a name="ms-component-deprecated"></a>ms-component-deprecated

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Deprecated attribute: ms.component. Use ms.subservice instead.`

Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja. Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is. Ne használja az `ms.component` attribútumot, mert az a jelen tartalom esetében elavult.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő, majd válasszon egy érvényes `ms.subservice` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
