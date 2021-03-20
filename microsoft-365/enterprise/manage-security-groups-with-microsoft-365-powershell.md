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
description: Erfahren Sie, wie Sie PowerShell zum Verwalten von Sicherheitsgruppen verwenden.
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909502"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="fe989-103">Verwalten von Sicherheitsgruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe989-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="fe989-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fe989-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fe989-105">Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um Sicherheitsgruppen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fe989-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="fe989-106">In diesem Artikel wird das Auflisten, Erstellen, Ändern von Einstellungen und Entfernen von Sicherheitsgruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe989-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="fe989-107">Wenn für einen Befehlsblock in diesem Artikel variablen Werte angegeben werden müssen, verwenden Sie die folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="fe989-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="fe989-108">Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Sie ihn in Notepad oder in die integrierte PowerShell-Skriptumgebung (ISE) ein.</span><span class="sxs-lookup"><span data-stu-id="fe989-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="fe989-109">Füllen Sie die Variablenwerte aus, und entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="fe989-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="fe989-110">Führen Sie die Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="fe989-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="fe989-111">Weitere [Informationen finden Sie unter Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe989-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fe989-112">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="fe989-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fe989-113">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="fe989-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="fe989-114">Auflisten Ihrer Gruppen</span><span class="sxs-lookup"><span data-stu-id="fe989-114">List your groups</span></span>

<span data-ttu-id="fe989-115">Verwenden Sie diesen Befehl, um alle Ihre Gruppen auflisten.</span><span class="sxs-lookup"><span data-stu-id="fe989-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="fe989-116">Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe nach dem Anzeigenamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe989-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="fe989-117">Erstellen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-117">Create a new group</span></span>

<span data-ttu-id="fe989-118">Verwenden Sie diesen Befehl, um eine neue Sicherheitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe989-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="fe989-119">Ändern der Einstellungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-119">Change the settings on a group</span></span>

<span data-ttu-id="fe989-120">Zeigen Sie die Einstellungen der Gruppe mit diesen Befehlen an.</span><span class="sxs-lookup"><span data-stu-id="fe989-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="fe989-121">Verwenden Sie dann den [Artikel Set-AzureADGroup,](/powershell/module/azuread/set-azureadgroup) um zu bestimmen, wie eine Einstellung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="fe989-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="fe989-122">Entfernen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-122">Remove a security group</span></span>

<span data-ttu-id="fe989-123">Verwenden Sie diese Befehle, um eine Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe989-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="fe989-124">Verwalten der Besitzer einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-124">Manage the owners of a security group</span></span>

<span data-ttu-id="fe989-125">Verwenden Sie diese Befehle, um die aktuellen Besitzer einer Sicherheitsgruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe989-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="fe989-126">Verwenden Sie diese Befehle, um den aktuellen Besitzern einer Sicherheitsgruppe ein Benutzerkonto mithilfe des Benutzerprinzipalnamens **(User Principal Name, UPN)** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe989-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="fe989-127">Verwenden Sie diese Befehle, um  den aktuellen Besitzern einer Sicherheitsgruppe ein Benutzerkonto mithilfe des Anzeigenamens hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe989-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="fe989-128">Verwenden Sie diese Befehle, um ein Benutzerkonto von seinem **UPN** an die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe989-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="fe989-129">Verwenden Sie diese Befehle, um ein Benutzerkonto mithilfe seines **Anzeigenamens** für die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe989-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fe989-130">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe989-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fe989-131">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="fe989-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="fe989-132">Auflisten Ihrer Gruppen</span><span class="sxs-lookup"><span data-stu-id="fe989-132">List your groups</span></span>

<span data-ttu-id="fe989-133">Verwenden Sie diesen Befehl, um alle Ihre Gruppen auflisten.</span><span class="sxs-lookup"><span data-stu-id="fe989-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="fe989-134">Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe nach dem Anzeigenamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe989-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="fe989-135">Erstellen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-135">Create a new group</span></span>

<span data-ttu-id="fe989-136">Verwenden Sie diesen Befehl, um eine neue Sicherheitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe989-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="fe989-137">Ändern der Einstellungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-137">Change the settings on a group</span></span>

<span data-ttu-id="fe989-138">Zeigen Sie die Einstellungen der Gruppe mit diesen Befehlen an.</span><span class="sxs-lookup"><span data-stu-id="fe989-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="fe989-139">Verwenden Sie dann den [Artikel Set-MsolGroup,](/powershell/module/msonline/set-msolgroup) um zu bestimmen, wie eine Einstellung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="fe989-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="fe989-140">Entfernen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fe989-140">Remove a security group</span></span>

<span data-ttu-id="fe989-141">Verwenden Sie diese Befehle, um eine Sicherheitsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe989-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="fe989-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe989-142">See also</span></span>

[<span data-ttu-id="fe989-143">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe989-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe989-144">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe989-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe989-145">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe989-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)