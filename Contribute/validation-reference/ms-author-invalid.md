---
title: ms-author-invalid
description: Magyarázat és megoldás a Docs ms-author-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 5d4cc6a08c6e70824ee3f7117d58be9c75aa7fa4
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987767"
---
# <a name="ms-author-invalid"></a>ms-author-invalid

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Invalid value for ms.author: '{value}' is not a valid Microsoft alias, or is not an allowed distribution list.`

## <a name="resolution"></a>Megoldás

Ellenőrizze, hogy az `ms.author` értéke egy érvényes Microsoft-alias. Ha az alias egy terjesztési lista, akkor engedélyezési listán kell lennie.

A terjesztési listák érvényes értékeiről [a Microsoft egy belső webhelyén](https://docsmetadatatool.azurewebsites.net/allowlists) tájékozódhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
