---
title: Git- és GitHub-alapismeretek a dokumentációs webhelyhez
description: Ebből a cikkből megismerheti a Gitet, a GitHub-tárházakat, illetve a docs.microsoft.com webhelyen használt tartalomrendszerezést és elnevezési konvenciókat.
ms.date: 06/30/2017
ms.openlocfilehash: b7eb82f299d3efcdb1e49649fb77367ef8ba3fae
ms.sourcegitcommit: 203ca15fda2d217f082c74ec648c1f1db323f9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55712878"
---
# <a name="git-and-github-essentials-for-docs"></a>Git- és GitHub-alapismeretek a Docs webhelyhez

## <a name="overview"></a>Áttekintés

Ha Docs-tartalmak közreműködője, akkor sokféle eszközzel és eljárással találkozhat. Más közreműködőkkel párhozamosan dolgozhat ugyanazon a projekten, olykor ugyanazon a tartalmon, akár egyidejűleg. Mindezt a Git és a GitHub szoftver teszi lehetővé.

A Git egy nyílt forráskódú verziókövető rendszer. Az ilyen jellegű projektekben való együttműködést a *tárházakban* lévő fájlok *elosztott verziókövetésével* valósítja meg. A Git lényegében lehetővé teszi több közreműködő egy adott időszakban egy adott tárházban elvégzett munkafolyamatainak integrálását.

