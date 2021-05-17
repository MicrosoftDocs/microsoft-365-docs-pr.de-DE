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
description: Erfahren Sie, wie Sie PowerShell zum Verwalten von Kennwörtern verwenden.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073212"
---
# <a name="manage-passwords-with-powershell"></a>Verwalten von Kennwörtern mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 als Alternative zum Microsoft 365 Admin Center zum Verwalten von Kennwörtern in Microsoft 365. 

Wenn für einen Befehlsblock in diesem Artikel variablen Werte angegeben werden müssen, verwenden Sie die folgenden Schritte.

1. Kopieren Sie den Befehlsblock in die Zwischenablage, und fügen Editor oder die integrierte PowerShell Script Environment (ISE) ein.
2. Füllen Sie die Variablenwerte aus, und entfernen Sie die Zeichen "<" und ">".
3. Führen Sie die Befehle im PowerShell-Fenster oder im PowerShell-ISE aus.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="set-a-password"></a>Festlegen eines Kennworts

Verwenden Sie diese Befehle, um ein Kennwort für ein Benutzerkonto anzugeben.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>Erzwingen, dass ein Benutzer sein Kennwort ändert

Verwenden Sie diese Befehle, um ein Kennwort zu setzen und einen Benutzer zum Ändern des neuen Kennworts zu zwingen.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

Verwenden Sie diese Befehle, um ein Kennwort festlegen und einen Benutzer zwingen, sein neues Kennwort bei der nächsten Anmeldung zu ändern.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="set-a-password"></a>Festlegen eines Kennworts

Verwenden Sie diese Befehle, um ein Kennwort für ein Benutzerkonto anzugeben.

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>Erzwingen, dass ein Benutzer sein Kennwort ändert

Verwenden Sie diese Befehle, um einen Benutzer zum Ändern des Kennworts zu zwingen.

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

