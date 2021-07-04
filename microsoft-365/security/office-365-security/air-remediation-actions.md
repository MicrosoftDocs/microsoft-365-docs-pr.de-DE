---
title: Korrekturaktionen in Microsoft Defender für Office 365
keywords: AIR, autoIR, Microsoft Defender für Endpunkt, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie mehr über Abhilfemaßnahmen nach einer automatisierten Untersuchung in Microsoft Defender für Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71c8ca842d9c88086dee041316899bbc08f943fe
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288911"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Korrekturaktionen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Wartungsaktionen

Zu den Bedrohungsschutzfeatures in [Microsoft Defender für Office 365](defender-for-office-365.md) gehören bestimmte Abhilfemaßnahmen. Solche Korrekturaktionen können Folgendes umfassen:

- E-Mail-Nachrichten oder Cluster vorläufig löschen
- URL blockieren (Zeitpunkt des Klickens)
- Externe E-Mail-Weiterleitung deaktivieren
- Deaktivieren der Delegierung

In Microsoft Defender für Office 365 werden Korrekturmaßnahmen nicht automatisch ausgeführt. Stattdessen werden Korrekturmaßnahmen nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt.

## <a name="threats-and-remediation-actions"></a>Bedrohungen und Abhilfemaßnahmen

Microsoft Defender für Office 365 umfasst Korrekturmaßnahmen, um verschiedene Bedrohungen zu beheben. Automatisierte Untersuchungen führen häufig zu einer oder mehreren Korrekturmaßnahmen, die überprüft und genehmigt werden müssen. In einigen Fällen führt eine automatisierte Untersuchung nicht zu einer bestimmten Korrekturmaßnahme. Verwenden Sie die Anleitungen in der folgenden Tabelle, um weitere Untersuchungen auszuführen und entsprechende Maßnahmen zu ergreifen.

