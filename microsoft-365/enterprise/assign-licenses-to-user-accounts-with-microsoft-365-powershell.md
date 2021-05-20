---
title: Zuweisen Microsoft 365 Lizenzen für Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um nicht lizenzierten Benutzern eine Microsoft 365 Lizenz zuzuweisen.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572621"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="358d8-103">Zuweisen Microsoft 365 Lizenzen für Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="358d8-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="358d8-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="358d8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="358d8-105">Benutzer können keine Microsoft 365 Dienste verwenden, bis ihrem Konto eine Lizenz aus einem Lizenzierungsplan zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="358d8-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="358d8-106">Sie können PowerShell verwenden, um Lizenzen schnell nicht lizenzierten Konten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="358d8-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="358d8-107">Benutzerkonten müssen zuerst einen Speicherort zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="358d8-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="358d8-108">Die Angabe eines Speicherorts ist ein erforderlicher Teil zum Erstellen eines neuen Benutzerkontos im [Microsoft 365 Admin Center](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="358d8-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="358d8-109">Für Konten, die von Ihren lokalen Active Directory-Domänendiensten synchronisiert werden, wurde standardmäßig kein Speicherort angegeben.</span><span class="sxs-lookup"><span data-stu-id="358d8-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="358d8-110">Sie können einen Speicherort für diese Konten konfigurieren von:</span><span class="sxs-lookup"><span data-stu-id="358d8-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="358d8-111">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="358d8-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="358d8-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="358d8-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="358d8-113">Das [Azure-Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active**  >  **Directory-Benutzer** > Benutzerkonto >   >  **Profilkontaktinformationen**  >  **Land oder Region**).</span><span class="sxs-lookup"><span data-stu-id="358d8-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="358d8-114">[Erfahren Sie, wie Sie Benutzerkonten](../admin/manage/assign-licenses-to-users.md) mit dem Microsoft 365 Admin Center Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="358d8-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="358d8-115">Eine Liste zusätzlicher Ressourcen finden Sie unter Verwalten von [Benutzern und Gruppen](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="358d8-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="358d8-116">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="358d8-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="358d8-117">Stellen [Sie](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)zunächst eine Verbindung zu Ihrem Microsoft 365 Mandanten her.</span><span class="sxs-lookup"><span data-stu-id="358d8-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="358d8-118">Listen Sie als Nächstes die Lizenzpläne für Ihren Mandanten mit diesem Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="358d8-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="358d8-119">Als Nächstes erhalten Sie den Anmeldenamen des Kontos, dem Sie eine Lizenz hinzufügen möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="358d8-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="358d8-120">Stellen Sie als Nächstes sicher, dass dem Benutzerkonto ein Verwendungsspeicherort zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="358d8-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="358d8-121">Wenn kein Verwendungsspeicherort zugewiesen ist, können Sie einen mit folgenden Befehlen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="358d8-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="358d8-122">Geben Sie schließlich den Namen der Benutzeranmeldung und den Lizenzplannamen an, und führen Sie diese Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="358d8-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="358d8-123">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="358d8-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="358d8-124">Bitte beachten Sie, dass wir damit beginnen, dieses Modul zu vernachdürfen, wenn die Funktionalität dieses Moduls in der neueren [Azure Active Directory PowerShell für Graph](/powershell/azuread/v2/azureactivedirectory) Modul verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="358d8-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="358d8-125">Wir empfehlen Kunden, die neue PowerShell-Skripts erstellen, das neuere Modul anstelle dieses Moduls zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="358d8-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="358d8-126">Stellen [Sie](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)zunächst eine Verbindung zu Ihrem Microsoft 365 Mandanten her.</span><span class="sxs-lookup"><span data-stu-id="358d8-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="358d8-127">Führen Sie den `Get-MsolAccountSku` Befehl aus, um die verfügbaren Lizenzpläne und die Anzahl der verfügbaren Lizenzen in jedem Plan in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="358d8-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="358d8-128">Die Anzahl der verfügbaren Lizenzen in jedem Plan ist **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="358d8-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="358d8-129">Weitere Informationen zu Lizenzierungsplänen, Lizenzen und Diensten finden Sie unter Anzeigen von [Lizenzen und Diensten mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="358d8-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="358d8-130">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="358d8-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="358d8-131">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="358d8-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="358d8-132">Führen Sie diesen Befehl aus, um die nicht lizenzierten Konten in Ihrer Organisation zu finden.</span><span class="sxs-lookup"><span data-stu-id="358d8-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="358d8-133">Sie können Nur Benutzerkonten Lizenzen zuweisen, deren **UsageLocation-Eigenschaft** auf einen gültigen ISO 3166-1 alpha-2-Ländercode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="358d8-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="358d8-134">„US" steht zum Beispiel für die Vereinigten Staaten und „FR" für Frankreich.</span><span class="sxs-lookup"><span data-stu-id="358d8-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="358d8-135">Einige Microsoft 365 Dienste sind in bestimmten Ländern nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="358d8-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="358d8-136">Weitere Informationen finden Sie unter [Informationen zu Lizenzbeschränkungen](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="358d8-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="358d8-137">Führen Sie diesen Befehl aus, um Konten zu finden, die keinen **UsageLocation-Wert** haben.</span><span class="sxs-lookup"><span data-stu-id="358d8-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="358d8-138">Führen Sie diesen Befehl aus, um den **UsageLocation-Wert** für ein Konto festzulegen.</span><span class="sxs-lookup"><span data-stu-id="358d8-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="358d8-139">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="358d8-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="358d8-140">Bei Verwendung des **Get-MsolUser**-Cmdlets ohne den **-All**-Parameter werden nur die ersten 500 Konten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="358d8-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="358d8-141">Zuweisen von Lizenzen zu Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="358d8-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="358d8-142">Um einem Benutzer eine Lizenz zuzuweisen, verwenden Sie den folgenden Befehl in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="358d8-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="358d8-143">In diesem Beispiel wird dem nicht lizenzierten Benutzer eine Lizenz aus dem **Lizenzierungsplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) **\@ zugewiesen, litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="358d8-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="358d8-144">Führen Sie diesen Befehl aus, um allen nicht lizenzierten Benutzern eine Lizenz zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="358d8-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="358d8-145">Sie können einem Benutzer nicht mehrere Lizenzen aus dem gleichen Lizenzierungsplan zuweisen.</span><span class="sxs-lookup"><span data-stu-id="358d8-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="358d8-146">Wenn Sie nicht über genügend verfügbare Lizenzen verfügen, werden die Lizenzen den Benutzern in der Reihenfolge zugewiesen, in der sie von dem **Get-MsolUser**-Cmdlet zurückgegeben werden, bis alle Lizenzen vergeben sind.</span><span class="sxs-lookup"><span data-stu-id="358d8-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="358d8-147">In diesem Beispiel werden allen nicht lizenzierten Benutzern Lizenzen aus dem **Lizenzierungsplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="358d8-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="358d8-148">In diesem Beispiel werden dieselben Lizenzen nicht lizenzierten Benutzern in der Vertriebsabteilung in den USA zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="358d8-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="358d8-149">Verschieben eines Benutzers in ein anderes Abonnement (Lizenzplan) mit der Azure Active Directory PowerShell für Graph Modul</span><span class="sxs-lookup"><span data-stu-id="358d8-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="358d8-150">Stellen [Sie](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)zunächst eine Verbindung zu Ihrem Microsoft 365 Mandanten her.</span><span class="sxs-lookup"><span data-stu-id="358d8-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="358d8-151">Als Nächstes erhalten Sie den Anmeldenamen des Benutzerkontos, für das Sie Abonnements wechseln möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="358d8-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="358d8-152">Listen Sie als Nächstes die Abonnements (Lizenzpläne) für Ihren Mandanten mit diesem Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="358d8-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="358d8-153">Führen Sie als Nächstes die Abonnements auf, die das Benutzerkonto derzeit mit diesen Befehlen hat.</span><span class="sxs-lookup"><span data-stu-id="358d8-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="358d8-154">Identifizieren Sie das Abonnement, über das der Benutzer derzeit verfügt (das FROM-Abonnement) und das Abonnement, in das der Benutzer wechselt (das TO-Abonnement).</span><span class="sxs-lookup"><span data-stu-id="358d8-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="358d8-155">Geben Sie schließlich die Abonnementnamen TO und FROM (SKU-Teilenummern) an, und führen Sie diese Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="358d8-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="358d8-156">Mit diesen Befehlen können Sie die Änderung im Abonnement für das Benutzerkonto überprüfen.</span><span class="sxs-lookup"><span data-stu-id="358d8-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="358d8-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="358d8-157">See also</span></span>

[<span data-ttu-id="358d8-158">Verwalten von Benutzerkonten, Lizenzen und Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="358d8-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="358d8-159">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="358d8-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="358d8-160">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="358d8-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
