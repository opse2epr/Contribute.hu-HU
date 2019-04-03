---
title: manager-invalid
description: Magyarázat és megoldás a Docs manager-invalid buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 3/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 44174bde29b63bffe709596f9c2d6be994f252a3
ms.sourcegitcommit: 8e897e90268a8a87dc4b97d7c28d22ed5950c8d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58637230"
---
# <a name="manager-invalid"></a>manager-invalid

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Invalid value for manager: '{value}' is not a valid Microsoft alias.`

Egyes tartalomcsoportok a szerző felettesének azonosításához megkövetelik a `manager` attribútumot.

## <a name="resolution"></a>Megoldás

A `manager` értékének egy Microsoft-alkalmazott érvényes aliasával kell egyeznie. Ellenőrizze a szerző felettesének aliasát, és módosítsa az értéket.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
