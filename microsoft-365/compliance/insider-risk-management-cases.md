---
title: Insider-Risikomanagement-Fälle
description: Informationen zu Insider-Risikomanagement-Fällen in Microsoft 365
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
ms.openlocfilehash: feabf3083b0ff1d182884c66fc2b2fd890275a0a
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976212"
---
# <a name="insider-risk-management-cases"></a>Insider-Risikomanagement-Fälle

Fälle sind das Herzstück des Insider-Risikomanagements und ermöglichen es Ihnen, Probleme, die durch in Ihren Richtlinien definierte Risikoindikatoren generiert werden, tief zu untersuchen und zu beheben. Fälle werden manuell aus Warnungen in Situationen erstellt, in denen weitere Aktionen erforderlich sind, um ein Complianceproblem für einen Benutzer zu beheben. Jeder Fall ist auf einen einzelnen Benutzer begrenzt, und mehrere Warnungen für den Benutzer können einem vorhandenen Fall oder einem neuen Fall hinzugefügt werden. 

Nachdem Sie die Details eines Falls untersucht haben, können Sie maßnahmen ergreifen, indem Sie:

- Senden einer Benachrichtigung an den Benutzer
- Auflösen des Falls als gutartig
- Freigeben des Falls für Ihre "ServiceNow"-Instanz oder für einen E-Mail-Empfänger
- Eskalieren des Falls für eine Advanced eDiscovery-Untersuchung

## <a name="cases-dashboard"></a>Falldashboard

Mit dem  Dashboard für Insider-Risikomanagementfälle können Sie Fälle anzeigen und bearbeiten. Jedes Berichts-Widget im Dashboard zeigt Informationen für die letzten 30 Tage an.

- **Aktive Fälle:** Die Gesamtzahl der aktiven Fälle, die untersucht werden.
- **Fälle über die letzten 30 Tage:** Die Gesamtzahl der erstellten Fälle, sortiert nach *Dem Status "Aktiv"* und *"Geschlossen".*
- **Statistiken:** Durchschnittliche Zeit aktiver Fälle in Stunden, Tagen oder Monaten.

In der Fallwarteschlange werden alle aktiven und geschlossenen Fälle für Ihre Organisation sowie der aktuelle Status der folgenden Fallattribute aufgeführt:

- **Fallname:** Der Name des Falls, der definiert wird, wenn eine Warnung bestätigt und der Fall erstellt wird.  
- **Status**: Der Status des Falls, entweder *Aktiv* oder *Geschlossen*.
- **Benutzer:** Der Benutzer für den Fall. Wenn die Anonymisierung für Benutzernamen aktiviert ist, werden anonymisierte Informationen angezeigt.
- **Zeitfall geöffnet:** Die Zeit, die seit dem Öffnen des Falls verstrichen ist.
- **Richtlinienwarnungen insgesamt:** Die Anzahl der in dem Fall enthaltenen Richtlinien-Übereinstimmungen. Diese Zahl kann steigen, wenn neue Warnungen zu dem Fall hinzugefügt werden.
- **Last updated:** The time that has passed since there has been an added case note or change in the case state.
- **Last updated by:** The name of the insider risk management analyst or investigator that last updated the case.

![Dashboard für Insider-Risikomanagement-Fälle](../media/insider-risk-cases-dashboard.png)

Verwenden Sie das **Suchsteuerelement,** um Nachfallnamen nach bestimmtem Text zu suchen, und verwenden Sie den Fallfilter, um Fälle nach den folgenden Attributen zu sortieren:

- Status
- Öffnung des Falls, Startdatum und Enddatum
- Letzte Aktualisierung, Startdatum und Enddatum

## <a name="filter-cases"></a>Filterfälle

