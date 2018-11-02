---
title: Markdown-fejlécek
description: Bemutatja a Markdown-fejlécekre vonatkozó követelményeket.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 05/03/2017
ms.openlocfilehash: 18beb815fdf7caad3e8e675e8d79853d8a5688f2
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084490"
---
# <a name="markdown-headings"></a>Markdown-fejlécek

Az OPS Markdown-fájljaiban szereplő fejlécekre az alábbi ellenőrzési követelmények vonatkoznak.

## <a name="h1"></a>H1

A `H1` a Markdown-fájl első fejlécét jelöli. A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg.

H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (`#`), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét. Például a cikkben szereplő H1 fejléc a következő:

```md
# Markdown headings
```

A H1 fejlécekre a következő szabályok vonatkoznak:

- A fájlban szerepelnie kell egy H1 fejlécnek.
- Egyszerre csak egy H1 fejléc szerepelhet benne.
- A H1-nek tartalommal kell rendelkeznie.

  ```markdown
  # 
  This is not allowed.
  ```
- A `#` karaktert és a H1 tartalmát szóközzel kell elválasztani. A szóköz nélkül a H1 nem fejlécként jelenik meg a közzétett oldalon.

  ```markdown
  #This looks bad on the site.
  ```
- Az YML metaadatfejléc után a H1-nek kell első tartalomként szerepelnie a fájlban. Az YML fejléc és a H1 között semmilyen tartalom (pl. szöveg vagy kép) nem szerepelhet.

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- Ne használja az első szintű fejlécekhez tartozó HTML-elemet (`<h1>`). Helyette használja a Markdown-szintaxist (`# `).
- A H1 fejléc legfeljebb 100 karakter hosszúságú lehet. Ez egy stílusútmutató.

## <a name="h2---h6"></a>H2–H6

Az OPS-ben a H2–H6 (`## `–`###### `) fejlécek engedélyezettek. Fejlécek létrehozásához a HTML (`<h2>` - `<h6>`) helyett használja a Markdown-fejléceket.
