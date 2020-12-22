---
title: Behebungsaktionen nach der automatischen Untersuchung in Microsoft Defender für Office 365
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie mehr über Behebungsaktionen nach der automatischen Untersuchung in Microsoft Defender für Office 365.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 74fe6f66d0970fe2725caba7b51bd8a95a34159e
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725165"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Behebungsaktionen nach der automatischen Untersuchung in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Wartungsaktionen

Die [automatisierten Ermittlungs-und Antwortfunktionen](office-365-air.md) (Air) in [Microsoft Defender für Office 365](office-365-atp.md) umfassen bestimmte Korrekturaktionen. Immer wenn eine automatisierte Untersuchung ausgeführt wird oder abgeschlossen ist, werden in der Regel eine oder mehrere Aktionen zur Fehlerbehebung angezeigt, die vom Sicherheitsteam genehmigt werden müssen, bevor sie ausgeführt werden können. Solche Korrekturaktionen können Folgendes umfassen:

- E-Mail-Nachrichten oder Cluster vorläufig löschen
- URL blockieren (Zeitpunkt des Klickens)
- Externe E-Mail-Weiterleitung deaktivieren
- Deaktivieren der Delegierung

> [!NOTE]
> In Microsoft Defender für Office 365 führen automatisierte Untersuchungen nicht dazu, dass automatische Korrekturaktionen ausgeführt werden. Korrekturaktionen werden nur nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation ausgeführt.

## <a name="threats-and-remediation-actions"></a>Bedrohungen und Korrekturaktionen

In der folgenden Tabelle sind die Bedrohungen und entsprechenden Korrekturaktionen in Microsoft Defender für Office 365 zusammengefasst. In einigen Fällen führt eine automatisierte Untersuchung nicht zu einer bestimmten Korrekturaktion. Ihr Sicherheits Betriebsteam kann weitere Untersuchungen durchführen und entsprechende Maßnahmen ergreifen, wie in der folgenden Tabelle beschrieben.

****

