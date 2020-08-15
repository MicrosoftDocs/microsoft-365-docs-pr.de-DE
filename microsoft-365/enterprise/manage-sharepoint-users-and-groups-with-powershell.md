---
title: Verwalten von SharePoint Online-Benutzern und-Gruppen mit PowerShell
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
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell für Microsoft 365 SharePoint Online-Benutzer,-Gruppen und-Websites verwalten können.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690741"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Verwalten von SharePoint Online-Benutzern und-Gruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie ein SharePoint Online Administrator sind, der mit umfangreichen Listen mit Benutzerkonten oder Gruppen arbeitet und eine einfachere Verwaltung wünscht, können Sie PowerShell für Microsoft 365 verwenden. 

Bevor Sie beginnen, müssen Sie mit den Verfahren in diesem Thema eine Verbindung mit SharePoint Online herstellen. Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) .

## <a name="get-a-list-of-sites-groups-and-users"></a>Abrufen einer Liste von Websites, Gruppen und Benutzern

Bevor wir mit der Verwaltung von Benutzern und Gruppen beginnen, müssen Sie Listen mit Websites, Gruppen und Benutzern abrufen. Anschließend können Sie diese Informationen verwenden, um das Beispiel in diesem Artikel zu bearbeiten.

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

Verwenden Sie das `Set-SPOUser` Cmdlet, um einen Benutzer zur Liste der Websitesammlungsadministratoren in einer Websitesammlung hinzuzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Um diese Befehle zu verwenden, ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der < und > Zeichen, mit den richtigen Namen.

Beispielsweise fügt dieser Befehlssatz der Liste der Websitesammlungsadministratoren in der ContosoTest-Websitesammlung im Contoso-Mandanten Opal Castillo (Benutzername opalc) hinzu:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Sie können diese Befehle Kopieren und in Editor einfügen, die Variablenwerte für $Tenant, $Site und $User auf Istwerte aus Ihrer Umgebung ändern und diese dann in das SharePoint Online Verwaltungsshell-Fenster einfügen, um Sie auszuführen.

## <a name="add-a-user-to-other-site-collection-groups"></a>Hinzufügen eines Benutzers zu anderen Website Sammlungsgruppen

In dieser Aufgabe verwenden wir das `Add-SPOUser` Cmdlet zum Hinzufügen eines Benutzers zu einer SharePoint-Gruppe in einer Websitesammlung.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Lassen Sie uns beispielsweise Glen weit verbreitet (Benutzername glenr) der Gruppe "Auditors" in der ContosoTest-Websitesammlung im Contoso-Mandanten hinzufügen:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Erstellen einer Website Sammlungs Gruppe

Verwenden Sie das `New-SPOSiteGroup` Cmdlet, um eine neue SharePoint-Gruppe zu erstellen und zu einer Websitesammlung hinzuzufügen.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Gruppeneigenschaften wie Berechtigungsstufen können später mithilfe des `Set-SPOSiteGroup` Cmdlets aktualisiert werden.

Lassen Sie uns beispielsweise die Gruppe "Auditors" mit Berechtigungen "nur anzeigen" für die ContosoTest-Websitesammlung in der Contoso-Mandantschaft hinzufügen:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Entfernen von Benutzern aus einer Gruppe

Manchmal müssen Sie einen Benutzer aus einer Website oder sogar aus allen Websites entfernen. Vielleicht bewegt sich der Mitarbeiter von einer Abteilung in eine andere oder verlässt das Unternehmen. Sie können dies für einen Mitarbeiter problemlos in der Benutzeroberfläche durchführen, dies ist jedoch nicht leicht möglich, wenn Sie eine vollständige Abteilung von einer Website zu einer anderen migrieren müssen.

Durch die Verwendung der SharePoint Online-Verwaltungsshell und CSV-Dateien ist dies jedoch schnell und einfach. In dieser Aufgabe verwenden Sie Windows PowerShell, um einen Benutzer aus einer Sicherheitsgruppe für Websitesammlungen zu entfernen. Anschließend verwenden Sie eine CSV-Datei und entfernen viele Benutzer aus unterschiedlichen Websites. 

Wir verwenden das Cmdlet "Remove-ehegatter", um einen einzelnen Microsoft 365-Benutzer aus einer Website Sammlungs Gruppe zu entfernen, damit die Befehlssyntax angezeigt werden kann. Hier sehen Sie, wie die Syntax aussieht:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Lassen Sie uns beispielsweise Bobby Overby aus der Gruppe "Website Sammlungs Prüfer" in der ContosoTest-Websitesammlung im Contoso-Mandanten entfernen:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Angenommen, wir wollten Bobby aus allen Gruppen entfernen, in denen er sich gerade befindet. Hier ist die Vorgehensweise:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Dies ist nur ein Beispiel. Sie sollten diesen Befehl nicht ausführen, es sei denn, Sie müssen wirklich einen Benutzer aus jeder Gruppe entfernen, beispielsweise wenn der Benutzer das Unternehmen verlässt.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatisieren der Verwaltung umfangreicher Listen von Benutzern und Gruppen

