---
title: Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um die Eigenschaften einzelner oder mehrerer Benutzerkonten in Ihrem Microsoft 365-Mandanten zu konfigurieren.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690248"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Obwohl Sie das Microsoft 365 Admin Center zum Konfigurieren von Eigenschaften für die Benutzerkonten Ihres Microsoft 365-Mandanten verwenden können, können Sie auch PowerShell verwenden und einige Dinge tun, die das Microsoft 365 Admin Center nicht kann.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten mit der Azure Active Directory PowerShell das [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)-Cmdlet und geben Sie die Eigenschaften an, die Sie festlegen bzw. ändern möchten. 

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Sie identifizieren das Konto mit dem **-ObjectID**-Parameter und legen bestimmte Eigenschaften mit weiteren Parametern fest bzw. ändern diese. Nachfolgend ist eine Liste der am häufigsten verwendeten Parameter aufgeführt.
  
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
    
Informationen zu weiteren Parametern finden Sie unter [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0).


Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
- Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).
    
- Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.

- Jeweils auf einem Bildschirm anzeigen (**More**).
    
Mit diesem Befehl werden alle Ihre Konten aufgelistet. Wenn Sie den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzeigen möchten, geben Sie unten die **$username** Variable ein (Entfernen der \< and > Zeichen), und führen Sie dann die folgenden Befehle aus:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigename Caleb Sills angezeigt.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mit der **$upn**-Variable können Sie Änderungen an den einzelnen Konten basierend auf deren Anzeigenamen vornehmen. Hier ist ein Beispiel für das Festlegen des Verwendungsstandorts von Belinda Newman in Frankreich. Dabei wird Ihr Anzeigenamen anstatt Ihres Benutzerprinzipalnamens verwendet:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination der Cmdlets **Get-AzureADUser** und **et-AzureADUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in Frankreich geändert:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
- Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Um die Eigenschaften für einen bestimmten Satz von Benutzerkonten zu ändern, können Sie eine Kombination der Cmdlets **Get-AzureADUser**, **Where** und **Set-AzureADUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in der Buchhaltungsabteilung in Frankreich geändert:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
- Suchen Sie alle Benutzerkonten, deren Abteilungs Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).
    
- Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Um Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory Modul für Windows PowerShell zu konfigurieren, verwenden Sie das Cmdlet " **MsolUser** " und geben die Eigenschaften an, die festgelegt oder geändert werden sollen. 

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Verwenden Sie zum Konfigurieren der Eigenschaften für ein bestimmtes Benutzerkonto das [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))-Cmdlet und geben die Eigenschaften an, die festgelegt oder geändert werden sollen. 

Sie identifizieren das Konto mit dem **-UserPrincipalName**-Parameter und legen bestimmte Eigenschaften mit weiteren Parametern fest bzw. ändern diese. Nachfolgend ist eine Liste der am häufigsten verwendeten Parameter aufgeführt.
  
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
    
Informationen zu weiteren Parametern finden Sie unter [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).

Führen Sie den folgenden Befehl aus, um die Benutzerprinzipalnamen aller Benutzer anzuzeigen.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).
    
- Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).
    
- Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.
    
- Jeweils auf einem Bildschirm anzeigen (**More**).
    
Mit diesem Befehl werden alle Ihre Konten aufgelistet. Wenn Sie den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzeigen möchten, geben Sie unten die **$username** Variable ein (Entfernen der \< and > Zeichen), und führen Sie dann die folgenden Befehle aus:
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für den Benutzer namens Caleb Sills angezeigt.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mit der **$upn** -Variable können Sie Änderungen an den einzelnen Konten basierend auf deren Anzeigenamen vornehmen. Hier ist ein Beispiel für das Festlegen des Verwendungsstandorts von Belinda Newman in Frankreich. Dabei wird Ihr Anzeigenamen anstatt Ihres Benutzerprinzipalnamens verwendet:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination der Cmdlets **Get-MsolUser** und **Set-MsolUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in Frankreich geändert:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).
    
- Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie die Kombination aus den Cmdlets **Get-MsolUser**, **Where**und **setMsolUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in der Buchhaltungsabteilung in Frankreich geändert:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).
    
- Suchen Sie alle Benutzerkonten, deren Abteilungs Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).
    
- Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).
    

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
