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
ms.openlocfilehash: 28a51cc39fe838f6c7f9c50e9d750d28e5d830c4
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594918"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie PowerShell für Microsoft 365 zum Erstellen SharePoint Online Websites und zum Hinzufügen von Benutzern verwenden, können Sie Aufgaben schnell und wiederholt wesentlich schneller ausführen, als Sie im Microsoft 365 Admin Center durchführen können. Sie können auch Aufgaben ausführen, die nicht im Microsoft 365 Admin Center ausgeführt werden können. 

## <a name="connect-to-sharepoint-online"></a>Herstellen einer Verbindung mit SharePoint Online

Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit SharePoint Online herstellen. Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) .

## <a name="step-1-create-new-site-collections-using-powershell"></a>Schritt 1: Erstellen neuer Websitesammlungen mithilfe von PowerShell

Erstellen Sie mehrere Websites mithilfe von PowerShell und eine CSV-Datei, die Sie mit dem bereitgestellten Beispielcode und mit Notepad erstellen. Hierzu ersetzen Sie die in Klammern stehende Platzhalter-Information durch Ihre eigenen Website- und Mandant-spezifischen Informationen. Bei diesem Verfahren können Sie eine einzelne Datei erstellen und einen einzelnen PowerShell-Befehl ausführen, der diese Datei verwendet. Die durchgeführten Maßnahmen sind sowohl wiederholbar als auch tragbar und es werden viele, wenn nicht alle Fehler vermieden, die durch die Eingabe der Befehle in die SharePoint Online-Verwaltungsshell entstehen können. Dieses Verfahren lässt sich in zwei Teile aufteilen. Zunächst erstellen Sie eine CSV-Datei, und dann verweisen Sie auf die CSV-Datei mithilfe von PowerShell, die ihren Inhalt zum Erstellen der Websites verwenden wird.

Das PowerShell-Cmdlet importiert die CSV-Datei und leitet Sie in eine Schleife innerhalb der geschweiften Klammern, die die erste Zeile der Datei als Spaltenüberschriften liest. Das PowerShell-Cmdlet durchläuft dann die restlichen Datensätze, erstellt eine neue Websitesammlung für jeden Datensatz und weist die Eigenschaften der Websitesammlung entsprechend den Spaltenüberschriften zu.

### <a name="create-a-csv-file"></a>Erstellen einer CSV-Datei

> [!NOTE]
> Der Parameter Resource Quota funktioniert nur auf klassischen Websites. Wenn Sie diesen Parameter für eine moderne Website verwenden, wird möglicherweise eine Warnmeldung angezeigt, dass er veraltet ist. 

1. Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Dabei ist *Mandanten* der Name Ihres Mandanten, und *Owner* ist der Benutzername des Benutzers in Ihrem Mandanten, dem Sie die Rolle des primären Websitesammlungsadministrators erteilen möchten.<br/>(Sie können Strg + H drücken, wenn Sie den Editor verwenden, um schneller Massen zu ersetzen.)<br/>

2. Speichern Sie die Datei auf Ihrem Desktop als **SiteCollections.csv**.<br/>

> [!TIP]
> Bevor Sie diese oder eine andere CSV-oder Windows PowerShell-Skriptdatei verwenden, sollten Sie sicherstellen, dass keine fremden oder nicht druckbaren Zeichen vorhanden sind. Öffnen Sie die Datei in Word und klicken Sie auf dem Menüband auf das Symbol Absatz, um nicht druckbare Zeichen anzuzeigen. Es sollten keine überflüssigen, nicht druckbaren Zeichen vorhanden sein. Es sollten beispielsweise keine Absatzmarken nach dem letzten Absatz am Ende der Datei vorkommen.

### <a name="run-the-windows-powershell-command"></a>Ausführen des PowerShell-Befehls

