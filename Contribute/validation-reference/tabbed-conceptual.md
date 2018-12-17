# <a name="tabbed-conceptual"></a><span data-ttu-id="1645f-101">Többlapos fogalmi tartalom</span><span class="sxs-lookup"><span data-stu-id="1645f-101">Tabbed conceptual</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1645f-102">A többlapos fogalmi tartalom szintaxisát kivontuk, ezért új lapokat már ne adjon hozzá.</span><span class="sxs-lookup"><span data-stu-id="1645f-102">The tabbed conceptual syntax has been deprecated and new tabs should not be added.</span></span> <span data-ttu-id="1645f-103">Az itt ismertetett ellenőrzés olyan tartalmakra vonatkozik, amelyeket jóváhagytak többlapos fogalmi tartalom használatára, amíg az újabb funkció nem lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="1645f-103">The validations described in this article apply to content sets that have been approved to use tabbed conceptual until replacement functionality is available.</span></span>

## <a name="tab-syntax"></a><span data-ttu-id="1645f-104">Lapszintaxis</span><span class="sxs-lookup"><span data-stu-id="1645f-104">Tab syntax</span></span>

<span data-ttu-id="1645f-105">A lapokra vonatkozó szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="1645f-105">The syntax for tabs is as follows:</span></span>

<span data-ttu-id="1645f-106">Egyszintű lap:</span><span class="sxs-lookup"><span data-stu-id="1645f-106">Single level tab:</span></span>

`# [Tab Display Name](#tab/tab-id)`

<span data-ttu-id="1645f-107">Nem kötelező függő lap:</span><span class="sxs-lookup"><span data-stu-id="1645f-107">Optional dependent tab:</span></span>

`# [Tab Display Name](#tab/tab-id/tab-condition)`

<span data-ttu-id="1645f-108">Példa egyszintű lapszakaszra két lappal és a lapcsoport elválasztójával (---):</span><span class="sxs-lookup"><span data-stu-id="1645f-108">Example of a single-level tab section with two tabs and the tab group terminator (---):</span></span>

```
# [Linux](#tab/linux)

Content for Linux...

# [Windows](#tab/windows)

Content for Windows...

---
```

<span data-ttu-id="1645f-109">A lapok tartalmazhatnak másodlagos vagy függő lapokat is.</span><span class="sxs-lookup"><span data-stu-id="1645f-109">Tabs can optionally contain secondary tabs, or dependency tabs.</span></span> <span data-ttu-id="1645f-110">Ez a lapot egy másik lapcsoportban lévő kiválasztástól teszi függővé.</span><span class="sxs-lookup"><span data-stu-id="1645f-110">This makes tabs dependent on the selection in another set of tabs.</span></span> <span data-ttu-id="1645f-111">Például:</span><span class="sxs-lookup"><span data-stu-id="1645f-111">Here's an example:</span></span>

```markdown
# [Azure CLI](#tab/azure-cli/linux)

Azure CLI content for Linux...

# [Azure CLI](#tab/azure-cli/windows)

Azure CLI content for Windows...

# [PowerShell](#tab/azure-powershell/linux)

PowerShell content for Linux...

# [PowerShell](#tab/azure-powershell/windows)

PowerShell content for Windows...

---
```

<span data-ttu-id="1645f-112">Az alábbi ellenőrzések a lapszintaxisra vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="1645f-112">The following validations apply to tab syntax:</span></span>

- <span data-ttu-id="1645f-113">A lapszintaxisnak helyesnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1645f-113">Tab syntax must be correct.</span></span>
- <span data-ttu-id="1645f-114">A függő lapokat egy előző lapcsoportban kell definiálni.</span><span class="sxs-lookup"><span data-stu-id="1645f-114">Dependent tabs must have been defined in a previous tab group.</span></span>
- <span data-ttu-id="1645f-115">A függőségnek csak egy szintje engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="1645f-115">Only one level of dependency is allowed.</span></span>
- <span data-ttu-id="1645f-116">Legalább két lapnak szerepelnie kell.</span><span class="sxs-lookup"><span data-stu-id="1645f-116">No fewer than two tabs are allowed.</span></span>
- <span data-ttu-id="1645f-117">Legfeljebb négy lap használata engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="1645f-117">No more than four tabs are allowed.</span></span>
- <span data-ttu-id="1645f-118">A lapokat engedélyezni kell.</span><span class="sxs-lookup"><span data-stu-id="1645f-118">Tabs must be whitelisted.</span></span>
- <span data-ttu-id="1645f-119">A lap/azonosító pároknak érvényesnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="1645f-119">Tab/ID pairs must be valid.</span></span>
- <span data-ttu-id="1645f-120">Ugyanabban a lapcsoportban nem szerepelhet többször ugyanaz a lapazonosító.</span><span class="sxs-lookup"><span data-stu-id="1645f-120">Cannot have the same tab ID multiple times in one tab group.</span></span>

