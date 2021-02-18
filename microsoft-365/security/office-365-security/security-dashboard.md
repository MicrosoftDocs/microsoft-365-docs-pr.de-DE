---
title: Übersicht über das Sicherheitsdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie das neue Sicherheitsdashboard, um den Status von Office 365 Threat Protection zu überprüfen und Sicherheitswarnungen anzuzeigen und zu bearbeiten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 72743f1b052d39ac4762dffc0b3e3e694befa8bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50288323"
---
# <a name="security-dashboard"></a>Sicherheitsdashboard

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Grundlegende Funktionen und Öffnen des Sicherheitsdashboards

Das [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) ermöglicht Ihrer Organisation die Verwaltung von Datenschutz und Compliance. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie mit dem Sicherheitsdashboard Ihren Threat Protection Status überprüfen sowie Sicherheitswarnungen anzeigen und bearbeiten.

Sehen Sie sich das Video an, um einen Überblick zu erhalten, und lesen Sie dann diesen Artikel, um mehr zu erfahren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Je nachdem, was das Abonnement Ihrer Organisation umfasst, enthält das Sicherheitsdashboard verschiedene Widgets, z. B. Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware und vieles mehr, wie in den folgenden Abschnitten beschrieben.

Wechseln Sie zum Anzeigen des Sicherheitsdashboards im [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)zum Dashboard für die **Bedrohungsverwaltung.** \> 

> [!NOTE]
> Sie müssen ein globaler Administrator, ein Sicherheitsadministrator oder ein Sicherheitsleseprogramm sein, um das Sicherheitsdashboard anzeigen zu können. Einige Widgets erfordern zusätzliche Berechtigungen zum Anzeigen. Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>Zusammenfassung der Bedrohungsverwaltung

Das Widget "Threat Management Summary" teilt Ihnen auf einen Blick mit, wie Ihre Organisation in den letzten sieben (7) Tagen vor Bedrohungen geschützt wurde.

![Sicherheitsdashboard – Zusammenfassungs-Widget "Bedrohungsverwaltung"](../../media/SecDash-ThreatMgmtSummary.png)

Welche Informationen in der Zusammenfassung zur Bedrohungsverwaltung angezeigt werden, hängt davon ab, was Ihr Abonnement enthält. In der folgenden Tabelle wird beschrieben, welche Informationen für Office 365 E3 und Office 365 E5 enthalten sind.

|Office 365 E3|Office 365 E5|
|---|---|
|Blockierte Schadsoftwarenachrichten<br>Blockierte Phishingnachrichten<br>Von Benutzern gemeldete Nachrichten<br><br><br><br>|Blockierte Schadsoftwarenachrichten<br>Blockierte Phishingnachrichten<br>Von Benutzern gemeldete Nachrichten<br>Zero-Day-Schadsoftware blockiert<br>Erweiterte Phishingnachrichten erkannt<br>Blockierte schädliche URLs|

