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
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/22/2018
---
# <a name="using-links-in-documentation"></a>Hivatkozások használata a dokumentációban
Ebből a cikkből megtudhatja, hogyan használhat hivatkozásokat a docs.microsoft.com webhelyen közzétett lapokon. A hivatkozások Markdown jelölőnyelven való hozzáadása egyszerű: csupán néhány konvenciót kell követnie. A hivatkozások mutathatnak ugyanannak a lapnak egy másik részére, egy másik kapcsolódó lapra, illetve külső webhelyekre és URL-címekre.

A docs.microsoft.com webhely háttérrendszere Open Publishing Services (OPS) szolgáltatást használ, mely a DocFX-stílusú Markdown (DFM) jelölőnyelvet implementálja. A DFM erősen kompatibilis a GitHub-stílusú Markdown (GFM) jelölőnyelvvel, és kiegészíti azt néhány további funkcióval Markdown-bővítmények segítségével.

> [!IMPORTANT]
> Minden hivatkozásnak biztonságosnak kell lennie (`https`, nem pedig `http`), ha a cél támogatja azt (az esetek többségében igen).

## <a name="link-text"></a>Hivatkozás szövege

A hivatkozásszövegbe foglalt szavaknak érthetőnek kell lenniük, azaz mindennapos angol szavakat célszerű használni, vagy a hivatkozott oldal címének kell lenniük.

> [!IMPORTANT]
> Ne használja a „Kattintson ide” kifejezést. Ez ugyanis hátrányos a keresőmotor-optimalizálás szempontjából, és nem megfelelően írja le a célt.

**Megfelelő:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Nem megfelelő:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>Az egyik cikkből a másikra mutató hivatkozások

Ha egy műszaki Docs-cikkben ugyanannak a dokumentumkészletnek egy másik műszaki Docs-cikkére mutató szövegbeli hivatkozást szeretne létrehozni, használja a következő hivatkozásszintaxist:

- Az adott könyvtárban lévő cikk az ugyanabban a könyvtárban lévő másik cikkre mutat:

  `[link text](article-name.md)`

- Az adott alkönyvtárban lévő cikk a gyökérkönyvtárban lévő cikkre mutat:

  `[link text](../article-name.md)`

- A gyökérkönyvtárban lévő cikk az alkönyvtárban lévő másik cikkre mutat:

  `[link text](./directory/article-name.md)`

- Az adott alkönyvtárban lévő cikk egy másik alkönyvtárban lévő cikkre mutat:

  `[link text](../directory/article-name.md)`

- A cikk egy másik dokumentumkészletben lévő cikkre mutat (egyazon tárházon belül is): `[link text](./directory/article-name)`
  
## <a name="links-to-anchors"></a>Horgonyokra mutató hivatkozások

Nem szükséges horgonyokat létrehozni. Ezeket ugyanis a közzététel időpontjában hozza létre automatikusan a rendszer az összes H2-fejléchez. Önnek nincs más dolga, mint létrehozni a H2-fejlécekre mutató hivatkozásokat.

- Ha ugyanabban a cikkben szereplő fejlécre mutató hivatkozást szeretne létrehozni, tegye a következőt:

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- Ha ugyanazon alkönyvtár másik cikkében található horgonyra mutató hivatkozást szeretne létrehozni, tegye a következőt:

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- Ha másik szolgáltatási alkönyvtárban található horgonyra mutató hivatkozást szeretne létrehozni, tegye a következőt:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>Beágyazásokhoz tartozó hivatkozások

A beágyazott fájlok másik könyvtárban találhatók, ezért hosszabb relatív elérési utakat kell használnia. Ha beágyazott fájlból szeretne cikkre mutató hivatkozást létrehozni, használja a következő formátumot:

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a>A választókban lévő hivatkozások

Ha beágyazásba ágyazott választókkal rendelkezik – amilyeneket az Azure dokumentációs csapata is használ –, akkor a következő hivatkozásszerkezetet kell használnia:

    > [AZURE.SELECTOR-LIST (Legördülő menü1 | Legördülő menü2 )]
    - [(Szöveg1 | Példa1 )](../articles/folder/article-name1.md)
    - [(Szöveg1 | Példa2 )](../articles/folder/article-name2.md)
    - [(Szöveg2 | Példa3 )](../articles/folder/article-name3.md)
    - [(Szöveg2 | Példa4 )](../articles/folder/article-name4.md) -->

## <a name="reference-style-links"></a>Referencia típusú hivatkozások