1. Geben Sie an der Windows PowerShell Aufforderung den folgenden Befehl ein, oder kopieren und fügen Sie ihn ein, und drücken Sie die EINGABETASTE:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Wobei *myalias* Ihrem Benutzer Alias entspricht.<br/>

2. Warten Sie, bis die Windows PowerShell-Eingabeaufforderung wieder erscheint. Dies kann einige Minuten dauern.<br/>

3. Bei Aufforderung durch Windows PowerShell geben Sie das folgende Cmdlet ein, oder kopieren und fügen Sie es ein, und drücken Sie die EINGABETASTE:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Beachten Sie die neuen Websitesammlungen in der Liste. Mithilfe unserer CSV-Beispieldatei werden die folgenden Websitesammlungen angezeigt: **TeamSite01**, **Blog01**, **Project01**und **Community01**

Fertig! Sie haben mehrere Websitesammlungen mit der von Ihnen erstellten CSV-Datei und einem einzelnen Windows PowerShell-Befehl erstellt. Sie können jetzt Benutzer erstellen und zu diesen Websites hinzufügen.

## <a name="step-2-add-users-and-groups"></a>Schritt 2: Hinzufügen von Benutzern und Gruppen

Sie werden nun Benutzer erstellen und sie zu einer Websitesammlungsgruppe hinzufügen. Sie werden danach mithilfe einer .csv-Datei große Mengen an neuen Gruppen und Benutzern hochladen.

Die folgenden Verfahren werden weiterhin mit den Beispiel Standorten TeamSite01, Blog01, Project01 und Community01 verwendet.

### <a name="create-csv-and-ps1-files"></a>Erstellen von CSV und ps1-Dateien

1. Öffnen Sie den Editor und fügen Sie den folgenden Textblock ein:<br/>

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
<br/>Wobei *Mandanten* Ihrem Mandantennamen entspricht.<br/>

2. Speichern Sie die Datei auf Ihrem Desktop als **GroupsAndPermissions.csv**.<br/>

3. Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:<br/>

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
<br/>Dabei ist *Mandant* gleich ihrem Mandantennamen, und *username* entspricht dem Benutzernamen eines vorhandenen Benutzers.<br/>

4. Speichern Sie die Datei auf Ihrem Desktop als **Users.csv**.<br/>

5. Öffnen Sie eine neue Instanz von Notepad und fügen Sie den folgenden Textblock ein:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Dabei entspricht myalias dem Benutzernamen des derzeit angemeldeten Benutzers.<br/>

6. Speichern Sie die Datei auf Ihrem Desktop als **UsersAndGroups.ps1**. Das ist ein einfaches Windows PowerShell-Skript.

Sie können jetzt das Skript UsersAndGroup.ps1 durchlaufen lassen, um Benutzer und Gruppen zu mehreren Websitesammlungen hinzuzufügen.

### <a name="run-usersandgroupsps1-script"></a>Ausführen von Skript UsersAndGroups.ps1

1. Gehen Sie zurück zu der SharePoint Online-Verwaltungsshell.<br/>
2. Bei Aufforderung durch Windows PowerShell geben sie die folgende Zeile ein, oder kopieren und fügen Sie sie ein, und drücken Sie die EINGABETASTE:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. Drücken Sie an der Bestätigungsaufforderung **Y**.<br/>

4. Bei Aufforderung durch Windows PowerShell geben Sie Folgendes ein oder kopieren und fügen es ein, und drücken Sie die EINGABETASTE:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Wobei *myalias* Ihrem Benutzernamen entspricht.<br/>

5. Warten Sie, bis die Eingabeaufforderung wieder erscheint, bevor Sie fortfahren. Zuerst werden Sie die Gruppen sehen, sobald diese erstellt sind. Sobald Benutzer hinzugefügt werden, sehen Sie wiederholt die Gruppenliste.

## <a name="see-also"></a>Siehe auch

[Herstellen einer Verbindung mit SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Verwalten von SharePoint Online-Websitegruppen mit PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
