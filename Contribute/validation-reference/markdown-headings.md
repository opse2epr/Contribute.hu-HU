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
# <a name="markdown-headings"></a><span data-ttu-id="3ac26-103">Markdown-fejlécek</span><span class="sxs-lookup"><span data-stu-id="3ac26-103">Markdown headings</span></span>

<span data-ttu-id="3ac26-104">Az OPS Markdown-fájljaiban szereplő fejlécekre az alábbi ellenőrzési követelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="3ac26-104">The following validation requirements apply to headings in OPS Markdown files.</span></span>

## <a name="h1"></a><span data-ttu-id="3ac26-105">H1</span><span class="sxs-lookup"><span data-stu-id="3ac26-105">H1</span></span>

<span data-ttu-id="3ac26-106">A `H1` a Markdown-fájl első fejlécét jelöli.</span><span class="sxs-lookup"><span data-stu-id="3ac26-106">`H1` refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="3ac26-107">A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="3ac26-107">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span>

<span data-ttu-id="3ac26-108">H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (`#`), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.</span><span class="sxs-lookup"><span data-stu-id="3ac26-108">An H1 is created by beginning a line with a single hash (`#`) followed by a space, then the heading text.</span></span> <span data-ttu-id="3ac26-109">Például a cikkben szereplő H1 fejléc a következő:</span><span class="sxs-lookup"><span data-stu-id="3ac26-109">For example, the H1 of this article is:</span></span>

```md
# Markdown headings
```

<span data-ttu-id="3ac26-110">A H1 fejlécekre a következő szabályok vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="3ac26-110">The following rules apply to H1 headings:</span></span>

- <span data-ttu-id="3ac26-111">A fájlban szerepelnie kell egy H1 fejlécnek.</span><span class="sxs-lookup"><span data-stu-id="3ac26-111">An H1 must be present in the file.</span></span>
- <span data-ttu-id="3ac26-112">Egyszerre csak egy H1 fejléc szerepelhet benne.</span><span class="sxs-lookup"><span data-stu-id="3ac26-112">There can only be one H1.</span></span>
- <span data-ttu-id="3ac26-113">A H1-nek tartalommal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="3ac26-113">The H1 must have content.</span></span>

  ```markdown
  # 
  This is not allowed.
  ```
- <span data-ttu-id="3ac26-114">A `#` karaktert és a H1 tartalmát szóközzel kell elválasztani.</span><span class="sxs-lookup"><span data-stu-id="3ac26-114">There must be a space between the `#` and the H1 content.</span></span> <span data-ttu-id="3ac26-115">A szóköz nélkül a H1 nem fejlécként jelenik meg a közzétett oldalon.</span><span class="sxs-lookup"><span data-stu-id="3ac26-115">An H1 with no space doesn't render as a heading on the published page.</span></span>

  ```markdown
  #This looks bad on the site.
  ```
- <span data-ttu-id="3ac26-116">Az YML metaadatfejléc után a H1-nek kell első tartalomként szerepelnie a fájlban.</span><span class="sxs-lookup"><span data-stu-id="3ac26-116">The H1 must be the first content in the file after the YML metadata header.</span></span> <span data-ttu-id="3ac26-117">Az YML fejléc és a H1 között semmilyen tartalom (pl. szöveg vagy kép) nem szerepelhet.</span><span class="sxs-lookup"><span data-stu-id="3ac26-117">No content, such as text or images, is allowed between the end of the YML header and the H1.</span></span>

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- <span data-ttu-id="3ac26-118">Ne használja az első szintű fejlécekhez tartozó HTML-elemet (`<h1>`).</span><span class="sxs-lookup"><span data-stu-id="3ac26-118">The HTML element for first-level headings, `<h1>`, should not be used.</span></span> <span data-ttu-id="3ac26-119">Helyette használja a Markdown-szintaxist (`# `).</span><span class="sxs-lookup"><span data-stu-id="3ac26-119">Use the Markdown syntax (`# `).</span></span>
- <span data-ttu-id="3ac26-120">A H1 fejléc legfeljebb 100 karakter hosszúságú lehet.</span><span class="sxs-lookup"><span data-stu-id="3ac26-120">The H1 should be no more than 100 characters long.</span></span> <span data-ttu-id="3ac26-121">Ez egy stílusútmutató.</span><span class="sxs-lookup"><span data-stu-id="3ac26-121">This is a style guideline.</span></span>

## <a name="h2---h6"></a><span data-ttu-id="3ac26-122">H2–H6</span><span class="sxs-lookup"><span data-stu-id="3ac26-122">H2 - H6</span></span>

<span data-ttu-id="3ac26-123">Az OPS-ben a H2–H6 (`## `–`###### `) fejlécek engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="3ac26-123">H2 (`## `) through H6 (`###### `) are allowed in OPS.</span></span> <span data-ttu-id="3ac26-124">Fejlécek létrehozásához a HTML (`<h2>` - `<h6>`) helyett használja a Markdown-fejléceket.</span><span class="sxs-lookup"><span data-stu-id="3ac26-124">Use the Markdown headers, not the HTML (`<h2>` - `<h6>`), to create headings.</span></span>
