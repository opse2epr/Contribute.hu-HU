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
# <a name="h1-missing"></a><span data-ttu-id="1af91-103">h1-missing</span><span class="sxs-lookup"><span data-stu-id="1af91-103">h1-missing</span></span>

## <a name="warning"></a><span data-ttu-id="1af91-104">Figyelmeztetés</span><span class="sxs-lookup"><span data-stu-id="1af91-104">Warning</span></span>

`H1 is required. Use a single hash (#) followed by a space to create your top-level heading.`

<span data-ttu-id="1af91-105">H1 a Markdown-fájl első fejlécét jelöli.</span><span class="sxs-lookup"><span data-stu-id="1af91-105">H1 refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="1af91-106">A docs.microsoft.com webhelyen közzétett Markdown-fájlokban a H1 az oldal tetején nagy betűmérettel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1af91-106">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span> <span data-ttu-id="1af91-107">H1 fejléc létrehozásakor kezdje a sort kettős kereszttel (#), hagyjon utána egy szóközt, majd adja meg a fejléc szövegét.</span><span class="sxs-lookup"><span data-stu-id="1af91-107">An H1 is created by beginning a line with a single hash (#) followed by a space, then the heading text.</span></span>

## <a name="resolution"></a><span data-ttu-id="1af91-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="1af91-108">Resolution</span></span>

<span data-ttu-id="1af91-109">A probléma megoldásához adjon meg egy H1 fejlécet az YML metaadatblokk utáni első tartalomként a fájlban:</span><span class="sxs-lookup"><span data-stu-id="1af91-109">To fix this issue, add an H1 as the first content after the YML metadata block in your file:</span></span>

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

> [!NOTE]
> <span data-ttu-id="1af91-110">Ez a szabály beágyazott fájlokra nem vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1af91-110">This rule does not apply to included files.</span></span> <span data-ttu-id="1af91-111">Ha beágyazott fájlokra vonatkozó H1-figyelmeztetéseket kap, akkor valószínűleg egy `includes` mappába kell áthelyeznie a beágyazott fájlokat.</span><span class="sxs-lookup"><span data-stu-id="1af91-111">If you get H1 warnings on included files, you most likely need to move your included files into an `includes` folder.</span></span> <span data-ttu-id="1af91-112">Az `includes` mappa a fájl elérési útvonalának bármelyik szintjén lehet.</span><span class="sxs-lookup"><span data-stu-id="1af91-112">The `includes` folder can be at any level in the file path.</span></span> <span data-ttu-id="1af91-113">A Docs-build az útvonal alapján beágyazott fájlként ismeri fel a fájlt, és nem futnak el a H1-ellenőrzések.</span><span class="sxs-lookup"><span data-stu-id="1af91-113">Based on the path, Docs build will recognize the file as an included file and H1 validations won't run.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]