---
title: 'Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból | Microsoft Docs'
description: 'Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages, keyvault-platforms
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b758274203748bb6e04c03dec5de38fb77947b4
ms.sourcegitcommit: b0105f322f91bb4dbde47f6da35b3c12271d5b03
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43239571"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="7bf02-103">Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból</span><span class="sxs-lookup"><span data-stu-id="7bf02-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="7bf02-104">Ez a rövid útmutató azt mutatja be, hogyan lehet tárolni a titkos kulcsokat a Key Vaultban, és hogyan lehet őket lekérni egy webalkalmazással.</span><span class="sxs-lookup"><span data-stu-id="7bf02-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="7bf02-105">Ahhoz, hogy láthassa a titkos kulcs értékét, az Azure-ban kell dolgoznia.</span><span class="sxs-lookup"><span data-stu-id="7bf02-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="7bf02-106">A rövid útmutató Node.js kódot és felügyeltszolgáltatás-identitásokat (MSI-ket) alkalmaz</span><span class="sxs-lookup"><span data-stu-id="7bf02-106">The quickstart uses Node.js and Managed service identities (MSIs)</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="7bf02-107">Key Vault létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7bf02-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="7bf02-108">Titkos kulcs tárolása a Key Vaultban.</span><span class="sxs-lookup"><span data-stu-id="7bf02-108">Store a secret in Key Vault.</span></span>
> * <span data-ttu-id="7bf02-109">Titkos kulcs lekérése a Key Vaultból.</span><span class="sxs-lookup"><span data-stu-id="7bf02-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="7bf02-110">Azure-webalkalmazás létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7bf02-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="7bf02-111">[Felügyeltszolgáltatás-identitások engedélyezése](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="7bf02-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="7bf02-112">A szükséges engedélyek megadása a webalkalmazás számára az adatoknak a Key Vaultból való olvasásához.</span><span class="sxs-lookup"><span data-stu-id="7bf02-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="7bf02-113">Mielőtt folytatná, győződjön meg arról, hogy tisztában van az [alapvető fogalmakkal](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span><span class="sxs-lookup"><span data-stu-id="7bf02-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

>[!NOTE]
<span data-ttu-id="7bf02-114">Ahhoz, hogy megérthesse, miért az alábbi oktatóanyagban ismertetett folyamat az ajánlott eljárás, néhány fogalommal tisztában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7bf02-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="7bf02-115">A Key Vault egy központi adattár a titkos kulcsok programozott módon való tárolásához.</span><span class="sxs-lookup"><span data-stu-id="7bf02-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="7bf02-116">A használatához azonban az alkalmazásoknak/felhasználóknak először hitelesíteniük kell magukat a Key Vaultban, azaz be kell mutatniuk egy titkos kulcsot.</span><span class="sxs-lookup"><span data-stu-id="7bf02-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="7bf02-117">Az ajánlott biztonsági eljárások betartása érdekében ezt az első titkos kulcsot rendszeres időközönként le kell váltani.</span><span class="sxs-lookup"><span data-stu-id="7bf02-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="7bf02-118">Az Azure-ban futó [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview)-alkalmazásokhoz jár egy olyan identitás, amelyet az Azure automatikusan felügyel.</span><span class="sxs-lookup"><span data-stu-id="7bf02-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="7bf02-119">Ez segít megoldani a **titkos kulcsok bemutatásának problémáját**, mivel a felhasználók/alkalmazások követhetik az ajánlott eljárásokat, és nem kell aggódniuk az első titkos kulcs leváltása miatt</span><span class="sxs-lookup"><span data-stu-id="7bf02-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7bf02-120">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7bf02-120">Prerequisites</span></span>

