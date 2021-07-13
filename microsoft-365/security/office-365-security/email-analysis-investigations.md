---
title: E-Mail-Analyse in Untersuchungen für Microsoft Defender für Office 365
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
keywords: Automatisierte Reaktion auf Vorfälle, Untersuchung, Behebung, Bedrohungsschutz
description: Erfahren Sie, wie die E-Mail-Analyse in Untersuchungen in Microsoft Defender für Office 365 funktioniert.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d222e1c8b6b5ca9e111b1dbe6b7fb31138a157b2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395120"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>E-Mail-Analyse in Untersuchungen für Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Während der automatisierten Untersuchung von Warnungen analysiert Microsoft Defender für Office 365 die ursprüngliche E-Mail auf Bedrohungen und identifiziert andere E-Mails, die mit der ursprünglichen E-Mail zusammenhängen und möglicherweise Teil eines Angriffs sind. Diese Analyse ist wichtig, da E-Mail-Angriffe selten aus einer einzelnen E-Mail bestehen.

Die E-Mail-Analyse der automatisierten Untersuchung identifiziert E-Mail-Cluster mithilfe von Attributen aus der ursprünglichen E-Mail, um nach E-Mails zu suchen, die von Ihrer Organisation gesendet und empfangen wurden. Dies ist vergleichbar mit einem Analysten für Sicherheitsvorgänge, der im Explorer oder bei der erweiterten Suche nach den zugehörigen E-Mails sucht. Mehrere Abfragen werden verwendet, um übereinstimmende E-Mails zu identifizieren, da Angreifer in der Regel die E-Mail-Parameter ändern, um die Sicherheitserkennung zu vermeiden. Die Clusteranalyse führt diese Überprüfungen durch, um zu ermitteln, wie E-Mails behandelt werden, die an der Untersuchung beteiligt sind:

- Die E-Mail-Analyse erstellt Abfragen (Cluster) von E-Mails mithilfe von Attributen aus der ursprünglichen E-Mail – Absenderwerte (IP-Adresse, sendende Domäne) und Inhalte (Betreff, Cluster-ID), um verwandte E-Mails zu finden.
- Wenn bei der Analyse der URLs und Dateien der ursprünglichen E-Mail ermittelt wird, dass einige schädlich sind (d. h. Schadsoftware oder Phishing), werden auch Abfragen oder Gruppen von E-Mails erstellt, die die schädliche URL oder Datei enthalten.
- Die Analyse des E-Mail-Clustering zählt die Bedrohungen, die mit den übereinstimmenden E-Mails im Cluster verbunden sind, um zu bestimmen, ob die E-Mails bösartig, verdächtig oder keine eindeutigen Bedrohungen sind. Wenn der Cluster von E-Mails, die mit der Abfrage übereinstimmen, über eine ausreichende Menge an Spam-, normalen Phishing-, Phishing- oder Schadsoftwarebedrohungen verfügt, erhält der E-Mail-Cluster diesen Bedrohungstyp. 
- Die Analyse des E-Mail-Clusterings überprüft auch den neuesten Zustellungsort der ursprünglichen E-Mails und E-Mails in den E-Mail-Clustern, um festzustellen, ob die E-Mails möglicherweise noch entfernt werden müssen oder bereits behoben oder verhindert wurden. Diese Analyse ist wichtig, da Angreifer bösartige Inhalte sowie Sicherheitsrichtlinien und Schutz zwischen Postfächern ändern können. Diese Funktion führt zu Situationen, in denen sich bösartige Inhalte möglicherweise weiterhin in Postfächern befinden, obwohl eine oder mehrere schädliche E-Mails von Zero-Hour Auto Protection (ZAP) erkannt und entfernt wurden.
- E-Mail-Cluster, die aufgrund von Schadsoftware, Phishing mit hoher Vertrauenswürdigkeit, schädlichen Dateien oder bösartigen URLs als schädlich eingestuft werden, erhalten eine ausstehende Aktion, um die E-Mails vorläufig zu löschen, wenn sich noch im Cloudpostfach (Posteingang oder Junk-Ordner) befinden. Wenn schädliche E-Mails oder E-Mail-Cluster nur "Nicht im Postfach" (blockiert, isoliert, fehlgeschlagen, vorläufig gelöscht usw.) oder "Lokal/Extern" ohne im Cloudpostfach sind, wird keine ausstehende Aktion eingerichtet, um sie zu entfernen.
- Wenn einer der E-Mail-Cluster als bösartig eingestuft wird, wird die vom Cluster identifizierte Bedrohung wieder auf die ursprüngliche E-Mail angewendet, die an der Untersuchung beteiligt ist. Dieses Verhalten ähnelt einem Analysten für Sicherheitsvorgänge, der die Ergebnisse der E-Mail-Suche verwendet, um die Bewertung einer ursprünglichen E-Mail basierend auf übereinstimmenden E-Mails zu bestimmen. Dadurch wird sichergestellt, dass das System unabhängig davon, ob urLs, Dateien oder Quell-E-Mail-Indikatoren einer ursprünglichen E-Mail erkannt werden oder nicht, böswillige E-Mails identifizieren kann, die der Erkennung durch Personalisierung, Morphen, Übehung oder andere Techniken des Angreifers möglicherweise ausweichen.
- Bei der Untersuchung von Benutzerkompromittieren werden zusätzliche E-Mail-Cluster erstellt, um potenzielle E-Mail-Probleme zu identifizieren, die vom Postfach erstellt wurden. Dieser Prozess umfasst einen sauberen E-Mail-Cluster (gute E-Mails vom Benutzer, potenzielle Datenexfiltration und potenzielle Befehls-/Steuerungs-E-Mails), verdächtige E-Mail-Cluster (E-Mails mit Spam oder normalem Phishing) und bösartige E-Mail-Cluster (E-Mails mit Schadsoftware oder Phishing mit hoher Vertrauenswürdigkeit). Diese E-Mail-Cluster stellen Daten von Analysten für Sicherheitsvorgänge bereit, um zu ermitteln, welche anderen Probleme möglicherweise durch eine Kompromittierung behoben werden müssen, und welche E-Mails möglicherweise die ursprünglichen Warnungen ausgelöst haben (z. B. Phishing/Spam, die Einschränkungen beim Senden von Benutzern ausgelöst haben).

