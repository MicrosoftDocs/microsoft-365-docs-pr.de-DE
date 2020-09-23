---
title: Entfernen von Microsoft 365-Lizenzen aus Benutzerkonten mit PowerShell
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Erläutert die Verwendung von PowerShell zum Entfernen von Microsoft 365-Lizenzen, die zuvor Benutzern zugewiesen wurden.
ms.openlocfilehash: 7651f300dbf7a57ce163096d500401365e624663
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235454"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Entfernen von Microsoft 365-Lizenzen aus Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

>[!Note]
>[Hier erfahren Sie, wie Sie Lizenzen aus Benutzerkonten](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) mit dem Microsoft 365 Admin Center entfernen. Eine Liste mit weiteren Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Als nächstes Listen Sie die Lizenz Pläne für Ihren Mandanten mit diesem Befehl auf.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Rufen Sie als nächstes den Anmeldenamen des Kontos ab, für das Sie eine Lizenz entfernen möchten, auch bekannt als Benutzerprinzipalname (User Principal Name, UPN).

Geben Sie schließlich die Benutzeranmelde-und Lizenzplan Namen an, entfernen Sie die Zeichen "<" und ">", und führen Sie diese Befehle aus.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Wenn Sie alle Lizenzen für ein bestimmtes Benutzerkonto entfernen möchten, geben Sie den Anmeldenamen des Benutzers an, entfernen Sie die Zeichen "<" und ">", und führen Sie diese Befehle aus.

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
   
Informationen zum Lizenzierungsplan (**AccountSkuID**) in Ihrer Organisation finden Sie in den folgenden Themen:
    
  - [Anzeigen von Lizenzen und Diensten mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Anzeigen von Konto Lizenz-und Dienstdetails mit PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Bei Verwendung des **Get-MsolUser**-Cmdlets ohne den _-All_-Parameter werden nur die ersten 500 Konten zurückgegeben.
    
### <a name="removing-licenses-from-user-accounts"></a>Entfernen von Lizenzen aus Benutzerkonten

Verwenden Sie die folgende Syntax, um Lizenzen von einem vorhandenen Benutzerkonto zu entfernen:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

In diesem Beispiel wird die **litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3)-Lizenz aus dem Benutzerkonto BelindaN@litwareinc.com entfernt.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>Sie können das Cmdlet nicht verwenden `Set-MsolUserLicense` , um die Zuweisung von Benutzern von *abgebrochenen* Lizenzen aufzuheben. Sie müssen dies für jedes Benutzerkonto im Microsoft 365 Admin Center einzeln durchführen.
>

Wenn Sie alle Lizenzen aus einer Gruppe vorhandener lizenzierter Benutzer entfernen möchten, verwenden Sie eine der folgenden Methoden:
  
- **Filtern der Konten basierend auf einem vorhandenen Kontoattribut** Verwenden Sie dazu die folgende Syntax:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

In diesem Beispiel werden alle Lizenzen aus allen Benutzerkonten in der Vertriebsabteilung in den Vereinigten Staaten entfernt.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Verwenden einer Liste bestimmter Konten für eine bestimmte Lizenz** Führen Sie dazu die folgenden Schritte aus:
    
1. Erstellen und speichern Sie eine Textdatei wie die folgende, die in jeder Zeile ein Konto enthält:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. Verwenden Sie folgende Syntax:
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
In diesem Beispiel wird die **litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3)-Lizenz aus den in der Textdatei C:\My Documents\Accounts.txt definierten Benutzerkonten entfernt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Verwenden Sie die folgende Syntax, um alle Lizenzen aus allen vorhandenen Benutzerkonten zu entfernen:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Eine andere Möglichkeit zum Freigeben einer Lizenz besteht im Löschen des Benutzerkontos. Weitere Informationen finden Sie unter [Löschen und Wiederherstellen von Benutzerkonten mit PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).
  
## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

