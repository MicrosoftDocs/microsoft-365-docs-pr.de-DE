---
title: Anzeigen der Ergebnisse einer automatisierten Untersuchung in Microsoft 365
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
description: Während und nach einer automatischen Untersuchung in Microsoft 365 können Sie die Ergebnisse und die wichtigsten Ergebnisse anzeigen.
ms.date: 11/05/2020
ms.openlocfilehash: 0f472c117ff1f6c2b563063d0eeb9a27cc5afebe
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931990"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Details und Ergebnisse einer automatisierten Untersuchung in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn in [Microsoft Defender für Office 365](office-365-atp.md)eine [automatisierte Untersuchung](office-365-air.md) erfolgt, stehen Details zu dieser Untersuchung während und nach dem automatisierten Untersuchungsprozess zur Verfügung. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie diese Details im Microsoft 365 Security Center anzeigen. Unter Suchdetails bieten Ihnen den aktuellen Status und die Möglichkeit, ausstehende Aktionen zu genehmigen.

## <a name="investigation-status"></a>Ermittlungsstatus

Der unter Suchstatus gibt den Fortschritt der Analyse und der Aktionen an. Während der Untersuchung wird der Status geändert, um anzugeben, ob Bedrohungen gefunden wurden und ob Aktionen genehmigt wurden.

|Status|Beschreibung|
|:---|:---|
|**Wird gestartet** | Die Untersuchung wurde ausgelöst und wartet darauf, mit der Ausführung zu beginnen.|
|**Wird ausgeführt** | Der Ermittlungsprozess wurde gestartet und ist im Gange. Dieser Status tritt auch ein, wenn [Ausstehende Aktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions) genehmigt werden.|
|**Keine Bedrohungen gefunden** | Die Untersuchung ist abgeschlossen, und es wurden keine Bedrohungen (Benutzerkonto, e-Mail-Nachricht, URL oder Datei) identifiziert. <br/><br/>**Tipp** : Wenn Sie vermuten, dass etwas verpasst wurde (beispielsweise ein falsches negativ), können Sie mit [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)Aktionen ausführen.|
|**Bedrohungen gefunden** |Die automatische Untersuchung hat Probleme festgestellt, aber es gibt keine spezifischen Korrekturaktionen zur Lösung dieser Probleme.<br/><br/> Der Status " **Bedrohungen gefunden** " kann auftreten, wenn ein bestimmter Typ von Benutzeraktivität identifiziert wurde, aber keine Bereinigungsaktionen verfügbar sind. Beispiele hierfür sind die folgenden Benutzeraktivitäten: <br/>-DLP-Ereignis ( [Data Loss Prevention, Verhinderung von Datenverlust](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) ) <br/>-Eine e-Mail-Sende Anomalie <br/>-Gesendete Schadsoftware <br/>-Phishing gesendet<br/>Die Untersuchung hat festgestellt, dass keine böswilligen URLs, Dateien oder e-Mail-Nachrichten behoben werden konnten, und keine zu reparierende Post Fach Aktivität wie das Deaktivieren von Weiterleitungsregeln oder Delegierung. <br/><br/>**Tipp** : Wenn Sie vermuten, dass etwas verpasst wurde (beispielsweise ein falsches negativ), können Sie mit dem [Threat-Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)untersuchen und Aktionen ausführen.|
|**Beendet von System** | Die Untersuchung wurde angehalten. Eine Untersuchung kann aus mehreren Gründen beendet werden:<br/>– Die ausstehenden Aktionen der Untersuchung sind abgelaufen. Timeout für ausstehende Aktionen nach dem warten auf die Genehmigung für eine Woche. <br/>-Es gibt zu viele Aktionen. Wenn beispielsweise zu viele Benutzer auf böswillige URLs klicken, kann die Untersuchung die Möglichkeit überschreiten, alle Analyzer auszuführen, sodass die Untersuchung angehalten wird. <br/><br/>**Tipp** : Wenn eine Untersuchung angehalten wird, bevor Aktionen durchgeführt wurden, versuchen Sie, Bedrohungen mithilfe von [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) zu finden und zu adressieren.|
|**Ausstehende Aktion** | Bei der Untersuchung wurde eine Bedrohung festgestellt, beispielsweise eine böswillige e-Mail, eine bösartige URL oder eine riskante Postfacheinstellung, und eine Aktion zum Beheben dieser Bedrohung wartet auf die [Genehmigung](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions).<br/><br/>Der Status **ausstehende Aktion** wird ausgelöst, wenn eine Bedrohung mit einer entsprechenden Aktion gefunden wird. Die Liste der ausstehenden Aktionen kann sich jedoch bei einer Untersuchung vergrössern. Überprüfen Sie das [Ermittlungsprotokoll](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#playbook-log) , um festzustellen, ob andere Elemente noch ausstehen.|
|**Bereinigt** | Die Untersuchung wurde abgeschlossen, und alle Korrekturaktionen wurden genehmigt (Dies wird als vollständig korrigiert festgestellt).<br/><br/>**Hinweis** : genehmigte Korrekturaktionen können Fehler aufweisen, die verhindern, dass die Aktionen ausgeführt werden. Unabhängig davon, ob Korrekturaktionen erfolgreich abgeschlossen wurden, ändert sich der Ermittlungsstatus nicht. Überprüfen Sie das [Ermittlungsprotokoll](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) auf detaillierte Ergebnisse.|
|**Teilweise behoben**| Die Untersuchung führte zu Korrekturaktionen, einige wurden genehmigt und abgeschlossen. Andere Aktionen sind noch [Ausstehend](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions).|
|**Fehlgeschlagen** | Mindestens ein Ermittlungs Analyse-Analyzer hat ein Problem aufgetreten, bei dem es nicht ordnungsgemäß abgeschlossen werden konnte. <br/><br/>**Hinweis** : Wenn eine Untersuchung fehlschlägt, nachdem Korrekturaktionen genehmigt wurden, sind die Korrekturaktionen möglicherweise weiterhin erfolgreich. Überprüfen Sie das [Ermittlungsprotokoll](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) auf detaillierte Ergebnisse.|
|**Durch Drosselung in der Warteschlange** | In einer Warteschlange wird eine Untersuchung durchgeführt. Wenn andere Untersuchungen abgeschlossen sind, beginnen Warteschlangen Untersuchungen. Die Drosselung hilft bei der Vermeidung schlechter Dienstleistung. <br/><br/>**Tipp** : Ausstehende Aktionen können einschränken, wie viele neue Untersuchungen ausgeführt werden können. Stellen Sie sicher, dass [Ausstehende Aktionen genehmigt (oder abgelehnt)](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions)werden.|
|**Durch Drosselung beendet** | Wenn eine Untersuchung zu lange in der Warteschleife stattfindet, wird Sie angehalten. <br/><br/>**Tipp** : Sie können [eine Untersuchung von Threat Explorer starten](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).|
|

## <a name="view-details-of-an-investigation"></a>Anzeigen von Details einer Untersuchung

1. Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ), und melden Sie sich an.

