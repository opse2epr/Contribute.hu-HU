---
title: 'Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból | Microsoft Docs'
description: 'Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 27ebd3e348fc231d8b82e6c17f282bd9ca4afb9f
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308824"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a>Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból

Ez a rövid útmutató azt mutatja be, hogyan lehet tárolni a titkos kulcsokat a Key Vaultban, és hogyan lehet őket lekérni egy webalkalmazással. Ahhoz, hogy láthassa a titkos kulcs értékét, az Azure-ban kell dolgoznia. A rövid útmutató Node.js kódot és felügyeltszolgáltatás-identitásokat (MSI-ket) alkalmaz

> [!div class="checklist"]
> * Key Vault létrehozása.
> * Titkos kulcs tárolása a Key Vaultban.
> * Titkos kulcs lekérése a Key Vaultból.
> * Azure-webalkalmazás létrehozása.
> * [Felügyeltszolgáltatás-identitások engedélyezése](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).
> * A szükséges engedélyek megadása a webalkalmazás számára az adatoknak a Key Vaultból való olvasásához.

Mielőtt folytatná, győződjön meg arról, hogy tisztában van az [alapvető fogalmakkal](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).

> [!NOTE]
> Ahhoz, hogy megérthesse, miért az alábbi oktatóanyagban ismertetett folyamat az ajánlott eljárás, néhány fogalommal tisztában kell lennie. A Key Vault egy központi adattár a titkos kulcsok programozott módon való tárolásához. A használatához azonban az alkalmazásoknak/felhasználóknak először hitelesíteniük kell magukat a Key Vaultban, azaz be kell mutatniuk egy titkos kulcsot. Az ajánlott biztonsági eljárások betartása érdekében ezt az első titkos kulcsot rendszeres időközönként le kell váltani. Az Azure-ban futó [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview)-alkalmazásokhoz jár egy olyan identitás, amelyet az Azure automatikusan felügyel. Ez segít megoldani a **titkos kulcsok bemutatásának problémáját**, mivel a felhasználók/alkalmazások követhetik az ajánlott eljárásokat, és nem kell aggódniuk az első titkos kulcs leváltása miatt

## <a name="prerequisites"></a>Előfeltételek

