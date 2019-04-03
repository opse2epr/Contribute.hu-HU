---
ms.date: 03/29/2019
ms.openlocfilehash: 4e07ecf777f1361e21343b7b80f59ad9c5e86b3e
ms.sourcegitcommit: af37d44eb67daa2841959817cd205ec95db18cec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653413"
---
# <a name="tabbed-conceptual"></a>Többlapos fogalmi tartalom

> [!IMPORTANT]
> A többlapos fogalmi tartalom szintaxisát kivontuk, ezért új lapokat már ne adjon hozzá. Az itt ismertetett ellenőrzés olyan tartalmakra vonatkozik, amelyeket jóváhagytak többlapos fogalmi tartalom használatára, amíg az újabb funkció nem lesz elérhető.

## <a name="tab-syntax"></a>Lapszintaxis

A lapokra vonatkozó szintaxis a következő:

Egyszintű lap:

`# [Tab Display Name](#tab/tab-id)`

Nem kötelező függő lap:

`# [Tab Display Name](#tab/tab-id/tab-condition)`

Példa egyszintű lapszakaszra két lappal és a lapcsoport elválasztójával (---):

```markdown
# [Linux](#tab/linux)

Content for Linux...

# [Windows](#tab/windows)

Content for Windows...

---
```

A lapok tartalmazhatnak másodlagos vagy függő lapokat is. Ez a lapot egy másik lapcsoportban lévő kiválasztástól teszi függővé. Például:

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

Az alábbi ellenőrzések a lapszintaxisra vonatkoznak:

- A lapszintaxisnak helyesnek kell lennie.
- A függő lapokat egy előző lapcsoportban kell definiálni.
- A függőségnek csak egy szintje engedélyezett.
- Legalább két lapnak szerepelnie kell.
- Legfeljebb négy lap használata engedélyezett.
- A lapokat jóvá kell hagyni.
- A lap/azonosító pároknak érvényesnek kell lenniük.
- Ugyanabban a lapcsoportban nem szerepelhet többször ugyanaz a lapazonosító.

## <a name="approved-tabs"></a>Jóváhagyott lapok

Az alábbi lapnév/lapazonosító párok vannak jóváhagyva. A függő lapazonosítók nincsenek párosítva, de a lapazonosító oszlop alapján érvényesnek kell lenniük. Az értékek megkülönböztetik a kis- és nagybetűket

|Lap neve              |Lap azonosítója            |
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