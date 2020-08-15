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
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="c708b-103">Verwenden der PowerShell-Cmdlets für zentrale Bereitstellung zum Verwalten von Add-Ins</span><span class="sxs-lookup"><span data-stu-id="c708b-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="c708b-104">Als globaler Administrator von Microsoft 365 können Sie Office-Add-Ins für Benutzer über das zentralisierte Bereitstellungsfeature bereitstellen (siehe [Deploy Office-Add-Ins im Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span><span class="sxs-lookup"><span data-stu-id="c708b-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span></span> <span data-ttu-id="c708b-105">Neben der Bereitstellung von Office-Add-Ins über das Microsoft 365 Admin Center können Sie auch Microsoft PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="c708b-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="c708b-106">Installieren [Sie das zentrale O365-Add-in-Bereitstellungsmodul für Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="c708b-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="c708b-107">Öffnen Sie nach dem Herunterladen des Moduls ein reguläres Windows PowerShell Fenster, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="c708b-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="c708b-108">Herstellen einer Verbindung mit Ihren Administratoranmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="c708b-108">Connect using your admin credentials</span></span>

<span data-ttu-id="c708b-109">Bevor Sie die Cmdlets für die zentrale Bereitstellung verwenden können, müssen Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="c708b-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="c708b-110">Starten Sie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c708b-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="c708b-111">Stellen Sie eine Verbindung mit PowerShell mithilfe ihrer Unternehmensadministrator Anmeldeinformationen her.</span><span class="sxs-lookup"><span data-stu-id="c708b-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="c708b-112">Führen Sie das folgende Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="c708b-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="c708b-113">Geben Sie auf der Seite **Anmeldeinformationen eingeben** ihre globalen Administratoranmeldeinformationen von Microsoft 365 ein.</span><span class="sxs-lookup"><span data-stu-id="c708b-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="c708b-114">Alternativ können Sie Ihre Anmeldeinformationen direkt in das Cmdlet eingeben.</span><span class="sxs-lookup"><span data-stu-id="c708b-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="c708b-115">Führen Sie das folgende Cmdlet aus, das die Anmeldeinformationen Ihres Unternehmens als PSCredential-Objekt angibt.</span><span class="sxs-lookup"><span data-stu-id="c708b-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="c708b-116">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span><span class="sxs-lookup"><span data-stu-id="c708b-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="c708b-117">Hochladen eines Add-in-Manifests</span><span class="sxs-lookup"><span data-stu-id="c708b-117">Upload an add-in manifest</span></span>

<span data-ttu-id="c708b-118">Führen Sie das Cmdlet **New-organisationadd-in** aus, um ein Add-in-Manifest aus einem Pfad hochzuladen, bei dem es sich entweder um einen Dateispeicherort oder eine URL handeln kann.</span><span class="sxs-lookup"><span data-stu-id="c708b-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="c708b-119">Das folgende Beispiel zeigt einen Dateispeicherort für den Wert des  _ManifestPath_ -Parameters.</span><span class="sxs-lookup"><span data-stu-id="c708b-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="c708b-120">Sie können auch das **New-organisationadd-in-** Cmdlet ausführen, um ein Add-in hochzuladen und es Benutzern oder Gruppen direkt mithilfe des  _Members_ -Parameters zuzuweisen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c708b-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="c708b-121">Trennen Sie die e-Mail-Adressen von Elementen durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="c708b-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="c708b-122">Hochladen eines Add-Ins aus dem Office Store</span><span class="sxs-lookup"><span data-stu-id="c708b-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="c708b-123">Führen Sie das Cmdlet **New-OrganizationAddIn** aus, um ein Manifest aus dem Office Store hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="c708b-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="c708b-124">Im folgenden Beispiel gibt das Cmdlet **New-OrganizationAddIn** die Asset-Nr für ein Add-in für einen Standort und einen Inhalts Markt in USA an.</span><span class="sxs-lookup"><span data-stu-id="c708b-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="c708b-125">Um den Wert für den Parameter  _Asset_ -Nr zu ermitteln, können Sie ihn aus der URL der Office Store Webseite für das Add-in kopieren.</span><span class="sxs-lookup"><span data-stu-id="c708b-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="c708b-126">AssetIds beginnen immer mit "WA", gefolgt von einer Zahl.</span><span class="sxs-lookup"><span data-stu-id="c708b-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="c708b-127">Im vorherigen Beispiel ist beispielsweise die Quelle für den Wert der WA104099688-Website die URL für das Add-in Office Store Webseite: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="c708b-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="c708b-128">Die Werte für den Parameter  _locale_ und den Parameter  _ContentMarket_ sind identisch und geben das Land/die Region an, aus dem das Add-in installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c708b-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="c708b-129">Das Format lautet en-US, fr-fr.</span><span class="sxs-lookup"><span data-stu-id="c708b-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="c708b-130">und so weiter.</span><span class="sxs-lookup"><span data-stu-id="c708b-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c708b-131">Aus dem Office Store hochgeladene Add-Ins werden automatisch innerhalb von ein paar Tagen nach der Verfügbarkeit des neuesten Updates im Office Store aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c708b-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="c708b-132">Abrufen von Details eines Add-ins</span><span class="sxs-lookup"><span data-stu-id="c708b-132">Get details of an add-in</span></span>

