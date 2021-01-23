---
title: Abhilfemaßnahmen nach automatisierter Untersuchung in Microsoft Defender für Office 365
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
ms.date: 01/21/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39032cb187b2654b6ae03c048e706afb665a8761
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939311"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Abhilfemaßnahmen nach automatisierter Untersuchung in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Wartungsaktionen

[Automatisierte Untersuchungs- und Reaktionsfunktionen](office-365-air.md) (AIR) in [Microsoft Defender für Office 365](office-365-atp.md) umfassen bestimmte Abhilfemaßnahmen. Immer wenn eine automatisierte Untersuchung ausgeführt wird oder abgeschlossen ist, werden in der Regel eine oder mehrere Aktionen zur Fehlerbehebung angezeigt, die vom Sicherheitsteam genehmigt werden müssen, bevor sie ausgeführt werden können. Solche Korrekturaktionen können Folgendes umfassen:

- E-Mail-Nachrichten oder Cluster vorläufig löschen
- URL blockieren (Zeitpunkt des Klickens)
- Externe E-Mail-Weiterleitung deaktivieren
- Deaktivieren der Delegierung

> [!NOTE]
> In Microsoft Defender für Office 365 führen automatisierte Untersuchungen nicht zu Korrekturmaßnahmen, die automatisch ausgeführt werden. Abhilfemaßnahmen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ergriffen.

## <a name="threats-and-remediation-actions"></a>Bedrohungen und Abhilfemaßnahmen

In der Tabelle in diesem Abschnitt werden Bedrohungen und geeignete Abhilfemaßnahmen in Microsoft Defender für Office 365 zusammengefasst. In einigen Fällen führt eine automatisierte Untersuchung nicht zu einer bestimmten Korrekturaktion. Ihr Sicherheitsteam kann weitere Untersuchungen durchführen und entsprechende Maßnahmen ergreifen, wie in der folgenden Tabelle beschrieben.