Die Analyse des E-Mail-Clusterings über Ähnlichkeiten und bösartige Entitätsabfragen stellt sicher, dass E-Mail-Probleme vollständig identifiziert und bereinigt werden, auch wenn nur eine E-Mail aus einem Angriff identifiziert wird. Sie können Links aus den seitenseitigen Panelansichten des E-Mail-Clusters verwenden, um die Abfragen im Explorer oder in der erweiterten Suche zu öffnen, um eine ausführlichere Analyse durchzuführen und die Abfragen bei Bedarf zu ändern. Diese Funktion ermöglicht eine manuelle Einschränkung und Korrektur, wenn Die Abfragen des E-Mail-Clusters zu eng oder zu breit sind (einschließlich nicht zusammenhängender E-Mails).

Hier sind weitere Verbesserungen bei der E-Mail-Analyse in Untersuchungen.

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>AIR-Untersuchung ignoriert erweiterte Übermittlungselemente (SecOps-Postfach- und PhishEDU-Nachrichten)

Während der Analyse des E-Mail-Clusterings ignorieren alle Clusteringabfragen Sicherheitspostfächer, die als Sicherheitsvorgänge-Postfächer in der Erweiterten Übermittlungsrichtlinie eingerichtet sind. Ebenso ignorieren die E-Mail-Clusteringabfragen Phishingsimulationsnachrichten (Education), die in der Richtlinie für die erweiterte Übermittlung konfiguriert sind. Weder die SecOps- noch die PhishEdu-Ausschlusswerte werden in der Abfrage angezeigt, um die Clusterattribute einfacher und einfacher zu lesen. Durch diesen Ausschluss wird sichergestellt, dass die Bedrohungserkennung und betriebsbereite Postfächer (SecOps-Postfächer) und die Phishsimulationen (PhishEdu) während der Bedrohungsanalyse ignoriert werden und während der Behebung nicht entfernt werden. 

>[!Note]
>Wenn Sie einen E-Mail-Cluster öffnen, um ihn im Explorer aus den Details des E-Mail-Clusters anzuzeigen, werden die Postfachfilter PhishEdu und SecOps im Explorer angewendet, aber nicht angezeigt. Wenn Sie die Explorer-Filter, -Datumsangaben ändern oder die Abfrage auf der Seite aktualisieren, werden die PhishEdu/SecOps-Filterausschlüsse entfernt, und E-Mails, die diesen entsprechen, werden erneut angezeigt. Wenn Sie die Explorer-Seite mithilfe der Browseraktualisierungsfunktion aktualisieren, werden die ursprünglichen Abfragefilter erneut geladen, einschließlich der PhishEdu/SecOps-Filter– entfernen jedoch alle nachfolgenden Änderungen, die Sie vorgenommen haben.
>

