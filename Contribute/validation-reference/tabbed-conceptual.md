---
ms.date: 03/29/2019
title: Többlapos fogalmi tartalom
ms.openlocfilehash: 3d6f38c1659297182a8bd50bf52b9853bd21b2c8
ms.sourcegitcommit: 1e53d17639277bebd89b2e7cabeb45bdad526354
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2019
ms.locfileid: "66841288"
---
# <a name="tabbed-conceptual"></a><span data-ttu-id="2b355-102">Többlapos fogalmi tartalom</span><span class="sxs-lookup"><span data-stu-id="2b355-102">Tabbed conceptual</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b355-103">A többlapos fogalmi tartalom szintaxisát kivontuk, ezért új lapokat már ne adjon hozzá.</span><span class="sxs-lookup"><span data-stu-id="2b355-103">The tabbed conceptual syntax has been deprecated and new tabs should not be added.</span></span> <span data-ttu-id="2b355-104">Az itt ismertetett ellenőrzés olyan tartalmakra vonatkozik, amelyeket jóváhagytak többlapos fogalmi tartalom használatára, amíg az újabb funkció nem lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="2b355-104">The validations described in this article apply to content sets that have been approved to use tabbed conceptual until replacement functionality is available.</span></span>

## <a name="tab-syntax"></a><span data-ttu-id="2b355-105">Lapszintaxis</span><span class="sxs-lookup"><span data-stu-id="2b355-105">Tab syntax</span></span>

<span data-ttu-id="2b355-106">A lapokra vonatkozó szintaxis a következő:</span><span class="sxs-lookup"><span data-stu-id="2b355-106">The syntax for tabs is as follows:</span></span>

<span data-ttu-id="2b355-107">Egyszintű lap:</span><span class="sxs-lookup"><span data-stu-id="2b355-107">Single level tab:</span></span>

`# [Tab Display Name](#tab/tab-id)`

<span data-ttu-id="2b355-108">Nem kötelező függő lap:</span><span class="sxs-lookup"><span data-stu-id="2b355-108">Optional dependent tab:</span></span>

`# [Tab Display Name](#tab/tab-id/tab-condition)`

<span data-ttu-id="2b355-109">Példa egyszintű lapszakaszra két lappal és a lapcsoport elválasztójával (---):</span><span class="sxs-lookup"><span data-stu-id="2b355-109">Example of a single-level tab section with two tabs and the tab group terminator (---):</span></span>

```markdown
# [Linux](#tab/linux)

Content for Linux...

# [Windows](#tab/windows)

Content for Windows...

---
```

<span data-ttu-id="2b355-110">A lapok tartalmazhatnak másodlagos vagy függő lapokat is.</span><span class="sxs-lookup"><span data-stu-id="2b355-110">Tabs can optionally contain secondary tabs, or dependency tabs.</span></span> <span data-ttu-id="2b355-111">Ez a lapot egy másik lapcsoportban lévő kiválasztástól teszi függővé.</span><span class="sxs-lookup"><span data-stu-id="2b355-111">This makes tabs dependent on the selection in another set of tabs.</span></span> <span data-ttu-id="2b355-112">Például:</span><span class="sxs-lookup"><span data-stu-id="2b355-112">Here's an example:</span></span>

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

<span data-ttu-id="2b355-113">Az alábbi ellenőrzések a lapszintaxisra vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="2b355-113">The following validations apply to tab syntax:</span></span>

- <span data-ttu-id="2b355-114">A lapszintaxisnak helyesnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2b355-114">Tab syntax must be correct.</span></span>
- <span data-ttu-id="2b355-115">A függő lapokat egy előző lapcsoportban kell definiálni.</span><span class="sxs-lookup"><span data-stu-id="2b355-115">Dependent tabs must have been defined in a previous tab group.</span></span>
- <span data-ttu-id="2b355-116">A függőségnek csak egy szintje engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="2b355-116">Only one level of dependency is allowed.</span></span>
- <span data-ttu-id="2b355-117">Legalább két lapnak szerepelnie kell.</span><span class="sxs-lookup"><span data-stu-id="2b355-117">No fewer than two tabs are allowed.</span></span>
- <span data-ttu-id="2b355-118">Legfeljebb négy lap használata engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="2b355-118">No more than four tabs are allowed.</span></span>
- <span data-ttu-id="2b355-119">A lapokat jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="2b355-119">Tabs must be approved.</span></span>
- <span data-ttu-id="2b355-120">A lap/azonosító pároknak érvényesnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="2b355-120">Tab/ID pairs must be valid.</span></span>
- <span data-ttu-id="2b355-121">Ugyanabban a lapcsoportban nem szerepelhet többször ugyanaz a lapazonosító.</span><span class="sxs-lookup"><span data-stu-id="2b355-121">Cannot have the same tab ID multiple times in one tab group.</span></span>

## <a name="approved-tabs"></a><span data-ttu-id="2b355-122">Jóváhagyott lapok</span><span class="sxs-lookup"><span data-stu-id="2b355-122">Approved tabs</span></span>

<span data-ttu-id="2b355-123">Az alábbi lapnév/lapazonosító párok vannak jóváhagyva.</span><span class="sxs-lookup"><span data-stu-id="2b355-123">The following tab name/tab ID pairs are approved.</span></span> <span data-ttu-id="2b355-124">A függő lapazonosítók nincsenek párosítva, de a lapazonosító oszlop alapján érvényesnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="2b355-124">Dependent tab IDs are not paired but must be valid per the Tab ID column.</span></span> <span data-ttu-id="2b355-125">Az értékek megkülönböztetik a kis- és nagybetűket</span><span class="sxs-lookup"><span data-stu-id="2b355-125">The values are case-sensitive</span></span>

|<span data-ttu-id="2b355-126">Lap neve</span><span class="sxs-lookup"><span data-stu-id="2b355-126">Tab name</span></span>              |<span data-ttu-id="2b355-127">Lap azonosítója</span><span class="sxs-lookup"><span data-stu-id="2b355-127">Tab ID</span></span>            |
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