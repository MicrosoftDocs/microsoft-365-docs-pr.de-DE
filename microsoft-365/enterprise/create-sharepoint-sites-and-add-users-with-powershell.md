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
description: 'Zusammenfassung: Verwenden Sie PowerShell, um neue SharePoint Onlinewebsites zu erstellen und diesen Websites dann Benutzer und Gruppen hinzuzufügen.'
ms.openlocfilehash: 0c363df3edd40d810a0d8ca63090c0fec4c1c155
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288659"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="5dd88-103">Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd88-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="5dd88-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5dd88-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5dd88-105">Wenn Sie PowerShell für Microsoft 365 verwenden, um SharePoint Onlinewebsites zu erstellen und Benutzer hinzuzufügen, können Sie Aufgaben schnell und wiederholt viel schneller ausführen als im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="5dd88-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5dd88-106">Sie können auch Aufgaben ausführen, die im Microsoft 365 Admin Center nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="5dd88-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="5dd88-107">Herstellen einer Verbindung mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5dd88-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="5dd88-108">Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit SharePoint Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="5dd88-109">Anweisungen finden Sie unter [Verbinden zu SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="5dd88-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="5dd88-110">Schritt 1: Erstellen neuer Websitesammlungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd88-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="5dd88-111">Erstellen Sie mehrere Websites mithilfe von PowerShell und einer .csv-Datei, die Sie mithilfe des bereitgestellten Beispielcodes und Editor erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="5dd88-112">Hierzu ersetzen Sie die in Klammern stehende Platzhalter-Information durch Ihre eigenen Website- und Mandant-spezifischen Informationen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="5dd88-113">Mit diesem Vorgang können Sie eine einzelne Datei erstellen und einen einzelnen PowerShell-Befehl ausführen, der diese Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="5dd88-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="5dd88-114">Die durchgeführten Maßnahmen sind sowohl wiederholbar als auch tragbar und es werden viele, wenn nicht alle Fehler vermieden, die durch die Eingabe der Befehle in die SharePoint Online-Verwaltungsshell entstehen können.</span><span class="sxs-lookup"><span data-stu-id="5dd88-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5dd88-115">Dieses Verfahren lässt sich in zwei Teile aufteilen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-115">There are two parts to this procedure.</span></span> <span data-ttu-id="5dd88-116">Zuerst erstellen Sie eine .csv-Datei, und dann verweisen Sie auf diese .csv Datei mithilfe von PowerShell, die den Inhalt zum Erstellen der Websites verwendet.</span><span class="sxs-lookup"><span data-stu-id="5dd88-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="5dd88-117">Das PowerShell-Cmdlet importiert die .csv-Datei und fügt sie in eine Schleife in den geschweiften Klammern ein, die die erste Zeile der Datei als Spaltenüberschriften liest.</span><span class="sxs-lookup"><span data-stu-id="5dd88-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="5dd88-118">Das PowerShell-Cmdlet durchläuft dann die verbleibenden Datensätze, erstellt eine neue Websitesammlung für jeden Datensatz und weist Eigenschaften der Websitesammlung gemäß den Spaltenüberschriften zu.</span><span class="sxs-lookup"><span data-stu-id="5dd88-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="5dd88-119">Erstellen einer CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="5dd88-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="5dd88-120">Der Parameter "Ressourcenkontingent" funktioniert nur auf klassischen Websites.</span><span class="sxs-lookup"><span data-stu-id="5dd88-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="5dd88-121">Wenn Sie diesen Parameter auf einer modernen Website verwenden, wird möglicherweise eine Warnmeldung angezeigt, dass er veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="5dd88-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span>

1. <span data-ttu-id="5dd88-122">Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="5dd88-122">Open Notepad, and paste the following text block into it:</span></span>

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   <span data-ttu-id="5dd88-123">Dabei ist der *Mandant* der Name Ihres Mandanten und der *Besitzer* der Benutzername des Benutzers auf Ihrem Mandanten, dem Sie die Rolle des primären Websitesammlungsadministrators zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dd88-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span>

   <span data-ttu-id="5dd88-124">(Sie können STRG+H drücken, wenn Sie Editor verwenden, um den Massenaustausch schneller zu beschleunigen.)</span><span class="sxs-lookup"><span data-stu-id="5dd88-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span>

2. <span data-ttu-id="5dd88-125">Speichern Sie die Datei auf Ihrem Desktop als **SiteCollections.csv.**</span><span class="sxs-lookup"><span data-stu-id="5dd88-125">Save the file on your desktop as **SiteCollections.csv**.</span></span>

> [!TIP]
> <span data-ttu-id="5dd88-126">Bevor Sie diese oder eine andere .csv oder Windows PowerShell Skriptdatei verwenden, sollten Sie sicherstellen, dass keine zusätzlichen oder nicht druckbaren Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5dd88-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="5dd88-127">Öffnen Sie die Datei in Word und klicken Sie auf dem Menüband auf das Symbol Absatz, um nicht druckbare Zeichen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="5dd88-128">Es sollten keine überflüssigen, nicht druckbaren Zeichen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="5dd88-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="5dd88-129">Es sollten beispielsweise keine Absatzmarken nach dem letzten Absatz am Ende der Datei vorkommen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="5dd88-130">Ausführen des PowerShell-Befehls</span><span class="sxs-lookup"><span data-stu-id="5dd88-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="5dd88-131">Geben Sie an der Windows PowerShell Eingabeaufforderung den folgenden Befehl ein, kopieren sie ihn, fügen Sie ihn ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5dd88-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span>

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   <span data-ttu-id="5dd88-132">Dabei *entspricht MyAlias* Ihrem Benutzeralias.</span><span class="sxs-lookup"><span data-stu-id="5dd88-132">Where *MyAlias* equals your user alias.</span></span>

2. <span data-ttu-id="5dd88-p107">Warten Sie, bis die Windows PowerShell-Eingabeaufforderung wieder erscheint. Dies kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="5dd88-p107">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span>

3. <span data-ttu-id="5dd88-135">Bei Aufforderung durch Windows PowerShell geben Sie das folgende Cmdlet ein, oder kopieren und fügen Sie es ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5dd88-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span>

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. <span data-ttu-id="5dd88-136">Beachten Sie die neuen Websitesammlungen in der Liste.</span><span class="sxs-lookup"><span data-stu-id="5dd88-136">Note the new site collections in the list.</span></span> <span data-ttu-id="5dd88-137">In unserer CSV-Beispieldatei würden die folgenden Websitesammlungen angezeigt: **TeamSite01**, **Blog01**, **Project01** und **Community01**</span><span class="sxs-lookup"><span data-stu-id="5dd88-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="5dd88-138">Fertig!</span><span class="sxs-lookup"><span data-stu-id="5dd88-138">That’s it.</span></span> <span data-ttu-id="5dd88-139">Sie haben mehrere Websitesammlungen mithilfe der von Ihnen erstellten .csv-Datei und einem einzelnen befehl Windows PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="5dd88-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="5dd88-140">Sie können jetzt Benutzer erstellen und zu diesen Websites hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="5dd88-141">Schritt 2: Hinzufügen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="5dd88-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="5dd88-p110">Sie werden nun Benutzer erstellen und sie zu einer Websitesammlungsgruppe hinzufügen. Sie werden danach mithilfe einer .csv-Datei große Mengen an neuen Gruppen und Benutzern hochladen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="5dd88-144">Die folgenden Verfahren verwenden weiterhin die Beispielwebsites TeamSite01, Blog01, Project01 und Community01.</span><span class="sxs-lookup"><span data-stu-id="5dd88-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="5dd88-145">Erstellen von CSV und ps1-Dateien</span><span class="sxs-lookup"><span data-stu-id="5dd88-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="5dd88-146">Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="5dd88-146">Open Notepad, and paste the following text block into it:</span></span>

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

   <span data-ttu-id="5dd88-147">Dabei entspricht *der Mandant* Ihrem Mandantennamen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-147">Where *tenant* equals your tenant name.</span></span>

2. <span data-ttu-id="5dd88-148">Speichern Sie die Datei auf Ihrem Desktop als **GroupsAndPermissions.csv.**</span><span class="sxs-lookup"><span data-stu-id="5dd88-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span>

3. <span data-ttu-id="5dd88-149">Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="5dd88-149">Open a new instance of Notepad, and paste the following text block into it:</span></span>

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

   <span data-ttu-id="5dd88-150">Dabei entspricht der *Mandant* Ihrem Mandantennamen und *der Benutzername* dem Benutzernamen eines vorhandenen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5dd88-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span>

4. <span data-ttu-id="5dd88-151">Speichern Sie die Datei auf Ihrem Desktop als **Users.csv.**</span><span class="sxs-lookup"><span data-stu-id="5dd88-151">Save the file to your desktop as **Users.csv**.</span></span>

5. <span data-ttu-id="5dd88-152">Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:</span><span class="sxs-lookup"><span data-stu-id="5dd88-152">Open a new instance of Notepad, and paste the following text block into it:</span></span>

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   <span data-ttu-id="5dd88-153">Dabei entspricht MyAlias dem Benutzernamen des Aktuell angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5dd88-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span>

6. <span data-ttu-id="5dd88-154">Speichern Sie die Datei auf Ihrem Desktop als **UsersAndGroups.ps1.**</span><span class="sxs-lookup"><span data-stu-id="5dd88-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="5dd88-155">Das ist ein einfaches Windows PowerShell-Skript.</span><span class="sxs-lookup"><span data-stu-id="5dd88-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="5dd88-156">Sie können jetzt das Skript UsersAndGroup.ps1 durchlaufen lassen, um Benutzer und Gruppen zu mehreren Websitesammlungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="5dd88-157">Ausführen von Skript UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="5dd88-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="5dd88-158">Gehen Sie zurück zu der SharePoint Online-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="5dd88-158">Return to the SharePoint Online Management Shell.</span></span>

2. <span data-ttu-id="5dd88-159">Bei Aufforderung durch Windows PowerShell geben sie die folgende Zeile ein, oder kopieren und fügen Sie sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5dd88-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span>

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. <span data-ttu-id="5dd88-160">Drücken Sie an der Bestätigungsaufforderung **Y**.</span><span class="sxs-lookup"><span data-stu-id="5dd88-160">At the confirmation prompt, press **Y**.</span></span>

4. <span data-ttu-id="5dd88-161">Bei Aufforderung durch Windows PowerShell geben Sie Folgendes ein oder kopieren und fügen es ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5dd88-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span>

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   <span data-ttu-id="5dd88-162">Dabei *entspricht MyAlias* Ihrem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="5dd88-162">Where *MyAlias* equals your user name.</span></span>

5. <span data-ttu-id="5dd88-p112">Warten Sie, bis die Eingabeaufforderung wieder erscheint, bevor Sie fortfahren. Zuerst werden Sie die Gruppen sehen, sobald diese erstellt sind. Sobald Benutzer hinzugefügt werden, sehen Sie wiederholt die Gruppenliste.</span><span class="sxs-lookup"><span data-stu-id="5dd88-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dd88-166">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5dd88-166">See also</span></span>

[<span data-ttu-id="5dd88-167">Herstellen einer Verbindung mit SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd88-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="5dd88-168">Verwalten von SharePoint Online-Websitegruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd88-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="5dd88-169">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd88-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="5dd88-170">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5dd88-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
