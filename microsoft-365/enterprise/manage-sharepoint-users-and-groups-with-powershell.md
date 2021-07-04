---
title: Verwalten SharePoint Onlinebenutzer und -gruppen mit PowerShell
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
description: In diesem Artikel erfahren Sie, wie Sie PowerShell für Microsoft 365 verwenden, um SharePoint Onlinebenutzer, -gruppen und -websites zu verwalten.
ms.openlocfilehash: 823c5fdc9af178a2e8ea8f0ca4c63fbfa4673dd8
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289055"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Verwalten SharePoint Onlinebenutzer und -gruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie ein SharePoint Onlineadministrator sind, der mit großen Listen von Benutzerkonten oder Gruppen arbeitet und eine einfachere Möglichkeit zum Verwalten möchte, können Sie PowerShell für Microsoft 365 verwenden.

Bevor Sie beginnen, müssen Sie bei den Verfahren in diesem Thema eine Verbindung mit SharePoint Online herstellen. Anweisungen finden Sie unter [Verbinden zu SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="get-a-list-of-sites-groups-and-users"></a>Abrufen einer Liste von Websites, Gruppen und Benutzern

Bevor wir mit der Verwaltung von Benutzern und Gruppen beginnen, müssen Sie Listen Ihrer Websites, Gruppen und Benutzer abrufen. Anhand dieser Informationen können Sie das Beispiel in diesem Artikel durcharbeiten.

Rufen Sie mit dem folgenden Befehl eine Liste der Websites in Ihrem Mandanten ab:

```powershell
Get-SPOSite
```

Rufen Sie mit dem folgenden Befehl eine Liste der Gruppen in Ihrem Mandanten ab:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Rufen Sie mit dem folgenden Befehl eine Liste der Benutzer in Ihrem Mandanten ab:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Hinzufügen eines Benutzers zur Gruppe "Websitesammlungsadministratoren"

Mit dem Cmdlet können Sie `Set-SPOUser` der Liste der Websitesammlungsadministratoren in einer Websitesammlung einen Benutzer hinzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Um diese Befehle zu verwenden, ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der < und > Zeichen, durch die richtigen Namen.

Mit diesem Befehlssatz wird z. B. Opal Legacy (Benutzername opalc) zur Liste der Websitesammlungsadministratoren in der ContosoTest-Websitesammlung im Contoso-Mandanten hinzugefügt:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Sie können diese Befehle kopieren und in Editor einfügen, die Variablenwerte für $tenant, $site und $user in tatsächliche Werte aus Ihrer Umgebung ändern und dann in das Fenster SharePoint Online-Verwaltungsshell einfügen, um sie auszuführen.

## <a name="add-a-user-to-other-site-collection-groups"></a>Hinzufügen eines Benutzers zu anderen Websitesammlungsgruppen

Für diese Aufgabe verwenden wir das `Add-SPOUser` Cmdlet, um einen Benutzer zu einer SharePoint Gruppe in einer Websitesammlung hinzuzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Fügen wir beispielsweise der Gruppe "Auditoren" in der ContosoTest-Websitesammlung im Contoso-Mandanten Denk rife (Benutzername) hinzu:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Erstellen einer Websitesammlungsgruppe

Mit dem Cmdlet erstellen Sie `New-SPOSiteGroup` eine neue SharePoint Gruppe und fügen sie einer Websitesammlung hinzu.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

Gruppeneigenschaften, z. B. Berechtigungsstufen, können später mithilfe des Cmdlets aktualisiert `Set-SPOSiteGroup` werden.

Fügen wir beispielsweise die Gruppe "Auditoren" mit den Berechtigungen "Nur anzeigen" zur contosotest-Websitesammlung im Mandanten contoso hinzu:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Entfernen von Benutzern aus einer Gruppe

Manchmal müssen Sie einen Benutzer von einer Website oder sogar allen Websites entfernen. Vielleicht wechselt der Mitarbeiter von einer Abteilung in eine andere oder verlässt das Unternehmen. Sie können dies für einen Mitarbeiter ganz einfach in der Benutzeroberfläche tun, aber dies ist nicht einfach, wenn Sie eine vollständige Abteilung von einer Website an eine andere verschieben müssen.

Durch die Verwendung der SharePoint Online-Verwaltungsshell und CSV-Dateien ist dies jedoch schnell und einfach. Für diese Aufgabe verwenden Sie Windows PowerShell, um einen Benutzer aus einer Sicherheitsgruppe für Websitesammlungen zu entfernen. Anschließend verwenden Sie eine CSV-Datei und entfernen viele Benutzer von verschiedenen Websites.

Wir verwenden das Cmdlet "Remove-SPOUser", um einen einzelnen Microsoft 365 Benutzer aus einer Websitesammlungsgruppe zu entfernen, damit die Befehlssyntax angezeigt wird. Die Syntax sieht wie folgt aus:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Entfernen wir beispielsweise Bobby Overby aus der Gruppe "Auditoren der Websitesammlung" in der contosotest-Websitesammlung im Mandanten "contoso":

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Angenommen, wir möchten Bobby aus allen Gruppen entfernen, in denen er sich gerade befindet. Hier sehen Sie, wie wir dies tun würden:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Dies ist nur ein Beispiel. Sie sollten diesen Befehl nur ausführen, wenn Sie wirklich einen Benutzer aus jeder Gruppe entfernen müssen, z. B. wenn der Benutzer das Unternehmen verlässt.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatisieren der Verwaltung großer Listen von Benutzern und Gruppen

Um eine große Anzahl von Konten zu SharePoint Websites hinzuzufügen und ihnen Berechtigungen zu erteilen, können Sie die Microsoft 365 Admin Center, einzelne PowerShell-Befehle oder PowerShell eine CSV-Datei verwenden. Unter diesen Optionen ist die CSV-Datei die schnellste Möglichkeit, diese Aufgabe zu automatisieren.

Der grundlegende Prozess besteht darin, eine CSV-Datei mit Kopfzeilen (Spalten) zu erstellen, die den Parametern entsprechen, die das Windows PowerShell Skript benötigt. Sie können eine solche Liste ganz einfach in Excel erstellen und dann als CSV-Datei exportieren. Anschließend verwenden Sie ein Windows PowerShell Skript, um Datensätze (Zeilen) in der CSV-Datei zu durchlaufen und die Benutzer zu Gruppen und die Gruppen zu Websites hinzuzufügen.

Erstellen wir beispielsweise eine CSV-Datei, um eine Gruppe von Websitesammlungen, Gruppen und Berechtigungen zu definieren. Als Nächstes erstellen wir eine CSV-Datei, um die Gruppen mit Benutzern aufzufüllen. Schließlich erstellen und führen wir ein einfaches Windows PowerShell Skript aus, das die Gruppen erstellt und auffüllt.

Die erste CSV-Datei fügt eine oder mehrere Gruppen zu einer oder mehreren Websitesammlungen hinzu und weist diese Struktur auf:

Header:

```powershell
Site,Group,PermissionLevels
```

Artikel:

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

Die zweite CSV-Datei fügt einen oder mehrere Benutzer zu einer oder mehreren Gruppen hinzu und weist diese Struktur auf:

Header:

```powershell
Group,LoginName,Site
```

Artikel:

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

Für den nächsten Schritt müssen die beiden CSV-Dateien auf Ihrem Laufwerk gespeichert sein. Hier sind Beispielbefehle, die sowohl CSV-Dateien verwenden als auch Berechtigungen und Gruppenmitgliedschaften hinzufügen:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Das Skript importiert den Inhalt der CSV-Datei und verwendet die Werte in den Spalten, um die Parameter der Befehle **"New-SPOSiteGroup"** und **"Add-SPOUser"** aufzufüllen. In unserem Beispiel speichern wir dies im Ordner "O365Admin" auf Laufwerk C, sie können sie aber überall speichern.

Jetzt entfernen wir eine Gruppe von Personen für mehrere Gruppen auf verschiedenen Websites, die dieselbe CSV-Datei verwenden. Nachfolgend sehen Sie einen Beispielbefehl:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Generieren von Benutzerberichten

Möglicherweise möchten Sie einen einfachen Bericht für einige Websites abrufen und die Benutzer für diese Websites, deren Berechtigungsstufe und andere Eigenschaften anzeigen. So sieht die Syntax aus:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Dadurch werden die Daten für diese drei Websites abgerufen und in eine Textdatei auf Ihrem lokalen Laufwerk geschrieben. Beachten Sie, dass der Parameter "–Append" einer vorhandenen Datei neuen Inhalt hinzufügt.

Führen wir beispielsweise einen Bericht zu den ContosoTest-, TeamSite01- und Project01-Websites für den Contoso1-Mandanten aus:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Beachten Sie, dass nur die **variable $site** geändert werden musste. Die **variable $tenant** behält ihren Wert in allen drei Ausführungen des Befehls bei.

Was aber, wenn Sie dies für jede Website tun möchten? Sie können dies tun, ohne alle diese Websites mithilfe des folgenden Befehls eingeben zu müssen:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Dieser Bericht ist ziemlich einfach, und Sie können mehr Code hinzufügen, um spezifischere Berichte oder Berichte zu erstellen, die ausführlichere Informationen enthalten. Dies sollte Ihnen jedoch eine Vorstellung davon vermitteln, wie Sie die SharePoint Online-Verwaltungsshell verwenden können, um Benutzer in der SharePoint Onlineumgebung zu verwalten.

## <a name="see-also"></a>Weitere Informationen:

[Herstellen einer Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Verwalten von SharePoint Online mit PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
