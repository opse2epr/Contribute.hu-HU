---
title: multiple-values
description: Magyarázat és megoldás a Docs multiple-values buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/19/2019
ms.prod: non-product-specific
ms.openlocfilehash: 479472abfb771ae5b4dc77cab2bf94633f3ead5c
ms.sourcegitcommit: fdaff82fec769f4ce9153ff1e0f968d3ea97a76d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899659"
---
# <a name="multiple-values"></a><span data-ttu-id="11c95-103">multiple-values</span><span class="sxs-lookup"><span data-stu-id="11c95-103">multiple-values</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="11c95-104">Javaslat</span><span class="sxs-lookup"><span data-stu-id="11c95-104">Suggestion</span></span>

`Single-valued attribute {attribute} has multiple values. Remove additional values.`

<span data-ttu-id="11c95-105">Egynél több értéket adott meg egy olyan attribútumhoz, amelyhez csak egy érték engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="11c95-105">You specified more than one value for an attribute that is ony allowed one value.</span></span>

`Single-valued attribute {attribute} is in multi-valued array format. Change to scalar format.`

<span data-ttu-id="11c95-106">Az egynél több értéket nem engedélyező attribútumokat egyértékes (skaláris) YML-formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="11c95-106">Attributes that aren't allowed to have more than one value must be specified in the single-valued (scalar) YML format.</span></span>

## <a name="resolution"></a><span data-ttu-id="11c95-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="11c95-107">Resolution</span></span>

<span data-ttu-id="11c95-108">Ezt a javaslatot akkor kapja, ha többértékes tömböt használ egy egyértékes attribútumhoz akár több értéket, akár egy értéket tartalmaz a tömb.</span><span class="sxs-lookup"><span data-stu-id="11c95-108">You get this Suggestion any time a multi-valued array is used for a single-valued attribute, either with multiple values or a single value in the array.</span></span>

<span data-ttu-id="11c95-109">A YML az alábbi tömbtípusokat támogatja a többértékes attribútumok esetén, amilyen például az `ms.custom`:</span><span class="sxs-lookup"><span data-stu-id="11c95-109">YML supports the following array formats for multi-valued attributes, such as `ms.custom`:</span></span>

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

<span data-ttu-id="11c95-110">Ezek a formátumok nem érvényesek az egyértékes attribútumok esetén, amilyen például az `author`.</span><span class="sxs-lookup"><span data-stu-id="11c95-110">These formats aren't valid for single-valued attributes, such as `author`.</span></span>

<span data-ttu-id="11c95-111">Ha több értéket adott meg, ellenőrizze a megadott értékeket, és válassza ki azt, amelyik helyes.</span><span class="sxs-lookup"><span data-stu-id="11c95-111">If you specified multiple values, review the specified values and determine which is correct.</span></span> <span data-ttu-id="11c95-112">Távolítsa el a többi értéket, és adja meg az egyetlen értéket ugyanabban a sorban, amelyben az attribútum szerepel, és ne használjon zárójelet, ahogy alább látható:</span><span class="sxs-lookup"><span data-stu-id="11c95-112">Remove other values and specify the single value on the same line as the attribute with no brackets, as follows:</span></span>

```yml
---
author: meganbradley
---
```

<span data-ttu-id="11c95-113">Ha egyértékes tömbje van, módosítsa azt skaláris formátumra (lásd fent).</span><span class="sxs-lookup"><span data-stu-id="11c95-113">If you have a single-valued array, change it to the scalar format above.</span></span>

## <a name="attributes-in-scope"></a><span data-ttu-id="11c95-114">Érvényes attribútumok</span><span class="sxs-lookup"><span data-stu-id="11c95-114">Attributes in scope</span></span>

<span data-ttu-id="11c95-115">Az alábbi attribútumoknak egyértékűnek kell lenniük:</span><span class="sxs-lookup"><span data-stu-id="11c95-115">The following attributes are required to be single-valued:</span></span>

- `author`
- `ms.author`
- `ms.date`
- `ms.prod`
- `ms.service`
- `ms.subservice`
- `ms.technology`
- `ms.topic`
- `title`

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
