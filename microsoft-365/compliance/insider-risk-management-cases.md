---
title: Fälle des Insiderrisikomanagements
description: Informationen zu Insider risk management cases in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 58c8d2cdebdef6c0307b0c234951f6d32e5009df
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820161"
---
# <a name="insider-risk-management-cases"></a>Fälle des Insiderrisikomanagements

Fälle sind das Herzstück des Insider-Risikomanagements und ermöglichen Es Ihnen, Probleme, die durch in Ihren Richtlinien definierte Risikoindikatoren generiert werden, eingehend zu untersuchen und zu handeln. Fälle werden manuell aus Warnungen in Situationen erstellt, in denen weitere Maßnahmen erforderlich sind, um ein compliancebezogenes Problem für einen Benutzer zu beheben. Jeder Fall ist auf einen einzelnen Benutzer begrenzt, und mehrere Warnungen für den Benutzer können einem vorhandenen Fall oder einem neuen Fall hinzugefügt werden. 

Nachdem Sie die Details eines Falls untersucht haben, können Sie maßnahmen:

- Senden einer Benachrichtigung an den Benutzer
- Lösen des Falls als gutartig
- Freigeben des Falls mit Ihrer ServiceNow-Instanz oder mit einem E-Mail-Empfänger
- Eskalieren des Falls für eine Erweiterte eDiscovery-Untersuchung

## <a name="cases-dashboard"></a>Falldashboard

Mit dem  Dashboard für Insider-Risikomanagementfälle können Sie Fälle anzeigen und bearbeiten. Jedes Berichts-Widget im Dashboard zeigt Informationen für die letzten 30 Tage an.

- **Aktive Fälle**: Die Gesamtzahl der untersuchten aktiven Fälle.
- **Fälle der letzten 30 Tage:** Die Gesamtanzahl der erstellten Fälle, sortiert nach *Dem Status "Aktiv"* und *"Geschlossen".*
- **Statistik**: Durchschnittliche Zeit der aktiven Fälle in Stunden, Tagen oder Monaten.

In der Fallwarteschlange werden neben dem aktuellen Status der folgenden Fallattribute alle aktiven und geschlossenen Fälle für Ihre Organisation aufgeführt:

- **Fallname**: Der Name des Falls, der definiert wird, wenn eine Warnung bestätigt und der Fall erstellt wird.  
- **Status**: Der Status des Falls, entweder *Active* oder *Closed*.
- **User**: Der Benutzer für den Fall. Wenn die Anonymisierung für Benutzernamen aktiviert ist, werden anonymisierte Informationen angezeigt.
- **Time case opened**: Die Zeit, die seit dem Öffnen des Falls vergangen ist.
- **Richtlinienwarnungen insgesamt:** Die Anzahl der in dem Fall enthaltenen Richtlinien übereinstimmungen. Diese Zahl kann steigen, wenn neue Warnungen zu dem Fall hinzugefügt werden.
- **Last updated**: The time that has passed since there has been an added case note or change in the case state.
- **Last updated by:** The name of the insider risk management analyst or investigator that last updated the case.

![Dashboard für Insider-Risikomanagementfälle](../media/insider-risk-cases-dashboard.png)

Verwenden Sie das **Suchsteuerelement,** um Nachfallnamen nach bestimmtem Text zu suchen, und verwenden Sie den Fallfilter, um Fälle nach den folgenden Attributen zu sortieren:

- Status
- Öffnung des Falls, Startdatum und Enddatum
- Letzte Aktualisierung, Startdatum und Enddatum

## <a name="filter-cases"></a>Filterfälle

Je nach Anzahl und Typ der aktiven Insider-Risikomanagementrichtlinien in Ihrer Organisation kann die Überprüfung einer großen Warteschlange von Fällen eine Herausforderung darstellen. Die Verwendung von Fallfiltern kann Analysten und Ermittlern dabei helfen, Fälle nach mehreren Attributen zu sortieren. Wählen Sie zum Filtern von Warnungen **im Falldashboard** das **Steuerelement Filter** aus. Sie können Fälle nach einem oder mehreren Attributen filtern:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Fallliste zu filtern. Die Optionen sind *Active* und *Closed*.
- **Zeitfall geöffnet:** Wählen Sie das Start- und Enddatum für den Zeitpunkt des Öffnens des Falls aus.
- **Last updated**: Select the start and end dates for when the case was updated.

