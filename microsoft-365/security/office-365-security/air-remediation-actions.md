---
title: Korrekturaktionen in Microsoft Defender for Office 365
keywords: AIR, AutoIR, Microsoft Defender for Endpoint, automatisiert, Untersuchung, Antwort, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
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
description: Erfahren Sie mehr über Korrekturaktionen nach der automatisierten Untersuchung in Microsoft Defender for Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ffaa7c46d81070a6443bf2233bbfdfd741ceb915
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114330"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Korrekturaktionen in Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Wartungsaktionen

Zu den Bedrohungsschutzfeatures in [Microsoft Defender for Office 365](defender-for-office-365.md) gehören bestimmte Abhilfemaßnahmen. Solche Korrekturaktionen können Folgendes umfassen:

- E-Mail-Nachrichten oder Cluster vorläufig löschen
- URL blockieren (Zeitpunkt des Klickens)
- Externe E-Mail-Weiterleitung deaktivieren
- Deaktivieren der Delegierung

In Microsoft Defender for Office 365 werden Korrekturaktionen nicht automatisch ausgeführt. Stattdessen werden Korrekturaktionen nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ergriffen.

## <a name="threats-and-remediation-actions"></a>Bedrohungen und Abhilfemaßnahmen

Microsoft Defender for Office 365 enthält Abhilfemaßnahmen zur Behebung verschiedener Bedrohungen. Automatisierte Untersuchungen führen häufig zu einer oder mehreren Korrekturaktionen, die überprüft und genehmigt werden müssen. In einigen Fällen führt eine automatisierte Untersuchung nicht zu einer bestimmten Korrekturaktion. Verwenden Sie die Anleitung in der folgenden Tabelle, um die entsprechenden Aktionen weiter zu untersuchen und zu ergreifen.

