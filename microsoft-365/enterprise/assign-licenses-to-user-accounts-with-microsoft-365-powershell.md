---
title: Zuweisen Microsoft 365 Lizenzen zu Benutzerkonten mit PowerShell
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
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um eine Microsoft 365 nicht lizenzierten Benutzern zuzuordnen.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572621"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Zuweisen Microsoft 365 Lizenzen zu Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Benutzer können keine Microsoft 365 verwenden, bis ihrem Konto eine Lizenz aus einem Lizenzierungsplan zugewiesen wurde. Sie können PowerShell verwenden, um nicht lizenzierten Konten schnell Lizenzen zuzuordnen. 

Benutzerkonten muss zuerst ein Speicherort zugewiesen werden. Das Angeben eines Speicherorts ist ein erforderlicher Bestandteil des Erstellens eines neuen Benutzerkontos im [Microsoft 365 Admin Center](../admin/add-users/add-users.md). 

Für Konten, die mit Ihren lokalen Active Directory-Domänendiensten synchronisiert wurden, ist standardmäßig kein Speicherort angegeben. Sie können einen Speicherort für diese Konten konfigurieren:

- Das Microsoft 365 Admin Center
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - Das [Azure-Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active**  >  **Directory-Benutzer** > Benutzerkonto >   >  **Profilkontaktinformationen**  >  **Land oder Region**).

>[!Note]
>[Informationen zum Zuweisen von Lizenzen zu Benutzerkonten](../admin/manage/assign-licenses-to-users.md) mit dem Microsoft 365 Admin Center. Eine Liste der zusätzlichen Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](../admin/add-users/index.yml).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Als Nächstes listen Sie die Lizenzpläne für Ihren Mandanten mit diesem Befehl auf.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Als Nächstes erhalten Sie den Anmeldenamen des Kontos, dem Sie eine Lizenz hinzufügen möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt.

Stellen Sie als Nächstes sicher, dass dem Benutzerkonto ein Verwendungsspeicherort zugewiesen ist.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Wenn kein Verwendungsspeicherort zugewiesen ist, können Sie einen mit den folgenden Befehlen zuweisen:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Geben Sie schließlich den Namen der Benutzer-Anmeldung und den Lizenzplannamen an, und führen Sie diese Befehle aus.

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

Bitte beachten Sie, dass wir mit dem Veralteten dieses Moduls beginnen, wenn die Funktionalität dieses Moduls in der neueren Azure Active Directory [PowerShell für](/powershell/azuread/v2/azureactivedirectory) Graph verfügbar ist. Wir empfehlen Kunden, die neue PowerShell-Skripts erstellen, das neuere Modul anstelle dieses Moduls zu verwenden.

Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Führen Sie den Befehl aus, um die verfügbaren Lizenzierungspläne und die Anzahl der verfügbaren Lizenzen in den einzelnen `Get-MsolAccountSku` Plänen in Ihrer Organisation anzeigen zu können. Die Anzahl der verfügbaren Lizenzen in jedem Plan ist **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Weitere Informationen zu Lizenzierungsplänen, Lizenzen und Diensten finden Sie unter Anzeigen von Lizenzen und Diensten [mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Führen Sie diesen Befehl aus, um die nicht lizenzierten Konten in Ihrer Organisation zu finden.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Sie können Benutzerkonten nur Lizenzen zuweisen, für die die **UsageLocation-Eigenschaft** auf einen gültigen ISO 3166-1 alpha-2-Ländercode festgelegt ist. „US" steht zum Beispiel für die Vereinigten Staaten und „FR" für Frankreich. Einige Microsoft 365 sind in bestimmten Ländern nicht verfügbar. Weitere Informationen finden Sie unter [Informationen zu Lizenzbeschränkungen](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Führen Sie diesen Befehl aus, um Konten zu finden, die keinen **UsageLocation-Wert** haben.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Führen Sie diesen Befehl aus, um den **UsageLocation-Wert** für ein Konto zu festlegen.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Zum Beispiel:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Bei Verwendung des **Get-MsolUser**-Cmdlets ohne den **-All**-Parameter werden nur die ersten 500 Konten zurückgegeben.

### <a name="assigning-licenses-to-user-accounts"></a>Zuweisen von Lizenzen zu Benutzerkonten
    
Verwenden Sie den folgenden Befehl in PowerShell, um einem Benutzer eine Lizenz zuzuordnen.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

In diesem Beispiel wird dem nicht lizenzierten Benutzer belindan eine Lizenz aus dem **Lizenzplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) **\@ litwareinc.com:**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Führen Sie diesen Befehl aus, um allen nicht lizenzierten Benutzern eine Lizenz zuzuordnen.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Sie können einem Benutzer nicht mehrere Lizenzen aus dem gleichen Lizenzierungsplan zuweisen. Wenn Sie nicht über genügend verfügbare Lizenzen verfügen, werden die Lizenzen den Benutzern in der Reihenfolge zugewiesen, in der sie von dem **Get-MsolUser**-Cmdlet zurückgegeben werden, bis alle Lizenzen vergeben sind.
>

In diesem Beispiel werden Lizenzen aus dem **lizenzierten Lizenzplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) allen nicht lizenzierten Benutzern zugewiesen:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

In diesem Beispiel werden dieselben Lizenzen nicht lizenzierten Benutzern in der Vertriebsabteilung in den USA zugewiesen:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Verschieben eines Benutzers in ein anderes Abonnement (Lizenzplan) mit dem Azure Active Directory PowerShell für Graph Modul

Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Als Nächstes erhalten Sie den Anmeldenamen des Benutzerkontos, für das Sie Switchabonnements verwenden möchten, auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt.

Listen Sie als Nächstes die Abonnements (Lizenzpläne) für Ihren Mandanten mit diesem Befehl auf.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Listen Sie als Nächstes die Abonnements auf, über die das Benutzerkonto derzeit mit diesen Befehlen verfügt.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifizieren Sie das Abonnement, über das der Benutzer derzeit verfügt (das FROM-Abonnement) und das Abonnement, in das der Benutzer sich bewegt (das TO-Abonnement).

Geben Sie schließlich die Namen des TO- und FROM-Abonnements (SKU-Teilnummern) an, und führen Sie diese Befehle aus.

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

Sie können die Änderung des Abonnements für das Benutzerkonto mit diesen Befehlen überprüfen.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Benutzerkonten, Lizenzen und Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