::: zone pivot="nodejs"
* [Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"
* A [Visual Studio 2017 szoftver 15.7.3-as vagy újabb verziója](https://www.microsoft.com/net/download/windows) a következő számítási feladatokkal:
  * ASP.NET és webfejlesztés
  * .NET Core platformfüggetlen fejlesztés
* [.NET Core 2.1 SDK vagy újabb](https://www.microsoft.com/net/download/windows) ::: zone-end
* Git ([letöltés](https://git-scm.com/downloads)).
* Azure-előfizetés. Ha nem rendelkezik Azure-előfizetéssel, mindössze néhány perc alatt létrehozhat egy [ingyenes fiókot](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) a virtuális gép létrehozásának megkezdése előtt.
* Az [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) 2.0.4-es vagy újabb verziója. Ez elérhető Windows, Mac és Linux rendszerekhez.

## <a name="login-to-azure"></a>Bejelentkezés az Azure-ba

Ha az Azure-ba a parancssori felület használatával szeretne bejelentkezni, írja be a következőt:

```azurecli
az login
```

## <a name="create-resource-group"></a>Erőforráscsoport létrehozása

Hozzon létre egy erőforráscsoportot az [az group create](/cli/azure/group#az-group-create) paranccsal. Az Azure-erőforráscsoportok logikai tárolók, amelyekben az Azure-erőforrások telepítése és kezelése történik.

Válasszon egy erőforráscsoport-nevet, és töltse ki a helyőrzőt.
A következő példában létrehozunk egy *<YourResourceGroupName>* nevű erőforráscsoportot az *eastus* helyen.

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

Az oktatóanyag az imént létrehozott erőforráscsoport használja.

## <a name="create-an-azure-key-vault"></a>Azure Key Vault létrehozása

A következő lépésben létre fog hozni egy Key Vaultot az előző lépésben létrehozott erőforráscsoport használatával. Jóllehet ebben a cikkben a Key Vault neve „ContosoKeyVault”, egyedi nevet kell használnia. Adja meg az alábbi információkat:

* Tároló neve: **Itt válasszon kulcstárolónevet**.
* Erőforráscsoport neve: **Itt válasszon erőforráscsoport-nevet**.
* Hely: **USA keleti régiója**.

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

Az Azure-fiókja jelenleg az egyetlen, amelyik jogosult arra, hogy műveleteket végezzen ezen az új tárolón.

## <a name="add-a-secret-to-key-vault"></a>Titkos kulcs hozzáadása a Key Vaulthoz

Egy titkos kulcs hozzáadásával mutatjuk be ennek működését. Tárolhat egy SQL-kapcsolati sztringet, vagy bármely olyan adatot, amelyet biztonságosan kell tárolni, de elérhetővé kell tenni az alkalmazás számára. Ebben az oktatóanyagban a jelszó neve **AppSecret** lesz, és a **MySecret** értékét fogja tárolni.

Írja be az alábbi parancsokat, ha a **MySecret** értékét tároló titkos kulcsot szeretne létrehozni a Key Vaultban **AppSecret** névvel:

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

A titkos kódban tárolt érték megtekintése egyszerű szövegként:

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

Ez a parancs megjeleníti a titkos információkat, beleértve az URI-t is. A fenti lépések elvégzése után rendelkeznie kell egy Azure Key Vaultban tárolt titkos kulcshoz tartozó URI-val. Jegyezze fel ezt az információt. Egy későbbi lépésben szüksége lesz rá.

## <a name="clone-the-repo"></a>Az adattár klónozása

A forrás szerkesztéséhez szükséges helyi másolat létrehozásához klónozza az adattárat a következő parancs futtatásával:

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a>Függőségek telepítése

Itt a függőségeket telepítjük. Futtassa a következő parancsokat: cd key-vault-node-quickstart npm install

Ez a projekt 2 csomópontmodult használt:

* [ms-rest-azure](https://www.npmjs.com/package/ms-rest-azure) 
* [azure-keyvault](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a>A webalkalmazás közzététele az Azure-ban

Az alábbiak ismertetik azt a néhány lépést, amelyet végre kell hajtanunk

* Az első lépés egy [Azure App Service](https://azure.microsoft.com/services/app-service/)-csomag létrehozása. Ebben a csomagban több webalkalmazást is tárolhat.

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* Ezután létrehozunk egy webalkalmazást. A következő példában cserélje ki az <app_name> helyőrzőt egy globálisan egyedi névre (érvényes karakterek: a–z, 0–9 és -). A futtatókörnyezet beállítása: NODE|6.9. Az összes támogatott futtatókörnyezet megtekintéséhez futtassa az az webapp list-runtimes parancsot

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    A webalkalmazás létrehozása után az Azure CLI az alábbi példához hasonló eredményeket jelenít meg:

    ```json
    {
      "availabilityState": "Normal",
      "clientAffinityEnabled": true,
      "clientCertEnabled": false,
      "cloningInfo": null,
      "containerSize": 0,
      "dailyMemoryTimeQuota": 0,
      "defaultHostName": "<app_name>.azurewebsites.net",
      "enabled": true,
      "deploymentLocalGitUrl": "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git"
      < JSON data removed for brevity. >
    }
    ```
    Tallózással keresse meg az újonnan létrehozott webalkalmazást, és láthatja, hogy az működik. Az <app_name> helyőrző helyett adjon meg egy egyedi nevet.

    ```text
    http://<app name>.azurewebsites.net
    ```
    A fenti parancs egy Git-kompatibilis alkalmazást is létrehoz, amely lehetővé teszi az Azure-ba történő üzembe helyezést a helyi Git-adattárból. 
    A helyi Git-adattár a következő URL-címmel van konfigurálva: „https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git”

* Üzembe helyező felhasználó létrehozása Az előző parancs lefutását követően hozzáadhat egy távoli Azure-mappát a helyi Git-adattárhoz. Cserélje le a <url> részt a távoli Git-elem URL-címére, amelyet a Git az alkalmazáson való engedélyezése során kapott meg.

    ```bash
    git remote add azure <url>
    ```
    
::: zone-end

::: zone pivot="dotnet"
## <a name="open-and-edit-the-solution"></a>A megoldás megnyitása és szerkesztése

Módosítsa a program.cs fájlt, hogy a minta az adott kulcstartó nevével fusson:

1. Lépjen a key-vault-dotnet-core-quickstart mappára.
2. Nyissa meg a key-vault-dotnet-core-quickstart.sln fájlt a Visual Studio 2017-ben.
3. Nyissa meg a program.cs fájlt, és a *YourKeyVaultName* helyőrzőt cserélje le a korábban létrehozott kulcstartó nevére.

Ez a megoldás [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) és [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet-kódtárakat használ.

## <a name="run-the-app"></a>Az alkalmazás futtatása

A Visual Studio 2017 főmenüjében válassza a **Debug** > **Start** without Debugging (Hibakeresés > Indítás hibakeresés nélkül) elemet. Amikor megjelenik a böngésző, lépjen az **About** (Névjegy) oldalra. Megjelenik az **AppSecret** értéke.

## <a name="publish-the-web-application-to-azure"></a>A webalkalmazás közzététele az Azure-ban

Tegye közzé ezt az alkalmazást az Azure-ban, hogy élő webalkalmazásként megtekinthető legyen, illetve hogy látható legyen, hogy a titkos érték lekérhető-e:

1. A Visual Studióban válassza a **key-vault-dotnet-core-quickstart** projektet.
2. Válassza a **Publish** > **Start** (Közzététel > Indítás) lehetőséget.
3. Hozzon létre egy új **App Service-t**, majd kattintson a **Publish** (Közzététel) parancsra.
4. Módosítsa az alkalmazás nevét a következőre: **keyvaultdotnetcorequickstart**.
5. Kattintson a **Létrehozás** gombra.

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
::: zone-end

## <a name="enable-managed-service-identities"></a>Felügyeltszolgáltatás-identitások engedélyezése

Az Azure Key Vault módot kínál a hitelesítő adatok, valamint egyéb kulcsok és titkos kódok biztonságos tárolására, azonban a kódnak hitelesítenie kell magát az Azure Key Vaultban az adatok lekéréséhez. A felügyeltszolgáltatás-identitás segít leegyszerűsíteni ezt, mivel az Azure-szolgáltatások számára egy automatikusan felügyelt identitást biztosít az Azure Active Directoryban (Azure AD-ben). Ezzel az identitással bármely, az Azure AD-hitelesítést támogató szolgáltatásban, többek között a Key Vaultban is elvégezheti a hitelesítést anélkül, hogy a hitelesítő adatokat a kódban kellene tárolnia.

1. Térjen vissza az Azure CLI-hez.
2. Futtassa az identitás hozzárendelésére szolgáló parancsot az alkalmazás identitásának létrehozásához:

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
>Az ebben az eljárásban használt parancs egyenértékű azzal, mintha megnyitná a portált, és a webalkalmazás tulajdonságai között átállítaná a **Felügyeltszolgáltatás-identitás** beállítást **Be** értékűre.

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a>Engedélyek kiosztása az alkalmazásnak a Key Vault titkos kulcsainak olvasásához

Jegyezze fel a kimenetből származó adatokat, amikor az Azure-ban közzéteszi az alkalmazást. Az adatok a következő formátumban jelennek meg:

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

Ezután futtassa ezt a parancsot a kulcstartó neve és a **PrincipalId** értéke használatával:

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a>A Node-alkalmazás üzembe helyezése az Azure-ban és a titkos kulcs értékének lekérése

Most már minden készen áll. Futtassa az alábbi parancsot az alkalmazás üzembe helyezéséhez az Azure-ban

```bash
git push azure master
```

Ezután a https://<app_name>.azurewebsites.net helyre lépve már láthatja a titkos kód értékét.
Ne feledje a(z) <YourKeyVaultName> helyőrzőt lecserélni a tároló nevére

::: zone-end

::: zone pivot="dotnet" Az alkalmazás futtatásakor meg kell jelennie a titkos kulcs lekért értékének.
::: zone-end

## <a name="next-steps"></a>Következő lépések

::: zone pivot="nodejs"
* [Az Azure Key Vault kezdőlapja](https://azure.microsoft.com/services/key-vault/)
* [Az Azure Key Vault dokumentációja](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK For Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* [Azure – REST API-referencia](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end

::: zone pivot="dotnet"
* [Az Azure Key Vault kezdőlapja](https://azure.microsoft.com/services/key-vault/)
* [Az Azure Key Vault dokumentációja](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK for .NET](https://github.com/Azure/azure-sdk-for-net)
* [Azure – REST API-referencia](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end
