---
title: h1-missing
description: Magyarázat és megoldás a Docs h1-missing buildelési problémájára.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: c920cc0f12a9fac41b640957d45452a7958d4b07
ms.sourcegitcommit: 89eb357721b26710e00d9b8fdab3e7628c34bdb6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459119"
---
# <a name="h1-missing"></a>h1-missing

## <a name="warning"></a>Figyelmeztetés

`H1 is required. Use a single hash (#) followed by a space to create your top-level heading.`

H1 a Markdown-fájl első fejlécét jelöli. A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg. H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.

## <a name="resolution"></a>Megoldás

A probléma megoldásához adjon meg egy H1 fejlécet az YML metaadatblokk utáni első tartalomként a fájlban:

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

> [!NOTE]
> Ez a szabály beágyazott fájlokra nem vonatkozik. Ha beágyazott fájlokra vonatkozó H1-figyelmeztetéseket kap, akkor valószínűleg egy `includes` mappába kell áthelyeznie a beágyazott fájlokat. Az `includes` mappa a fájl elérési útvonalának bármelyik szintjén lehet. A Docs-build az útvonal alapján beágyazott fájlként ismeri fel a fájlt, és nem futnak el a H1-ellenőrzések.

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]