Je nach Anzahl und Art der aktiven Richtlinien für das Insiderrisikomanagement in Ihrer Organisation kann die Überprüfung einer großen Warteschlange von Fällen eine Herausforderung darstellen. Mithilfe von Fallfiltern können Analysten und Ermittler Fälle nach verschiedenen Attributen sortieren. Um Warnungen im Dashboard **"Fälle" zu filtern,** wählen Sie das **Steuerelement "Filter"** aus. Sie können Fälle nach einem oder mehreren Attributen filtern:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Fallliste zu filtern. Die Optionen sind *"Aktiv"* und *"Geschlossen".*
- **Zeitfall geöffnet:** Wählen Sie das Start- und Enddatum für den Zeitpunkt des Öffnens des Falls aus.
- **Last updated:** Select the start and end dates for when the case was updated.

## <a name="investigate-a-case"></a>Untersuchen eines Falls

Eine tiefere Untersuchung von Warnungen im Risikomanagement von Insidern ist entscheidend, um geeignete Korrekturmaßnahmen zu ergreifen. Fälle des Risikomanagements von Insidern sind das zentrale Verwaltungstool, um sich tiefer in den Verlauf der Benutzerrisikoaktivität und Warnungsdetails zu eintauchen und die Inhalte und Nachrichten zu untersuchen, die Risiken ausgesetzt sind. Risikoanalysten und Ermittler verwenden Fälle auch, um Feedback und Notizen zu rezensionen zentralisieren und die Fallauflösung zu verarbeiten.

Wenn Sie einen Fall auswählen, werden die Fall-Verwaltungstool geöffnet. Diese ermöglichen es Analysten und Ermittlern, sich den Fall bis ins kleinste Detail anzeigen zu lassen.

### <a name="case-overview"></a>Fallübersicht

Die Registerkarte **Fallübersicht** fasst die Warnungsaktivitäten und den Verlauf der Risikostufe für jeden Fall zusammen. 

- Das **Widget "Warnungen"** zeigt die Richtlinien-Übereinstimmungen für den Fall an, einschließlich des Status der Warnung, des Schweregrads des Warnungsrisikos und des Erkannten der Warnung. 
- Das Diagramm **Risikostufenverlauf** zeigt die Risikostufe des entsprechenden Benutzers in den letzten 30 Tagen. Das Liniendiagramm ermöglicht es Analysten und Ermittlern, die Entwicklung des allgemeinen Benutzerrisikos im Laufe der Zeit schnell auf einen Blick zu erfassen. 
- Das Widget **Inhalt der Risikoaktivität** fasst die Daten- und Inhaltstypen zusammen, die in Fall-Warnungen enthalten sind. Dieses Widget bietet einen Gesamtüberblick über alle Daten und Inhalte, die in diesem Fall gefährdet sind.

Der **Detailbereich "Fall"** ist auf allen Registerkarten für die Fallverwaltung verfügbar und fasst die Falldetails für Risikoanalysten und Ermittler zusammen. Sie umfasst die folgenden Bereiche:

- **Fallname:** Der Name des Falls, dem eine automatisch generierte Fallsequenznummer vorangestellt ist, und der Name des Risikos, das der Richtlinienvorlage zugeordnet ist, mit der die erste bestätigte Warnung übereinstimmunget. 
- **Fallstatus:** Der aktuelle Status des Falls, entweder *Aktiv* oder *Geschlossen*.
- **Risikobewertung des Benutzers:** Die aktuell berechnete Risikostufe des Benutzers für den Fall. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein.
- **Warnungen bestätigt:** Liste der Warnungen für den Benutzer, die für den Fall bestätigt wurden.
- **Zugehöriger Inhalt:** Liste der Inhalte, sortiert nach Inhaltsquellen und -typen. Beispielsweise würden Sie für gefährdete Inhalte in SharePoint Online eine Liste mit Ordner- oder Dateinamen sehen, die der Risikoaktivität für Warnungen im entsprechenden Fall zugeordnet sind.

