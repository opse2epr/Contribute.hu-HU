---
title: ms-prod-missing
description: Magyarázat és megoldás a Docs ms-prod-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/2/2019
ms.prod: non-product-specific
ms.openlocfilehash: ee29396a20345f6884a5bbc94aa25f48dafaff52
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713223"
---
# <a name="ms-prod-missing"></a>ms-prod-missing

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Missing attribute: ms.prod. If you specify ms.technology, you must also specify ms.prod.`

Helyszíni termékek megadására használja az `ms.prod` attribútumot. Az `ms.prod` attribútummal kapcsolatos részletesebb információk megadásához megadhatja az `ms.technology` attribútumot is, de ha megadja az `ms.technology` attribútumot, az `ms.prod` megadása is kötelező. Az `ms.prod` és az `ms.technology` értékeinek érvényes párt kell alkotniuk.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy az Ön által megadott `ms.technology` érték a cikkének megfelelő, majd adja hozzá a megfelelő `ms.prod` értéket, amely érvényes szülőattribútum az `ms.technology` számára.

Az érvényes értékekről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/whitelists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
