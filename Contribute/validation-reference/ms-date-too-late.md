---
title: ms-date-too-late
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: b38392e9f297e4ee4147ca7fc65f938b5cd53403
ms.sourcegitcommit: f374ad2607360f46d88982b4b7ecc63d3ab08235
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/20/2019
ms.locfileid: "56431484"
---
# <a name="ms-date-too-late"></a>ms-date-too-late

**Hamarosan elérhető**

## <a name="warning"></a>Figyelmeztetés

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

Az `ms.date` attribútum a „frissesség” jelzésére szolgál, azaz, hogy mikor ellenőrizték utoljára a cikket a relevancia, a pontosság, a képernyőképek helyessége és a hivatkozások működése szempontjából. Ezért nem lehet jövőbeli dátum. A közzétételi idő figyelembe vétele érdekében öt nap ráhagyás megengedett, például a tartalom minőségbiztosítási célú rögzítésekor egy jelentős esemény előkészítése során.

## <a name="resolution"></a>Megoldás

Adjon meg egy, a mai naptól számított nem több, mint öt napon belüli `ms.date` dátumot HH/NN/ÉÉÉÉ formátumban:

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
