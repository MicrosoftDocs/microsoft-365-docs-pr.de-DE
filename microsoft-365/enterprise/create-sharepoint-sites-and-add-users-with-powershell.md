---
title: Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 'Zusammenfassung: Verwenden Sie PowerShell zum Erstellen neuer SharePoint Online Websites und Hinzufügen von Benutzern und Gruppen zu diesen Websites.'
ms.openlocfilehash: 4c4edbd68343f0eaf3a25a8c60a2af1e83b058b6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690439"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="8152b-103">Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8152b-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="8152b-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8152b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8152b-105">Wenn Sie PowerShell für Microsoft 365 zum Erstellen SharePoint Online Websites und zum Hinzufügen von Benutzern verwenden, können Sie Aufgaben schnell und wiederholt wesentlich schneller ausführen, als Sie im Microsoft 365 Admin Center durchführen können.</span><span class="sxs-lookup"><span data-stu-id="8152b-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8152b-106">Sie können auch Aufgaben ausführen, die nicht im Microsoft 365 Admin Center ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="8152b-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="8152b-107">Herstellen einer Verbindung mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8152b-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="8152b-108">Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit SharePoint Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="8152b-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="8152b-109">Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) .</span><span class="sxs-lookup"><span data-stu-id="8152b-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="8152b-110">Schritt 1: Erstellen neuer Websitesammlungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="8152b-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="8152b-111">Erstellen Sie mehrere Websites mithilfe von PowerShell und eine CSV-Datei, die Sie mit dem bereitgestellten Beispielcode und mit Notepad erstellen.</span><span class="sxs-lookup"><span data-stu-id="8152b-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="8152b-112">Hierzu ersetzen Sie die in Klammern stehende Platzhalter-Information durch Ihre eigenen Website- und Mandant-spezifischen Informationen.</span><span class="sxs-lookup"><span data-stu-id="8152b-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="8152b-113">Bei diesem Verfahren können Sie eine einzelne Datei erstellen und einen einzelnen PowerShell-Befehl ausführen, der diese Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="8152b-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="8152b-114">Die durchgeführten Maßnahmen sind sowohl wiederholbar als auch tragbar und es werden viele, wenn nicht alle Fehler vermieden, die durch die Eingabe der Befehle in die SharePoint Online-Verwaltungsshell entstehen können.</span><span class="sxs-lookup"><span data-stu-id="8152b-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="8152b-115">Dieses Verfahren lässt sich in zwei Teile aufteilen.</span><span class="sxs-lookup"><span data-stu-id="8152b-115">There are two parts to this procedure.</span></span> <span data-ttu-id="8152b-116">Zunächst erstellen Sie eine CSV-Datei, und dann verweisen Sie auf die CSV-Datei mithilfe von PowerShell, die ihren Inhalt zum Erstellen der Websites verwenden wird.</span><span class="sxs-lookup"><span data-stu-id="8152b-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="8152b-117">Das PowerShell-Cmdlet importiert die CSV-Datei und leitet Sie in eine Schleife innerhalb der geschweiften Klammern, die die erste Zeile der Datei als Spaltenüberschriften liest.</span><span class="sxs-lookup"><span data-stu-id="8152b-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="8152b-118">Das PowerShell-Cmdlet durchläuft dann die restlichen Datensätze, erstellt eine neue Websitesammlung für jeden Datensatz und weist die Eigenschaften der Websitesammlung entsprechend den Spaltenüberschriften zu.</span><span class="sxs-lookup"><span data-stu-id="8152b-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="8152b-119">Erstellen einer CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="8152b-119">Create a .csv file</span></span>

