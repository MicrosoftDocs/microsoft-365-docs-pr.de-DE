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
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Verwalten SharePoint Onlinebenutzern und -gruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie ein SharePoint online-Administrator sind, der mit großen Listen von Benutzerkonten oder Gruppen arbeitet und eine einfachere Möglichkeit zum Verwalten dieser Konten möchte, können Sie PowerShell für Microsoft 365. 

Bevor Sie beginnen, müssen Sie für die Verfahren in diesem Thema eine Verbindung mit SharePoint Online herstellen. Anweisungen finden Sie [unter Verbinden to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="get-a-list-of-sites-groups-and-users"></a>Eine Liste der Websites, Gruppen und Benutzer erhalten

Bevor wir mit der Verwaltung von Benutzern und Gruppen beginnen, müssen Sie Listen Ihrer Websites, Gruppen und Benutzer erhalten. Anschließend können Sie diese Informationen verwenden, um das Beispiel in diesem Artikel zu durcharbeiten.

Mit diesem Befehl können Sie eine Liste der Websites in Ihrem Mandanten erhalten:

```powershell
Get-SPOSite
```

Mit diesem Befehl erhalten Sie eine Liste der Gruppen in Ihrem Mandanten:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Mit diesem Befehl erhalten Sie eine Liste der Benutzer in Ihrem Mandanten:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Hinzufügen eines Benutzers zur Gruppe "Websitesammlungsadministratoren"

Sie verwenden das Cmdlet, um der Liste der Websitesammlungsadministratoren in einer Websitesammlung einen `Set-SPOUser` Benutzer hinzuzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Um diese Befehle zu verwenden, ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich < und > Zeichen, durch die richtigen Namen.

Mit diesem Befehlssatz wird beispielsweise Opal Castillo (Benutzername opalc) zur Liste der Websitesammlungsadministratoren in der ContosoTest-Websitesammlung im Mandanten Contoso hinzugefügt:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Sie können diese Befehle kopieren und in Editor einfügen, die Variablenwerte für $tenant, $site und $user in tatsächliche Werte aus Ihrer Umgebung ändern und diese dann in das Fenster SharePoint Online Management Shell einfügen, um sie auszuführen.

## <a name="add-a-user-to-other-site-collection-groups"></a>Hinzufügen eines Benutzers zu anderen Websitesammlungsgruppen

In dieser Aufgabe verwenden wir das Cmdlet, um einen Benutzer zu einer SharePoint `Add-SPOUser` einer Websitesammlung hinzuzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Fügen wir beispielsweise Der Gruppe "Auditor" in der ContosoTest-Websitesammlung im Mandanten contoso "Glen Rife" (Benutzername glenr) hinzu:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Erstellen einer Websitesammlungsgruppe

Mit dem Cmdlet können Sie eine neue SharePoint erstellen und `New-SPOSiteGroup` einer Websitesammlung hinzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Gruppeneigenschaften, z. B. Berechtigungsstufen, können später mithilfe des `Set-SPOSiteGroup` Cmdlets aktualisiert werden.

Fügen wir beispielsweise die Gruppe "Auditoren" mit den Berechtigungen Nur anzeigen der contosotest-Websitesammlung im Mandanten contoso hinzu:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Entfernen von Benutzern aus einer Gruppe

Manchmal müssen Sie einen Benutzer von einer Website oder sogar von allen Websites entfernen. Vielleicht wechselt der Mitarbeiter von einer Abteilung in eine andere oder verlässt das Unternehmen. Sie können dies für einen Mitarbeiter problemlos auf der Benutzeroberfläche tun, aber dies ist nicht einfach, wenn Sie eine vollständige Abteilung von einem Standort zu einem anderen verschieben müssen.

Mithilfe der SharePoint online-Verwaltungsshell und -CSV-Dateien ist dies jedoch schnell und einfach. In dieser Aufgabe verwenden Sie Windows PowerShell, um einen Benutzer aus einer Sicherheitsgruppe für Websitesammlungen zu entfernen. Anschließend verwenden Sie eine CSV-Datei und entfernen viele Benutzer von verschiedenen Websites. 

Wir verwenden das Cmdlet "Remove-SPOUser", um einen einzelnen Microsoft 365-Benutzer aus einer Websitesammlungsgruppe zu entfernen, damit die Befehlssyntax angezeigt wird. Die Syntax sieht wie folgt aus:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Entfernen wir beispielsweise "Bobby Overby" aus der Gruppe "Auditoren" der Websitesammlung in der contosotest-Websitesammlung im Mandanten contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Angenommen, wir wollten "Bobby" aus allen Gruppen entfernen, in der er sich derzeit befindet. Hier sehen Sie, wie wir dies tun würden:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Dies ist nur ein Beispiel. Sie sollten diesen Befehl nur ausführen, wenn Sie wirklich einen Benutzer aus jeder Gruppe entfernen müssen, z. B. wenn der Benutzer das Unternehmen verlässt.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatisieren der Verwaltung großer Listen von Benutzern und Gruppen

Zum Hinzufügen einer großen Anzahl von Konten zu SharePoint Websites und zum Erteilen von Berechtigungen können Sie das Microsoft 365 Admin Center, einzelne PowerShell-Befehle oder PowerShell eine CSV-Datei verwenden. Bei diesen Optionen ist die CSV-Datei die schnellste Möglichkeit, diese Aufgabe zu automatisieren.

Der grundlegende Prozess besteht im Erstellen einer CSV-Datei mit Kopfzeilen (Spalten), die den Parametern entsprechen, die das Windows PowerShell benötigt. Sie können eine solche Liste ganz einfach in Excel erstellen und dann als CSV-Datei exportieren. Anschließend verwenden Sie ein Windows PowerShell-Skript, um Datensätze (Zeilen) in der CSV-Datei zu durch iterieren und die Benutzer zu Gruppen und die Gruppen zu Websites zu hinzufügen. 

Erstellen wir beispielsweise eine CSV-Datei, um eine Gruppe von Websitesammlungen, Gruppen und Berechtigungen zu definieren. Als Nächstes erstellen wir eine CSV-Datei, um die Gruppen mit Benutzern zu füllen. Schließlich erstellen und führen wir ein einfaches Skript Windows PowerShell, das die Gruppen erstellt und auffüllt.

Die erste CSV-Datei fügt einer oder mehreren Websitesammlungen eine oder mehrere Gruppen hinzu und hat diese Struktur:

Header:

```powershell
Site,Group,PermissionLevels
```

Element:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Hier ist eine Beispieldatei:

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

Die zweite CSV-Datei fügt einer oder mehreren Gruppen einen oder mehrere Benutzer hinzu und hat diese Struktur:

Header:

```powershell
Group,LoginName,Site
```

Element:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Hier ist eine Beispieldatei:

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

Für den nächsten Schritt müssen die beiden CSV-Dateien auf dem Laufwerk gespeichert sein. Hier sind Beispielbefehle, die sowohl CSV-Dateien als auch Zum Hinzufügen von Berechtigungen und Gruppenmitgliedschaften verwenden:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Das Skript importiert den Inhalt der CSV-Datei und verwendet die Werte in den Spalten, um die Parameter der **Befehle New-SPOSiteGroup** und **Add-SPOUser auffüllen** zu können. In unserem Beispiel speichern wir dies im OrdnerO365Admin auf Laufwerk C, aber Sie können es speichern, wo immer Sie möchten.

Nun entfernen wir eine Reihe von Personen für mehrere Gruppen an verschiedenen Websites mit derselben CSV-Datei. Nachfolgend sehen Sie einen Beispielbefehl:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Generieren von Benutzerberichten

Sie können einen einfachen Bericht für einige wenige Websites erhalten und die Benutzer für diese Websites, deren Berechtigungsstufe und andere Eigenschaften anzeigen. Die Syntax sieht wie folgt aus:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Dadurch werden die Daten für diese drei Websites gespeichert und in eine Textdatei auf Dem lokalen Laufwerk geschrieben. Beachten Sie, dass der Parameter –Append einer vorhandenen Datei neuen Inhalt hinzugibt.

Führen wir beispielsweise einen Bericht auf den Standorten ContosoTest, TeamSite01 und Project01 für den Contoso1-Mandanten aus:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Beachten Sie, dass wir nur die $site **ändern** mussten. Die **$tenant-Variable** behält ihren Wert in allen drei Durchläufen des Befehls bei.

Was aber, wenn Sie dies für jede Website tun möchten? Sie können dies tun, ohne alle diese Websites mit diesem Befehl eingeben zu müssen:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Dieser Bericht ist recht einfach, und Sie können mehr Code hinzufügen, um spezifischere Berichte oder Berichte zu erstellen, die ausführlichere Informationen enthalten. Dies sollte Ihnen jedoch eine Vorstellung davon geben, wie Sie die SharePoint Online-Verwaltungsshell zum Verwalten von Benutzern in der SharePoint Onlineumgebung verwenden.
   
## <a name="see-also"></a>Siehe auch

[Herstellen einer Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Verwalten von SharePoint Online mit PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)