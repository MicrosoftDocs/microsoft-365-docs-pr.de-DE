---
title: Abhilfemaßnahmen in Microsoft Defender für Office 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Problembehebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d50ea767a795eb8370e9e5c8c1b07a8c9877424
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176039"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Abhilfemaßnahmen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="remediation-actions"></a>Wartungsaktionen

Zu den Bedrohungsschutzfeatures in [Microsoft Defender für Office 365](office-365-atp.md) gehören bestimmte Abhilfemaßnahmen. Solche Korrekturaktionen können Folgendes umfassen:

- E-Mail-Nachrichten oder Cluster vorläufig löschen
- URL blockieren (Zeitpunkt des Klickens)
- Externe E-Mail-Weiterleitung deaktivieren
- Deaktivieren der Delegierung

In Microsoft Defender für Office 365 werden Korrekturaktionen nicht automatisch ausgeführt. Stattdessen werden Abhilfemaßnahmen nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ergriffen.

## <a name="threats-and-remediation-actions"></a>Bedrohungen und Abhilfemaßnahmen

Microsoft Defender für Office 365 umfasst Abhilfemaßnahmen zur Behebung verschiedener Bedrohungen. Automatisierte Untersuchungen führen häufig zu einer oder mehreren Korrekturaktionen, die überprüft und genehmigt werden müssen. In einigen Fällen führt eine automatisierte Untersuchung nicht zu einer bestimmten Korrekturaktion. Verwenden Sie die Anweisungen in der folgenden Tabelle, um weitere Untersuchungen zu ergreifen und entsprechende Maßnahmen zu ergreifen.

|Kategorie|Bedrohung/Risiko|Wartungsaktion(en)|
|:---|:---|:---|
|E-Mails|Schadsoftware|Soft delete email/cluster <p> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Schadsoftware enthalten, wird der Cluster als bösartig betrachtet.|
|E-Mails|Schädliche URL<br/>(Eine schädliche URL wurde von sicheren [Links erkannt.)](atp-safe-links.md)|Soft delete email/cluster <p>E-Mails, die eine schädliche URL enthalten, werden als schädlich betrachtet.|
|E-Mails|Phishing|Soft delete email/cluster <p> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Phishingversuche enthalten, wird der gesamte Cluster als Phishingversuch betrachtet.|
|E-Mails|Zapped phish <br>(E-Mail-Nachrichten wurden zugestellt und [dann abgeschnitten.)](zero-hour-auto-purge.md)|Soft delete email/cluster <p>Berichte stehen zum Anzeigen von zappten Nachrichten zur Verfügung. [Sehen Sie, ob ZAP eine Nachricht und häufig gestellte Fragen verschoben hat.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-Mails|Von einem Benutzer gemeldete [verpasste](enable-the-report-message-add-in.md) Phishing-E-Mails|[Automatisierte Untersuchung, ausgelöst durch den Bericht des Benutzers](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-Mails|Volumenanomalie <br> (Die letzten E-Mail-Mengen überschreiten die vorherigen 7 bis 10 Tage für übereinstimmende Kriterien.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Volume anomaly is not a clear threat, but is merely an indication of larger email volumes in recent days compared to the last 7-10 days. <p>Obwohl eine große Menge von E-Mails auf potenzielle Probleme hinweisen kann, ist eine Bestätigung im Hinblick auf böswillige Beanschauungen oder eine manuelle Überprüfung von E-Mail-Nachrichten/Clustern erforderlich. Siehe Suchen [verdächtiger E-Mails, die zugestellt wurden.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-Mails|Keine Bedrohungen gefunden <br> (Das System hat keine Bedrohungen basierend auf Dateien, URLs oder der Analyse von E-Mail-Cluster-Auswertungen finden.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Bedrohungen, [](zero-hour-auto-purge.md) die nach Abschluss einer Untersuchung gefunden und verknappt wurden, werden nicht in den numerischen Ergebnissen einer Untersuchung widergespiegelt, aber solche Bedrohungen sind im Threat [Explorer zu sehen.](threat-explorer.md)|
|Benutzer|Ein Benutzer hat auf eine schädliche URL geklickt <br> (Ein Benutzer hat zu einer Seite navigiert, die später [](atp-safe-links.md#warning-pages-from-safe-links) als schädlich eingestuft wurde, oder ein Benutzer hat eine Warnseite für sichere Links umgangen, um zu einer schädlichen Seite zu gelangen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Verwenden Sie den [Bedrohungs-Explorer, um Daten zu URLs anzeigen und auf "Verdingungen" zu klicken.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Wenn Ihre Organisation Microsoft Defender for [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) [Endpoint verwendet,](https://docs.microsoft.com/windows/security/threat-protection/)sollten Sie den Benutzer untersuchen, um festzustellen, ob sein Konto gefährdet ist.|
|Benutzer|Ein Benutzer sendet Schadsoftware/Phishing|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Der Benutzer meldet möglicherweise Schadsoftware/Phishing, [](anti-spoofing-protection.md) oder ein Benutzer könnte den Benutzer im Rahmen eines Angriffs gefälscht haben. Verwenden [Sie den Bedrohungs-Explorer,](threat-explorer.md) um E-Mails mit [Schadsoftware oder](threat-explorer-views.md#email--malware) Phishing anzeigen und [behandeln.](threat-explorer-views.md#email--phish)|
|Benutzer|E-Mail-Weiterleitung <br> (Postfach forwarding rules are configured, which could be used for data exfiltration.)|Weiterleitungsregel entfernen <p> Verwenden [Sie Einblicke in den Nachrichtenfluss,](mail-flow-insights-v2.md)einschließlich des Berichts ["Automatisch weitergeleitete](mfi-auto-forwarded-messages-report.md)Nachrichten", um spezifischere Details zu weitergeleiteten E-Mails anzuzeigen.|
|Benutzer|Regeln für die E-Mail-Delegierung <br> (Für das Konto eines Benutzers wurde eine Delegierung eingerichtet.)|Delegierungsregel entfernen <p> Wenn Ihre Organisation Microsoft Defender für [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) [Endpoint verwendet,](https://docs.microsoft.com/windows/security/threat-protection/)sollten Sie den Benutzer untersuchen, der die Delegierungsberechtigung erhalten hat.|
|Benutzer|Datenexﬁltration <br> (Ein Benutzer hat gegen E-Mail- oder [Dateifreigabe-DLP-Richtlinien verstoßen.)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> [Anzeigen von DLP-Berichten und Ergreifen von Maßnahmen.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|Benutzer|Anomales Senden von E-Mails <br> (Ein Benutzer hat kürzlich mehr E-Mails als in den letzten 7 bis 10 Tagen gesendet.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Das Senden einer großen Menge von E-Mails ist allein nicht schädlich. Möglicherweise hat der Benutzer gerade eine E-Mail an eine große Gruppe von Empfängern für ein Ereignis gesendet. Um dies zu untersuchen, [](mfi-mail-flow-map-report.md) verwenden Sie [Nachrichtenflusseinblicke,](mail-flow-insights-v2.md)einschließlich des Nachrichtenflusszuordnungsberichts, um zu ermitteln, was vor sich geht und Maßnahmen zu ergreifen.|

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatischen Untersuchung in Microsoft Defender für Office 365](air-view-investigation-results.md)
- [Anzeigen ausstehender oder abgeschlossener Wartungsaktionen nach einer automatischen Untersuchung in Microsoft Defender für Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Informationen zur automatisierten Untersuchung in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Erfahren Sie mehr über die Funktionen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
