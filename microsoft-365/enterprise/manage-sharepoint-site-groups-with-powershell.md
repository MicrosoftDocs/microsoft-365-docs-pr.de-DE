---
title: Verwalten von SharePoint Online-Websitegruppen mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: In diesem Artikel finden Sie Verfahren für die Verwendung von PowerShell für Microsoft 365 zum Verwalten SharePoint Online-Websitegruppen.
ms.openlocfilehash: 383536a6ad5ac5742cf1e38081a9be984ce4806b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289079"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Verwalten von SharePoint Online-Websitegruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Obwohl Sie die Microsoft 365 Admin Center verwenden können, können Sie auch PowerShell für Microsoft 365 verwenden, um Ihre SharePoint Online-Websitegruppen zu verwalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Für die Verfahren in diesem Artikel müssen Sie eine Verbindung mit SharePoint Online herstellen. Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Anzeigen SharePoint Online mit PowerShell für Microsoft 365

Das SharePoint Online Admin Center verfügt über einige benutzerfreundliche Methoden zum Verwalten von Websitegruppen. Angenommen, Sie möchten sich die Gruppen und die Gruppenmitglieder für die `https://litwareinc.sharepoint.com/sites/finance` Website ansehen. Dazu müssen Sie Folgendes tun:

1. Klicken Sie im SharePoint Admin Center auf **"Aktive Websites"** und dann auf die URL der Website.
2. Klicken Sie auf der Websiteseite auf das **symbol Einstellungen** (in der oberen rechten Ecke der Seite), und klicken Sie dann auf **"Websiteberechtigungen".**

Wiederholen Sie dieses Verfahren für die nächste gewünschte Website.

Zum Abrufen einer Liste der Gruppen mit PowerShell für Microsoft 365 können Sie die folgenden Befehle verwenden:

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

Es gibt zwei Möglichkeiten, diesen Befehl in der Eingabeaufforderung SharePoint Onlineverwaltungsshell auszuführen:

- Kopieren Sie die Befehle in Editor (oder einen anderen Text-Editor), ändern Sie den Wert der **variablen $siteURL,** wählen Sie die Befehle aus, und fügen Sie sie dann in die Eingabeaufforderung SharePoint Online-Verwaltungsshell ein. In diesem Fall wird PowerShell bei einer **>>** Eingabeaufforderung beendet. Drücken Sie die EINGABETASTE, um den `foreach` Befehl auszuführen.<br/>
- Kopieren Sie die Befehle in Editor (oder einen anderen Text-Editor), ändern Sie den Wert der **$siteURL** Variable, und speichern Sie dann diese Textdatei mit einem Namen und der Erweiterung „.ps1“ in einem geeigneten Ordner. Führen Sie als Nächstes das Skript über die Eingabeaufforderung SharePoint Onlineverwaltungsshell aus, indem Sie den Pfad und den Dateinamen angeben. Nachfolgend sehen Sie einen Beispielbefehl:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

In beiden Fällen wird Folgendes angezeigt.

![SharePoint Onlinewebsitegruppen](../media/SPO-site-groups.png)

Dies sind alle Gruppen, die für die Website erstellt `https://litwareinc.sharepoint.com/sites/finance` wurden, und alle Benutzer, die diesen Gruppen zugewiesen sind. Die Gruppennamen werden in gelb dargestellt, damit Sie die Gruppennamen von den Mitgliedern leicht unterscheiden können.

Ein weiteres Beispiel ist ein Befehlssatz, der die Gruppen und alle Gruppenmitgliedschaften für alle Ihre SharePoint Onlinewebsites auflistet.

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```

## <a name="see-also"></a>Weitere Informationen:

[Herstellen einer Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Verwalten SharePoint Onlinebenutzer und -gruppen mit PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
