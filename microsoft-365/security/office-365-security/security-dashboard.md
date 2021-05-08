---
title: Übersicht über das Sicherheitsdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie das neue Sicherheitsdashboard, um Office 365 Bedrohungsschutzstatus zu überprüfen und Sicherheitswarnungen anzuzeigen und zu reagieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71c077853c8dbb68b78c8073f650bcb2df4d1b9a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246453"
---
# <a name="security-dashboard"></a>Sicherheitsdashboard

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Grundlegende Funktionen und Öffnen des Sicherheitsdashboards

Das [Security & Compliance Center](../../compliance/microsoft-365-compliance-center.md) ermöglicht Es Ihrer Organisation, Datenschutz und Compliance zu verwalten. Unter der Voraussetzung, dass Sie über die erforderlichen Berechtigungen verfügen, können Sie mit dem Sicherheitsdashboard Ihren Threat Protection Status überprüfen sowie Sicherheitswarnungen anzeigen und reagieren.

Sehen Sie sich das Video an, um eine Übersicht zu erhalten, und lesen Sie dann diesen Artikel, um weitere Informationen zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Je nachdem, was das Abonnement Ihrer Organisation umfasst, enthält das Sicherheitsdashboard mehrere Widgets, z. B. Zusammenfassung der Bedrohungsverwaltung, Bedrohungsschutzstatus, Globale wöchentliche Bedrohungserkennungen, Schadsoftware und vieles mehr, wie in den folgenden Abschnitten beschrieben.

Um das Sicherheitsdashboard anzuzeigen, wechseln Sie im [Security & Compliance Center](../../compliance/microsoft-365-compliance-center.md)zu Threat **Management** \> **Dashboard**.

> [!NOTE]
> Sie müssen ein globaler Administrator, ein Sicherheitsadministrator oder ein Sicherheitsleser sein, um das Sicherheitsdashboard anzuzeigen. Einige Widgets erfordern zusätzliche Berechtigungen zum Anzeigen. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="threat-management-summary"></a>Zusammenfassung der Bedrohungsverwaltung

Das Widget Zusammenfassung der Bedrohungsverwaltung informiert Sie auf einen Blick darüber, wie Ihre Organisation in den letzten sieben (7) Tagen vor Bedrohungen geschützt wurde.

![Sicherheitsdashboard – Zusammenfassung des Widget "Bedrohungsverwaltung"](../../media/SecDash-ThreatMgmtSummary.png)

Die Informationen, die Sie in der Zusammenfassung zur Bedrohungsverwaltung sehen, hängen davon ab, was Ihr Abonnement enthält. In der folgenden Tabelle wird beschrieben, welche Informationen für E3 und Office 365 E5 Office 365 sind.

|Office 365 E3|Office 365 E5|
|---|---|
|Blockierte Schadsoftwarenachrichten<br>Blockierte Phishingnachrichten<br>Von Benutzern gemeldete Nachrichten<br><br><br><br>|Blockierte Schadsoftwarenachrichten<br>Blockierte Phishingnachrichten<br>Von Benutzern gemeldete Nachrichten<br>Zero-Day-Schadsoftware blockiert<br>Erweiterte Phishingnachrichten erkannt<br>Blockierte bösartige URLs|

