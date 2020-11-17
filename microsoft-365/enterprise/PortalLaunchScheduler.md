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
ms.openlocfilehash: 6a191cf323e180fa77614eb09bae4185228a5029
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087667"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Starten Ihres Portals mithilfe des Portal-Start Planungsmoduls

Bei einem Portal handelt es sich um eine SharePoint-Website in Ihrem Intranet mit einer großen Anzahl von Websitebenutzern, die Inhalte auf der Website nutzen. Das Starten Ihres Portals in Wellen ist ein wichtiger Bestandteil, um sicherzustellen, dass Benutzer über eine reibungslose und leistungsfähige Erfahrung beim Zugriff auf ein neues SharePoint Online Portal verfügen. 

Das Starten in Waves ist eine wichtige Möglichkeit zum Rollout Ihres Portals, wie im Abschnitt [Planen des Rollout Plans für die Portal Einführung in SharePoint Online](https://docs.microsoft.com/en-us/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)beschrieben. Der Start Planer des Portals soll Ihnen dabei helfen, einen Wave/Phasen-Roll-Out-Ansatz zu verfolgen, indem Sie die Umleitungen für das neue Portal verwalten. Während jeder Wellen Phase können Sie Benutzer Feedback erfassen und die Leistung während der einzelnen Bereitstellungsphasen überwachen. Dies hat den Vorteil, dass Sie das Portal langsam einführen und Ihnen die Möglichkeit geben, Probleme zu unterbrechen und zu beheben, bevor Sie mit der nächsten Welle fortfahren, und letztendlich eine positive Benutzererfahrung sicherzustellen. 

Es gibt zwei Arten von Umleitungen: 
- Bidirektional: Einführung eines neuen modernen SharePoint Online-Portals zum Ersetzen eines vorhandenen SharePoint-Klassikers oder modernen Portals 
- temporäre seitenumleitung: Einführung eines neuen modernen SharePoint Online-Portals ohne vorhandenes SharePoint-Portal

Der Start Planer des Portals steht nur für moderne SharePoint Online-Portale zur Verfügung, wie Kommunikationswebsites und moderne Teamwebsites. Starts müssen mindestens 7 Tage im Voraus geplant werden. Die Anzahl der erforderlichen Wellen wird durch die erwartete Anzahl von Benutzern bestimmt. Vor dem Planen eines Portal Starts muss das [Tool Seite Diagnostics für SharePoint](https://aka.ms/perftool) ausgeführt werden, um zu überprüfen, ob die Homepage im Portal fehlerfrei ist. Am Ende des Starts des Portals können alle Benutzer mit Berechtigungen für die Website auf die neue Website zugreifen. 

Weitere Informationen zum Starten eines erfolgreichen Portals finden Sie Untergrund Legende Prinzipien, Vorgehensweisen und Empfehlungen, die unter [Creating, Launching and maintaine a healthy Portal](https://docs.microsoft.com/sharepoint/portal-health)beschrieben werden. 

> [!NOTE]
> Dieses Feature ist nicht verfügbar für Office 365 Deutschland, Office 365 betrieben von 21Vianet (China) oder Microsoft 365 US Government Plans.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Einrichten von apps und Herstellen einer Verbindung mit SharePoint Online
1. [Neueste Microsoft Office SharePoint Online-Verwaltungsshell herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Wenn Sie eine frühere Version der Microsoft Office SharePoint Online-Verwaltungsshell installiert haben, gehen Sie zu Programme hinzufügen oder entfernen und deinstallieren Sie "SharePoint Online-Verwaltungsshell".<br>Wählen Sie auf der Seite Download Center Ihre Sprache aus, und klicken Sie dann auf „Herunterladen“. Wählen Sie eine x64- oder eine x86-MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie mit der 64-Bit-Version von Windows arbeiten, oder die x86-Datei, wenn Sie mit der 32-Bit-Version arbeiten. Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate. Nachdem die Sie die Datei heruntergeladen haben, führen Sie die Datei aus und folgen Sie den Schritten im Setup-Assistenten.

2. Stellen Sie eine Verbindung zu Microsoft Office SharePoint Online als [Globaler Admin oder Microsoft Office SharePoint Online-Admin](/sharepoint/sharepoint-admin-role) in Microsoft 365 her. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Anzeigen aller vorhandenen Portal-Start-Setups

So prüfen Sie, ob es vorhandene Portal Startkonfigurationen gibt:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Planen eines Portal Starts auf der Website

Die Anzahl der erforderlichen Wellen hängt von der erwarteten Startgröße ab. 
- Weniger als 10.000 Benutzer: 1 Welle
- 10K bis 30K Benutzer: 3 Wellen 
- 30K + to 100K users: 5 Waves
- Mehr als 100K Benutzer: 5 Wellen und wenden Sie sich an Ihr Microsoft-Konto Team

### <a name="steps-for-bi-directional-redirection"></a>Schritte für die bidirektionale Umleitung

Die bidirektionale Umleitung umfasst die Einführung eines neuen modernen SharePoint Online-Portals zum Ersetzen eines vorhandenen SharePoint-Klassikers oder modernen Portals. Benutzer in aktiven Wellen werden an die neue Website umgeleitet, unabhängig davon, ob Sie zu der alten oder neuen Website navigieren. Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zuzugreifen, werden zurück an die alte Website umgeleitet, bis Ihre Wave gestartet wird. Wenn Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass Sie mit dem Parameter aufgelistet werden `WaveOverrideUsers` . 

So migrieren Sie Benutzer von einer vorhandenen SharePoint-Website zu einer neuen SharePoint-Website in einer stufenweise:

1. Führen Sie den folgenden Befehl aus, um Portal Start Wellen festzulegen.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Beispiel:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Vollständige Überprüfung. Es kann 5-10 Minuten dauern, bis die Umleitung seine Konfiguration im gesamten Dienst abgeschlossen hat. 

### <a name="steps-for-redirection-to-temporary-page"></a>Schritte für die Umleitung zu einer temporären Seite

Die temporäre seitenumleitung sollte verwendet werden, wenn kein vorhandenes SharePoint-Portal vorhanden ist. Benutzer werden in einer inszenierten Weise zu einem neuen modernen SharePoint Online Portal geleitet. Wenn sich ein Benutzer in einer Welle befindet, die noch nicht gestartet wurde, wird er an eine temporäre Seite (eine beliebige URL) umgeleitet. 

1. Führen Sie den folgenden Befehl aus, um Portal Start Wellen festzulegen.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Beispiel:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Vollständige Überprüfung. Es kann 5-10 Minuten dauern, bis die Umleitung seine Konfiguration im gesamten Dienst abgeschlossen hat. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Anhalten oder Neustarten eines Portal Starts auf der Website

1. Führen Sie den folgenden Befehl aus, um den laufenden Start des Portals anzuhalten und vorübergehend bevorstehende Wellen Progressionen zu verhindern:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Überprüfen Sie, dass alle Benutzer an die alte Website umgeleitet werden. 

3. Führen Sie den folgenden Befehl aus, um einen angehenden Portal Start neu zu starten:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde. 

## <a name="delete-a-portal-launch-on-the-site"></a>Löschen eines Portal Starts auf der Website
1. Erstellen Sie eine Portal Start Wave.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Führen Sie den folgenden Befehl aus, um einen geplanten oder laufenden Portal Start für eine Website zu löschen.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Überprüfen Sie, dass keine Umleitung für alle Benutzer erfolgt.

## <a name="learn-more"></a>Weitere Informationen
[Planen des Rollout Plans für den Portal Start in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
