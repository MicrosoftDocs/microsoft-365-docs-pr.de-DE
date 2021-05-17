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
description: Erfahren Sie, wie Sie Mithilfe von PowerShell die Mitgliedschaft in Microsoft 365 verwalten.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909574"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="1ab71-103">Verwalten der Mitgliedschaft in Sicherheitsgruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ab71-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="1ab71-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1ab71-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1ab71-105">Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um die Mitgliedschaft in Sicherheitsgruppen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ab71-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="1ab71-106">[Erfahren Sie, wie Microsoft 365 gruppenmitgliedschaft](../admin/create-groups/add-or-remove-members-from-groups.md) mit dem Microsoft 365 verwalten.</span><span class="sxs-lookup"><span data-stu-id="1ab71-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="1ab71-107">Eine Liste der zusätzlichen Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="1ab71-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1ab71-108">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="1ab71-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="1ab71-109">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1ab71-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="1ab71-110">Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="1ab71-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="1ab71-111">Geben Sie zum Hinzufügen eines Benutzerkontos über den **UPN** den Benutzerprinzipalnamen (UPN) (Beispiel: belindan@contoso.com) und den Anzeigenamen der Sicherheitsgruppe ein, entfernen Sie die Zeichen "<" und ">", und führen Sie diese Befehle im PowerShell-Fenster oder in der integrierten PowerShell-Skriptumgebung (ISE) aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-112">Um ein Benutzerkonto über seinen Anzeigenamen **hinzuzufügen,** geben Sie den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-113">Geben Sie zum Entfernen eines Benutzerkontos durch den **UPN** den Benutzerkonto-UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-114">Geben Sie zum Entfernen eines Benutzerkontos durch den Anzeigenamen den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="1ab71-115">Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="1ab71-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="1ab71-116">Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ab71-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="1ab71-117">Microsoft 365 kann jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="1ab71-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="1ab71-118">Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1ab71-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="1ab71-119">Geben Sie zum Hinzufügen einer Gruppe nach dem Anzeigenamen den Anzeigenamen der Gruppe **ein,** die Sie hinzufügen möchten, und den Anzeigenamen der Gruppe, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-120">Um eine Gruppe nach ihrem Anzeigenamen zu **entfernen,** geben Sie den Anzeigenamen der Zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1ab71-121">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ab71-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1ab71-122">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="1ab71-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="1ab71-123">Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="1ab71-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="1ab71-124">Um ein Benutzerkonto über den **UPN** hinzuzufügen, geben Sie den Benutzerprinzipalnamen (UPN) des Benutzerkontos (Beispiel: belindan@contoso.com) und den Gruppenanzeigenamen ein, entfernen die Zeichen "<" und ">", und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-125">Um ein Benutzerkonto über seinen Anzeigenamen **hinzuzufügen,** geben Sie den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-126">Geben Sie zum Entfernen eines Benutzerkontos durch den **UPN** den Benutzerkonto-UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1ab71-127">Geben Sie zum Entfernen eines Benutzerkontos durch den Anzeigenamen den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="1ab71-128">Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="1ab71-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="1ab71-129">Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ab71-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="1ab71-130">Microsoft 365 kann jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="1ab71-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="1ab71-131">Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1ab71-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="1ab71-132">Geben Sie zum Hinzufügen einer Gruppe nach dem Anzeigenamen den Anzeigenamen der Gruppe **ein,** die Sie hinzufügen möchten, und den Anzeigenamen der Gruppe, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="1ab71-133">Um eine Gruppe nach ihrem Anzeigenamen zu **entfernen,** geben Sie den Anzeigenamen der Zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.</span><span class="sxs-lookup"><span data-stu-id="1ab71-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="1ab71-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ab71-134">See also</span></span>

[<span data-ttu-id="1ab71-135">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ab71-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1ab71-136">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ab71-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1ab71-137">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ab71-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)