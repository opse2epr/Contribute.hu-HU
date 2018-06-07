---
title: Hivatkozások használata a dokumentációban
description: Ebből a cikkből megtudhatja, hogyan hozhat létre más tartalmakra mutató hivatkozásokat a docs.microsoft.com webhelyen.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/29/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1699e57ac6a4dc4c5a1ef099ea183b3cbc6307cd
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469532"
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="fed0a-103">Hivatkozások használata a dokumentációban</span><span class="sxs-lookup"><span data-stu-id="fed0a-103">Using links in documentation</span></span>
<span data-ttu-id="fed0a-104">Ebből a cikkből megtudhatja, hogyan használhat hivatkozásokat a docs.microsoft.com webhelyen közzétett lapokon.</span><span class="sxs-lookup"><span data-stu-id="fed0a-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com.</span></span> <span data-ttu-id="fed0a-105">A hivatkozások Markdown jelölőnyelven való hozzáadása egyszerű: csupán néhány konvenciót kell követnie.</span><span class="sxs-lookup"><span data-stu-id="fed0a-105">Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="fed0a-106">A hivatkozások mutathatnak ugyanannak a lapnak egy másik részére, egy másik kapcsolódó lapra, illetve külső webhelyekre és URL-címekre.</span><span class="sxs-lookup"><span data-stu-id="fed0a-106">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="fed0a-107">A docs.microsoft.com webhely háttérrendszere Open Publishing Services (OPS) szolgáltatást használ, mely a DocFX-stílusú Markdown (DFM) jelölőnyelvet implementálja.</span><span class="sxs-lookup"><span data-stu-id="fed0a-107">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="fed0a-108">A DFM erősen kompatibilis a GitHub-stílusú Markdown (GFM) jelölőnyelvvel, és kiegészíti azt néhány további funkcióval Markdown-bővítmények segítségével.</span><span class="sxs-lookup"><span data-stu-id="fed0a-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fed0a-109">Minden hivatkozásnak biztonságosnak kell lennie (`https`, nem pedig `http`), ha a cél támogatja azt (az esetek többségében igen).</span><span class="sxs-lookup"><span data-stu-id="fed0a-109">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="fed0a-110">Hivatkozás szövege</span><span class="sxs-lookup"><span data-stu-id="fed0a-110">Link text</span></span>

<span data-ttu-id="fed0a-111">A hivatkozásszövegbe foglalt szavaknak érthetőnek kell lenniük,</span><span class="sxs-lookup"><span data-stu-id="fed0a-111">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="fed0a-112">azaz mindennapos angol szavakat célszerű használni, vagy a hivatkozott oldal címének kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="fed0a-112">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fed0a-113">Ne használja a „Kattintson ide” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="fed0a-113">Do not use "click here."</span></span> <span data-ttu-id="fed0a-114">Ez ugyanis hátrányos a keresőmotor-optimalizálás szempontjából, és nem megfelelően írja le a célt.</span><span class="sxs-lookup"><span data-stu-id="fed0a-114">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="fed0a-115">**Megfelelő:**</span><span class="sxs-lookup"><span data-stu-id="fed0a-115">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="fed0a-116">**Nem megfelelő:**</span><span class="sxs-lookup"><span data-stu-id="fed0a-116">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="fed0a-117">Az egyik cikkből a másikra mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-117">Links from one article to another</span></span>

<span data-ttu-id="fed0a-118">Ha egy műszaki Docs-cikkben ugyanannak a dokumentumkészletnek egy másik műszaki Docs-cikkére mutató szövegbeli hivatkozást szeretne létrehozni, használja a következő hivatkozásszintaxist:</span><span class="sxs-lookup"><span data-stu-id="fed0a-118">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="fed0a-119">Az adott könyvtárban lévő cikk az ugyanabban a könyvtárban lévő másik cikkre mutat:</span><span class="sxs-lookup"><span data-stu-id="fed0a-119">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="fed0a-120">Az adott alkönyvtárban lévő cikk a gyökérkönyvtárban lévő cikkre mutat:</span><span class="sxs-lookup"><span data-stu-id="fed0a-120">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="fed0a-121">A gyökérkönyvtárban lévő cikk az alkönyvtárban lévő másik cikkre mutat:</span><span class="sxs-lookup"><span data-stu-id="fed0a-121">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="fed0a-122">Az adott alkönyvtárban lévő cikk egy másik alkönyvtárban lévő cikkre mutat:</span><span class="sxs-lookup"><span data-stu-id="fed0a-122">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="fed0a-123">A cikk egy másik dokumentumkészletben lévő cikkre mutat (egyazon tárházon belül is): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="fed0a-123">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>
  
