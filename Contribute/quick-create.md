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
ms.openlocfilehash: 497631fe46ac4e2c9c495a609547753a84d662bf
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805744"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="15f5a-103">Rövid útmutató: Titkos kulcs beállítása és lekérése az Azure Key Vaultból</span><span class="sxs-lookup"><span data-stu-id="15f5a-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="15f5a-104">Ez a rövid útmutató azt mutatja be, hogyan lehet tárolni a titkos kulcsokat a Key Vaultban, és hogyan lehet őket lekérni egy webalkalmazással.</span><span class="sxs-lookup"><span data-stu-id="15f5a-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="15f5a-105">Ahhoz, hogy láthassa a titkos kulcs értékét, az Azure-ban kell dolgoznia.</span><span class="sxs-lookup"><span data-stu-id="15f5a-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="15f5a-106">A rövid útmutató Node.js kódot és felügyeltszolgáltatás-identitásokat (MSI-ket) alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="15f5a-106">The quickstart uses Node.js and Managed service identities (MSIs).</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="15f5a-107">Key Vault létrehozása.</span><span class="sxs-lookup"><span data-stu-id="15f5a-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="15f5a-108">Titkos kulcs tárolása a Key Vaultban.</span><span class="sxs-lookup"><span data-stu-id="15f5a-108">Store a secret in the Key Vault.</span></span>
> * <span data-ttu-id="15f5a-109">Titkos kulcs lekérése a Key Vaultból.</span><span class="sxs-lookup"><span data-stu-id="15f5a-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="15f5a-110">Azure-webalkalmazás létrehozása.</span><span class="sxs-lookup"><span data-stu-id="15f5a-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="15f5a-111">[Felügyeltszolgáltatás-identitások engedélyezése](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="15f5a-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="15f5a-112">A szükséges engedélyek megadása a webalkalmazás számára az adatoknak a Key Vaultból való olvasásához.</span><span class="sxs-lookup"><span data-stu-id="15f5a-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="15f5a-113">Mielőtt folytatná, győződjön meg arról, hogy tisztában van az [alapvető fogalmakkal](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span><span class="sxs-lookup"><span data-stu-id="15f5a-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

> [!NOTE]
> <span data-ttu-id="15f5a-114">Ahhoz, hogy megérthesse, miért az alábbi oktatóanyagban ismertetett folyamat az ajánlott eljárás, néhány fogalommal tisztában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="15f5a-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="15f5a-115">A Key Vault egy központi adattár a titkos kulcsok programozott módon való tárolásához.</span><span class="sxs-lookup"><span data-stu-id="15f5a-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="15f5a-116">A használatához azonban az alkalmazásoknak/felhasználóknak először hitelesíteniük kell magukat a Key Vaultban, azaz be kell mutatniuk egy titkos kulcsot.</span><span class="sxs-lookup"><span data-stu-id="15f5a-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="15f5a-117">Az ajánlott biztonsági eljárások betartása érdekében ezt az első titkos kulcsot rendszeres időközönként le kell váltani.</span><span class="sxs-lookup"><span data-stu-id="15f5a-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="15f5a-118">Az Azure-ban futó [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview)-alkalmazásokhoz jár egy olyan identitás, amelyet az Azure automatikusan felügyel.</span><span class="sxs-lookup"><span data-stu-id="15f5a-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview), applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="15f5a-119">Ez segít megoldani a **titkos kulcsok bemutatásának problémáját**, mivel a felhasználók/alkalmazások követhetik az ajánlott eljárásokat, és nem kell aggódniuk az első titkos kulcs leváltása miatt</span><span class="sxs-lookup"><span data-stu-id="15f5a-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15f5a-120">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="15f5a-120">Prerequisites</span></span>

::: zone pivot="nodejs"
* [<span data-ttu-id="15f5a-121">Node JS</span><span class="sxs-lookup"><span data-stu-id="15f5a-121">Node JS</span></span>](https://nodejs.org/en/)
::: zone-end
::: zone pivot="dotnet"
* <span data-ttu-id="15f5a-122">A [Visual Studio 2017 szoftver 15.7.3-as vagy újabb verziója](https://www.microsoft.com/net/download/windows) a következő számítási feladatokkal:</span><span class="sxs-lookup"><span data-stu-id="15f5a-122">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="15f5a-123">ASP.NET és webfejlesztés</span><span class="sxs-lookup"><span data-stu-id="15f5a-123">ASP.NET and web development</span></span>
  * <span data-ttu-id="15f5a-124">.NET Core platformfüggetlen fejlesztés</span><span class="sxs-lookup"><span data-stu-id="15f5a-124">.NET Core cross-platform development</span></span>
* [<span data-ttu-id="15f5a-125">.NET Core 2.1 SDK vagy újabb</span><span class="sxs-lookup"><span data-stu-id="15f5a-125">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/windows)
::: zone-end
* <span data-ttu-id="15f5a-126">Git ([letöltés](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="15f5a-126">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="15f5a-127">Azure-előfizetés.</span><span class="sxs-lookup"><span data-stu-id="15f5a-127">An Azure subscription.</span></span> <span data-ttu-id="15f5a-128">Ha nem rendelkezik Azure-előfizetéssel, mindössze néhány perc alatt létrehozhat egy [ingyenes fiókot](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) a virtuális gép létrehozásának megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="15f5a-128">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="15f5a-129">Az [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) 2.0.4-es vagy újabb verziója.</span><span class="sxs-lookup"><span data-stu-id="15f5a-129">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="15f5a-130">Ez elérhető Windows, Mac és Linux rendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="15f5a-130">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="15f5a-131">Bejelentkezés az Azure-ba</span><span class="sxs-lookup"><span data-stu-id="15f5a-131">Login to Azure</span></span>

<span data-ttu-id="15f5a-132">Ha az Azure-ba a parancssori felület használatával szeretne bejelentkezni, írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="15f5a-132">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="15f5a-133">Erőforráscsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="15f5a-133">Create resource group</span></span>

<span data-ttu-id="15f5a-134">Hozzon létre egy erőforráscsoportot az [az group create](/cli/azure/group#az-group-create) paranccsal.</span><span class="sxs-lookup"><span data-stu-id="15f5a-134">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="15f5a-135">Az Azure-erőforráscsoportok logikai tárolók, amelyekben az Azure-erőforrások telepítése és kezelése történik.</span><span class="sxs-lookup"><span data-stu-id="15f5a-135">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="15f5a-136">Válasszon egy erőforráscsoport-nevet, és töltse ki a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="15f5a-136">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="15f5a-137">A következő példában létrehozunk egy *<YourResourceGroupName>* nevű erőforráscsoportot az *eastus* helyen.</span><span class="sxs-lookup"><span data-stu-id="15f5a-137">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="15f5a-138">Az oktatóanyag az imént létrehozott erőforráscsoport használja.</span><span class="sxs-lookup"><span data-stu-id="15f5a-138">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="15f5a-139">Azure Key Vault létrehozása</span><span class="sxs-lookup"><span data-stu-id="15f5a-139">Create an Azure Key Vault</span></span>

<span data-ttu-id="15f5a-140">A következő lépésben létre fog hozni egy Key Vaultot az előző lépésben létrehozott erőforráscsoport használatával.</span><span class="sxs-lookup"><span data-stu-id="15f5a-140">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="15f5a-141">Jóllehet ebben a cikkben a Key Vault neve „ContosoKeyVault”, egyedi nevet kell használnia.</span><span class="sxs-lookup"><span data-stu-id="15f5a-141">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="15f5a-142">Adja meg az alábbi információkat:</span><span class="sxs-lookup"><span data-stu-id="15f5a-142">Provide the following information:</span></span>

* <span data-ttu-id="15f5a-143">Tároló neve: **Itt válasszon kulcstárolónevet**.</span><span class="sxs-lookup"><span data-stu-id="15f5a-143">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="15f5a-144">Erőforráscsoport neve: **Itt válasszon erőforráscsoport-nevet**.</span><span class="sxs-lookup"><span data-stu-id="15f5a-144">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="15f5a-145">Hely: **USA keleti régiója**.</span><span class="sxs-lookup"><span data-stu-id="15f5a-145">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="15f5a-146">Az Azure-fiókja jelenleg az egyetlen, amelyik jogosult arra, hogy műveleteket végezzen ezen az új tárolón.</span><span class="sxs-lookup"><span data-stu-id="15f5a-146">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="15f5a-147">Titkos kulcs hozzáadása a Key Vaulthoz</span><span class="sxs-lookup"><span data-stu-id="15f5a-147">Add a secret to key vault</span></span>

<span data-ttu-id="15f5a-148">Egy titkos kulcs hozzáadásával mutatjuk be ennek működését.</span><span class="sxs-lookup"><span data-stu-id="15f5a-148">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="15f5a-149">Tárolhat egy SQL-kapcsolati sztringet, vagy bármely olyan adatot, amelyet biztonságosan kell tárolni, de elérhetővé kell tenni az alkalmazás számára.</span><span class="sxs-lookup"><span data-stu-id="15f5a-149">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="15f5a-150">Ebben az oktatóanyagban a jelszó neve **AppSecret** lesz, és a **MySecret** értékét fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="15f5a-150">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="15f5a-151">Írja be az alábbi parancsokat, ha a **MySecret** értékét tároló titkos kulcsot szeretne létrehozni a Key Vaultban **AppSecret** névvel:</span><span class="sxs-lookup"><span data-stu-id="15f5a-151">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="15f5a-152">A titkos kódban tárolt érték megtekintése egyszerű szövegként:</span><span class="sxs-lookup"><span data-stu-id="15f5a-152">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="15f5a-153">Ez a parancs megjeleníti a titkos információkat, beleértve az URI-t is.</span><span class="sxs-lookup"><span data-stu-id="15f5a-153">This command shows the secret information including the URI.</span></span> <span data-ttu-id="15f5a-154">A fenti lépések elvégzése után rendelkeznie kell egy Azure Key Vaultban tárolt titkos kulcshoz tartozó URI-val.</span><span class="sxs-lookup"><span data-stu-id="15f5a-154">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="15f5a-155">Jegyezze fel ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="15f5a-155">Write this information down.</span></span> <span data-ttu-id="15f5a-156">Egy későbbi lépésben szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="15f5a-156">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="15f5a-157">Az adattár klónozása</span><span class="sxs-lookup"><span data-stu-id="15f5a-157">Clone the Repo</span></span>

<span data-ttu-id="15f5a-158">A forrás szerkesztéséhez szükséges helyi másolat létrehozásához klónozza az adattárat a következő parancs futtatásával:</span><span class="sxs-lookup"><span data-stu-id="15f5a-158">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a><span data-ttu-id="15f5a-159">Függőségek telepítése</span><span class="sxs-lookup"><span data-stu-id="15f5a-159">Install dependencies</span></span>

<span data-ttu-id="15f5a-160">Itt a függőségeket telepítjük.</span><span class="sxs-lookup"><span data-stu-id="15f5a-160">Here we install the dependencies.</span></span> <span data-ttu-id="15f5a-161">Futtassa az alábbi parancsot:</span><span class="sxs-lookup"><span data-stu-id="15f5a-161">Run the following commands:</span></span>

    cd key-vault-node-quickstart
    npm install

<span data-ttu-id="15f5a-162">Ez a projekt 2 csomópontmodult használt:</span><span class="sxs-lookup"><span data-stu-id="15f5a-162">This project used 2 node modules:</span></span>

* [<span data-ttu-id="15f5a-163">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="15f5a-163">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="15f5a-164">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="15f5a-164">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="15f5a-165">A webalkalmazás közzététele az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="15f5a-165">Publish the web application to Azure</span></span>

<span data-ttu-id="15f5a-166">Az alkalmazás Azure-ban való közzétételét az alábbi néhány lépéssel lehet elvégezni.</span><span class="sxs-lookup"><span data-stu-id="15f5a-166">Below are the few steps we need to do to publish the application to Azure.</span></span>

* <span data-ttu-id="15f5a-167">Az első lépés egy [Azure App Service](https://azure.microsoft.com/services/app-service/)-csomag létrehozása.</span><span class="sxs-lookup"><span data-stu-id="15f5a-167">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="15f5a-168">Ebben a csomagban több webalkalmazást is tárolhat.</span><span class="sxs-lookup"><span data-stu-id="15f5a-168">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="15f5a-169">Ezután létrehozunk egy webalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="15f5a-169">Next we create a web app.</span></span> <span data-ttu-id="15f5a-170">A következő példában cserélje ki az <app_name> helyőrzőt egy globálisan egyedi névre (érvényes karakterek: a–z, 0–9 és -).</span><span class="sxs-lookup"><span data-stu-id="15f5a-170">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="15f5a-171">A futtatókörnyezet beállítása: NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="15f5a-171">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="15f5a-172">Az összes támogatott futtatókörnyezet megtekintéséhez futtassa az `az webapp list-runtimes` parancsot</span><span class="sxs-lookup"><span data-stu-id="15f5a-172">To see all supported runtimes, run `az webapp list-runtimes`</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="15f5a-173">A webalkalmazás létrehozása után az Azure CLI az alábbi példához hasonló eredményeket jelenít meg:</span><span class="sxs-lookup"><span data-stu-id="15f5a-173">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="15f5a-174">Tallózással keresse meg az újonnan létrehozott webalkalmazást, és láthatja, hogy az működik.</span><span class="sxs-lookup"><span data-stu-id="15f5a-174">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="15f5a-175">Az <app_name> helyőrző helyett adjon meg egy egyedi nevet.</span><span class="sxs-lookup"><span data-stu-id="15f5a-175">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="15f5a-176">A fenti parancs egy Git-kompatibilis alkalmazást is létrehoz, amely lehetővé teszi az Azure-ba történő üzembe helyezést a helyi Git-adattárból.</span><span class="sxs-lookup"><span data-stu-id="15f5a-176">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="15f5a-177">A helyi Git-adattár a következő URL-címmel van konfigurálva: „https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git”</span><span class="sxs-lookup"><span data-stu-id="15f5a-177">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="15f5a-178">Üzembe helyező felhasználó létrehozása Az előző parancs lefutását követően hozzáadhat egy távoli Azure-mappát a helyi Git-adattárhoz.</span><span class="sxs-lookup"><span data-stu-id="15f5a-178">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="15f5a-179">Cserélje le a <url> részt a távoli Git-elem URL-címére, amelyet a Git az alkalmazáson való engedélyezése során kapott meg.</span><span class="sxs-lookup"><span data-stu-id="15f5a-179">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
    
::: zone-end

::: zone pivot="dotnet"
## <a name="open-and-edit-the-solution"></a><span data-ttu-id="15f5a-180">A megoldás megnyitása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="15f5a-180">Open and edit the solution</span></span>

<span data-ttu-id="15f5a-181">Módosítsa a program.cs fájlt, hogy a minta az adott kulcstartó nevével fusson:</span><span class="sxs-lookup"><span data-stu-id="15f5a-181">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="15f5a-182">Lépjen a key-vault-dotnet-core-quickstart mappára.</span><span class="sxs-lookup"><span data-stu-id="15f5a-182">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="15f5a-183">Nyissa meg a key-vault-dotnet-core-quickstart.sln fájlt a Visual Studio 2017-ben.</span><span class="sxs-lookup"><span data-stu-id="15f5a-183">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="15f5a-184">Nyissa meg a program.cs fájlt, és a *YourKeyVaultName* helyőrzőt cserélje le a korábban létrehozott kulcstartó nevére.</span><span class="sxs-lookup"><span data-stu-id="15f5a-184">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="15f5a-185">Ez a megoldás [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) és [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet-kódtárakat használ.</span><span class="sxs-lookup"><span data-stu-id="15f5a-185">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="15f5a-186">Az alkalmazás futtatása</span><span class="sxs-lookup"><span data-stu-id="15f5a-186">Run the app</span></span>

<span data-ttu-id="15f5a-187">A Visual Studio 2017 főmenüjében válassza a **Debug** > **Start** without Debugging (Hibakeresés > Indítás hibakeresés nélkül) elemet.</span><span class="sxs-lookup"><span data-stu-id="15f5a-187">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="15f5a-188">Amikor megjelenik a böngésző, lépjen az **About** (Névjegy) oldalra.</span><span class="sxs-lookup"><span data-stu-id="15f5a-188">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="15f5a-189">Megjelenik az **AppSecret** értéke.</span><span class="sxs-lookup"><span data-stu-id="15f5a-189">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="15f5a-190">A webalkalmazás közzététele az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="15f5a-190">Publish the web application to Azure</span></span>

<span data-ttu-id="15f5a-191">Tegye közzé ezt az alkalmazást az Azure-ban, hogy élő webalkalmazásként megtekinthető legyen, illetve hogy látható legyen, hogy a titkos érték lekérhető-e:</span><span class="sxs-lookup"><span data-stu-id="15f5a-191">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="15f5a-192">A Visual Studióban válassza a **key-vault-dotnet-core-quickstart** projektet.</span><span class="sxs-lookup"><span data-stu-id="15f5a-192">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="15f5a-193">Válassza a **Publish** > **Start** (Közzététel > Indítás) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15f5a-193">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="15f5a-194">Hozzon létre egy új **App Service-t**, majd kattintson a **Publish** (Közzététel) parancsra.</span><span class="sxs-lookup"><span data-stu-id="15f5a-194">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="15f5a-195">Módosítsa az alkalmazás nevét a következőre: **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="15f5a-195">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="15f5a-196">Kattintson a **Létrehozás** gombra.</span><span class="sxs-lookup"><span data-stu-id="15f5a-196">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
::: zone-end

## <a name="enable-managed-service-identities"></a><span data-ttu-id="15f5a-197">Felügyeltszolgáltatás-identitások engedélyezése</span><span class="sxs-lookup"><span data-stu-id="15f5a-197">Enable managed service identities</span></span>

<span data-ttu-id="15f5a-198">Az Azure Key Vault módot kínál a hitelesítő adatok, valamint egyéb kulcsok és titkos kódok biztonságos tárolására, azonban a kódnak hitelesítenie kell magát az Azure Key Vaultban az adatok lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="15f5a-198">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="15f5a-199">A felügyeltszolgáltatás-identitás segít leegyszerűsíteni ezt, mivel az Azure-szolgáltatások számára egy automatikusan felügyelt identitást biztosít az Azure Active Directoryban (Azure AD-ben).</span><span class="sxs-lookup"><span data-stu-id="15f5a-199">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="15f5a-200">Ezzel az identitással bármely, az Azure AD-hitelesítést támogató szolgáltatásban, többek között a Key Vaultban is elvégezheti a hitelesítést anélkül, hogy a hitelesítő adatokat a kódban kellene tárolnia.</span><span class="sxs-lookup"><span data-stu-id="15f5a-200">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="15f5a-201">Térjen vissza az Azure CLI-hez.</span><span class="sxs-lookup"><span data-stu-id="15f5a-201">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="15f5a-202">Futtassa az identitás hozzárendelésére szolgáló parancsot az alkalmazás identitásának létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="15f5a-202">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="15f5a-203">Az ebben az eljárásban használt parancs egyenértékű azzal, mintha megnyitná a portált, és a webalkalmazás tulajdonságai között átállítaná a **Felügyeltszolgáltatás-identitás** beállítást **Be** értékűre.</span><span class="sxs-lookup"><span data-stu-id="15f5a-203">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="15f5a-204">Engedélyek kiosztása az alkalmazásnak a Key Vault titkos kulcsainak olvasásához</span><span class="sxs-lookup"><span data-stu-id="15f5a-204">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="15f5a-205">Jegyezze fel a kimenetből származó adatokat, amikor az Azure-ban közzéteszi az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="15f5a-205">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="15f5a-206">Az adatok a következő formátumban jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="15f5a-206">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="15f5a-207">Ezután futtassa ezt a parancsot a kulcstartó neve és a **PrincipalId** értéke használatával:</span><span class="sxs-lookup"><span data-stu-id="15f5a-207">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="15f5a-208">A Node-alkalmazás üzembe helyezése az Azure-ban és a titkos kulcs értékének lekérése</span><span class="sxs-lookup"><span data-stu-id="15f5a-208">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="15f5a-209">Most már minden készen áll.</span><span class="sxs-lookup"><span data-stu-id="15f5a-209">Now that everything is set.</span></span> <span data-ttu-id="15f5a-210">Futtassa az alábbi parancsot az alkalmazás üzembe helyezéséhez az Azure-ban</span><span class="sxs-lookup"><span data-stu-id="15f5a-210">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="15f5a-211">Ezután a https://<app_name>.azurewebsites.net helyre lépve már láthatja a titkos kód értékét.</span><span class="sxs-lookup"><span data-stu-id="15f5a-211">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="15f5a-212">Ne feledje a(z) <YourKeyVaultName> helyőrzőt lecserélni a tároló nevére</span><span class="sxs-lookup"><span data-stu-id="15f5a-212">Make sure that you replaced the name <YourKeyVaultName> with your vault name</span></span>

::: zone-end

::: zone pivot="dotnet"
<span data-ttu-id="15f5a-213">Az alkalmazás futtatásakor meg kell jelennie a titkos kulcs lekért értékének.</span><span class="sxs-lookup"><span data-stu-id="15f5a-213">Now when you run the application, you should see your secret value retrieved.</span></span>
::: zone-end

## <a name="next-steps"></a><span data-ttu-id="15f5a-214">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="15f5a-214">Next steps</span></span>

::: zone pivot="nodejs"
* [<span data-ttu-id="15f5a-215">Az Azure Key Vault kezdőlapja</span><span class="sxs-lookup"><span data-stu-id="15f5a-215">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="15f5a-216">Az Azure Key Vault dokumentációja</span><span class="sxs-lookup"><span data-stu-id="15f5a-216">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="15f5a-217">Azure SDK For Node</span><span class="sxs-lookup"><span data-stu-id="15f5a-217">Azure SDK For Node</span></span>](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* [<span data-ttu-id="15f5a-218">Azure – REST API-referencia</span><span class="sxs-lookup"><span data-stu-id="15f5a-218">Azure REST API Reference</span></span>](https://docs.microsoft.com/rest/api/keyvault/)
::: zone-end

::: zone pivot="dotnet"
* [<span data-ttu-id="15f5a-219">Az Azure Key Vault kezdőlapja</span><span class="sxs-lookup"><span data-stu-id="15f5a-219">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="15f5a-220">Az Azure Key Vault dokumentációja</span><span class="sxs-lookup"><span data-stu-id="15f5a-220">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="15f5a-221">Azure SDK for .NET</span><span class="sxs-lookup"><span data-stu-id="15f5a-221">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* [<span data-ttu-id="15f5a-222">Azure – REST API-referencia</span><span class="sxs-lookup"><span data-stu-id="15f5a-222">Azure REST API reference</span></span>](https://docs.microsoft.com/rest/api/keyvault/)
::: zone-end