![Details zum Fall des Insider-Risikomanagements](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Warnungen

Auf **der** Registerkarte "Warnungen" werden die aktuellen Warnungen zusammengefasst, die im Fall enthalten sind. Neue Warnungen können einem vorhandenen Fall hinzugefügt  werden, und sie werden der Warnungswarteschlange hinzugefügt, sobald sie zugewiesen sind. Die folgenden Warnungsattribute sind in der Warteschlange aufgeführt:

- Status
- Severity
- Zeit erkannt

Wählen Sie eine Warnung aus der Warteschlange aus, um die Seite **mit den Warnungsdetails** anzeigen zu können.

Verwenden Sie das Suchsteuerelement, um Warnungsnamen nach bestimmtem Text zu durchsuchen, und verwenden Sie den Warnungsfilter, um Fälle nach den folgenden Attributen zu sortieren:

- Status
- Severity
- Zeitpunkt der Erkennung, Startdatum und Enddatum

Verwenden Sie das Filtersteuerelement, um Warnungen nach mehreren Attributen zu filtern, darunter:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen sind *Bestätigt*, *Abgelehnt*, *Überprüfung erforderlich* und *Behoben*.
- **Schweregrad:** Wählen Sie einen oder mehrere Risikoschweregrade für Warnungen aus, um die Warnungsliste zu filtern. Die Optionen sind *Hoch*, *Moderat* und *Niedrig*.
- **Zeit erkannt:** Wählen Sie das Start- und Enddatum aus, ab dem die Warnung erstellt wurde.
- **Richtlinie:** Wählen Sie eine oder mehrere Richtlinien aus, um die von den ausgewählten Richtlinien generierten Warnungen zu filtern.

### <a name="user-activity"></a>Benutzeraktivität

Die Registerkarte **Benutzeraktivität** ist eines der leistungsstärksten Werkzeuge für die Analyse und Untersuchung interner Risiken bei Föllen in der Insider-Risikomanagement-Lösung. Diese Registerkarte ist so strukturiert, dass sie eine schnelle Überprüfung eines Falls ermöglicht, einschließlich einer historischen Zeitachse aller Warnungen, aller Benachrichtigungsdetails, der aktuellen Risikobewertung für den Benutzer in dem Fall und Kontrollen, um effektive Maßnahmen zur Eindämmung der Risiken in dem Fall zu ergreifen.

![Benutzeraktivität des Insider-Risikomanagements](../media/insider-risk-user-activities.png)

1. **Datums- und Fensterzeitfilter:** Standardmäßig werden die letzten sechs Monate der im Fall bestätigten Warnungen im Benutzeraktivitätsdiagramm angezeigt. Sie können die Diagrammansicht ganz einfach mit den Schiebereglersteuerelementen an beiden Enden des Diagrammfensters filtern oder indem Sie bestimmte Start- und Enddaten im Diagrammfiltersteuerelement definieren.
2. **Aktivität und Details von Risikowarnungen:** Risikoaktivitäten werden visuell als farbige Blasen im Benutzeraktivitätsdiagramm angezeigt. Blasen werden für verschiedene Risikokategorien erstellt, und die Blasengröße ist proportional zur Anzahl der Risikoaktivitäten für die Kategorie. Wählen Sie eine Blase aus, um die Details für jede Risikoaktivität anzuzeigen. Zu den Details gehören:
    - **Datum** der Risikoaktivität.
    - Die **Risikoaktivitätskategorie**. Beispielsweise *E-Mails* mit Anlagen, die außerhalb der Organisation gesendet werden, oder Dateien, die *von SharePoint Online heruntergeladen wurden.*
    - **Risikobewertung** für die Warnung. Diese Bewertung ist der numerische Wert für den Schweregrad des Risikos.
    - Anzahl der Ereignisse, die mit der Warnung verknüpft sind. Links zu jeder Datei oder E-Mail, die mit der Risikoaktivität verknüpft sind, können ebenfalls abgerufen werden.
3. **Legende der Risikoaktivität:** Am unteren Rand des Benutzeraktivitätsdiagramms hilft Ihnen eine farblich codierte Legende, die Ihnen dabei hilft, die Risikokategorie für jede Warnung schnell zu bestimmen.
4. **Risikoaktivitätschronologie:** Die vollständige Chronologie aller mit dem Fall verbundenen Risikowarnungen wird aufgeführt, einschließlich aller Details, die in der entsprechenden Warnungsblase verfügbar sind.
5. **Fallaktionen:** Optionen zum Auflösen des Falls befinden sich auf der Symbolleiste für Fallaktionen. Sie können einen Fall auflösen, eine E-Mail-Benachrichtigung an den Benutzer senden oder den Fall für eine Daten- oder Benutzeruntersuchung eskalieren.

### <a name="activity-explorer-preview"></a>Aktivitäten-Explorer (Vorschau)

>[!IMPORTANT]
>Die Registerkarte "Aktivitäts-Explorer" ist im Bereich "Fallverwaltung" für Benutzer mit auslösenden Ereignissen verfügbar, nachdem dieses Feature in Ihrer Organisation verfügbar ist.

Auf **der Registerkarte "Aktivitäts-Explorer"** können Risikoanalysten und Ermittler Aktivitätsdetails im Zusammenhang mit Risikowarnungen überprüfen. Beispielsweise müssen Ermittler und Analysten im Rahmen der Fallverwaltungsaktionen möglicherweise alle Risikoaktivitäten im Zusammenhang mit dem Fall überprüfen, um weitere Details zu erhalten. Mit dem **Aktivitäts-Explorer** können Prüfer schnell eine Zeitachse erkannter riskanter Aktivitäten überprüfen und alle Risikoaktivitäten im Zusammenhang mit Warnungen identifizieren und filtern.

Weitere Informationen zum Aktivitäten-Explorer finden Sie im Artikel zu Warnungen zum [Insider-Risikomanagement.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Inhalts-Explorer

Auf **der Registerkarte "Inhalts-Explorer"** können Risikoanalysten und Ermittler Kopien aller einzelnen Dateien und E-Mail-Nachrichten überprüfen, die risikowarnungen zugeordnet sind. Wenn beispielsweise eine Warnung erstellt wird, wenn ein Benutzer Hunderte von Dateien aus SharePoint Online herunterläutet und die Aktivität eine Richtlinienwarnung auslöst, werden alle heruntergeladenen Dateien für die Warnung erfasst und aus ursprünglichen Speicherquellen in den Fall des Insiderrisikomanagements kopiert.

Der Inhalts-Explorer ist ein leistungsstarkes Tool mit grundlegenden und erweiterten Such- und Filterfeatures. Weitere Informationen zur Verwendung des Inhalts-Explorers finden Sie im [Inhalts-Explorer für Insider-Risikomanagement.](insider-risk-management-content-explorer.md)

![Insider-Risikomanagement- Fall Inhalts-Explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Fallnotizen

Auf **der Registerkarte** "Fallnotizen" geben Risikoanalysten und Ermittler Kommentare, Feedback und Einblicke zu ihrer Arbeit für den Fall weiter. Notizen sind dauerhafte Ergänzungen zu einem Fall und können nicht mehr bearbeitet oder gelöscht werden, sobald sie gespeichert wurden. Wenn ein Fall aus einer Warnung erstellt wird, werden die im Dialogfeld **Benachrichtigung bestätigen und Insider-Risikofall erstellen** eingegebenen Kommentare automatisch als Fallnotiz hinzugefügt.

Im Dashboard für Fallnotizen werden die Notizen des Benutzers angezeigt, der die Notiz erstellt hat, sowie die Zeit, die seit dem Speichern der Notiz verstrichen ist. Verwenden Sie die Schaltfläche "Suchen" im  Falldashboard, und geben Sie ein bestimmtes Schlüsselwort ein, um das Textfeld mit der Fallnotiz nach einem bestimmten Schlüsselwort zu durchsuchen.

So fügen Sie einem Fall eine Notiz hinzu

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Fälle"** aus. 
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **"Fallnotizen"** aus.
3. Select **Add case note**.
4. Geben Sie **im Dialogfeld "Fallnotiz** hinzufügen" Ihre Notiz für den Fall ein. Wählen **Sie "Speichern"** aus, um die Notiz zu dem Fall hinzuzufügen, oder wählen Sie **"Schließen** abbrechen" aus, ohne die Notiz im Fall zu speichern.

### <a name="contributors"></a>Mitwirkende

Auf der Registerkarte **Mitwirkende** können Risikoanalysten und Ermittler weitere Mitwirkende zu dem Fall hinzufügen. Standardmäßig werden alle Benutzer, denen die Rollen **"Insider Risk Management Analysts"** und **"Insider Risk Management Investigators"** zugewiesen sind, als Mitwirkende für jeden aktiven und geschlossenen Fall aufgeführt.

Alle Fälle des Insider-Risikomanagements müssen mit angemessenen Zugriffssteuerungen verwaltet werden, damit die Vertraulichkeit und Integrität der Untersuchung aufrechterhalten wird. Um die Zugriffssteuerung für Fälle aufrechtzuerhalten, werden Benutzern ein oder zwei Arten von Zugriff auf Fälle zugewiesen:

- **Dauerhafter** Zugriff: Benutzern mit den Rollen **"Insider Risk Management Analysts"** und **"Insider Risk Management Investigators"** wird automatisch dauerhafter Zugriff gewährt, wenn der Fall aus einer Warnung erstellt wird. Dauerhafter Zugriff gewährt den vollständigen Zugriff auf den Fall während der Lebensdauer des Falls, und ermöglicht es der Person, weitere Mitwirkende zu dem Fall hinzuzufügen.
- **Temporärer** Zugriff: Der temporäre Zugriff wird Benutzern nur von Mitwirkenden gewährt, die dauerhaften Zugriff auf den Fall haben. In der Regel wird diese Zugriffsebene Benutzern gewährt, die einem Fall Notizen hinzufügen müssen. Mitwirkende mit temporärem Zugriff können auf alle Steuerelemente für das Fallmanagement zugreifen, ausgenommen:
    - Die Berechtigung, Warnungen zu bestätigen oder zu verwerfen
    - Die Berechtigung, die Mitwirkenden eines Falles zu bearbeiten
    - Die Berechtigung, Dateien und Nachrichten im Inhaltsexplorer anzuzeigen

So fügen Sie einen Mitwirkenden zu einem Fall hinzu:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Fälle"** aus. 
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **"Mitwirkende"** aus.
3. Wählen Sie **"Mitwirkender hinzufügen" aus.**
4. Beginnen Sie **im** Dialogfeld "Mitwirkender hinzufügen" mit der Eingabe des Namens des Benutzers, den Sie hinzufügen möchten, und wählen Sie dann den Benutzer aus der Liste der vorgeschlagenen Benutzer aus. Diese Liste wird aus dem Azure Active Directory Ihres Mandantenabonnements generiert.
5. Wählen **Sie "Hinzufügen"** aus, um den Benutzer als Mitwirkender hinzuzufügen, oder wählen Sie **"Abbrechen"** aus, um das Dialogfeld zu schließen, ohne den Benutzer als Mitwirkenden hinzuzufügen.

## <a name="case-actions"></a>Fallmaßnahmen

Risikoanalysten und Ermittler können in abhängigkeit vom Schweregrad des Falls, dem Risikoverlauf des Benutzers und den Risikorichtlinien Ihrer Organisation Maßnahmen für einen Fall in einer von mehreren Methoden ergreifen. In einigen Situationen müssen Sie einen Fall möglicherweise an einen Benutzer oder eine Datenuntersuchung eskalieren, um mit anderen Bereichen Ihrer Organisation zusammenzuarbeiten und sich tiefer in die Risikoaktivitäten eintauchen zu lassen. Das Risikomanagement für Insider ist eng in andere Microsoft 365-Compliancelösungen integriert, um Ihnen bei der End-to-End-Lösungsverwaltung zu helfen.

### <a name="send-email-notice"></a>E-Mail-Benachrichtigung senden

In den meisten Fällen sind Benutzeraktionen, die Warnungen zu Insiderrisiken auslösen, unbeabsichtigt oder unbeabsichtigt. Das Senden einer Erinnerung per E-Mail an den Benutzer ist eine effektive Methode zum Dokumentieren der Fallüberprüfung und -aktion und eine Methode, um Benutzer an Unternehmensrichtlinien zu erinnern oder sie auf aktualisierungsschulungen zu verweisen. Benachrichtigungen werden aus [Benachrichtigungsvorlagen generiert, die Sie für](insider-risk-management-notices.md) Ihre Infrastruktur für das Insider-Risikomanagement erstellen.

Es ist wichtig zu beachten, dass das Senden einer E-Mail-Benachrichtigung an einen Benutzer *_*_* den Fall nicht als _Closed* löst. In einigen Fällen möchten Sie möglicherweise einen Fall offen lassen, nachdem Sie einen Hinweis an einen Benutzer senden, um nach weiteren Risikoaktivitäten zu suchen, ohne einen neuen Fall zu öffnen. Wenn Sie einen Fall nach dem Senden einer Benachrichtigung auflösen möchten, müssen Sie **Fall lösen** als Folgeschritt nach dem Senden einer Benachrichtigung auswählen.

So senden Sie eine Benachrichtigung an den Benutzer, der einem Fall zugewiesen ist:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Fälle"** aus. 
2. Wählen Sie einen Fall aus, und wählen Sie dann **auf** der Symbolleiste für Fallaktion die Schaltfläche "E-Mail senden" aus.
3. Wählen Sie **im Dialogfeld "E-Mail-Benachrichtigung** senden" das Dropdownsteuerelement "Benachrichtigungsvorlage auswählen" aus, um die Benachrichtigungsvorlage für den Hinweis auszuwählen.  Diese Auswahl füllt die anderen Felder auf dem Hinweis vorab aus.
4. Überprüfen Sie die Benachrichtigungsfelder, und aktualisieren Sie sie entsprechend. Die hier eingegebenen Werte überschreiben die Werte in der Vorlage.
5. Wählen **Sie "Senden"** aus, um den Hinweis an den Benutzer zu senden, oder wählen Sie **"Abbrechen"** aus, um das Dialogfeld zu schließen, ohne den Hinweis an den Benutzer zu senden. Alle gesendeten Benachrichtigungen werden der Fallnotizwarteschlange im Dashboard für **Fallnotizen** hinzugefügt.

### <a name="escalate-for-investigation"></a>Eskalieren zur Überprüfung

Eskalieren Sie den Fall für die Benutzeruntersuchung in Situationen, in denen eine zusätzliche rechtliche Überprüfung für die Risikoaktivität des Benutzers erforderlich ist. Diese Eskalation öffnet einen neuen Advanced eDiscovery-Fall in Ihrer Microsoft 365-Organisation. Advanced eDiscovery bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen rechtlichen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem kann Ihr Rechtsteam den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren. Das Zuweisen eines Überprüfers als Verwahrer in einem Advanced eDiscovery-Fall, der aus einem Fall im Insider-Risikomanagement erstellt wurde, hilft Ihrem Rechtsteam dabei, angemessene Maßnahmen zu ergreifen, und die Erhaltung von Inhalten zu verwalten. Weitere Informationen zu den Advanced eDiscovery-Fällen finden Sie unter [Übersicht über Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).

So eskalieren Sie einen Fall an eine Benutzeruntersuchung

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Fälle"** aus. 
2. Wählen Sie einen Fall  aus, und wählen Sie dann auf der Symbolleiste für Fallaktion die Schaltfläche "Eskalieren für Untersuchung" aus.
3. Geben Sie **im Dialogfeld "Eskalieren für Untersuchung"** einen Namen für die neue Benutzeruntersuchung ein. Geben Sie bei Bedarf Notizen zu dem Fall ein, und wählen Sie **Eskalieren aus.**
4. Überprüfen Sie die Benachrichtigungsfelder, und aktualisieren Sie sie entsprechend. Die hier eingegebenen Werte überschreiben die Werte in der Vorlage.
5. Wählen **Sie "Bestätigen"** aus, um den Benutzeruntersuchungsfall zu erstellen, oder wählen Sie **"Abbrechen"** aus, um das Dialogfeld zu schließen, ohne einen neuen Benutzeruntersuchungsfall zu erstellen.

Nachdem der Fall des Insider-Risikomanagements zu einem neuen Untersuchungsfall für Benutzer eskaliert wurde, können Sie den neuen Fall im **Bereich eDiscovery** Advanced im  >   Microsoft 365 Compliance Center überprüfen.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Ausführen automatisierter Aufgaben mit Power Automate-Flüssen für den Fall

Mithilfe empfohlener Power Automate-Flüsse können Risikoermittler und Analysten schnell Maßnahmen ergreifen für:

- Anfordern von Informationen von der Personalabteilung oder dem Unternehmen zu einem Benutzer in einem Insiderrisikofall
- Vorgesetzter benachrichtigen, wenn ein Benutzer über eine Warnung zu Insiderrisiken verfügt
- Kalendererinnerung hinzufügen, um einen Insider-Risikofall zu verfolgen
- Erstellen eines Datensatzes für einen Fall eines Insider-Risikomanagements in ServiceNow

Zum Ausführen, Verwalten oder Erstellen von Power Automate-Flüssen für einen Fall eines Insider-Risikomanagements:

1. Wählen Sie **auf der Symbolleiste** für Fallaktion "Automatisieren" aus. 
2. Wählen Sie den power Automate-Fluss aus, der ausgeführt werden soll, und wählen Sie dann **"Flow ausführen" aus.** 
3. Nachdem der Fluss abgeschlossen ist, wählen Sie **"Fertig" aus.**

Weitere Informationen zu Power Automate-Flüssen für das Insider-Risikomanagement finden Sie unter ["Erste Schritte mit Den Einstellungen für das Insider-Risikomanagement".](insider-risk-management-settings.md#power-automate-flows-preview)

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Anzeigen oder Erstellen eines Microsoft Teams-Teams für den Fall

Wenn die Integration von Microsoft Teams für das Insiderrisikomanagement in den Einstellungen aktiviert ist, wird jedes Mal automatisch ein Microsoft Teams-Team erstellt, wenn eine Warnung bestätigt und ein Fall erstellt wird. Risikoermittler und Analysten können Microsoft Teams schnell öffnen und direkt zum Team für einen Fall navigieren, indem sie auf der Symbolleiste für Fallaktion **das Microsoft** Teams-Team anzeigen auswählen.

Bei Fällen, die vor der Aktivierung der Integration von Microsoft Teams geöffnet wurden, können Risikoermittler und Analysten ein neues Microsoft Teams-Team für einen Fall erstellen, indem sie auf der Symbolleiste für Fallaktion das Team **"Microsoft Teams** erstellen" auswählen.

Wenn ein Fall aufgelöst wird, wird das zugeordnete Microsoft Team automatisch archiviert (ausgeblendet und schreibgeschützt).

Weitere Informationen zu Microsoft Teams für das Insider-Risikomanagement finden Sie unter ["Erste Schritte mit Den Einstellungen für das Insider-Risikomanagement".](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="share-the-case"></a>Freigeben des Falls

Durch die Freigabe eines Insider-Risikomanagement-Falls können Risikoermittler und Analysten problemlos mit anderen Compliancebeteiligten in Ihrer Organisation zusammenarbeiten. Sie können schnell einen Link zu einem Insider-Risikomanagement-Fall für externe Beteiligte aus dem Bereich "Fallmanagement" freigeben. Um über den Link auf den Fall des Insiderrisikomanagements zugreifen zu können, müssen die Beteiligten in eine der Rollengruppen des Insider-Risikomanagements einbezogen werden.

>[!NOTE]
>Vielen Dank für Ihr Feedback und Ihren Support während der Vorschau des ServiceNow-Connectors. Wir haben beschlossen, die Vorschau des ServiceNow-Connectors zu beenden und den Support im Insider-Risikomanagement am 30. November 2020 zu beenden. Wir bewerten aktiv alternative Methoden, um Kunden die Integration von ServiceNow in das Insider-Risikomanagement zu ermöglichen.

Die folgenden Freigabeoptionen sind verfügbar:

- **ServiceNow:** Nach dem Konfigurieren des Microsoft 365 -ServiceNow-Connectors für Ihre Microsoft 365-Organisation können Sie einfach einen Link zu dem Fall freigeben, einen Vorfall öffnen oder eine Änderung mit Ihrer ServiceNow-Organisation anfordern. Um den Fall mit ServiceNow zu teilen, wählen Sie in der Fallaktion **"Share**  >  **ServiceNow"** aus. Die ServiceNow-Integration in das Insider-Risikomanagement unterstützt die folgenden Fallinformationen und -aktionen:
    - **Vorgangsname:** Der Name für die neue ServiceNow-Aufgabe.
    - **Vorgangsbeschreibung:** Die Beschreibung für die neue ServiceNow-Aufgabe. Dieses bearbeitbare Beschreibungsfeld enthält automatisch einen Link zum Fall des Insider-Risikomanagements.
    - **Vorgangstyp:** Der Vorgangstyp für den neuen ServiceNow-Vorgang, entweder *Vorfall-* oder *Änderungsanforderung.*
    - **Priorität:** Die Priorität für den neuen ServiceNow-Vorgang, entweder *Planning*, *Low*, *Moderate*, *High* oder *Critical*.
    - **Fälligkeitsdatum:** Das angeforderte Datum für den Abschluss der ServiceNow-Aufgabe.

![Freigabe von Insider-Risikomanagement mit ServiceNow](../media/insider-risk-share-servicenow.png)

- **E-Mail:** Gibt einen Link zum Fall des Insider-Risikomanagements in einer E-Mail weiter. Mit dieser Freigabeoption können Sie einen beliebigen lokal konfigurierten E-Mail-Client auswählen. Um den Falllink mit E-Mail zu teilen, wählen **Sie auf** der Symbolleiste für  >   Fallaktion "E-Mail freigeben" aus.
- **Link "Kopieren":** Kopiert einen Link zum Fall "Insider-Risikomanagement" in die Zwischenablage. Um den Falllink in die Zwischenablage zu kopieren, **wählen** Sie auf der Symbolleiste für Fallaktion den Link "Kopie  >   freigeben" aus.

### <a name="resolve-the-case"></a>Auflösen des Falls

Nachdem Risikoanalysten und Ermittler ihre Überprüfung und Untersuchung abgeschlossen haben, kann ein Fall aufgelöst werden, um auf alle Warnungen zu reagieren, die derzeit in dem Fall enthalten sind. Beim Auflösen eines Falls wird eine Auflösungsklassifikation hinzugefügt, der Fallstatus wird in *"Geschlossen"* geändert, und die Gründe für die Lösungsaktion werden automatisch der Fallnotizwarteschlange im Dashboard mit **Fallnotizen** hinzugefügt. Fälle können auf zwei Arten aufgelöst werden:

- **Gutartig:** Die Klassifizierung für Fälle, in denen Warnungen zur Übereinstimmung mit Richtlinien als niedriges Risiko, als nicht schwerwiegend oder als falsch positiv bewertet werden.
- **Bestätigte Richtlinienverletzung:** Die Klassifizierung für Fälle, in denen Warnungen zu Richtlinienab übereinstimmungen als riskant, schwerwiegend oder als Ergebnis von böswilliger Absicht ausgewertet werden.

So lösen Sie einen Fall auf:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Fälle"** aus. 
2. Wählen Sie einen Fall aus, und wählen Sie dann **auf** der Symbolleiste für Fallaktion die Schaltfläche "Fall auflösen" aus.
3. Wählen Sie **im Dialogfeld "Fall auflösen"** das Steuerelement "Als **Dropdown** auflösen" aus, um die Auflösungsklassifikation für den Fall auszuwählen. Die Optionen sind **"Benign" oder** **"Confirmed policy violation".**
4. Geben Sie **im Dialogfeld "Fall** auflösen" die Gründe für die Auflösungsklassifikation in das Textfeld **"Aktion ergriffen"** ein.
5. Wählen **Sie "Auflösen"** aus, um den Fall zu schließen, oder wählen Sie **"Abbrechen"** aus, um das Dialogfeld zu schließen, ohne den Fall zu lösen.
