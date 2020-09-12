---
title: Verschieben einer SharePoint-Website an einen anderen geografischen Standort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie eine SharePoint-Website an einen anderen geografischen Standort in ihrer Multi-Geo-Umgebung umstellen und die Erwartungen an die Änderungen an Ihre Benutzer weitergeben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 819496b9f7612afa1db902e6fc5a0844e99d7a8e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545636"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Verschieben einer SharePoint-Website an einen anderen geografischen Standort

Mit der geografischen Verschiebung von SharePoint-Websites können Sie SharePoint-Websites in einer Umgebung mit mehreren geografischen Standorten an andere geografische Standorte verschieben.

Die folgenden Website-Typen können zwischen geografischen Standorten verschoben werden:

- Mit einer Microsoft 365-Gruppe verbundene Websites
- Moderne Websites ohne eine Verbindung mit einer Microsoft 365-Gruppe
- Klassische SharePoint-Websites
- Kommunikationswebsites

Sie müssen ein globaler Administrator oder SharePoint-Administrator sein, um eine Website zwischen geografischen Standorten zu verschieben.

Bei der Verschiebung des geografischen Standorts einer SharePoint-Websites gibt es ein Zeitfenster von etwa 4 bis 6 Stunden, indem Schreibschutz besteht (abhängig vom Websiteinhalt).

## <a name="best-practices"></a>Bewährte Methoden

- Probieren Sie das Verschieben einer SharePoint-Website mit einer Testwebsite aus, um sich mit dem Verfahren vertraut zu machen.
- Überprüfen Sie, ob die Website vor dem Planen oder Ausführen der Verschiebung verschoben werden kann.
- Planen Sie die geografische Verschiebung von Websites möglichst außerhalb der Arbeitszeiten, um die Auswirkungen auf die Benutzer möglichst gering zu halten.
- Teilen Sie den Benutzer, die von der Verschiebung betroffen sind, vorher mit, was passiert.

## <a name="communicating-to-your-users"></a>Kommunikation mit Benutzern

Wenn Sie SharePoint-Websites zwischen geografischen Standorten verschieben, ist es wichtig, dass Sie den Benutzern der Websites (in der Regel alle Benutzer, die die Website bearbeiten können) mitteilen, was sie erwartet. Dies kann verhindern, dass es bei den Benutzern zu Verwirrung kommt und unnötige Anrufe an den Helpdesk gerichtet werden. Senden Sie vor dem Verschieben eine E-Mail an die Benutzer der Websites, und teilen Sie ihnen die folgenden Informationen mit:

- Wann die Verschiebung voraussichtlich stattfinden soll und wie lange sie dauern wird.
- An welchen geografischen Standort die Website der Benutzer verschoben wird und welche URL zum Zugreifen auf den neuen Standort verwendet wird.
- Die Benutzer sollten alle Dateien schließen und während der Verschiebung keine Änderungen vornehmen.
- Dateiberechtigungen und -freigabe ändern sich aufgrund der Verschiebung nicht.
- Erwartungen im Hinblick auf die Benutzererfahrung in einer Multi-Geo-Umgebung

Vergessen Sie nicht, den Benutzern der Websites eine E-Mail zu schicken, wenn die Verschiebung erfolgreich abgeschlossen wurde, um sie darüber zu informieren, dass sie ihre Arbeit auf den Websites fortsetzen können.

## <a name="scheduling-sharepoint-site-moves"></a>Planen der Verschiebung von SharePoint-Websites

Sie können das Verschieben von SharePoint-Websites im voraus planen (wie weiter unten in diesem Artikel beschriebenen). Sie können Verschiebungen wie folgt planen:

- Sie können bis zu 4.000 Verschiebungen zugleich planen.
- Wenn mit dem Verschieben begonnen wird, können Sie weitere planen, bis zu maximal jeweils 4.000 ausstehenden Verschiebungen in der Warteschlange.

Um das Verschieben einer SharePoint-Website für einen späteren Zeitpunkt zu planen, schließen Sie beim Beginn der Verschiebung einen der folgenden Parameter ein:

- `PreferredMoveBeginDate` – Die Verschiebung beginnt wahrscheinlich zu diesem Zeitpunkt.
- `PreferredMoveEndDate` – Die Verschiebung wird wahrscheinlich bis zu diesem Zeitpunkt abgeschlossen sein.

Die Uhrzeit muss für beide Parameter in koordinierter Weltzeit (UTC) angegeben werden.

## <a name="moving-the-site"></a>Verschieben einer Website

Die geografische Verschiebung von SharePoint-Websites setzt voraus, dass Sie eine Verbindung mit der SharePoint-Admin-URL an dem Standort herstellen, an dem sich die Website befindet, und die Verschiebung von hier aus durchführen.

