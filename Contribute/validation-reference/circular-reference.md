---
title: circular-reference
description: Magyarázat és megoldás a Docs circular-reference buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4600465cf940efa82c61bcbac4a1d912c16e6903
ms.sourcegitcommit: 89eb357721b26710e00d9b8fdab3e7628c34bdb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459211"
---
# <a name="circular-reference"></a>circular-reference

## <a name="error"></a>Hiba

`Files '{file name 1}' and '{file name 2}' reference each other.`

Ez lehet például egy beágyazott fájl, amely az aktuális fájlra hivatkozik, vagy egy olyan fájlra mutató hivatkozás, amely az aktuális fájlra lett átirányítva.

## <a name="resolution"></a>Megoldás

Vizsgálja meg a fájlokban lévő hivatkozásokat, és végezze el az ahhoz szükséges módosításokat, hogy egy fájl se hivatkozzon önmagára, vagy tartalmazza önmagát.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
