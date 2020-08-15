---
title: Deaktivieren des Zugriffs auf Microsoft 365-Dienste mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um den Zugriff auf Microsoft 365-Dienste für Benutzer zu deaktivieren.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690508"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Deaktivieren des Zugriffs auf Microsoft 365-Dienste mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn einem Microsoft 365-Konto eine Lizenz aus einem Lizenzierungs Plan zugewiesen wird, werden dem Benutzer die Microsoft 365-Dienste von dieser Lizenz zur Verfügung gestellt. Sie können jedoch die Microsoft 365-Dienste steuern, auf die der Benutzer zugreifen kann. Beispielsweise können Sie den Zugriff darauf deaktivieren, auch wenn die Lizenz den Zugriff auf den SharePoint Online Dienst zulässt. Sie können PowerShell verwenden, um den Zugriff auf eine beliebige Anzahl von Diensten für einen bestimmten Lizenzierungs Plan für zu deaktivieren:

- ein einzelnes Konto
- eine Gruppe von Konten
- Alle Konten in Ihrer Organisation.

>[!Note]
>Es gibt Microsoft 365-Dienstabhängigkeiten, die verhindern können, dass Sie einen bestimmten Dienst deaktivieren, wenn andere Dienste davon abhängig sind.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Verwenden Sie anschließend diesen Befehl, um die verfügbaren Lizenzierungs Pläne anzuzeigen, die auch als AccountSkuIds bezeichnet werden:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).
    
Informationen zu den vor-und nach Ergebnissen der Verfahren in diesem Thema finden Sie unter [View Account License and Servicedetails with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).
    
Ein PowerShell-Skript steht zur Verfügung, das die in diesem Thema erläuterten Verfahren automatisiert. Insbesondere können Sie mit dem Skriptdienste in Ihrer Microsoft 365-Organisation anzeigen und deaktivieren, einschließlich Sway. Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Sway mit PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Deaktivieren bestimmter Microsoft 365-Dienste für bestimmte Benutzer für einen bestimmten Lizenzierungs Plan
  
Führen Sie die folgenden Schritte aus, um eine bestimmte Gruppe von Microsoft 365-Diensten für Benutzer für einen bestimmten Lizenzierungs Plan zu deaktivieren:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Schritt 1: Identifizieren der unerwünschten Dienste im Lizenzierungs Plan mithilfe der folgenden Syntax:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

Im folgenden Beispiel wird ein **licenseoptions** -Objekt erstellt, das die Office-und SharePoint Online-Dienste im Lizenzierungs Plan mit dem Namen `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3) deaktiviert.
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Schritt 2: Verwenden Sie das **licenseoptions** -Objekt aus Schritt 1 für einen oder mehrere Benutzer.
    
Wenn Sie ein neues Konto zu erstellen möchten, für das die Dienste deaktiviert sind, verwenden Sie die folgende Syntax:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

Im folgenden Beispiel wird ein neues Konto für Allie Bellew erstellt, das die Lizenz zuweist und die in Schritt 1 beschriebenen Dienste deaktiviert.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Weitere Informationen zum Erstellen von Benutzerkonten in PowerShell für Microsoft 365 finden Sie unter [Erstellen von Benutzerkonten mit PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
Verwenden Sie die folgende Syntax, um die Dienste für einen vorhandenen lizenzierten Benutzer zu deaktivieren:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

In diesem Beispiel werden die Dienste für den Benutzer „BelindaN@litwareinc.com“ deaktiviert.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Um die in Schritt 1 beschriebenen Dienste für alle vorhandenen lizenzierten Benutzer zu deaktivieren, geben Sie den Namen Ihres Microsoft 365-Plans in der Anzeige des Cmdlets **Get-MsolAccountSku** (wie **litwareinc: ENTERPRISEPACK**) ein, und führen Sie dann die folgenden Befehle aus:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Wenn Sie das Cmdlet **Get-MsolUser** ohne den Parameter _all_ verwenden, werden nur die ersten 500-Benutzerkonten zurückgegeben.

Verwenden Sie eine der folgenden Methoden, um die Dienste für eine Gruppe von vorhandenen Benutzern zu deaktivieren und die Benutzer zu identifizieren:
    
**Methode 1. Filtern der Konten basierend auf einem vorhandenen Kontoattribut** 

Verwenden Sie hierzu die folgende Syntax:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

Im folgenden Beispiel werden die Dienste für Benutzer in der Vertriebsabteilung in den Vereinigten Staaten deaktiviert.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Methode 2: Verwenden einer Liste bestimmter Konten** 

Gehen Sie dazu folgendermaßen vor:
    
1. Erstellen Sie eine Textdatei wie die folgende, die in jeder Zeile ein Konto enthält:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   In diesem Beispiel lautet die Textdatei C: \\ My Documents \\Accounts.txt.
    
2. Führen Sie den folgenden Befehl aus:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Wenn Sie den Zugriff auf Dienste für mehrere Lizenzierungs Pläne deaktivieren möchten, wiederholen Sie die obigen Anweisungen für jeden Lizenzierungs Plan, um Folgendes sicherzustellen:

- Die Benutzerkonten wurden mit dem Lizenzierungs Plan versehen.
- Die zu deaktivierenden Dienste stehen im Lizenzierungs Plan zur Verfügung.

Informationen zum Deaktivieren von Microsoft 365-Diensten für Benutzer, während Sie Sie einem Lizenzierungs Plan zuweisen, finden Sie unter [Deaktivieren des Zugriffs auf Dienste beim Zuweisen von Benutzerlizenzen](disable-access-to-services-while-assigning-user-licenses.md).

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Zuweisen aller Dienste in einem Lizenzierungs Plan zu einem Benutzerkonto

Für Benutzerkonten, für die Dienste deaktiviert wurden, können Sie mit den folgenden Befehlen alle Dienste für einen bestimmten Lizenzierungs Plan aktivieren:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Verwandtes Thema

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
