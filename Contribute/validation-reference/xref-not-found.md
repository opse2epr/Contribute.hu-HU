---
title: xref-not-found
description: Magyarázat és megoldás a Docs xref-not-found buildelési problémájára
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: d51eace291bfac179be2701463d113c06627f92f
ms.sourcegitcommit: 4053577bd0478d711257a283ee661d618b49c2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57427882"
---
# <a name="xref-not-found"></a>xref-not-found

## <a name="warning"></a>Figyelmeztetés

`Cross reference not found: '<xref: {uid}>'.`

`Cross reference not found: '@{uid}'.`

A hivatkozott UID nem létezik, vagy az adattár számára nem érhető el.

## <a name="resolution"></a>Megoldás

Győződjön meg róla, hogy az UID helyes, és hogy az Xref Service megfelelően, a Microsoft belső használatú [Xref Service](https://review.docs.microsoft.com/en-us/help/onboard/admin/xref-service?branch=master)-dokumentációjában leírtak szerint van konfigurálva az adattárában.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