<span data-ttu-id="7bf02-121">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="7bf02-121">::: zone pivot="nodejs"</span></span>
* <span data-ttu-id="7bf02-122">[Node JS](https://nodejs.org/en/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-122">[Node JS](https://nodejs.org/en/) ::: zone-end</span></span>

<span data-ttu-id="7bf02-123">::: zone pivot="dotnet, windows"</span><span class="sxs-lookup"><span data-stu-id="7bf02-123">::: zone pivot="dotnet, windows"</span></span>
* <span data-ttu-id="7bf02-124">A [Visual Studio 2017 szoftver 15.7.3-as vagy újabb verziója](https://www.microsoft.com/net/download/windows) a következő számítási feladatokkal:</span><span class="sxs-lookup"><span data-stu-id="7bf02-124">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="7bf02-125">ASP.NET és webfejlesztés</span><span class="sxs-lookup"><span data-stu-id="7bf02-125">ASP.NET and web development</span></span>
  * <span data-ttu-id="7bf02-126">.NET Core platformfüggetlen fejlesztés</span><span class="sxs-lookup"><span data-stu-id="7bf02-126">.NET Core cross-platform development</span></span>
* <span data-ttu-id="7bf02-127">[.NET Core 2.1 SDK vagy újabb](https://www.microsoft.com/net/download/windows) :::zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-127">[.NET Core 2.1 SDK or later](https://www.microsoft.com/net/download/windows) :::zone-end</span></span>

<span data-ttu-id="7bf02-128">::: zone pivot="dotnet, mac"</span><span class="sxs-lookup"><span data-stu-id="7bf02-128">::: zone pivot="dotnet, mac"</span></span>
* <span data-ttu-id="7bf02-129">Lásd a [Visual Studio for Mac újdonságait](https://visualstudio.microsoft.com/vs/mac/) bemutató cikket.</span><span class="sxs-lookup"><span data-stu-id="7bf02-129">See [What’s New in Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/).</span></span>
<span data-ttu-id="7bf02-130">:::zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-130">:::zone-end</span></span>

* <span data-ttu-id="7bf02-131">Git ([letöltés](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="7bf02-131">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="7bf02-132">Azure-előfizetés.</span><span class="sxs-lookup"><span data-stu-id="7bf02-132">An Azure subscription.</span></span> <span data-ttu-id="7bf02-133">Ha nem rendelkezik Azure-előfizetéssel, mindössze néhány perc alatt létrehozhat egy [ingyenes fiókot](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) a virtuális gép létrehozásának megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="7bf02-133">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="7bf02-134">Az [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) 2.0.4-es vagy újabb verziója.</span><span class="sxs-lookup"><span data-stu-id="7bf02-134">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="7bf02-135">Ez elérhető Windows, Mac és Linux rendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="7bf02-135">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="7bf02-136">Bejelentkezés az Azure-ba</span><span class="sxs-lookup"><span data-stu-id="7bf02-136">Login to Azure</span></span>

<span data-ttu-id="7bf02-137">Ha az Azure-ba a parancssori felület használatával szeretne bejelentkezni, írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="7bf02-137">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="7bf02-138">Erőforráscsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="7bf02-138">Create resource group</span></span>

<span data-ttu-id="7bf02-139">Hozzon létre egy erőforráscsoportot az [az group create](/cli/azure/group#az-group-create) paranccsal.</span><span class="sxs-lookup"><span data-stu-id="7bf02-139">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="7bf02-140">Az Azure-erőforráscsoportok logikai tárolók, amelyekben az Azure-erőforrások telepítése és kezelése történik.</span><span class="sxs-lookup"><span data-stu-id="7bf02-140">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="7bf02-141">Válasszon egy erőforráscsoport-nevet, és töltse ki a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="7bf02-141">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="7bf02-142">A következő példában létrehozunk egy *<YourResourceGroupName>* nevű erőforráscsoportot az *eastus* helyen.</span><span class="sxs-lookup"><span data-stu-id="7bf02-142">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="7bf02-143">Az oktatóanyag az imént létrehozott erőforráscsoport használja.</span><span class="sxs-lookup"><span data-stu-id="7bf02-143">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="7bf02-144">Azure Key Vault létrehozása</span><span class="sxs-lookup"><span data-stu-id="7bf02-144">Create an Azure Key Vault</span></span>

<span data-ttu-id="7bf02-145">A következő lépésben létre fog hozni egy Key Vaultot az előző lépésben létrehozott erőforráscsoport használatával.</span><span class="sxs-lookup"><span data-stu-id="7bf02-145">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="7bf02-146">Jóllehet ebben a cikkben a Key Vault neve „ContosoKeyVault”, egyedi nevet kell használnia.</span><span class="sxs-lookup"><span data-stu-id="7bf02-146">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="7bf02-147">Adja meg az alábbi információkat:</span><span class="sxs-lookup"><span data-stu-id="7bf02-147">Provide the following information:</span></span>

* <span data-ttu-id="7bf02-148">Tároló neve: **Itt válasszon kulcstárolónevet**.</span><span class="sxs-lookup"><span data-stu-id="7bf02-148">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="7bf02-149">Erőforráscsoport neve: **Itt válasszon erőforráscsoport-nevet**.</span><span class="sxs-lookup"><span data-stu-id="7bf02-149">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="7bf02-150">Hely: **USA keleti régiója**.</span><span class="sxs-lookup"><span data-stu-id="7bf02-150">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="7bf02-151">Az Azure-fiókja jelenleg az egyetlen, amelyik jogosult arra, hogy műveleteket végezzen ezen az új tárolón.</span><span class="sxs-lookup"><span data-stu-id="7bf02-151">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="7bf02-152">Titkos kulcs hozzáadása a Key Vaulthoz</span><span class="sxs-lookup"><span data-stu-id="7bf02-152">Add a secret to key vault</span></span>

<span data-ttu-id="7bf02-153">Egy titkos kulcs hozzáadásával mutatjuk be ennek működését.</span><span class="sxs-lookup"><span data-stu-id="7bf02-153">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="7bf02-154">Tárolhat egy SQL-kapcsolati sztringet, vagy bármely olyan adatot, amelyet biztonságosan kell tárolni, de elérhetővé kell tenni az alkalmazás számára.</span><span class="sxs-lookup"><span data-stu-id="7bf02-154">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="7bf02-155">Ebben az oktatóanyagban a jelszó neve **AppSecret** lesz, és a **MySecret** értékét fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="7bf02-155">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="7bf02-156">Írja be az alábbi parancsokat, ha a **MySecret** értékét tároló titkos kulcsot szeretne létrehozni a Key Vaultban **AppSecret** névvel:</span><span class="sxs-lookup"><span data-stu-id="7bf02-156">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="7bf02-157">A titkos kódban tárolt érték megtekintése egyszerű szövegként:</span><span class="sxs-lookup"><span data-stu-id="7bf02-157">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="7bf02-158">Ez a parancs megjeleníti a titkos információkat, beleértve az URI-t is.</span><span class="sxs-lookup"><span data-stu-id="7bf02-158">This command shows the secret information including the URI.</span></span> <span data-ttu-id="7bf02-159">A fenti lépések elvégzése után rendelkeznie kell egy Azure Key Vaultban tárolt titkos kulcshoz tartozó URI-val.</span><span class="sxs-lookup"><span data-stu-id="7bf02-159">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="7bf02-160">Jegyezze fel ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="7bf02-160">Write this information down.</span></span> <span data-ttu-id="7bf02-161">Egy későbbi lépésben szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="7bf02-161">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="7bf02-162">Az adattár klónozása</span><span class="sxs-lookup"><span data-stu-id="7bf02-162">Clone the Repo</span></span>

<span data-ttu-id="7bf02-163">A forrás szerkesztéséhez szükséges helyi másolat létrehozásához klónozza az adattárat a következő parancs futtatásával:</span><span class="sxs-lookup"><span data-stu-id="7bf02-163">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

<span data-ttu-id="7bf02-164">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="7bf02-164">::: zone pivot="nodejs"</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="7bf02-165">Függőségek telepítése</span><span class="sxs-lookup"><span data-stu-id="7bf02-165">Install dependencies</span></span>

<span data-ttu-id="7bf02-166">Itt a függőségeket telepítjük.</span><span class="sxs-lookup"><span data-stu-id="7bf02-166">Here we install the dependencies.</span></span> <span data-ttu-id="7bf02-167">Futtassa a következő parancsokat: cd key-vault-node-quickstart npm install</span><span class="sxs-lookup"><span data-stu-id="7bf02-167">Run the following commands cd key-vault-node-quickstart npm install</span></span>

<span data-ttu-id="7bf02-168">Ez a projekt 2 csomópontmodult használt:</span><span class="sxs-lookup"><span data-stu-id="7bf02-168">This project used 2 node modules:</span></span>

* [<span data-ttu-id="7bf02-169">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="7bf02-169">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="7bf02-170">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="7bf02-170">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="7bf02-171">A webalkalmazás közzététele az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="7bf02-171">Publish the web application to Azure</span></span>

<span data-ttu-id="7bf02-172">Az alábbiak ismertetik azt a néhány lépést, amelyet végre kell hajtanunk</span><span class="sxs-lookup"><span data-stu-id="7bf02-172">Below are the few steps we need to do</span></span>

* <span data-ttu-id="7bf02-173">Az első lépés egy [Azure App Service](https://azure.microsoft.com/services/app-service/)-csomag létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7bf02-173">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="7bf02-174">Ebben a csomagban több webalkalmazást is tárolhat.</span><span class="sxs-lookup"><span data-stu-id="7bf02-174">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="7bf02-175">Ezután létrehozunk egy webalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="7bf02-175">Next we create a web app.</span></span> <span data-ttu-id="7bf02-176">A következő példában cserélje ki az <app_name> helyőrzőt egy globálisan egyedi névre (érvényes karakterek: a–z, 0–9 és -).</span><span class="sxs-lookup"><span data-stu-id="7bf02-176">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="7bf02-177">A futtatókörnyezet beállítása: NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="7bf02-177">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="7bf02-178">Az összes támogatott futtatókörnyezet megtekintéséhez futtassa az az webapp list-runtimes parancsot</span><span class="sxs-lookup"><span data-stu-id="7bf02-178">To see all supported runtimes, run az webapp list-runtimes</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="7bf02-179">A webalkalmazás létrehozása után az Azure CLI az alábbi példához hasonló eredményeket jelenít meg:</span><span class="sxs-lookup"><span data-stu-id="7bf02-179">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="7bf02-180">Tallózással keresse meg az újonnan létrehozott webalkalmazást, és láthatja, hogy az működik.</span><span class="sxs-lookup"><span data-stu-id="7bf02-180">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="7bf02-181">Az <app_name> helyőrző helyett adjon meg egy egyedi nevet.</span><span class="sxs-lookup"><span data-stu-id="7bf02-181">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="7bf02-182">A fenti parancs egy Git-kompatibilis alkalmazást is létrehoz, amely lehetővé teszi az Azure-ba történő üzembe helyezést a helyi Git-adattárból.</span><span class="sxs-lookup"><span data-stu-id="7bf02-182">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="7bf02-183">A helyi Git-adattár a következő URL-címmel van konfigurálva: „https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git”</span><span class="sxs-lookup"><span data-stu-id="7bf02-183">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="7bf02-184">Üzembe helyező felhasználó létrehozása Az előző parancs lefutását követően hozzáadhat egy távoli Azure-mappát a helyi Git-adattárhoz.</span><span class="sxs-lookup"><span data-stu-id="7bf02-184">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="7bf02-185">Cserélje le a <url> részt a távoli Git-elem URL-címére, amelyet a Git az alkalmazáson való engedélyezése során kapott meg.</span><span class="sxs-lookup"><span data-stu-id="7bf02-185">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
<span data-ttu-id="7bf02-186">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-186">::: zone-end</span></span>

<span data-ttu-id="7bf02-187">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="7bf02-187">::: zone pivot="dotnet"</span></span>

## <a name="open-and-edit-the-solution"></a><span data-ttu-id="7bf02-188">A megoldás megnyitása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="7bf02-188">Open and edit the solution</span></span>

<span data-ttu-id="7bf02-189">Módosítsa a program.cs fájlt, hogy a minta az adott kulcstartó nevével fusson:</span><span class="sxs-lookup"><span data-stu-id="7bf02-189">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="7bf02-190">Lépjen a key-vault-dotnet-core-quickstart mappára.</span><span class="sxs-lookup"><span data-stu-id="7bf02-190">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="7bf02-191">Nyissa meg a key-vault-dotnet-core-quickstart.sln fájlt a Visual Studio 2017-ben.</span><span class="sxs-lookup"><span data-stu-id="7bf02-191">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="7bf02-192">Nyissa meg a program.cs fájlt, és a *YourKeyVaultName* helyőrzőt cserélje le a korábban létrehozott kulcstartó nevére.</span><span class="sxs-lookup"><span data-stu-id="7bf02-192">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="7bf02-193">Ez a megoldás [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) és [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet-kódtárakat használ.</span><span class="sxs-lookup"><span data-stu-id="7bf02-193">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="7bf02-194">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="7bf02-194">Run the app</span></span>

<span data-ttu-id="7bf02-195">A Visual Studio 2017 főmenüjében válassza a **Debug** > **Start** without Debugging (Hibakeresés > Indítás hibakeresés nélkül) elemet.</span><span class="sxs-lookup"><span data-stu-id="7bf02-195">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="7bf02-196">Amikor megjelenik a böngésző, lépjen az **About** (Névjegy) oldalra.</span><span class="sxs-lookup"><span data-stu-id="7bf02-196">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="7bf02-197">Megjelenik az **AppSecret** értéke.</span><span class="sxs-lookup"><span data-stu-id="7bf02-197">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="7bf02-198">A webalkalmazás közzététele az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="7bf02-198">Publish the web application to Azure</span></span>

<span data-ttu-id="7bf02-199">Tegye közzé ezt az alkalmazást az Azure-ban, hogy élő webalkalmazásként megtekinthető legyen, illetve hogy látható legyen, hogy a titkos érték lekérhető-e:</span><span class="sxs-lookup"><span data-stu-id="7bf02-199">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="7bf02-200">A Visual Studióban válassza a **key-vault-dotnet-core-quickstart** projektet.</span><span class="sxs-lookup"><span data-stu-id="7bf02-200">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="7bf02-201">Válassza a **Publish** > **Start** (Közzététel > Indítás) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7bf02-201">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="7bf02-202">Hozzon létre egy új **App Service-t**, majd kattintson a **Publish** (Közzététel) parancsra.</span><span class="sxs-lookup"><span data-stu-id="7bf02-202">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="7bf02-203">Módosítsa az alkalmazás nevét a következőre: **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="7bf02-203">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="7bf02-204">Kattintson a **Létrehozás** gombra.</span><span class="sxs-lookup"><span data-stu-id="7bf02-204">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]

<span data-ttu-id="7bf02-205">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-205">::: zone-end</span></span>

## <a name="enable-managed-service-identities"></a><span data-ttu-id="7bf02-206">Felügyeltszolgáltatás-identitások engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7bf02-206">Enable managed service identities</span></span>

<span data-ttu-id="7bf02-207">Az Azure Key Vault módot kínál a hitelesítő adatok, valamint egyéb kulcsok és titkos kódok biztonságos tárolására, azonban a kódnak hitelesítenie kell magát az Azure Key Vaultban az adatok lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="7bf02-207">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="7bf02-208">A felügyeltszolgáltatás-identitás segít leegyszerűsíteni ezt, mivel az Azure-szolgáltatások számára egy automatikusan felügyelt identitást biztosít az Azure Active Directoryban (Azure AD-ben).</span><span class="sxs-lookup"><span data-stu-id="7bf02-208">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7bf02-209">Ezzel az identitással bármely, az Azure AD-hitelesítést támogató szolgáltatásban, többek között a Key Vaultban is elvégezheti a hitelesítést anélkül, hogy a hitelesítő adatokat a kódban kellene tárolnia.</span><span class="sxs-lookup"><span data-stu-id="7bf02-209">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="7bf02-210">Térjen vissza az Azure CLI-hez.</span><span class="sxs-lookup"><span data-stu-id="7bf02-210">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="7bf02-211">Futtassa az identitás hozzárendelésére szolgáló parancsot az alkalmazás identitásának létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="7bf02-211">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="7bf02-212">Az ebben az eljárásban használt parancs egyenértékű azzal, mintha megnyitná a portált, és a webalkalmazás tulajdonságai között átállítaná a **Felügyeltszolgáltatás-identitás** beállítást **Be** értékűre.</span><span class="sxs-lookup"><span data-stu-id="7bf02-212">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="7bf02-213">Engedélyek kiosztása az alkalmazásnak a Key Vault titkos kulcsainak olvasásához</span><span class="sxs-lookup"><span data-stu-id="7bf02-213">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="7bf02-214">Jegyezze fel a kimenetből származó adatokat, amikor az Azure-ban közzéteszi az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="7bf02-214">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="7bf02-215">Az adatok a következő formátumban jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="7bf02-215">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="7bf02-216">Ezután futtassa ezt a parancsot a kulcstartó neve és a **PrincipalId** értéke használatával:</span><span class="sxs-lookup"><span data-stu-id="7bf02-216">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

<span data-ttu-id="7bf02-217">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="7bf02-217">::: zone pivot="nodejs"</span></span>
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="7bf02-218">A Node-alkalmazás üzembe helyezése az Azure-ban és a titkos kulcs értékének lekérése</span><span class="sxs-lookup"><span data-stu-id="7bf02-218">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="7bf02-219">Most már minden készen áll.</span><span class="sxs-lookup"><span data-stu-id="7bf02-219">Now that everything is set.</span></span> <span data-ttu-id="7bf02-220">Futtassa az alábbi parancsot az alkalmazás üzembe helyezéséhez az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="7bf02-220">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="7bf02-221">Ezután a https://<app_name>.azurewebsites.net helyre lépve már láthatja a titkos kód értékét.</span><span class="sxs-lookup"><span data-stu-id="7bf02-221">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="7bf02-222">Ne feledje a(z) <YourKeyVaultName> helyőrzőt lecserélni a tároló nevére ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-222">Make sure that you replaced the name <YourKeyVaultName> with your vault name ::: zone-end</span></span>

<span data-ttu-id="7bf02-223">::: zone pivot="dotnet" Az alkalmazás futtatásakor meg kell jelennie a titkos kulcs lekért értékének.</span><span class="sxs-lookup"><span data-stu-id="7bf02-223">::: zone pivot="dotnet" Now when you run the application, you should see your secret value retrieved.</span></span>
<span data-ttu-id="7bf02-224">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-224">::: zone-end</span></span>

## <a name="next-steps"></a><span data-ttu-id="7bf02-225">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="7bf02-225">Next steps</span></span>

<span data-ttu-id="7bf02-226">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="7bf02-226">::: zone pivot="nodejs"</span></span>
* [<span data-ttu-id="7bf02-227">Az Azure Key Vault kezdőlapja</span><span class="sxs-lookup"><span data-stu-id="7bf02-227">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="7bf02-228">Az Azure Key Vault dokumentációja</span><span class="sxs-lookup"><span data-stu-id="7bf02-228">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="7bf02-229">Azure SDK For Node</span><span class="sxs-lookup"><span data-stu-id="7bf02-229">Azure SDK For Node</span></span>](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* <span data-ttu-id="7bf02-230">[Azure – REST API-referencia](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-230">[Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>

<span data-ttu-id="7bf02-231">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="7bf02-231">::: zone pivot="dotnet"</span></span>
* [<span data-ttu-id="7bf02-232">Az Azure Key Vault kezdőlapja</span><span class="sxs-lookup"><span data-stu-id="7bf02-232">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="7bf02-233">Az Azure Key Vault dokumentációja</span><span class="sxs-lookup"><span data-stu-id="7bf02-233">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="7bf02-234">Azure SDK for .NET</span><span class="sxs-lookup"><span data-stu-id="7bf02-234">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* <span data-ttu-id="7bf02-235">[Azure – REST API-referencia](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="7bf02-235">[Azure REST API reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>