2. Führen Sie eine der folgenden Aktionen aus:

    - Wechseln Sie zu **Threat Management**  >  **Dashboard**. Dadurch gelangen Sie zum [Sicherheits Dashboard](security-dashboard.md). Die Air-Widgets werden am oberen Rand des [Sicherheits Dashboards](security-dashboard.md)angezeigt. Wählen Sie ein Widget aus, beispielsweise **Zusammenfassung der Untersuchungen**.

    - Wechseln Sie zu **Threat Management**  >  **Investigations**.

    Mit beiden Methoden gelangen Sie zu einer Liste von Untersuchungen.

    ![Haupt Untersuchungs Seite für Air](../../media/air-maininvestigationpage.png)

3. Wählen Sie in der Liste der Untersuchungen ein Element in der Spalte **ID** aus. Dadurch wird die Seite Ermittlungs Details geöffnet, beginnend mit dem unter Such Diagramm in der Ansicht.

    ![Seite "Luft Untersuchungs Diagramm"](../../media/air-investigationgraphpage.png)

   Verwenden Sie die verschiedenen Registerkarten, um mehr über die Untersuchung zu erfahren.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung

Bestimmte Arten von Warnungen lösen eine automatische Untersuchung in Microsoft 365 aus. Weitere Informationen finden Sie unter [Alert Policies that Trigger Automated Investigations](office-365-air.md#which-alert-policies-trigger-automated-investigations). 

Verwenden Sie das folgende Verfahren, um Details zu einer Warnung anzuzeigen, die einer automatisierten Untersuchung zugeordnet ist.

1. Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ), und melden Sie sich an.