## <a name="investigate-a-case"></a>Untersuchen eines Falls

Eine tiefergehende Untersuchung von Insider-Risikomanagementwarnungen ist für ordnungsgemäße Korrekturmaßnahmen von entscheidender Bedeutung. Insider risk management cases are the central management tool to dive into user risk activity history, alert details, the sequence of risk events, and to explore the content and messages exposed to risks. Risikoanalysten und Ermittler verwenden Fälle auch, um Feedback und Notizen zu überprüfen und die Fallauflösung zu verarbeiten.

Wenn Sie einen Fall auswählen, werden die Fall-Verwaltungstool geöffnet. Diese ermöglichen es Analysten und Ermittlern, sich den Fall bis ins kleinste Detail anzeigen zu lassen.

### <a name="case-overview"></a>Fallübersicht

Die Registerkarte **Fallübersicht** fasst die Warnungsaktivitäten und den Verlauf der Risikostufe für jeden Fall zusammen. 

- Das **Widget Warnungen** zeigt die Übereinstimmungen der Richtlinie für den Fall an, einschließlich des Status der Warnung, des Schweregrads des Warnungsrisikos und des Erkennens der Warnung. 
- Das Diagramm **Risikostufenverlauf** zeigt die Risikostufe des entsprechenden Benutzers in den letzten 30 Tagen. Das Liniendiagramm ermöglicht es Analysten und Ermittlern, die Entwicklung des allgemeinen Benutzerrisikos im Laufe der Zeit schnell auf einen Blick zu erfassen. 
- Das Widget **Inhalt der Risikoaktivität** fasst die Daten- und Inhaltstypen zusammen, die in Fall-Warnungen enthalten sind. Dieses Widget bietet einen Gesamtüberblick über alle Daten und Inhalte, die in diesem Fall gefährdet sind.

Der **Bereich** Falldetails ist auf allen Registerkarten für die Fallverwaltung verfügbar und fasst die Falldetails für Risikoanalysten und Ermittler zusammen. Es umfasst die folgenden Bereiche:

- **Fallname**: Der Name des Falls, dem eine automatisch generierte Fallsequenznummer vorangestellt ist, und der Name des Risikos, das der Richtlinienvorlage zugeordnet ist, mit der die erste bestätigte Warnung entspricht. 
- **Fallstatus**: Der aktuelle Status des Falls, entweder *Active* oder *Closed*.
- **Risikopunktzahl des Benutzers:** Die aktuelle berechnete Risikostufe des Benutzers für den Fall. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein.
- **Warnungen bestätigt**: Liste der Warnungen für den Benutzer, die für den Fall bestätigt wurden.
- **Zugehöriger Inhalt:** Liste der Inhalte, sortiert nach Inhaltsquellen und -typen. Beispielsweise würden Sie für gefährdete Inhalte in SharePoint Online eine Liste mit Ordner- oder Dateinamen sehen, die der Risikoaktivität für Warnungen im entsprechenden Fall zugeordnet sind.