|Kategorie|Bedrohung/Risiko|Korrekturaktion(en)|
|:---|:---|:---|
|E-Mail senden|Schadsoftware|Soft delete email/cluster <p> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Schadsoftware enthält, wird der Cluster als bösartig betrachtet.|
|E-Mail senden|Bösartige URL<br/>(Eine schädliche URL wurde von sicheren [Links erkannt.)](safe-links.md)|Soft delete email/cluster <br/>Blockieren der URL (Überprüfung der Uhrzeit des Klicks)<p> E-Mails, die eine schädliche URL enthalten, werden als schädlich betrachtet.|
|E-Mail senden|Phishing|Soft delete email/cluster <p> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Phishingversuche enthält, wird der gesamte Cluster als Phishingversuch betrachtet.|
|E-Mail senden|Zapped Phish <br>(E-Mail-Nachrichten wurden zugestellt und dann [abgezapft.)](zero-hour-auto-purge.md)|Soft delete email/cluster <p>Berichte stehen zum Anzeigen von gezapften Nachrichten zur Verfügung. [Sehen Sie, ob ZAP eine Nachricht und FAQs verschoben hat.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-Mail senden|Verpasste Phishing-E-Mails, [die von](enable-the-report-message-add-in.md) einem Benutzer gemeldet wurden|[Automatisierte Untersuchung, ausgelöst durch den Bericht des Benutzers](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-Mail senden|Volumenanomalie <br> (Die letzten E-Mail-Mengen überschreiten die vorherigen 7-10 Tage für übereinstimmende Kriterien.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Volume anomaly is not a clear threat, but is merely an indication of larger email volumes in recent days compared to the last 7-10 days. <p>Obwohl ein hohes E-Mail-Volumen auf potenzielle Probleme hinweisen kann, ist eine Bestätigung in Bezug auf böswillige Urteile oder eine manuelle Überprüfung von E-Mail-Nachrichten/Clustern erforderlich. Weitere [Informationen finden Sie unter Suchen verdächtiger E-Mails, die zugestellt wurden.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-Mail senden|Keine Bedrohungen gefunden <br> (Das System hat keine Bedrohungen basierend auf Dateien, URLs oder der Analyse von E-Mail-Cluster-Urteilen finden.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>Bedrohungen, [](zero-hour-auto-purge.md) die nach Abschluss einer Untersuchung gefunden und gezappt wurden, werden nicht in den numerischen Ergebnissen einer Untersuchung widergespiegelt, aber solche Bedrohungen werden im Threat [Explorer angezeigt.](threat-explorer.md)|
|Benutzer|Ein Benutzer hat auf eine schädliche URL geklickt. <br> (Ein Benutzer navigierte zu einer Seite, die später als [](safe-links.md#warning-pages-from-safe-links) schädlich eingestuft wurde, oder ein Benutzer hat eine Warnungsseite für sichere Links umgangen, um zu einer schädlichen Seite zu gelangen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p>URL blockieren (Zeitpunkt des Klickens) <p>Verwenden Sie den [Bedrohungs-Explorer, um Daten zu URLs zu anzeigen und auf Urteile zu klicken.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Wenn Ihre Organisation Microsoft Defender for [](/microsoft-365/security/defender-endpoint/investigate-user) [Endpoint verwendet,](/windows/security/threat-protection/)sollten Sie den Benutzer untersuchen, um zu ermitteln, ob sein Konto gefährdet ist.|
|Benutzer|Ein Benutzer sendet Schadsoftware/Phishing|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Der Benutzer meldet möglicherweise Schadsoftware/Phishing, oder ein Benutzer kann den Benutzer im Rahmen eines Angriffs [spoofing.](anti-spoofing-protection.md) Verwenden [Sie Threat Explorer,](threat-explorer.md) um E-Mails mit [Schadsoftware oder](threat-explorer-views.md#email--malware) Phishing ein- und zu [behandeln.](threat-explorer-views.md#email--phish)|
|Benutzer|E-Mail-Weiterleitung <br> (Postfach forwarding rules are configured, which could be used for data exfiltration.)|Weiterleitungsregel entfernen <p> Verwenden [Sie Einblicke in den Nachrichtenfluss,](mail-flow-insights-v2.md)einschließlich des Berichts für automatisch [weitergeleitete](mfi-auto-forwarded-messages-report.md)Nachrichten, um spezifischere Details zu weitergeleiteten E-Mails anzuzeigen.|
|Benutzer|Regeln für die E-Mail-Delegierung <br> (Für das Konto eines Benutzers wurde eine Delegierung eingerichtet.)|Delegierungsregel entfernen <p> Wenn Ihre Organisation [Microsoft Defender for Endpoint verwendet,](/windows/security/threat-protection/)sollten Sie den Benutzer untersuchen, der die Delegierungsberechtigung erhalten hat. [](/microsoft-365/security/defender-endpoint/investigate-user)|
|Benutzer|Datenexﬁltration <br> (Ein Benutzer hat gegen E-Mail- oder [Dateifreigabe-DLP-Richtlinien verstoßen](../../compliance/dlp-learn-about-dlp.md) |Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> [Anzeigen von DLP-Berichten und Ergreifen von Aktionen](../../compliance/view-the-dlp-reports.md).|
|Benutzer|Anomales Senden von E-Mails <br> (Ein Benutzer hat kürzlich mehr E-Mails als in den vorherigen 7-10 Tagen gesendet.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Das Senden einer großen Menge von E-Mails ist für sich allein nicht schädlich. Möglicherweise hat der Benutzer gerade eine E-Mail an eine große Gruppe von Empfängern für ein Ereignis gesendet. Verwenden Sie zum Untersuchen Einblicke [in den](mail-flow-insights-v2.md)Nachrichtenfluss, einschließlich des Berichts zur [Nachrichtenflusszuordnung,](mfi-mail-flow-map-report.md) um zu bestimmen, was vor sich geht und Maßnahmen zu ergreifen.|

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Microsoft Defender for Office 365](air-view-investigation-results.md)
- [Anzeigen ausstehender oder abgeschlossener Korrekturaktionen nach einer automatisierten Untersuchung in Microsoft Defender for Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Informationen zur automatisierten Untersuchung in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Informationen zu Funktionen in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