## <a name="air-updates-pending-email-action-status"></a>AIR aktualisiert den Status ausstehender E-Mail-Aktionen

Die Untersuchungs-E-Mail-Analyse berechnet E-Mail-Bedrohungen und -Speicherorte zum Zeitpunkt der Untersuchung, um die Untersuchungsnachweise und -aktionen zu erstellen. Diese Daten können veraltet und veraltet sein, wenn Sich Aktionen außerhalb der Untersuchung auf die an der Untersuchung beteiligten E-Mails auswirken. Beispielsweise kann die manuelle Suche und Behebung von Sicherheitsvorgängen E-Mails bereinigen, die in einer Untersuchung enthalten sind. Ebenso haben Löschaktionen, die in parallelen Untersuchungen oder zap-automatischen Quarantäneaktionen (Zero-Hour Auto Protection) genehmigt wurden, möglicherweise E-Mails entfernt. Darüber hinaus können verzögerte Erkennungen von Bedrohungen nach der E-Mail-Zustellung die Anzahl der Bedrohungen ändern, die in den E-Mail-Abfragen/Clustern der Untersuchung enthalten sind. 

Um sicherzustellen, dass Untersuchungsaktionen auf dem neuesten Stand sind, führt jede Untersuchung mit ausstehenden Aktionen regelmäßig die E-Mail-Analyseabfragen erneut aus, um die E-Mail-Speicherorte und -Bedrohungen zu aktualisieren. 

- Wenn sich die E-Mail-Clusterdaten ändern, werden die Anzahl der Bedrohungen und der neuesten Zustellungsspeicherorte aktualisiert. 
- Wenn sich E-Mails oder E-Mail-Cluster mit ausstehenden Aktionen nicht mehr im Postfach befinden, wird die ausstehende Aktion abgebrochen, und die schädliche E-Mail/der Cluster wird als behoben betrachtet.
- Sobald alle Bedrohungen der Untersuchung wie oben erwähnt behoben oder abgebrochen wurden, wechselt die Untersuchung in einen bereinigten Zustand, und die ursprüngliche Warnung wurde aufgelöst.

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>Die Anzeige von Vorfallsnachweisen für E-Mail- und E-Mail-Cluster

E-Mail-basierter Nachweis auf der Registerkarte "Nachweise und Reaktion" für einen Vorfall zeigt jetzt die folgenden Informationen an.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="Beispiel für E-Mail-Analyseinformationen in Nachweis und Antwort" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

Aus den nummerierten Legenden in der Abbildung:

1. Sie können zusätzlich zum **Info-Center** Abhilfemaßnahmen ausführen.
2. Sie können Korrekturmaßnahmen für E-Mail-Cluster mit einer **böswilligen** Bewertung (aber nicht **verdächtig)** ausführen.
3. Für die Spambewertung von E-Mails wird Phishing in hochwahrscheinliche und normale Phishing-Nachrichten aufgeteilt.

   Bei einer Bewertung mit böswilligen Absichten sind die Bedrohungskategorien Schadsoftware, Phishing mit hoher Vertrauenswürdigkeit, bösartige URL und schädliche Dateien.

   Bei einer verdächtigen Bewertung sind die Bedrohungskategorien Spam und normaler Phishing.

4. Die Anzahl der E-Mails basiert auf dem neuesten Zustellungsort und enthält Indikatoren für E-Mails in Postfächern, nicht in Postfächern und lokal.
5. Enthält das Datum und die Uhrzeit der Abfrage, die für die neuesten Daten aktualisiert werden können.

Bei E-Mail- oder E-Mail-Clustern auf der Registerkarte **"Entitäten"** eines Vorfalls bedeutet **"Verhindert",** dass für dieses Element (E-Mail oder Cluster) keine schädlichen E-Mails im Postfach vorhanden waren. Hier ein Beispiel.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="Beispiel für eine verhinderte E-Mail" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

In diesem Beispiel ist die E-Mail bösartig, aber nicht in einem Postfach.

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen ausstehender oder abgeschlossener Wartungsaktionen](air-review-approve-pending-completed-actions.md)