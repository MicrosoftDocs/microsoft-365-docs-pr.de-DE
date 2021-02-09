---
title: Anzeigen der Ergebnisse einer automatisierten Untersuchung in Microsoft 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Wartung, Aktionen
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
ms.openlocfilehash: 7ebfa8bb7060b633bdb48c77bc661477ad3e201b
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142513"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Details und Ergebnisse einer automatisierten Untersuchung in Microsoft 365

Wenn eine [automatisierte Untersuchung](office-365-air.md) in Microsoft Defender für [Office 365](office-365-atp.md)stattfindet, sind Details zu dieser Untersuchung während und nach dem automatisierten Untersuchungsprozess verfügbar. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie diese Details in Ihrem Security Center anzeigen. Untersuchungsdetails bieten Ihnen den aktuellen Status und die Möglichkeit, ausstehende Aktionen zu genehmigen.

> [!TIP]
> Sehen Sie sich die neue, einheitliche Untersuchungsseite im Microsoft 365 Security Center an. Weitere Informationen finden Sie unter [(NEU!) Einheitliche Untersuchungsseite](../mtp/mtp-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Untersuchungsstatus

Der Untersuchungsstatus gibt den Fortschritt der Analyse und der Aktionen an. Während der Untersuchung ändert sich der Status, um anzugeben, ob Bedrohungen gefunden wurden und ob Aktionen genehmigt wurden.

|Status|Beschreibung|
|:---|:---|
|**Wird gestartet**|Die Untersuchung wurde ausgelöst und wartet auf die Ausführung.|
|**Wird ausgeführt**|Der Untersuchungsprozess wurde gestartet und läuft. Dieser Status tritt auch auf, wenn [ausstehende Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) genehmigt werden.|
|**Keine Bedrohungen gefunden**|Die Untersuchung wurde abgeschlossen, und es wurden keine Bedrohungen (Benutzerkonto, E-Mail-Nachricht, URL oder Datei) identifiziert. <p> **TIPP:** Wenn Sie vermuten, dass etwas ausgelassen wurde (z. B. ein falsch negatives Ergebnis), können Sie mithilfe von [Threat Explorer Maßnahmen ergreifen.](threat-explorer.md)|
|**Bedrohungen gefunden**|Bei der automatischen Untersuchung wurden Probleme gefunden, es gibt jedoch keine spezifischen Abhilfemaßnahmen, um diese Probleme zu beheben. <p> Der **Status "Gefundene** Bedrohungen" kann auftreten, wenn eine Art von Benutzeraktivität identifiziert wurde, aber keine Bereinigungsaktionen verfügbar sind. Beispiele hierfür sind die folgenden Benutzeraktivitäten: <br/>- Ein Ereignis zur Verhinderung von Datenverlust (Data [Loss Prevention,](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) DLP)<br/>– Anomalie beim Senden von E-Mails<br/>– Gesendete Schadsoftware<br/>– Gesendeter Phishing <p> Bei der Untersuchung wurden keine schädlichen URLs, Dateien oder E-Mail-Nachrichten gefunden, die korrigiert werden sollten, und keine zu behebenden Postfachaktivitäten, z. B. das Deaktivieren von Weiterleitungsregeln oder delegierung. <p> **TIPP:** Wenn Sie vermuten, dass etwas ausgelassen wurde (z. B. ein falsch negatives Ergebnis), können Sie mit dem Bedrohungs-Explorer untersuchen und [Maßnahmen ergreifen.](threat-explorer.md)|
|**Vom System beendet**|Die Untersuchung wurde beendet. Eine Untersuchung kann aus mehreren Gründen beendet werden: <br/>– Die ausstehenden Aktionen der Untersuchung sind abgelaufen. Zeit für ausstehende Aktionen nach dem Warten auf die Genehmigung für eine Woche.<br/>– Es gibt zu viele Aktionen. Wenn beispielsweise zu viele Benutzer auf schädliche URLs klicken, kann dies die Fähigkeit der Untersuchung zur Ausführung aller Analyzer überschreiten, sodass die Untersuchung beendet wird.<p> **TIPP:** Wenn eine Untersuchung beendet wird, bevor Aktionen ergriffen wurden, versuchen Sie, Bedrohungen mithilfe des [Bedrohungs-Explorers](threat-explorer.md) zu finden und zu adressiert.|
|**Ausstehende Aktion**|Die Untersuchung hat eine Bedrohung gefunden, z. B. eine schädliche E-Mail, eine schädliche URL oder eine riskante Postfacheinstellung, und eine Maßnahme zur Behebung dieser Bedrohung wartet auf [eine Genehmigung.](air-review-approve-pending-completed-actions.md) <p> Der **Zustand "Ausstehende Aktion"** wird ausgelöst, wenn eine Bedrohung mit einer entsprechenden Aktion gefunden wird. Die Liste der ausstehenden Aktionen kann sich jedoch erhöhen, wenn eine Untersuchung ausgeführt wird. Zeigen Sie Untersuchungsdetails an, um zu sehen, ob weitere Elemente noch nicht abgeschlossen sind.|
|**Bereinigt**|Die Untersuchung wurde abgeschlossen, und alle Abhilfemaßnahmen wurden genehmigt (als vollständig behoben angegeben). <p> **HINWEIS:** Genehmigte Abhilfemaßnahmen können Fehler enthalten, die verhindern, dass die Aktionen ergriffen werden. Unabhängig davon, ob Korrekturaktionen erfolgreich abgeschlossen wurden, ändert sich der Untersuchungsstatus nicht. Zeigen Sie Untersuchungsdetails an.|
|**Teilweise behoben**|Die Untersuchung führte zu Korrekturmaßnahmen, und einige wurden genehmigt und abgeschlossen. Andere Aktionen sind noch [ausstehend.](air-review-approve-pending-completed-actions.md)|
|**Fehlgeschlagen**|Mindestens ein Untersuchungsanalysegerät ist auf ein Problem ge gelaufen, bei dem es nicht ordnungsgemäß abgeschlossen werden konnte. <p> **HINWEIS:** Wenn eine Untersuchung fehlschlägt, nachdem Korrekturaktionen genehmigt wurden, sind die Korrekturaktionen möglicherweise noch erfolgreich. Zeigen Sie die Untersuchungsdetails an. |
|**Durch Einschränkung in die Warteschlange eingereiht**|Eine Untersuchung wird in einer Warteschlange gespeichert. Wenn andere Untersuchungen abgeschlossen sind, beginnen Untersuchungen in der Warteschlange. Die Drosselung trägt dazu bei, eine schlechte Dienstleistung zu vermeiden.  <p> **TIPP:** Ausstehende Aktionen können einschränken, wie viele neue Untersuchungen ausgeführt werden können. Stellen Sie sicher, [dass Ausstehende Aktionen genehmigt (oder abgelehnt) werden.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Beendet durch Einschränkung**|Wenn eine Untersuchung zu lang in der Warteschlange gehalten wird, wird sie angehalten. <p> **TIPP:** Sie können [eine Untersuchung im Bedrohungs-Explorer starten.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Anzeigen von Details einer Untersuchung

1. Wechseln Sie zum Microsoft 365 Security [https://security.microsoft.com](https://security.microsoft.com) Center, und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **"Aktionscenter" aus.**
3. Wählen Sie auf  den **Registerkarten "Ausstehend"** oder "Verlauf" eine Aktion aus. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich die Seite **"Untersuchung öffnen" aus.** 
5. Verwenden Sie die verschiedenen Registerkarten, um mehr über die Untersuchung zu erfahren.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung

Bestimmte Arten von Warnungen lösen eine automatisierte Untersuchung in Microsoft 365 aus. Weitere Informationen finden Sie unter [Warnungsrichtlinien, die automatisierte Untersuchungen auslösen.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Wechseln Sie zum Microsoft 365 Security [https://security.microsoft.com](https://security.microsoft.com) Center, und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **"Aktionscenter" aus.**
3. Wählen Sie auf  den **Registerkarten "Ausstehend"** oder "Verlauf" eine Aktion aus. Der Flyoutbereich wird geöffnet.
4. Wählen Sie im Flyoutbereich die Seite **"Untersuchung öffnen" aus.** 
5. Wählen **Sie** die Registerkarte "Warnungen" aus, um eine Liste aller Warnungen anzuzeigen, die dieser Untersuchung zugeordnet sind.
6. Wählen Sie ein Element in der Liste aus, um den Flyoutbereich zu öffnen. Dort können Sie weitere Informationen zur Warnung anzeigen.

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- E-Mail-Zählungen werden zum Zeitpunkt der Untersuchung berechnet, und einige Zahlen werden neu berechnet, wenn Sie Untersuchungsf flyouts öffnen (basierend auf einer zugrunde liegenden Abfrage).

- Die E-Mail-Zähler,  die für die E-Mail-Cluster auf der Registerkarte "E-Mail" angezeigt werden, und der wert der E-Mail-Menge, der im Clusterf flyout angezeigt wird, werden zum Zeitpunkt der Untersuchung berechnet und ändern sich nicht.

- Die E-Mail-Anzahl unten  auf der Registerkarte "E-Mail" des E-Mail-Cluster-Flyouts und die Anzahl der im Explorer angezeigten E-Mail-Nachrichten spiegeln die E-Mail-Nachrichten wider, die nach der ersten Analyse der Untersuchung empfangen wurden.

  Ein E-Mail-Cluster, der eine ursprüngliche Menge von 10 E-Mail-Nachrichten zeigt, würde also insgesamt 15 E-Mail-Nachrichten anzeigen, wenn zwischen der Untersuchungsphase und wenn der Administrator die Untersuchung überprüft. Ebenso können alte Untersuchungen eine höhere Anzahl als in Explorer-Abfragen zeigen, da Daten in Microsoft Defender für Office 365 Plan 2 nach sieben Tagen für Testversionen und nach 30 Tagen für kostenpflichtige Lizenzen ablaufen.

  Das Anzeigen der Anzahl der historischen und aktuellen Zahlen in verschiedenen Ansichten erfolgt, um die E-Mail-Auswirkungen zum Zeitpunkt der Untersuchung und die aktuellen Auswirkungen bis zum Zeitpunkt der Behebung anzugeben.

- Im Kontext von E-Mails wird im Rahmen der Untersuchung möglicherweise eine Bedrohungsoberfläche für Volumenanomalie sehen. Eine Volumenanomalie weist auf einen Anstieg ähnlicher E-Mail-Nachrichten um die Untersuchungsereigniszeit im Vergleich zu früheren Zeitrahmen hin. Ein Anstieg des E-Mail-Datenverkehrs zusammen mit bestimmten Merkmalen (z. B. Betreff- und Absenderdomäne, Body-Ähnlichkeit und Absender-IP) ist typisch für den Beginn von E-Mail-Kampagnen oder Angriffen. Massen-, Spam- und legitime E-Mail-Kampagnen teilen diese Merkmale jedoch häufig.

- Volumenanomalien stellen eine potenzielle Bedrohung dar und könnten daher im Vergleich zu Schadsoftware- oder Phishingbedrohungen, die mithilfe von Virenschutzmodule, Detonation oder schadhafter Reputation identifiziert werden, weniger schädlich sein.

- Sie müssen nicht jede Aktion genehmigen. Wenn Sie der empfohlenen Aktion nicht zustimmen oder Ihre Organisation bestimmte Arten von  Aktionen nicht aussuchet, können Sie die Aktionen ablehnen oder einfach ignorieren und keine Maßnahmen ergreifen.

- Wenn Sie alle Aktionen genehmigen und/oder ablehnen, kann die Untersuchung vollständig geschlossen werden (der Status wird behoben), während einige Aktionen unvollständig bleiben, was dazu führt, dass der Untersuchungsstatus in einen teilweise behobenen Zustand geändert wird.

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen und Genehmigen ausstehender Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
