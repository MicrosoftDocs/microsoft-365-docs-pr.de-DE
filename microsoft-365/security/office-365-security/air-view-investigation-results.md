---
title: Anzeigen der Ergebnisse einer automatisierten Untersuchung in Microsoft 365
keywords: AIR, autoIR, Microsoft Defender für Endpunkt, automatisiert, Untersuchung, Wartung, Aktionen
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
description: Während und nach einer automatisierten Untersuchung in Microsoft 365 können Sie die Ergebnisse und wichtigen Ergebnisse anzeigen.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef91a3b218c2dda671bf7d07bf2615001bd20ebc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290135"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Details und Ergebnisse einer automatisierten Untersuchung in Microsoft 365

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn eine [automatisierte Untersuchung](office-365-air.md) in Microsoft Defender [für Office 365](defender-for-office-365.md)stattfindet, sind Details zu dieser Untersuchung während und nach dem automatisierten Untersuchungsprozess verfügbar. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie diese Details im Microsoft 365 Defender Portal anzeigen. Untersuchungsdetails bieten Ihnen den aktuellen Status und die Möglichkeit, alle ausstehenden Aktionen zu genehmigen.

> [!TIP]
> Sehen Sie sich die neue, einheitliche Untersuchungsseite im Microsoft 365 Defender-Portal an. Weitere Informationen finden Sie unter [(NEU!) Einheitliche Untersuchungsseite](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Untersuchungsstatus

Der Untersuchungsstatus gibt den Fortschritt der Analyse und der Aktionen an. Während der Untersuchung ändert sich der Status, um anzugeben, ob Bedrohungen gefunden wurden und ob Aktionen genehmigt wurden.

<br>

****

|Status|Beschreibung|
|---|---|
|**Wird gestartet**|Die Untersuchung wurde ausgelöst und wartet auf die Ausführung.|
|**Wird ausgeführt**|Der Untersuchungsprozess wurde gestartet und läuft. Dieser Zustand tritt auch auf, wenn [ausstehende Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) genehmigt werden.|
|**Keine Bedrohungen gefunden**|Die Untersuchung wurde abgeschlossen, und es wurden keine Bedrohungen (Benutzerkonto, E-Mail-Nachricht, URL oder Datei) identifiziert. <p> **TIPP:** Wenn Sie vermuten, dass etwas übersehen wurde (z. B. ein falsch negativer Wert), können Sie mithilfe des [Bedrohungs-Explorers](threat-explorer.md)Maßnahmen ergreifen.|
|**Bedrohungen gefunden**|Die automatisierte Untersuchung hat Probleme gefunden, aber es gibt keine spezifischen Abhilfemaßnahmen, um diese Probleme zu beheben. <p> Der Status **"Bedrohungen gefunden"** kann auftreten, wenn eine Bestimmte Art von Benutzeraktivität identifiziert wurde, aber keine Bereinigungsaktionen verfügbar sind. Beispiele sind eine der folgenden Benutzeraktivitäten: <ul><li>Ein Ereignis [zur Verhinderung von Datenverlust](../../compliance/dlp-learn-about-dlp.md)</li><li>Eine E-Mail, die eine Anomalie sendet</li><li>Gesendete Schadsoftware</li><li>Phishing gesendet</li></ul> <p> Die Untersuchung hat keine schädlichen URLs, Dateien oder E-Mail-Nachrichten gefunden, die korrigiert werden müssen, und keine Postfachaktivität, die korrigiert werden muss, z. B. das Deaktivieren von Weiterleitungsregeln oder die Delegierung. <p> **TIPP:** Wenn Sie vermuten, dass etwas übersehen wurde (z. B. ein falsch negativer Wert), können Sie den [Bedrohungs-Explorer](threat-explorer.md) untersuchen und entsprechende Maßnahmen ergreifen.|
|**Vom System beendet**|Die Untersuchung wurde beendet. Eine Untersuchung kann aus mehreren Gründen beendet werden: <ul><li>Die ausstehenden Aktionen der Untersuchung sind abgelaufen. Timeout für ausstehende Aktionen nach dem Warten auf die Genehmigung für eine Woche</li><li>Es gibt zu viele Aktionen. Wenn beispielsweise zu viele Benutzer auf bösartige URLs klicken, kann dies die Fähigkeit der Untersuchung, alle Analyseprogramme auszuführen, überschreiten, sodass die Untersuchung angehalten wird.</li></ul> <p> **TIPP:** Wenn eine Untersuchung angehalten wird, bevor Aktionen ausgeführt wurden, versuchen Sie, [den Bedrohungs-Explorer](threat-explorer.md) zu verwenden, um Bedrohungen zu finden und zu beheben.|
|**Ausstehende Aktion**|Die Untersuchung hat eine Bedrohung gefunden, z. B. eine schädliche E-Mail, eine schädliche URL oder eine riskante Postfacheinstellung sowie eine Aktion zur Behebung dieser Bedrohung, die [auf die Genehmigung wartet.](air-review-approve-pending-completed-actions.md) <p> Der Status **"Ausstehende Aktion"** wird ausgelöst, wenn eine Bedrohung mit einer entsprechenden Aktion gefunden wird. Die Liste der ausstehenden Aktionen kann sich jedoch erhöhen, wenn eine Untersuchung ausgeführt wird. Zeigen Sie Untersuchungsdetails an, um festzustellen, ob weitere Elemente noch ausstehen.|
|**Bereinigt**|Die Untersuchung wurde abgeschlossen, und alle Abhilfemaßnahmen wurden genehmigt (als vollständig behoben gekennzeichnet). <p> **HINWEIS:** Genehmigte Abhilfemaßnahmen können Fehler aufweisen, die verhindern, dass die Aktionen ausgeführt werden. Unabhängig davon, ob Korrekturaktionen erfolgreich abgeschlossen wurden, ändert sich der Untersuchungsstatus nicht. Anzeigen von Untersuchungsdetails.|
|**Teilweise behoben**|Die Untersuchung führte zu Abhilfemaßnahmen, und einige wurden genehmigt und abgeschlossen. Andere Aktionen sind noch [ausstehend.](air-review-approve-pending-completed-actions.md)|
|**Fehlgeschlagen**|Bei mindestens einer Untersuchungsuntersuchung ist ein Problem aufgetreten, bei dem es nicht ordnungsgemäß abgeschlossen werden konnte. <p> **HINWEIS** Wenn eine Untersuchung fehlschlägt, nachdem Abhilfemaßnahmen genehmigt wurden, sind die Korrekturaktionen möglicherweise trotzdem erfolgreich. Zeigen Sie die Untersuchungsdetails an.|
|**In die Warteschlange eingereiht durch Einschränkung**|Eine Untersuchung wird in einer Warteschlange durchgeführt. Wenn andere Untersuchungen abgeschlossen sind, beginnen die Untersuchungen in der Warteschlange. Drosselung trägt dazu bei, leistungsschwache Dienste zu vermeiden.  <p> **TIPP:** Ausstehende Aktionen können einschränken, wie viele neue Untersuchungen ausgeführt werden können. Stellen Sie sicher, [dass ausstehende Aktionen genehmigt (oder abgelehnt) werden.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Beendet durch Drosselung**|Wenn eine Untersuchung in der Warteschleife zu lang gehalten wird, wird sie beendet. <p> **TIPP:** Sie können [eine Untersuchung im Bedrohungs-Explorer starten.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Anzeigen von Details einer Untersuchung

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **das Info-Center** aus.
3. Wählen Sie auf den Registerkarten **"Ausstehend"** oder **"Verlauf"** eine Aktion aus. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich die **Seite "Untersuchung öffnen"** aus. 
5. Verwenden Sie die verschiedenen Registerkarten, um mehr über die Untersuchung zu erfahren.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung

Bestimmte Arten von Warnungen lösen eine automatisierte Untersuchung in Microsoft 365 aus. Weitere Informationen finden Sie unter [Warnungsrichtlinien, die automatisierte Untersuchungen auslösen.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **das Info-Center** aus.
3. Wählen Sie auf den Registerkarten **"Ausstehend"** oder **"Verlauf"** eine Aktion aus. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich die **Seite "Untersuchung öffnen"** aus.
5. Wählen Sie die Registerkarte **"Warnungen" aus,** um eine Liste aller warnungen anzuzeigen, die dieser Untersuchung zugeordnet sind.
6. Wählen Sie ein Element in der Liste aus, um den Flyoutbereich zu öffnen. Dort können Sie weitere Informationen zu der Warnung anzeigen.

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- E-Mail-Zählungen werden zum Zeitpunkt der Untersuchung berechnet, und einige Zählungen werden neu berechnet, wenn Sie Untersuchungs-Flyouts öffnen (basierend auf einer zugrunde liegenden Abfrage).

- Die für die E-Mail-Cluster auf der Registerkarte **"E-Mail"** angezeigten E-Mail-Zählungen und der E-Mail-Mengenwert, der im Cluster-Flyout angezeigt wird, werden zum Zeitpunkt der Untersuchung berechnet und ändern sich nicht.

- Die E-Mail-Anzahl unten auf der Registerkarte **"E-Mail"** des E-Mail-Cluster-Flyouts und die Anzahl der im Explorer angezeigten E-Mail-Nachrichten spiegeln E-Mail-Nachrichten wider, die nach der anfänglichen Analyse der Untersuchung empfangen wurden.

  Daher würde ein E-Mail-Cluster, der eine ursprüngliche Anzahl von 10 E-Mail-Nachrichten anzeigt, eine E-Mail-Liste von insgesamt 15 anzeigen, wenn zwischen der Untersuchungsanalysephase und dem Zeitpunkt, in dem der Administrator die Untersuchung überprüft, fünf weitere E-Mail-Nachrichten eintreffen. Ebenso können alte Untersuchungen mit höheren Zählungen beginnen, als in Explorer-Abfragen angezeigt werden, da Daten in Microsoft Defender für Office 365 Plan 2 nach sieben Tagen für Testversionen und nach 30 Tagen für kostenpflichtige Lizenzen ablaufen.

  Die Anzeige sowohl der anzahlhistorischen als auch der aktuellen Anzahl in verschiedenen Ansichten erfolgt, um die E-Mail-Auswirkungen zum Zeitpunkt der Untersuchung und die aktuellen Auswirkungen bis zur Durchführung der Korrektur anzugeben.

- Im Kontext von E-Mails wird möglicherweise eine Volume-Anomalie-Bedrohungsoberfläche im Rahmen der Untersuchung angezeigt. Eine Volumeanomalie weist auf einen Anstieg ähnlicher E-Mail-Nachrichten um die Untersuchungszeit im Vergleich zu früheren Zeiträumen hin. Ein Anstieg des E-Mail-Datenverkehrs zusammen mit bestimmten Merkmalen (z. B. Betreff- und Absenderdomäne, Body Similarity und Absender-IP) ist typisch für den Beginn von E-Mail-Kampagnen oder Angriffen. Massen-, Spam- und seriöse E-Mail-Kampagnen teilen diese Merkmale jedoch häufig.

- Volumenanomalien stellen eine potenzielle Bedrohung dar und könnten daher im Vergleich zu Schadsoftware- oder Phishing-Bedrohungen, die mithilfe von Antiviren-Engines, Detonation oder böswilligem Ruf identifiziert werden, weniger schwerwiegend sein.

- Sie müssen nicht jede Aktion genehmigen. Wenn Sie mit der empfohlenen Aktion nicht einverstanden sind oder Ihre Organisation bestimmte Arten von Aktionen nicht auswählt, können Sie die Aktionen **ablehnen** oder einfach ignorieren und keine Maßnahmen ergreifen.

- Wenn Sie alle Aktionen genehmigen und/oder ablehnen, kann die Untersuchung vollständig geschlossen werden (der Status wird korrigiert), während einige Aktionen unvollständige Ergebnisse hinterlassen, wenn der Untersuchungsstatus in einen teilweise korrigierten Zustand geändert wird.

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen und Genehmigen ausstehender Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
