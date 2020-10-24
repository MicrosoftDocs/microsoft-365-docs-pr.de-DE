---
title: Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell
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
description: Verwenden Sie PowerShell für Microsoft 365, um Eigenschaften für einzelne oder mehrere Benutzerkonten in Ihrem Microsoft 365-Mandanten zu konfigurieren.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754328"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können das Microsoft 365 Admin Center verwenden, um Eigenschaften für die Benutzerkonten Ihres Microsoft 365-Mandanten zu konfigurieren. In PowerShell können Sie dies auch tun, und einige andere Dinge, die Sie im Admin Center nicht tun können.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Verwenden Sie das Cmdlet "AzureADUser", um Eigenschaften für Benutzerkonten im Azure Active Directory PowerShell for Graph [**-**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) Modul zu konfigurieren, und geben Sie die Eigenschaften an, die festgelegt oder geändert werden sollen.

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Sie identifizieren das Konto mit dem Parameter *-objectID* und legen oder ändern bestimmte Eigenschaften mithilfe zusätzlicher Parameter. Im folgenden finden Sie eine Liste der gebräuchlichsten Parameter:
  
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
    
- -UsageLocation " \<2-character country or region code> "
    
    Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).
    
Weitere Parameter finden Sie unter [festlegen-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .

>[!Note]
>Bevor Sie einem Benutzerkonto Lizenzen zuweisen können, müssen Sie einen Verwendungs Speicherort zuweisen.
>

Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
1. Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).
    
1. Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.

1. Jeweils auf einem Bildschirm anzeigen (**More**).
    
Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzuzeigen. Füllen Sie die *$username* Variable aus, und entfernen Sie die \< and > Zeichen:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigenamen " *Caleb Sills*" angezeigt.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mithilfe einer *$UPN* Variablen können Sie Änderungen an einzelnen Konten basierend auf Ihrem Anzeigenamen vornehmen. Hier ist ein Beispiel, das den Verwendungsstandort von *Belinda Newman*auf Frankreich festlegt. Sie gibt jedoch Ihren Anzeigenamen anstelle des Benutzerprinzipalnamens an:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination aus den Cmdlets **Get-AzureADUser** und **setAzureADUser** verwenden. Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in *Frankreich*geändert:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
1. Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den Cmdlets " **Get-AzureADUser**", " **Where**" und " **Sets-AzureADUser** " verwenden. Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich*geändert:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
1.  Suchen Sie alle Benutzerkonten, deren *Abteilungs* Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).
    
1. Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Verwenden Sie das Cmdlet "MsolUser", um Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory **-** Modul für Windows PowerShell zu konfigurieren, und geben Sie die Eigenschaften an, die festgelegt oder geändert werden sollen.

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell Core unterstützt das Microsoft Azure Active Directory Modul für Windows PowerShell Modul und Cmdlets mit *MSOL* nicht in Ihrem Namen. Führen Sie diese Cmdlets aus Windows PowerShell aus.
>

### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Um Eigenschaften für ein bestimmtes Benutzerkonto zu konfigurieren, verwenden Sie das Cmdlet " [**MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) ", und geben Sie die Eigenschaften an, die festgelegt oder geändert werden sollen. 

Sie identifizieren das Konto mit dem Parameter " *-userPrincipalName* " und legen oder ändern bestimmte Eigenschaften mithilfe zusätzlicher Parameter. Im folgenden finden Sie eine Liste der gebräuchlichsten Parameter.
  
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
    
- -UsageLocation " \<2-character country or region code> "
    
    Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).
    
Weitere Parameter finden Sie unter [festlegen-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).

Um die Benutzerprinzipalnamen aller Benutzer anzuzeigen, führen Sie den folgenden Befehl aus:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Rufen Sie alle Informationen für die Benutzerkonten ab (**Get-MsolUser**), und senden Sie es an den nächsten Befehl ( **|** ).
    
1. Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).
    
1. Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.
    
1. Jeweils auf einem Bildschirm anzeigen (**More**).
    
Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzuzeigen. Füllen Sie die *$username* Variable aus, und entfernen Sie die \< and > Zeichen.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipal Name für den Benutzernamens Caleb Sills angezeigt:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mithilfe einer *$UPN* Variablen können Sie Änderungen an einzelnen Konten basierend auf Ihrem Anzeigenamen vornehmen. Hier ist ein Beispiel, das den Verwendungs Speicherort von *Belinda Newman*auf *Frankreich*festlegt, jedoch Ihren Anzeigenamen anstelle des Benutzerprinzipalnamens angibt:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Verwenden Sie eine Kombination aus den Cmdlets **Get-MsolUser** und **setMsolUser** , um die Eigenschaften für alle Benutzer zu ändern. Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in *Frankreich*geändert:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Rufen Sie alle Informationen für die Benutzerkonten ab (**Get-MsolUser**), und senden Sie Sie an den nächsten Befehl ( **|** ).
    
1. Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den Cmdlets " **Get-MsolUser**", " **Where**" und " **Sets-MsolUser** " verwenden. Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich*geändert:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Rufen Sie alle Informationen für die Benutzerkonten ab (**Get-MsolUser**), und senden Sie Sie an den nächsten Befehl ( **|** ).
    
1. Suchen Sie nach allen Benutzerkonten, deren *Abteilungs* Eigenschaft auf "Buchhaltung" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).
    
1. Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