2. Wechseln Sie zu **Threat Management**  >  **Investigations**.

3. Wählen Sie in der Liste der Untersuchungen ein Element in der Spalte **ID** aus.

4. Wenn Details zu einer Untersuchung geöffnet sind, wählen Sie die Registerkarte **Benachrichtigungen** aus. Alle Warnungen, die die Untersuchung ausgelöst haben, werden hier aufgelistet.

5. W?hlen Sie ein Element in der Liste aus. Ein Flyout mit Details zur Warnung und Links zu zusätzlichen Informationen und Aktionen wird geöffnet.

6. Überprüfen Sie die Informationen im Flyout, und nehmen Sie abhängig von der jeweiligen Warnung eine Aktion vor, beispielsweise zum **Auflösen** , unter **drücken** oder **Benachrichtigen von Benutzern**.

    - **Resolve** entspricht dem Schließen einer Warnung.

    - Unter **drücken** bewirkt, dass eine Richtlinie Warnungen für einen bestimmten Zeitraum nicht auslöst

    - **Benutzer benachrichtigen** startet eine e-Mail mit bereits eingegebenen e-Mail-Adressen der Benutzer und ermöglicht es dem Team für Sicherheitsvorgänge, diesen Benutzern eine Nachricht zu geben. (Dies ähnelt dem Senden einer Nachricht an Empfänger mithilfe von [Threat Explorer](threat-explorer.md).)

## <a name="how-to-use-the-various-tabs"></a>Verwenden der verschiedenen Registerkarten

Die folgenden Abschnitte führen Sie durch die verschiedenen Registerkarten auf der Seite Automatische Untersuchungen und darüber, wie Sie die Informationen verwenden können.

### <a name="automated-investigations-page"></a>Seite "automatische Untersuchungen"

Die Seite Automatische Untersuchungen zeigt die Ermittlungen Ihrer Organisation und ihre aktuellen Status.

![Haupt Untersuchungs Seite für Air](../../media/air-maininvestigationpage.png)

Sie können:

- Navigieren Sie direkt zu einer Untersuchung (Wählen Sie eine **Ermittlungs-ID** aus).

- Anwenden von Filtern. Wählen Sie zwischen **Ermittlungstyp** , **Zeitbereich** , **Status** oder einer Kombination aus diesen aus.

- Exportieren Sie die Daten in eine CSV-Datei.

### <a name="investigation-graph"></a>Untersuchungsdiagramm

Wenn Sie eine bestimmte Untersuchung öffnen, wird die Seite "Ermittlungs Diagramm" angezeigt. Auf dieser Seite werden alle unterschiedlichen Entitäten angezeigt: e-Mail-Nachrichten, Benutzer (und deren Aktivitäten) und Geräte, die automatisch als Teil der ausgelösten Warnung untersuchtwurden.

![Seite "Luft Untersuchungs Diagramm"](../../media/air-investigationgraphpage.png)

Sie können:

- Erhalten Sie eine visuelle Übersicht über die aktuelle Untersuchung.

- Hier wird eine Zusammenfassung der Untersuchungsdauer angezeigt.

- Wählen Sie einen Knoten in der Visualisierung aus, um Details zu diesem Knoten anzuzeigen.

- Wählen Sie eine Registerkarte oben aus, um Details für diese Registerkarte anzuzeigen.

### <a name="alert-investigation"></a>Warnungs Ermittlung

Auf der Registerkarte **Benachrichtigungen** für eine Untersuchung können Sie Warnungen anzeigen, die für die Untersuchung relevant sind. Details umfassen die Warnung, die die Untersuchung ausgelöst hat, und andere korrelierte Warnungen, wie etwa riskante Anmeldungen, [DLP-Richtlinien](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) Verstöße usw., die mit der Untersuchung korreliert sind. Auf dieser Seite kann ein Sicherheitsanalytiker auch weitere Details zu einzelnen Benachrichtigungen anzeigen.

![Seite "Luft Warnungen"](../../media/air-investigationalertspage.png)

Sie können:

- Erhalten Sie eine visuelle Übersicht über die aktuelle Auslöse Warnung und alle zugeordneten Warnungen.

- Wählen Sie eine Warnung in der Liste aus, um eine Ausklappseite zu öffnen, auf der vollständige Warnungsdetails angezeigt werden.

