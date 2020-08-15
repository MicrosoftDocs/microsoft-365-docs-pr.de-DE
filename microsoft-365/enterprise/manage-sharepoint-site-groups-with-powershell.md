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
description: In diesem Artikel finden Sie Verfahren für die Verwendung von PowerShell für Microsoft 365 zum Verwalten von SharePoint Online Websitegruppen.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690744"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Verwalten von SharePoint Online-Websitegruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Obwohl Sie das Microsoft 365 Admin Center verwenden können, können Sie auch PowerShell für Microsoft 365 verwenden, um Ihre SharePoint Online Websitegruppen zu verwalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Für die Verfahren in diesem Artikel müssen Sie eine Verbindung mit SharePoint Online herstellen. Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Anzeigen SharePoint Online mit PowerShell für Microsoft 365

Das SharePoint Online Admin Center verfügt über einige einfach zu verwendende Methoden zum Verwalten von Websitegruppen. Nehmen wir beispielsweise an, Sie möchten die Gruppen und die Gruppenmitglieder für die `https://litwareinc.sharepoint.com/sites/finance` Website betrachten. Hier erfahren Sie, wie Sie vorgehen müssen:

1. Klicken Sie im SharePoint Admin Center auf **aktive Websites**, und klicken Sie dann auf die URL der Website.
2. Klicken Sie auf der Seite Website auf das Symbol **Einstellungen** (befindet sich in der rechten oberen Ecke der Seite), und klicken Sie dann auf **Websiteberechtigungen**.

Wiederholen Sie dieses Verfahren für die nächste gewünschte Website.

Um eine Liste der Gruppen mit PowerShell für Microsoft 365 zu erhalten, können Sie die folgenden Befehle verwenden:

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

Es gibt zwei Möglichkeiten zum Ausführen dieses Befehlssatzes in der Eingabeaufforderung der SharePoint Online Verwaltungsshell:

- Kopieren Sie die Befehle in Notepad (oder einen anderen Text-Editor), ändern Sie den Wert der **$SiteUrl** -Variablen, wählen Sie die Befehle aus, und fügen Sie Sie dann in die Eingabeaufforderung der SharePoint Online Verwaltungsshell ein. Wenn Sie dies tun, wird PowerShell an einer **>>** Eingabeaufforderung angehalten. Drücken Sie die EINGABETASTE, um den `foreach` Befehl auszuführen.<br/>
- Kopieren Sie die Befehle in Editor (oder einen anderen Text-Editor), ändern Sie den Wert der **$siteURL**Variable, und speichern Sie dann diese Textdatei mit einem Namen und der Erweiterung „.ps1“ in einem geeigneten Ordner. Führen Sie als nächstes das Skript über die Eingabeaufforderung der SharePoint Online Management Shell aus, indem Sie den Pfad und den Dateinamen angeben. Nachfolgend sehen Sie einen Beispielbefehl:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

In beiden Fällen wird Folgendes angezeigt.

![SharePoint Online Websitegruppen](../media/SPO-site-groups.png)

Dies sind alle Gruppen, die für die Website erstellt wurden `https://litwareinc.sharepoint.com/sites/finance` , sowie alle Benutzer, die diesen Gruppen zugewiesen sind. Die Gruppennamen werden in gelb dargestellt, damit Sie die Gruppennamen von den Mitgliedern leicht unterscheiden können.

Ein weiteres Beispiel ist ein Befehlssatz, der die Gruppen und alle Gruppenmitgliedschaften für alle Ihre SharePoint Online Websites auflistet.

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
    
## <a name="see-also"></a>Siehe auch

[Herstellen einer Verbindung mit SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Verwalten von SharePoint Online-Benutzern und-Gruppen mit PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

