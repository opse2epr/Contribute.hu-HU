---
title: validation-timeout
description: Magyarázat és megoldás a Docs buildelési validation-timeout (ellenőrzés-időtúllépés) problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 6/5/2019
ms.prod: non-product-specific
ms.openlocfilehash: 018634b1c5fba0848fb36a70d81c46be9acf2ecd
ms.sourcegitcommit: 1e53d17639277bebd89b2e7cabeb45bdad526354
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67024210"
---
# <a name="validation-timeout"></a>validation-timeout

## <a name="warning"></a>Figyelmeztetés

`The call to the validation service timed out and validation was not completed. This happens when there's an issue with the service and continuing to retry the call could cause build delays. You might have content issues that were not reported. To retry validation, close and open your PR. If you continue to see this message, file an issue via https://SiteHelp.`

Néha előfordulhat, hogy az érvényesítési szolgáltatás átmeneti hibái (például a kiszolgáló nem megfelelő állapota) megakadályozza a Docs buildelését abban, hogy sikeresen meghívhassa a szolgáltatást. Három próbálkozás után a hívás meghaladja az időkorlátot, és az érvényesítés leáll, hogy elkerülhetőek legyenek a buildelési késések és a buildelési folyamat feltorlódása.

## <a name="resolution"></a>Megoldás

Ilyen esetben próbálja meg bezárni, majd újra megnyitni a lekéréses kérelmet, vagy manuálisan is újra futtathatja a buildelést (ez csak a tárház adminisztrátorai számára érhető el). Gyakran előfordul, hogy a szolgáltatásproblémák maguktól megoldódnak az első újrapróbálkozás után. Ha továbbra is hibaüzenet jelenik meg, küldje be a problémát a [https://SiteHelp](https://SiteHelp) oldalon, ha Ön Microsoft-alkalmazott; ha pedig külső közreműködő, akkor segítségkéréshez @ említse meg a szerzőt a lekéréses kérelemben.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