## <a name="tab-whitelist"></a><span data-ttu-id="1645f-121">Engedélyezett lapok</span><span class="sxs-lookup"><span data-stu-id="1645f-121">Tab whitelist</span></span>

<span data-ttu-id="1645f-122">Az alábbi lapnév/lapazonosító párok vannak engedélyezve.</span><span class="sxs-lookup"><span data-stu-id="1645f-122">The following tab name/tab ID pairs are whitelisted.</span></span> <span data-ttu-id="1645f-123">A függő lapazonosítók nincsenek párosítva, de a lapazonosító oszlop alapján érvényesnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="1645f-123">Dependent tab IDs are not paired but must be valid per the Tab ID column.</span></span> <span data-ttu-id="1645f-124">Az értékek megkülönböztetik a kis- és nagybetűket</span><span class="sxs-lookup"><span data-stu-id="1645f-124">The values are case-sensitive</span></span>

|<span data-ttu-id="1645f-125">Lap neve</span><span class="sxs-lookup"><span data-stu-id="1645f-125">Tab name</span></span>              |<span data-ttu-id="1645f-126">Lap azonosítója</span><span class="sxs-lookup"><span data-stu-id="1645f-126">Tab ID</span></span>            |
|----------------------|------------------|
|`[.NET]`              |`(#tab/dotnet)`   |
|`[.NET Core 1.x]`     |`(#tab/netcore1x)`|
|`[.NET Core 2.x]`     |`(#tab/netcore2x)`|
|`[.NET Core 2.0]`     |`(#tab/netcore20)`|
|`[.NET Core 2.1]`     |`(#tab/netcore21)`|
|`[.NET Core 2.2]`     |`(#tab/netcore22)`|
|`[.NET Core 3.x]`     |`(#tab/netcore3x)`|
|`[.NET Core 3.0]`     |`(#tab/netcore30)`|
|`[.NET Core CLI]`     |`(#tab/netcore-cli)`|
|`[Azure CLI]`         |`(#tab/azure-cli)`|
|`[Android]`           |`(#tab/android)`  |
|`[Browser]`           |`(#tab/browser)`  |
|`[C#]`                |`(#tab/csharp)`   |
|`[C# Script]`         |`(#tab/csharp-script)`|
|`[CentOS]`            |`(#tab/centos)`|
|`[Command Line]`      |`(#tab/command-line)`|
|`[Debian]`            |`(#tab/debian)`|
|`[Docker Hub]`        |`(#tab/docker-hub)`|
|`[F#]`                |`(#tab/fsharp)`|
|`[Fedora]`            |`(#tab/fedora)`|
|`[iOS]`               |`(#tab/ios)`      |
|`[Java]`              |`(#tab/java)`|
|`[JavaScript]`        |`(#tab/javascript)`|
|`[Linux]`             |`(#tab/linux)`    |
|`[macOS]`             |`(#tab/macos)`    |
|`[Managed Kubernetes]`|`(#tab/kubernetes-managed)`|
|`[Maven]`             |`(#tab/maven)`|
|`[Mint]`              |`(#tab/mint)`|
|`[Node.js]`           |`(#tab/nodejs)`|
|`[npm]`               |`(#tab/npm)` |
|`[NuGet]`             |`(#tab/nuget)`|
|`[openSUSE]`          |`(#tab/opensuse)`|
|`[Other]`             |`(#tab/other)` |
|`[Oracle Linux]`      |`(#tab/oracle-linux)`|
|`[Package Manager]`   |`(#tab/package-manager)` |
|`[PEAR]`              |`(#tab/pear)`|
|`[pip]`               |`(#tab/pip)`|
|`[Portal]`            |`(#tab/azure-portal)`    |
|`[PowerShell]`        |`(#tab/azure-powershell)`|
|`[Private Registry]`  |`(#tab/private-registry)`|
|`[Python]`            |`(#tab/python)`|
|`[Resource Manager Template]`|`(#tab/azure-resource-manager)`|
|`[RHEL]`              |`(#tab/rhel)`|
|`[RubyGems]`          |`(#tab/rubygems)`|
|`[SQL Server]`        |`(#tab/sql-server)`|
|`[SQLite]`            |`(#tab/sqlite)`|
|`[TypeScript]`        |`(#tab/typescript)`|
|`[Visual Basic]`      |`(#tab/vb)` |
|`[Visual Studio]`     |`(#tab/visual-studio)`|
|`[Visual Studio 15.6 and earlier]`|`(#tab/vs156)`|
|`[Visual Studio 15.7 and later]`  |`(#tab/vs157)`|
|`[Visual Studio Code]`            |`(#tab/visual-studio-code)`|
|`[Visual Studio for Mac]`         |`(#tab/visual-studio-mac)`|
|`[Ubuntu]`                        |`(#tab/ubuntu)`|
|`[Unmanaged Kubernetes]`          |`(#tab/kubernetes-unmanaged)`|
|`[Windows]`   |`(#tab/windows)`   |