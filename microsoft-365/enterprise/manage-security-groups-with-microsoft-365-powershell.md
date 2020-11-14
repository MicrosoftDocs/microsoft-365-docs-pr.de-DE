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
# <a name="manage-security-groups-with-powershell"></a>Verwalten von Sicherheitsgruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um Sicherheitsgruppen zu verwalten. 

In diesem Artikel wird das auflisten, erstellen, Ändern von Einstellungen und Entfernen von Sicherheitsgruppen beschrieben. 

Wenn für einen Befehlsblock in diesem Artikel Variablenwerte angegeben werden müssen, führen Sie die folgenden Schritte aus.

1. Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Sie ihn in Editor oder in die PowerShell Integrated Script Environment (ISE) ein.
2. Geben Sie die Variablenwerte ein, und entfernen Sie die Zeichen "<" und ">".
3. Führen Sie die Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

Informationen zum Verwalten der Gruppenmitgliedschaft mit PowerShell finden Sie unter [MAINTAIN Security Group Membership](maintain-group-membership-with-microsoft-365-powershell.md) .

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Gruppen auflisten

Verwenden Sie diesen Befehl, um alle Ihre Gruppen aufzulisten.

```powershell
Get-AzureADGroup
```
Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe anhand des Anzeigenamens anzuzeigen.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Erstellen einer neuen Gruppe

Verwenden Sie diesen Befehl, um eine neue Sicherheitsgruppe zu erstellen.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Ändern der Einstellungen für eine Gruppe

Zeigt die Einstellungen der Gruppe mit den folgenden Befehlen an.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Verwenden Sie dann den Artikel " [AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) ", um zu bestimmen, wie eine Einstellung geändert werden soll.

### <a name="remove-a-security-group"></a>Entfernen einer Sicherheitsgruppe

Verwenden Sie diese Befehle, um eine Sicherheitsgruppe zu entfernen.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Verwalten der Besitzer einer Sicherheitsgruppe

Verwenden Sie diese Befehle, um die aktuellen Besitzer einer Sicherheitsgruppe anzuzeigen.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Verwenden Sie diese Befehle, um dem aktuellen Besitzer einer Sicherheitsgruppe ein Benutzerkonto durch den **Benutzerprinzipalnamen (User Principal Name, UPN)** hinzuzufügen.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Verwenden Sie diese Befehle, um dem aktuellen Besitzer einer Sicherheitsgruppe ein Benutzerkonto anhand seines **Anzeigenamens** hinzuzufügen.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Verwenden Sie diese Befehle, um ein Benutzerkonto durch seinen **UPN** an die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Verwenden Sie diese Befehle, um ein Benutzerkonto anhand seines **Anzeigenamens** an die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Gruppen auflisten

Verwenden Sie diesen Befehl, um alle Ihre Gruppen aufzulisten.

```powershell
Get-MsolGroup
```
Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe anhand des Anzeigenamens anzuzeigen.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Erstellen einer neuen Gruppe

Verwenden Sie diesen Befehl, um eine neue Sicherheitsgruppe zu erstellen.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Ändern der Einstellungen für eine Gruppe

Zeigt die Einstellungen der Gruppe mit den folgenden Befehlen an.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Verwenden Sie dann den Artikel " [MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) ", um zu bestimmen, wie eine Einstellung geändert werden soll.

### <a name="remove-a-security-group"></a>Entfernen einer Sicherheitsgruppe

Verwenden Sie diese Befehle, um eine Sicherheitsgruppe zu entfernen.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