<span data-ttu-id="c708b-133">Führen Sie das **Get-OrganizationAddIn-** Cmdlet wie unten beschrieben aus, um Details zu allen Add-Ins abzurufen, die in den Mandanten hochgeladen wurden und die Produkt-ID eines Add-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="c708b-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="c708b-134">Führen Sie das Cmdlet **Get-OrganizationAddIn** mit einem Wert für den  _ProductID_ -Parameter aus, um anzugeben, für welches Add-in Sie Details abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="c708b-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="c708b-135">Um vollständige Informationen zu allen Add-Ins sowie den zugewiesenen Benutzern und Gruppen zu erhalten, übergeben Sie die Ausgabe des Cmdlets **Get-OrganizationAddIn** an das Cmdlet Format-List, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c708b-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="c708b-136">Aktivieren oder Deaktivieren eines Add-ins</span><span class="sxs-lookup"><span data-stu-id="c708b-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="c708b-137">Wenn Sie ein Add-in deaktivieren möchten, sodass Benutzern und Gruppen, denen es zugewiesen ist, kein Zugriff mehr gewährt wird, führen Sie das Cmdlet " **OrganizationAddIn** " mit dem Parameter "  _ProductID_ " und dem Parameter "  _Enabled_ " aus  `$false` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c708b-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="c708b-138">Wenn Sie ein Add-in wieder aktivieren möchten, führen Sie dasselbe Cmdlet aus, wobei der Parameter  _Enabled_ auf festgelegt ist  `$true` .</span><span class="sxs-lookup"><span data-stu-id="c708b-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="c708b-139">Hinzufügen oder Entfernen von Benutzern aus einem Add-in</span><span class="sxs-lookup"><span data-stu-id="c708b-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="c708b-140">Zum Hinzufügen von Benutzern und Gruppen zu einem bestimmten Add-in führen Sie das Cmdlet " **OrganizationAddInAssignments** " mit den Parametern "  _ProductID_", "  _Add_" und "  _Members_ " aus.</span><span class="sxs-lookup"><span data-stu-id="c708b-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="c708b-141">Trennen Sie die e-Mail-Adressen von Elementen durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="c708b-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="c708b-142">Wenn Sie Benutzer und Gruppen entfernen möchten, führen Sie das gleiche Cmdlet mit dem  _Remove_ -Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="c708b-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="c708b-143">Um ein Add-in allen Benutzern im Mandanten zuzuweisen, führen Sie das gleiche Cmdlet mit dem  _AssignToEveryone_ -Parameter aus, wobei der Wert auf festgelegt ist  `$true` .</span><span class="sxs-lookup"><span data-stu-id="c708b-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="c708b-144">Um kein Add-in allen Benutzern zuzuweisen und die zuvor zugewiesenen Benutzer und Gruppen wiederherzustellen, können Sie dasselbe Cmdlet ausführen und den Parameter  _AssignToEveryone_ deaktivieren, indem Sie seinen Wert auf festlegen  `$false` .</span><span class="sxs-lookup"><span data-stu-id="c708b-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="c708b-145">Aktualisieren eines Add-ins</span><span class="sxs-lookup"><span data-stu-id="c708b-145">Update an add-in</span></span>

<span data-ttu-id="c708b-146">Um ein Add-in aus einem Manifest zu aktualisieren, führen Sie das Cmdlet " **OrganizationAddIn** " mit den Parametern  _ProductID_,  _ManifestPath_und  _locale_ aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c708b-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="c708b-147">Aus dem Office Store hochgeladene Add-Ins werden automatisch innerhalb von ein paar Tagen nach der Verfügbarkeit des neuesten Updates im Office Store aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c708b-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="c708b-148">Löschen eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="c708b-148">Delete an add-in</span></span>

<span data-ttu-id="c708b-149">Um ein Add-in zu löschen, führen **Sie das Cmdlet Remove-OrganizationAddIn** mit dem Parameter  _ProductID_ aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c708b-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="c708b-150">Ausführliche Hilfe zu jedem Cmdlet erhalten</span><span class="sxs-lookup"><span data-stu-id="c708b-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="c708b-151">Sie können die detaillierte Hilfe zu jedem Cmdlet mithilfe des Cmdlets Get-Help betrachten.</span><span class="sxs-lookup"><span data-stu-id="c708b-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="c708b-152">Beispielsweise enthält das folgende Cmdlet ausführliche Informationen zum Cmdlet Remove-OrganizationAddIn.</span><span class="sxs-lookup"><span data-stu-id="c708b-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