### <a name="email-investigation"></a>E-Mail-Untersuchung

Auf der Registerkarte **e-Mail** für eine Untersuchung können Sie die ursprünglichen e-Mails und die Cluster ähnlicher e-Mails sehen, die im Rahmen der Untersuchung identifiziert wurden. Auf der Registerkarte **e** -Mail werden auch e-Mail-Elemente im Zusammenhang mit der Untersuchung angezeigt, beispielsweise die e-Mail-Details des Benutzers, die gemeldeten e-Mails, die e-Mail-Nachricht (en), die aufgrund von Malware/Phishing zapped wurden

![Seite für die Untersuchung von Air e-Mail](../../media/air-investigationemailpage.png)

Mit e-Mail-Untersuchung können Sie:

- Erhalten Sie eine visuelle Übersicht über die aktuellen Clustering-Ergebnisse und Bedrohungen, die gefunden wurden.

- Klicken Sie auf eine Cluster Entität oder eine Bedrohungsliste, um eine Ausklappseite zu öffnen, auf der die vollständigen Warnungsdetails angezeigt werden.

- Untersuchen Sie den e-Mail-Cluster weiter, indem Sie oben auf der Registerkarte **e-Mail-Cluster Details** auf den Link **in Explorer öffnen** klicken.

![Air Investigation e-Mail mit Flyout-Details](../../media/air-investigationemailpageflyoutdetails.png)

Angesichts der schieren Menge an e-Mails, die Benutzer in einer Organisation senden und empfangen, sowie der mehr Benutzer Natur von e-Mail-Kommunikation und Angriffen kann der folgende Vorgang eine erhebliche Zeit in Anspruch nehmen:

1. Gruppieren von e-Mail-Nachrichten basierend auf ähnlichen Attributen aus einer Nachrichtenkopfzeile, einem Text, einer URL und Anlagen

2. Trennen von böswilligen e-Mails von der guten e-Mail-Nachricht

3. Ausführen von Aktionen in böswilligen e-Mail-Nachrichten

Mit Air wird dieser Prozess automatisiert, sodass Zeit und Aufwand für das Sicherheitsteam Ihres Unternehmens gespart werden. 

#### <a name="types-of-email-clusters"></a>Arten von e-Mail-Clustern

Während des e-Mail-Analyse Schritts können drei verschiedene Arten von e-Mail-Clustern identifiziert werden: Ähnlichkeits Cluster (alle Untersuchungen), Indikator Cluster (alle Untersuchungen) und Post Fach/Benutzer Cluster. In der folgenden Tabelle werden diese Arten von e-Mail-Clustern beschrieben.

|E-Mail-Cluster  |Beschreibung  |
|---------|---------|
|Ähnlichkeits Cluster     |E-Mail-Nachrichten, die durch die Suche nach e-Mails mit ähnlichen Absender-und Inhaltsattributen identifiziert wurden. Diese Cluster werden basierend auf den ursprünglichen Entdeckungs Ergebnissen auf schädliche Inhalte ausgewertet. E-Mail-Cluster mit ausreichenden bösartigen e-Mail-Erkennungen werden als böswillig betrachtet.         |
|Indikator Cluster | E-Mail-Nachrichten, die durch die Suche nach der gleichen Indikator Entität (Datei Hash oder URL) aus der ursprünglichen e-Mail identifiziert werden. Wenn die ursprüngliche Datei/URL-Entität als bösartig identifiziert wird, wendet Air das Indikator Urteil auf den gesamten Cluster von e-Mail-Nachrichten an, die diese Entität enthalten. Eine als Schadsoftware bezeichnete Datei bedeutet, dass der Cluster von e-Mail-Nachrichten mit dieser Datei als Schadsoftware-e-Mail-Nachrichten behandelt wird. |
|Postfachbenutzer Cluster | E-Mail-Nachrichten im Zusammenhang mit dem Benutzer, der an einer Benutzer Gefährdungs Prüfung beteiligt ist  Diese e-Mail-Cluster sind für eine weitere Analyse durch das Sicherheits Betriebsteam und generieren keine e-Mail-Korrekturaktionen. <br/> Das kompromittierte User Security-Textbuch überprüft die e-Mails, die von dem Benutzer gesendet werden, der analysiert wurde, um die potenziellen Auswirkungen der e-Mails zu verstehen, die vom Postfach gesendet werden. |

