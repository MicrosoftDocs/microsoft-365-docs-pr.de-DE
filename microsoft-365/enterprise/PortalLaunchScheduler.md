---
title: Starten Ihres Portals mit dem Portalstartplaner
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
description: In diesem Artikel wird beschrieben, wie Sie Ihr Portal mit dem Portalstartplaner starten können.
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926142"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Starten Ihres Portals mit dem Portalstartplaner

Bei einem Portal handelt es sich um eine SharePoint-Website in Ihrem Intranet mit einer großen Anzahl von Websitebenutzern, die Inhalte auf der Website nutzen. Das Starten Ihres Portals in Wellen ist ein wichtiger Bestandteil der Sicherstellung, dass Benutzer problemlos und performant auf ein neues SharePoint Online-Portal zugreifen können. 

Das Starten in Wellen ist eine wichtige Möglichkeit zum Rollout Ihres Portals, wie unter [Planning your portal launch roll-out plan in SharePoint Online detailliert.](./planportallaunchroll-out.md?view=o365-worldwide) Der Portalstartplaner wurde entwickelt, um Ihnen zu helfen, einen Wave-/Phase-Roll-out-Ansatz zu verfolgen, indem sie die Umleitungen für das neue Portal verwalten. Während der einzelnen Wellen können Sie Feedback von Benutzern sammeln und die Leistung während jeder Bereitstellungswelle überwachen. Dies hat den Vorteil, dass Sie das Portal langsam einführen und Ihnen die Möglichkeit geben, Probleme anzuhalten und zu beheben, bevor Sie mit der nächsten Welle fortfahren, und letztendlich eine positive Erfahrung für Ihre Benutzer zu gewährleisten. 

Es gibt zwei Arten von Umleitung: 
- bidirektional: Starten eines neuen modernen SharePoint Online-Portals, um ein vorhandenes klassisches oder modernes SharePoint-Portal zu ersetzen 
- Temporäre Seitenumleitung: Starten eines neuen modernen SharePoint Online-Portals ohne vorhandenes SharePoint-Portal

Der Portalstartplaner steht nur zum Starten moderner SharePoint Online-Portale (d. h. Kommunikationswebsites) zur Verfügung. Starts müssen mindestens 7 Tage im Voraus geplant sein. Die Anzahl der erforderlichen Wellen wird durch die erwartete Anzahl von Benutzern bestimmt. Vor dem Planen eines Portalstarts muss das Tool Seitendiagnose für [SharePoint](./page-diagnostics-for-spo.md) ausgeführt werden, um zu überprüfen, ob die Startseite im Portal fehlerfrei ist. Am Ende des Portalstarts können alle Benutzer mit Berechtigungen für die Website auf die neue Website zugreifen. 

Weitere Informationen zum Starten eines erfolgreichen Portals finden Sie unter Erstellen, Starten und Verwalten eines fehlerfreien [Portals.](/sharepoint/portal-health) 

