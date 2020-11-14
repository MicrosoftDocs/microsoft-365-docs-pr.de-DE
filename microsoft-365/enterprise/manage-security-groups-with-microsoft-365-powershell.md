---
title: Verwalten von Sicherheitsgruppen mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Erfahren Sie, wie Sie mithilfe von PowerShell Sicherheitsgruppen verwalten.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073233"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="e6287-103">Verwalten von Sicherheitsgruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6287-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="e6287-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e6287-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e6287-105">Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um Sicherheitsgruppen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e6287-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="e6287-106">In diesem Artikel wird das auflisten, erstellen, Ändern von Einstellungen und Entfernen von Sicherheitsgruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6287-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="e6287-107">Wenn für einen Befehlsblock in diesem Artikel Variablenwerte angegeben werden müssen, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="e6287-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="e6287-108">Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Sie ihn in Editor oder in die PowerShell Integrated Script Environment (ISE) ein.</span><span class="sxs-lookup"><span data-stu-id="e6287-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="e6287-109">Geben Sie die Variablenwerte ein, und entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="e6287-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="e6287-110">Führen Sie die Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="e6287-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="e6287-111">Informationen zum Verwalten der Gruppenmitgliedschaft mit PowerShell finden Sie unter [MAINTAIN Security Group Membership](maintain-group-membership-with-microsoft-365-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="e6287-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e6287-112">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="e6287-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e6287-113">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="e6287-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="e6287-114">Gruppen auflisten</span><span class="sxs-lookup"><span data-stu-id="e6287-114">List your groups</span></span>

<span data-ttu-id="e6287-115">Verwenden Sie diesen Befehl, um alle Ihre Gruppen aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="e6287-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="e6287-116">Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe anhand des Anzeigenamens anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e6287-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="e6287-117">Erstellen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-117">Create a new group</span></span>

<span data-ttu-id="e6287-118">Verwenden Sie diesen Befehl, um eine neue Sicherheitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6287-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="e6287-119">Ändern der Einstellungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-119">Change the settings on a group</span></span>

<span data-ttu-id="e6287-120">Zeigt die Einstellungen der Gruppe mit den folgenden Befehlen an.</span><span class="sxs-lookup"><span data-stu-id="e6287-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="e6287-121">Verwenden Sie dann den Artikel " [AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) ", um zu bestimmen, wie eine Einstellung geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6287-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="e6287-122">Entfernen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-122">Remove a security group</span></span>

<span data-ttu-id="e6287-123">Verwenden Sie diese Befehle, um eine Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e6287-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="e6287-124">Verwalten der Besitzer einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-124">Manage the owners of a security group</span></span>

<span data-ttu-id="e6287-125">Verwenden Sie diese Befehle, um die aktuellen Besitzer einer Sicherheitsgruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e6287-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="e6287-126">Verwenden Sie diese Befehle, um dem aktuellen Besitzer einer Sicherheitsgruppe ein Benutzerkonto durch den **Benutzerprinzipalnamen (User Principal Name, UPN)** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6287-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="e6287-127">Verwenden Sie diese Befehle, um dem aktuellen Besitzer einer Sicherheitsgruppe ein Benutzerkonto anhand seines **Anzeigenamens** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6287-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="e6287-128">Verwenden Sie diese Befehle, um ein Benutzerkonto durch seinen **UPN** an die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e6287-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="e6287-129">Verwenden Sie diese Befehle, um ein Benutzerkonto anhand seines **Anzeigenamens** an die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e6287-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e6287-130">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6287-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e6287-131">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6287-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="e6287-132">Gruppen auflisten</span><span class="sxs-lookup"><span data-stu-id="e6287-132">List your groups</span></span>

<span data-ttu-id="e6287-133">Verwenden Sie diesen Befehl, um alle Ihre Gruppen aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="e6287-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="e6287-134">Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe anhand des Anzeigenamens anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e6287-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="e6287-135">Erstellen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-135">Create a new group</span></span>

<span data-ttu-id="e6287-136">Verwenden Sie diesen Befehl, um eine neue Sicherheitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6287-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="e6287-137">Ändern der Einstellungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-137">Change the settings on a group</span></span>

<span data-ttu-id="e6287-138">Zeigt die Einstellungen der Gruppe mit den folgenden Befehlen an.</span><span class="sxs-lookup"><span data-stu-id="e6287-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="e6287-139">Verwenden Sie dann den Artikel " [MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) ", um zu bestimmen, wie eine Einstellung geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6287-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="e6287-140">Entfernen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="e6287-140">Remove a security group</span></span>

<span data-ttu-id="e6287-141">Verwenden Sie diese Befehle, um eine Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e6287-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="e6287-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6287-142">See also</span></span>

[<span data-ttu-id="e6287-143">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6287-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e6287-144">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6287-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e6287-145">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6287-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