Wenn beispielsweise die Website-URL lautet <https://contosohealthcare.sharepoint.com/sites/Turbines> , stellen Sie eine Verbindung mit der SharePoint-Administrator-URL her unter <https://contosohealthcare-admin.sharepoint.com> :

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Online-Verwaltungsshell-Fenster mit dem Befehl "Connect-SPOService"](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>Überprüfen der Umgebung

Wir empfehlen, vor der Planung einer Websiteverschiebung eine Prüfung durchzuführen, um sicherzustellen, dass die Website verschoben werden kann.

Das Verschieben von Websites wird nicht unterstützt mit:

- Business Connectivity Services
- InfoPath-Formularen
- Angewendete IRM-Vorlagen (Information Rights Management)

Um sicherzustellen, dass alle geografischen Standorte kompatibel sind, führen Sie `Get-SPOGeoMoveCrossCompatibilityStatus` aus. Hiermit werden alle geografischen Standorte aufgeführt, und es wird angezeigt, ob die Umgebung mit dem geografischen Zielstandort kompatibel ist.

Um für Ihre Website eine reine Überprüfung durchzuführen, verwenden Sie `Start-SPOSiteContentMove` mit dem `-ValidationOnly`-Parameter. So können Sie prüfen, ob die Website verschoben werden kann. Beispiel:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Es wird *Erfolg* zurückgegeben, wenn die Website verschoben werden kann, oder *Fehler*, wenn Bedingungen vorhanden sind, die eine Verschiebung blockieren.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Starten einer Verschiebung des geografischen Standorts einer SharePoint-Website ohne zugehöriger Microsoft 365-Gruppe

Standardmäßig ändert sich die anfängliche URL für die Website in die URL des geografischen Zielstandorts. Beispiel:

<https://Contoso.sharepoint.com/sites/projectx> in <https://ContosoEUR.sharepoint.com/sites/projectx>

Bei Websites, denen keine Microsoft 365-Gruppe zugeordnet ist, können Sie die Website mit dem `-DestinationUrl`-Parameter umbenennen. Zum Beispiel:

<https://Contoso.sharepoint.com/sites/projectx> in <https://ContosoEUR.sharepoint.com/sites/projecty>

Führe Sie Folgendes aus, um mit der Verschiebung der Website zu beginnen:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Screenshot des PowerShell-Fensters mit dem Cmdlet „Start-SPOSiteContentMove“](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Starten einer Verschiebung des geografischen Standorts einer SharePoint-Website mit zugehöriger Microsoft 365-Gruppe

Um eine Website zu verschieben, die mit einer Office 365-Gruppe verbundene ist, muss der globale Administrator oder SharePoint-Administrator zuerst das PDL-Attribut (Preferred Data Location, bevorzugter Datenspeicherort) der Office 365-Gruppe ändern.

So Legen Sie den PDL einer Microsoft 365-Gruppe fest:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

Nachdem Sie den bevorzugten Datenspeicherort aktualisiert haben, können Sie mit der Websiteverschiebung beginnen:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Abbrechen der Verschiebung des geografischen Standorts einer SharePoint-Website

Sie können die Verschiebung des geografischen Standorts einer SharePoint-Website stoppen, vorausgesetzt, dass die Verschiebung noch nicht läuft oder durch das Cmdlet `Stop-SPOSiteContentMove` abgeschlossen wurde.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Feststellen des Status SharePoint-Websiteverschiebung

Sie können den Status einer Websiteverschiebung an den geografischen Standort oder von dem geografischen Standort, mit dem Sie verbunden sind, mit den folgenden Cmdlets ermitteln:

- [Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (Websites, die nicht mit Gruppen verbunden sind)
- [Get-SPOUnifiedGroupMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (Gruppen verbundene Websites)

Verwenden Sie den `-SourceSiteUrl`-Parameter, um die Website anzugeben, für die Sie den Verschiebungsstatus anzeigen möchten.

Die Statuswerte der Verschiebung werden in der folgenden Tabelle beschrieben.

****

|Status|Beschreibung|
|---|---|
|Bereit zum Auslösen|Die Verschiebung wurde noch nicht begonnen.|
|Geplant|Die Verschiebung befindet sich in der Warteschlange, wurde aber noch nicht begonnen.|
|In Bearbeitung (n/4)|Die Verschiebung wird ausgeführt, wenn einer der folgenden Statuswerte angezeigt wird: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).|
|Success|Die Verschiebung wurde erfolgreich ausgeführt.|
|Failed|Beim Verschieben ist ein Fehler aufgetreten.|
|

Sie können auch die Option `-Verbose` anwenden, um weitere Informationen zur Verschiebung anzuzeigen.

## <a name="user-experience"></a>Benutzererfahrung

Benutzer sollten nur minimale Unterbrechungen bemerken, während ihre Website an einen anderen geografischen Standort verschoben wird. Während des Verschiebens kommt es nur zu einem kurzen, vorübergehenden schreibgeschützten Zustand, wobei vorhandene Links und Berechtigungen nach der Verschiebung weiterhin wie gewohnt funktionieren.

### <a name="site"></a>Website

Während die Verschiebung der Website durchgeführt wird, ist die Website kurzzeitig schreibgeschützt. Sobald die Verschiebung abgeschlossen ist, wird der Benutzer auf die neue Website am neuen geografischen Standort umgeleitet, wenn er auf Lesezeichen oder andere Links zur Website klickt.

### <a name="permissions"></a>Berechtigungen

Benutzer, die über Berechtigungen für die Website verfügen, können auch während des Verschiebens und nach Abschluss des Vorgangs auf die Website zugreifen.

### <a name="sync-client"></a>Synchronisierungsclient

Der Synchronisierungsclient erkennt den neuen Standort der Website nach Abschluss des Vorgangs automatisch und überträgt die Synchronisierung nahtlos auf diese Website. Der Benutzer muss sich nicht erneut anmelden oder eine andere Aktion ausführen. (Es ist Version 17.3.6943.0625 oder höher für den Synchronisierungsclient erforderlich.)

Wenn ein Benutzer eine Datei aktualisiert, während die Verschiebung ausgeführt wird, benachrichtigt der Synchronisierungsclient den Benutzer, dass Dateiuploads ausstehen, während die Verschiebung ausgeführt wird.

### <a name="sharing-links"></a>Freigabelinks

Nach Abschluss der geografischen Standortverschiebung in SharePoint werden vorhandene Freigabelinks für verschobene Dateien automatisch zu den Dateien an dem neuen geografischen Standort weitergeleitet.

### <a name="most-recently-used-files-in-office-mru"></a>Zuletzt verwendete Dateien in Office (MRU)

Nach Abschluss der Verschiebung wird der MRU-Dienst mit der Website-URL und den Inhalts-URLs aktualisiert. Dies gilt für Word, Excel und PowerPoint.

### <a name="onenote-experience"></a>OneNote-Benutzererfahrung

Der OneNote-win32-Client und die UWP (Universal) App erkennen Notizbücher automatisch und synchronisieren sie mit dem neuen Websitestandort, nachdem die Verschiebung abgeschlossen ist. Der Benutzer muss sich nicht erneut anmelden oder eine andere Aktion ausführen. Der Benutzer bemerkt die Verschiebung gegebenenfalls nur dadurch, dass das Synchronisieren von Notizbüchern fehlschlägt, wenn die Verschiebung gerade läuft. Diese Benutzererfahrung ist für die folgenden Versionen des OneNote-Clients verfügbar:

- OneNote-Win32 – Version 16.0.8326.2096 (und höher)
- OneNote UWP – Version 16.0.8431.1006 (und höher)
- Mobile OneNote-App – Version 16.0.8431.1011 (und höher)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (gilt für Websites, die mit Microsoft 365-Gruppen verbunden sind)

Wenn die Verschiebung des geografischen SharePoint-Websitestandorts abgeschlossen ist, haben Benutzer in der Teams-App Zugriff auf die Websitedateien ihrer Microsoft 365-Gruppe. Außerdem können Dateien, die vor dem Verschieben über den Teams-Chat geteilt wurden, nach Abschluss der Verschiebung weiterhin verwendet werden.

### <a name="sharepoint-mobile-app-iosandroid"></a>Mobile SharePoint-App (iOS/Android)

Die mobile SharePoint-App ist über geografische Standorte hinweg kompatibel und erkennt den neuen geografischen Standort der Website.

### <a name="sharepoint-workflows"></a>SharePoint-Workflows

SharePoint 2013-Workflows müssen erneut veröffentlicht werden, nachdem die Website verschoben wurde. SharePoint 2010-Workflows sollten auch weiterhin normal funktionieren.

### <a name="apps"></a>Apps

Wenn Sie eine Website mit Apps verschieben, müssen Sie die App am neuen geografischen Standort neu instanziieren, da die App und ihre Verbindungen am geografischen Zielstandort möglicherweise nicht verfügbar sind.

### <a name="flow"></a>Flow

In den meisten Fällen funktioniert Flow nach dem Verschieben des geografischen Standorts der SharePoint-Website. Wir empfehlen, dies nach Abschluss der Verschiebung zu testen.

### <a name="powerapps"></a>PowerApps

PowerApps müssen am Zielstandort neu erstellt werden.

### <a name="data-movement-between-geo-locations"></a>Verschieben von Daten zwischen geografischen Standorten

SharePoint verwendet Azure Blob-Speicher für Inhalte, während die mit den Websites verknüpften Metadaten und die zugehörigen Dateien in SharePoint gespeichert werden. Nachdem die Website von ihrem Quellstandort an den Zielstandort verschoben wurde, verschiebt der Dienst auch den zugehörigen Blob-Speicher. Der Blob-Speicher wird in ungefähr 40 Tagen vollständig verschoben.