|Kategorie|Bedrohung/Risiko|Korrekturmaßnahmen|
|:---|:---|:---|
|E-Mails|Schadsoftware|Vorläufiges Löschen von E-Mails/Clustern <p> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Schadsoftware enthalten, wird der Cluster als bösartig eingestuft.|
|E-Mails|Bösartige URL <br> (Eine schädliche URL wurde von [Tresor Links](safe-links.md)erkannt.)|Vorläufiges Löschen von E-Mails/Clustern <br> Block-URL (Überprüfungszeit des Klicks) <p> E-Mails, die eine schädliche URL enthalten, gelten als bösartig.|
|E-Mails|Phishing|Vorläufiges Löschen von E-Mails/Clustern <p> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Phishingversuche enthalten, wird der gesamte Cluster als Phishingversuch betrachtet.|
|E-Mails|Zapped phish <br> (E-Mail-Nachrichten wurden zugestellt und dann [angespippt.)](zero-hour-auto-purge.md)|Vorläufiges Löschen von E-Mails/Clustern <p> Berichte sind verfügbar, um zappede Nachrichten anzuzeigen. [Überprüfen Sie, ob ZAP eine Nachricht und häufig gestellte Fragen verschoben hat.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-Mails|Von einem Benutzer [gemeldete](enable-the-report-message-add-in.md) verpasste Phishing-E-Mail|[Automatisierte Untersuchung, ausgelöst durch den Bericht des Benutzers](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-Mails|Volumeanomalie <br> (Die letzten E-Mail-Mengen überschreiten die vorherigen 7 bis 10 Tage für übereinstimmende Kriterien.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Die Volumeanomalie ist keine eindeutige Bedrohung, sondern lediglich ein Hinweis auf größere E-Mail-Volumes in den letzten Tagen im Vergleich zu den letzten 7 bis 10 Tagen. <p>Obwohl eine große Anzahl von E-Mails auf potenzielle Probleme hinweisen kann, ist eine Bestätigung entweder in Bezug auf böswillige Bewertungen oder eine manuelle Überprüfung von E-Mail-Nachrichten/Clustern erforderlich. Siehe [Suchen nach verdächtigen E-Mails, die zugestellt wurden.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-Mails|Keine Bedrohungen gefunden <br> (Das System hat keine Bedrohungen gefunden, die auf Dateien, URLs oder analysen von E-Mail-Clusterbewertungen basieren.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Bedrohungen, die nach Abschluss einer Untersuchung gefunden und [abgespippt](zero-hour-auto-purge.md) wurden, werden nicht in den numerischen Ergebnissen einer Untersuchung widergespiegelt, aber solche Bedrohungen sind im [Bedrohungs-Explorer](threat-explorer.md)sichtbar.|
|Benutzer|Ein Benutzer hat auf eine schädliche URL geklickt <br> (Ein Benutzer hat zu einer Seite navigiert, die später als bösartig eingestuft wurde, oder ein Benutzer hat eine [Warnseite für Tresor Links](safe-links.md#warning-pages-from-safe-links) umgangen, um zu einer schädlichen Seite zu gelangen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> URL blockieren (Zeitpunkt des Klickens) <p> Verwenden Sie den Bedrohungs-Explorer, um [Daten zu URLs anzuzeigen und auf "Bewertung" zu klicken.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> Wenn Ihre Organisation [Microsoft Defender für Endpunkt](/windows/security/threat-protection/)verwendet, sollten Sie den Benutzer [untersuchen,](/microsoft-365/security/defender-endpoint/investigate-user) um festzustellen, ob sein Konto kompromittiert ist.|
|Benutzer|Ein Benutzer sendet Schadsoftware/Phishing|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Der Benutzer meldet möglicherweise Schadsoftware/Phishing oder [spooft den Benutzer](anti-spoofing-protection.md) im Rahmen eines Angriffs. Verwenden Sie [den Bedrohungs-Explorer,](threat-explorer.md) um E-Mails mit [Schadsoftware](threat-explorer-views.md#email--malware) oder [Phishing](threat-explorer-views.md#email--phish)anzuzeigen und zu behandeln.|
|Benutzer|E-Mail-Weiterleitung <br> (Postfachweiterleitungsregeln sind konfiguriert, chch kann für die Datenexfiltration verwendet werden.)|Entfernen der Weiterleitungsregel <p> Verwenden Sie [Nachrichtenflusseinblicke,](mail-flow-insights-v2.md)einschließlich des Berichts über [automatisch gesendete Nachrichten,](mfi-auto-forwarded-messages-report.md)um spezifischere Details zu weitergeleiteten E-Mails anzuzeigen.|
|Benutzer|E-Mail-Delegierungsregeln <br> (Für das Konto eines Benutzers sind Delegationen eingerichtet.)|Delegierungsregel entfernen <p> Wenn Ihre Organisation [Microsoft Defender für Endpunkt](/windows/security/threat-protection/)verwendet, sollten Sie den Benutzer [untersuchen, der](/microsoft-365/security/defender-endpoint/investigate-user) die Delegierungsberechtigung erhält.|
|Benutzer|Datenexﬁltration <br> (Ein Benutzer hat gegen E-Mail- oder [Dateifreigabe-DLP-Richtlinien](../../compliance/dlp-learn-about-dlp.md) verstoßen |Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> [Anzeigen von DLP-Berichten und Ergreifen von Maßnahmen.](../../compliance/view-the-dlp-reports.md)|
|Benutzer|Anomales E-Mail-Senden <br> (Ein Benutzer hat kürzlich mehr E-Mails als in den vorherigen 7 bis 10 Tagen gesendet.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Das Senden eines großen E-Mail-Volumens ist nicht selbst bösartig. Der Benutzer hat möglicherweise gerade eine E-Mail an eine große Gruppe von Empfängern für ein Ereignis gesendet. Um dies zu untersuchen, verwenden Sie Einblicke in den [Nachrichtenfluss,](mail-flow-insights-v2.md)einschließlich des Berichts über die [Nachrichtenflusszuordnung,](mfi-mail-flow-map-report.md) um zu bestimmen, was vor sich geht, und Maßnahmen zu ergreifen.|

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Microsoft Defender für Office 365](air-view-investigation-results.md)
- [Anzeigen ausstehender oder abgeschlossener Korrekturaktionen nach einer automatisierten Untersuchung in Microsoft Defender für Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Erfahren Sie mehr über die automatisierte Untersuchung in Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Erfahren Sie mehr über die Funktionen in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