Zum Anzeigen oder Zugreifen auf das Widget "Zusammenfassung der Bedrohungsverwaltung" müssen Sie über Berechtigungen zum Anzeigen von Defender für Office 365 verfügen. Weitere Informationen finden Sie unter [Welche Berechtigungen sind erforderlich, um defender for Office 365 anzeigen?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Status des Bedrohungsschutzes

Das Widget Bedrohungsschutzstatus zeigt die Effektivität des Bedrohungsschutzes mit einer trendenden und detaillierten Ansicht von Phishing und Schadsoftware.

![Bedrohungsschutzstatus-Widget](../../media/tpswidget.png)

Die Details hängen davon ab, ob Microsoft 365 [-Abonnement Exchange Online Protection](exchange-online-protection-overview.md) (EOP) mit oder ohne [Microsoft Defender für](defender-for-office-365.md)Office 365.

|Wenn Ihr Abonnement...|Sie sehen diese Details|
|---|---|
|EOP, aber nicht Microsoft Defender für Office 365|Bösartige E-Mails, die von EOP erkannt und blockiert wurden.<p> Siehe [Threat Protection Status Report (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Microsoft Defender für Office 365|Schädliche Inhalte und schädliche E-Mails, die von EOP und Defender für die Office 365 <p> Aggregierte Anzahl eindeutiger E-Mail-Nachrichten mit schädlichen [](zero-hour-auto-purge.md)Inhalten, die vom Anti-Malware-Modul blockiert werden, automatisches Löschen der Nullstunde und Defender für Office 365-Features (einschließlich [sicherer](safe-links.md) [Links,](safe-attachments.md)sicherer Anlagen und [Antiphishing in Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)). <p> Weitere [Informationen finden Sie unter Statusbericht zum Bedrohungsschutz](view-reports-for-mdo.md#threat-protection-status-report).|

Zum Anzeigen oder Zugreifen auf das Threat Protection Status-Widget müssen Sie über Berechtigungen zum Anzeigen von Defender für Office 365 verfügen. Weitere Informationen finden Sie unter [Welche Berechtigungen sind erforderlich, um defender for Office 365 anzeigen?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Globale wöchentliche Bedrohungserkennungen

Das Widget "Globale wöchentliche Bedrohungserkennung" zeigt an, wie viele Bedrohungen in den letzten sieben (7) Tagen in E-Mail-Nachrichten erkannt wurden.

![Widget "Globale wöchentliche Bedrohungserkennung"](../../media/globalweeklythreatdetections.png)

Die Metriken werden wie in der folgenden Tabelle beschrieben berechnet:

|Metrik|Berechnung|
|---|---|
|Gescannte Nachrichten|Anzahl der gescannten E-Mail-Nachrichten multipliziert mit der Anzahl der Empfänger|
|Bedrohungen beendet|Anzahl der als Schadsoftware gekennzeichneten E-Mail-Nachrichten multipliziert mit der Anzahl der Empfänger|
|Von [Defender für Office 365](defender-for-office-365.md)|Anzahl der E-Mail-Nachrichten, die von Defender für Office 365 anzahl der Empfänger blockiert wurden|
|Nach der Zustellung entfernt|Anzahl der Nachrichten, die durch [automatisches](zero-hour-auto-purge.md) Löschen in null Stunden multipliziert mit der Anzahl der Empfänger entfernt wurden|

## <a name="malware"></a>Schadsoftware

Malware widgets show details about malware trends and malware family types over the past seven (7) days.

![Malwaretrends und Familientypen](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Einblicke

Einblicke enthalten nicht nur wichtige Aspekte, die Sie überprüfen sollten, sondern auch Empfehlungen und Aktionen, die Sie berücksichtigen sollten.

![Intelligente Einblicke](../../media/smartinsights.png)

Sie können z. B. sehen, dass Phishing-E-Mail-Nachrichten zugestellt werden, da einige Benutzer ihre Junk-E-Mail-Optionen deaktiviert haben. Weitere Informationen zur Funktionsweise von Einblicken finden Sie unter [Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen

Wenn das Abonnement Ihrer Organisation [Microsoft Defender für Office 365 Plan 2](office-365-ti.md)enthält, enthält Ihr Sicherheitsdashboard einen Abschnitt, der erweiterte Tools zur Untersuchung und Reaktion auf Bedrohungen enthält. Diese Tools umfassen [automatisierte Untersuchungs- und Reaktionsfunktionen.](automated-investigation-response-office.md) Automatisierte Untersuchung und Reaktion können in Szenarien hilfreich sein, z. B. bei der schnellen Behandlung von [gefährdeten Benutzerkonten.](address-compromised-users-quickly.md)

Weitere Informationen finden Sie unter Erste Schritte mit der automatisierten Untersuchung und Reaktion [(AIR) in Office 365](office-365-air.md).

## <a name="trends"></a>Trends

Am unteren Rand des Sicherheitsdashboards befindet sich ein **Abschnitt Trends,** der E-Mail-Flusstrends für Ihre Organisation zusammenfasst. Berichte enthalten Informationen zu E-Mails, die als Spam, Schadsoftware, Phishingversuche und gute E-Mails kategorisiert sind. Klicken Sie auf eine Kachel, um ausführlichere Informationen im Bericht anzeigen zu können.

![Der Abschnitt Trends fasst E-Mail-Flusstrends für die Organisation zusammen.](../../media/trends.png)

Und wenn das Abonnement Ihrer Organisation Defender für [Office 365 Plan 2](office-365-ti.md)enthält, erhalten Sie in diesem Abschnitt auch einen Bericht über Warnungen zur letzten Bedrohungsverwaltung, mit dem Ihr Sicherheitsteam Sicherheitswarnungen mit hoher Priorität anzeigen und Maßnahmen ergreifen kann. 

Zum Anzeigen oder Zugreifen auf das Widget "Gesendete und empfangene E-Mail" müssen Sie über Berechtigungen zum Anzeigen von Defender für Office 365 verfügen. Weitere Informationen finden Sie unter [Welche Berechtigungen sind erforderlich, um defender for Office 365 anzeigen?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Zum Anzeigen oder Zugreifen auf das Widget "Zuletzt verwendete Bedrohungsverwaltungswarnungen" müssen Sie über Berechtigungen zum Anzeigen von Warnungen verfügen. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich sind.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-topics"></a>Verwandte Themen

[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Microsoft Defender für Office 365](view-reports-for-mdo.md)

[Defender for Office 365](defender-for-office-365.md)

[Office 365 Bedrohungsuntersuchung und -reaktion](office-365-ti.md)