> [!NOTE]
> Das Ziel des Clusterings besteht darin, andere verwandte e-Mail-Nachrichten zu suchen und zu finden, die von demselben Absender als Teil eines Angriffs oder einer Kampagne gesendet werden.  In einigen Fällen kann die legitime e-Mail eine Untersuchung auslösen (beispielsweise meldet ein Benutzer eine Marketing-e-Mail).  In diesen Szenarien sollte das e-Mail-Clustering erkennen, dass e-Mail-Cluster nicht bösartig sind – wenn dies entsprechend erfolgt, wird keine Bedrohung angezeigt, und es wird auch **keine** e-Mail-Entfernung empfohlen.

#### <a name="email-classifications"></a>E-Mail-Klassifikationen

Wenn e-Mail-Nachrichten analysiert werden, werden Sie als *bösartig* , *verdächtig* oder *sauber* klassifiziert (wie in, *nicht als Bedrohung identifiziert* ):

- Vom Postfach/Benutzer gesendete *böswillige e-Mails* deuten auf mögliche Gefährdung des Postfachs/Kontos hin. Andere Benutzer/Postfächer, die potenziell durch böswillige e-Mails im Rahmen eines Kompromisses beeinträchtigt werden, werden angezeigt.

- *Verdächtige e-Mails* , die vom Postfach/Benutzer gesendet werden, deuten auf das Potenzial für ein kompromittiertes Konto oder unerwünschte e-Mail-Aktivitäten hin. Diese Nachrichten enthalten alle Spam/Massen-e-Mails, die vom Postfach gesendet werden.

- Durch das Postfach/den Benutzer gesendete e- *Mail* -Nachrichten (e-Mails, die nicht als Bedrohung betrachtet werden) können Ihrem Sicherheits Betriebsteam eine Ansicht der gesendeten legitimen Benutzer-e-Mails zur Verfügung stellen. Diese e-Mails können jedoch auch Daten Ausschleusen, wenn das e-Mail-Konto kompromittiert wird.

#### <a name="more-about-email-counts"></a>Weitere Informationen zu e-Mail-Zählungen

Die auf der Registerkarte e-Mail-Adresse angegebene Anzahl von e-Mails stellt derzeit die Gesamtsumme aller e-Mail-Nachrichten dar, die auf der Registerkarte **e-Mail** angezeigt werden. Da e-Mail-Nachrichten in mehreren Clustern vorhanden sind, ist die tatsächliche Gesamtanzahl der identifizierten e-Mail-Nachrichten (und von Korrekturaktionen betroffen) die Anzahl der eindeutigen e-Mail-Nachrichten, die in allen Clustern und e-Mail-Nachrichten der ursprünglichen Empfänger vorhanden sind.

Sowohl [Explorer](threat-explorer.md) als auch Air zählen e-Mail-Nachrichten pro Empfänger, da sich die Sicherheits Urteile, Aktionen und Zustellungsorte auf Empfängerbasis unterscheiden. Eine ursprüngliche e-Mail-Nachricht, die an drei Benutzer gesendet wird, zählt also insgesamt drei e-Mail-Nachrichten statt einer e-Mail. 

Es kann vorkommen, dass eine e-Mail zwei oder mehr Mal gezählt wird, beispielsweise wenn eine e-Mail mehrere Aktionen enthält oder wenn mehrere Kopien der e-Mail vorhanden sind, wenn alle Aktionen ausgeführt werden. 

Beispielsweise kann eine Malware-e-Mail, die bei der Zustellung erkannt wird, sowohl eine blockierte (isolierte) e-Mail-Nachricht als auch eine ersetzte e-Mail verursachen (Bedrohungs Datei wurde durch eine Warnungsdatei ersetzt und dann an das Postfach des Benutzers gesendet). Da es buchstäblich zwei Kopien der e-Mail im System gibt, werden beide möglicherweise in Cluster Zählungen gezählt.