A GitHub az olyan Git-tárházakhoz készült webes üzemeltetési szolgáltatás, mint például amelyek a [docs.microsoft.com](https://docs.microsoft.com) tartalmait tárolják. Minden projekt fő tárházát a GitHub üzemelteti, a közreműködők pedig másolatokat készíthetnek erről a saját munkájukhoz.

## <a name="git"></a>Git

Ha ismeri a központosított verziókövető rendszereket (ilyen például a Team Foundation Server, a SharePoint vagy a Visual SourceSafe), megfigyelheti, hogy a Git elosztott modellje egyedi közreműködői munkafolyamatot és terminológiát használ. Nem történik például a kivételi és a beadási műveletekkel általában együtt járó fájlzárolás. Ami azt illeti, a Git sokkal aprólékosabban kezeli a változásokat, és bájtról bájtra hasonlítja össze a fájlokat.

A Git többszintű struktúrában tárolja és kezeli az adott projekthez tartozó tartalmat:

- *Tárház*: Ez a legnagyobb tárolási egység, rövid angol neve *repo*. Egy tárház egy vagy több ágat tartalmaz.
- *Ág*: A projekt tartalomkészletét alkotó fájlokat és mappákat tartalmazó tárolási egység. Az ágak a munkafolyamatok (általános elnevezéssel verziók) elkülönítésére szolgálnak. A közreműködők hatásköre pedig mindig egy adott ágra terjed ki. Minden tárház tartalmaz egy (általában master elnevezésű) főágat és egy vagy több ágat, amelyek végül egyesítve lesznek a főággal. A főág szolgál aktuális verzióként, a projekt „egyetlen hiteles forrásaként”. Ez a tárházban létrehozott összes további ág szülője.

A közreműködők helyi szinten és a GitHub szintjén egyaránt a Git használatával frissítik és kezelik a tárházakat:

- Helyben olyan eszközökkel, mint például a helyi tárházakat kezelő és GitHub-tárházakkal kommunikáló Git-parancsokat támogató Git Bash konzol.
- A [www.github.com](https://www.github.com) webhelyen keresztül, amely a Gitet integrálva kezeli a fő tárházba visszaérkező közreműködések egyeztetését.

## <a name="github"></a>GitHub

> [!NOTE]
> Bár a Docs útmutatói a GitHub használatára épülnek, néhány csapat a Visual Studio Team Services használatával üzemeltet Git-tárházakat. A Visual Studio Team Explorer ügyfél grafikus felhasználói felület kínál a Team Services-tárházakkal végzett munkához a Git-parancsok parancssori használatának kiváltására.
> </br>
> Ugyanakkor az alábbi irányelvek többsége az Azure-szolgáltatásbeli tartalmak GitHubon való kezelésével szerezett többéves tapasztalat birtokában kialakult ajánlott eljárások. Egyes Docs-tárházak esetében kötelezőek lehetnek.

Minden munkafolyamat a GitHub szintjén kezdődik és ér véget, ahol minden egyes Docs-projekt fő tárháza tárolódik. A közreműködők által saját használatra készített másolatok több számítógépen lesznek elosztva. Ezek a másolatok végül ismét össze lesznek hangolva a projekt fő GitHub-tárházával.

### <a name="directory-organization"></a>Könyvtárszerkezet

A korábban leírtaknak megfelelően egy projekt alapértelmezett/master ága a projekt tartalmának aktuális verziójaként szolgál. A főág – és az abból létrehozott ágak – tartalma hozzávetőlegesen megfeleltethető annak a Docs megfelelő oldalain található cikkek elrendezésének. Alkönyvtárakkal különíthető el a tartalom (például szolgáltatások), a médiatartalom (például képek) és (a tartalmak újrafelhasználását lehetővé tevő) beágyazható fájlok.

A tárház gyökérkönyvtárában általában megtalálható egy fő `articles` könyvtár. A cikkek könyvtára több alkönyvtárral rendelkezik. Az alkönyvtárakban lévő cikkek *.md* kiterjesztésű, Markdown-formátumú fájlok. Egyes, több szolgáltatást támogató tárházak egy általános `/articles` alkönyvtárat használnak. Ilyen például a [Azure-Docs](https://github.com/MicrosoftDocs/Azure-Docs) tárház. Mások a szolgáltatásra utaló nevet használnak, mint például az [IntuneDocs](https://github.com/MicrosoftDocs/IntuneDocs) tárház, amely az `/IntuneDocs` nevet használja.

Ennek a könyvtárnak a gyökerében találhatók a szolgáltatás vagy termék egészére vonatkozó, általános tartalmú cikkek. Ezt többnyire más, a funkciókhoz, szolgáltatásokhoz vagy gyakori forgatókönyvekhez tartozó alkönyvtárak egészítik ki. Az Azure „Virtual Machine” (virtuális gép) témájú cikkei például a `/virtual-machines` alkönyvtárban, az Intune „Understand & Explore” (Az Intune bemutatása) témájú cikkei pedig az `/understand-explore` alkönyvtárban helyezkednek el, stb.

### <a name="media-subdirectory"></a>Médiafájlok alkönyvtára

Minden cikk-könyvtár tartalmaz egy `/media` alkönyvtárat a kapcsolódó médiafájlok számára. A médiafájlok a képhivatkozásokkal rendelkező cikkekben használt képeket tartalmazzák.

### <a name="includes-subdirectory"></a>Beágyazott fájlok alkönyvtára

Ha újrafelhasználható tartalmat használ két vagy több cikkben, akkor azt a fő `articles` könyvtár `/includes` alkönyvtára tartalmazza. Egy Markdown-fájlban, amely felhasználja a beágyazott fájlt, a beágyazott fájlra való hivatkozás helyén egy megfelelő "include" Markdown-bővítményt kell elhelyezni.

További iránymutatásokért lásd [A Markdown használata: Beágyazások](how-to-write-use-markdown.md#include-files) című témakört.

### <a name="markdown-file-template"></a>Markdown-fájlsablon

Segítségképpen általában minden tárház gyökérkönyvtárában található egy `template.md` nevű Markdown-fájlsablon. Ez kiindulásként használható, ha új cikket szeretne létrehozni és feltölteni a tárházba. A fájl tartalma:

- Egy **metaadat-fejléc** a fájl elején – ez egy kétsoros, három kötőjellel megjelölt rész. Ez a cikkel kapcsolatos nyomkövetési információkhoz tartalmaz különféle címkéket. A cikkek metaadatai bizonyos funkciókat tesznek elérhetővé; ilyenek például a szerzők és a közreműködők megnevezése, az útkövetés, és a cikkleírások. Ide tartozik még a keresőmotor-optimalizálás és olyan jelentési folyamatok, amelyeket a Microsoft használ a tartalom teljesítményének értékeléséhez. A metaadatok tehát fontos szerepet játszanak.
- Egy **metaadatok szakasz**, amely ismerteti a különféle metaadat-címkéket és azok értékeit. Ha nem tudja biztosan, milyen értékeket kell használnia az egyes metaadatoknál, üresen is hagyhatja őket, vagy egy sor eleji hashtaggel (#) megjegyzéssé alakíthatja, majd a tárház pull-kérelmének felülvizsgálója ellenőrzi vagy kiegészíti azokat.
- Különféle **Markdown-használati példák**, amelyek a cikk különféle részeinek formázását mutatják be.
- **Markdown-bővítményekre vonatkozó általános használati útmutatók**, amelyek különféle típusú riasztásokhoz használhatók.
- Példák **videó beágyazására** Iframe használatával.
- Általános **használati útmutató a docs.microsoft.com-bővítmények**, többek között speciális vezérlők, például gombok és választókapcsolók használatáról.

## <a name="pull-requests"></a>Lekéréses kérelmek

A *pull-kérelem* kényelmes módot kínál a közreműködőknek arra, hogy javaslatot tegyenek módosítások egy készletének az alapértelmezett ágon való alkalmazására. A módosítások (más szóval *véglegesítések*) egy közreműködő ágában tárolódnak, lehetővé téve, hogy a GitHub először modellezze az alapértelmezett ággal való *egyesítés* következményeit. A lekéréses kérelmek ugyanakkor annak mechanizmusaként is szolgálnak, hogy a közreműködők visszajelzést kapjanak az összeállítás és az ellenőrzés folyamatáról, a lekéréses kérelem véleményezőjétől, hogy az esetleges problémákat és kérdéseket tisztázni tudják, mielőtt a változások egyesítve lennének az alapértelmezett ággal.

A javasolt változtatások méretétől függően a pull-kérelmeket két különböző módon használhatja a közreműködéshez. Erről a jelen útmutatónak [a GitHub-munkafolyamattal](how-to-write-workflows-major.md) foglalkozó részében olvashat bővebben.

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
