---
title: Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Informationen zum Zuweisen von Lizenzen zu Benutzerkonten und zum gleichzeitigen deaktivieren bestimmter Dienstpläne mithilfe von PowerShell für Microsoft 365.
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690506"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Deaktivieren des Zugriffs auf Microsoft 365-Dienste beim Zuweisen von Benutzerlizenzen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365-Abonnements bieten Dienstpläne für einzelne Dienste. Microsoft 365-Administratoren müssen häufig bestimmte Pläne deaktivieren, wenn Sie Benutzern Lizenzen zuweisen. Mit den Anweisungen in diesem Artikel können Sie eine Microsoft 365-Lizenz zuweisen, während bestimmte Dienstpläne mithilfe von PowerShell für ein einzelnes Benutzerkonto oder mehrere Benutzerkonten deaktiviert werden.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

Als nächstes Listen Sie die Lizenz Pläne für Ihren Mandanten mit diesem Befehl auf.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Rufen Sie als nächstes den Anmeldenamen des Kontos ab, für das Sie eine Lizenz hinzufügen möchten, die auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird.

Kompilieren Sie als nächstes eine Liste der zu aktivierende Dienste. Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Geben Sie für den folgenden Befehlsblock den Benutzerprinzipalnamen des Benutzerkontos, die SKU-Teilnummer und die Liste der Dienstpläne ein, um den erläuternden Text und die Zeichen zu aktivieren und zu entfernen \< and > . Führen Sie anschließend die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Führen Sie als nächstes den folgenden Befehl aus, um Ihre aktuellen Abonnements anzuzeigen:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

In dem vom  `Get-MsolAccountSku`-Befehl zurückgegebenen Ergebnis gilt Folgendes:
  
- **AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format. Dies \<OrganizationName> ist der Wert, den Sie bei der Registrierung in Microsoft 365 angegeben haben und der für Ihre Organisation eindeutig ist. The \<Subscription> value is for a specific subscription. For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).
    
- **ActiveUnits** ist die Anzahl der Lizenzen, die Sie für das Abonnement erworben haben.
    
- **WarningUnits** gibt die Anzahl der Lizenzen in einem Abonnement an, die Sie nicht verlängert haben und die nach der 30-tägigen Toleranzperiode ablaufen werden.
    
- **ConsumedUnits** ist die Anzahl der Lizenzen, die Sie Benutzern für das Abonnement zugeordnet haben.
    
Beachten Sie die AccountSkuId für Ihr Microsoft 365-Abonnement, das die Benutzer enthält, die Sie lizenzieren möchten. Stellen Sie außerdem sicher, dass genügend Lizenzen zum Zuweisen verfügbar sind (subtrahieren Sie **ConsumedUnits** von **ActiveUnits** ).
  
Führen Sie als nächstes den folgenden Befehl aus, um die Details zu den Microsoft 365-Dienstplänen anzuzeigen, die in allen ihren Abonnements zur Verfügung stehen:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Anhand der vom Befehl zurückgegebenen Ausgabe können Sie bestimmen, welche Servicepläne Sie beim Zuweisen von Lizenzen an Benutzer deaktivieren möchten.
  
Es folgt eine unvollständige Liste von Dienstplänen und den dazugehörigen Microsoft 365-Diensten.

In der folgenden Tabelle sind die Microsoft 365-Dienstpläne und ihre Anzeigenamen für die am häufigsten verwendeten Dienste aufgeführt. Ihre individuelle Serviceplanliste sieht möglicherweise anders aus. 
  
|**Dienstplan**|**Beschreibung**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure-Rechteverwaltung (Rights Management, RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-Apps für Unternehmen *(zuvor mit dem Namen Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Plan 2  <br/> |
   
Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
   
Nachdem Sie festgelegt haben, dass AccountSkuId und die Servicepläne deaktiviert werden sollen, können Sie einem einzelnen oder mehreren Benutzern Lizenzen zuweisen.
  
### <a name="for-a-single-user"></a>Für einen einzelnen Benutzer

Geben Sie für einen einzelnen Benutzer den Benutzerprinzipalnamen des Benutzerkontos, das AccountSkuId und die Liste der Dienstpläne ein, um den erläuternden Text und die Zeichen zu deaktivieren und zu entfernen \< and > . Führen Sie anschließend die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Hier ein Beispiel für einen Befehlsblock für das Konto namens „belindan@contoso.com“, für contoso:ENTERPRISEPACK-Lizenz, und die zu deaktivierenden Servicepläne lauten: RMS_S_ENTERPRISE, SCHLINGERN, INTUNE_O365 und YAMMER_ENTERPRISE:
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>Für mehrere Benutzer

Erstellen Sie zum Ausführen dieser Aufgabe eine CSV-Textdatei mit den UserPrincipalName- und UsageLocation-Feldern. Hier ein Beispiel:
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Geben Sie als Nächstes den Speicherort für die CSV-Eingabe- und CSV-Ausgabedateien, die Konto-SKU-ID und die Liste der zu deaktivierenden Servicepläne ein, und führen Sie anschließend die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Dieser PowerShell-Befehlsblock:
  
- Zeigt den Benutzerprinzipalnamen für jeden Benutzer an.
    
- Weist jedem Benutzer die angepassten Lizenzen zu.
    
- Erstellt eine CSV-Datei mit allen Benutzern, die verarbeitet wurden, und zeigt den Status ihrer Lizenz an.
    
## <a name="see-also"></a>Siehe auch

[Deaktivieren des Zugriffs auf Microsoft 365-Dienste mit PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)
  
[Deaktivieren des Zugriffs auf Sway mit PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
