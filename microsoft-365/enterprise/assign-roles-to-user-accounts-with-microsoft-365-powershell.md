---
title: Zuweisen von Rollen zu Microsoft 365-Benutzerkonten mit PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: In diesem Artikel erfahren Sie, wie Sie PowerShell für Microsoft 365 schnell und einfach verwenden können, um Benutzerkontenadministrator Rollen zuzuweisen.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754198"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Zuweisen von Administratorrollen zu Microsoft 365-Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können Benutzerkonten problemlos Rollen zuweisen, indem Sie PowerShell für Microsoft 365 verwenden.

>[!Note]
>Informationen zum  [Zuweisen von Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) zu Benutzerkonten mit dem Microsoft 365 Admin Center.
>
>Eine Liste mit weiteren Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Verwenden Sie zunächst ein globales Administratorkonto, um eine [Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Identifizieren Sie als nächstes den Anmeldenamen des Benutzerkontos, das Sie einer Rolle hinzufügen möchten (Beispiel: fredsm \@ contoso.com). Dies wird auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet.

Ermitteln Sie nun den Namen der Rolle. Weitere Informationen finden Sie unter [Administratorrollen Berechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Achten Sie auf die Hinweise in diesem Artikel. Einige Rollennamen unterscheiden sich für Azure Active Directory (Azure AD) PowerShell. Die *SharePoint-Administrator* Rolle im Microsoft 365 Admin Center ist beispielsweise *SharePoint-Dienstadministrator* in Azure AD PowerShell.
>

Geben Sie als nächstes die Anmelde-und Rollennamen ein, und führen Sie die folgenden Befehle aus:
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Hier ist ein Beispiel für einen abgeschlossenen Befehlssatz, der die Rolle des SharePoint-Dienstadministrators dem contoso.com-Konto von *belindan \@ * zuweist:
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Verwenden Sie diese Befehle, um die Liste der Benutzernamen für eine bestimmte Administratorrolle anzuzeigen.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Verwenden Sie zunächst ein globales Administratorkonto, um eine [Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
### <a name="for-a-single-role-change"></a>Bei einer einzelnen Rollenänderung

Die am häufigsten verwendeten Methoden zum Angeben des Benutzerkontos sind der Anzeigename oder der e-Mail-Name, der auch als Anmeldename oder Benutzerprinzipalname (UPN) bezeichnet wird.

#### <a name="display-names-of-user-accounts"></a>Anzeigen der Namen von Benutzerkonten

Wenn Sie mit den Anzeigenamen von Benutzerkonten gearbeitet haben, müssen Sie die folgenden Informationen ermitteln:
  
- Das Benutzerkonto, das Sie konfigurieren möchten
    
    Beim Angeben des Benutzerkontos müssen Sie seinen Anzeigenamen bestimmen. Verwenden Sie diesen Befehl, um eine vollständige Liste der Konten zu erhalten:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Mit diesem Befehl wird der Anzeigename der Benutzerkonten nach Anzeigename sortiert angezeigt, jeweils einer auf einem Bildschirm. Sie können die Liste mit dem **Where** -Cmdlets weiter eingrenzen. Beispiel:

   >[!Note]
   >PowerShell Core unterstützt das Microsoft Azure Active Directory Modul für Windows PowerShell Modul und Cmdlets mit *MSOL* nicht in Ihrem Namen. Führen Sie diese Cmdlets aus Windows PowerShell aus.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Mit diesem Befehl werden nur die Benutzerkonten angezeigt, deren Anzeigename mit „John“ beginnt.
    
- Die Rolle, die Sie zuweisen möchten
    
    Verwenden Sie den folgenden Befehl, um die Liste der verfügbaren Administratorrollen anzuzeigen, die Sie Benutzerkonten zuweisen können:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Nachdem Sie den Anzeigenamen des Kontos und den Namen der Rolle bestimmt haben, verwenden Sie die folgenden Befehle, um dem Konto die Rolle zuzuweisen:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Fügen Sie die Befehle in Notepad ein. Ersetzen Sie für die *$dispName* -und *$roleName* -Variablen den Beschreibungstext durch ihre Werte. Entfernen Sie die \< and > Zeichen, aber halten Sie die Anführungszeichen. Fügen Sie die geänderten Zeilen in das Microsoft Azure Active Directory Modul für Windows PowerShell Fenster ein, um Sie auszuführen. Alternativ können Sie die Windows PowerShell ISE (Integrated Script Environment) verwenden.
  
Hier ist ein Beispiel für eine abgeschlossene Befehlsgruppe:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Anmeldenamen von Benutzerkonten

Wenn Sie mit den Anmeldenamen oder der UPNs von Benutzerkonten arbeiten, müssen Sie die folgenden Informationen ermitteln:
  
- UPN des Benutzerkontos
    
    Wenn Sie den UPN nicht kennen, verwenden Sie diesen Befehl:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Mit diesem Befehl wird der UPN Ihrer Benutzerkonten aufgelistet, sortiert nach UPN, jeweils jeweils einem Bildschirm. Sie können das Cmdlet **Where** verwenden, um die Liste zu filtern. Hier ein Beispiel:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Mit diesem Befehl werden nur die Benutzerkonten angezeigt, deren Anzeigename mit „John“ beginnt.
    
- Die Rolle, die Sie zuweisen möchten
    
    Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Nachdem Sie über den UPN des Kontos und den Namen der Rolle verfügen, verwenden Sie diese Befehle, um dem Konto die Rolle zuzuweisen:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Kopieren Sie die Befehle, und fügen Sie sie in Editor ein. Für die **$upnName** -und **$roleName** -Variablen. Ersetzen Sie den Beschreibungstext durch ihre Werte. Entfernen Sie die \< and > Zeichen, aber halten Sie die Anführungszeichen. Fügen Sie die geänderten Zeilen in Microsoft Azure Active Directory Modul für Windows PowerShell Fenster ein, um Sie auszuführen. Alternativ können Sie die Windows PowerShell ISE verwenden.
  
Hier ist ein Beispiel für eine abgeschlossene Befehlsgruppe:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Mehrere Rollenänderungen

Ermitteln Sie bei mehreren Rollenänderungen die folgenden Informationen:
  
- Die Benutzerkonten, die Sie konfigurieren möchten. Sie können die Methoden im vorherigen Abschnitt verwenden, um die Gruppe von Anzeigenamen oder UPNs zu sammeln.
    
- Rollen, die Sie jedem Benutzerkonto zuweisen möchten. Um die Liste der verfügbaren Rollen anzuzeigen, die Benutzerkonten zugeordnet werden können, verwenden Sie den folgenden Befehl:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Erstellen Sie als nächstes eine CSV-Textdatei (Comma-Separated Value) mit den Feldern Anzeigename oder UPN-und Rollenname. Sie können dies problemlos in Microsoft Excel tun.

Hier sehen Sie ein Beispiel für Anzeigenamen:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Geben Sie anschließend den Speicherort der CSV-Datei an, und führen Sie die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Hier ist ein Beispiel für UPNs:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Geben Sie anschließend den Speicherort der CSV-Datei an, und führen Sie die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Siehe auch

- [Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
