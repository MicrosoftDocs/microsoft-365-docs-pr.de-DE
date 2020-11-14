---
title: Verwalten von Kennwörtern mit PowerShell
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
description: Erfahren Sie, wie Sie mithilfe von PowerShell Kennwörter verwalten.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073212"
---
# <a name="manage-passwords-with-powershell"></a>Verwalten von Kennwörtern mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center verwenden, um Kennwörter in Microsoft 365 zu verwalten. 

Wenn für einen Befehlsblock in diesem Artikel Variablenwerte angegeben werden müssen, führen Sie die folgenden Schritte aus.

1. Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Sie ihn in Editor oder in die PowerShell Integrated Script Environment (ISE) ein.
2. Geben Sie die Variablenwerte ein, und entfernen Sie die Zeichen "<" und ">".
3. Führen Sie die Befehle im PowerShell-Fenster oder in der PowerShell ISE aus.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="set-a-password"></a>Festlegen eines Kennworts

Verwenden Sie diese Befehle, um ein Kennwort für ein Benutzerkonto anzugeben.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>Erzwingen der Änderung des Kennworts für einen Benutzer

Verwenden Sie diese Befehle, um ein Kennwort festzulegen und zu erzwingen, dass ein Benutzer sein neues Kennwort ändert.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

Verwenden Sie diese Befehle, um ein Kennwort festzulegen und zu erzwingen, dass ein Benutzer sein neues Kennwort ändert, wenn er sich das nächste Mal anmeldet.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="set-a-password"></a>Festlegen eines Kennworts

Verwenden Sie diese Befehle, um ein Kennwort für ein Benutzerkonto anzugeben.

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>Erzwingen der Änderung des Kennworts für einen Benutzer

Verwenden Sie diese Befehle, um zu erzwingen, dass ein Benutzer sein Kennwort ändert.

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