Wenn Sie eine große Anzahl von Konten zu SharePoint-Websites hinzufügen und Ihnen Berechtigungen erteilen möchten, können Sie das Microsoft 365 Admin Center, einzelne PowerShell-Befehle oder PowerShell als CSV-Datei verwenden. Von diesen Optionen ist die CSV-Datei die schnellste Möglichkeit, diese Aufgabe zu automatisieren.

Der grundlegende Prozess besteht darin, eine CSV-Datei mit Kopfzeilen (Spalten) zu erstellen, die den Parametern entspricht, die das Windows PowerShell Skript benötigt. Sie können eine solche Liste ganz einfach in Excel erstellen und dann als CSV-Datei exportieren. Anschließend verwenden Sie ein Windows PowerShelles Skript zum Durchlaufen von Datensätzen (Zeilen) in der CSV-Datei und zum Hinzufügen der Benutzer zu Gruppen und den Gruppen zu Websites. 

Erstellen wir beispielsweise eine CSV-Datei zum Definieren einer Gruppe von Websitesammlungen, Gruppen und Berechtigungen. Als Nächstes erstellen wir eine CSV-Datei, mit der die Gruppen mit Benutzern aufgefüllt werden. Schließlich erstellen und führen wir ein einfaches Windows PowerShell-Skript aus, mit dem die Gruppen erstellt und aufgefüllt werden.

In der ersten CSV-Datei wird mindestens eine Gruppe zu einer oder mehreren Websitesammlungen hinzugefügt und diese Struktur erhalten:

Header

```powershell
Site,Group,PermissionLevels
```

Element

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

Die zweite CSV-Datei fügt einer oder mehreren Gruppen einen oder mehrere Benutzer hinzu und weist diese Struktur auf:

Header

```powershell
Group,LoginName,Site
```

Element

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

Für den nächsten Schritt müssen Sie die beiden CSV-Dateien auf Ihrem Laufwerk gespeichert haben. Im folgenden finden Sie Beispielbefehle, die sowohl CSV-Dateien verwenden als auch Berechtigungen und Gruppenmitgliedschaften hinzufügen:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Das Skript importiert den Inhalt der CSV-Datei und verwendet die Werte in den Spalten, um die Parameter der Befehle **New-SPOSiteGroup** und **Add-ehegatter** aufzufüllen. In unserem Beispiel speichern wir diese in theO365Admin Ordner auf Laufwerk C, aber Sie können Sie speichern, wo immer Sie möchten.

Nun können wir eine Gruppe von Personen für mehrere Gruppen in verschiedenen Websites mit derselben CSV-Datei entfernen. Nachfolgend sehen Sie einen Beispielbefehl:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Generieren von Benutzer berichten

Möglicherweise möchten Sie einen einfachen Bericht für einige Websites erhalten und die Benutzer für diese Websites, ihre Berechtigungsstufe und andere Eigenschaften anzeigen. So sieht die Syntax aus:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Dadurch werden die Daten für diese drei Standorte erfasst und in eine Textdatei auf Ihrem lokalen Laufwerk geschrieben. Beachten Sie, dass mit dem Parameter – Append neue Inhalte zu einer vorhandenen Datei hinzugefügt werden.

Lassen Sie uns beispielsweise einen Bericht über die ContosoTest-, TeamSite01-und Project01-Websites für den Contoso1-Mandanten ausführen:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Beachten Sie, dass nur die **$Site** Variable geändert werden musste. Die **$Tenant** -Variable behält ihren Wert über alle drei Ausführungen des Befehls bei.

Was jedoch, wenn Sie dies für jede Website tun wollten? Sie können dies tun, ohne alle diese Websites mithilfe dieses Befehls eingeben zu müssen:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Dieser Bericht ist ziemlich einfach, und Sie können weitere Code hinzufügen, um spezifischere Berichte oder Berichte zu erstellen, die detailliertere Informationen enthalten. Dies sollte Ihnen jedoch eine Vorstellung davon geben, wie Sie die SharePoint Online-Verwaltungsshell zum Verwalten von Benutzern in der SharePoint Online Umgebung verwenden.
   
## <a name="see-also"></a>Siehe auch

[Herstellen einer Verbindung mit SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Verwalten von SharePoint Online mit PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
