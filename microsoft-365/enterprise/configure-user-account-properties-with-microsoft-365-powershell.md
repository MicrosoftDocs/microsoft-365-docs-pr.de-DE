---
title: Konfigurieren Microsoft 365 Benutzerkontoeigenschaften mit PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Verwenden Sie PowerShell für Microsoft 365, um Eigenschaften einzelner oder mehrerer Benutzerkonten in Ihrem Microsoft 365 Mandanten zu konfigurieren.
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286009"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Konfigurieren Microsoft 365 Benutzerkontoeigenschaften mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können die Microsoft 365 Admin Center verwenden, um Eigenschaften für die Benutzerkonten Ihres Microsoft 365 Mandanten zu konfigurieren. In PowerShell können Sie dies auch tun und einige andere Aktionen, die Sie im Admin Center nicht ausführen können.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten im Azure Active Directory PowerShell für Graph Modul das Cmdlet [**"Set-AzureADUser",**](/powershell/module/azuread/set-azureaduser) und geben Sie die festzulegenden oder zu ändernden Eigenschaften an.

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)her.

### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Sie können das Konto mit dem Parameter *"-ObjectID"* identifizieren und bestimmte Eigenschaften mithilfe zusätzlicher Parameter festlegen oder ändern. Hier ist eine Liste der gängigsten Parameter:
  
- -Department „\<department name>"

- -DisplayName „<Vollständiger Benutzername>"

- -FacsimilieTelephoneNumber „\<fax number>"

- -GivenName „\<user first name>"

- -Surname „\<user last name>"

- -Mobile „\<mobile phone number>"

- -JobTitle „\<job title>"

- -PreferredLanguage „\<language>"

- -StreetAddress „\<street address>"

- -City „\<city name>"

- -State „<Bundesland/Kanton>"

- -PostalCode „\<postal code>"

- -Country „<Ländername>"

- -TelephoneNumber „<Telefon Büro>"

- -UsageLocation \<2-character country or region code> " "

    Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).

Weitere Parameter finden Sie unter ["Set-AzureADUser".](/powershell/module/azuread/set-azureaduser)

> [!NOTE]
> Bevor Sie einem Benutzerkonto Lizenzen zuweisen können, müssen Sie einen Verwendungsort zuweisen.

Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).

1. Sortieren Sie die Liste der Benutzerprinzipalnamen alphabetisch (**Sort UserPrincipalName**) und senden Sie sie an den nächsten Befehl ( **|** ).

1. Zeigt nur die Eigenschaft "Benutzerprinzipalname" für jedes Konto an (**UserPrincipalName auswählen).**

1. Jeweils auf einem Bildschirm anzeigen (**More**).

Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf seinem Anzeigenamen (Vor- und Nachname) anzuzeigen. Füllen Sie die *variable $userName* aus, und entfernen Sie die \< and > Zeichen:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigenamen *Caleb Sills* angezeigt.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mithilfe einer *$upn* Variablen können Sie Änderungen an einzelnen Konten basierend auf ihrem Anzeigenamen vornehmen. Hier ist ein Beispiel, in dem der Verwendungsort von *Belinda Newman* auf Frankreich festgelegt wird. Es gibt jedoch ihren Anzeigenamen anstelle des Benutzerprinzipalnamens an:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Zum Ändern der Eigenschaften für alle Benutzer können Sie eine Kombination der Cmdlets **"Get-AzureADUser"** und **"Set-AzureADUser"** verwenden. Im folgenden Beispiel wird der Verwendungsort für alle Benutzer in *Frankreich* geändert:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).

1. Legen Sie den Standort des Benutzers auf Frankreich fest (**Set-AzureADUser -UsageLocation "FR"**).

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination der Cmdlets **"Get-AzureADUser",** **"Where"** und **"Set-AzureADUser"** verwenden. Im folgenden Beispiel wird der Verwendungsort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich* geändert:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten ab (**Get-AzureADUser**), und senden Sie sie an den nächsten Befehl ( **|** ).

