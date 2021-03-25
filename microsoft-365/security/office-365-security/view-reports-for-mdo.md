---
title: Anzeigen von Defender for Office 365-Berichten im Dashboard "Berichte"
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Suchen und verwenden Sie Berichte für Microsoft Defender für Office 365 im Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 28978dbca3f9e4039b4f8c21c49a2963802afa54
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205603"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Anzeigen von Defender for Office 365-Berichten im Dashboard "Berichte" im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender für Office 365-Organisationen (z. B. Microsoft 365 E5-Abonnements oder Microsoft Defender für Office 365 Plan 1 oder Microsoft Defender für Office 365 Plan 2-Add-Ons) enthalten eine Vielzahl sicherheitsbezogener Berichte. Wenn Sie über die [erforderlichen Berechtigungen verfügen,](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie zu **Reports** \> **Dashboard gehen.** Öffnen Sie , um direkt zum Dashboard Berichte zu <https://protection.office.com/insightdashboard> wechseln.

![Das Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Defender für Office 365-Bericht zu Dateitypen

Im Bericht über Dateitypen von **Defender für Office 365** wird der Dateityp angezeigt, der von sicheren Anlagen als schädlich [erkannt wurde.](safe-attachments.md)

 Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 90 Tagen, während die Detailansicht nur 10 Tage Filterung zulässt.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  Defender für **Office 365-Dateitypen aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=ATPFileReport> wechseln.

![Defender für Office 365-Dateitypen-Widget im Dashboard "Berichte"](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> Die Informationen in diesem Bericht sind auch im Bericht zur Disposition von [Defender für Office 365-Nachrichten verfügbar.](#defender-for-office-365-message-disposition-report)

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Berichtsansicht für den Defender for Office 365-Dateitypbericht

Die folgenden Ansichten sind verfügbar:

- **Daten anzeigen nach: Datei**: Das Diagramm enthält die folgenden Informationen:

  - **Schädliche Excel-Anlagen**
  - **Bösartige Flash-Anlagen**
  - **Schädliche PDF-Anlagen**
  - **Schädliche PowerPoint-Anlagen**
  - **Bösartige URLs**
  - **Schädliche Word-Anlagen**
  - **Schädliche ausführbare Anlagen**
  - **Sonstige**

  Wenn Sie den Mauszeiger auf einen bestimmten Tag (Datenpunkt) zeigen, können Sie die Aufschlüsselung der Typen von schädlichen Dateien sehen, die von sicheren [Anlagen](safe-attachments.md) und Schutz vor Schadsoftware [in EOP erkannt wurden.](anti-malware-protection.md)

  ![Dateiansicht im Bericht über Dateitypen von Defender for Office 365](../../media/atp-file-types-report-file-view.png)

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Dieselben Dateitypwerte, die im Diagramm angezeigt werden.

- **Daten anzeigen nach: Nachricht**: Das Diagramm enthält die folgenden Informationen:

  - **Zugriff blockieren**
  - **Ersetzte Nachrichten**
  - **Überwachte Nachrichten**
  - **Durch dynamische E-Mail-Zustellung** ersetzt: Weitere Informationen finden Sie unter [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Nachrichtenansicht im Bericht über Defender for Office 365-Dateitypen](../../media/atp-file-types-report-message-view.png)

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und die **zusätzlichen Nachrichten übergebenen** Wert.

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Detailtabelle für den Defender for Office 365-Dateitypbericht

Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine Nahezu-Echtzeitansicht aller Klicks, die in der Organisation für die letzten 10 Tage vorkommen. Die angezeigten Informationen hängen von dem Diagramm ab, das Sie betrachtet haben:

- **Daten anzeigen nach: Datei**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**: Im **Kopfzeilenfeld Message-ID** im Nachrichtenkopf verfügbar und sollte eindeutig sein. Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die eckigen Klammern).
  - **Datei**

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Dieselben Dateitypwerte, die im Diagramm angezeigt werden.

- **Daten anzeigen nach: Message**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**
  - **Datei**
  - **Betreff**

  Wenn Sie auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und die **zusätzlichen Nachrichten übergebenen** Wert.

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu kommen.**

## <a name="defender-for-office-365-message-disposition-report"></a>Defender für Office 365-Bericht zum Nachrichtenstatus

Der Bericht zur Disposition **von ATP-Nachrichten** zeigt die Aktionen an, die für E-Mail-Nachrichten ergriffen wurden, die als schädliche Inhalte erkannt wurden.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  Defender für **Office 365-Nachrichtendisposition aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=ATPMessageReport> wechseln.

![Defender für Office 365-Nachrichtendispositions-Widget im Dashboard "Berichte"](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> Die Informationen in diesem Bericht sind auch im [Defender for Office 365-Dateitypenbericht verfügbar.](#defender-for-office-365-file-types-report)

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Berichtsansicht für den Bericht zur Disposition von Defender für Office 365-Nachrichten

Die folgenden Ansichten sind verfügbar:

- **Daten anzeigen nach: Nachricht**: Das Diagramm enthält die folgenden Informationen:

  - **Zugriff blockieren**
  - **Ersetzte Nachrichten**
  - **Überwachte Nachrichten**
  - **Durch dynamische E-Mail-Zustellung** ersetzt: Weitere Informationen finden Sie unter [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Nachrichtenansicht im Bericht über Defender for Office 365-Dateitypen](../../media/atp-file-types-report-message-view.png)

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und die **zusätzlichen Nachrichten übergebenen** Wert.

- **Daten anzeigen nach: Datei**: Das Diagramm enthält die folgenden Informationen:

  - **Schädliche Excel-Anlagen**
  - **Bösartige Flash-Anlagen**
  - **Schädliche PDF-Anlagen**
  - **Schädliche PowerPoint-Anlagen**
  - **Bösartige URLs**
  - **Schädliche Word-Anlagen**
  - **Schädliche ausführbare Anlagen**
  - **Sonstige**

  Wenn Sie den Mauszeiger auf einen bestimmten Tag (Datenpunkt) zeigen, können Sie die Aufschlüsselung der Typen von schädlichen Dateien sehen, die von sicheren [Anlagen](safe-attachments.md) und Schutz vor Schadsoftware [in EOP erkannt wurden.](anti-malware-protection.md)

  ![Dateiansicht im Bericht über Dateitypen von Defender for Office 365](../../media/atp-file-types-report-file-view.png)

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Dieselben Dateitypwerte, die im Diagramm angezeigt werden.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Detailtabelle für den Bericht zur Disposition von Defender for Office 365-Nachrichten

Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine Nahezu-Echtzeitansicht aller Klicks, die in der Organisation für die letzten 10 Tage vorkommen. Die angezeigten Informationen hängen von dem Diagramm ab, das Sie betrachtet haben:

- **Daten anzeigen nach: Message**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**
  - **Datei**
  - **Betreff**

  Wenn Sie auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Die gleichen Nachrichtendispositionswerte, die im Diagramm verfügbar sind, und die **zusätzlichen Nachrichten übergebenen** Wert.

- **Daten anzeigen nach: Datei**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**
  - **Datei**

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Dieselben Dateitypwerte, die im Diagramm angezeigt werden.

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu kommen.**

## <a name="mail-latency-report"></a>Bericht über die E-Mail-Latenz

Der **Bericht über die E-Mail-Latenz** zeigt eine aggregierte Ansicht der E-Mail-Zustellung und detonationslatenz in Ihrer Organisation. Die E-Mail-Zustellungszeiten im Dienst werden von einer Reihe von Faktoren beeinflusst, und die absolute Zustellungszeit in Sekunden ist häufig kein guter Indikator für erfolg oder ein Problem. Eine langsame Zustellungszeit an einem Tag kann als durchschnittliche Lieferzeit an einem anderen Tag betrachtet werden oder umgekehrt. Der **Bericht über die E-Mail-Latenz** versucht, die Nachrichtenzustellung basierend auf statistischen Daten zu den beobachteten Zustellungszeiten anderer Nachrichten zu qualifizieren:

- **50. Perzentil:** Dies ist die Mitte für Nachrichtenzustellungszeiten. Sie können diesen Wert als durchschnittliche Lieferzeit betrachten.
- **90. Perzentil**: Dies gibt eine hohe Latenz für die Nachrichtenzustellung an. Nur 10 % der Nachrichten dauerten länger als dieser Wert, um zu liefern.
- **99. Perzentil**: Dies gibt die höchste Wartezeit für die Nachrichtenzustellung an.

Clientseitige und Netzwerklatenz sind nicht enthalten.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **E-Mail-Latenzbericht aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/mailLatencyReport?viewid=P50> wechseln.

![Widget für E-Mail-Latenzberichte im Berichtsdashboard](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Berichtsansicht für den E-Mail-Latenzbericht

Wenn Sie den Bericht öffnen, ist standardmäßig die **Registerkarte 50.** Perzentile ausgewählt.

Standardmäßig enthält diese Ansicht ein Diagramm, das mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage
- **Nachrichtenansicht**:
  - Detonierte Nachrichten

Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:

- **Wartezeit bei der E-Mail-Zustellung**
- **Verzögerung der Detonation**

Wenn Sie den Mauszeiger auf eine Kategorie im Diagramm zeigen, wird eine Aufschlüsselung der Wartezeit in den einzelnen Kategorien angezeigt.

![Bericht über die E-Mail-Latenz](../../media/mail-latency-report.png)

Wenn Sie in **der** Berichtsansicht auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- Alle Nachrichten
- Nachrichten, die Anlagen oder URLs enthalten

Wenn Sie auf die **Registerkarte 90.** Perzentile oder **die Registerkarte 99.** Perzentile klicken, werden dieselben Standardfilter aus der **50.** Perzentilansicht verwendet.

### <a name="details-table-view-for-the-mail-latency-report"></a>Detailtabelle für den Bericht "E-Mail-Latenz"

Die folgenden Informationen werden in der Detailtabelle angezeigt:

- **Date**
- **Perzentile**
- **Anzahl der Nachrichten**
- **Gesamtlatenz**

![Details zu E-Mail-Latenzberichten](../../media/mail-latency-report-details.png)

Die obigen Informationen zeigen, dass die durchschnittliche Wartezeit am 14. November für alle übermittelten und detonierten **Nachrichten 108,033 Sekunden beträgt.**

Die Detailtabelle enthält die gleichen Informationen auf jeder Registerkarte.

## <a name="threat-protection-status-report"></a>Threat Protection-Statusbericht

Der **Statusbericht** zum Bedrohungsschutz ist eine einzelne Ansicht, die Informationen zu schädlichen Inhalten und schädlichen E-Mails enthält, die von [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) und Microsoft Defender für Office 365 erkannt und blockiert werden. Weitere Informationen finden Sie unter [Statusbericht zum Bedrohungsschutz](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>BERICHT zum Schutz vor URL-Bedrohungen

Der **Bericht zum Schutz vor URL-Bedrohungen** enthält Zusammenfassungs- und Trendansichten für erkannte Bedrohungen und Aktionen für URL-Klicks im Rahmen von Sicheren [Links](safe-links.md). In diesem Bericht werden keine Klickdaten von Benutzern angezeigt, für die die angewendete Richtlinie für sichere Links die Option **Benutzerklicks** nicht nachverfolgen aktiviert hat.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen \>  Sie **URL-Schutzbericht aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=URLProtectionActionReport> wechseln.

![URL-Schutzbericht-Widget im Berichtsdashboard](../../media/url-protection-report-widget.png)

> [!NOTE]
> Dies ist ein *Schutztrendbericht,* d. h. Daten stellen Trends in einem größeren Dataset dar. Daher sind die Daten in der aggregierten Ansicht hier nicht in Echtzeit verfügbar, die Daten in der Detailtabelle sind jedoch so, dass möglicherweise eine geringfügige Diskrepanz zwischen den beiden Ansichten angezeigt wird.

### <a name="report-view-for-the-url-threat-protection-report"></a>Berichtsansicht für den BERICHT zum Schutz vor URL-Bedrohungen

Der **Bericht zum Schutz** vor URL-Bedrohungen verfügt über zwei aggregierte Ansichten, die alle vier Stunden aktualisiert werden und Daten für die letzten 90 Tage enthalten:

- **URL-Klickschutzaktion**: Zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klicks an:

  - **Blockiert** (der Benutzer wurde an der Navigation zur URL blockiert)
  - **Blockiert und durchklickt**
  - **Während der Überprüfung durchklickt**

  Ein Klick gibt an, dass der Benutzer über die Sperrseite zur schädlichen Website geklickt hat (Administratoren können das Klicken unter Richtlinien für sichere Links deaktivieren).

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Die verfügbaren Klickschutzaktionen sowie der Wert **Allowed** (der Benutzer konnte zur URL navigieren).

  ![URL-Klick-Aktionsansicht im Bericht zum Schutz von URL-Bedrohungen](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL-Klick nach Anwendung**: Zeigt die Anzahl der URL-Klicks von Anwendungen an, die sichere Links unterstützen:

  - **E-Mail-Client**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Other**

  Wenn Sie auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Die verfügbaren Anwendungen.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Detailtabelle für den Bericht zum Schutz vor URL-Bedrohungen

Wenn Sie auf **Detailtabelle anzeigen** klicken, bietet der Bericht eine Fast-Echtzeit-Ansicht aller Klicks, die in der Organisation für die letzten 7 Tage passiert sind, mit den folgenden Details:

- **Klickzeit**
- **Benutzer**
- **URL**
- **Aktion**
- **App**

Wenn Sie **in** der Detailtabelle auf Filter klicken, können Sie nach denselben  Kriterien  wie in der Berichtsansicht und auch nach Domänen oder Empfängern filtern, die durch Kommas getrennt sind.

> [!NOTE]
> Der **Filter Domänen** verweist auf die in den Berichtsergebnissen aufgeführte URL-Domäne. 

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu kommen.**

## <a name="additional-reports-to-view"></a>Weitere zu sehende Berichte

Zusätzlich zu den in diesem Artikel beschriebenen Berichten sind weitere Berichte verfügbar, wie in der folgenden Tabelle beschrieben:

****

|Bericht|Thema|
|---|---|
|**Explorer** (Microsoft Defender für Office 365  Plan 2) oder Echtzeiterkennungen (Microsoft Defender für Office 365 Plan 1)|[Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)](threat-explorer.md)|
|**E-Mail-Sicherheitsberichte,** z. B. der Bericht "Die besten Absender und Empfänger", der Bericht "Spoof-E-Mail" und der Bericht "Spamerkennungen".|[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)|
|**Nachrichtenflussberichte,** z. B. der Weiterleitungsbericht, der Statusbericht "E-Mailflow" und der Bericht "Absender und Empfänger am oberen Rand".|[Anzeigen von Nachrichtenflussberichten im Security & Compliance Center](view-mail-flow-reports.md)|
|**URL-Ablaufverfolgung für sichere Links** (nur PowerShell). In der Ausgabe dieses Cmdlets werden die Ergebnisse der Aktionen für sichere Links in den letzten sieben Tagen angezeigt.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**Ergebnisse des E-Mail-Datenverkehrs für EOP und Microsoft Defender für Office 365** (nur PowerShell). Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-Mail-Detailberichte für EOP- und Defender for Office 365-Erkennungen** (nur PowerShell). Die Ausgabe dieses Cmdlets enthält Details zu schädlichen Dateien oder URLs, Phishingversuchen, Identitätswechseln und anderen potenziellen Bedrohungen in E-Mails oder Dateien.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Welche Berechtigungen sind erforderlich, um die Defender for Office 365-Berichte anzeigen zu können?

Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:

- **Organisationsverwaltung**
- **Sicherheitsadministrator**
- **Security Reader**
- **Globaler Leser**

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

**Hinweis**: Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Security & Compliance _Center_ und Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Was passiert, wenn in den Berichten keine Daten angezeigt werden?

Wenn in Ihren Defender for Office 365-Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind. Ihre Organisation muss über [](set-up-safe-attachments-policies.md) Richtlinien für sichere [Links](set-up-safe-links-policies.md) und Richtlinien für sichere Anlagen verfügen, damit Defender for Office 365-Schutz möglich ist. Weitere Informationen finden [Sie unter Antispam- und Schutz vor Schadsoftware.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Verwandte Themen

[Intelligente Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)

[Rollenberechtigungen (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)