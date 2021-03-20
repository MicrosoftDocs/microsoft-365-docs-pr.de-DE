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
# <a name="manage-security-groups-with-powershell"></a>Verwalten von Sicherheitsgruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um Sicherheitsgruppen zu verwalten. 

In diesem Artikel wird das Auflisten, Erstellen, Ändern von Einstellungen und Entfernen von Sicherheitsgruppen beschrieben. 

Wenn für einen Befehlsblock in diesem Artikel variablen Werte angegeben werden müssen, verwenden Sie die folgenden Schritte.

1. Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Sie ihn in Notepad oder in die integrierte PowerShell-Skriptumgebung (ISE) ein.
2. Füllen Sie die Variablenwerte aus, und entfernen Sie die Zeichen "<" und ">".
3. Führen Sie die Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

Weitere [Informationen finden Sie unter Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="list-your-groups"></a>Auflisten Ihrer Gruppen

Verwenden Sie diesen Befehl, um alle Ihre Gruppen auflisten.

```powershell
Get-AzureADGroup
```
Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe nach dem Anzeigenamen anzuzeigen.

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

Zeigen Sie die Einstellungen der Gruppe mit diesen Befehlen an.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Verwenden Sie dann den [Artikel Set-AzureADGroup,](/powershell/module/azuread/set-azureadgroup) um zu bestimmen, wie eine Einstellung geändert wird.

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
Verwenden Sie diese Befehle, um den aktuellen Besitzern einer Sicherheitsgruppe ein Benutzerkonto mithilfe des Benutzerprinzipalnamens **(User Principal Name, UPN)** hinzuzufügen.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Verwenden Sie diese Befehle, um  den aktuellen Besitzern einer Sicherheitsgruppe ein Benutzerkonto mithilfe des Anzeigenamens hinzuzufügen.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Verwenden Sie diese Befehle, um ein Benutzerkonto von seinem **UPN** an die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Verwenden Sie diese Befehle, um ein Benutzerkonto mithilfe seines **Anzeigenamens** für die aktuellen Besitzer einer Sicherheitsgruppe zu entfernen.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="list-your-groups"></a>Auflisten Ihrer Gruppen

Verwenden Sie diesen Befehl, um alle Ihre Gruppen auflisten.

```powershell
Get-MsolGroup
```
Verwenden Sie diese Befehle, um die Einstellungen einer bestimmten Gruppe nach dem Anzeigenamen anzuzeigen.

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

Zeigen Sie die Einstellungen der Gruppe mit diesen Befehlen an.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Verwenden Sie dann den [Artikel Set-MsolGroup,](/powershell/module/msonline/set-msolgroup) um zu bestimmen, wie eine Einstellung geändert wird.

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