---
title: Löschen von Microsoft 365-Benutzerkonten mit PowerShell
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: In diesem Artikel erfahren Sie, wie Sie mithilfe verschiedener Module in PowerShell Microsoft 365-Benutzerkonten löschen.
ms.openlocfilehash: 0c13b57c13fb3d01d648438a5d6973fea8b9db67
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235442"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Löschen von Microsoft 365-Benutzerkonten mit PowerShell

Sie können PowerShell für Microsoft 365 verwenden, um ein Benutzerkonto zu löschen und wiederherzustellen.

>[!Note]
>[Hier erfahren Sie, wie Sie ein Benutzerkonto](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) im Microsoft 365 Admin Center wiederherstellen. Eine Liste mit weiteren Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Nachdem Sie eine Verbindung hergestellt haben, verwenden Sie die folgende Syntax, um ein einzelnes Benutzerkonto zu entfernen:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

In diesem Beispiel wird das Benutzerkonto „fabricec@litwareinc.com“ entfernt.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Der Parameter **-objectID** im Cmdlet **Remove-AzureADUser** akzeptiert entweder den Anmeldenamen des Kontos, der auch als Benutzerprinzipalname bezeichnet wird, oder die Objekt-ID des Kontos.
  
Um den Kontonamen basierend auf dem Namen des Benutzers anzuzeigen, verwenden Sie die folgenden Befehle:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Kontoname für den Benutzer namens Caleb Sills angezeigt.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Um einen Kontonamen basierend auf dem Anzeigenamen des Benutzers zu entfernen, verwenden Sie die folgenden Befehle:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Wenn Sie ein Benutzerkonto mit dem Microsoft Azure AD-Modul für Windows PowerShell löschen, wird das Konto nicht endgültig gelöscht. Sie können das gelöschte Benutzerkonto innerhalb von 30 Tagen wiederherstellen.

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Wenn Sie ein Benutzerkonto löschen möchten, verwenden Sie die folgende Syntax:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

In diesem Beispiel wird das Benutzerkonto „BelindaN@litwareinc.com“ gelöscht.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Wenn Sie ein gelöschtes Benutzerkonto innerhalb der Nachfrist von 30 Tagen wiederherstellen möchten, verwenden Sie die folgende Syntax:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

In diesem Beispiel wird das gelöschte Benutzerkonto „BelindaN@litwareinc.com“ wiederhergestellt.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 **Hinweise:**
  
- Um die Liste der gelöschten Benutzer anzuzeigen, die wiederhergestellt werden können, führen Sie den folgenden Befehl aus:
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- Wenn der ursprüngliche Benutzerprinzipalnamen des Benutzerkontos durch ein anderes Konto verwendet wird, verwenden Sie den _NewUserPrincipalName_-Parameter anstelle von _UserPrincipalName_, um einen anderen Benutzerprinzipalnamen anzugeben, wenn Sie das Benutzerkonto wiederherstellen.


## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