> [!IMPORTANT]
> Im folgenden sind einige Punkte zu beachten:
> 
> - E-Mail-Anzahlen werden zum Zeitpunkt der Untersuchung berechnet, und einige Zählungen werden neu berechnet, wenn Sie Ermittlungs Flyouts (basierend auf einer zugrunde liegenden Abfrage) öffnen. 
> 
> - Die e-Mail-Anzahl, die für die e-Mail-Cluster auf der Registerkarte **e-Mail** angezeigt wird, und der Wert für die e-Mail-Menge im Cluster Flyout werden zum Zeitpunkt der Untersuchung berechnet und nicht geändert. 
> 
> - Die e-Mail-Anzahl, die am unteren Rand der Registerkarte **e** -Mail-Nachrichten im e-Mail-Cluster-Flyout und der Anzahl der im Explorer angezeigten e-Mail-Nachrichten angezeigt wird 

Daher würde ein e-Mail-Cluster, der eine ursprüngliche Menge von 10 e-Mail-Nachrichten anzeigt, eine e-Mail-Listen Summe von 15 anzeigen, wenn fünf weitere e-Mail-Nachrichten zwischen der Ermittlungs Analysephase eingehen und der Administrator die Untersuchung überprüft. Ebenso können alte Untersuchungen mit höheren Zählungen beginnen, als Explorer-Abfragen anzeigen, da Daten in Microsoft Defender für Office 365 Plan 2 nach 7 Tagen für Versuche und nach 30 Tagen für bezahlte Lizenzen ablaufen.  

Das Anzeigen der Anzahl der historischen und aktuellen Zählungen in unterschiedlichen Ansichten wird durchgeführt, um die e-Mail-Auswirkungen zum Zeitpunkt der Untersuchung und die aktuellen Auswirkungen bis zur Ausführung der Wiederherstellung anzugeben.

> [!NOTE]
> Im Zusammenhang mit e-Mails wird möglicherweise im Rahmen der Untersuchung eine Bedrohungs Fläche für Volumen Anomalien angezeigt. Eine Volumen Anomalie gibt eine Spitze in ähnlichen e-Mail-Nachrichten um die Ermittlungsereignis Zeit im Vergleich zu früheren Zeitrahmen an. Diese Spitze im e-Mail-Datenverkehr mit ähnlichen Merkmalen (z. b. Betreff-und Absenderdomäne, Text Ähnlichkeit und Absender-IP) ist typisch für den Start von e-Mail-Kampagnen oder-Angriffen. Massen-, Spam-und legitime e-Mail-Kampagnen teilen diese Merkmale jedoch häufig. 
>
> Volumen Anomalien stellen eine potenzielle Bedrohung dar und können dementsprechend im Vergleich zu Malware-oder Phishing-Bedrohungen, die mit Antiviren-Engines, Detonation oder böswilliger Reputation identifiziert werden, eine geringere schwere aufweisen.

### <a name="user-investigation"></a>Benutzer Ermittlung

Auf der Registerkarte **Benutzer** werden alle Benutzer angezeigt, die als Teil der Untersuchung identifiziert wurden. Benutzerkonten werden in der Untersuchung angezeigt, wenn ein Ereignis oder ein Hinweis darauf besteht, dass diese Benutzerkonten möglicherweise betroffen oder beeinträchtigt werden.

In der folgenden Abbildung zeigt Air beispielsweise Indikatoren für Kompromisse und Anomalien basierend auf einer neuen Posteingangsregel, die erstellt wurde. Weitere Details (Beweise) der Untersuchung stehen über detaillierte Ansichten auf dieser Registerkarte zur Verfügung. Zu den Indikatoren für Kompromisse und Anomalien können auch anomale Erkennungen von [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)gehören.

![Seite "Air Investigation Users"](../../media/air-investigationuserspage.png)

Sie können:

- Erhalten Sie eine visuelle Übersicht über identifizierte Benutzer Ergebnisse und gefundene Risiken.

- Wählen Sie einen Benutzer aus, um eine Ausklappseite zu öffnen, auf der die vollständigen Warnungsdetails angezeigt werden.

### <a name="machine-investigation"></a>Maschinelle Untersuchung

Auf der Registerkarte " **Computer** " werden alle Computer angezeigt, die als Teil der Untersuchung identifiziert wurden.

![Seite "Air Investigation Machine"](../../media/air-investigationmachinepage.png)

Im Rahmen einiger Textbuch-Elemente korreliert Air die e-Mail-Bedrohungen mit Geräten (beispielsweise gezappte Schadsoftware). Beispielsweise übergibt eine Untersuchung einen bösartigen Datei Hash an [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) , um den Endpunkt zu untersuchen. Dies ermöglicht eine automatisierte Untersuchung relevanter Computer für Ihre Benutzer, um sicherzustellen, dass Bedrohungen sowohl in der Cloud als auch in ihren Endpunkten behandelt werden.

