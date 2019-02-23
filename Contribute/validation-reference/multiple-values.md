---
title: multiple-values
description: Magyarázat és megoldás a Docs multiple-values buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/19/2019
ms.prod: non-product-specific
ms.openlocfilehash: 8cee25b07e5bd1e019f8d270888eff73292d8e7c
ms.sourcegitcommit: ae71ca811c143deb6214147c7eea8704444a6093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56465116"
---
# <a name="multiple-values"></a>multiple-values

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Single-valued attribute {attribute} has multiple values. Remove additional values.`

Egynél több értéket adott meg egy olyan attribútumhoz, amelyhez csak egy érték engedélyezett.

`Single-valued attribute {attribute} is in multi-valued array format. Change to scalar format.`

Az egynél több értéket nem engedélyező attribútumokat egyértékes (skaláris) YML-formátumban kell megadni.

## <a name="resolution"></a>Megoldás

Ezt a javaslatot akkor kapja, ha többértékes tömböt használ egy egyértékes attribútumhoz akár több értéket, akár egy értéket tartalmaz a tömb.

A YML az alábbi tömbtípusokat támogatja a többértékes attribútumok esetén, amilyen például az `ms.custom`:

```yml
---
# comma-separated bracketed list:
ms.custom: [WIP, generated-via-CI]

# each value on its own line:
ms.custom:
  - WIP
  - generated-via-CI
---
```

Ezek a formátumok nem érvényesek az egyértékes attribútumok esetén, amilyen például az `author`.

Ha több értéket adott meg, ellenőrizze a megadott értékeket, és válassza ki azt, amelyik helyes. Távolítsa el a többi értéket, és adja meg az egyetlen értéket ugyanabban a sorban, amelyben az attribútum szerepel, és ne használjon zárójelet, ahogy alább látható:

```yml
---
author: meganbradley
---
```

Ha egyértékes tömbje van, módosítsa azt skaláris formátumra (lásd fent).

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
