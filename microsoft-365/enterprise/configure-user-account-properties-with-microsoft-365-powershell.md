---
title: Konfigurieren von Microsoft 365-Benutzerkontoeigenschaften mit PowerShell
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
description: Verwenden Sie PowerShell für Microsoft 365, um Eigenschaften einzelner oder mehrerer Benutzerkonten in Ihrem Microsoft 365-Mandanten zu konfigurieren.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911084"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Konfigurieren von Microsoft 365-Benutzerkontoeigenschaften mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können das Microsoft 365 Admin Center verwenden, um Eigenschaften für die Benutzerkonten Ihres Microsoft 365-Mandanten zu konfigurieren. In PowerShell können Sie dies auch tun, sowie einige andere Dinge, die Sie im Admin Center nicht tun können.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten im Azure Active Directory PowerShell für Graph-Modul das [**Cmdlet Set-AzureADUser,**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) und geben Sie die eigenschaften an, die festgelegt oder geändert werden müssen.

Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Sie identifizieren das Konto mit dem *-ObjectID-Parameter* und legen bestimmte Eigenschaften mithilfe zusätzlicher Parameter fest oder ändern sie. Hier ist eine Liste der gängigsten Parameter:
  
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
    
- -UsageLocation " \<2-character country or region code> " "
    
    Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).
    
Weitere Parameter finden Sie unter [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .

>[!Note]
>Bevor Sie einem Benutzerkonto Lizenzen zuweisen können, müssen Sie einen Verwendungsspeicherort zuweisen.
>

Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Dieser Befehl wies PowerShell an:
  
1. Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).
    
1. Sortieren Sie die Liste der Benutzerprinzipalnamen alphabetisch (**Sortieren von UserPrincipalName**) und senden Sie sie an den nächsten Befehl ( **|** ).
    
1. Zeigt nur die User Principal Name-Eigenschaft für jedes Konto an (**Select UserPrincipalName**).

1. Jeweils auf einem Bildschirm anzeigen (**More**).
    
Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf seinem Anzeigenamen (Vor- und Nachname) anzuzeigen. Füllen Sie die *$userName* aus, und entfernen Sie die \< and > Zeichen:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigenamen *Caleb Sills angezeigt.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mithilfe einer *$upn* können Sie änderungen an einzelnen Konten basierend auf ihrem Anzeigenamen vornehmen. Hier ist ein Beispiel, das den Verwendungsspeicherort von *Belinda Newman* auf Frankreich legt. Sie gibt jedoch ihren Anzeigenamen anstelle ihres Benutzerprinzipalnamens an:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Zum Ändern von Eigenschaften für alle Benutzer können Sie eine Kombination der **Cmdlets Get-AzureADUser** und **Set-AzureADUser** verwenden. Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in *Frankreich geändert:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Dieser Befehl wies PowerShell an:
  
1. Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).
    
1. Legen Sie den Benutzerspeicherort auf Frankreich (**Set-AzureADUser -UsageLocation "FR" ) festgelegt.**
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern von Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den **Cmdlets Get-AzureADUser**, **Where** und **Set-AzureADUser** verwenden. Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich geändert:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Dieser Befehl wies PowerShell an:
  
1. Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).
    
1.  Suchen Sie alle Benutzerkonten, deren *Department-Eigenschaft* auf "Accounting" festgelegt ist (**Where {$_. Department -eq "Accounting"}**), und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).
    
1. Legen Sie den Benutzerspeicherort auf Frankreich (**Set-AzureADUser -UsageLocation "FR" ) festgelegt.**
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory-Modul für Windows PowerShell das **Cmdlet Set-MsolUser,** und geben Sie die eigenschaften an, die festgelegt oder geändert werden müssen.

Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt. Führen Sie diese Cmdlets über Windows PowerShell aus.
>

### <a name="change-properties-for-a-specific-user-account"></a>Ändern von Eigenschaften für ein bestimmtes Benutzerkonto

Verwenden Sie zum Konfigurieren von Eigenschaften für ein bestimmtes Benutzerkonto das [**Cmdlet Set-MsolUser,**](/previous-versions/azure/dn194136(v=azure.100)) und geben Sie die eigenschaften an, die festgelegt oder geändert werden müssen. 

Sie identifizieren das Konto mit dem *-UserPrincipalName-Parameter* und legen bestimmte Eigenschaften mithilfe zusätzlicher Parameter fest oder ändern sie. Hier finden Sie eine Liste der gängigsten Parameter.
  
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
    
- -UsageLocation " \<2-character country or region code> " "
    
    Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).
    
Weitere Parameter finden Sie unter [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).

Führen Sie den folgenden Befehl aus, um die Benutzerprinzipalnamen aller Benutzer zu sehen:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Dieser Befehl wies PowerShell an:
  
1. Alle Informationen für die Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).
    
1. Sortieren Sie die Liste der Benutzerprinzipalnamen alphabetisch (**Sortieren von UserPrincipalName**) und senden Sie sie an den nächsten Befehl ( **|** ).
    
1. Zeigt nur die User Principal Name-Eigenschaft für jedes Konto an (**Select UserPrincipalName**).
    
1. Jeweils auf einem Bildschirm anzeigen (**More**).
    
Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf seinem Anzeigenamen (Vor- und Nachname) anzuzeigen. Geben Sie *die* $userName ein, und entfernen Sie die \< and > Zeichen.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In diesem Beispiel wird der Benutzerprinzipalname für den Benutzer namens Caleb Sills angezeigt:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Mithilfe einer *$upn* können Sie änderungen an einzelnen Konten basierend auf ihrem Anzeigenamen vornehmen. Im Folgenden sehen Sie ein Beispiel, in dem der Verwendungsspeicherort von *Belinda Newman* auf *Frankreich* festgelegt wird, aber ihr Anzeigename und nicht ihr Benutzerprinzipalname angegeben wird:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändern von Eigenschaften für alle Benutzerkonten

Verwenden Sie zum Ändern von Eigenschaften für alle Benutzer eine Kombination aus **den Cmdlets Get-MsolUser** und **Set-MsolUser.** Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in *Frankreich geändert:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Dieser Befehl wies PowerShell an:
  
1. Alle Informationen für die Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).
    
1. Legen Sie den Benutzerspeicherort auf Frankreich (**Set-MsolUser -UsageLocation "FR" ) festgelegt.**
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändern von Eigenschaften für bestimmte Benutzerkonten

Zum Ändern von Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den **Cmdlets Get-MsolUser**, **Where** und **Set-MsolUser** verwenden. Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich geändert:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Dieser Befehl wies PowerShell an:
  
1. Alle Informationen für die Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).
    
1. Suchen Sie alle Benutzerkonten, deren *Department-Eigenschaft* auf "Accounting" festgelegt ist (**Where {$_. Department -eq "Accounting"}**) und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).
    
1. Legen Sie den Benutzerspeicherort auf Frankreich (**Set-MsolUser -UsageLocation "FR" ) festgelegt.**

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)