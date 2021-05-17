---
title: Verwenden der PowerShell-Cmdlets für zentrale Bereitstellung zum Verwalten von Add-Ins
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie die PowerShell-Cmdlets für die zentrale Bereitstellung, um Die Bereitstellung und Verwaltung von Office-Add-Ins für Microsoft 365 unterstützen.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924672"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Verwenden der PowerShell-Cmdlets für zentrale Bereitstellung zum Verwalten von Add-Ins

Als globaler Microsoft 365 können Sie Office-Add-Ins über das Feature für die zentrale Bereitstellung für Benutzer bereitstellen (siehe [Deploy Office Add-ins in the Admin Center](../admin/manage/manage-deployment-of-add-ins.md)). Zusätzlich zur Bereitstellung Office Add-Ins über das Microsoft 365 Admin Center können Sie auch Microsoft PowerShell verwenden. Installieren Sie [das O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

Öffnen Sie nach dem Herunterladen des Moduls ein reguläres Windows PowerShell, und führen Sie das folgende Cmdlet aus:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Verbinden verwenden Ihrer Administratoranmeldeinformationen

Bevor Sie die Cmdlets für die zentrale Bereitstellung verwenden können, müssen Sie sich anmelden.
  
1. Starten Sie PowerShell.
    
2. Verbinden powerShell mithilfe der Anmeldeinformationen Ihres Unternehmensadministrators. Führen Sie das folgende Cmdlet aus.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. Geben Sie auf der Seite **Anmeldeinformationen** eingeben Ihre Microsoft 365 Anmeldeinformationen für den globalen Administrator ein. Alternativ können Sie Ihre Anmeldeinformationen direkt in das Cmdlet eingeben. 
    
    Führen Sie das folgende Cmdlet aus, das Ihre Unternehmensadministratoranmeldeinformationen als PSCredential-Objekt anfordert.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Weitere Informationen zur Verwendung von PowerShell finden Sie [unter Verbinden to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md). 
  
## <a name="upload-an-add-in-manifest"></a>Hochladen eines Add-In-Manifests

Führen Sie **das Cmdlet New-OrganizationAdd-In** aus, um ein Add-In-Manifest aus einem Pfad hochzuladen, der entweder dateispeicherort oder URL sein kann. Das folgende Beispiel zeigt einen Dateispeicherort für den Wert des _ManifestPath-Parameters._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Sie können auch das **Cmdlet New-OrganizationAdd-In** ausführen, um ein Add-In hochzuladen und mithilfe des  _Parameters Members_ Benutzern oder Gruppen direkt zuzuordnen, wie im folgenden Beispiel gezeigt. Trennen Sie die E-Mail-Adressen von Mitgliedern durch ein Komma. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Hochladen ein Add-In aus dem Office Store

Führen Sie **das Cmdlet New-OrganizationAddIn** aus, um ein Manifest aus dem Office Store.
  
Im folgenden Beispiel gibt das **Cmdlet New-OrganizationAddIn** die AssetId für ein Add-In für einen Standort- und Inhaltsmarkt in den USA an.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Um den Wert für den _AssetId-Parameter_ zu bestimmen, können Sie ihn aus der URL der Office Store webseite für das Add-In kopieren. AssetIds beginnen immer mit "WA", gefolgt von einer Zahl. Im vorherigen Beispiel ist die Quelle für den AssetId-Wert von WA104099688 beispielsweise die url der Office Store Webseite für das Add-In: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Die Werte für den  _Parameter Locale_ und  _den Parameter ContentMarket_ sind identisch und geben das Land/die Region an, aus dem Sie das Add-In installieren möchten. Das Format ist en-US, fr-FR. usw. 
  
> [!NOTE]
> Add-Ins, die aus dem Office Store hochgeladen wurden, werden innerhalb weniger Tage automatisch aktualisiert, wenn das neueste Update auf dem Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Details zu einem Add-In erhalten

Führen Sie **das Cmdlet Get-OrganizationAddIn** wie unten gezeigt aus, um Details aller add-ins zu erhalten, die in den Mandanten hochgeladen wurden und die Produkt-ID eines Add-Ins enthalten.
  
```powershell
Get-OrganizationAddIn
```

Führen Sie **das Cmdlet Get-OrganizationAddIn** mit einem Wert für den  _ProductId-Parameter_ aus, um anzugeben, für welches Add-In Sie Details abrufen möchten. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Um vollständige Details aller Add-Ins sowie der zugewiesenen Benutzer und Gruppen zu erhalten, geben Sie die Ausgabe des **Cmdlets Get-OrganizationAddIn** an das cmdlet Format-List weiter, wie im folgenden Beispiel gezeigt.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Aktivieren oder Deaktivieren eines Add-Ins

Führen Sie das **Cmdlet Set-OrganizationAddIn** mit dem  _Parameter ProductId_ und dem  _Enabled-Parameter_ auf aus, um ein Add-In zu deaktivieren, damit benutzer und Gruppen, die ihm zugewiesen sind, keinen Zugriff mehr haben, wie im folgenden Beispiel  `$false` gezeigt.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Um ein Add-In wieder zu aktivieren, führen Sie dasselbe Cmdlet aus, bei dem der  _Parameter Enabled_ auf festgelegt  `$true` ist.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Hinzufügen oder Entfernen von Benutzern aus einem Add-In

Führen Sie zum Hinzufügen von Benutzern und Gruppen zu einem bestimmten **Add-In das Cmdlet Set-OrganizationAddInAssignments** mit den  _Parametern ProductId,_  _Add_ und  _Members_ aus. Trennen Sie die E-Mail-Adressen von Mitgliedern durch ein Komma. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Führen Sie dasselbe Cmdlet mit dem Parameter Remove aus, um Benutzer und Gruppen  _zu_ entfernen. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Um allen Benutzern im Mandanten ein Add-In zuzuordnen, führen Sie dasselbe Cmdlet mit dem  _Parameter AssignToEveryone_ aus, und der Wert ist auf  `$true` festgelegt.
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Um keinem Benutzer ein Add-In zuzuordnen und zu den zuvor zugewiesenen Benutzern und Gruppen zurückzuschalten, können Sie dasselbe Cmdlet ausführen und den  _Parameter AssignToEveryone_ deaktivieren, indem Sie dessen Wert auf  `$false` festlegen.
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Aktualisieren eines Add-Ins

Führen Sie zum Aktualisieren eines Add-Ins aus einem Manifest das **Cmdlet Set-OrganizationAddIn** mit den  _Parametern ProductId,_  _ManifestPath_ und  _Locale_ aus, wie im folgenden Beispiel gezeigt. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Add-Ins, die aus dem Office Store hochgeladen wurden, werden innerhalb weniger Tage automatisch aktualisiert, wenn das neueste Update auf dem Office Store. 
  
## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Führen Sie zum Löschen eines Add-Ins das **Cmdlet Remove-OrganizationAddIn** mit dem  _Parameter ProductId_ aus, wie im folgenden Beispiel gezeigt. 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>Detaillierte Hilfe für jedes Cmdlet erhalten

Mithilfe des Cmdlets Get-help können Sie detaillierte Hilfe für jedes Cmdlet finden. Das folgende Cmdlet enthält beispielsweise detaillierte Informationen zum Remove-OrganizationAddIn Cmdlet.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```