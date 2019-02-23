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
# <a name="multiple-values"></a><span data-ttu-id="9e1d6-103">multiple-values</span><span class="sxs-lookup"><span data-stu-id="9e1d6-103">multiple-values</span></span>

<span data-ttu-id="9e1d6-104">**Hamarosan elérhető**</span><span class="sxs-lookup"><span data-stu-id="9e1d6-104">**Coming soon!**</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="9e1d6-105">Javaslat</span><span class="sxs-lookup"><span data-stu-id="9e1d6-105">Suggestion</span></span>

`Single-valued attribute {attribute} has multiple values. Remove additional values.`

<span data-ttu-id="9e1d6-106">Egynél több értéket adott meg egy olyan attribútumhoz, amelyhez csak egy érték engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-106">You specified more than one value for an attribute that is ony allowed one value.</span></span>

`Single-valued attribute {attribute} is in multi-valued array format. Change to scalar format.`

<span data-ttu-id="9e1d6-107">Az egynél több értéket nem engedélyező attribútumokat egyértékes (skaláris) YML-formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-107">Attributes that aren't allowed to have more than one value must be specified in the single-valued (scalar) YML format.</span></span>

## <a name="resolution"></a><span data-ttu-id="9e1d6-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="9e1d6-108">Resolution</span></span>

<span data-ttu-id="9e1d6-109">Ezt a javaslatot akkor kapja, ha többértékes tömböt használ egy egyértékes attribútumhoz akár több értéket, akár egy értéket tartalmaz a tömb.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-109">You get this Suggestion any time a multi-valued array is used for a single-valued attribute, either with multiple values or a single value in the array.</span></span>

<span data-ttu-id="9e1d6-110">A YML az alábbi tömbtípusokat támogatja a többértékes attribútumok esetén, amilyen például az `ms.custom`:</span><span class="sxs-lookup"><span data-stu-id="9e1d6-110">YML supports the following array formats for multi-valued attributes, such as `ms.custom`:</span></span>

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

<span data-ttu-id="9e1d6-111">Ezek a formátumok nem érvényesek az egyértékes attribútumok esetén, amilyen például az `author`.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-111">These formats aren't valid for single-valued attributes, such as `author`.</span></span>

<span data-ttu-id="9e1d6-112">Ha több értéket adott meg, ellenőrizze a megadott értékeket, és válassza ki azt, amelyik helyes.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-112">If you specified multiple values, review the specified values and determine which is correct.</span></span> <span data-ttu-id="9e1d6-113">Távolítsa el a többi értéket, és adja meg az egyetlen értéket ugyanabban a sorban, amelyben az attribútum szerepel, és ne használjon zárójelet, ahogy alább látható:</span><span class="sxs-lookup"><span data-stu-id="9e1d6-113">Remove other values and specify the single value on the same line as the attribute with no brackets, as follows:</span></span>

```yml
---
author: meganbradley
---
```

<span data-ttu-id="9e1d6-114">Ha egyértékes tömbje van, módosítsa azt skaláris formátumra (lásd fent).</span><span class="sxs-lookup"><span data-stu-id="9e1d6-114">If you have a single-valued array, change it to the scalar format above.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
