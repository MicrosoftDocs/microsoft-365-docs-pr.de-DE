---
title: Verwalten der Microsoft 365-Gruppenmitgliedschaft mit PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Erfahren Sie, wie Sie mithilfe von PowerShell die Mitgliedschaft in Microsoft 365-Gruppen beibehalten.
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235630"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="0ab3d-103">Verwalten der Microsoft 365-Gruppenmitgliedschaft mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ab3d-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="0ab3d-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0ab3d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0ab3d-105">Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um die Gruppenmitgliedschaft in Microsoft 365 beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="0ab3d-106">Zum Generieren von Ready-to-Run PowerShell-Befehlen durch Angabe von Benutzerkonten-und Gruppennamen verwenden Sie diese [Gruppenpflege Microsoft Excel Arbeitsmappe](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span><span class="sxs-lookup"><span data-stu-id="0ab3d-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

>[!Note]
><span data-ttu-id="0ab3d-107">[Erfahren Sie, wie Sie die Microsoft 365-Gruppenmitgliedschaft](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) mit dem Microsoft 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-107">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="0ab3d-108">Eine Liste mit weiteren Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="0ab3d-108">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="0ab3d-109">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="0ab3d-109">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="0ab3d-110">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="0ab3d-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="0ab3d-111">Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="0ab3d-111">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="0ab3d-112">**Um ein Benutzerkonto nach seinem UPN hinzuzufügen**, geben Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzerkontos ein (Beispiel: belindan@contoso.com) und den Gruppen Anzeigenamen, indem Sie die Zeichen "<" und ">" entfernen und diese Befehle im PowerShell-Fenster oder in der PowerShell-integrierten Skriptumgebung (ISE) ausführen.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-112">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-113">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens hinzufügen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-113">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-114">**Wenn Sie ein Benutzerkonto nach seinem UPN entfernen möchten**, füllen Sie das Benutzerkonto UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeige Namen aus, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-114">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-115">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens entfernen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-115">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="0ab3d-116">Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="0ab3d-116">Add or remove groups as members of a group</span></span>

<span data-ttu-id="0ab3d-117">Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-117">Security groups can contain other groups as members.</span></span> <span data-ttu-id="0ab3d-118">Microsoft 365-Gruppen können jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-118">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="0ab3d-119">Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-119">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="0ab3d-120">**Um eine Gruppe nach dem Anzeigenamen hinzuzufügen**, geben Sie den Anzeigenamen der hinzuzufügenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-120">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-121">**Wenn Sie eine Gruppe nach Ihrem Anzeigenamen entfernen möchten**, geben Sie den Anzeigenamen der zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-121">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0ab3d-122">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ab3d-122">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0ab3d-123">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0ab3d-123">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="0ab3d-124">Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="0ab3d-124">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="0ab3d-125">**Um ein Benutzerkonto nach seinem UPN hinzuzufügen**, geben Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzerkontos ein (Beispiel: belindan@contoso.com) und den Gruppen Anzeigenamen, indem Sie die Zeichen "<" und ">" entfernen und diese Befehle im PowerShell-Fenster oder in der PowerShell ISE ausführen.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-125">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-126">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens hinzufügen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-126">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-127">**Wenn Sie ein Benutzerkonto nach seinem UPN entfernen möchten**, füllen Sie das Benutzerkonto UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeige Namen aus, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-127">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="0ab3d-128">**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens entfernen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-128">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="0ab3d-129">Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="0ab3d-129">Add or remove groups as members of a group</span></span>

<span data-ttu-id="0ab3d-130">Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-130">Security groups can contain other groups as members.</span></span> <span data-ttu-id="0ab3d-131">Microsoft 365-Gruppen können jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-131">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="0ab3d-132">Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-132">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="0ab3d-133">**Um eine Gruppe nach dem Anzeigenamen hinzuzufügen**, geben Sie den Anzeigenamen der hinzuzufügenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-133">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="0ab3d-134">**Wenn Sie eine Gruppe nach Ihrem Anzeigenamen entfernen möchten**, geben Sie den Anzeigenamen der zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="0ab3d-134">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="0ab3d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ab3d-135">See also</span></span>

[<span data-ttu-id="0ab3d-136">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ab3d-136">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0ab3d-137">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ab3d-137">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0ab3d-138">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ab3d-138">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

