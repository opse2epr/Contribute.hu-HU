---
title: deprecated-attribute
description: Magyarázat és megoldás a Docs deprecated-attribute buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 564bd35c418fb9def6bf20240fca64265a477f46
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987790"
---
# <a name="deprecated-attribute"></a>deprecated-attribute

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Deprecated attribute: ms.component. Use ms.subservice instead.`

Az `ms.service` attribútumot felhőszolgáltatások megadására használhatja. Az `ms.service` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.subservice` attribútumot is. Ne használja az `ms.component` attribútumot, mert az a jelen tartalom esetében elavult.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy cikkének `ms.service` értéke megfelelő, majd válasszon egy érvényes `ms.subservice` értéket.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
