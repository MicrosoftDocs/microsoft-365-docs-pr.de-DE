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
# <a name="maintain-security-group-membership-with-powershell"></a>Verwalten der Mitgliedschaft in Sicherheitsgruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um die Mitgliedschaft in Sicherheitsgruppen in Microsoft 365. 

>[!Note]
>[Erfahren Sie, wie Microsoft 365 gruppenmitgliedschaft](../admin/create-groups/add-or-remove-members-from-groups.md) mit dem Microsoft 365 verwalten. Eine Liste der zusätzlichen Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](../admin/add-users/index.yml).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module
Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe

Geben Sie zum Hinzufügen eines Benutzerkontos über den **UPN** den Benutzerprinzipalnamen (UPN) (Beispiel: belindan@contoso.com) und den Anzeigenamen der Sicherheitsgruppe ein, entfernen Sie die Zeichen "<" und ">", und führen Sie diese Befehle im PowerShell-Fenster oder in der integrierten PowerShell-Skriptumgebung (ISE) aus.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Um ein Benutzerkonto über seinen Anzeigenamen **hinzuzufügen,** geben Sie den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Geben Sie zum Entfernen eines Benutzerkontos durch den **UPN** den Benutzerkonto-UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Geben Sie zum Entfernen eines Benutzerkontos durch den Anzeigenamen den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe

Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten. Microsoft 365 kann jedoch nicht. Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.

Geben Sie zum Hinzufügen einer Gruppe nach dem Anzeigenamen den Anzeigenamen der Gruppe **ein,** die Sie hinzufügen möchten, und den Anzeigenamen der Gruppe, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Um eine Gruppe nach ihrem Anzeigenamen zu **entfernen,** geben Sie den Anzeigenamen der Zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe

Um ein Benutzerkonto über den **UPN** hinzuzufügen, geben Sie den Benutzerprinzipalnamen (UPN) des Benutzerkontos (Beispiel: belindan@contoso.com) und den Gruppenanzeigenamen ein, entfernen die Zeichen "<" und ">", und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Um ein Benutzerkonto über seinen Anzeigenamen **hinzuzufügen,** geben Sie den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Geben Sie zum Entfernen eines Benutzerkontos durch den **UPN** den Benutzerkonto-UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Geben Sie zum Entfernen eines Benutzerkontos durch den Anzeigenamen den Anzeigenamen des Benutzerkontos (Beispiel: Belinda Newman) und den Gruppenanzeigenamen ein, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe

Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten. Microsoft 365 kann jedoch nicht. Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.

Geben Sie zum Hinzufügen einer Gruppe nach dem Anzeigenamen den Anzeigenamen der Gruppe **ein,** die Sie hinzufügen möchten, und den Anzeigenamen der Gruppe, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

Um eine Gruppe nach ihrem Anzeigenamen zu **entfernen,** geben Sie den Anzeigenamen der Zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthält, und führen Sie diese Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)