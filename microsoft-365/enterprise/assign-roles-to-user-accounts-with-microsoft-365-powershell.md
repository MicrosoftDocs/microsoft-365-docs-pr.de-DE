---
title: Zuweisen von Rollen zu Microsoft 365-Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
description: In diesem Artikel erfahren Sie, wie Sie PowerShell für Microsoft 365 schnell und einfach verwenden können, um Benutzerkontenrollen zuzuweisen.
ms.openlocfilehash: 4726dcea109490ff28299002bc5263aa15dca949
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690328"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="ebdde-103">Zuweisen von Rollen zu Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebdde-103">Assign roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="ebdde-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ebdde-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ebdde-105">Sie können Benutzerkonten schnell und einfach Rollen zuweisen, indem Sie PowerShell für Microsoft 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebdde-105">You can quickly and easily assign roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="ebdde-106">Informationen zum Zuweisen von Rollen zu Benutzerkonten mit dem Microsoft 365 Admin Center finden Sie in den [folgenden Anweisungen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ebdde-106">To assign roles to user accounts with the Microsoft 365 admin center, see [these instructions](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ebdde-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="ebdde-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ebdde-108">Stellen Sie zunächst über ein globales Administratorkonto eine [Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) .</span><span class="sxs-lookup"><span data-stu-id="ebdde-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="ebdde-p101">Als Nächstes ermitteln Sie den Anmeldenamen des Benutzerkontos, das Sie zu einer Rolle hinzufügen möchten (Beispiel: fredsm@contoso.com). Dies wird auch als der Benutzerprinzipalname (User Principal Name, UPN) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ebdde-p101">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com). This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="ebdde-111">Ermitteln Sie nun den Namen der Rolle.</span><span class="sxs-lookup"><span data-stu-id="ebdde-111">Next, determine the name of the role.</span></span> <span data-ttu-id="ebdde-112">Verwenden Sie die [Liste der Berechtigungen der Administratorrolle in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ebdde-112">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="ebdde-113">Achten Sie auf die Hinweise in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="ebdde-113">Pay attention to the notes in this article.</span></span> <span data-ttu-id="ebdde-114">Einige Rollennamen sind für Azure AD PowerShell unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="ebdde-114">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="ebdde-115">Beispielsweise wird die Rolle "SharePoint-Administrator" im Microsoft 365 Admin Center "SharePoint-Dienstadministrator" für Azure AD PowerShell genannt.</span><span class="sxs-lookup"><span data-stu-id="ebdde-115">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="ebdde-116">Als Nächstes geben Sie den Anmelde- und Rollennamen ein, und führen die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="ebdde-116">Next, fill in the sign-in and role names and run these commands.</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="ebdde-117">Es folgt ein Beispiel für einen abgeschlossenen Befehlssatz, der dem belindan@contoso.com-Konto die Rolle "SharePoint-Dienst Administrator" zuweist:</span><span class="sxs-lookup"><span data-stu-id="ebdde-117">Here is an example of a completed command set that assigns the SharePoint Service Administrator role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="ebdde-118">Verwenden Sie diese Befehle zum Anzeigen der Liste der Benutzernamen für eine bestimmte Rolle.</span><span class="sxs-lookup"><span data-stu-id="ebdde-118">To display the list of user names for a specific role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ebdde-119">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebdde-119">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ebdde-120">Stellen Sie zunächst über ein globales Administratorkonto eine [Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) .</span><span class="sxs-lookup"><span data-stu-id="ebdde-120">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="ebdde-121">Bei einer einzelnen Rollenänderung</span><span class="sxs-lookup"><span data-stu-id="ebdde-121">For a single role change</span></span>

<span data-ttu-id="ebdde-122">Die am häufigsten verwendeten Methoden für ein bestimmtes Benutzerkonto sind der Anzeigename oder der e-Mail-Name, auch bekannt für den Anmeldenamen oder den Benutzerprinzipalnamen (User Principal Name, UPN).</span><span class="sxs-lookup"><span data-stu-id="ebdde-122">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="ebdde-123">Anzeigen der Namen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ebdde-123">Display names of user accounts</span></span>

<span data-ttu-id="ebdde-124">Wenn Sie mit den Anzeigenamen von Benutzerkonten arbeiten, müssen Sie Folgendes ermitteln:</span><span class="sxs-lookup"><span data-stu-id="ebdde-124">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="ebdde-125">Das Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ebdde-125">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="ebdde-p104">Beim Angeben des Benutzerkontos müssen Sie seinen Anzeigenamen bestimmen. Verwenden Sie den folgenden Befehl, um eine vollständige Liste der Konten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="ebdde-p104">To specify the user account, you must determine its Display Name. To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="ebdde-p105">Mit diesem Befehl wird der Anzeigename der Benutzerkonten nach Anzeigename sortiert angezeigt, jeweils einer auf einem Bildschirm. Sie können die Liste mit dem **Where** -Cmdlets weiter eingrenzen. Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ebdde-p105">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time. You can filter the list to a smaller set by using the **Where** cmdlet. Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="ebdde-131">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-131">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ebdde-132">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-132">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="ebdde-133">Mit diesem Befehl werden nur die Benutzerkonten angezeigt, deren Anzeigename mit „John“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="ebdde-133">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="ebdde-134">Die Rolle, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ebdde-134">The role you want to assign.</span></span>
    
    <span data-ttu-id="ebdde-135">Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ebdde-135">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="ebdde-136">Nachdem Sie den Anzeigenamen des Kontos und den Namen der Rolle bestimmt haben, verwenden Sie die folgenden Befehle, um dem Konto die Rolle zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="ebdde-136">Once you have determined the Display Name of the account and the Name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="ebdde-137">Kopieren Sie die Befehle, und fügen Sie sie in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="ebdde-137">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="ebdde-138">Ersetzen Sie für die **$dispName** -und **$roleName** -Variablen den Beschreibungstext durch ihre Werte, entfernen Sie die \< and > Zeichen, und lassen Sie die Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-138">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="ebdde-139">Kopieren Sie die geänderten Zeilen, und fügen Sie sie in das Fenster „Windows Azure Active Directory-Modul für Windows PowerShell", um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-139">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="ebdde-140">Alternativ können Sie die Windows PowerShell ISE (Integrated Script Environment) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebdde-140">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="ebdde-141">Hier ein Beispiel für einen abgeschlossenen Befehlssatz:</span><span class="sxs-lookup"><span data-stu-id="ebdde-141">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="ebdde-142">Anmeldenamen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ebdde-142">Sign-in names of user accounts</span></span>

<span data-ttu-id="ebdde-143">Wenn Sie mit den Anmeldenamen oder der UPNs von Benutzerkonten arbeiten, müssen Sie Folgendes ermitteln:</span><span class="sxs-lookup"><span data-stu-id="ebdde-143">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="ebdde-144">Der UPN des Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="ebdde-144">The user account's UPN.</span></span>
    
    <span data-ttu-id="ebdde-145">Wenn Sie den UPN nicht bereits kennen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ebdde-145">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="ebdde-146">Mit diesem Befehl wird der UPN Ihrer Benutzerkonten aufgelistet, sortiert nach dem UPN, jeweils ein Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="ebdde-146">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="ebdde-147">Sie können die Liste mit dem **Where** -Cmdlets weiter eingrenzen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-147">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="ebdde-148">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ebdde-148">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="ebdde-149">Mit diesem Befehl werden nur die Benutzerkonten angezeigt, deren Anzeigename mit „John“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="ebdde-149">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="ebdde-150">Die Rolle, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ebdde-150">The role you want to assign.</span></span>
    
    <span data-ttu-id="ebdde-151">Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ebdde-151">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="ebdde-152">Nachdem Sie über den UPN des Kontos und den Namen der Rolle verfügen, verwenden Sie diese Befehle, um dem Konto die Rolle zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="ebdde-152">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="ebdde-153">Kopieren Sie die Befehle, und fügen Sie sie in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="ebdde-153">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="ebdde-154">Ersetzen Sie für die **$upnName** -und **$roleName** -Variablen den Beschreibungstext durch ihre Werte, entfernen Sie die \< and > Zeichen, und lassen Sie die Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-154">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="ebdde-155">Kopieren Sie die geänderten Zeilen, und fügen Sie sie in das Fenster „Windows Azure Active Directory-Modul für Windows PowerShell", um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebdde-155">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="ebdde-156">Alternativ können Sie die Windows PowerShell ISE verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebdde-156">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="ebdde-157">Hier ein Beispiel für einen abgeschlossenen Befehlssatz:</span><span class="sxs-lookup"><span data-stu-id="ebdde-157">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="ebdde-158">Mehrere Rollenänderungen</span><span class="sxs-lookup"><span data-stu-id="ebdde-158">Multiple role changes</span></span>

<span data-ttu-id="ebdde-159">Bestimmen Sie für mehrere Rollenänderungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ebdde-159">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="ebdde-160">Die Benutzerkonten, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ebdde-160">Which user accounts that you want to configure.</span></span> <span data-ttu-id="ebdde-161">Sie können die Methoden im vorherigen Abschnitt verwenden, um die Gruppe von Anzeigenamen oder UPNs zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="ebdde-161">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="ebdde-162">Rollen, die Sie jedem Benutzerkonto zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ebdde-162">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="ebdde-163">Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ebdde-163">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="ebdde-164">Erstellen Sie als nächstes eine CSV-Textdatei (Comma-Separated Value) mit den Feldern Anzeigename oder UPN-und Rollenname.</span><span class="sxs-lookup"><span data-stu-id="ebdde-164">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="ebdde-165">Sie können dies problemlos mit Microsoft Excel tun.</span><span class="sxs-lookup"><span data-stu-id="ebdde-165">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="ebdde-166">Im folgenden finden Sie ein Beispiel für Anzeigenamen:</span><span class="sxs-lookup"><span data-stu-id="ebdde-166">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="ebdde-167">Geben Sie anschließend den Speicherort der CSV-Datei an, und führen Sie die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="ebdde-167">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="ebdde-168">Hier ist ein Beispiel für UPNs:</span><span class="sxs-lookup"><span data-stu-id="ebdde-168">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="ebdde-169">Geben Sie anschließend den Speicherort der CSV-Datei an, und führen Sie die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="ebdde-169">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="ebdde-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebdde-170">See also</span></span>

- [<span data-ttu-id="ebdde-171">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebdde-171">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="ebdde-172">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebdde-172">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="ebdde-173">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebdde-173">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