Zum Anzeigen oder Zugreifen auf das Widget "Zusammenfassung der Bedrohungsverwaltung" müssen Sie über Berechtigungen zum Anzeigen von Defender für Office 365-Berichten verfügen. Weitere Informationen finden Sie unter [Welche Berechtigungen sind erforderlich, um die Defender für Office 365-Berichte anzeigen zu können?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="threat-protection-status"></a>Threat Protection Status

Das Threat Protection Status Widget zeigt die Effektivität des Bedrohungsschutzes mit einer trendenden und detaillierten Ansicht von Phishing und Schadsoftware.

![Status widget für Bedrohungsschutz](../../media/tpswidget.png)

Die Details hängen davon ab, ob Ihr Microsoft 365-Abonnement [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) mit oder ohne Microsoft Defender für Office [365 umfasst.](office-365-atp.md)

|Wenn Ihr Abonnement...|Sie werden diese Details sehen.|
|---|---|
|EOP, aber nicht Microsoft Defender für Office 365|Bösartige E-Mails, die von EOP erkannt und blockiert wurden.<p> Siehe [Threat Protection Status Report (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Microsoft Defender für Office 365|Bösartige Inhalte und schädliche E-Mails, die von EOP und Defender für Office 365 erkannt und blockiert werden <p> Aggregierte Anzahl eindeutiger E-Mail-Nachrichten mit schädlichen Inhalten, die vom Ansoftwaremodul, der automatischen Bereinigung [](atp-safe-attachments.md)zur Nullstunde und den Funktionen von Defender für Office 365 blockiert werden (einschließlich sicherer [Links,](atp-safe-links.md)sicherer Anlagen und [Antiphishing in Defender für Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [](zero-hour-auto-purge.md) <p> Siehe [Statusbericht zu Bedrohungsschutz.](view-reports-for-atp.md#threat-protection-status-report)|

Zum Anzeigen oder Zugreifen auf das Threat Protection Status Widget müssen Sie über Berechtigungen zum Anzeigen von Defender für Office 365-Berichten verfügen. Weitere Informationen finden Sie unter [Welche Berechtigungen sind erforderlich, um die Defender für Office 365-Berichte anzeigen zu können?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Globale wöchentliche Bedrohungserkennungen

Das Widget "Globale wöchentliche Bedrohungserkennung" zeigt an, wie viele Bedrohungen in E-Mail-Nachrichten in den letzten sieben (7) Tagen erkannt wurden.

![Widget "Globale wöchentliche Bedrohungserkennungen"](../../media/globalweeklythreatdetections.png)

Die Metriken werden wie in der folgenden Tabelle beschrieben berechnet:

|Metrik|Berechnung|
|---|---|
|Überprüfte Nachrichten|Anzahl der gescannten E-Mail-Nachrichten multipliziert mit der Anzahl der Empfänger|
|Bedrohungen beendet|Anzahl der E-Mail-Nachrichten, die schadsoftwarebefreit wurden, multipliziert mit der Anzahl der Empfänger|
|Blockiert von [Defender für Office 365 ](office-365-atp.md)|Anzahl der von Defender für Office 365 blockierten E-Mail-Nachrichten multipliziert mit der Anzahl der Empfänger|
|Nach Zustellung entfernt|Anzahl der durch automatische Bereinigung zur Nullstunde entfernten Nachrichten [multipliziert](zero-hour-auto-purge.md) mit der Anzahl der Empfänger|

## <a name="malware"></a>Schadsoftware

Malware widgets show details about malware trends and malware family types over the past seven (7) days.

![Schadsoftwaretrends und Familientypen](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Einblicke

Einblicke enthalten nicht nur wichtige Aspekte, die Sie überprüfen sollten, sondern auch Empfehlungen und Zu berücksichtigende Aktionen.

![Intelligente Einblicke](../../media/smartinsights.png)

Sie können beispielsweise sehen, dass Phishing-E-Mail-Nachrichten zugestellt werden, da einige Benutzer ihre Junk-E-Mail-Optionen deaktiviert haben. Weitere Informationen zur Funktionsweise von Einblicken finden Sie unter "Berichte und Einblicke" im [Security & Compliance Center.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen

Wenn das Abonnement Ihrer Organisation  [Microsoft Defender für Office 365 Plan 2](office-365-ti.md)enthält, enthält Ihr Sicherheitsdashboard einen Abschnitt mit erweiterten Tools zur Bedrohungsuntersuchung und -reaktion. Diese Tools umfassen [automatisierte Untersuchungs- und Reaktionsfunktionen.](automated-investigation-response-office.md) Automatisierte Untersuchung und Reaktion können in Szenarien hilfreich sein, z. B. schnelles Adressieren von [gefährdeten Benutzerkonten.](address-compromised-users-quickly.md)

Weitere Informationen finden Sie unter [Erste Schritte mit der automatisierten Untersuchung und Reaktion (AIR) in Office 365.](office-365-air.md)

## <a name="trends"></a>Trends

Am unteren Rand des Sicherheitsdashboards befindet sich ein Abschnitt **"Trends",** in dem die E-Mail-Flusstrends für Ihre Organisation zusammengefasst werden. Berichte enthalten Informationen zu E-Mails, die als Spam, Schadsoftware, Phishingversuche und gute E-Mails kategorisiert sind. Klicken Sie auf eine Kachel, um ausführlichere Informationen im Bericht anzeigen zu können.

![Im Abschnitt "Trends" werden die E-Mail-Flusstrends für die Organisation zusammengefasst.](../../media/trends.png)

Und wenn das Abonnement Ihrer Organisation [Defender für Office 365 Plan 2](office-365-ti.md)enthält, erhalten Sie in diesem Abschnitt auch einen Bericht über Warnungen zur Bedrohungsverwaltung, die es Ihrem Sicherheitsteam ermöglichen, Sicherheitswarnungen mit hoher Priorität anzuzeigen und Maßnahmen zu ergreifen. 

Zum Anzeigen oder Zugreifen auf das Widget "Gesendete und empfangene E-Mail" müssen Sie über Berechtigungen zum Anzeigen von Defender für Office 365-Berichten verfügen. Weitere Informationen finden Sie unter [Welche Berechtigungen sind erforderlich, um die Defender für Office 365-Berichte anzeigen zu können?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

Zum Anzeigen oder Zugreifen auf das Widget "Zuletzt verwendeter Bedrohungsverwaltungswarnungen" müssen Sie über Berechtigungen zum Anzeigen von Warnungen verfügen. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich sind.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-topics"></a>Verwandte Themen

[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Microsoft Defender für Office 365](view-reports-for-atp.md)

[Defender for Office 365](office-365-atp.md)

[Untersuchung und Reaktion auf Bedrohungen in Office 365](office-365-ti.md)