|Kategorie|Bedrohung/Risiko|Korrekturaktion (en)|
|---|---|---|
|E-Mails|Schadsoftware|Soft Delete e-Mail/Cluster <br> Wenn mehr als eine Handvoll von e-Mail-Nachrichten in einem Cluster Schadsoftware enthalten, wird der Cluster als bösartig eingestuft.|
|E-Mails|Bösartige URL <br> (Eine bösartige URL wurde von [sicheren Links in Microsoft Defender für Office 365](atp-safe-links.md)erkannt).|Soft Delete e-Mail/Cluster <p> E-Mails, die eine bösartige URL enthalten, werden als böswillig eingestuft.|
|E-Mails|Phishing|Soft Delete e-Mail/Cluster <br> Wenn mehr als eine Handvoll von e-Mail-Nachrichten in einem Cluster Phishing-Versuche enthalten, wird der Cluster als Phishing betrachtet.|
|E-Mails|Gezappte Phishing-Angriffe <br> (E-Mail-Nachrichten wurden zugestellt und [gezappt](zero-hour-auto-purge.md).)|Soft Delete e-Mail/Cluster <p> Berichte sind für die Anzeige von gezappten Nachrichten verfügbar. [Prüfen Sie, ob zap eine Nachricht und FAQs verschoben](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)hat.|
|E-Mails|Von einem Benutzer [gemeldete](enable-the-report-message-add-in.md) Phishing-e-Mails|[Automatische Untersuchung, ausgelöst durch den Bericht des Benutzers](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-Mails|Volumen Anomalie <br> (Aktuelle e-Mail-Mengen überschreiten die vorherigen 7-10 Tage für Übereinstimmungskriterien.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Volumen Anomalie ist keine eindeutige Bedrohung, sondern lediglich ein Hinweis auf größere e-Mail-Volumes in den letzten Tagen im Vergleich zu den letzten 7-10 Tagen. Auch wenn dies auf mögliche Probleme hindeuten kann, ist eine Bestätigung sowohl in Bezug auf böswillige Urteile als auch auf eine manuelle Überprüfung von e-Mail-Nachrichten/Clustern erforderlich. Siehe [Suchen verdächtiger e-Mails, die zugestellt wurden](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|E-Mails|Keine Bedrohungen gefunden <br> (Aufgrund von Dateien, URLs oder Analysen von e-Mail-Cluster Urteilen wurden keine Bedrohungen gefunden.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Bedrohungen, die nach Abschluss einer Untersuchung gefunden und [gezappt](zero-hour-auto-purge.md) wurden, werden in den numerischen Ergebnissen einer Untersuchung nicht berücksichtigt, diese Bedrohungen können jedoch im [Threat Explorer](threat-explorer.md)angezeigt werden.|
|Benutzer|Ein Benutzer hat auf eine bösartige URL geklickt <br> (Ein Benutzer navigierte zu einer Seite, die später als bösartig erkannt wurde, oder ein Benutzer hat eine [Warnseite für sichere Links](atp-safe-links.md#warning-pages-from-safe-links) umgangen, um zu einer bösartigen Seite zu gelangen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Verwenden Sie Threat Explorer, um [Daten zu URLs anzuzeigen und auf Urteile zu klicken](threat-explorer.md#view-phishing-url-and-click-verdict-data). <p> Wenn Ihre Organisation [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)verwendet, sollten Sie [den Benutzer untersuchen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) , um zu ermitteln, ob sein Konto kompromittiert wurde.|
|Benutzer|Ein Benutzer sendet Schadsoftware/Phishing|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Der Benutzer meldet möglicherweise Malware/Phishing, oder jemand kann [den Benutzer](anti-spoofing-protection.md) als Teil eines Angriffs manipulieren. Verwenden Sie [Threat Explorer](threat-explorer.md) , um e-Mails mit [Schadsoftware](threat-explorer-views.md#email--malware) oder [Phishing](threat-explorer-views.md#email--phish)anzuzeigen und zu verarbeiten.|
|Benutzer|E-Mail-Weiterleitung <br> (Post Fach Weiterleitungsregeln werden konfiguriert, die für die Datenfilterung verwendet werden können.)|Weiterleitungsregel entfernen <p> Verwenden Sie [Einblicke in den Nachrichtenfluss](mail-flow-insights-v2.md), einschließlich des [Berichts zum automatischen Weiterleiten von Nachrichten](mfi-auto-forwarded-messages-report.md), um spezifischere Details zu weitergeleiteten e-Mails anzuzeigen.|
|Benutzer|E-Mail-Delegierungs Regeln <br> (Das Konto eines Benutzers hat die Delegierung eingerichtet.)|Delegierungsregel entfernen <p> Wenn Ihre Organisation [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)verwendet, erwägen Sie [die Untersuchung des Benutzers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) , der die Berechtigung "delegieren" erhält.|
|Benutzer|Datenexﬁltration <br> (Ein Benutzer hat die e-Mail-oder [DLP-Richtlinien](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)für die Dateifreigabe verletzt.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> [DLP-Berichte anzeigen und Aktionen ausführen](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Benutzer|Anomaler e-Mail-Versand <br> (Ein Benutzer hat vor kurzem mehr e-Mails gesendet als in den vorherigen 7-10 Tagen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Das Senden einer Menge von e-Mails ist nicht von selbst böswillig; möglicherweise hat der Benutzer nur eine e-Mail an eine große Gruppe von Empfängern für ein Ereignis gesendet. Verwenden Sie zur Untersuchung des [Nachrichtenflusses Einblicke](mail-flow-insights-v2.md), einschließlich des [Nachrichtenfluss-Zuordnungs Berichts](mfi-mail-flow-map-report.md) , um zu ermitteln, was vor sich geht, und um Maßnahmen zu ergreifen.|
|

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Microsoft Defender für Office 365](air-view-investigation-results.md)

- [Anzeigen ausstehender oder abgeschlossener Korrekturaktionen nach einer automatischen Untersuchung in Microsoft Defender für Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Informationen zur automatischen Untersuchung in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Informationen zu zusätzlichen Funktionen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
