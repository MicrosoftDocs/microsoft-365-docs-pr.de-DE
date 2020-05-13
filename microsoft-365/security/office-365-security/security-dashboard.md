---
title: Übersicht über das Sicherheits Dashboard
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: Verwenden Sie das neue Sicherheits Dashboard, um Office 365 Bedrohungsschutz Status zu überprüfen und Sicherheitswarnungen anzuzeigen und zu bearbeiten.
ms.openlocfilehash: d750c0055a9a55f573e4b920166284f6d95ae70f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208036"
---
# <a name="security-dashboard"></a>Sicherheits Dashboard

## <a name="overview"></a>Übersicht

Das [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) ermöglicht Ihrer Organisation das Verwalten von Datenschutz und Compliance. Unter der Voraussetzung, dass Sie über die erforderlichen Berechtigungen verfügen, können Sie mit dem Sicherheits Dashboard den Status des Bedrohungsschutzes überprüfen und Sicherheitswarnungen anzeigen und bearbeiten.

Sehen Sie sich das Video an, um einen Überblick zu erhalten, und lesen Sie diesen Artikel, um mehr darüber zu erfahren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Je nachdem, was das Abonnement Ihrer Organisation umfasst, enthält das Sicherheits Dashboard verschiedene Widgets, wie die in den folgenden Abschnitten beschriebene Zusammenfassung der Bedrohungs Verwaltung, Bedrohungsschutz Status, globale wöchentliche Bedrohungserkennungen, Schadsoftware und vieles mehr.

Um das Sicherheits Dashboard anzuzeigen, wechseln Sie im [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)zu **Threat Management** \> **Dashboard**.

> [!NOTE]
> Sie müssen ein globaler Administrator, ein Sicherheitsadministrator oder ein Sicherheits Leser sein, um das Sicherheits Dashboard anzuzeigen. Einige Widgets erfordern zusätzliche Berechtigungen zur Anzeige. Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="threat-management-summary"></a>Threat Management-Zusammenfassung

Das Widget "Threat Management Summary" informiert Sie auf einen Blick, wie Ihre Organisation vor Bedrohungen in den letzten sieben (7) Tagen geschützt wurde.

![Security Dashboard – Zusammenfassung zum Threat Management-Widget](../../media/SecDash-ThreatMgmtSummary.png)

Die Informationen, die Sie in der Zusammenfassung des Threat Managements sehen, hängen davon ab, was Ihr Abonnement enthält. In der folgenden Tabelle wird beschrieben, welche Informationen für Office 365 E3 und Office 365 E5 enthalten sind.
|||
|---|---|
|**Office 365 E3**|**Office 365 E5**|
|Blockierte Schadsoftware-Nachrichten<br/>Blockierte Phishing-Nachrichten<br>Von Benutzern gemeldete Nachrichten<br><br><br><br>|Blockierte Schadsoftware-Nachrichten<br>Blockierte Phishing-Nachrichten<br>Von Benutzern gemeldete Nachrichten<br>Zero-Day-Schadsoftware blockiert<br>Erweiterte Phishing-Nachrichten erkannt<br>Blockierte schädliche URLs|
|

Zum Anzeigen oder zugreifen auf das Threat Management-Zusammenfassungs Widget benötigen Sie Berechtigungen zum Anzeigen von Advanced Threat Protection-Berichten. Weitere Informationen finden Sie unter [welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).

## <a name="threat-protection-status"></a>Bedrohungsschutz Status

Das Threat Protection-Status-Widget zeigt die Effektivität des Bedrohungsschutzes mit einer Trend-und detaillierten Ansicht von Phishing und Schadsoftware.

![Widget "Bedrohungsschutz Status"](../../media/tpswidget.png)

Die Details hängen davon ab, ob Ihr Microsoft 365-Abonnement [Exchange Online Protection](exchange-online-protection-overview.md) (EoP) mit oder ohne [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) enthält.