Sie können:

- Erhalten Sie eine visuelle Übersicht über die gefundenen aktuellen Computer und Bedrohungen.

-  Wählen Sie einen Computer aus, um eine Ansicht zu öffnen, die im entsprechenden [Microsoft Defender für Endpoint Investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) im Microsoft Defender Security Center angezeigt wird.

### <a name="entity-investigation"></a>Untersuchung von Entitäten

Auf der Registerkarte **Entitäten** werden die Entitäten, die im Rahmen der Untersuchung identifiziert und analysiert wurden, angezeigt.

Hier sehen Sie die untersuchten Entitäten und Details der Entitätstypen wie e-Mail-Nachrichten, Cluster, IP-Adressen, Benutzer und vieles mehr. Sie können auch sehen, wie viele Entitäten analysiert wurden, und die Bedrohungen, die jedem zugeordnet wurden.

![Seite "Air Investigation Entities"](../../media/air-investigationentitiespage.png)

Sie können:

- Erhalten Sie eine visuelle Übersicht über die gefundenen Ermittlungs Entitäten und-Bedrohungen.

- Wählen Sie eine Entität aus, um eine Ausklappseite zu öffnen, auf der die zugehörigen Entitäts Details angezeigt werden.

![Details zu Air Investigation Entities](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Manuskript Protokoll

Auf der Registerkarte **Protokoll** werden alle Schritte im Textbuch angezeigt, die während der Untersuchung aufgetreten sind. Das Protokoll erfasst einen vollständigen bestand aller Analysatoren und Aktionen, die von Office 365 automatischen Ermittlungsfunktionen als Teil von Air abgeschlossen wurden. Es bietet eine klare Sicht auf alle Schritte, einschließlich der Aktion selbst, eine Beschreibung und die Dauer des tatsächlichen von Anfang bis Ende.

![Seite "Air Investigation log"](../../media/air-investigationlogpage.png)

Sie können:

- Erhalten Sie eine visuelle Übersicht über die ausgeführten Schritte im Textbuch.

- Exportieren Sie die Ergebnisse in eine CSV-Datei.
- Filtern Sie die Ansicht.

### <a name="recommended-actions"></a>Empfohlene Aktionen

Auf der Registerkarte **Aktionen** werden alle Textbuch-Aktionen angezeigt, die nach Abschluss der Untersuchung zur Korrektur empfohlen werden. Durch Aktionen werden die Schritte erfasst, die Microsoft am Ende einer Untersuchung empfiehlt. Sie können hier Korrekturaktionen durch Auswählen einer oder mehrerer Aktionen durchführen. 

Durch Auswählen von **genehmigen** kann die Wiederherstellung beginnen. (Entsprechende Berechtigungen sind erforderlich – die **Such-und Säuberungs** Rolle ist erforderlich, um Aktionen von Explorer und Air auszuführen). 

Beispielsweise kann ein Sicherheits Leser Aktionen anzeigen, aber nicht genehmigen. 

> [!IMPORTANT]
> Sie müssen nicht jede Aktion genehmigen. Wenn Sie mit der empfohlenen Aktion nicht einverstanden sind oder Ihre Organisation keine bestimmten Arten von Aktionen ausgewählt hat, können Sie die Aktionen **ablehnen** oder einfach ignorieren und keine Aktionen ausführen. Durch das genehmigen und/oder ablehnen aller Aktionen kann die Untersuchung vollständig abgeschlossen werden (der Status wird korrigiert), während einige Aktionen unvollständig sind und der unter Suchstatus in einen teilweise korrigierten Zustand wechselt.

![Seite "Luft Ermittlungsaktionen"](../../media/air-investigationactionspage.png)

Sie können:

- Erhalten Sie eine visuelle Übersicht über die empfohlenen Aktionen im Textbuch.

- Wählen Sie eine einzelne Aktion oder mehrere Aktionen aus.

- Genehmigen oder ablehnen von empfohlenen Aktionen mit Kommentaren.

- Exportieren Sie die Ergebnisse in eine CSV-Datei.

- Filtern Sie die Ansicht.

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen und genehmigen ausstehender Aktionen](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)

