---
title: snippet-not-found
description: Magyarázat és megoldás a Docs snippet-not-found buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: 82fc2926f5bc2ec01577670b066b88fb59d7ea11
ms.sourcegitcommit: 89eb357721b26710e00d9b8fdab3e7628c34bdb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459096"
---
# <a name="snippet-not-found"></a>snippet-not-found

## <a name="warning"></a>Figyelmeztetés

`Code snippet '{snippet path}' not found.`

A hivatkozott kódrészlet nem létezik a megadott útvonalon, vagy az útvonal nem érhető el az aktuális fájlból.

## <a name="resolution"></a>Megoldás

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

Győződjön meg a kódrészlet elérési útjának helyességéről. Ha a kódrészlet az aktuális adattáron kívül van tárolva, akkor ellenőrizze, hogy az adattár függő adattárként van-e konfigurálva. További információt a Microsoft belső használatára fenntartott, [kódrészletekről szóló cikkben](https://review.docs.microsoft.com/en-us/help/contribute/code-in-docs?branch=master) találhat.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
