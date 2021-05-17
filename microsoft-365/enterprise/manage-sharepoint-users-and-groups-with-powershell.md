---
title: Verwalten SharePoint Onlinebenutzern und -gruppen mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
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
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: In diesem Artikel erfahren Sie, wie Sie PowerShell for Microsoft 365 verwenden, um SharePoint, Gruppen und Websites zu verwalten.
ms.openlocfilehash: cc977355f1182b18d2f2e90b573683ed69299c1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916726"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="5948a-103">Verwalten SharePoint Onlinebenutzern und -gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5948a-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="5948a-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5948a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5948a-105">Wenn Sie ein SharePoint online-Administrator sind, der mit großen Listen von Benutzerkonten oder Gruppen arbeitet und eine einfachere Möglichkeit zum Verwalten dieser Konten möchte, können Sie PowerShell für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5948a-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span> 

<span data-ttu-id="5948a-106">Bevor Sie beginnen, müssen Sie für die Verfahren in diesem Thema eine Verbindung mit SharePoint Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="5948a-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="5948a-107">Anweisungen finden Sie [unter Verbinden to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="5948a-107">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="5948a-108">Eine Liste der Websites, Gruppen und Benutzer erhalten</span><span class="sxs-lookup"><span data-stu-id="5948a-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="5948a-109">Bevor wir mit der Verwaltung von Benutzern und Gruppen beginnen, müssen Sie Listen Ihrer Websites, Gruppen und Benutzer erhalten.</span><span class="sxs-lookup"><span data-stu-id="5948a-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="5948a-110">Anschließend können Sie diese Informationen verwenden, um das Beispiel in diesem Artikel zu durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="5948a-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="5948a-111">Mit diesem Befehl können Sie eine Liste der Websites in Ihrem Mandanten erhalten:</span><span class="sxs-lookup"><span data-stu-id="5948a-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="5948a-112">Mit diesem Befehl erhalten Sie eine Liste der Gruppen in Ihrem Mandanten:</span><span class="sxs-lookup"><span data-stu-id="5948a-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="5948a-113">Mit diesem Befehl erhalten Sie eine Liste der Benutzer in Ihrem Mandanten:</span><span class="sxs-lookup"><span data-stu-id="5948a-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="5948a-114">Hinzufügen eines Benutzers zur Gruppe "Websitesammlungsadministratoren"</span><span class="sxs-lookup"><span data-stu-id="5948a-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="5948a-115">Sie verwenden das Cmdlet, um der Liste der Websitesammlungsadministratoren in einer Websitesammlung einen `Set-SPOUser` Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5948a-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="5948a-116">Um diese Befehle zu verwenden, ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich < und > Zeichen, durch die richtigen Namen.</span><span class="sxs-lookup"><span data-stu-id="5948a-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="5948a-117">Mit diesem Befehlssatz wird beispielsweise Opal Castillo (Benutzername opalc) zur Liste der Websitesammlungsadministratoren in der ContosoTest-Websitesammlung im Mandanten Contoso hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="5948a-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="5948a-118">Sie können diese Befehle kopieren und in Editor einfügen, die Variablenwerte für $tenant, $site und $user in tatsächliche Werte aus Ihrer Umgebung ändern und diese dann in das Fenster SharePoint Online Management Shell einfügen, um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5948a-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="5948a-119">Hinzufügen eines Benutzers zu anderen Websitesammlungsgruppen</span><span class="sxs-lookup"><span data-stu-id="5948a-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="5948a-120">In dieser Aufgabe verwenden wir das Cmdlet, um einen Benutzer zu einer SharePoint `Add-SPOUser` einer Websitesammlung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5948a-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="5948a-121">Fügen wir beispielsweise Der Gruppe "Auditor" in der ContosoTest-Websitesammlung im Mandanten contoso "Glen Rife" (Benutzername glenr) hinzu:</span><span class="sxs-lookup"><span data-stu-id="5948a-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="5948a-122">Erstellen einer Websitesammlungsgruppe</span><span class="sxs-lookup"><span data-stu-id="5948a-122">Create a site collection group</span></span>

<span data-ttu-id="5948a-123">Mit dem Cmdlet können Sie eine neue SharePoint erstellen und `New-SPOSiteGroup` einer Websitesammlung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5948a-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
<span data-ttu-id="5948a-124">Gruppeneigenschaften, z. B. Berechtigungsstufen, können später mithilfe des `Set-SPOSiteGroup` Cmdlets aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5948a-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="5948a-125">Fügen wir beispielsweise die Gruppe "Auditoren" mit den Berechtigungen Nur anzeigen der contosotest-Websitesammlung im Mandanten contoso hinzu:</span><span class="sxs-lookup"><span data-stu-id="5948a-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="5948a-126">Entfernen von Benutzern aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="5948a-126">Remove users from a group</span></span>

