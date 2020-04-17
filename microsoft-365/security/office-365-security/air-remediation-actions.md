---
title: Korrekturaktionen in Office 365 automatisierte Untersuchung und Antwort
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
ms.collection: M365-security-compliance
description: Erfahren Sie mehr Überkorrektur Aktionen in automatisierten Ermittlungs-und Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2.
ms.openlocfilehash: d0f08c3e89882e21263c18246612949ea68ac1ad
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528929"
---
# <a name="remediation-actions-in-office-365"></a>Korrekturaktionen in Office 365

## <a name="remediation-actions"></a>Wartungsaktionen

Zu den [automatischen Ermittlungs-und Antwortfunktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 gehören bestimmte Korrekturaktionen. Wenn eine automatische Untersuchung ausgeführt wird oder abgeschlossen ist, wird in der Regel eine oder mehrere Korrekturaktionen angezeigt, die von Ihrem Sicherheits Betriebsteam genehmigt werden müssen, um den Vorgang fortzusetzen. Solche Korrekturaktionen können Folgendes umfassen:

- E-Mail-Nachrichten oder Cluster vorläufig löschen
- URL blockieren (Zeitpunkt des Klickens)
- Externe E-Mail-Weiterleitung deaktivieren
- Delegierung deaktivieren

> [!NOTE]
> In Office 365 ATP werden automatische Untersuchungen nicht automatisch behoben. Korrekturaktionen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt.

## <a name="threats-and-remediation-actions"></a>Bedrohungen und Korrekturaktionen

In der folgenden Tabelle sind die Bedrohungen und die entsprechenden Korrekturaktionen in Office 365 ATP zusammengefasst. In einigen Fällen führt eine automatisierte Untersuchung nicht zu einer bestimmten Korrekturaktion. Ihr Sicherheits Betriebsteam kann weitere Untersuchungen durchführen und entsprechende Maßnahmen ergreifen, wie in der folgenden Tabelle beschrieben.

||||
|---|---|---|
|**Kategorie**|**Bedrohung/Risiko**|**Korrekturaktion (en)**|
|E-Mail|Schadsoftware| Soft Delete e-Mail/Cluster <br/><br/>Wenn mehr als eine Handvoll von e-Mail-Nachrichten in einem Cluster Schadsoftware enthalten, wird der Cluster als bösartig eingestuft.|
|E-Mail|Bösartige URL<br/>(Eine bösartige URL wurde von [Office 365 ATP-Sicherheits Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)erkannt.)|Soft Delete e-Mail/Cluster <br/><br/>E-Mails, die eine bösartige URL enthalten, werden als böswillig eingestuft.|
|E-Mail|Phishingfilterrichtlinie| Soft Delete e-Mail/Cluster <br/><br/>Wenn mehr als eine Handvoll von e-Mail-Nachrichten in einem Cluster Phishing-Versuche enthalten, wird der Cluster als Phishing betrachtet.|
|E-Mail|Gezappte Phishing-Angriffe <br/>(E-Mail-Nachrichten wurden zugestellt und [gezappt](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|Soft Delete e-Mail/Cluster <br/><br/>Berichte sind für die Anzeige von gezappten Nachrichten verfügbar. [Prüfen Sie, ob zap eine Nachricht und FAQs verschoben](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)hat.|
|E-Mail|Von einem Benutzer [gemeldete](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) Phishing-e-Mails| [Automatische Untersuchung, ausgelöst durch den Bericht des Benutzers](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-Mail|Volumen Anomalie <br/>(Aktuelle e-Mail-Mengen überschreiten die vorherigen 7-10 Tage für Übereinstimmungskriterien.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <br/><br/>Volumen Anomalie ist keine eindeutige Bedrohung, sondern lediglich ein Hinweis auf größere e-Mail-Volumes in den letzten Tagen im Vergleich zu den letzten 7-10 Tagen. Auch wenn dies auf mögliche Probleme hindeuten kann, ist eine Bestätigung sowohl in Bezug auf böswillige Urteile als auch auf eine manuelle Überprüfung von e-Mail-Nachrichten/Clustern erforderlich. Weitere Informationen finden Sie unter [Suchen und löschen verdächtiger e-Mails, die zugestellt wurden](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|E-Mail|Keine Bedrohungen gefunden <br/>(Aufgrund von Dateien, URLs oder Analysen von e-Mail-Cluster Urteilen wurden keine Bedrohungen gefunden.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <br/><br/>Bedrohungen, die nach Abschluss einer Untersuchung gefunden und [gezappt](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) wurden, werden in den numerischen Ergebnissen einer Untersuchung nicht berücksichtigt, diese Bedrohungen können jedoch im [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)angezeigt werden.|
|Benutzer|Ein Benutzer hat auf eine bösartige URL geklickt <br/>(Ein Benutzer navigierte zu einer Seite, die später als bösartig erkannt wurde, oder ein Benutzer hat eine [Warnseite für sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) umgangen, um zu einer bösartigen Seite zu gelangen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <br/><br/>Verwenden Sie Threat Explorer, um [Daten zu URLs anzuzeigen und auf Urteile zu klicken](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Wenn Ihre Organisation [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)verwendet, sollten Sie [den Benutzer untersuchen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) , um zu ermitteln, ob sein Konto kompromittiert wurde.|
|Benutzer|Ein Benutzer sendet Schadsoftware/Phishing|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <br/><br/>Der Benutzer meldet möglicherweise Malware/Phishing, oder jemand kann [den Benutzer](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) als Teil eines Angriffs manipulieren. Verwenden Sie [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) , um e-Mails mit [Schadsoftware](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) oder [Phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)anzuzeigen und zu verarbeiten.|
|Benutzer|E-Mail-Weiterleitung <br/>(Post Fach Weiterleitungsregeln werden konfiguriert, die für die Datenfilterung verwendet werden können.)|Weiterleitungsregel entfernen <br/><br/>Verwenden Sie [Einblicke in den Nachrichtenfluss](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), einschließlich des [Berichts zum automatischen Weiterleiten von Nachrichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), um spezifischere Details zu weitergeleiteten e-Mails anzuzeigen.|
|Benutzer|E-Mail-Delegierungs Regeln <br/>(Das Konto eines Benutzers hat die Delegierung eingerichtet.)|Delegierungsregel entfernen <br/><br/> Wenn Ihre Organisation [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)verwendet, erwägen Sie [die Untersuchung des Benutzers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) , der die Berechtigung "delegieren" erhält.|
|Benutzer|Datenfilterung<br/>(Ein Benutzer hat die e-Mail-oder [DLP-Richtlinien](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)für die Dateifreigabe verletzt.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <br/><br/>[DLP-Berichte anzeigen und Aktionen ausführen](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Benutzer|Anomaler e-Mail-Versand <br/>(Ein Benutzer hat vor kurzem mehr e-Mails gesendet als in den vorherigen 7-10 Tagen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <br/><br/>Das Senden einer Menge von e-Mails ist nicht von selbst böswillig; möglicherweise hat der Benutzer nur eine e-Mail an eine große Gruppe von Empfängern für ein Ereignis gesendet. Verwenden Sie zur Untersuchung des [Nachrichtenflusses Einblicke](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), einschließlich des [Nachrichtenfluss-Zuordnungs Berichts](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) , um zu ermitteln, was vor sich geht, und um Maßnahmen zu ergreifen.|
|

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365](air-view-investigation-results.md)

- [Anzeigen ausstehender oder abgeschlossener Korrekturaktionen nach einer automatisierten Untersuchung in Office 365](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>Verwandte Artikel

- [Automatisierte Untersuchung in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Informationen zum Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