|||
|---|---|
|**Wenn Ihr Abonnement Folgendes enthält...**|**Diese Details werden angezeigt.**|
|EoP, jedoch nicht Office 365 ATP|Böswillige e-Mails, die von EoP erkannt und blockiert wurden.<br><br> Siehe [Threat Protection-Status Bericht (EoP)](view-email-security-reports.md#threat-protection-status-report).|
|Office 365 ATP|Böswillige Inhalte und böswillige e-Mails, die von EoP und Office 365 ATP erkannt und blockiert wurden<br><br>Aggregierte Anzahl von eindeutigen e-Mail-Nachrichten mit böswilligen Inhalten, die durch das Anti-Malware-Modul, die [Automatische Säuberungs](zero-hour-auto-purge.md)-und ATP-Funktion (einschließlich [sicherer Links](atp-safe-links.md), [sicherer Anlagen](atp-safe-attachments.md)und [ATP-AntiPhishing](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)) blockiert wurden.<br><br>Siehe [Threat Protection-Status Bericht (ATP)](view-reports-for-atp.md#threat-protection-status-report).|
|

Zum Anzeigen oder zugreifen auf das Threat Protection-Status-widget benötigen Sie Berechtigungen zum Anzeigen von Advanced Threat Protection-Berichten. Weitere Informationen finden Sie unter [welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).

## <a name="global-weekly-threat-detections"></a>Globale wöchentliche Bedrohungserkennungen

Das Global Weekly Threat Detections-Widget zeigt, wie viele Bedrohungen in e-Mail-Nachrichten in den letzten sieben (7) Tagen erkannt wurden.

![Globales wöchentliches Threat Detections-widget](../../media/globalweeklythreatdetections.png)

Die Metriken werden wie in der folgenden Tabelle beschrieben berechnet:

|||
|---|---|
|**Metrik**|**Berechnung**|
|Gescannte Nachrichten|Anzahl der gescannten e-Mail-Nachrichten multipliziert mit der Anzahl der Empfänger|
|Bedrohungen angehalten|Anzahl von e-Mail-Nachrichten, die mit der Anzahl der Empfänger multipliziert wurden.|
|Gesperrt durch [ATP](office-365-atp.md)|Anzahl von von ATP blockierten e-Mail-Nachrichten multipliziert mit der Anzahl der Empfänger|
|Nach Zustellung entfernt|Die Anzahl der Nachrichten, die von der [automatischen Bereinigung ohne Stunden](zero-hour-auto-purge.md) entfernt werden multipliziert mit der Anzahl der Empfänger|
|

## <a name="malware"></a>Schadsoftware

Malware-Widgets zeigen Details zu Malware Trends und Malware Familientypen in den letzten sieben (7) Tagen an.

![Malware Trends und Familientypen](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Insights

Insights nicht nur grundlegende Probleme, die Sie überprüfen sollten, sondern auch Empfehlungen und zu berücksichtigende Maßnahmen.

![Intelligente Einblicke](../../media/smartinsights.png)

Beispielsweise können Sie sehen, dass Phishing-e-Mails zugestellt werden, weil einige Benutzer Ihre Junk-e-Mail-Optionen deaktiviert haben. Weitere Informationen zur Funktionsweise von Insights finden Sie unter [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen

Wenn das Abonnement Ihrer Organisation [Office 365 Advanced Threat Protection-Plan 2](office-365-ti.md)enthält, enthält Ihr Sicherheits Dashboard einen Abschnitt mit erweiterten Tools für die Untersuchung und Reaktion auf Bedrohungen. Das Sicherheitsteam Ihrer Organisation kann anhand der Informationen in diesem Abschnitt neue Kampagnen verstehen, Bedrohungen untersuchen und Vorfälle verwalten.

![Threat Intelligence hilft Ihnen beim verstehen von Angriffen, die auf Ihre Organisation zugeschnitten sind.](../../media/threatintelwidget.png)

## <a name="trends"></a>Trends

Im unteren Bereich des Sicherheits Dashboards finden Sie einen Abschnitt **Trends** , in dem e-Mail-Fluss Trends für Ihre Organisation zusammengefasst werden. Berichte bieten Informationen zu e-Mail-Nachrichten, die als Spam, Schadsoftware, Phishing-Versuche und gute e-Mails kategorisiert werden. Klicken Sie auf eine Kachel, um ausführlichere Informationen im Bericht anzuzeigen.

![Im Abschnitt Trends werden die e-Mail-Fluss Trends für die Organisation zusammengefasst.](../../media/trends.png)

Wenn das Abonnement Ihrer Organisation [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)enthält, haben Sie auch einen Bericht über **aktuelle Threat Management Alerts** in diesem Abschnitt, mit dem Ihr Sicherheitsteam Sicherheitswarnungen mit hoher Priorität anzeigen und ausführen kann.

Zum Anzeigen oder zugreifen auf das gesendete und empfangene e-Mail-widget benötigen Sie Berechtigungen zum Anzeigen von Advanced Threat Protection-Berichten. Weitere Informationen finden Sie unter [welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).

Zum Anzeigen oder zugreifen auf das zuletzt verwendete Threat Management Alerts-Widget benötigen Sie Berechtigungen zum Anzeigen von Benachrichtigungen. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)sind.

## <a name="related-topics"></a>Verwandte Themen

[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Untersuchung und Reaktion der Office 365 Bedrohung](office-365-ti.md)
