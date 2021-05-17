---
title: Zuweisen von Rollen Microsoft 365 Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: In diesem Artikel erfahren Sie, wie schnell und einfach PowerShell für Microsoft 365 zum Zuweisen von Administratorrollen zu Benutzerkonten verwendet wird.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905380"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="42071-103">Zuweisen von Administratorrollen Microsoft 365 Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="42071-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="42071-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="42071-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="42071-105">Sie können Benutzerkonten problemlos Rollen zuweisen, indem Sie PowerShell für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42071-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="42071-106">Informationen zum [Zuweisen von Administratorrollen](../admin/add-users/assign-admin-roles.md) zu Benutzerkonten mit dem Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="42071-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="42071-107">Eine Liste der zusätzlichen Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="42071-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="42071-108">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="42071-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="42071-109">Verwenden Sie zunächst ein globales Administratorkonto, um eine Verbindung [mit Ihrem Microsoft 365 herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="42071-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="42071-110">Identifizieren Sie als Nächstes den Anmeldenamen des Benutzerkontos, das Sie einer Rolle hinzufügen möchten (Beispiel: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="42071-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="42071-111">Dies wird auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt.</span><span class="sxs-lookup"><span data-stu-id="42071-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="42071-112">Ermitteln Sie nun den Namen der Rolle.</span><span class="sxs-lookup"><span data-stu-id="42071-112">Next, determine the name of the role.</span></span> <span data-ttu-id="42071-113">Weitere [Informationen finden Sie unter Administratorrolleberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="42071-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="42071-114">Achten Sie auf die Hinweise in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="42071-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="42071-115">Einige Rollennamen unterscheiden sich für Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42071-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="42071-116">Beispielsweise ist die SharePoint *Administratorrolle* im Microsoft 365 Admin Center SharePoint *Dienstadministrator* in Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42071-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="42071-117">Geben Sie als Nächstes die Anmelde- und Rollennamen ein, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="42071-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="42071-118">Im Folgenden finden Sie ein Beispiel für einen abgeschlossenen Befehlssatz, der die Rolle SharePoint Dienstadministrator dem *\@ belindan-Contoso.com* zurkennt:</span><span class="sxs-lookup"><span data-stu-id="42071-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="42071-119">Verwenden Sie diese Befehle, um die Liste der Benutzernamen für eine bestimmte Administratorrolle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="42071-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="42071-120">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42071-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="42071-121">Verwenden Sie zunächst ein globales Administratorkonto, um eine Verbindung [mit Ihrem Microsoft 365 herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="42071-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="42071-122">Bei einer einzelnen Rollenänderung</span><span class="sxs-lookup"><span data-stu-id="42071-122">For a single role change</span></span>

<span data-ttu-id="42071-123">Die am häufigsten verwendeten Methoden zum Angeben des Benutzerkontos sind der Anzeigename oder der E-Mail-Name, der auch als Anmelde- oder Benutzerprinzipalname (User Principal Name, UPN) bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="42071-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="42071-124">Anzeigenamen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="42071-124">Display names of user accounts</span></span>

<span data-ttu-id="42071-125">Wenn Sie es gewohnt sind, mit den Anzeigenamen von Benutzerkonten zu arbeiten, ermitteln Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="42071-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="42071-126">Das Benutzerkonto, das Sie konfigurieren möchten</span><span class="sxs-lookup"><span data-stu-id="42071-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="42071-127">Beim Angeben des Benutzerkontos müssen Sie seinen Anzeigenamen bestimmen.</span><span class="sxs-lookup"><span data-stu-id="42071-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="42071-128">Verwenden Sie diesen Befehl, um eine vollständige Liste der Konten zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="42071-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="42071-129">Mit diesem Befehl wird der Anzeigename der Benutzerkonten nach Anzeigename sortiert angezeigt, jeweils einer auf einem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="42071-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="42071-130">Sie können die Liste mit dem **Where** -Cmdlets weiter eingrenzen.</span><span class="sxs-lookup"><span data-stu-id="42071-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="42071-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="42071-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="42071-132">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42071-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="42071-133">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="42071-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="42071-134">Mit diesem Befehl werden nur die Benutzerkonten angezeigt, deren Anzeigename mit „John“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="42071-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="42071-135">Die Rolle, die Sie zuweisen möchten</span><span class="sxs-lookup"><span data-stu-id="42071-135">The role you want to assign</span></span>
    
    <span data-ttu-id="42071-136">Verwenden Sie den folgenden Befehl, um die Liste der verfügbaren Administratorrollen anzeigen zu können, die Sie Benutzerkonten zuweisen können:</span><span class="sxs-lookup"><span data-stu-id="42071-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="42071-137">Nachdem Sie den Anzeigenamen des Kontos und den Namen der Rolle bestimmt haben, verwenden Sie die folgenden Befehle, um die Rolle dem Konto zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="42071-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="42071-138">Fügen Sie die Befehle in Editor.</span><span class="sxs-lookup"><span data-stu-id="42071-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="42071-139">Ersetzen Sie *für $dispName* *und $roleName* den Beschreibungstext durch ihre Werte.</span><span class="sxs-lookup"><span data-stu-id="42071-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="42071-140">Entfernen Sie die \< and > Zeichen, behalten Sie jedoch die Anführungszeichen bei.</span><span class="sxs-lookup"><span data-stu-id="42071-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="42071-141">Fügen Sie die geänderten Zeilen in das Microsoft Azure Active Directory Module ein, Windows PowerShell sie ausführen können.</span><span class="sxs-lookup"><span data-stu-id="42071-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="42071-142">Alternativ können Sie die Windows PowerShell ISE (Integrated Script Environment) verwenden.</span><span class="sxs-lookup"><span data-stu-id="42071-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="42071-143">Hier ist ein Beispiel für einen abgeschlossenen Befehlssatz:</span><span class="sxs-lookup"><span data-stu-id="42071-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="42071-144">Anmeldenamen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="42071-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="42071-145">Wenn Sie es gewohnt sind, mit den Anmeldenamen oder UPNs von Benutzerkonten zu arbeiten, ermitteln Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="42071-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="42071-146">UPN des Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="42071-146">The user account's UPN</span></span>
    
    <span data-ttu-id="42071-147">Wenn Sie den UPN nicht kennen, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="42071-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="42071-148">Dieser Befehl listet den UPN Ihrer Benutzerkonten, sortiert nach UPN, einen Bildschirm nach dem anderen auf.</span><span class="sxs-lookup"><span data-stu-id="42071-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="42071-149">Sie können das **Cmdlet Where** verwenden, um die Liste zu filtern.</span><span class="sxs-lookup"><span data-stu-id="42071-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="42071-150">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="42071-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="42071-151">Mit diesem Befehl werden nur die Benutzerkonten angezeigt, deren Anzeigename mit „John“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="42071-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="42071-152">Die Rolle, die Sie zuweisen möchten</span><span class="sxs-lookup"><span data-stu-id="42071-152">The role you want to assign</span></span>
    
    <span data-ttu-id="42071-153">Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="42071-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="42071-154">Nachdem Sie über den UPN des Kontos und den Namen der Rolle verfügen, verwenden Sie die folgenden Befehle, um die Rolle dem Konto zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="42071-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="42071-155">Kopieren Sie die Befehle, und fügen Sie sie in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="42071-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="42071-156">Für die **$upnName** und **$roleName** Variablen.</span><span class="sxs-lookup"><span data-stu-id="42071-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="42071-157">Ersetzen Sie den Beschreibungstext durch ihre Werte.</span><span class="sxs-lookup"><span data-stu-id="42071-157">Replace the description text with their values.</span></span> <span data-ttu-id="42071-158">Entfernen Sie die \< and > Zeichen, behalten Sie jedoch die Anführungszeichen bei.</span><span class="sxs-lookup"><span data-stu-id="42071-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="42071-159">Fügen Sie die geänderten Zeilen in Microsoft Azure Active Directory Modul ein, Windows PowerShell, um sie ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="42071-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="42071-160">Alternativ können Sie die ise-Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="42071-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="42071-161">Hier ist ein Beispiel für einen abgeschlossenen Befehlssatz:</span><span class="sxs-lookup"><span data-stu-id="42071-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="42071-162">Mehrere Rollenänderungen</span><span class="sxs-lookup"><span data-stu-id="42071-162">Multiple role changes</span></span>

<span data-ttu-id="42071-163">Ermitteln Sie für mehrere Rollenänderungen die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="42071-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="42071-164">Welche Benutzerkonten Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="42071-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="42071-165">Sie können die Methoden im vorherigen Abschnitt verwenden, um den Satz von Anzeigenamen oder UPNs zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="42071-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="42071-166">Rollen, die Sie jedem Benutzerkonto zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="42071-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="42071-167">Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="42071-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="42071-168">Erstellen Sie als Nächstes eine CSV-Textdatei (Comma-separated Value), die den Anzeigenamen oder upN- und Rollennamenfelder enthält.</span><span class="sxs-lookup"><span data-stu-id="42071-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="42071-169">Sie können dies ganz einfach in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="42071-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="42071-170">Hier ist ein Beispiel für Anzeigenamen:</span><span class="sxs-lookup"><span data-stu-id="42071-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="42071-171">Geben Sie anschließend den Speicherort der CSV-Datei an, und führen Sie die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="42071-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="42071-172">Hier ist ein Beispiel für UPNs:</span><span class="sxs-lookup"><span data-stu-id="42071-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="42071-173">Geben Sie anschließend den Speicherort der CSV-Datei an, und führen Sie die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="42071-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="42071-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42071-174">See also</span></span>

- [<span data-ttu-id="42071-175">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="42071-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="42071-176">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="42071-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="42071-177">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42071-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)