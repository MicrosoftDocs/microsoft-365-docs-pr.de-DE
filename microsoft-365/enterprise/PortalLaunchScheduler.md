---
title: Starten Ihres Portals mithilfe des Portal-Start Planungsmoduls
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In diesem Artikel wird beschrieben, wie Sie Ihr Portal mit dem Start Planer des Portals starten können.
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999579"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Starten Ihres Portals mithilfe des Portal-Start Planungsmoduls

Sie können Ihr Portal mit dem Start Planer des Portals starten, indem Sie zunächst die Möglichkeit des Mandanten Administrators validieren, ein Waves für ein neues Portal einzurichten. Anschließend kann der Administrator eine Umleitung von Anforderungen überprüfen, basierend auf dem vorhanden sein eines Benutzers in den aktiven Wellen.

Weitere Informationen zum Starten eines erfolgreichen Portals finden Sie in den Grundsätzen, Vorgehensweisen und Empfehlungen, die im Thema [erstellen, starten und Verwalten eines gesunden Portals](https://go.microsoft.com/fwlink/?linkid=2105838)erläutert werden. 

## <a name="app-setup"></a>App-Setup
1. Deinstallieren Sie, wenn ein vorhandener `Microsoft.Online.SharePoint.PowerShell` von Ihrem Computer über die Systemsteuerung vorhanden ist.
2. Im PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` -Durchlauf.

## <a name="connect-to-sharepoint-online"></a>Herstellen einer Verbindung mit SharePoint Online
1. Öffnen Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.
2. Stellen Sie eine Verbindung mit Ihrem Mandanten als Administrator her.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  Geben Sie Ihr Kennwort ein, wenn Sie dazu aufgefordert werden.

## <a name="command-to-get-an-existing-setup"></a>Befehl zum Abrufen eines vorhandenen Setups

So zeigen Sie vorhandene Portal Startkonfigurationen an:

1. Übergeben `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Übergeben Sie den zusätzlichen Parameter `-DisplayFormat Raw` , wenn die Wave-Auflistung als RAW-Eingabeformat formatiert angezeigt werden soll.

## <a name="commands-for-bi-directional-redirection"></a>Befehle für die bidirektionale Umleitung

So migrieren Sie alte Websitebenutzer in einer mehrstufigen Weise zu der neuen Website:

1. Erstellen von Portal Start Wellen
   - Dies gilt nur für die Testphase der frühen Version.
   - Um die Auswirkungen der Änderung sofort zu testen, müssen Sie sicherstellen, dass die erste Welle `LaunchDateUtc` auf das aktuelle Datum festgelegt ist. Wenn Sie dieses Flag nicht angeben, erhalten Sie eine Fehlermeldung. Dieser Fehler tritt auf, weil Starts in Production mindestens 7 Tage im Voraus geplant werden müssen.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Vollständige Überprüfung.
  - Es kann bis zu 5 Minuten dauern, bis die Umleitung seine Konfiguration über den Dienst abgeschlossen hat, warten Sie also, bevor Sie fortfahren.
  - Wenn Sie sich mit dem angegebenen Benutzer anmelden `WaveOverrideUsers` , ändert sich nichts. Sie sollten auf der Website bleiben, zu der Sie navigiert sind.
  - Melden Sie sich bei einem Benutzer an, der Teil der *SG1-Viewer* ist.
    - Navigieren Sie zur alten Website, und Sie sollten zur neuen Website umgeleitet werden.
    - Navigieren Sie zur neuen Website, und Sie sollten auf der neuen Website bleiben.
    - Melden Sie sich mit dem Benutzer in *SG2* an, und navigieren Sie zum alten Standort, und bleiben Sie auf der alten Website.
    - Navigieren Sie zur neuen Website, und Sie sollten an die alte Website umgeleitet werden.

3. Unterbrechen Sie den Portal Start.
  - Wenn Sie die Start Wellen anhalten müssen, können Sie Sie für "x" Anzahl der Tage anhalten. Wenn `Status` Sie das Flag auf Pause festlegen, werden alle bevorstehenden Wellen Progressionen verhindert. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Dadurch wird überprüft, ob alle Benutzer an die alte Website umgeleitet werden.

4. Starten Sie den Start Verlauf des Portals neu. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde.

5. Löschen Sie ein Portal-Start Setup.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Überprüfen Sie, dass keine Umleitung für alle Benutzer erfolgt.

## <a name="commands-for-redirection-to-temporary-page"></a>Befehle für die Umleitung zu einer temporären Seite

Führen Sie die folgenden Schritte aus, wenn Sie nicht über eine frühere Website verfügen und Benutzer nicht auf der neuen Portalseite landen möchten.

So erstellen Sie eine temporäre Seite auf einer der Websites:

1. Erstellen Sie eine Portal Start Wave.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Vollständige Überprüfung.

  - Warten Sie fünf Minuten, bevor Sie fortfahren, da die Ausführung der Aktion bis zu fünf Minuten dauern kann.
  - Melden Sie sich mit dem Benutzer an, der Teil der *Viewer-SG1* ist, und:
     - Navigieren Sie zur neuen Website, und Sie sollten auf der neuen Website bleiben.
     - Navigieren Sie zur Seite Temp, und Sie sollten auf der Seite Temp bleiben.
  - Melden Sie sich mit dem Benutzer an, der Teil der *Viewer-SG2* ist, und:
     - Navigieren Sie zur neuen Website, und Sie sollten zur Seite Temp umgeleitet werden.
     - Navigieren Sie zur Seite Temp, und Sie sollten auf der Seite Temp bleiben.

3. Löschen Sie ein Portal-Start Setup.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Überprüfen Sie, dass keine Umleitung für alle Benutzer erfolgt.

## <a name="learn-more"></a>Weitere Informationen
[Planen des Rollout Plans für den Portal Start in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)