---
title: Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten mit PowerShell
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
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um nicht lizenzierten Benutzern eine Microsoft 365-Lizenz zuzuordnen.
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905464"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="72640-103">Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="72640-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="72640-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="72640-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="72640-105">Benutzer können keine Microsoft 365-Dienste verwenden, bis ihrem Konto eine Lizenz aus einem Lizenzierungsplan zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="72640-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="72640-106">Sie können PowerShell verwenden, um nicht lizenzierten Konten schnell Lizenzen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="72640-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="72640-107">Benutzerkonten muss zuerst ein Speicherort zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="72640-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="72640-108">Das Angeben eines Speicherorts ist ein erforderlicher Bestandteil des Erstellens eines neuen Benutzerkontos im [Microsoft 365 Admin Center](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="72640-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="72640-109">Für Konten, die mit Ihren lokalen Active Directory-Domänendiensten synchronisiert wurden, ist standardmäßig kein Speicherort angegeben.</span><span class="sxs-lookup"><span data-stu-id="72640-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="72640-110">Sie können einen Speicherort für diese Konten konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="72640-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="72640-111">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="72640-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="72640-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="72640-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="72640-113">Das [Azure-Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active**  >  **Directory-Benutzer** > Benutzerkonto >   >  **Profilkontaktinformationen**  >  **Land oder Region**).</span><span class="sxs-lookup"><span data-stu-id="72640-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="72640-114">[Informationen zum Zuweisen von Lizenzen zu Benutzerkonten](../admin/manage/assign-licenses-to-users.md) mit dem Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="72640-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="72640-115">Eine Liste der zusätzlichen Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="72640-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="72640-116">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="72640-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="72640-117">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="72640-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="72640-118">Als Nächstes listen Sie die Lizenzpläne für Ihren Mandanten mit diesem Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="72640-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="72640-119">Als Nächstes erhalten Sie den Anmeldenamen des Kontos, dem Sie eine Lizenz hinzufügen möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt.</span><span class="sxs-lookup"><span data-stu-id="72640-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="72640-120">Stellen Sie als Nächstes sicher, dass dem Benutzerkonto ein Verwendungsspeicherort zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="72640-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="72640-121">Wenn kein Verwendungsspeicherort zugewiesen ist, können Sie einen mit den folgenden Befehlen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="72640-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="72640-122">Geben Sie schließlich den Namen der Benutzer-Anmeldung und den Lizenzplannamen an, und führen Sie diese Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="72640-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="72640-123">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72640-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="72640-124">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="72640-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="72640-125">Führen Sie den Befehl aus, um die verfügbaren Lizenzierungspläne und die Anzahl der verfügbaren Lizenzen in den einzelnen `Get-MsolAccountSku` Plänen in Ihrer Organisation anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="72640-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="72640-126">Die Anzahl der verfügbaren Lizenzen in jedem Plan ist **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="72640-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="72640-127">Weitere Informationen zu Lizenzierungsplänen, Lizenzen und Diensten finden Sie unter Anzeigen von Lizenzen und Diensten [mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="72640-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="72640-128">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="72640-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="72640-129">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="72640-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="72640-130">Führen Sie diesen Befehl aus, um die nicht lizenzierten Konten in Ihrer Organisation zu finden.</span><span class="sxs-lookup"><span data-stu-id="72640-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="72640-131">Sie können Benutzerkonten nur Lizenzen zuweisen, für die die **UsageLocation-Eigenschaft** auf einen gültigen ISO 3166-1 alpha-2-Ländercode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="72640-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="72640-132">„US" steht zum Beispiel für die Vereinigten Staaten und „FR" für Frankreich.</span><span class="sxs-lookup"><span data-stu-id="72640-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="72640-133">Einige Microsoft 365-Dienste sind in bestimmten Ländern nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="72640-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="72640-134">Weitere Informationen finden Sie unter [Informationen zu Lizenzbeschränkungen](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="72640-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="72640-135">Führen Sie diesen Befehl aus, um Konten zu finden, die keinen **UsageLocation-Wert** haben.</span><span class="sxs-lookup"><span data-stu-id="72640-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="72640-136">Führen Sie diesen Befehl aus, um den **UsageLocation-Wert** für ein Konto zu festlegen.</span><span class="sxs-lookup"><span data-stu-id="72640-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="72640-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72640-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="72640-138">Bei Verwendung des **Get-MsolUser**-Cmdlets ohne den **-All**-Parameter werden nur die ersten 500 Konten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="72640-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="72640-139">Zuweisen von Lizenzen zu Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="72640-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="72640-140">Verwenden Sie den folgenden Befehl in PowerShell, um einem Benutzer eine Lizenz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="72640-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="72640-141">In diesem Beispiel wird dem nicht lizenzierten Benutzer belindan eine Lizenz aus dem **Lizenzplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) **\@ litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="72640-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="72640-142">Führen Sie diesen Befehl aus, um allen nicht lizenzierten Benutzern eine Lizenz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="72640-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="72640-143">Sie können einem Benutzer nicht mehrere Lizenzen aus dem gleichen Lizenzierungsplan zuweisen.</span><span class="sxs-lookup"><span data-stu-id="72640-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="72640-144">Wenn Sie nicht über genügend verfügbare Lizenzen verfügen, werden die Lizenzen den Benutzern in der Reihenfolge zugewiesen, in der sie von dem **Get-MsolUser**-Cmdlet zurückgegeben werden, bis alle Lizenzen vergeben sind.</span><span class="sxs-lookup"><span data-stu-id="72640-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="72640-145">In diesem Beispiel werden Allen nicht lizenzierten Benutzern Lizenzen aus dem **Lizenzplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="72640-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="72640-146">In diesem Beispiel werden dieselben Lizenzen nicht lizenzierten Benutzern in der Vertriebsabteilung in den USA zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="72640-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="72640-147">Verschieben eines Benutzers in ein anderes Abonnement (Lizenzplan) mit dem Azure Active Directory PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="72640-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="72640-148">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="72640-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="72640-149">Als Nächstes erhalten Sie den Anmeldenamen des Benutzerkontos, für das Sie Switchabonnements verwenden möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt.</span><span class="sxs-lookup"><span data-stu-id="72640-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="72640-150">Listen Sie als Nächstes die Abonnements (Lizenzpläne) für Ihren Mandanten mit diesem Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="72640-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="72640-151">Listen Sie als Nächstes die Abonnements auf, über die das Benutzerkonto derzeit mit diesen Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="72640-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="72640-152">Identifizieren Sie das Abonnement, über das der Benutzer derzeit verfügt (das FROM-Abonnement) und das Abonnement, in das der Benutzer sich bewegt (das TO-Abonnement).</span><span class="sxs-lookup"><span data-stu-id="72640-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="72640-153">Geben Sie schließlich die Namen des TO- und FROM-Abonnements (SKU-Teilnummern) an, und führen Sie diese Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="72640-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="72640-154">Sie können die Änderung des Abonnements für das Benutzerkonto mit diesen Befehlen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="72640-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="72640-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72640-155">See also</span></span>

[<span data-ttu-id="72640-156">Verwalten von Benutzerkonten, Lizenzen und Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="72640-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="72640-157">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="72640-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="72640-158">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72640-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)