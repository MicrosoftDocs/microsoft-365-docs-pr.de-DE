---
title: Starten Des Portals mithilfe des Portalstartplans
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
ms.openlocfilehash: fdf92f2bbdfb673f1db446b562e941d61679fa9a
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694353"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>Starten Des Portals mithilfe des SharePoint Portalstartplaner

Ein Portal ist eine SharePoint-Kommunikationswebsite in Ihrem Intranet mit hohem Datenverkehr – eine Website, die über mehrere Wochen zwischen 10.000 und über 100.000 Viewern verfügt. Verwenden Sie den Portalstartplaner, um Ihr Portal zu starten, um sicherzustellen, dass Benutzer beim Zugriff auf Ihr neues Portal SharePoint können.
<br>
<br>
Der Startplaner des Portals soll Ihnen dabei helfen, einen schrittweisen Roll-out-Ansatz zu verfolgen, indem Sie Viewer in Wellen stapeln und die URL-Umleitungen für das neue Portal verwalten. Während des Start jeder Welle können Sie Benutzerfeedback sammeln, die Portalleistung überwachen und den Start anhalten, um Probleme zu beheben, bevor Sie mit der nächsten Welle fortfahren. Erfahren Sie mehr über die [Planung eines Portalstarts in SharePoint.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) 

**Es gibt zwei Arten von Umleitungen:**

- **Bidirektional**: Starten eines neuen modernen SharePoint, um ein vorhandenes portal SharePoint klassischen oder modernen Portals zu ersetzen
- **Umleitung zu einer temporären Seite:** Starten Eines neuen modernen SharePoint ohne vorhandenes SharePoint Portal

Websiteberechtigungen müssen im Rahmen des Startstarts getrennt von Wellen eingerichtet werden. Wenn Sie beispielsweise ein organisationsweites Portal freigeben, können Sie Berechtigungen auf "Jeder außer externen Benutzern" festlegen und Ihre Benutzer mithilfe von Sicherheitsgruppen in Wellen trennen. Das Hinzufügen einer Sicherheitsgruppe zu einer Welle bietet dieser Sicherheitsgruppe keinen Zugriff auf die Website. 