## <a name="links-to-anchors"></a><span data-ttu-id="fed0a-124">Horgonyokra mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-124">Links to anchors</span></span>

<span data-ttu-id="fed0a-125">Nem szükséges horgonyokat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="fed0a-125">You do not have to create anchors.</span></span> <span data-ttu-id="fed0a-126">Ezeket ugyanis a közzététel időpontjában hozza létre automatikusan a rendszer az összes H2-fejléchez.</span><span class="sxs-lookup"><span data-stu-id="fed0a-126">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="fed0a-127">Önnek nincs más dolga, mint létrehozni a H2-fejlécekre mutató hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="fed0a-127">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="fed0a-128">Ha ugyanabban a cikkben szereplő fejlécre mutató hivatkozást szeretne létrehozni, tegye a következőt:</span><span class="sxs-lookup"><span data-stu-id="fed0a-128">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="fed0a-129">Ha ugyanazon alkönyvtár másik cikkében található horgonyra mutató hivatkozást szeretne létrehozni, tegye a következőt:</span><span class="sxs-lookup"><span data-stu-id="fed0a-129">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="fed0a-130">Ha másik szolgáltatási alkönyvtárban található horgonyra mutató hivatkozást szeretne létrehozni, tegye a következőt:</span><span class="sxs-lookup"><span data-stu-id="fed0a-130">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="fed0a-131">Beágyazásokhoz tartozó hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-131">Links from includes</span></span>

<span data-ttu-id="fed0a-132">A beágyazott fájlok másik könyvtárban találhatók, ezért hosszabb relatív elérési utakat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="fed0a-132">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="fed0a-133">Ha beágyazott fájlból szeretne cikkre mutató hivatkozást létrehozni, használja a következő formátumot:</span><span class="sxs-lookup"><span data-stu-id="fed0a-133">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="fed0a-134">A választókban lévő hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-134">Links in selectors</span></span>

