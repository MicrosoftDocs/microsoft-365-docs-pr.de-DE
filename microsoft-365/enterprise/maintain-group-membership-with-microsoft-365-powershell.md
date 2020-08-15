---
title: Verwalten der Microsoft 365-Gruppenmitgliedschaft mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.openlocfilehash: 61bdcb96433f4f384033768debf416900a305624
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690778"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a>Verwalten der Microsoft 365-Gruppenmitgliedschaft mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um die Gruppenmitgliedschaft in Microsoft 365 beizubehalten. 

> [!TIP]
> Zum Generieren von Ready-to-Run PowerShell-Befehlen durch Angabe von Benutzerkonten-und Gruppennamen verwenden Sie diese [Gruppenpflege Microsoft Excel Arbeitsmappe](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx). 

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module
Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe

**Um ein Benutzerkonto nach seinem UPN hinzuzufügen**, geben Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzerkontos ein (Beispiel: belindan@contoso.com) und den Gruppen Anzeigenamen, indem Sie die Zeichen "<" und ">" entfernen und diese Befehle im PowerShell-Fenster oder in der PowerShell-integrierten Skriptumgebung (ISE) ausführen.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens hinzufügen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie ein Benutzerkonto nach seinem UPN entfernen möchten**, füllen Sie das Benutzerkonto UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeige Namen aus, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens entfernen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe

Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten. Microsoft 365-Gruppen können jedoch nicht. Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.

**Um eine Gruppe nach dem Anzeigenamen hinzuzufügen**, geben Sie den Anzeigenamen der hinzuzufügenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie eine Gruppe nach Ihrem Anzeigenamen entfernen möchten**, geben Sie den Anzeigenamen der zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Benutzerkonten als Mitglieder einer Gruppe

**Um ein Benutzerkonto nach seinem UPN hinzuzufügen**, geben Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzerkontos ein (Beispiel: belindan@contoso.com) und den Gruppen Anzeigenamen, indem Sie die Zeichen "<" und ">" entfernen und diese Befehle im PowerShell-Fenster oder in der PowerShell ISE ausführen.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens hinzufügen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie ein Benutzerkonto nach seinem UPN entfernen möchten**, füllen Sie das Benutzerkonto UPN (Beispiel: belindan@contoso.com) und den Gruppenanzeige Namen aus, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Wenn Sie ein Benutzerkonto anhand des Anzeigenamens entfernen möchten**, geben Sie den Anzeigenamen des Benutzerkontos ein (Beispiel: Belinda Newman) und den Gruppenanzeige Namen, und führen Sie diese Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Hinzufügen oder Entfernen von Gruppen als Mitglieder einer Gruppe

Sicherheitsgruppen können andere Gruppen als Mitglieder enthalten. Microsoft 365-Gruppen können jedoch nicht. Dieser Abschnitt enthält PowerShell-Befehle zum Hinzufügen oder Entfernen von Gruppen nur für eine Sicherheitsgruppe.

**Um eine Gruppe nach dem Anzeigenamen hinzuzufügen**, geben Sie den Anzeigenamen der hinzuzufügenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

**Wenn Sie eine Gruppe nach Ihrem Anzeigenamen entfernen möchten**, geben Sie den Anzeigenamen der zu entfernenden Gruppe und den Anzeigenamen der Gruppe ein, die die Mitgliedergruppe enthalten soll, und führen Sie diese Befehle im PowerShell-Fenster oder in PowerShell ISE aus.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