<span data-ttu-id="5948a-127">Manchmal müssen Sie einen Benutzer von einer Website oder sogar von allen Websites entfernen.</span><span class="sxs-lookup"><span data-stu-id="5948a-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="5948a-128">Vielleicht wechselt der Mitarbeiter von einer Abteilung in eine andere oder verlässt das Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="5948a-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="5948a-129">Sie können dies für einen Mitarbeiter problemlos auf der Benutzeroberfläche tun, aber dies ist nicht einfach, wenn Sie eine vollständige Abteilung von einem Standort zu einem anderen verschieben müssen.</span><span class="sxs-lookup"><span data-stu-id="5948a-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="5948a-130">Mithilfe der SharePoint online-Verwaltungsshell und -CSV-Dateien ist dies jedoch schnell und einfach.</span><span class="sxs-lookup"><span data-stu-id="5948a-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="5948a-131">In dieser Aufgabe verwenden Sie Windows PowerShell, um einen Benutzer aus einer Sicherheitsgruppe für Websitesammlungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="5948a-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="5948a-132">Anschließend verwenden Sie eine CSV-Datei und entfernen viele Benutzer von verschiedenen Websites.</span><span class="sxs-lookup"><span data-stu-id="5948a-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span> 

<span data-ttu-id="5948a-133">Wir verwenden das Cmdlet "Remove-SPOUser", um einen einzelnen Microsoft 365-Benutzer aus einer Websitesammlungsgruppe zu entfernen, damit die Befehlssyntax angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5948a-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="5948a-134">Die Syntax sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5948a-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
<span data-ttu-id="5948a-135">Entfernen wir beispielsweise "Bobby Overby" aus der Gruppe "Auditoren" der Websitesammlung in der contosotest-Websitesammlung im Mandanten contoso:</span><span class="sxs-lookup"><span data-stu-id="5948a-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="5948a-136">Angenommen, wir wollten "Bobby" aus allen Gruppen entfernen, in der er sich derzeit befindet.</span><span class="sxs-lookup"><span data-stu-id="5948a-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="5948a-137">Hier sehen Sie, wie wir dies tun würden:</span><span class="sxs-lookup"><span data-stu-id="5948a-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="5948a-138">Dies ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5948a-138">This is just an example.</span></span> <span data-ttu-id="5948a-139">Sie sollten diesen Befehl nur ausführen, wenn Sie wirklich einen Benutzer aus jeder Gruppe entfernen müssen, z. B. wenn der Benutzer das Unternehmen verlässt.</span><span class="sxs-lookup"><span data-stu-id="5948a-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="5948a-140">Automatisieren der Verwaltung großer Listen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="5948a-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="5948a-141">Zum Hinzufügen einer großen Anzahl von Konten zu SharePoint Websites und zum Erteilen von Berechtigungen können Sie das Microsoft 365 Admin Center, einzelne PowerShell-Befehle oder PowerShell eine CSV-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="5948a-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="5948a-142">Bei diesen Optionen ist die CSV-Datei die schnellste Möglichkeit, diese Aufgabe zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="5948a-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="5948a-143">Der grundlegende Prozess besteht im Erstellen einer CSV-Datei mit Kopfzeilen (Spalten), die den Parametern entsprechen, die das Windows PowerShell benötigt.</span><span class="sxs-lookup"><span data-stu-id="5948a-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="5948a-144">Sie können eine solche Liste ganz einfach in Excel erstellen und dann als CSV-Datei exportieren.</span><span class="sxs-lookup"><span data-stu-id="5948a-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="5948a-145">Anschließend verwenden Sie ein Windows PowerShell-Skript, um Datensätze (Zeilen) in der CSV-Datei zu durch iterieren und die Benutzer zu Gruppen und die Gruppen zu Websites zu hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5948a-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span> 

<span data-ttu-id="5948a-146">Erstellen wir beispielsweise eine CSV-Datei, um eine Gruppe von Websitesammlungen, Gruppen und Berechtigungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5948a-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="5948a-147">Als Nächstes erstellen wir eine CSV-Datei, um die Gruppen mit Benutzern zu füllen.</span><span class="sxs-lookup"><span data-stu-id="5948a-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="5948a-148">Schließlich erstellen und führen wir ein einfaches Skript Windows PowerShell, das die Gruppen erstellt und auffüllt.</span><span class="sxs-lookup"><span data-stu-id="5948a-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="5948a-149">Die erste CSV-Datei fügt einer oder mehreren Websitesammlungen eine oder mehrere Gruppen hinzu und hat diese Struktur:</span><span class="sxs-lookup"><span data-stu-id="5948a-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="5948a-150">Header:</span><span class="sxs-lookup"><span data-stu-id="5948a-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="5948a-151">Element:</span><span class="sxs-lookup"><span data-stu-id="5948a-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="5948a-152">Hier ist eine Beispieldatei:</span><span class="sxs-lookup"><span data-stu-id="5948a-152">Here is an example file:</span></span>

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