<span data-ttu-id="fed0a-135">Ha beágyazásba ágyazott választókkal rendelkezik – amilyeneket az Azure dokumentációs csapata is használ –, akkor a következő hivatkozásszerkezetet kell használnia:</span><span class="sxs-lookup"><span data-stu-id="fed0a-135">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="fed0a-136">[AZURE.SELECTOR-LIST (Legördülő menü1 | Legördülő menü2 )]</span><span class="sxs-lookup"><span data-stu-id="fed0a-136">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="fed0a-137">(Szöveg1 | Példa1 )</span><span class="sxs-lookup"><span data-stu-id="fed0a-137">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="fed0a-138">(Szöveg1 | Példa2 )</span><span class="sxs-lookup"><span data-stu-id="fed0a-138">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="fed0a-139">(Szöveg2 | Példa3 )</span><span class="sxs-lookup"><span data-stu-id="fed0a-139">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="fed0a-140">[(Szöveg2 | Példa4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="fed0a-140">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="fed0a-141">Referencia típusú hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-141">Reference-style links</span></span>

<span data-ttu-id="fed0a-142">Referencia típusú hivatkozások használatával leegyszerűsíthető a forrástartalom olvasása.</span><span class="sxs-lookup"><span data-stu-id="fed0a-142">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="fed0a-143">A referencia típusú hivatkozások olyan egyszerűsített szintaxissal váltják fel a szövegbeli hivatkozásszintaxist, amely lehetővé teszi a hosszú URL-címek cikk végére való áthelyezését.</span><span class="sxs-lookup"><span data-stu-id="fed0a-143">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="fed0a-144">Íme a [Daring Fireball](https://daringfireball.net/projects/markdown/) példája:</span><span class="sxs-lookup"><span data-stu-id="fed0a-144">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="fed0a-145">Beágyazott szöveg:</span><span class="sxs-lookup"><span data-stu-id="fed0a-145">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="fed0a-146">Cikk végén található hivatkozások:</span><span class="sxs-lookup"><span data-stu-id="fed0a-146">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="fed0a-147">Ügyeljen arra, hogy a kettőspont és a hivatkozás között szóközt hagyjon.</span><span class="sxs-lookup"><span data-stu-id="fed0a-147">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="fed0a-148">Ha más műszaki cikkekre mutató hivatkozást hoz létre, és elfelejt szóközt hagyni, akkor a hivatkozás hibásan szerepel majd a közzétett cikkben.</span><span class="sxs-lookup"><span data-stu-id="fed0a-148">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="fed0a-149">Hivatkozás a műszaki dokumentációkészlet részét nem képező lapokra</span><span class="sxs-lookup"><span data-stu-id="fed0a-149">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="fed0a-150">Ha a Microsoft tulajdonában lévő másik lapra mutató hivatkozást szeretne létrehozni (például az egyik díjszabási lapra, SLA-lapra vagy bármi olyanra, amely nem dokumentációs cikk), használjon abszolút URL-címet, de hagyja ki a területi kódot.</span><span class="sxs-lookup"><span data-stu-id="fed0a-150">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="fed0a-151">A cél itt az, hogy a hivatkozások működjenek a GitHubban és a megjelenített webhelyen:</span><span class="sxs-lookup"><span data-stu-id="fed0a-151">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="fed0a-152">Külső webhelyekre mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-152">Links to third-party sites</span></span>

<span data-ttu-id="fed0a-153">A legjobb felhasználói környezet az, amely minimális szintre csökkenti a felhasználók másik webhelyre való küldését.</span><span class="sxs-lookup"><span data-stu-id="fed0a-153">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="fed0a-154">Ezért a (néha valóban szükséges) külső webhelyekre mutató hivatkozásokat a következő információk alapján hozza létre:</span><span class="sxs-lookup"><span data-stu-id="fed0a-154">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="fed0a-155">**Felelősség:** Akkor hivatkozzon külső tartalomra, ha az külső fél megosztani kívánt információja.</span><span class="sxs-lookup"><span data-stu-id="fed0a-155">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="fed0a-156">Például nem a Microsoft feladata tájékoztatni a felhasználókat az androidos fejlesztői eszközök használatának módjáról (illetve nem a Microsoft a megfelelő platform erre). Ez ugyanis a Google dolga.</span><span class="sxs-lookup"><span data-stu-id="fed0a-156">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="fed0a-157">Ha szükséges, el tudjuk magyarázni az androidos fejlesztői eszközök *Azure-ral* való használatának módját, de a Google feladata ismertetni az eszközeik használatát.</span><span class="sxs-lookup"><span data-stu-id="fed0a-157">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="fed0a-158">**PM-jóváhagyás:** Külső tartalmakra való hivatkozáshoz kérje a Microsoft jóváhagyását.</span><span class="sxs-lookup"><span data-stu-id="fed0a-158">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="fed0a-159">Az ilyen tartalomra mutató hivatkozás létrehozása az abba vetett bizalmunkról tanúskodik, és felelősségvállalást jelent arra az esetre, ha a felhasználók követik az ott szereplő utasításokat.</span><span class="sxs-lookup"><span data-stu-id="fed0a-159">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="fed0a-160">**Naprakészségi ellenőrzések:** Győződjön meg arról, hogy a harmadik féltől származó adatok még aktuálisak, pontosak és relevánsak, illetve hogy a hivatkozás nem módosult.</span><span class="sxs-lookup"><span data-stu-id="fed0a-160">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="fed0a-161">**Külső webhely:** Tudassa a felhasználókkal, hogy másik webhelyet keresnek fel.</span><span class="sxs-lookup"><span data-stu-id="fed0a-161">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="fed0a-162">Ha a kontextusból nem derül ki világosan, biztosítson valamilyen tájékoztató szöveget.</span><span class="sxs-lookup"><span data-stu-id="fed0a-162">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="fed0a-163">Példa: „Az előfeltételek közé tartoznak az androidos fejlesztői eszközök, amelyeket az Android Studio webhelyéről tölthet le.”</span><span class="sxs-lookup"><span data-stu-id="fed0a-163">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="fed0a-164">**Következő lépések:** Nyugodtan felvehet például egy Következő lépések című szakaszba egy MVP-blogra mutató hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="fed0a-164">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="fed0a-165">Itt is fontos tudatni a felhasználókkal, hogy elhagyják a webhelyet.</span><span class="sxs-lookup"><span data-stu-id="fed0a-165">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="fed0a-166">**Jogi szabályozás**: Jogi szempontból az összes ms.com-oldal láblécében szereplő **Használati feltételek** **külső felek webhelyeire mutató hivatkozásokról szóló szakasza** vonatkozik ránk.</span><span class="sxs-lookup"><span data-stu-id="fed0a-166">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="fed0a-167">Az MSDN vagy a TechNet webhelyére mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-167">Links to MSDN or TechNet</span></span>

<span data-ttu-id="fed0a-168">Ha az MSDN vagy TechNet webhelyére mutató hivatkozásra van szüksége, használja a témakörre mutató teljes hivatkozást, és távolítsa el a hivatkozásból az „en-us” nyelvi kódot.</span><span class="sxs-lookup"><span data-stu-id="fed0a-168">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="fed0a-169">Az Azure PowerShell-referenciatartalomra mutató hivatkozások</span><span class="sxs-lookup"><span data-stu-id="fed0a-169">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="fed0a-170">Az Azure PowerShell-referenciatartalom több módosuláson is átesett 2016. november óta.</span><span class="sxs-lookup"><span data-stu-id="fed0a-170">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="fed0a-171">Az alábbi irányelvek használatával hozhat létre erre a tartalomra mutató hivatkozást a docs.microsoft.com webhelyén található más cikkekből.</span><span class="sxs-lookup"><span data-stu-id="fed0a-171">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="fed0a-172">Az URL-cím szerkezete:</span><span class="sxs-lookup"><span data-stu-id="fed0a-172">Structure of the URL:</span></span>

* <span data-ttu-id="fed0a-173">Parancsmagok esetében:</span><span class="sxs-lookup"><span data-stu-id="fed0a-173">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="fed0a-174">Fogalmi témakörök esetében:</span><span class="sxs-lookup"><span data-stu-id="fed0a-174">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="fed0a-175">A &lt;moniker-name&gt; rész nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="fed0a-175">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="fed0a-176">Ha ezt kihagyja, akkor a rendszer a legújabb verziójú tartalomra irányítja majd át.</span><span class="sxs-lookup"><span data-stu-id="fed0a-176">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="fed0a-177">A &lt;service-name&gt; rész a következő alap URL-címek között szereplő példák egyike:</span><span class="sxs-lookup"><span data-stu-id="fed0a-177">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="fed0a-178">Azure PowerShell- (AzureRM-) tartalom: https://docs.microsoft.com/powershell/azure/</span><span class="sxs-lookup"><span data-stu-id="fed0a-178">Azure PowerShell (AzureRM) content: https://docs.microsoft.com/powershell/azure/</span></span>
- <span data-ttu-id="fed0a-179">Azure PowerShell- (ASM-) tartalom: https://docs.microsoft.com/powershell/azure/_servicemanagement_</span><span class="sxs-lookup"><span data-stu-id="fed0a-179">Azure PowerShell (ASM) content: https://docs.microsoft.com/powershell/azure/_servicemanagement_</span></span>
- <span data-ttu-id="fed0a-180">Azure Active Directory (AzureAD) PowerShell-tartalom: https://docs.microsoft.com/powershell/azure/_active-directory_</span><span class="sxs-lookup"><span data-stu-id="fed0a-180">Azure Active Directory (AzureAD) PowerShell content: https://docs.microsoft.com/powershell/azure/_active-directory_</span></span>
- <span data-ttu-id="fed0a-181">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span><span class="sxs-lookup"><span data-stu-id="fed0a-181">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span></span>
- <span data-ttu-id="fed0a-182">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span><span class="sxs-lookup"><span data-stu-id="fed0a-182">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span></span>
- <span data-ttu-id="fed0a-183">Azure Elastic DB-feladatok PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span><span class="sxs-lookup"><span data-stu-id="fed0a-183">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span></span>

<span data-ttu-id="fed0a-184">Ha ezeket az URL-címeket használja, akkor a rendszer a legújabb verziójú tartalomra irányítja majd át.</span><span class="sxs-lookup"><span data-stu-id="fed0a-184">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="fed0a-185">Ennek köszönhetően nem kell verziós kézjegyet megadnia.</span><span class="sxs-lookup"><span data-stu-id="fed0a-185">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="fed0a-186">Így nem kell fogalmi tartalomra mutató, a verzió változásakor frissítendő hivatkozásokat sem használnia.</span><span class="sxs-lookup"><span data-stu-id="fed0a-186">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="fed0a-187">A megfelelő hivatkozás létrehozásához keresse meg a böngészőben hivatkozni kívánt oldalt, és másolja az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="fed0a-187">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="fed0a-188">Aztán távolítsa el a "https://docs.microsoft.com"-t és a területi beállítási beállítást.</span><span class="sxs-lookup"><span data-stu-id="fed0a-188">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="fed0a-189">Amikor tartalomjegyzékben hoz létre hivatkozást, akkor a területi információval kapcsolatos adatok nélküli teljes URL-címet kell használnia.</span><span class="sxs-lookup"><span data-stu-id="fed0a-189">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="fed0a-190">Markdown-példa:</span><span class="sxs-lookup"><span data-stu-id="fed0a-190">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
