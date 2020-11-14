---
title: Verwalten der Mitgliedschaft in Sicherheitsgruppen mit PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Erfahren Sie, wie Sie mithilfe von PowerShell die Mitgliedschaft in Microsoft 365-Gruppen beibehalten.
ms.openlocfilehash: b47f501c9726e1d4dcb2e9d61108224db0408b8e
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073061"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="5f001-103">Verwalten der Mitgliedschaft in Sicherheitsgruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f001-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="5f001-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5f001-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5f001-105">Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um die Mitgliedschaft in Sicherheitsgruppen in Microsoft 365 beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="5f001-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="5f001-106">[Erfahren Sie, wie Sie die Microsoft 365-Gruppenmitgliedschaft](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) mit dem Microsoft 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="5f001-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="5f001-107">Eine Liste mit weiteren Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="5f001-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5f001-108">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="5f001-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="5f001-109">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5f001-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="5f001-110">Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="5f001-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="5f001-111">**Wenn Sie ein Benutzerkonto nach seinem UPN hinzufügen möchten** , geben Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzerkontos ein (Beispiel: belindan@contoso.com) und den Anzeigenamen der Sicherheitsgruppe, entfernen Sie die Zeichen "<" und ">", und führen Sie diese Befehle im PowerShell-Fenster oder in der integrierten PowerShell-Skriptumgebung (ISE) aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-111">**To add a user account by its UPN** , fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-112">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens hinzufügen möchten** , geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-112">**To add a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-113">**Wenn Sie ein Benutzerkonto nach seinem UPN entfernen möchten** , füllen Sie das Benutzerkonto UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeige Namen aus, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-113">**To remove a user account by its UPN** , fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-114">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens entfernen möchten** , geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-114">**To remove a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="5f001-115">Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="5f001-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="5f001-116">Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f001-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="5f001-117">Microsoft 365-Gruppen können jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="5f001-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="5f001-118">Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="5f001-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="5f001-119">**Um eine Gruppe nach dem Anzeigenamen hinzuzufügen** , geben Sie den Anzeigenamen der hinzuzufügenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-119">**To add a group by its display name** , fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-120">**Wenn Sie eine Gruppe nach Ihrem Anzeigenamen entfernen möchten** , geben Sie den Anzeigenamen der zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-120">**To remove a group by its display name** , fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5f001-121">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f001-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5f001-122">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f001-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="5f001-123">Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="5f001-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="5f001-124">**Um ein Benutzerkonto nach seinem UPN hinzuzufügen** , geben Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzerkontos ein (Beispiel: belindan@contoso.com) und den Gruppen Anzeigenamen, indem Sie die Zeichen "<" und ">" entfernen und diese Befehle im PowerShell-Fenster oder in der PowerShell ISE ausführen.</span><span class="sxs-lookup"><span data-stu-id="5f001-124">**To add a user account by its UPN** , fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-125">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens hinzufügen möchten** , geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-125">**To add a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-126">**Wenn Sie ein Benutzerkonto nach seinem UPN entfernen möchten** , füllen Sie das Benutzerkonto UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeige Namen aus, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-126">**To remove a user account by its UPN** , fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="5f001-127">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens entfernen möchten** , geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-127">**To remove a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="5f001-128">Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="5f001-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="5f001-129">Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f001-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="5f001-130">Microsoft 365-Gruppen können jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="5f001-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="5f001-131">Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="5f001-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="5f001-132">**Um eine Gruppe nach dem Anzeigenamen hinzuzufügen** , geben Sie den Anzeigenamen der hinzuzufügenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-132">**To add a group by its display name** , fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="5f001-133">**Wenn Sie eine Gruppe nach Ihrem Anzeigenamen entfernen möchten** , geben Sie den Anzeigenamen der zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="5f001-133">**To remove a group by its display name** , fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="5f001-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f001-134">See also</span></span>

[<span data-ttu-id="5f001-135">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f001-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5f001-136">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f001-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5f001-137">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f001-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

