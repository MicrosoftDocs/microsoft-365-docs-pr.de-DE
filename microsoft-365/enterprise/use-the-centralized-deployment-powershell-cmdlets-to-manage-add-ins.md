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
description: Verwenden Sie die PowerShell-Cmdlets für zentralisierte Bereitstellung, um die Bereitstellung und Verwaltung von Office-Add-Ins für Ihre Microsoft 365-Organisation zu erleichtern.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690773"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Verwenden der PowerShell-Cmdlets für zentrale Bereitstellung zum Verwalten von Add-Ins

Als globaler Administrator von Microsoft 365 können Sie Office-Add-Ins für Benutzer über das zentralisierte Bereitstellungsfeature bereitstellen (siehe [Deploy Office-Add-Ins im Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)). Neben der Bereitstellung von Office-Add-Ins über das Microsoft 365 Admin Center können Sie auch Microsoft PowerShell verwenden. Installieren [Sie das zentrale O365-Add-in-Bereitstellungsmodul für Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

Öffnen Sie nach dem Herunterladen des Moduls ein reguläres Windows PowerShell Fenster, und führen Sie das folgende Cmdlet aus:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Herstellen einer Verbindung mit Ihren Administratoranmeldeinformationen

Bevor Sie die Cmdlets für die zentrale Bereitstellung verwenden können, müssen Sie sich anmelden.
  
1. Starten Sie PowerShell.
    
2. Stellen Sie eine Verbindung mit PowerShell mithilfe ihrer Unternehmensadministrator Anmeldeinformationen her. Führen Sie das folgende Cmdlet aus.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. Geben Sie auf der Seite **Anmeldeinformationen eingeben** ihre globalen Administratoranmeldeinformationen von Microsoft 365 ein. Alternativ können Sie Ihre Anmeldeinformationen direkt in das Cmdlet eingeben. 
    
    Führen Sie das folgende Cmdlet aus, das die Anmeldeinformationen Ihres Unternehmens als PSCredential-Objekt angibt.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585). 
  
## <a name="upload-an-add-in-manifest"></a>Hochladen eines Add-in-Manifests

Führen Sie das Cmdlet **New-organisationadd-in** aus, um ein Add-in-Manifest aus einem Pfad hochzuladen, bei dem es sich entweder um einen Dateispeicherort oder eine URL handeln kann. Das folgende Beispiel zeigt einen Dateispeicherort für den Wert des  _ManifestPath_ -Parameters. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Sie können auch das **New-organisationadd-in-** Cmdlet ausführen, um ein Add-in hochzuladen und es Benutzern oder Gruppen direkt mithilfe des  _Members_ -Parameters zuzuweisen, wie im folgenden Beispiel gezeigt. Trennen Sie die e-Mail-Adressen von Elementen durch ein Komma. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Hochladen eines Add-Ins aus dem Office Store

Führen Sie das Cmdlet **New-OrganizationAddIn** aus, um ein Manifest aus dem Office Store hochzuladen.
  
Im folgenden Beispiel gibt das Cmdlet **New-OrganizationAddIn** die Asset-Nr für ein Add-in für einen Standort und einen Inhalts Markt in USA an.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Um den Wert für den Parameter  _Asset_ -Nr zu ermitteln, können Sie ihn aus der URL der Office Store Webseite für das Add-in kopieren. AssetIds beginnen immer mit "WA", gefolgt von einer Zahl. Im vorherigen Beispiel ist beispielsweise die Quelle für den Wert der WA104099688-Website die URL für das Add-in Office Store Webseite: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Die Werte für den Parameter  _locale_ und den Parameter  _ContentMarket_ sind identisch und geben das Land/die Region an, aus dem das Add-in installiert werden soll. Das Format lautet en-US, fr-fr. und so weiter. 
  
> [!NOTE]
> Aus dem Office Store hochgeladene Add-Ins werden automatisch innerhalb von ein paar Tagen nach der Verfügbarkeit des neuesten Updates im Office Store aktualisiert. 
  
## <a name="get-details-of-an-add-in"></a>Abrufen von Details eines Add-ins

Führen Sie das **Get-OrganizationAddIn-** Cmdlet wie unten beschrieben aus, um Details zu allen Add-Ins abzurufen, die in den Mandanten hochgeladen wurden und die Produkt-ID eines Add-Ins enthalten.
  
```powershell
Get-OrganizationAddIn
```

Führen Sie das Cmdlet **Get-OrganizationAddIn** mit einem Wert für den  _ProductID_ -Parameter aus, um anzugeben, für welches Add-in Sie Details abrufen möchten. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Um vollständige Informationen zu allen Add-Ins sowie den zugewiesenen Benutzern und Gruppen zu erhalten, übergeben Sie die Ausgabe des Cmdlets **Get-OrganizationAddIn** an das Cmdlet Format-List, wie im folgenden Beispiel dargestellt.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Aktivieren oder Deaktivieren eines Add-ins

Wenn Sie ein Add-in deaktivieren möchten, sodass Benutzern und Gruppen, denen es zugewiesen ist, kein Zugriff mehr gewährt wird, führen Sie das Cmdlet " **OrganizationAddIn** " mit dem Parameter "  _ProductID_ " und dem Parameter "  _Enabled_ " aus  `$false` , wie im folgenden Beispiel gezeigt.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Wenn Sie ein Add-in wieder aktivieren möchten, führen Sie dasselbe Cmdlet aus, wobei der Parameter  _Enabled_ auf festgelegt ist  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Hinzufügen oder Entfernen von Benutzern aus einem Add-in

Zum Hinzufügen von Benutzern und Gruppen zu einem bestimmten Add-in führen Sie das Cmdlet " **OrganizationAddInAssignments** " mit den Parametern "  _ProductID_", "  _Add_" und "  _Members_ " aus. Trennen Sie die e-Mail-Adressen von Elementen durch ein Komma. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Wenn Sie Benutzer und Gruppen entfernen möchten, führen Sie das gleiche Cmdlet mit dem  _Remove_ -Parameter aus. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Um ein Add-in allen Benutzern im Mandanten zuzuweisen, führen Sie das gleiche Cmdlet mit dem  _AssignToEveryone_ -Parameter aus, wobei der Wert auf festgelegt ist  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Um kein Add-in allen Benutzern zuzuweisen und die zuvor zugewiesenen Benutzer und Gruppen wiederherzustellen, können Sie dasselbe Cmdlet ausführen und den Parameter  _AssignToEveryone_ deaktivieren, indem Sie seinen Wert auf festlegen  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Aktualisieren eines Add-ins

Um ein Add-in aus einem Manifest zu aktualisieren, führen Sie das Cmdlet " **OrganizationAddIn** " mit den Parametern  _ProductID_,  _ManifestPath_und  _locale_ aus, wie im folgenden Beispiel gezeigt. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Aus dem Office Store hochgeladene Add-Ins werden automatisch innerhalb von ein paar Tagen nach der Verfügbarkeit des neuesten Updates im Office Store aktualisiert. 
  
## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Um ein Add-in zu löschen, führen **Sie das Cmdlet Remove-OrganizationAddIn** mit dem Parameter  _ProductID_ aus, wie im folgenden Beispiel gezeigt. 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a>Ausführliche Hilfe zu jedem Cmdlet erhalten

Sie können die detaillierte Hilfe zu jedem Cmdlet mithilfe des Cmdlets Get-Help betrachten. Beispielsweise enthält das folgende Cmdlet ausführliche Informationen zum Cmdlet Remove-OrganizationAddIn.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


