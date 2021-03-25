---
title: Anzeigen der Ergebnisse einer automatisierten Untersuchung in Microsoft 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Korrektur, Aktionen
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
description: Während und nach einer automatisierten Untersuchung in Microsoft 365 können Sie die Ergebnisse und wichtigsten Ergebnisse anzeigen.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bf18a9fb80805581a1439b3965a664fd0868248
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205531"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Details und Ergebnisse einer automatisierten Untersuchung in Microsoft 365

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn eine [automatisierte Untersuchung](office-365-air.md) in Microsoft Defender für [Office 365](defender-for-office-365.md)stattfindet, sind Details zu dieser Untersuchung während und nach dem automatisierten Untersuchungsprozess verfügbar. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie diese Details im Microsoft 365 Security Center anzeigen. Untersuchungsdetails bieten Ihnen den aktuellen Status und die Möglichkeit, ausstehende Aktionen zu genehmigen.

> [!TIP]
> Sehen Sie sich die neue, einheitliche Untersuchungsseite im Microsoft 365 Security Center an. Weitere Informationen finden Sie unter [(NEU!) Vereinheitlichte Untersuchungsseite](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Untersuchungsstatus

Der Untersuchungsstatus gibt den Fortschritt der Analyse und der Aktionen an. Während der Untersuchung ändert sich der Status, um anzugeben, ob Bedrohungen gefunden wurden und ob Aktionen genehmigt wurden.

|Status|Beschreibung|
|:---|:---|
|**Wird gestartet**|Die Untersuchung wurde ausgelöst und wartet auf die Ausführung.|
|**Wird ausgeführt**|Der Untersuchungsprozess wurde gestartet und läuft. Dieser Zustand tritt auch auf, wenn [ausstehende Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) genehmigt werden.|
|**Keine Bedrohungen gefunden**|Die Untersuchung ist abgeschlossen, und es wurden keine Bedrohungen (Benutzerkonto, E-Mail-Nachricht, URL oder Datei) identifiziert. <p> **TIPP:** Wenn Sie vermuten, dass etwas verpasst wurde (z. B. ein falsch negatives Objekt), können Sie mithilfe des [Bedrohungs-Explorers Maßnahmen ergreifen.](threat-explorer.md)|
|**Bedrohungen gefunden**|Bei der automatisierten Untersuchung wurden Probleme gefunden, es gibt jedoch keine spezifischen Abhilfemaßnahmen, um diese Probleme zu beheben. <p> Der **Status "Gefundene** Bedrohungen" kann auftreten, wenn eine Art von Benutzeraktivität identifiziert wurde, aber keine Bereinigungsaktionen verfügbar sind. Beispiele hierfür sind die folgenden Benutzeraktivitäten: <br/>- Ein Ereignis zur Verhinderung von Datenverlust (Data [Loss Prevention,](../../compliance/data-loss-prevention-policies.md) DLP)<br/>– Eine Anomalie beim Senden von E-Mails<br/>- Gesendete Schadsoftware<br/>- Gesendeter Phish <p> Bei der Untersuchung wurden keine schädlichen URLs, Dateien oder E-Mail-Nachrichten gefunden, die behoben werden sollten, und keine zu behebenden Postfachaktivitäten, z. B. das Deaktivieren von Weiterleitungsregeln oder delegierung. <p> **TIPP:** Wenn Sie vermuten, dass etwas verpasst wurde (z. B. ein falsch negatives Objekt), können Sie mithilfe des Bedrohungs-Explorers untersuchen und [Maßnahmen ergreifen.](threat-explorer.md)|
|**Vom System beendet**|Die Untersuchung wurde beendet. Eine Untersuchung kann aus mehreren Gründen beendet werden: <br/>– Die ausstehenden Aktionen der Untersuchung sind abgelaufen. Ausstehende Aktionen sind nach einer Genehmigung für eine Woche nicht mehr zeitig.<br/>– Es gibt zu viele Aktionen. Wenn beispielsweise zu viele Benutzer auf bösartige URLs klicken, kann dies die Fähigkeit der Untersuchung überschreiten, alle Analysegeräte ausführen zu können, sodass die Untersuchung beendet wird.<p> **TIPP:** Wenn eine Untersuchung beendet wird, [](threat-explorer.md) bevor Aktionen ergriffen wurden, versuchen Sie, den Bedrohungs-Explorer zu verwenden, um Bedrohungen zu finden und zu bekämpfen.|
|**Ausstehende Aktion**|Die Untersuchung hat eine Bedrohung gefunden, z. B. eine schädliche E-Mail, eine schädliche URL oder eine Einstellung für riskante Postfächer sowie eine Aktion zur Behebung dieser Bedrohung, die auf die Genehmigung [wartet.](air-review-approve-pending-completed-actions.md) <p> Der **Status Ausstehende Aktion** wird ausgelöst, wenn eine Bedrohung mit einer entsprechenden Aktion gefunden wird. Die Liste der ausstehenden Aktionen kann jedoch mit dem Ausführen einer Untersuchung zunehmen. Zeigen Sie Untersuchungsdetails an, um zu sehen, ob andere Elemente noch ausstehen.|
|**Bereinigt**|Die Untersuchung wurde abgeschlossen, und alle Abhilfemaßnahmen wurden genehmigt (als vollständig behoben notiert). <p> **HINWEIS**: Genehmigte Korrekturaktionen können Fehler enthalten, die verhindern, dass die Aktionen ergriffen werden. Unabhängig davon, ob Korrekturaktionen erfolgreich abgeschlossen wurden, ändert sich der Untersuchungsstatus nicht. Anzeigen von Untersuchungsdetails.|
|**Teilweise behoben**|Die Untersuchung führte zu Korrekturmaßnahmen, und einige wurden genehmigt und abgeschlossen. Weitere Aktionen sind noch [ausstehend.](air-review-approve-pending-completed-actions.md)|
|**Fehlgeschlagen**|Bei mindestens einer Untersuchungsuntersuchung wurde ein Problem verursacht, bei dem es nicht ordnungsgemäß abgeschlossen werden konnte. <p> **HINWEIS:** Wenn eine Untersuchung nach der Genehmigung von Korrekturaktionen fehlschlägt, sind die Behebungsaktionen möglicherweise noch erfolgreich. Zeigen Sie die Untersuchungsdetails an. |
|**Durch Einschränkung in die Warteschlange eingereiht**|Eine Untersuchung wird in einer Warteschlange abgehalten. Wenn andere Untersuchungen abgeschlossen sind, beginnen die Untersuchungen in der Warteschlange. Drosselung trägt dazu bei, eine schlechte Dienstleistung zu vermeiden.  <p> **TIPP:** Ausstehende Aktionen können die Anzahl neuer Untersuchungen einschränken. Stellen Sie [sicher, dass ausstehende Aktionen genehmigt (oder abgelehnt) werden.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Durch Einschränkung beendet**|Wenn eine Untersuchung zu lange in der Warteschlange gehalten wird, wird sie beendet. <p> **TIPP:** Sie können [eine Untersuchung über den Bedrohungs-Explorer starten.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Anzeigen von Details einer Untersuchung

1. Wechseln Sie zum Microsoft 365 Security Center ( <https://security.microsoft.com> ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Aktionscenter aus.**
3. Wählen Sie auf den Registerkarten **Ausstehend** **oder Verlauf** eine Aktion aus. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich Die Seite **Untersuchung öffnen aus.** 
5. Verwenden Sie die verschiedenen Registerkarten, um mehr über die Untersuchung zu erfahren.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung

Bestimmte Arten von Warnungen lösen eine automatisierte Untersuchung in Microsoft 365 aus. Weitere Informationen finden Sie unter [Warnungsrichtlinien, die automatisierte Untersuchungen auslösen.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Wechseln Sie zum Microsoft 365 Security Center ( <https://security.microsoft.com> ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Aktionscenter aus.**
3. Wählen Sie auf den Registerkarten **Ausstehend** **oder Verlauf** eine Aktion aus. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich Die Seite **Untersuchung öffnen aus.** 
5. Wählen Sie die **Registerkarte Warnungen** aus, um eine Liste aller Warnungen anzuzeigen, die dieser Untersuchung zugeordnet sind.
6. Wählen Sie ein Element in der Liste aus, um den Flyoutbereich zu öffnen. Dort können Sie weitere Informationen zur Warnung anzeigen.

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- Die E-Mail-Anzahl wird zum Zeitpunkt der Untersuchung berechnet, und einige Anzahlen werden neu berechnet, wenn Sie Untersuchungsf flyouts öffnen (basierend auf einer zugrunde liegenden Abfrage).

- Die E-Mail-Zählungen,  die für die E-Mail-Cluster auf der Registerkarte E-Mail angezeigt werden, und der E-Mail-Mengewert, der im Clusterf flyout angezeigt wird, werden zum Zeitpunkt der Untersuchung berechnet und ändern sich nicht.

- Die E-Mail-Anzahl unten  auf der Registerkarte E-Mail des E-Mail-Cluster-Flyouts und die Anzahl der im Explorer angezeigten E-Mail-Nachrichten spiegeln E-Mail-Nachrichten wider, die nach der ersten Analyse der Untersuchung empfangen wurden.

  So würde ein E-Mail-Cluster, der eine ursprüngliche Menge von 10 E-Mail-Nachrichten zeigt, eine E-Mail-Liste von insgesamt 15 anzeigen, wenn fünf weitere E-Mail-Nachrichten zwischen der Untersuchungsanalysephase und wenn der Administrator die Untersuchung überprüft. Ebenso können alte Untersuchungen beginnen, höhere Anzahlen als Explorer-Abfragen anzeigen, da Daten in Microsoft Defender für Office 365 Plan 2 nach sieben Tagen für Testversionen und nach 30 Tagen für kostenpflichtige Lizenzen ablaufen.

  Das Anzeigen der anzahlhistorischen und aktuellen Anzahl in verschiedenen Ansichten erfolgt, um die E-Mail-Auswirkungen zum Zeitpunkt der Untersuchung und die aktuellen Auswirkungen bis zum Zeitpunkt der Behebung anzugeben.

- Im Kontext von E-Mails wird möglicherweise eine Bedrohungsoberfläche für Volumenanomalie im Rahmen der Untersuchung zu sehen sein. Eine Volumenanomalie zeigt eine Spitzenmenge ähnlicher E-Mail-Nachrichten um die Untersuchungsereigniszeit im Vergleich zu früheren Zeitrahmen an. Eine Erhöhung des E-Mail-Datenverkehrs zusammen mit bestimmten Merkmalen (z. B. Betreff- und Absenderdomäne, Body similarity und Absender-IP) ist typisch für den Beginn von E-Mail-Kampagnen oder Angriffen. Massen-, Spam- und legitime E-Mail-Kampagnen teilen diese Merkmale jedoch häufig.

- Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation, or malicious reputation.

- Sie müssen nicht jede Aktion genehmigen. Wenn Sie mit der empfohlenen Aktion nicht einverstanden sind oder Ihre Organisation bestimmte  Arten von Aktionen nicht wählt, können Sie die Aktionen ablehnen oder einfach ignorieren und keine Aktion ergreifen.

- Wenn Sie alle Aktionen genehmigen und/oder ablehnen, kann die Untersuchung vollständig abgeschlossen werden (der Status wird behoben), während einige Aktionen unvollständige Ergebnisse zur Änderung des Untersuchungsstatus in einen teilweise behobenen Zustand führen.

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen und Genehmigen ausstehender Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
