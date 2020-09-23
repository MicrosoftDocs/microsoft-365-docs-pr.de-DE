---
title: Erstellen von Microsoft 365-Benutzerkonten mit PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell Benutzerkonten oder mehrere Microsoft 365-Benutzerkonten erstellen.
ms.openlocfilehash: 00ae8806e786eada092704febd65c72c72382788
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235594"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Erstellen von Microsoft 365-Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können PowerShell für Microsoft 365 zum effizienten Erstellen von Benutzerkonten verwenden, insbesondere für mehrere Benutzerkonten. Wenn Sie Benutzerkonten in PowerShell erstellen, sind bestimmte Kontoeigenschaften immer erforderlich. Andere Eigenschaften sind nicht erforderlich, um das Konto zu erstellen, sind aber dennoch wichtig. Diese Eigenschaften werden in der folgenden Tabelle beschrieben:
  
|**Eigenschaftenname**|**Erforderlich?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anzeigename** <br/> |Ja  <br/> |Dies ist der Anzeigename, der in Microsoft 365-Diensten verwendet wird. Zum Beispiel „Caleb Sills".  <br/> |
|**UserPrincipalName** <br/> |Ja  <br/> |Hierbei handelt es sich um den Kontonamen, der für die Anmeldung bei Microsoft 365-Diensten verwendet wird. Zum Beispiel „CalebS@contoso.onmicrosoft.com".  <br/> |
|**FirstName** <br/> |Nein  <br/> ||
|**Nachname** <br/> |Nein  <br/> ||
|**LicenseAssignment** <br/> |Nein  <br/> |Hierbei handelt es sich um den Lizenzierungs Plan (auch als Lizenzplan oder SKU bezeichnet), von dem eine verfügbare Lizenz dem Benutzerkonto zugewiesen wird. Die Lizenz definiert die Microsoft 365-Dienste, die für das Konto verfügbar sind. Sie müssen einem Benutzer beim Erstellen des Kontos keine Lizenz zuweisen, aber für das Konto ist eine Lizenz für den Zugriff auf Microsoft 365-Dienste erforderlich. Sie haben 30 Tage Zeit, um das Benutzerkonto zu lizenzieren, nachdem Sie es erstellt haben. |
|**Password** <br/> |Nein  <br/> | Wenn Sie kein Kennwort angeben, wird dem Benutzerkonto ein zufälliges Kennwort zugewiesen, und das Kennwort wird in den Ergebnissen des Befehls angezeigt. Wenn Sie ein Kennwort angeben, muss es aus 8 bis 16 ASCII-Textzeichen aus drei der folgenden Kategorien bestehen: Kleinbuchstaben, Großbuchstaben, Zahlen oder Symbole. <br/> |
|**UsageLocation** <br/> |Nein  <br/> |Dies ist ein gültiger ISO 3166-1-Alpha-2-Ländercode. „US" steht zum Beispiel für die Vereinigten Staaten und „FR" für Frankreich. Es ist wichtig, diesen Wert anzugeben, da einige Microsoft 365-Dienste in bestimmten Ländern nicht verfügbar sind, sodass Sie einem Benutzerkonto keine Lizenz zuweisen können, es sei denn, das Konto hat diesen Wert konfiguriert. Weitere Informationen finden Sie unter [Informationen zu Lizenzbeschränkungen](https://go.microsoft.com/fwlink/p/?LinkId=691730).  <br/> |

>[!Note]
>[Erfahren Sie, wie Sie Benutzerkonten](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) mit dem Microsoft 365 Admin Center erstellen. Eine Liste mit weiteren Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Nachdem Sie eine Verbindung hergestellt haben, verwenden Sie die folgende Syntax, um ein einzelnes Konto zu erstellen:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

In diesem Beispiel wird ein Konto für den US-amerikanischen Benutzer mit dem Namen „Caleb Sills“ erstellt:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="create-an-individual-user-account"></a>Erstellen eines einzelnen Benutzerkontos

Verwenden Sie die folgende Syntax, um ein einzelnes Konto zu erstellen:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Mit dem folgenden Befehl erhalten Sie eine Liste der Namen der Lizenzierungspläne:

````powershell
Get-MsolAccountSku
````

In diesem Beispiel wird ein Konto für den US-amerikanischen Benutzer mit dem Namen „Caleb Sills" erstellt und eine Lizenz aus dem `contoso:ENTERPRISEPACK`-Lizenzierungsplan (Office 365 Enterprise E3) zugewiesen.
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Erstellen mehrerer Benutzerkonten

1. Erstellen Sie eine durch Kommata getrennte Wertedatei (CSV), die die erforderlichen Informationen zum Benutzerkonto enthält. Beispiel:
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
>Die Spaltennamen und ihre Reihenfolge in der ersten Zeile der CSV-Datei sind willkürlich, aber stellen Sie sicher, dass die Daten im Rest der Datei mit der Reihenfolge der Spaltennamen übereinstimmen, und verwenden Sie die Spaltennamen für die Parameterwerte im PowerShell for Microsoft 365-Befehl.
    
2. Verwenden Sie die folgende Syntax:
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

In diesem Beispiel werden die Benutzerkonten aus der Datei mit dem Namen „C:\My Documents\NewAccounts.csv“ erstellt, und die Ergebnisse werden in der Datei mit dem Namen „C:\My Documents\NewAccountResults.csv“ protokolliert.
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. Die Ergebnisse können Sie in der Ausgabedatei überprüfen. Es wurden keine Kennwörter angegeben, sodass die zufälligen Kennwörter, die von Microsoft 365 generiert wurden, in der Ausgabedatei angezeigt werden.
    
## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
