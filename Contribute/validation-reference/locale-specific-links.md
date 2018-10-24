# <a name="locale-specific-links"></a><span data-ttu-id="abe0f-101">Területi beállításokhoz kötődő hivatkozások</span><span class="sxs-lookup"><span data-stu-id="abe0f-101">Locale-specific links</span></span>

<span data-ttu-id="abe0f-102">A nyelvterületkódok, például az `en-us` Microsoft bizonyos webhelyeire mutató hivatkozásokba történő belefoglalása nem javasolt.</span><span class="sxs-lookup"><span data-stu-id="abe0f-102">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="abe0f-103">Ha egy angol nyelvű tartalomban található hivatkozásba foglalja bele a nyelvterületkódot, akkor a honosított hivatkozásokban is meg fog jelenni, ami rontja a honosítás összhatását.</span><span class="sxs-lookup"><span data-stu-id="abe0f-103">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="abe0f-104">Például, ha egy német nyelvű honosított tartalomban szerepel az `en-us`, akkor a német ügyfeleket is az angol cikkhez fogja irányítani a hivatkozás, még akkor is, ha a cikk németül is elérhető.</span><span class="sxs-lookup"><span data-stu-id="abe0f-104">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="abe0f-105">Távolítsa el a Microsoft webhelyeire mutató hivatkozásokból a nyelvterületkódokat.</span><span class="sxs-lookup"><span data-stu-id="abe0f-105">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="abe0f-106">Például:</span><span class="sxs-lookup"><span data-stu-id="abe0f-106">The following is an example.</span></span>

<span data-ttu-id="abe0f-107">Előtte:</span><span class="sxs-lookup"><span data-stu-id="abe0f-107">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="abe0f-108">Utána:</span><span class="sxs-lookup"><span data-stu-id="abe0f-108">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="abe0f-109">A következő oldalak tartoznak az ellenőrzés hatáskörébe:</span><span class="sxs-lookup"><span data-stu-id="abe0f-109">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="abe0f-110">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="abe0f-110">azure.microsoft.com</span></span>
- <span data-ttu-id="abe0f-111">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="abe0f-111">docs.microsoft.com</span></span>
- <span data-ttu-id="abe0f-112">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="abe0f-112">msdn.microsoft.com</span></span>
- <span data-ttu-id="abe0f-113">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="abe0f-113">technet.microsoft.com</span></span>