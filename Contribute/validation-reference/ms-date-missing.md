---
title: ms-date-missing
description: Magyarázat és megoldás a Docs ms-date-missing buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: f5603dee7efe5c7ce3eaa4fa944031d94a9283d8
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55713246"
---
# <a name="ms-date-missing"></a>ms-date-missing

**Hamarosan elérhető**

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>Javaslat

`Missing attribute: ms.date. A freshness date is required for this content. Add a date in format MM/DD/YYYY.`

A dátum a „frissesség” jelzésére szolgál, azaz, hogy mikor ellenőrizték utoljára a cikket a relevancia, a pontosság, a képernyőképek helyessége és a hivatkozások működése szempontjából. Ez nem ugyanaz, mint a cikk *közzétételének* utolsó dátuma, amely akkor jelenik meg az oldalon, ha az `ms.date` nincs explicit módon megadva.

## <a name="resolution"></a>Megoldás

Ellenőrizze a cikk naprakészségét és a tartalom helyességét, majd adjon hozzá érvényes dátumot HH/NN/ÉÉÉÉ formátumban.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