Referencia típusú hivatkozások használatával leegyszerűsíthető a forrástartalom olvasása. A referencia típusú hivatkozások olyan egyszerűsített szintaxissal váltják fel a szövegbeli hivatkozásszintaxist, amely lehetővé teszi a hosszú URL-címek cikk végére való áthelyezését. Íme a [Daring Fireball](https://daringfireball.net/projects/markdown/) példája:

Beágyazott szöveg:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Cikk végén található hivatkozások:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

Ügyeljen arra, hogy a kettőspont és a hivatkozás között szóközt hagyjon. Ha más műszaki cikkekre mutató hivatkozást hoz létre, és elfelejt szóközt hagyni, akkor a hivatkozás hibásan szerepel majd a közzétett cikkben.

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>Hivatkozás a műszaki dokumentációkészlet részét nem képező lapokra

Ha a Microsoft tulajdonában lévő másik lapra mutató hivatkozást szeretne létrehozni (például az egyik díjszabási lapra, SLA-lapra vagy bármi olyanra, amely nem dokumentációs cikk), használjon abszolút URL-címet, de hagyja ki a területi kódot. A cél itt az, hogy a hivatkozások működjenek a GitHubban és a megjelenített webhelyen:

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a>Külső webhelyekre mutató hivatkozások

A legjobb felhasználói környezet az, amely minimális szintre csökkenti a felhasználók másik webhelyre való küldését. Ezért a (néha valóban szükséges) külső webhelyekre mutató hivatkozásokat a következő információk alapján hozza létre:

- **Felelősség:** Akkor hivatkozzon külső tartalomra, ha az külső fél megosztani kívánt információja. Például nem a Microsoft feladata tájékoztatni a felhasználókat az androidos fejlesztői eszközök használatának módjáról (illetve nem a Microsoft a megfelelő platform erre). Ez ugyanis a Google dolga. Ha szükséges, el tudjuk magyarázni az androidos fejlesztői eszközök *Azure-ral* való használatának módját, de a Google feladata ismertetni az eszközeik használatát.
- **PM-jóváhagyás:** Külső tartalmakra való hivatkozáshoz kérje a Microsoft jóváhagyását. Az ilyen tartalomra mutató hivatkozás létrehozása az abba vetett bizalmunkról tanúskodik, és felelősségvállalást jelent arra az esetre, ha a felhasználók követik az ott szereplő utasításokat.
- **Naprakészségi ellenőrzések:** Győződjön meg arról, hogy a harmadik féltől származó adatok még aktuálisak, pontosak és relevánsak, illetve hogy a hivatkozás nem módosult.
- **Külső webhely:** Tudassa a felhasználókkal, hogy másik webhelyet keresnek fel. Ha a kontextusból nem derül ki világosan, biztosítson valamilyen tájékoztató szöveget. Példa: „Az előfeltételek közé tartoznak az androidos fejlesztői eszközök, amelyeket az Android Studio webhelyéről tölthet le.”
- **Következő lépések:** Nyugodtan felvehet például egy Következő lépések című szakaszba egy MVP-blogra mutató hivatkozást. Itt is fontos tudatni a felhasználókkal, hogy elhagyják a webhelyet.
- **Jogi szabályozás**: Jogi szempontból az összes ms.com-oldal láblécében szereplő **Használati feltételek** **külső felek webhelyeire mutató hivatkozásokról szóló szakasza** vonatkozik ránk.

## <a name="links-to-msdn-or-technet"></a>Az MSDN vagy a TechNet webhelyére mutató hivatkozások

Ha az MSDN vagy TechNet webhelyére mutató hivatkozásra van szüksége, használja a témakörre mutató teljes hivatkozást, és távolítsa el a hivatkozásból az „en-us” nyelvi kódot.

## <a name="links-to-azure-powershell-reference-content"></a>Az Azure PowerShell-referenciatartalomra mutató hivatkozások

Az Azure PowerShell-referenciatartalom több módosuláson is átesett 2016. november óta. Az alábbi irányelvek használatával hozhat létre erre a tartalomra mutató hivatkozást a docs.microsoft.com webhelyén található más cikkekből.

Az URL-cím szerkezete:

* Parancsmagok esetében:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* Fogalmi témakörök esetében:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

A &lt;moniker-name&gt; rész nem kötelező. Ha ezt kihagyja, akkor a rendszer a legújabb verziójú tartalomra irányítja majd át. A &lt;service-name&gt; rész a következő alap URL-címek között szereplő példák egyike:

- Azure PowerShell- (AzureRM-) tartalom: https://docs.microsoft.com/powershell/azure/
- Azure PowerShell- (ASM-) tartalom: https://docs.microsoft.com/powershell/azure/_servicemanagement_
- Azure Active Directory (AzureAD) PowerShell-tartalom: https://docs.microsoft.com/powershell/azure/_active-directory_
- Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_
- Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_
- Azure Elastic DB-feladatok PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_

Ha ezeket az URL-címeket használja, akkor a rendszer a legújabb verziójú tartalomra irányítja majd át. Ennek köszönhetően nem kell verziós kézjegyet megadnia. Így nem kell fogalmi tartalomra mutató, a verzió változásakor frissítendő hivatkozásokat sem használnia.

A megfelelő hivatkozás létrehozásához keresse meg a böngészőben hivatkozni kívánt oldalt, és másolja az URL-címet.
Aztán távolítsa el a "https://docs.microsoft.com"-t és a területi beállítási beállítást.

Amikor tartalomjegyzékben hoz létre hivatkozást, akkor a területi információval kapcsolatos adatok nélküli teljes URL-címet kell használnia.

Markdown-példa:

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