1. <span data-ttu-id="8152b-120">Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="8152b-120">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="8152b-121">Dabei ist *Mandanten* der Name Ihres Mandanten, und *Owner* ist der Benutzername des Benutzers in Ihrem Mandanten, dem Sie die Rolle des primären Websitesammlungsadministrators erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="8152b-121">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="8152b-122">(Sie können Strg + H drücken, wenn Sie den Editor verwenden, um schneller Massen zu ersetzen.)</span><span class="sxs-lookup"><span data-stu-id="8152b-122">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="8152b-123">Speichern Sie die Datei auf Ihrem Desktop als **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="8152b-123">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="8152b-124">Bevor Sie diese oder eine andere CSV-oder Windows PowerShell-Skriptdatei verwenden, sollten Sie sicherstellen, dass keine fremden oder nicht druckbaren Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8152b-124">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="8152b-125">Öffnen Sie die Datei in Word und klicken Sie auf dem Menüband auf das Symbol Absatz, um nicht druckbare Zeichen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8152b-125">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="8152b-126">Es sollten keine überflüssigen, nicht druckbaren Zeichen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8152b-126">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="8152b-127">Es sollten beispielsweise keine Absatzmarken nach dem letzten Absatz am Ende der Datei vorkommen.</span><span class="sxs-lookup"><span data-stu-id="8152b-127">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="8152b-128">Ausführen des PowerShell-Befehls</span><span class="sxs-lookup"><span data-stu-id="8152b-128">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="8152b-129">Geben Sie an der Windows PowerShell Aufforderung den folgenden Befehl ein, oder kopieren und fügen Sie ihn ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="8152b-129">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="8152b-130">Wobei *myalias* Ihrem Benutzer Alias entspricht.</span><span class="sxs-lookup"><span data-stu-id="8152b-130">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="8152b-p106">Warten Sie, bis die Windows PowerShell-Eingabeaufforderung wieder erscheint. Dies kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="8152b-p106">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="8152b-133">Bei Aufforderung durch Windows PowerShell geben Sie das folgende Cmdlet ein, oder kopieren und fügen Sie es ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="8152b-133">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="8152b-134">Beachten Sie die neuen Websitesammlungen in der Liste.</span><span class="sxs-lookup"><span data-stu-id="8152b-134">Note the new site collections in the list.</span></span> <span data-ttu-id="8152b-135">Mithilfe unserer CSV-Beispieldatei werden die folgenden Websitesammlungen angezeigt: **TeamSite01**, **Blog01**, **Project01**und **Community01**</span><span class="sxs-lookup"><span data-stu-id="8152b-135">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="8152b-136">Fertig!</span><span class="sxs-lookup"><span data-stu-id="8152b-136">That’s it.</span></span> <span data-ttu-id="8152b-137">Sie haben mehrere Websitesammlungen mit der von Ihnen erstellten CSV-Datei und einem einzelnen Windows PowerShell-Befehl erstellt.</span><span class="sxs-lookup"><span data-stu-id="8152b-137">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="8152b-138">Sie können jetzt Benutzer erstellen und zu diesen Websites hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8152b-138">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="8152b-139">Schritt 2: Hinzufügen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="8152b-139">Step 2: Add users and groups</span></span>

<span data-ttu-id="8152b-p109">Sie werden nun Benutzer erstellen und sie zu einer Websitesammlungsgruppe hinzufügen. Sie werden danach mithilfe einer .csv-Datei große Mengen an neuen Gruppen und Benutzern hochladen.</span><span class="sxs-lookup"><span data-stu-id="8152b-p109">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="8152b-142">Die folgenden Verfahren werden weiterhin mit den Beispiel Standorten TeamSite01, Blog01, Project01 und Community01 verwendet.</span><span class="sxs-lookup"><span data-stu-id="8152b-142">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="8152b-143">Erstellen von CSV und ps1-Dateien</span><span class="sxs-lookup"><span data-stu-id="8152b-143">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="8152b-144">Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="8152b-144">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="8152b-145">Wobei *Mandanten* Ihrem Mandantennamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="8152b-145">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="8152b-146">Speichern Sie die Datei auf Ihrem Desktop als **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="8152b-146">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="8152b-147">Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="8152b-147">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="8152b-148">Dabei ist *Mandant* gleich ihrem Mandantennamen, und *username* entspricht dem Benutzernamen eines vorhandenen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="8152b-148">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="8152b-149">Speichern Sie die Datei auf Ihrem Desktop als **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="8152b-149">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="8152b-150">Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="8152b-150">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="8152b-151">Dabei entspricht myalias dem Benutzernamen des derzeit angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="8152b-151">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="8152b-152">Speichern Sie die Datei auf Ihrem Desktop als **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="8152b-152">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="8152b-153">Das ist ein einfaches Windows PowerShell-Skript.</span><span class="sxs-lookup"><span data-stu-id="8152b-153">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="8152b-154">Sie können jetzt das Skript UsersAndGroup.ps1 durchlaufen lassen, um Benutzer und Gruppen zu mehreren Websitesammlungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8152b-154">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="8152b-155">Ausführen von Skript UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="8152b-155">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="8152b-156">Gehen Sie zurück zu der SharePoint Online-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8152b-156">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="8152b-157">Bei Aufforderung durch Windows PowerShell geben sie die folgende Zeile ein, oder kopieren und fügen Sie sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="8152b-157">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="8152b-158">Drücken Sie an der Bestätigungsaufforderung **Y**.</span><span class="sxs-lookup"><span data-stu-id="8152b-158">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="8152b-159">Bei Aufforderung durch Windows PowerShell geben Sie Folgendes ein oder kopieren und fügen es ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="8152b-159">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="8152b-160">Wobei *myalias* Ihrem Benutzernamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="8152b-160">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="8152b-p111">Warten Sie, bis die Eingabeaufforderung wieder erscheint, bevor Sie fortfahren. Zuerst werden Sie die Gruppen sehen, sobald diese erstellt sind. Sobald Benutzer hinzugefügt werden, sehen Sie wiederholt die Gruppenliste.</span><span class="sxs-lookup"><span data-stu-id="8152b-p111">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="8152b-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8152b-164">See also</span></span>

[<span data-ttu-id="8152b-165">Herstellen einer Verbindung mit SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8152b-165">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="8152b-166">Verwalten von SharePoint Online-Websitegruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8152b-166">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="8152b-167">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8152b-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8152b-168">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8152b-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