> [!NOTE]
> Dieses Feature ist nicht für Office 365 Deutschland, Office 365 betrieben von 21Vianet (China) oder Microsoft 365 US Government-Pläne verfügbar.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Einrichten und Herstellen einer Verbindung mit SharePoint Online
1. [Neueste Microsoft Office SharePoint Online-Verwaltungsshell herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Wenn Sie eine frühere Version der Microsoft Office SharePoint Online-Verwaltungsshell installiert haben, gehen Sie zu Programme hinzufügen oder entfernen und deinstallieren Sie "SharePoint Online-Verwaltungsshell".<br>Wählen Sie auf der Seite Download Center Ihre Sprache aus, und klicken Sie dann auf „Herunterladen“. Wählen Sie eine x64- oder eine x86-MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie mit der 64-Bit-Version von Windows arbeiten, oder die x86-Datei, wenn Sie mit der 32-Bit-Version arbeiten. Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate. Nachdem die Sie die Datei heruntergeladen haben, führen Sie die Datei aus und folgen Sie den Schritten im Setup-Assistenten.

2. Stellen Sie eine Verbindung zu Microsoft Office SharePoint Online als [Globaler Admin oder Microsoft Office SharePoint Online-Admin](/sharepoint/sharepoint-admin-role) in Microsoft 365 her. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Anzeigen vorhandener Portalstarteinrichtung

So sehen Sie, ob vorhandene Portalstartkonfigurationen vorhanden sind:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Planen eines Portalstarts auf der Website

Die Anzahl der erforderlichen Wellen hängt von der erwarteten Startgröße ab. 
- Weniger als 10.000 Benutzer: 1 Welle
- Benutzer mit 10 bis 30 k: 3 Wellen 
- 30k+ bis 100k-Benutzer: 5 Wellen
- Mehr als 100.000 Benutzer: 5 Wellen, und wenden Sie sich an Ihr Microsoft-Kontoteam.

### <a name="steps-for-bidirectional-redirection"></a>Schritte für die bidirektionale Umleitung

Die bidirektionale Umleitung umfasst das Starten eines neuen modernen SharePoint Online-Portals, um ein vorhandenes klassisches oder modernes SharePoint-Portal zu ersetzen. Benutzer in aktiven Wellen werden auf die neue Website umgeleitet, unabhängig davon, ob sie zur alten oder zur neuen Website navigieren. Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zu zugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird. 

Wir unterstützen nur die Umleitung zwischen der Standard-Homepage auf der alten Website und der Standard-Homepage auf der neuen Website. Sollten Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass sie mit dem Parameter aufgelistet `WaveOverrideUsers` werden.

So migrieren Sie Benutzer von einer vorhandenen SharePoint-Website auf eine neue SharePoint-Website in einer mehrstufigen Weise:

1. Führen Sie den folgenden Befehl aus, um Portalstartwellen zu bestimmen.
   
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

2. Vollständige Überprüfung. Es kann 5 bis 10 Minuten dauern, bis die Umleitung ihre Konfiguration über den Dienst hinweg abgeschlossen hat. 

### <a name="steps-for-redirection-to-temporary-page"></a>Schritte für die Umleitung auf eine temporäre Seite

Temporäre Seitenumleitung sollte verwendet werden, wenn kein vorhandenes SharePoint-Portal vorhanden ist. Benutzer werden in einer mehrstufigen Weise zu einem neuen modernen SharePoint Online-Portal geleitet. Wenn sich ein Benutzer in einer Welle befindet, die nicht gestartet wurde, wird er auf eine temporäre Seite (eine beliebige URL) umgeleitet. 

1. Führen Sie den folgenden Befehl aus, um Portalstartwellen zu bestimmen.
   
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

2. Vollständige Überprüfung. Es kann 5 bis 10 Minuten dauern, bis die Umleitung ihre Konfiguration über den Dienst hinweg abgeschlossen hat. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Anhalten oder Neu starten eines Portalstarts auf der Website

1. Führen Sie den folgenden Befehl aus, um den Start eines Portals anzuhalten und das Auftreten bevorstehender Wellenprogressionen vorübergehend zu verhindern:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Überprüfen Sie, ob alle Benutzer zur alten Website umgeleitet werden. 

3. Führen Sie den folgenden Befehl aus, um einen angehaltenen Portalstart neu zu starten:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde. 

## <a name="delete-a-portal-launch-on-the-site"></a>Löschen eines Portalstarts auf der Website

1. Führen Sie den folgenden Befehl aus, um einen geplanten oder in Bearbeitung gelaufenen Portalstart für eine Website zu löschen.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Überprüfen Sie, ob keine Umleitung für alle Benutzer erfolgt.

## <a name="learn-more"></a>Weitere Informationen
[Planen des Rolloutplans für den Portalstart in SharePoint Online](./planportallaunchroll-out.md)