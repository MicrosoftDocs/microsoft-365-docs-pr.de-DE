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
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="f8cb7-103">Verwenden der PowerShell-Cmdlets für zentrale Bereitstellung zum Verwalten von Add-Ins</span><span class="sxs-lookup"><span data-stu-id="f8cb7-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="f8cb7-104">Als globaler Microsoft 365 können Sie Office-Add-Ins über das Feature für die zentrale Bereitstellung für Benutzer bereitstellen (siehe [Deploy Office Add-ins in the Admin Center](../admin/manage/manage-deployment-of-add-ins.md)).</span><span class="sxs-lookup"><span data-stu-id="f8cb7-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)).</span></span> <span data-ttu-id="f8cb7-105">Zusätzlich zur Bereitstellung Office Add-Ins über das Microsoft 365 Admin Center können Sie auch Microsoft PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="f8cb7-106">Installieren Sie [das O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="f8cb7-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="f8cb7-107">Öffnen Sie nach dem Herunterladen des Moduls ein reguläres Windows PowerShell, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f8cb7-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="f8cb7-108">Verbinden verwenden Ihrer Administratoranmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f8cb7-108">Connect using your admin credentials</span></span>

<span data-ttu-id="f8cb7-109">Bevor Sie die Cmdlets für die zentrale Bereitstellung verwenden können, müssen Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="f8cb7-110">Starten Sie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="f8cb7-111">Verbinden powerShell mithilfe der Anmeldeinformationen Ihres Unternehmensadministrators.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="f8cb7-112">Führen Sie das folgende Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="f8cb7-113">Geben Sie auf der Seite **Anmeldeinformationen** eingeben Ihre Microsoft 365 Anmeldeinformationen für den globalen Administrator ein.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="f8cb7-114">Alternativ können Sie Ihre Anmeldeinformationen direkt in das Cmdlet eingeben.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="f8cb7-115">Führen Sie das folgende Cmdlet aus, das Ihre Unternehmensadministratoranmeldeinformationen als PSCredential-Objekt anfordert.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="f8cb7-116">Weitere Informationen zur Verwendung von PowerShell finden Sie [unter Verbinden to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f8cb7-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="f8cb7-117">Hochladen eines Add-In-Manifests</span><span class="sxs-lookup"><span data-stu-id="f8cb7-117">Upload an add-in manifest</span></span>

<span data-ttu-id="f8cb7-118">Führen Sie **das Cmdlet New-OrganizationAdd-In** aus, um ein Add-In-Manifest aus einem Pfad hochzuladen, der entweder dateispeicherort oder URL sein kann.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="f8cb7-119">Das folgende Beispiel zeigt einen Dateispeicherort für den Wert des _ManifestPath-Parameters._</span><span class="sxs-lookup"><span data-stu-id="f8cb7-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="f8cb7-120">Sie können auch das **Cmdlet New-OrganizationAdd-In** ausführen, um ein Add-In hochzuladen und mithilfe des  _Parameters Members_ Benutzern oder Gruppen direkt zuzuordnen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="f8cb7-121">Trennen Sie die E-Mail-Adressen von Mitgliedern durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="f8cb7-122">Hochladen ein Add-In aus dem Office Store</span><span class="sxs-lookup"><span data-stu-id="f8cb7-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="f8cb7-123">Führen Sie **das Cmdlet New-OrganizationAddIn** aus, um ein Manifest aus dem Office Store.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="f8cb7-124">Im folgenden Beispiel gibt das **Cmdlet New-OrganizationAddIn** die AssetId für ein Add-In für einen Standort- und Inhaltsmarkt in den USA an.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="f8cb7-125">Um den Wert für den _AssetId-Parameter_ zu bestimmen, können Sie ihn aus der URL der Office Store webseite für das Add-In kopieren.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="f8cb7-126">AssetIds beginnen immer mit "WA", gefolgt von einer Zahl.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="f8cb7-127">Im vorherigen Beispiel ist die Quelle für den AssetId-Wert von WA104099688 beispielsweise die url der Office Store Webseite für das Add-In: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="f8cb7-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="f8cb7-128">Die Werte für den  _Parameter Locale_ und  _den Parameter ContentMarket_ sind identisch und geben das Land/die Region an, aus dem Sie das Add-In installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="f8cb7-129">Das Format ist en-US, fr-FR.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="f8cb7-130">usw.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f8cb7-131">Add-Ins, die aus dem Office Store hochgeladen wurden, werden innerhalb weniger Tage automatisch aktualisiert, wenn das neueste Update auf dem Office Store.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="f8cb7-132">Details zu einem Add-In erhalten</span><span class="sxs-lookup"><span data-stu-id="f8cb7-132">Get details of an add-in</span></span>

<span data-ttu-id="f8cb7-133">Führen Sie **das Cmdlet Get-OrganizationAddIn** wie unten gezeigt aus, um Details aller add-ins zu erhalten, die in den Mandanten hochgeladen wurden und die Produkt-ID eines Add-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="f8cb7-134">Führen Sie **das Cmdlet Get-OrganizationAddIn** mit einem Wert für den  _ProductId-Parameter_ aus, um anzugeben, für welches Add-In Sie Details abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="f8cb7-135">Um vollständige Details aller Add-Ins sowie der zugewiesenen Benutzer und Gruppen zu erhalten, geben Sie die Ausgabe des **Cmdlets Get-OrganizationAddIn** an das cmdlet Format-List weiter, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="f8cb7-136">Aktivieren oder Deaktivieren eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="f8cb7-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="f8cb7-137">Führen Sie das **Cmdlet Set-OrganizationAddIn** mit dem  _Parameter ProductId_ und dem  _Enabled-Parameter_ auf aus, um ein Add-In zu deaktivieren, damit benutzer und Gruppen, die ihm zugewiesen sind, keinen Zugriff mehr haben, wie im folgenden Beispiel  `$false` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="f8cb7-138">Um ein Add-In wieder zu aktivieren, führen Sie dasselbe Cmdlet aus, bei dem der  _Parameter Enabled_ auf festgelegt  `$true` ist.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="f8cb7-139">Hinzufügen oder Entfernen von Benutzern aus einem Add-In</span><span class="sxs-lookup"><span data-stu-id="f8cb7-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="f8cb7-140">Führen Sie zum Hinzufügen von Benutzern und Gruppen zu einem bestimmten **Add-In das Cmdlet Set-OrganizationAddInAssignments** mit den  _Parametern ProductId,_  _Add_ und  _Members_ aus.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="f8cb7-141">Trennen Sie die E-Mail-Adressen von Mitgliedern durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="f8cb7-142">Führen Sie dasselbe Cmdlet mit dem Parameter Remove aus, um Benutzer und Gruppen  _zu_ entfernen.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="f8cb7-143">Um allen Benutzern im Mandanten ein Add-In zuzuordnen, führen Sie dasselbe Cmdlet mit dem  _Parameter AssignToEveryone_ aus, und der Wert ist auf  `$true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="f8cb7-144">Um keinem Benutzer ein Add-In zuzuordnen und zu den zuvor zugewiesenen Benutzern und Gruppen zurückzuschalten, können Sie dasselbe Cmdlet ausführen und den  _Parameter AssignToEveryone_ deaktivieren, indem Sie dessen Wert auf  `$false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="f8cb7-145">Aktualisieren eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="f8cb7-145">Update an add-in</span></span>

<span data-ttu-id="f8cb7-146">Führen Sie zum Aktualisieren eines Add-Ins aus einem Manifest das **Cmdlet Set-OrganizationAddIn** mit den  _Parametern ProductId,_  _ManifestPath_ und  _Locale_ aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="f8cb7-147">Add-Ins, die aus dem Office Store hochgeladen wurden, werden innerhalb weniger Tage automatisch aktualisiert, wenn das neueste Update auf dem Office Store.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="f8cb7-148">Löschen eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="f8cb7-148">Delete an add-in</span></span>

<span data-ttu-id="f8cb7-149">Führen Sie zum Löschen eines Add-Ins das **Cmdlet Remove-OrganizationAddIn** mit dem  _Parameter ProductId_ aus, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="f8cb7-150">Detaillierte Hilfe für jedes Cmdlet erhalten</span><span class="sxs-lookup"><span data-stu-id="f8cb7-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="f8cb7-151">Mithilfe des Cmdlets Get-help können Sie detaillierte Hilfe für jedes Cmdlet finden.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="f8cb7-152">Das folgende Cmdlet enthält beispielsweise detaillierte Informationen zum Remove-OrganizationAddIn Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8cb7-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```