1.  Suchen Sie alle Benutzerkonten, deren *Abteilungseigenschaft* auf "Buchhaltung" festgelegt ist (**Wobei {$_. Department -eq "Accounting"}**), und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).

1. Legen Sie den Standort des Benutzers auf Frankreich fest (**Set-AzureADUser -UsageLocation "FR"**).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Um Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory Modul für Windows PowerShell zu konfigurieren, verwenden Sie das Cmdlet **"Set-MsolUser",** und geben Sie die festzulegenden oder zu ändernden Eigenschaften an.

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)her.
  
> [!NOTE]
> Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt. Führen Sie diese Cmdlets über Windows PowerShell aus.

### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Verwenden Sie zum Konfigurieren von Eigenschaften für ein bestimmtes Benutzerkonto das Cmdlet [**"Set-MsolUser",**](/previous-versions/azure/dn194136(v=azure.100)) und geben Sie die festzulegenden oder zu ändernden Eigenschaften an. 

Sie können das Konto mit dem Parameter *"-UserPrincipalName"* identifizieren und bestimmte Eigenschaften mithilfe zusätzlicher Parameter festlegen oder ändern. Hier ist eine Liste der gängigsten Parameter.
  
- -City „\<city name>"

- -Country „<Ländername>"

- -Department „\<department name>"

- -DisplayName „<Vollständiger Benutzername>"

- -Fax „\<fax number>"

- -FirstName „\<user first name>"

- -LastName „\<user last name>"

- -MobilePhone „\<mobile phone number>"

- -Office „<Standort des Büros>"

- -PhoneNumber „<Telefon Büro>"

- -PostalCode „\<postal code>"

- -PreferredLanguage „\<language>"

- -State „<Bundesland/Kanton>"

- -StreetAddress „\<street address>"

- -Title „\<title name>"

- -UsageLocation \<2-character country or region code> " "

    Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).

Weitere Parameter finden Sie unter ["Set-MsolUser".](/previous-versions/azure/dn194136(v=azure.100))

Führen Sie den folgenden Befehl aus, um die Benutzerprinzipalnamen aller Benutzer anzuzeigen:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen für die Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).

1. Sortieren Sie die Liste der Benutzerprinzipalnamen alphabetisch (**Sort UserPrincipalName**) und senden Sie sie an den nächsten Befehl ( **|** ).

1. Zeigt nur die Eigenschaft "Benutzerprinzipalname" für jedes Konto an (**UserPrincipalName auswählen).**

1. Jeweils auf einem Bildschirm anzeigen (**More**).

Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf seinem Anzeigenamen (Vor- und Nachname) anzuzeigen. Füllen Sie die *variable $userName* aus, und entfernen Sie die \< and > Zeichen.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für den Benutzer namens "Caleb Sills" angezeigt:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mithilfe einer *$upn* Variablen können Sie Änderungen an einzelnen Konten basierend auf ihrem Anzeigenamen vornehmen. Hier ist ein Beispiel, das den Verwendungsort von *Belinda Newman* auf *Frankreich* festlegt, aber den Anzeigenamen anstelle des Benutzerprinzipalnamens angibt:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Verwenden Sie eine Kombination der Cmdlets **"Get-MsolUser"** und **"Set-MsolUser",** um die Eigenschaften für alle Benutzer zu ändern. Im folgenden Beispiel wird der Verwendungsort für alle Benutzer in *Frankreich* geändert:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen für die Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).

1. Legen Sie den Standort des Benutzers auf Frankreich fest (**Set-MsolUser -UsageLocation "FR"**).

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination der Cmdlets **"Get-MsolUser",** **"Where"** und **"Set-MsolUser"** verwenden. Im folgenden Beispiel wird der Verwendungsort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich* geändert:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen für die Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).

1. Suchen Sie alle Benutzerkonten, deren *Abteilungseigenschaft* auf "Buchhaltung" festgelegt ist (**Wobei {$_. Department -eq "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl ( ) senden. **|**

1. Legen Sie den Standort des Benutzers auf Frankreich fest (**Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>Weitere Informationen:

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