|Kategorie|Bedrohung/Risiko|Wartungsaktion(en)|
|:---|:---|:---|
|E-Mails|Schadsoftware|Soft delete email/cluster <br> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Schadsoftware enthalten, wird der Cluster als bösartig betrachtet.|
|E-Mails|Schädliche URL <br> (Eine schädliche URL wurde von sicheren Links [in Microsoft Defender für Office 365 erkannt.](atp-safe-links.md)|Soft delete email/cluster <p> E-Mails, die eine schädliche URL enthalten, werden als schädlich betrachtet.|
|E-Mails|Phishing|Soft delete email/cluster <br> Wenn mehr als eine Handvoll E-Mail-Nachrichten in einem Cluster Phishingversuche enthalten, wird der Cluster als Phishing betrachtet.|
|E-Mails|Zapped phish <br> (E-Mail-Nachrichten wurden zugestellt [und abgeschnitten.)](zero-hour-auto-purge.md)|Soft delete email/cluster <p> Berichte stehen zum Anzeigen von zappten Nachrichten zur Verfügung. [Sehen Sie, ob ZAP eine Nachricht und häufig gestellte Fragen verschoben hat.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-Mails|Von einem Benutzer gemeldete [verpasste](enable-the-report-message-add-in.md) Phishing-E-Mails|[Automatisierte Untersuchung, ausgelöst durch den Bericht des Benutzers](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-Mails|Volumenanomalie <br> (Die letzten E-Mail-Mengen überschreiten die vorherigen 7 bis 10 Tage für übereinstimmende Kriterien.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Volume anomaly is not a clear threat, but is merely an indication of larger email volumes in recent days compared to the last 7-10 days. Obwohl Volumenanomalie auf potenzielle Probleme hinweisen kann, ist eine Bestätigung in Bezug auf böswillige Beanschauungen oder eine manuelle Überprüfung von E-Mail-Nachrichten/Clustern erforderlich. Siehe Suchen [verdächtiger E-Mails, die zugestellt wurden.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-Mails|Keine Bedrohungen gefunden <br> (Das System hat keine Bedrohungen basierend auf Dateien, URLs oder der Analyse von E-Mail-Cluster-Auswertungen finden.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Bedrohungen, [](zero-hour-auto-purge.md) die nach Abschluss einer Untersuchung gefunden und verknappt wurden, werden nicht in den numerischen Ergebnissen einer Untersuchung widergespiegelt, aber solche Bedrohungen sind im Threat [Explorer zu sehen.](threat-explorer.md)|
|Benutzer|Ein Benutzer hat auf eine schädliche URL geklickt <br> (Ein Benutzer hat zu einer Seite navigiert, die später [](atp-safe-links.md#warning-pages-from-safe-links) als schädlich eingestuft wurde, oder ein Benutzer hat eine Warnseite für sichere Links umgangen, um zu einer schädlichen Seite zu gelangen.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Verwenden Sie den [Bedrohungs-Explorer, um Daten zu URLs anzeigen und auf "Verdingungen" zu klicken.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> Wenn Ihre Organisation Microsoft Defender für [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) [Endpoint verwendet,](https://docs.microsoft.com/windows/security/threat-protection/)sollten Sie den Benutzer untersuchen, um festzustellen, ob sein Konto gefährdet ist.|
|Benutzer|Ein Benutzer sendet Schadsoftware/Phishing|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Der Benutzer meldet möglicherweise Schadsoftware/Phishing, [](anti-spoofing-protection.md) oder ein Benutzer könnte den Benutzer im Rahmen eines Angriffs gefälscht haben. Verwenden [Sie Den Bedrohungs-Explorer,](threat-explorer.md) um E-Mails mit [Schadsoftware oder](threat-explorer-views.md#email--malware) Phishing anzeigen und [behandeln.](threat-explorer-views.md#email--phish)|
|Benutzer|E-Mail-Weiterleitung <br> (Mailbox forwarding rules are configured, which could be used for data exfiltration.)|Weiterleitungsregel entfernen <p> Verwenden [Sie Einblicke in den Nachrichtenfluss,](mail-flow-insights-v2.md)einschließlich des Berichts ["Automatisch weitergeleitete](mfi-auto-forwarded-messages-report.md)Nachrichten", um spezifischere Details zu weitergeleiteten E-Mails anzuzeigen.|
|Benutzer|Regeln für die E-Mail-Delegierung <br> (Für das Konto eines Benutzers wurde eine Delegierung eingerichtet.)|Delegierungsregel entfernen <p> Wenn Ihre Organisation Microsoft Defender für [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) [Endpoint verwendet,](https://docs.microsoft.com/windows/security/threat-protection/)sollten Sie den Benutzer untersuchen, der die Delegierungsberechtigung erhalten hat.|
|Benutzer|Datenexﬁltration <br> (Ein Benutzer hat gegen E-Mail- oder [Dateifreigabe-DLP-Richtlinien verstoßen.)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> [Anzeigen von DLP-Berichten und Ergreifen von Maßnahmen.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|Benutzer|Anomales Senden von E-Mails <br> (Ein Benutzer hat kürzlich mehr E-Mails als in den letzten 7 bis 10 Tagen gesendet.)|Eine automatisierte Untersuchung führt nicht zu einer bestimmten ausstehenden Aktion. <p> Das Senden einer großen Menge von E-Mails ist allein nicht schädlich. Möglicherweise hat der Benutzer gerade eine E-Mail an eine große Gruppe von Empfängern für ein Ereignis gesendet. Um dies zu untersuchen, [](mfi-mail-flow-map-report.md) verwenden Sie [Nachrichtenflusseinblicke,](mail-flow-insights-v2.md)einschließlich des Nachrichtenflusszuordnungsberichts, um zu ermitteln, was vor sich geht, und maßnahmen zu ergreifen.|
|

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen von Details und Ergebnissen einer automatischen Untersuchung in Microsoft Defender für Office 365](air-view-investigation-results.md)

- [Anzeigen ausstehender oder abgeschlossener Wartungsaktionen nach einer automatischen Untersuchung in Microsoft Defender für Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Informationen zur automatisierten Untersuchung in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Erfahren Sie mehr über die Funktionen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
