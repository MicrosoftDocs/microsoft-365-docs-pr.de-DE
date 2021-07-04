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
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie PowerShell für Microsoft 365 verwenden, um SharePoint Onlinewebsites zu erstellen und Benutzer hinzuzufügen, können Sie Aufgaben schnell und wiederholt viel schneller ausführen als im Microsoft 365 Admin Center. Sie können auch Aufgaben ausführen, die im Microsoft 365 Admin Center nicht ausgeführt werden können.

## <a name="connect-to-sharepoint-online"></a>Herstellen einer Verbindung mit SharePoint Online

Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit SharePoint Online herstellen. Anweisungen finden Sie unter [Verbinden zu SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Schritt 1: Erstellen neuer Websitesammlungen mithilfe von PowerShell

Erstellen Sie mehrere Websites mithilfe von PowerShell und einer .csv-Datei, die Sie mithilfe des bereitgestellten Beispielcodes und Editor erstellen. Hierzu ersetzen Sie die in Klammern stehende Platzhalter-Information durch Ihre eigenen Website- und Mandant-spezifischen Informationen. Mit diesem Vorgang können Sie eine einzelne Datei erstellen und einen einzelnen PowerShell-Befehl ausführen, der diese Datei verwendet. Die durchgeführten Maßnahmen sind sowohl wiederholbar als auch tragbar und es werden viele, wenn nicht alle Fehler vermieden, die durch die Eingabe der Befehle in die SharePoint Online-Verwaltungsshell entstehen können. Dieses Verfahren lässt sich in zwei Teile aufteilen. Zuerst erstellen Sie eine .csv-Datei, und dann verweisen Sie auf diese .csv Datei mithilfe von PowerShell, die den Inhalt zum Erstellen der Websites verwendet.

Das PowerShell-Cmdlet importiert die .csv-Datei und fügt sie in eine Schleife in den geschweiften Klammern ein, die die erste Zeile der Datei als Spaltenüberschriften liest. Das PowerShell-Cmdlet durchläuft dann die verbleibenden Datensätze, erstellt eine neue Websitesammlung für jeden Datensatz und weist Eigenschaften der Websitesammlung gemäß den Spaltenüberschriften zu.

### <a name="create-a-csv-file"></a>Erstellen einer CSV-Datei

> [!NOTE]
> Der Parameter "Ressourcenkontingent" funktioniert nur auf klassischen Websites. Wenn Sie diesen Parameter auf einer modernen Website verwenden, wird möglicherweise eine Warnmeldung angezeigt, dass er veraltet ist.

1. Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   Dabei ist der *Mandant* der Name Ihres Mandanten und der *Besitzer* der Benutzername des Benutzers auf Ihrem Mandanten, dem Sie die Rolle des primären Websitesammlungsadministrators zuweisen möchten.

   (Sie können STRG+H drücken, wenn Sie Editor verwenden, um den Massenaustausch schneller zu beschleunigen.)

2. Speichern Sie die Datei auf Ihrem Desktop als **SiteCollections.csv.**

> [!TIP]
> Bevor Sie diese oder eine andere .csv oder Windows PowerShell Skriptdatei verwenden, sollten Sie sicherstellen, dass keine zusätzlichen oder nicht druckbaren Zeichen vorhanden sind. Öffnen Sie die Datei in Word und klicken Sie auf dem Menüband auf das Symbol Absatz, um nicht druckbare Zeichen anzuzeigen. Es sollten keine überflüssigen, nicht druckbaren Zeichen vorhanden sein. Es sollten beispielsweise keine Absatzmarken nach dem letzten Absatz am Ende der Datei vorkommen.

### <a name="run-the-windows-powershell-command"></a>Ausführen des PowerShell-Befehls

1. Geben Sie an der Windows PowerShell Eingabeaufforderung den folgenden Befehl ein, kopieren sie ihn, fügen Sie ihn ein, und drücken Sie die EINGABETASTE:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   Dabei *entspricht MyAlias* Ihrem Benutzeralias.

2. Warten Sie, bis die Windows PowerShell-Eingabeaufforderung wieder erscheint. Dies kann einige Minuten dauern.

3. Bei Aufforderung durch Windows PowerShell geben Sie das folgende Cmdlet ein, oder kopieren und fügen Sie es ein, und drücken Sie die EINGABETASTE:

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. Beachten Sie die neuen Websitesammlungen in der Liste. In unserer CSV-Beispieldatei würden die folgenden Websitesammlungen angezeigt: **TeamSite01**, **Blog01**, **Project01** und **Community01**

Fertig! Sie haben mehrere Websitesammlungen mithilfe der von Ihnen erstellten .csv-Datei und einem einzelnen befehl Windows PowerShell erstellt. Sie können jetzt Benutzer erstellen und zu diesen Websites hinzufügen.

## <a name="step-2-add-users-and-groups"></a>Schritt 2: Hinzufügen von Benutzern und Gruppen

Sie werden nun Benutzer erstellen und sie zu einer Websitesammlungsgruppe hinzufügen. Sie werden danach mithilfe einer .csv-Datei große Mengen an neuen Gruppen und Benutzern hochladen.

Die folgenden Verfahren verwenden weiterhin die Beispielwebsites TeamSite01, Blog01, Project01 und Community01.

### <a name="create-csv-and-ps1-files"></a>Erstellen von CSV und ps1-Dateien

1. Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:

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

   Dabei entspricht *der Mandant* Ihrem Mandantennamen.

2. Speichern Sie die Datei auf Ihrem Desktop als **GroupsAndPermissions.csv.**

3. Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:

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

   Dabei entspricht der *Mandant* Ihrem Mandantennamen und *der Benutzername* dem Benutzernamen eines vorhandenen Benutzers.

4. Speichern Sie die Datei auf Ihrem Desktop als **Users.csv.**

5. Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   Dabei entspricht MyAlias dem Benutzernamen des Aktuell angemeldeten Benutzers.

6. Speichern Sie die Datei auf Ihrem Desktop als **UsersAndGroups.ps1.** Das ist ein einfaches Windows PowerShell-Skript.

Sie können jetzt das Skript UsersAndGroup.ps1 durchlaufen lassen, um Benutzer und Gruppen zu mehreren Websitesammlungen hinzuzufügen.

### <a name="run-usersandgroupsps1-script"></a>Ausführen von Skript UsersAndGroups.ps1

1. Gehen Sie zurück zu der SharePoint Online-Verwaltungsshell.

2. Bei Aufforderung durch Windows PowerShell geben sie die folgende Zeile ein, oder kopieren und fügen Sie sie ein, und drücken Sie die EINGABETASTE:

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. Drücken Sie an der Bestätigungsaufforderung **Y**.

4. Bei Aufforderung durch Windows PowerShell geben Sie Folgendes ein oder kopieren und fügen es ein, und drücken Sie die EINGABETASTE:

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   Dabei *entspricht MyAlias* Ihrem Benutzernamen.

5. Warten Sie, bis die Eingabeaufforderung wieder erscheint, bevor Sie fortfahren. Zuerst werden Sie die Gruppen sehen, sobald diese erstellt sind. Sobald Benutzer hinzugefügt werden, sehen Sie wiederholt die Gruppenliste.

## <a name="see-also"></a>Weitere Informationen:

[Herstellen einer Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Verwalten von SharePoint Online-Websitegruppen mit PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
