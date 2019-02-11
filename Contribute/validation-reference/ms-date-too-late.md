---
title: ms-date-too-late
description: Magyarázat és megoldás a Docs ms-date-too-late buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 863b13e55c2aaa2057920e3bd77ec75ab5945277
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713108"
---
# <a name="ms-date-too-late"></a>ms-date-too-late

**Hamarosan elérhető**

## <a name="warning"></a>Figyelmeztetés

`Invalid value for ms.date. The freshness date can't be more than five days in the future.`

Az `ms.date` attribútum a „frissesség” jelzésére szolgál, azaz, hogy mikor ellenőrizték utoljára a cikket a relevancia, a pontosság, a képernyőképek helyessége és a hivatkozások működése szempontjából. Ezért nem lehet jövőbeli dátum. A közzétételi idő figyelembe vétele érdekében öt nap ráhagyás megengedett, például a tartalom minőségbiztosítási célú rögzítésekor egy jelentős esemény előkészítése során.

## <a name="resolution"></a>Megoldás

Adjon meg egy, a mai naptól számított nem több, mint öt napon belüli `ms.date` dátumot HH/NN/ÉÉÉÉ formátumban.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
