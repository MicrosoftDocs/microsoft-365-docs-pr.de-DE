---
title: Zuweisen Microsoft 365 Lizenzen für Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um nicht lizenzierten Benutzern eine Microsoft 365 Lizenz zuzuweisen.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572621"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Zuweisen Microsoft 365 Lizenzen für Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Benutzer können keine Microsoft 365 Dienste verwenden, bis ihrem Konto eine Lizenz aus einem Lizenzierungsplan zugewiesen wurde. Sie können PowerShell verwenden, um Lizenzen schnell nicht lizenzierten Konten zuzuweisen. 

Benutzerkonten müssen zuerst einen Speicherort zugewiesen werden. Die Angabe eines Speicherorts ist ein erforderlicher Teil zum Erstellen eines neuen Benutzerkontos im [Microsoft 365 Admin Center](../admin/add-users/add-users.md). 

Für Konten, die von Ihren lokalen Active Directory-Domänendiensten synchronisiert werden, wurde standardmäßig kein Speicherort angegeben. Sie können einen Speicherort für diese Konten konfigurieren von:

- Das Microsoft 365 Admin Center
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - Das [Azure-Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active**  >  **Directory-Benutzer** > Benutzerkonto >   >  **Profilkontaktinformationen**  >  **Land oder Region**).

>[!Note]
>[Erfahren Sie, wie Sie Benutzerkonten](../admin/manage/assign-licenses-to-users.md) mit dem Microsoft 365 Admin Center Lizenzen zuweisen. Eine Liste zusätzlicher Ressourcen finden Sie unter Verwalten von [Benutzern und Gruppen](../admin/add-users/index.yml).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen [Sie](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)zunächst eine Verbindung zu Ihrem Microsoft 365 Mandanten her.
  

Listen Sie als Nächstes die Lizenzpläne für Ihren Mandanten mit diesem Befehl auf.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Als Nächstes erhalten Sie den Anmeldenamen des Kontos, dem Sie eine Lizenz hinzufügen möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet.

Stellen Sie als Nächstes sicher, dass dem Benutzerkonto ein Verwendungsspeicherort zugewiesen ist.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Wenn kein Verwendungsspeicherort zugewiesen ist, können Sie einen mit folgenden Befehlen zuweisen:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Geben Sie schließlich den Namen der Benutzeranmeldung und den Lizenzplannamen an, und führen Sie diese Befehle aus.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Bitte beachten Sie, dass wir damit beginnen, dieses Modul zu vernachdürfen, wenn die Funktionalität dieses Moduls in der neueren [Azure Active Directory PowerShell für Graph](/powershell/azuread/v2/azureactivedirectory) Modul verfügbar ist. Wir empfehlen Kunden, die neue PowerShell-Skripts erstellen, das neuere Modul anstelle dieses Moduls zu verwenden.

Stellen [Sie](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)zunächst eine Verbindung zu Ihrem Microsoft 365 Mandanten her.

Führen Sie den `Get-MsolAccountSku` Befehl aus, um die verfügbaren Lizenzpläne und die Anzahl der verfügbaren Lizenzen in jedem Plan in Ihrer Organisation anzuzeigen. Die Anzahl der verfügbaren Lizenzen in jedem Plan ist **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Weitere Informationen zu Lizenzierungsplänen, Lizenzen und Diensten finden Sie unter Anzeigen von [Lizenzen und Diensten mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Führen Sie diesen Befehl aus, um die nicht lizenzierten Konten in Ihrer Organisation zu finden.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Sie können Nur Benutzerkonten Lizenzen zuweisen, deren **UsageLocation-Eigenschaft** auf einen gültigen ISO 3166-1 alpha-2-Ländercode festgelegt ist. „US" steht zum Beispiel für die Vereinigten Staaten und „FR" für Frankreich. Einige Microsoft 365 Dienste sind in bestimmten Ländern nicht verfügbar. Weitere Informationen finden Sie unter [Informationen zu Lizenzbeschränkungen](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Führen Sie diesen Befehl aus, um Konten zu finden, die keinen **UsageLocation-Wert** haben.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Führen Sie diesen Befehl aus, um den **UsageLocation-Wert** für ein Konto festzulegen.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Zum Beispiel:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Bei Verwendung des **Get-MsolUser**-Cmdlets ohne den **-All**-Parameter werden nur die ersten 500 Konten zurückgegeben.

### <a name="assigning-licenses-to-user-accounts"></a>Zuweisen von Lizenzen zu Benutzerkonten
    
Um einem Benutzer eine Lizenz zuzuweisen, verwenden Sie den folgenden Befehl in PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

In diesem Beispiel wird dem nicht lizenzierten Benutzer eine Lizenz aus dem **Lizenzierungsplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) **\@ zugewiesen, litwareinc.com:**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Führen Sie diesen Befehl aus, um allen nicht lizenzierten Benutzern eine Lizenz zuzuweisen.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Sie können einem Benutzer nicht mehrere Lizenzen aus dem gleichen Lizenzierungsplan zuweisen. Wenn Sie nicht über genügend verfügbare Lizenzen verfügen, werden die Lizenzen den Benutzern in der Reihenfolge zugewiesen, in der sie von dem **Get-MsolUser**-Cmdlet zurückgegeben werden, bis alle Lizenzen vergeben sind.
>

In diesem Beispiel werden allen nicht lizenzierten Benutzern Lizenzen aus dem **Lizenzierungsplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) zugewiesen:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

In diesem Beispiel werden dieselben Lizenzen nicht lizenzierten Benutzern in der Vertriebsabteilung in den USA zugewiesen:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Verschieben eines Benutzers in ein anderes Abonnement (Lizenzplan) mit der Azure Active Directory PowerShell für Graph Modul

Stellen [Sie](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)zunächst eine Verbindung zu Ihrem Microsoft 365 Mandanten her.
  
Als Nächstes erhalten Sie den Anmeldenamen des Benutzerkontos, für das Sie Abonnements wechseln möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet.

Listen Sie als Nächstes die Abonnements (Lizenzpläne) für Ihren Mandanten mit diesem Befehl auf.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Führen Sie als Nächstes die Abonnements auf, die das Benutzerkonto derzeit mit diesen Befehlen hat.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifizieren Sie das Abonnement, über das der Benutzer derzeit verfügt (das FROM-Abonnement) und das Abonnement, in das der Benutzer wechselt (das TO-Abonnement).

Geben Sie schließlich die Abonnementnamen TO und FROM (SKU-Teilenummern) an, und führen Sie diese Befehle aus.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

Mit diesen Befehlen können Sie die Änderung im Abonnement für das Benutzerkonto überprüfen.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Benutzerkonten, Lizenzen und Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