![Details zu Insider risk management case](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Warnungen

Auf **der** Registerkarte Warnungen werden die aktuellen Warnungen zusammengefasst, die in dem Fall enthalten sind. Einem vorhandenen Fall können neue Warnungen hinzugefügt  werden, und sie werden der Warnungswarteschlange hinzugefügt, sobald sie zugewiesen sind. Die folgenden Warnungsattribute sind in der Warteschlange aufgeführt:

- Status
- Severity
- Erkannte Zeit

Wählen Sie eine Warnung aus der Warteschlange aus, um die Seite **Warnungsdetail anzeigen.**

Verwenden Sie das Suchsteuerelement, um Benachrichtigungsnamen nach bestimmtem Text zu suchen, und verwenden Sie den Warnungsfilter, um Fälle nach den folgenden Attributen zu sortieren:

- Status
- Severity
- Zeitpunkt der Erkennung, Startdatum und Enddatum

Verwenden Sie das Filtersteuerelement, um Warnungen nach mehreren Attributen zu filtern, darunter:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen sind *Bestätigt*, *Abgelehnt*, *Überprüfung erforderlich* und *Behoben*.
- **Schweregrad**: Wählen Sie einen oder mehrere Schweregrade des Warnungsrisikos aus, um die Warnungsliste zu filtern. Die Optionen sind *Hoch*, *Moderat* und *Niedrig*.
- **Erkannte Uhrzeit**: Wählen Sie das Start- und Enddatum für den Zeitpunkt der Warnungs erstellen aus.
- **Richtlinie**: Wählen Sie eine oder mehrere Richtlinien aus, um die von den ausgewählten Richtlinien generierten Warnungen zu filtern.

### <a name="user-activity"></a>Benutzeraktivität

Die Registerkarte **Benutzeraktivität** ist eines der leistungsstärksten Werkzeuge für die Analyse und Untersuchung interner Risiken bei Föllen in der Insider-Risikomanagement-Lösung. Diese Registerkarte ist so strukturiert, dass eine schnelle Überprüfung eines Falls ermöglicht wird, einschließlich einer verlaufshistorischen Zeitachse aller Warnungen, Benachrichtigungsdetails, der aktuellen Risikobewertung für den Benutzer in dem Fall, der Abfolge von Risikoereignissen und Steuerelementen, um effektive Maßnahmen zur Eindämmung der Risiken in dem Fall zu ergreifen.

![Benutzeraktivität des Insider-Risikomanagements](../media/insider-risk-user-activities.png)

1. **Zeitfilter**: Standardmäßig werden die letzten sechs Monate der im Fall bestätigten Warnungen im Diagramm Benutzeraktivität angezeigt. Sie können die Diagrammansicht problemlos filtern, indem Sie die *Registerkarten 6 Monate,* *3* Monate oder *1* Monat im Blasendiagramm auswählen.
2. **Risikobenachrichtigungsaktivität und -details:** Risikoaktivitäten werden im Diagramm Benutzeraktivität visuell als farbige Blasen angezeigt. Blasen werden für verschiedene Risikokategorien erstellt, und die Blasengröße ist proportional zur Anzahl der Risikoaktivitäten für die Kategorie. Wählen Sie eine Blase aus, um die Details für jede Risikoaktivität anzuzeigen. Zu den Details gehören:
    - **Datum** der Risikoaktivität.
    - Die **Risikoaktivitätskategorie**. Beispielsweise *E-Mails* mit Anlagen, die außerhalb der Organisation gesendet werden, oder Dateien, die *von SharePoint Online heruntergeladen werden.*
    - **Risikobewertung** für die Warnung. Diese Bewertung ist der numerische Wert für den Schweregrad des Risikos.
    - Anzahl der Ereignisse, die mit der Warnung verknüpft sind. Links zu jeder Datei oder E-Mail, die der Risikoaktivität zugeordnet ist, sind ebenfalls verfügbar.
3. **Risikosequenz (Vorschau):** Die chronologische Reihenfolge riskanter Aktivitäten ist ein wichtiger Aspekt der Risikountersuchung, und die Identifizierung dieser verwandten Aktivitäten ist ein wichtiger Bestandteil der Bewertung des Gesamtrisikos für Ihre Organisation. Verknüpfte Benachrichtigungsaktivitäten werden mit Verbindungslinien angezeigt, um zu unterstreichen, dass diese Aktivitäten einem größeren Risikobereich zugeordnet sind. Diese Ansicht von Aktivitäten kann Ermittlern dabei helfen, die Punkte für Risikoaktivitäten, die als isolierte ereignisse oder als Einzelereignisse hätten angezeigt werden können, wörtlich zu verbinden. Wählen Sie eine beliebige Blase in der Sequenz aus, um Details für alle zugeordneten Risikoaktivitäten anzuzeigen. Zu den Details gehören:

    - **Name** der Sequenz.
    - **Datum** oder **Datumsbereich** der Sequenz.
    - **Risikopunktzahl** für die Sequenz. Diese Bewertung ist die numerische Bewertung für die Abfolge der kombinierten Risikoschweregrade für alle verwandten Aktivitäten in der Sequenz.
    - **Anzahl der Ereignisse, die jeder Warnung in der Sequenz zugeordnet sind.** Links zu jeder Datei oder E-Mail, die jeder Risikoaktivität zugeordnet ist, sind ebenfalls verfügbar.
    - **Anzeigen von Aktivitäten in der Reihenfolge**. Zeigt die Sequenz als Hervorhebungslinie im Blasendiagramm an und erweitert die Warnungsdetails, um alle zugehörigen Warnungen in der Sequenz anzuzeigen.

4. **Legende der Risikoaktivität:** Am unteren Rand des Benutzeraktivitätsdiagramms hilft Ihnen eine farblich codierte Legende, die Ihnen hilft, die Risikokategorie für jede Warnung schnell zu bestimmen.
5. **Risikoaktivitätschronologie:** Die vollständige Chronologie aller mit dem Fall verbundenen Risikowarnungen wird aufgelistet, einschließlich aller Details, die in der entsprechenden Warnungsblase verfügbar sind.
6. **Fallaktionen**: Optionen zum Auflösen des Falls befinden sich auf der Symbolleiste der Fallaktion. Sie können einen Fall auflösen, eine E-Mail-Benachrichtigung an den Benutzer senden oder den Fall für eine Daten- oder Benutzeruntersuchung eskalieren.

### <a name="activity-explorer-preview"></a>Aktivitäts-Explorer (Vorschau)

>[!IMPORTANT]
>Die Registerkarte Aktivitäts-Explorer ist im Bereich Fallverwaltung für Benutzer mit auslösenden Ereignissen verfügbar, nachdem dieses Feature in Ihrer Organisation verfügbar ist.

Auf **der Registerkarte** Aktivitäts-Explorer können Risikoanalysten und Ermittler Aktivitätsdetails im Zusammenhang mit Risikowarnungen überprüfen. Beispielsweise müssen Ermittler und Analysten im Rahmen der Fallverwaltungsaktionen möglicherweise alle Risikoaktivitäten im Zusammenhang mit dem Fall überprüfen, um weitere Details zu erhalten. Mit dem **Aktivitäts-Explorer** können Prüfer schnell eine Zeitachse erkannter riskanter Aktivitäten überprüfen und alle Risikoaktivitäten identifizieren und filtern, die mit Warnungen verbunden sind.

Weitere Informationen zum Aktivitäts-Explorer finden Sie im [Artikel insider risk management alerts.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Inhaltsexplorer

Die Registerkarte **Inhaltsexplorer** ermöglicht es Risikoanalysten und Ermittlern, Kopien aller einzelnen Dateien und E-Mail-Nachrichten zu überprüfen, die mit der Risiko-Warnung verknüpft sind. Wenn beispielsweise eine Warnung erstellt wird, wenn ein Benutzer Hunderte von Dateien aus SharePoint Online herunterläutet und die Aktivität eine Richtlinienwarnung auslöst, werden alle heruntergeladenen Dateien für die Warnung erfasst und aus ursprünglichen Speicherquellen in den Fall des Insiderrisikomanagements kopiert.

Der Inhalts-Explorer ist ein leistungsstarkes Tool mit einfachen und erweiterten Such- und Filterfunktionen. Weitere Informationen zur Verwendung des Inhalts-Explorers finden Sie unter [Insider risk management Content explorer](insider-risk-management-content-explorer.md).

![Insider-Risikomanagement-Fall Inhalts-Explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Fallnotizen

Auf **der Registerkarte** Fallnotizen teilen Risikoanalysten und Ermittler Kommentare, Feedback und Einblicke zu ihrer Arbeit für den Fall. Notizen sind dauerhafte Ergänzungen zu einem Fall und können nicht mehr bearbeitet oder gelöscht werden, sobald sie gespeichert wurden. Wenn ein Fall aus einer Warnung erstellt wird, werden die im Dialogfeld **Benachrichtigung bestätigen und Insider-Risikofall erstellen** eingegebenen Kommentare automatisch als Fallnotiz hinzugefügt.

Das Dashboard für Fallnotizen zeigt Notizen des Benutzers an, der die Notiz erstellt hat, sowie die Zeit, die seit dem Speichern der Notiz vergangen ist. Verwenden Sie die Schaltfläche Suchen im Falldashboard, und geben Sie ein bestimmtes Schlüsselwort ein, um das Textfeld "Fallnotizen" nach einem bestimmten Schlüsselwort zu durchsuchen. 

So fügen Sie einem Fall eine Notiz hinzu:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **Fallnotizen** aus.
3. Wählen **Sie Fallnotiz hinzufügen aus.**
4. Geben Sie **im Dialogfeld Fallnotiz** hinzufügen Ihre Notiz für den Fall ein. Wählen **Sie Speichern** aus, um die Notiz dem Fall hinzuzufügen, oder wählen Sie **Abbrechen** schließen aus, ohne die Notiz im Fall zu speichern.

### <a name="contributors"></a>Mitwirkende

Auf der Registerkarte **Mitwirkende** können Risikoanalysten und Ermittler weitere Mitwirkende zu dem Fall hinzufügen. Standardmäßig werden alle Benutzer, denen die Rollen **Insider Risk Management Analysts** und **Insider Risk Management Investigators** zugewiesen sind, als Mitwirkende für jeden aktiven und geschlossenen Fall aufgeführt. Nur Benutzer, denen die **Rolle Insider Risk Management Investigators** zugewiesen ist, verfügen über die Berechtigung zum Anzeigen von Dateien und Nachrichten im Inhalts-Explorer.

Temporärer Zugriff auf einen Fall kann gewährt werden, indem ein Benutzer als Mitwirkender hinzugefügt wird. Mitwirkende haben alle Fallverwaltungssteuerelemente für den jeweiligen Fall, mit Ausnahme von:

- Die Berechtigung, Warnungen zu bestätigen oder zu verwerfen
- Die Berechtigung, die Mitwirkenden eines Falles zu bearbeiten
- Berechtigung zum Anzeigen von Dateien und Nachrichten im Inhalts-Explorer

So fügen Sie einem Fall einen Mitwirkenden hinzu:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **Mitwirkende** aus.
3. Wählen **Sie Mitwirkender hinzufügen aus.**
4. Geben Sie **im** Dialogfeld Mitwirkender hinzufügen den Namen des Benutzers ein, den Sie hinzufügen möchten, und wählen Sie dann den Benutzer aus der Vorgeschlagenen Benutzerliste aus. Diese Liste wird aus dem Azure Active Directory Ihres Mandantenabonnements generiert.
5. Wählen **Sie Hinzufügen** aus, um den Benutzer als Mitwirkenden hinzuzufügen, oder wählen Sie **Abbrechen** schließen das Dialogfeld aus, ohne den Benutzer als Mitwirkenden hinzuzufügen.

## <a name="case-actions"></a>Fallmaßnahmen

Risikoanalysten und Ermittler können in einem Fall in einer von mehreren Methoden Maßnahmen ergreifen, je nach Schweregrad des Falls, Risikoverlauf des Benutzers und Risikorichtlinien Ihrer Organisation. In einigen Situationen müssen Sie möglicherweise einen Fall an einen Benutzer oder eine Datenuntersuchung eskalieren, um mit anderen Bereichen Ihrer Organisation zusammenzuarbeiten und tiefer in Risikoaktivitäten zu gehen. Das Insider-Risikomanagement ist eng in andere Microsoft 365-Compliancelösungen integriert, um Ihnen bei der End-to-End-Lösungsverwaltung zu helfen.

### <a name="send-email-notice"></a>Senden von E-Mail-Benachrichtigungen

In den meisten Fällen sind Benutzeraktionen, die Insiderrisikowarnungen erstellen, unbeabsichtigt oder versehentlich. Das Senden einer Erinnerungsbenachrichtigung per E-Mail an den Benutzer ist eine effektive Methode zum Dokumentieren von Fallüberprüfungen und -aktionen und eine Methode, um Benutzer an Unternehmensrichtlinien zu erinnern oder sie auf Aktualisierungsschulungen zu verweisen. Hinweise werden aus [Benachrichtigungsvorlagen generiert, die Sie für](insider-risk-management-notices.md) Ihre Infrastruktur für insider risk management erstellen.

Es ist wichtig zu bedenken, dass das Senden einer E-Mail-Nachricht an einen Benutzer ***** den Fall nicht als _Closed* löst. In einigen Fällen sollten Sie einen Fall nach dem Senden einer Benachrichtigung an einen Benutzer offen lassen, um nach weiteren Risikoaktivitäten zu suchen, ohne einen neuen Fall zu öffnen. Wenn Sie einen Fall nach dem Senden einer Benachrichtigung auflösen möchten, müssen Sie **Fall lösen** als Folgeschritt nach dem Senden einer Benachrichtigung auswählen.

So senden Sie eine Benachrichtigung an den Benutzer, der einem Fall zugewiesen ist:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen **Sie** dann auf der Symbolleiste der Fallaktion die Schaltfläche E-Mail-Benachrichtigung senden aus.
3. Wählen Sie **im Dialogfeld E-Mail-Benachrichtigung senden** das **Dropdownsteuerelement** Eine Benachrichtigungsvorlage auswählen aus, um die Benachrichtigungsvorlage für den Hinweis auszuwählen. Diese Auswahl füllt die anderen Felder im Hinweis vorab aus.
4. Überprüfen Sie die Benachrichtigungsfelder, und aktualisieren Sie sie entsprechend. Die hier eingegebenen Werte überschreiben die Werte in der Vorlage.
5. Wählen **Sie Senden** aus, um den Hinweis an den Benutzer zu senden, oder wählen Sie **Abbrechen** Schließen Sie das Dialogfeld aus, ohne den Hinweis an den Benutzer zu senden. Alle gesendeten Benachrichtigungen werden der Fallnotizwarteschlange im **Fallnotizdashboard** hinzugefügt.

### <a name="escalate-for-investigation"></a>Eskalieren zur Untersuchung

Eskalieren Sie den Fall für die Benutzeruntersuchung in Situationen, in denen eine zusätzliche rechtliche Überprüfung für die Risikoaktivität des Benutzers erforderlich ist. Diese Eskalation öffnet einen neuen Advanced eDiscovery-Fall in Ihrer Microsoft 365-Organisation. Advanced eDiscovery bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen rechtlichen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem kann Ihr Rechtsteam den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren. Das Zuweisen eines Überprüfers als Verwahrer in einem Advanced eDiscovery-Fall, der aus einem Fall im Insider-Risikomanagement erstellt wurde, hilft Ihrem Rechtsteam dabei, angemessene Maßnahmen zu ergreifen, und die Erhaltung von Inhalten zu verwalten. Weitere Informationen zu den Advanced eDiscovery-Fällen finden Sie unter [Übersicht über Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).

So eskalieren Sie einen Fall an eine Benutzeruntersuchung:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Schaltfläche **Eskalieren** für Untersuchung auf der Symbolleiste der Fallaktion aus.
3. Geben Sie **im Dialogfeld Eskalieren für Untersuchung** einen Namen für die neue Benutzeruntersuchung ein. Geben Sie bei Bedarf Notizen zu dem Fall ein, und wählen Sie **Eskalieren aus.**
4. Überprüfen Sie die Benachrichtigungsfelder, und aktualisieren Sie sie entsprechend. Die hier eingegebenen Werte überschreiben die Werte in der Vorlage.
5. Wählen **Sie Bestätigen** aus, um den Benutzeruntersuchungsfall zu erstellen, oder wählen Sie **Abbrechen** aus, um das Dialogfeld zu schließen, ohne einen neuen Benutzeruntersuchungsfall zu erstellen.

Nachdem der Fall des Insider-Risikomanagements zu einem neuen Benutzeruntersuchungsfall eskaliert wurde, können Sie den neuen Fall im **Bereich eDiscovery** Advanced im  >   Microsoft 365 Compliance Center überprüfen.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Ausführen automatisierter Aufgaben mit Power Automate-Flüssen für den Fall

Mithilfe empfohlener Power Automate-Flüsse können Risikoermittler und Analysten schnell Maßnahmen ergreifen, um:

- Anfordern von Informationen von Personal oder Unternehmen zu einem Benutzer in einem Insiderrisikofall
- Benachrichtigen des Managers, wenn ein Benutzer über eine Benachrichtigung über Insiderrisiken verfügt
- Hinzufügen einer Kalendererinnerung zum Folgen eines Insiderrisikofalles
- Erstellen eines Datensatzes für einen Insider-Risikomanagementfall in ServiceNow

So führen, verwalten oder erstellen Sie Power Automate-Flüsse für einen Insider-Risikomanagementfall:

1. Wählen **Sie automatisieren** auf der Symbolleiste für Fallaktion aus. 
2. Wählen Sie den zu ausführende Power Automate-Fluss aus, und wählen Sie **dann Flow ausführen aus.** 
3. Nachdem der Fluss abgeschlossen ist, wählen Sie **Fertig aus.**

Weitere Informationen zu Power Automate-Flüssen für insider risk management finden Sie unter [Getting started with insider risk management settings](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Anzeigen oder Erstellen eines Microsoft Teams-Teams für den Fall

Wenn die Microsoft Teams-Integration für insider risk management in den Einstellungen aktiviert ist, wird jedes Mal, wenn eine Warnung bestätigt und ein Fall erstellt wird, automatisch ein Microsoft Teams-Team erstellt. Risikoermittler und Analysten können Microsoft Teams schnell öffnen und direkt zum Team für einen Fall navigieren, indem Sie **Microsoft Teams-Team** anzeigen auf der Symbolleiste für Fallaktion auswählen.

Bei Fällen, die vor der Aktivierung der Microsoft Team-Integration geöffnet wurden, können Risikoermittler und Analysten ein neues Microsoft Teams-Team für einen Fall erstellen, indem Sie **Microsoft Teams-Team** erstellen auf der Symbolleiste für Fallaktion auswählen.

Wenn ein Fall aufgelöst wird, wird das zugeordnete Microsoft Team automatisch archiviert (ausgeblendet und schreibgeschützt).

Weitere Informationen zu Microsoft Teams for Insider Risk Management finden Sie unter [Getting started with insider risk management settings](insider-risk-management-settings.md#microsoft-teams-preview).

### <a name="share-the-case"></a>Freigeben des Falls

Die Freigabe eines Insider-Risikomanagement-Falls ermöglicht Risikoermittlern und Analysten die einfache Zusammenarbeit mit anderen Compliancebeteiligten in Ihrer Organisation. Sie können schnell einen Link zu einem Fall für insider risk management mit externen Beteiligten aus dem Fallmanagementbereich teilen. Um über den Link auf den Fall des Insiderrisikomanagements zu zugreifen, müssen die Beteiligten in eine der Rollengruppen für das Insiderrisikomanagement einbezogen werden.

>[!NOTE]
>Vielen Dank für Ihr Feedback und Ihren Support während der Vorschau des ServiceNow-Connectors. Wir haben beschlossen, die Vorschau des ServiceNow-Connectors zu beenden und den Support im Insider risk management am 30. November 2020 zu beenden. Wir bewerten derzeit aktiv alternative Methoden, um Kunden die ServiceNow-Integration in das Insider-Risikomanagement zu ermöglichen.

Die folgenden Freigabeoptionen sind verfügbar:

- **ServiceNow**: Nach der Konfiguration des Microsoft 365 ServiceNow-Connectors für Ihre Microsoft 365-Organisation können Sie ganz einfach einen Link zu dem Fall freigeben, einen Vorfall öffnen oder eine Änderung mit Ihrer ServiceNow-Organisation anfordern. Wenn Sie den Fall für ServiceNow freigeben möchten, wählen Sie **in** der Fallaktion  >  Fallaktionen **Freigeben**  >  **von ServiceNow** aus. Die ServiceNow-Integration in insider risk management unterstützt umfasst die folgenden Fallinformationen und -aktionen:
    - **Vorgangsname**: Der Name der neuen ServiceNow-Aufgabe.
    - **Aufgabenbeschreibung**: Die Beschreibung für die neue ServiceNow-Aufgabe. Dieses bearbeitbare Beschreibungsfeld enthält automatisch einen Link zum Fall des Insider-Risikomanagements.
    - **Vorgangstyp**: Der Vorgangstyp für die neue ServiceNow-Aufgabe, entweder *Incident* oder *Change Request*.
    - **Priorität**: Die Priorität für die neue ServiceNow-Aufgabe, entweder *Planning*, *Low*, *Moderate*, *High* oder *Critical*.
    - **Fälligkeitsdatum**: Das angeforderte Datum für das Abschließen der ServiceNow-Aufgabe.

![Freigabe von Insider-Risikomanagement mit ServiceNow](../media/insider-risk-share-servicenow.png)

- **E-Mail:** Gibt einen Link zum Fall des Insider-Risikomanagements in einer E-Mail weiter. Sie können einen beliebigen lokal konfigurierten E-Mail-Client mit dieser Freigabeoption auswählen. Wenn Sie den Falllink für E-Mail freigeben möchten, wählen **Sie E-Mail** freigeben  >   in der Symbolleiste der Fallaktion aus.
- **Link kopieren:** Kopiert einen Link zum Fall des Insider-Risikomanagements in die Zwischenablage. Wenn Sie den Falllink in die Zwischenablage kopieren möchten, wählen Sie **in** der Symbolleiste der Fallaktion den Link Kopieren  >   freigeben aus.

### <a name="resolve-the-case"></a>Auflösen des Falls

Nachdem Risikoanalysten und Ermittler ihre Überprüfung und Untersuchung abgeschlossen haben, kann ein Fall aufgelöst werden, um auf alle derzeit in dem Fall enthaltenen Warnungen zu reagieren. Beim Auflösen eines Falls wird eine Lösungsklassifikation hinzugefügt, der Fallstatus wird in *Geschlossen* geändert, und die Gründe für die Lösungsaktion werden automatisch der Fallnotizwarteschlange im Fallnotizdashboard hinzugefügt.  Fälle können auf zwei Arten aufgelöst werden:

- **Benign**: Die Klassifizierung für Fälle, in denen Warnungen zur Übereinstimmung von Richtlinien als niedriges Risiko, nicht schwerwiegend oder falsch positiv ausgewertet werden.
- **Bestätigter Richtlinienverstoß:** Die Klassifizierung für Fälle, in denen Warnungen zur Übereinstimmung von Richtlinien als riskant, schwerwiegend oder das Ergebnis böswilliger Absichten ausgewertet werden.

So lösen Sie einen Fall auf:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Schaltfläche **Fall** auflösen auf der Symbolleiste der Fallaktion aus.
3. Wählen Sie **im Dialogfeld** Fall auflösen das **Dropdownsteuerelement Auflösen als** aus, um die Lösungsklassifikation für den Fall auszuwählen. Die Optionen sind **Benign oder** **Confirmed policy violation**.
4. Geben Sie **im Dialogfeld Fall** auflösen die Gründe für die Lösungsklassifizierung in das Textfeld Aktion **ergriffen** ein.
5. Wählen **Sie Auflösen** aus, um den Fall zu schließen, oder wählen Sie **Abbrechen** schließen, ohne den Fall zu lösen.