> [!NOTE]
> - Auf dieses Feature kann ab Mai 2021 über den **Einstellungen-Bereich** auf der Homepage von SharePoint-Kommunikationswebsites für Kunden mit gezielter Veröffentlichung zugegriffen werden und wird bis Juli 2021 für alle Kunden verfügbar sein.
> - Die PowerShell-Version dieses Tools ist heute verfügbar.
> - Dieses Feature kann nur auf modernen Kommunikationswebsites SharePoint werden
> - Sie müssen über Websitebesitzerberechtigungen für die Website verfügen, um den Start eines Portals anpassen und planen zu können.
> - Starts müssen mindestens sieben Tage im Voraus geplant sein, und jede Welle kann ein bis sieben Tage dauern.
> - Die Anzahl der erforderlichen Wellen wird automatisch von der erwarteten Anzahl von Benutzern bestimmt. 
> - Vor dem Planen eines [Portalstarts](https://aka.ms/perftool) muss die Seitendiagnose für SharePoint ausgeführt werden, um sicherzustellen, dass die Homepage der Website fehlerfrei ist.
> - Am Ende des Startstarts können alle Benutzer mit Berechtigungen für die Website auf die neue Website zugreifen.
> - Wenn Ihre Organisation ["Viva Connections"](https://docs.microsoft.com/SharePoint/viva-connections)verwendet, wird benutzern möglicherweise das Symbol Ihrer Organisation in der Microsoft Teams-App-Leiste angezeigt. Wenn das Symbol ausgewählt ist, können Benutzer jedoch erst auf das Portal zugreifen, nachdem ihre Welle gestartet wurde.
> - Dieses Feature ist nicht verfügbar für Office 365 Deutschland, Office 365 betrieben von 21Vianet (China) oder Microsoft 365 US Government-Pläne

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>Verstehen der Unterschiede zwischen den Optionen für den Startplaner des Portals:

Früher konnten Portalstarts nur über powerShell SharePoint werden. Jetzt stehen Ihnen zwei Optionen zur Verfügung, mit deren Hilfe Sie den Start Ihres Portals planen und verwalten können. Erfahren Sie mehr über die wichtigsten Unterschiede zwischen beiden Tools:

**SharePoint PowerShell-Version:**

- Administratoranmeldeinformationen sind für die Verwendung [SharePoint PowerShell erforderlich](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) 
- Mindestanforderung einer Welle 
- Planen der Startzeit basierend auf der Zeitzone für koordinierte Weltzeit (Coordinated Universal Time, KOORDINIERTE Weltzeit)

**Produktversion:**

- Anmeldeinformationen des Websitebesitzers sind erforderlich 
- Mindestanforderung von zwei Wellen
- Planen Des Startes basierend auf der lokalen Zeitzone des Portals, wie in den regionalen Einstellungen angegeben



## <a name="get-started-using-the-portal-launch-scheduler"></a>Erste Schritte mit dem Portalstartplaner

1.  Fügen Sie vor der Verwendung des Portalstartplantools alle Benutzer  [hinzu,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) die über Websiteberechtigungen als Websitebesitzer, Websitemitglied oder Besucher Zugriff auf diese Website benötigen.

2.  Beginnen Sie dann mit der Planung des Portalstarts, indem Sie auf zwei Arten auf den Portalstartplaner zugreifen:

    **Option 1**: Bei der ersten Bearbeitung und Veröffentlichung von Änderungen an Ihrer Homepage – oder bis zur Startseite, Version 3.0 – werden Sie aufgefordert, das Tool zum Starten des Portals zu verwenden. Wählen **Sie Start planen aus,** um mit der Planung voran zu gehen. Oder wählen **Sie Erneut veröffentlichen aus,** um Ihre Seitenbearbeitungen erneut zu veröffentlichen, ohne den Start zu planen.
    
    ![Abbildung der Aufforderung zur Verwendung des Portalstartplans beim erneuten Veröffentlichen der Startseite](../media/portal-launch-republish-2.png)
    
    **Option 2**: Sie können jederzeit zur Startseite der SharePoint-Kommunikationswebsite navigieren, **Einstellungen**  auswählen und dann den Start der Website planen, um den Start Ihres Portals zu planen.
    
    ![Abbildung des Einstellungen mit hervorgehobener Planung eines Websitestarts](../media/portal-launch-settings-2.png)

3.  Bestätigen Sie als Nächstes die Integritätsnote des [Portals,](https://aka.ms/perftool) und verbessern Sie das Portal bei Bedarf mithilfe des Tools Seitendiagnose für SharePoint, bis Ihr Portal eine **Fehlerfreie** Bewertung erhält. Wählen Sie dann **Weiter aus.**

    ![Abbildung des Tools zum Starten des Portals](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > Der Websitename und die Beschreibung können nicht über den Portalstartplaner  bearbeitet werden und  können stattdessen geändert werden, indem Einstellungen und dann Websiteinformationen auf der Startseite auswählen.
 
4.  Wählen Sie **in der Dropdownliste die Anzahl** der erwarteten Benutzer aus. Diese Abbildung stellt die Anzahl der Benutzer dar, die wahrscheinlich Zugriff auf die Website benötigen. Der Startplaner des Portals bestimmt automatisch die ideale Anzahl von Wellen, je nach den erwarteten Benutzern wie diesem:
    
    - Weniger als 10.000 Benutzer: Zwei Wellen
    - 10-30-k-Benutzer: Drei Wellen 
    - 30k+ bis 100k-Benutzer: Fünf Wellen
    - Mehr als 100.000 Benutzer: Fünf Wellen, und wenden Sie sich über die Schritte im Abschnitt Startportal mit mehr als 100.000 Benutzern an Microsoft. 

5.  Bestimmen Sie dann den typ **der erforderlichen Umleitung:**

    Option 1: Senden von Benutzern an eine vorhandene **SharePoint-Seite (bidirektional)** – Verwenden Sie diese Option beim Starten eines neuen modernen SharePoint-Portals, um ein vorhandenes SharePoint zu ersetzen. Benutzer in aktiven Wellen werden auf die neue Website umgeleitet, unabhängig davon, ob sie zur alten oder zur neuen Website navigieren. Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zu zugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird.
    
    > [!NOTE] 
    > Bei Verwendung der bidirektionalen Option muss die Person, die den Start anregt, auch über Websitebesitzerberechtigungen für das andere SharePoint verfügen.
       
    **Option 2: Senden** von Benutzern an eine automatisch generierte temporäre Seite (temporäre Seitenumleitung) – Verwenden Sie eine temporäre Seitenumleitung, wenn kein vorhandenes SharePoint vorhanden ist. Benutzer werden zu einem neuen modernen SharePoint weitergeleitet, und wenn sich ein Benutzer in einer Welle befindet, die noch nicht gestartet wurde, werden sie zu einer temporären Seite umgeleitet.
    
    **Option 3: Senden** von Benutzern an eine externe Seite – Geben Sie eine externe URL für eine temporäre Angebotsseite an, bis die Welle des Benutzers gestartet wird.
    
6.  Unterlegen Sie Ihre Zielgruppe in Wellen. Add up to 20 security groups per wave. Wellendetails können bis zum Start jeder Welle bearbeitet werden. Jede Welle kann mindestens einen Tag (24 Stunden) und mindestens sieben Tage dauern. Dies SharePoint und Ihrer technischen Umgebung die Möglichkeit, sich auf die große Anzahl von Websitebenutzern zu gewöhnen und zu skalieren. Beim Planen eines Startes über die Benutzeroberfläche basiert die Zeitzone auf den regionalen Einstellungen der Website. 

    >[!NOTE] 
    > - Der Startplaner des Portals wird automatisch auf mindestens 2 Wellen festgelegt. Die PowerShell-Version dieses Tools ermöglicht jedoch eine Welle.
    >  - Microsoft 365 werden von dieser Version des Portalstartplans nicht unterstützt.

7. Bestimmen Sie, wer die Website sofort anzeigen muss, und geben Sie ihre Informationen in das Feld Benutzer ein, **die von Wellen ausgenommen** sind. Diese Benutzer sind von Wellen ausgeschlossen und werden nicht vor, während oder nach dem Start umgeleitet.

8.  Bestätigen Sie die Details zum Starten des Portals, und wählen Sie **Zeitplan aus.** Nachdem der Start geplant wurde, müssen alle Änderungen an der SharePoint-Portal-Homepage ein fehlerfreies Diagnoseergebnis erhalten, bevor der Portalstart fortgesetzt wird.

### <a name="launch-portal-with-over-100k-users"></a>Startportal mit mehr als 100.000 Benutzern

Wenn Sie beabsichtigen, mehr als 100 TB zu migrieren, senden Sie eine Supportanfrage, indem Sie die nachstehenden Schritte ausführen. Stellen Sie sicher, dass Sie alle angeforderten Informationen angeben.

Führen Sie die folgenden Schritte aus:
1. Navigieren Sie zu https://admin.microsoft.com.
2. Stellen Sie sicher, dass Sie das neue Admin Center (Vorschau) verwenden.
3. Klicken Sie im linken Navigationsbereich auf **Support** und dann auf **Neue Serviceanfrage**. 


   Damit wird der Bereich **Benötigen Sie Hilfe?** auf der rechten Seite des Bildschirms aktiviert.

4.  Geben Sie **im Bereich Kurz beschreiben Ihren Problembereich** "Starten SharePoint Portal mit 100-k-Benutzern" ein.</br>
5. Wählen Sie **Support kontaktieren** aus.
6. Geben **Sie unter** Beschreibung "Starten SharePoint Portal mit 100.000 Benutzern" ein. 
7. Füllen Sie die restlichen Informationen aus, und wählen Sie **Kontakt** aus.
8. Stellen Sie nach der Erstellung des Tickets sicher, dass Sie dem Supportmitarbeiter folgende Informationen mitteilen:
- Startportal-URL 
- Anzahl der erwarteten Benutzer
- Geschätzte Startzeit 

## <a name="make-changes-to-a-scheduled-portal-launch"></a>Vornehmen von Änderungen an einem geplanten Portalstart

Startdetails können für jede Welle bis zum Startdatum der Welle bearbeitet werden. 

1.  Navigieren Sie zum Bearbeiten von Portalstartdetails zu **Einstellungen** und wählen **Sie Websitestart planen aus.**
2.  Wählen Sie dann **Bearbeiten aus.**
3.  Wenn Sie die Bearbeitungen abgeschlossen haben, wählen Sie **Aktualisieren aus.**


## <a name="delete-a-scheduled-portal-launch"></a>Löschen eines geplanten Portalstarts

Mit dem Portalstartplanertool geplante Starts können jederzeit abgebrochen oder gelöscht werden, auch wenn bereits einige Wellen gestartet wurden.

1.  Navigieren Sie zum Abbrechen des Portalstarts zu **Einstellungen** und **Planen des Websitestarts.**

2.  Wählen Sie dann **Löschen** aus, und wählen Sie dann, wenn die folgende Nachricht angezeigt **wird, erneut Löschen** aus.

    ![Abbildung des Tools zum Starten des Portals](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a>Verwenden des Startzeitplans für das PowerShell-Portal

Das SharePoint Portal-Startplanertool war ursprünglich nur über [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) verfügbar und wird weiterhin über PowerShell für Kunden unterstützt, die diese Methode bevorzugen. Die gleichen Hinweise am Anfang dieses Artikels gelten für beide Versionen des Portalstartplans. 

>[!NOTE]
> Sie benötigen Administratorberechtigungen für die Verwendung SharePoint PowerShell.
> Portalstartdetails für in PowerShell erstellte Starts werden angezeigt und können im neuen Tool zum Starten des Portals in SharePoint.


### <a name="app-setup-and-connecting-to-sharepoint-online"></a>Einrichten und Herstellen einer Verbindung mit SharePoint Online
1. [Neueste Microsoft Office SharePoint Online-Verwaltungsshell herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Wenn Sie eine frühere Version der Microsoft Office SharePoint Online-Verwaltungsshell installiert haben, gehen Sie zu Programme hinzufügen oder entfernen und deinstallieren Sie "SharePoint Online-Verwaltungsshell".<br>Wählen Sie auf der Seite Download Center Ihre Sprache aus, und klicken Sie dann auf „Herunterladen“. Wählen Sie eine x64- oder eine x86-MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie mit der 64-Bit-Version von Windows arbeiten, oder die x86-Datei, wenn Sie mit der 32-Bit-Version arbeiten. Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate. Nachdem die Sie die Datei heruntergeladen haben, führen Sie die Datei aus und folgen Sie den Schritten im Setup-Assistenten.

2. Stellen Sie eine Verbindung zu Microsoft Office SharePoint Online als [Globaler Admin oder Microsoft Office SharePoint Online-Admin](/sharepoint/sharepoint-admin-role) in Microsoft 365 her. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


### <a name="view-any-existing-portal-launch-setups"></a>Anzeigen vorhandener Portalstarteinrichtung

So sehen Sie, ob vorhandene Portalstartkonfigurationen vorhanden sind:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>Planen eines Portalstarts auf der Website

Die Anzahl der erforderlichen Wellen hängt von der erwarteten Startgröße ab. 
- Weniger als 10.000 Benutzer: Eine Welle
- 10-30-k-Benutzer: Drei Wellen 
- 30k+ bis 100k-Benutzer: Fünf Wellen
- Mehr als 100.000 Benutzer: Fünf Wellen, und wenden Sie sich an Ihr Microsoft-Kontoteam

#### <a name="steps-for-bidirectional-redirection"></a>Schritte für die bidirektionale Umleitung

Die bidirektionale Umleitung umfasst das Starten eines neuen modernen SharePoint Online-Portals, um ein vorhandenes SharePoint klassisches oder modernes Portal zu ersetzen. Benutzer in aktiven Wellen werden auf die neue Website umgeleitet, unabhängig davon, ob sie zur alten oder zur neuen Website navigieren. Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zu zugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird. 

Wir unterstützen nur die Umleitung zwischen der Standard-Homepage auf der alten Website und der Standard-Homepage auf der neuen Website. Sollten Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass sie mit dem Parameter aufgelistet `WaveOverrideUsers` werden.

So migrieren Sie Benutzer von einer vorhandenen SharePoint auf eine neue SharePoint website in einer mehrstufigen Weise:

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

#### <a name="steps-for-redirection-to-temporary-page"></a>Schritte für die Umleitung auf eine temporäre Seite

Temporäre Seitenumleitung sollte verwendet werden, wenn kein vorhandenes SharePoint vorhanden ist. Benutzer werden in einer mehrstufigen Weise SharePoint ein neues, modernes Onlineportal geleitet. Wenn sich ein Benutzer in einer Welle befindet, die nicht gestartet wurde, wird er auf eine temporäre Seite (eine beliebige URL) umgeleitet. 

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

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Anhalten oder Neu starten eines Portalstarts auf der Website

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

### <a name="delete-a-portal-launch-on-the-site"></a>Löschen eines Portalstarts auf der Website

1. Führen Sie den folgenden Befehl aus, um einen geplanten oder in Bearbeitung gelaufenen Portalstart für eine Website zu löschen.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Überprüfen Sie, ob keine Umleitung für alle Benutzer erfolgt.

## <a name="learn-more"></a>Weitere Informationen

[Planen des Rolloutplans für den Portalstart in SharePoint Online](./planportallaunchroll-out.md)

[Planen Ihrer Kommunikationswebsite](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
