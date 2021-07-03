---
title: Blockieren Microsoft 365 Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Verwenden von PowerShell zum Blockieren und Aufheben des Zugriffs auf Microsoft 365 Konten.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287221"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Blockieren Microsoft 365 Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie den Zugriff auf ein Microsoft 365 Konto blockieren, verhindern Sie, dass jemand das Konto verwendet, um sich anzumelden und auf die Dienste und Daten in Ihrer Microsoft 365 Organisation zuzugreifen. Sie können PowerShell verwenden, um den Zugriff auf einzelne oder mehrere Benutzerkonten zu blockieren.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)her.

### <a name="block-access-to-individual-user-accounts"></a>Zugriff auf einzelne Benutzerkonten blockieren

Verwenden Sie die folgende Syntax, um ein einzelnes Benutzerkonto zu blockieren:

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Der Parameter *"-ObjectID"* im Cmdlet **"Set-AzureAD"** akzeptiert entweder den Anmeldenamen des Kontos, der auch als Benutzerprinzipalname bezeichnet wird, oder die Objekt-ID des Kontos.

In diesem Beispiel wird der Zugriff auf das Benutzerkonto *fabricec@litwareinc.com* blockiert.

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Führen Sie zum Aufheben der Blockierung dieses Benutzerkontos den folgenden Befehl aus:

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Verwenden Sie die folgenden Befehle, um den UPN des Benutzerkontos basierend auf dem Anzeigenamen des Benutzers anzuzeigen:

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

In diesem Beispiel wird der UpN des Benutzerkontos für den Benutzer  *Caleb Sills* angezeigt.

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Verwenden Sie die folgenden Befehle, um ein Konto basierend auf dem Anzeigenamen des Benutzers zu blockieren:

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Verwenden Sie den folgenden Befehl, um den Sperrstatus eines Benutzerkontos zu überprüfen:

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Blockieren mehrerer Benutzerkonten

Um den Zugriff für mehrere Benutzerkonten zu blockieren, erstellen Sie eine Textdatei mit einem Konto-Anmeldenamen in jeder Zeile wie folgt:

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

In den folgenden Befehlen lautet die Beispieltextdatei *"C:\My Documents\Accounts.txt".* Ersetzen Sie diesen Dateinamen durch den Pfad und den Dateinamen ihrer Textdatei.

Um den Zugriff auf die in der Textdatei aufgelisteten Konten zu blockieren, führen Sie den folgenden Befehl aus:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

Führen Sie den folgenden Befehl aus, um die Blockierung der in der Textdatei aufgeführten Konten aufzuheben:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)her.

### <a name="block-individual-user-accounts"></a>Blockieren einzelner Benutzerkonten

Verwenden Sie die folgende Syntax, um den Zugriff für ein einzelnes Benutzerkonto zu blockieren:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets, die *Msol* im Namen haben. Sie müssen diese Cmdlets über Windows PowerShell ausführen.

In diesem Beispiel wird der Zugriff auf das Benutzerkonto *fabricec \@ litwareinc.com* blockiert.

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Führen Sie zum Aufheben der Blockierung des Benutzerkontos den folgenden Befehl aus:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Führen Sie den folgenden Befehl aus, um den Blockierten Status eines Benutzerkontos zu überprüfen:

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Zugriff für mehrere Benutzerkonten blockieren

Erstellen Sie zunächst eine Textdatei mit einem Konto in jeder Zeile wie folgt:

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

In den folgenden Befehlen lautet die Beispieltextdatei *"C:\My Documents\Accounts.txt".* Ersetzen Sie diesen Dateinamen durch den Pfad und den Dateinamen ihrer Textdatei.

Führen Sie den folgenden Befehl aus, um den Zugriff auf die in der Textdatei aufgeführten Konten zu blockieren:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Um den Zugriff auf die in der Textdatei aufgelisteten Konten wieder freizugeben, führen Sie den folgenden Befehl aus:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