<span data-ttu-id="5948a-153">Die zweite CSV-Datei fügt einer oder mehreren Gruppen einen oder mehrere Benutzer hinzu und hat diese Struktur:</span><span class="sxs-lookup"><span data-stu-id="5948a-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="5948a-154">Header:</span><span class="sxs-lookup"><span data-stu-id="5948a-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="5948a-155">Element:</span><span class="sxs-lookup"><span data-stu-id="5948a-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="5948a-156">Hier ist eine Beispieldatei:</span><span class="sxs-lookup"><span data-stu-id="5948a-156">Here is an example file:</span></span>

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

<span data-ttu-id="5948a-157">Für den nächsten Schritt müssen die beiden CSV-Dateien auf dem Laufwerk gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="5948a-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="5948a-158">Hier sind Beispielbefehle, die sowohl CSV-Dateien als auch Zum Hinzufügen von Berechtigungen und Gruppenmitgliedschaften verwenden:</span><span class="sxs-lookup"><span data-stu-id="5948a-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="5948a-159">Das Skript importiert den Inhalt der CSV-Datei und verwendet die Werte in den Spalten, um die Parameter der **Befehle New-SPOSiteGroup** und **Add-SPOUser auffüllen** zu können.</span><span class="sxs-lookup"><span data-stu-id="5948a-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="5948a-160">In unserem Beispiel speichern wir dies im OrdnerO365Admin auf Laufwerk C, aber Sie können es speichern, wo immer Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="5948a-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="5948a-161">Nun entfernen wir eine Reihe von Personen für mehrere Gruppen an verschiedenen Websites mit derselben CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="5948a-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="5948a-162">Nachfolgend sehen Sie einen Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="5948a-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="5948a-163">Generieren von Benutzerberichten</span><span class="sxs-lookup"><span data-stu-id="5948a-163">Generate user reports</span></span>

<span data-ttu-id="5948a-164">Sie können einen einfachen Bericht für einige wenige Websites erhalten und die Benutzer für diese Websites, deren Berechtigungsstufe und andere Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5948a-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="5948a-165">Die Syntax sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5948a-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="5948a-166">Dadurch werden die Daten für diese drei Websites gespeichert und in eine Textdatei auf Dem lokalen Laufwerk geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5948a-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="5948a-167">Beachten Sie, dass der Parameter –Append einer vorhandenen Datei neuen Inhalt hinzugibt.</span><span class="sxs-lookup"><span data-stu-id="5948a-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="5948a-168">Führen wir beispielsweise einen Bericht auf den Standorten ContosoTest, TeamSite01 und Project01 für den Contoso1-Mandanten aus:</span><span class="sxs-lookup"><span data-stu-id="5948a-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="5948a-169">Beachten Sie, dass wir nur die $site **ändern** mussten.</span><span class="sxs-lookup"><span data-stu-id="5948a-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="5948a-170">Die **$tenant-Variable** behält ihren Wert in allen drei Durchläufen des Befehls bei.</span><span class="sxs-lookup"><span data-stu-id="5948a-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="5948a-171">Was aber, wenn Sie dies für jede Website tun möchten?</span><span class="sxs-lookup"><span data-stu-id="5948a-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="5948a-172">Sie können dies tun, ohne alle diese Websites mit diesem Befehl eingeben zu müssen:</span><span class="sxs-lookup"><span data-stu-id="5948a-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="5948a-173">Dieser Bericht ist recht einfach, und Sie können mehr Code hinzufügen, um spezifischere Berichte oder Berichte zu erstellen, die ausführlichere Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5948a-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="5948a-174">Dies sollte Ihnen jedoch eine Vorstellung davon geben, wie Sie die SharePoint Online-Verwaltungsshell zum Verwalten von Benutzern in der SharePoint Onlineumgebung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5948a-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>
   
## <a name="see-also"></a><span data-ttu-id="5948a-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5948a-175">See also</span></span>

[<span data-ttu-id="5948a-176">Herstellen einer Verbindung mit SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5948a-176">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="5948a-177">Verwalten von SharePoint Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5948a-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="5948a-178">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5948a-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5948a-179">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5948a-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)