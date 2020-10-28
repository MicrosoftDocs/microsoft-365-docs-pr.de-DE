---
title: Insider Risikomanagement-Fälle
description: Informationen zu Insider Risikomanagement-Fällen in Microsoft 365
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
ms.openlocfilehash: f0251f783aebd1264facfcbaa23a9b7afa286833
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774018"
---
# <a name="insider-risk-management-cases"></a>Insider Risikomanagement-Fälle

Fälle sind das Herzstück des Insider Risikomanagements und ermöglichen es Ihnen, Probleme, die durch in ihren Richtlinien definierte Risikoindikatoren generiert werden, eingehend zu untersuchen und zu bearbeiten. Fälle werden manuell aus Warnungen in Situationen erstellt, in denen weitere Aktionen erforderlich sind, um einen Compliance-bezogenen Fehler für einen Benutzer zu beheben. Bei jedem Fall handelt es sich um einen einzelnen Benutzer, und mehrere Benachrichtigungen für den Benutzer können einem vorhandenen Fall oder einem neuen Fall hinzugefügt werden. 

Nachdem Sie die Details eines Falles untersucht haben, können Sie folgende Aktionen durchführen:

- Senden des Benutzers eine Benachrichtigung
- Auflösen des Falls als gutartig
- Freigeben des Falls für Ihre ServiceNow-Instanz oder mit einem e-Mail-Empfänger
- eskalieren der Argumente für eine erweiterte eDiscovery-Untersuchung

## <a name="cases-dashboard"></a>Cases-Dashboard

Im Dashboard für Insider Risikomanagement- **Fälle** können Sie Fälle anzeigen und bearbeiten. Jedes Berichts-Widget auf dem Dashboard zeigt Informationen für die letzten 30 Tage an.

- **Aktive Fälle** : die Gesamtzahl der untersuchten aktiven Fälle.
- **Fälle in den letzten 30 Tagen** : die Gesamtzahl der erstellten Fälle, sortiert nach *aktivem* und *geschlossenem* Status.
- **Statistik** : durchschnittliche Zeit der aktiven Fälle, aufgeführt in Stunden, Tagen oder Monaten.

In der Fall Warteschlange werden alle aktiven und geschlossenen Fälle für Ihre Organisation neben dem aktuellen Status der folgenden Fall Attribute aufgeführt:

- **Case Name** : der Name des Falls, der definiert wird, wenn eine Warnung bestätigt wird und der Fall erstellt wird.  
- **Status** : der Status des Falls, entweder *aktiv* oder *geschlossen* .
- **User** : der Benutzer für den Fall. Wenn die Anonymisierung für Benutzernamen aktiviert ist, werden anonymisierte Informationen angezeigt.
- **Geöffneter Zeitfall** : die Zeit, die seit dem Öffnen des Groß-/Kleinschreibung-Verfahrens vergangen ist.
- **Total Policy Alerts** : die Anzahl der Richtlinien Übereinstimmungen, die in der Anfrage enthalten sind. Diese Zahl kann steigen, wenn neue Warnungen zu dem Fall hinzugefügt werden.
- **Last updated** : die Zeit, die vergangen ist, seit es eine zusätzliche Groß-/Kleinschreibung oder Änderung im Fall Status gegeben hat.
- **Zuletzt aktualisiert von** : der Name des Insider Risk Management Analysts oder Investigators, der den Fall zuletzt aktualisiert hat.

![Insider Risk Management Cases-Dashboard](../media/insider-risk-cases-dashboard.png)

Verwenden Sie das **Search** -Steuerelement, um nach bestimmten Text zu suchen, und verwenden Sie den Fallfilter, um Fälle anhand der folgenden Attribute zu sortieren:

- Status
- Öffnung des Falls, Startdatum und Enddatum
- Letzte Aktualisierung, Startdatum und Enddatum

## <a name="filter-cases"></a>Filter Fälle

Je nach Anzahl und Typ der aktiven Insider Risiko-Verwaltungsrichtlinien in Ihrer Organisation kann die Überprüfung einer großen Warteschlange eine Herausforderung darstellen. Die Verwendung von Case-filtern kann Analysten und Ermittlern beim Sortieren von Fällen mit verschiedenen Attributen helfen. Um Warnungen im **Cases-Dashboard** zu filtern, wählen Sie das **Filter** -Steuerelement aus. Sie können Fälle nach einem oder mehreren Attributen filtern:

- **Status** : Wählen Sie einen oder mehrere Statuswerte aus, um die Anfrageliste zu filtern. Die Optionen sind *aktiv* und *geschlossen* .
- **Geöffneter Zeitfall** : Wählen Sie das Start-und Enddatum für den Zeitpunkt, an dem der Fall geöffnet wurde.
- **Zuletzt aktualisiert** : Wählen Sie das Start-und Enddatum für den Zeitpunkt, an dem der Fall aktualisiert wurde.

## <a name="investigate-a-case"></a>Untersuchen eines Falls

Eine eingehendere Untersuchung der Warnungen beim Insider Risikomanagement ist für die richtigen Korrekturmaßnahmen wichtig. Bei Insider Risk Management-Fällen handelt es sich um das zentrale Verwaltungstool, mit dem Sie tiefer in den Verlauf von Benutzer Risiko Aktivitäten und Warnungsdetails eintauchen und die Inhalte und Nachrichten untersuchen können, die Risiken ausgesetzt sind. Risikoanalysten und Ermittler verwenden auch Fälle, um Überprüfung Feedback und Notizen zu zentralisieren und die Fall Behebung zu verarbeiten.

Wenn Sie einen Fall auswählen, werden die Fall-Verwaltungstool geöffnet. Diese ermöglichen es Analysten und Ermittlern, sich den Fall bis ins kleinste Detail anzeigen zu lassen.

### <a name="case-overview"></a>Fallübersicht

Die Registerkarte **Fallübersicht** fasst die Warnungsaktivitäten und den Verlauf der Risikostufe für jeden Fall zusammen. 

- Das Widget **Warnungen** zeigt die Richtlinien Übereinstimmungen für den Fall an, einschließlich des Status der Warnung, des Schweregrads des Warnungs Risikos und der Feststellung der Warnung. 
- Das Diagramm **Risikostufenverlauf** zeigt die Risikostufe des entsprechenden Benutzers in den letzten 30 Tagen. Das Liniendiagramm ermöglicht es Analysten und Ermittlern, die Entwicklung des allgemeinen Benutzerrisikos im Laufe der Zeit schnell auf einen Blick zu erfassen. 
- Das Widget **Inhalt der Risikoaktivität** fasst die Daten- und Inhaltstypen zusammen, die in Fall-Warnungen enthalten sind. Dieses Widget bietet einen Gesamtüberblick über alle Daten und Inhalte, die in diesem Fall gefährdet sind.

Der Bereich **Fall Details** ist auf allen Registerkarten für die Fallverwaltung verfügbar und fasst die Fall Details für Risikoanalysten und Ermittler zusammen. Sie umfasst die folgenden Bereiche:

- **Case Name** : der Name der Groß-/Kleinschreibung mit einer automatisch generierten fallsequenz Nummer und dem Namen des Risikos, das der Richtlinienvorlage zugeordnet ist, die von der ersten bestätigten Warnung gefunden wurde. 
- **Case Status** : der aktuelle Status des Falls, entweder *aktiv* oder *geschlossen* .
- **Risikobewertung des Benutzers** : das aktuelle berechnete Risikoniveau des Benutzers für den Fall. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein.
- **Benachrichtigungen bestätigt** : Liste der Benachrichtigungen für den Benutzer, die für den Fall bestätigt wurden.
- **Zugehöriger Inhalt** : Liste der Inhalte, sortiert nach Inhaltsquellen und Typen. Beispielsweise würden Sie für gefährdete Inhalte in SharePoint Online eine Liste mit Ordner- oder Dateinamen sehen, die der Risikoaktivität für Warnungen im entsprechenden Fall zugeordnet sind.

![Insider Risk Management-Fall Details](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Warnungen

Auf der Registerkarte **Benachrichtigungen** werden die aktuellen Warnungen zusammengefasst, die in der Anfrage enthalten sind. Neue Warnungen werden möglicherweise zu einem vorhandenen Fall hinzugefügt, und Sie werden der **Benachrichtigungs** Warteschlange hinzugefügt, sobald Sie zugewiesen sind. Die folgenden Warnungs Attribute werden in der Warteschlange aufgeführt:

- Status
- Severity
- Erkannte Zeit

Wählen Sie in der Warteschlange eine Warnung aus, um die **Warnungs Detail** Seite anzuzeigen.

Verwenden Sie das Search-Steuerelement, um Warnungsnamen nach bestimmten Text zu durchsuchen, und verwenden Sie den Warnungsfilter, um Fälle anhand der folgenden Attribute zu sortieren:

- Status
- Severity
- Zeitpunkt der Erkennung, Startdatum und Enddatum

Verwenden Sie das Filter-Steuerelement, um Warnungen nach verschiedenen Attributen zu filtern, einschließlich:

- **Status** : Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen sind *Bestätigt* , *Abgelehnt* , *Überprüfung erforderlich* und *Behoben* .
- **Schweregrad** : Wählen Sie einen oder mehrere Warnungs Risikoschwere Grade aus, um die Warnungsliste zu filtern. Die Optionen sind *Hoch* , *Moderat* und *Niedrig* .
- **Erkannte Zeit** : Wählen Sie das Start-und Enddatum für die Erstellung der Warnung aus.
- **Richtlinie** : Wählen Sie eine oder mehrere Richtlinien aus, um die Warnungen zu filtern, die von den ausgewählten Richtlinien generiert wurden.

### <a name="user-activity"></a>Benutzeraktivität

Die Registerkarte **Benutzeraktivität** ist eines der leistungsstärksten Werkzeuge für die Analyse und Untersuchung interner Risiken bei Föllen in der Insider-Risikomanagement-Lösung. Diese Registerkarte ist so strukturiert, dass eine schnelle Überprüfung eines Falls möglich ist, einschließlich einer Verlaufs Zeitachse aller Warnungen, aller Warnungsdetails, des aktuellen Risiko Werts für den Benutzer in dem Fall und der Steuerelemente, mit denen wirksame Maßnahmen zur Eindämmung der Risiken in dem Fall ergriffen werden.

![Insider Risk Management-Benutzeraktivität](../media/insider-risk-user-activities.png)

1. **Datums-und Fenster Zeitfilter** : Standardmäßig werden die letzten sechs Monate der im Fall bestätigten Benachrichtigungen im Diagramm Benutzeraktivität angezeigt. Sie können die Diagrammansicht ganz einfach mit dem Schieberegler an beiden Enden des Diagrammfensters filtern oder indem Sie ein bestimmtes Start-und Enddatum im Diagramm Filter-Steuerelement definieren.
2. **Risiko Warnungs Aktivität und Details** : Risiko Aktivitäten werden visuell als farbige Blasen im Diagramm Benutzeraktivität angezeigt. Blasen werden für verschiedene Risikokategorien erstellt, und die Blasengröße ist proportional zur Anzahl der Risiko Aktivitäten für die Kategorie. Wählen Sie eine Blase aus, um die Details für jede Risiko Aktivität anzuzeigen. Details umfassen:
    - **Datum** der Risikoaktivität.
    - Die **Risiko Aktivitätskategorie** . *E-Mail-Nachrichten beispielsweise mit Anlagen, die außerhalb der Organisation* oder *von SharePoint Online heruntergeladen* wurden.
    - **Risikobewertung** für die Warnung. Diese Bewertung ist der numerische Wert für den Schweregrad des Risikos.
    - Anzahl der Ereignisse, die mit der Warnung verknüpft sind. Links zu jeder Datei oder E-Mail, die mit der Risikoaktivität verknüpft sind, können ebenfalls abgerufen werden.
3. **Legende zur Risiko Aktivität** : am unteren Rand des Benutzer Aktivitätsdiagramms können Sie mit einer farbcodierten Legende schnell die Risikokategorie für jede Warnung bestimmen.
4. **Chronologie der Risiko Aktivität** : die vollständige Chronologie aller mit dem Fall verbundenen Risikowarnungen wird aufgeführt, einschließlich aller Details, die in der entsprechenden Warnungs Blase verfügbar sind.
5. **Case-Aktionen** : Optionen zum Auflösen der Groß-/Kleinschreibung befinden sich auf der Symbolleiste für den Fall Vorgang. Sie können einen Fall lösen, eine e-Mail-Benachrichtigung an den Benutzer senden oder den Fall für eine Daten-oder Benutzer Ermittlung eskalieren.

### <a name="activity-explorer-preview"></a>Aktivitäts-Explorer (Vorschau)

>[!IMPORTANT]
>Die Registerkarte Aktivitäts-Explorer steht im Bereich Fallverwaltung für Benutzer mit auslösenden Ereignissen zur Verfügung, nachdem dieses Feature in Ihrer Organisation verfügbar ist.

Auf der Registerkarte **Aktivitäts-Explorer** können Risikoanalysten und Ermittler Aktivitätsdetails im Zusammenhang mit Risikowarnungen überprüfen. Im Rahmen der Fall Verwaltungsaktionen müssen beispielsweise Ermittler und Analysten möglicherweise alle mit dem Fall verbundenen Risiko Aktivitäten für weitere Details überprüfen. Mit dem **Aktivitäts-Explorer** können Bearbeiter schnell eine Zeitachse der erkannten riskanten Aktivität überprüfen und alle Risiko Aktivitäten identifizieren und Filtern, die mit Warnungen verbunden sind.

Weitere Informationen zum Aktivitäts-Explorer finden Sie im Artikel zum Thema [Insider Risk Management Alerts](insider-risk-management-alerts.md#activity-explorer-preview) .

### <a name="content-explorer"></a>Inhalts-Explorer

Auf der Registerkarte **Inhalts-Explorer** können Risikoanalysten und Ermittler Kopien aller einzelnen Dateien und e-Mail-Nachrichten überprüfen, die mit Risikowarnungen verbunden sind. Wenn beispielsweise eine Warnung erstellt wird, wenn ein Benutzer Hunderte von Dateien aus SharePoint Online herunterlädt und die Aktivität eine Richtlinien Warnung auslöst, werden alle heruntergeladenen Dateien für die Warnung erfasst und aus den ursprünglichen Speicherquellen in den Fall Insider Risk Management kopiert.

Der Inhalts-Explorer ist ein leistungsfähiges Tool mit einfachen und erweiterten Such-und Filterfunktionen. Weitere Informationen zur Verwendung des Inhalts-Explorers finden Sie unter [Insider Risk Management Content Explorer](insider-risk-management-content-explorer.md).

![Risikomanagement für Insider Fälle Inhalts-Explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Fallnotizen

Die Registerkarte **fallnotizen** in dem Fall besteht darin, dass Risikoanalysten und Ermittler Kommentare, Feedback und Einblicke in Ihre Arbeit für den Fall freigeben. Notizen sind dauerhafte Ergänzungen zu einem Fall und können nicht mehr bearbeitet oder gelöscht werden, sobald sie gespeichert wurden. Wenn ein Fall aus einer Warnung erstellt wird, werden die im Dialogfeld **Benachrichtigung bestätigen und Insider-Risikofall erstellen** eingegebenen Kommentare automatisch als Fallnotiz hinzugefügt.

Das Case Notes-Dashboard zeigt Notizen des Benutzers an, der die Notiz erstellt hat, und die Zeit, die seit dem Speichern der Notiz verstrichen ist. Verwenden Sie zum Durchsuchen des Textfeldes Groß-/Kleinschreibung für ein bestimmtes Stichwort die Schaltfläche **Suchen** im Fall Dashboard, und geben Sie ein bestimmtes Stichwort ein.

So fügen Sie einer Anfrage eine Notiz hinzu:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **fallnotizen** aus.
3. Wählen Sie **Fall Hinweis hinzufügen** aus.
4. Geben Sie im Dialogfeld **Fall Hinweis hinzufügen** den Hinweis für den Fall ein. Wählen Sie **Speichern** aus, um den Hinweis zur Anfrage hinzuzufügen, oder wählen Sie **Abbrechen** schließen, ohne die Notiz in den Fall zu speichern.

### <a name="contributors"></a>Mitwirkende

Auf der Registerkarte **Mitwirkende** können Risikoanalysten und Ermittler weitere Mitwirkende zu dem Fall hinzufügen. Standardmäßig werden alle Benutzer, denen die **Insider Risk Management Analysts** und **Insider Risk Management Investigators** -Rollen zugewiesen sind, als Mitwirkende für jeden aktiven und geschlossenen Fall aufgeführt.

Alle Fälle des Insider-Risikomanagements müssen mit angemessenen Zugriffssteuerungen verwaltet werden, damit die Vertraulichkeit und Integrität der Untersuchung aufrechterhalten wird. Um die Zugriffssteuerung für Fälle aufrechtzuerhalten, werden Benutzern ein oder zwei Arten von Zugriff auf Fälle zugewiesen:

- **Permanenter Zugriff** : für Benutzer mit den **Insider Risk Management Analysts** und **Insider Risk Management Investigators** -Rollen wird automatisch ein dauerhafter Zugriff gewährt, wenn der Fall aus einer Warnung erstellt wird. Dauerhafter Zugriff gewährt den vollständigen Zugriff auf den Fall während der Lebensdauer des Falls, und ermöglicht es der Person, weitere Mitwirkende zu dem Fall hinzuzufügen.
- **Vorübergehender Zugriff** : der temporäre Zugriff wird nur Benutzern von Mitwirkenden gewährt, die permanenten Zugriff für den Fall haben. Normalerweise wird diese Zugriffsebene dem Benutzer erteilt, der einer Anfrage Notizen hinzufügen muss. Mitwirkende mit temporärem Zugriff können auf alle Steuerelemente für das Fallmanagement zugreifen, ausgenommen:
    - Die Berechtigung, Warnungen zu bestätigen oder zu verwerfen
    - Die Berechtigung, die Mitwirkenden eines Falles zu bearbeiten
    - Die Berechtigung, Dateien und Nachrichten im Inhaltsexplorer anzuzeigen

So fügen Sie einem Fall einen Mitwirkenden hinzu:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **mitwirk** Ende aus.
3. Wählen Sie **Add Contributor** aus.
4. Geben Sie im Dialogfeld **Mitwirkender hinzufügen** den Namen des Benutzers ein, den Sie hinzufügen möchten, und wählen Sie dann den Benutzer in der Liste vorgeschlagener Benutzer aus. Diese Liste wird aus dem Azure-Active Directory Ihres Mandanten Abonnements generiert.
5. Wählen Sie im Dialogfeld **Mitwirkender hinzufügen** die Zugriffsebene für den Mitwirkenden aus. Sie können **dauerhaft** oder **temporär** auswählen.
6. Wählen Sie **Hinzufügen** aus, um den Benutzer als Teilnehmer hinzuzufügen, oder wählen Sie **Abbrechen** schließen, ohne den Benutzer als Mitwirkenden hinzuzufügen.

## <a name="case-actions"></a>Fallmaßnahmen

Risikoanalysten und Ermittler können in einer von mehreren Methoden Maßnahmen in Bezug auf einen Fall ergreifen, je nach Schweregrad des Falls, Risikoverlauf des Benutzers und Risikorichtlinien Ihrer Organisation. In einigen Situationen müssen Sie möglicherweise einen Fall an einen Benutzer oder eine Datenermittlung eskalieren, um mit anderen Bereichen Ihrer Organisation zusammenzuarbeiten und tiefer in Risiko Aktivitäten einzutauchen. Das Insider Risikomanagement ist eng mit anderen Microsoft 365-Kompatibilitätslösungen integriert, die Ihnen bei der End-to-End-Lösungsverwaltung helfen.

### <a name="send-email-notice"></a>E-Mail-Benachrichtigung senden

In den meisten Fällen sind Benutzeraktionen, die Warnungen zu Insider Risiken verursachen, versehentlich oder versehentlich. Das Senden einer Mahnungsbenachrichtigung per e-Mail an den Benutzer ist eine effektive Methode zum Dokumentieren der Fall Überprüfung und-Aktion sowie eine Methode, um Benutzer an Unternehmensrichtlinien zu erinnern oder Sie auf eine Auffrischungsschulung hinzuweisen. Benachrichtigungen werden aus [Benachrichtigungsvorlagen generiert, die Sie](insider-risk-management-notices.md) für ihre Insider Risk Management-Infrastruktur erstellen.

Es ist wichtig zu beachten, dass das Senden einer e-Mail-Benachrichtigung an einen Benutzer * nicht den Fall als _Closed * auflösen *_wird_* . In einigen Fällen möchten Sie möglicherweise eine Anfrage offen lassen, nachdem Sie eine Benachrichtigung an einen Benutzer gesendet haben, um nach weiteren Risiko Aktivitäten zu suchen, ohne einen neuen Fall zu öffnen. Wenn Sie einen Fall nach dem Senden einer Benachrichtigung auflösen möchten, müssen Sie **Fall lösen** als Folgeschritt nach dem Senden einer Benachrichtigung auswählen.

So senden Sie eine Benachrichtigung an den Benutzer, der einem Fall zugewiesen wurde:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann auf der Symbolleiste für den Fall Aktion die Schaltfläche **e-Mail-Nachricht senden** .
3. Wählen Sie im Dialogfeld **e-Mail-Nachricht senden** das Dropdown-Steuerelement **Hinweis Vorlage** auswählen aus, um die Benachrichtigungsvorlage für den Hinweis auszuwählen. Mit dieser Auswahl werden die anderen Felder im Hinweis vorab ausgefüllt.
4. Überprüfen Sie die Hinweis Felder, und aktualisieren Sie nach Bedarf. Durch die hier eingegebenen Werte werden die Werte der Vorlage außer Kraft gesetzt.
5. Wählen Sie **senden** aus, um den Hinweis an den Benutzer zu senden, oder wählen Sie **Abbrechen** , um das Dialogfeld zu schließen, ohne den Hinweis an den Benutzer zu senden. Alle gesendeten Benachrichtigungen werden der Fall Notes-Warteschlange im **Case Notes** -Dashboard hinzugefügt.

### <a name="escalate-for-investigation"></a>Eskalieren zur Überprüfung

Eskalieren Sie den Fall für die Benutzer Ermittlung in Situationen, in denen zusätzliche rechtliche Überprüfungen für die Risiko Aktivität des Benutzers erforderlich sind. Diese Eskalation öffnet einen neuen Advanced eDiscovery-Fall in Ihrer Microsoft 365-Organisation. Advanced eDiscovery bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen rechtlichen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem kann Ihr Rechtsteam den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren. Das Zuweisen eines Überprüfers als Verwahrer in einem Advanced eDiscovery-Fall, der aus einem Fall im Insider-Risikomanagement erstellt wurde, hilft Ihrem Rechtsteam dabei, angemessene Maßnahmen zu ergreifen, und die Erhaltung von Inhalten zu verwalten. Weitere Informationen zu den Advanced eDiscovery-Fällen finden Sie unter [Übersicht über Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).

So eskalieren Sie einen Fall an eine Benutzer Ermittlung:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann auf der Symbolleiste für den Fall Vorgang die Schaltfläche **zur Untersuchung eskalieren aus** .
3. Geben Sie im Dialogfeld **zur Untersuchung eskalieren** einen Namen für die Untersuchung des neuen Benutzers ein. Geben Sie bei Bedarf Hinweise zu dem Fall ein, und wählen Sie **eskalieren** aus.
4. Überprüfen Sie die Hinweis Felder, und aktualisieren Sie nach Bedarf. Durch die hier eingegebenen Werte werden die Werte der Vorlage außer Kraft gesetzt.
5. Wählen Sie **bestätigen** aus, um den Benutzer Ermittlungs Fall zu erstellen, oder klicken Sie auf **Abbrechen** , um das Dialogfeld zu schließen, ohne einen neuen Ermittlungs Fall für Benutzer zu erstellen.

Nachdem der Fall des Insider Risikomanagements an einen neuen Benutzer Ermittlungs Fall eskaliert wurde, können Sie den neuen Fall im **eDiscovery**  >  Microsoft 365 Compliance Center im Bereich eDiscovery **Advanced** überprüfen.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Ausführen von automatisierten Aufgaben mit Power Automation Flows für den Fall

Mit den empfohlenen Power-Automatisierungs Flüssen können Risiko Ermittler und Analysten schnell Aktionen durchführen:

- Anfordern von Informationen von HR oder Unternehmen über einen Benutzer in einem Fall mit Insider Risiken
- Benachrichtigen des Managers, wenn ein Benutzer über eine Insider Risiko Warnung verfügt
- Hinzufügen von Kalendererinnerungen zur Nachverfolgung bei einem Insider Risikofall

Zum Ausführen, verwalten oder Erstellen von Power Automation Flows für ein Insider Risk Management-Fall:

1. Wählen Sie auf der Symbolleiste für den Fall Vorgang **automatisieren** aus. 
2. Wählen Sie den auszuführenden Power-Automatisierungs Fluss aus, und wählen Sie **Ablaufsteuerung** aus. 
3. Klicken Sie nach Abschluss des Ablaufs auf **Fertig** .

Weitere Informationen zu Power Automation Flows für Insider Risk Management finden Sie unter [Erste Schritte mit Einstellungen für das Insider Risikomanagement](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Anzeigen oder Erstellen eines Teams von Microsoft Teams für den Fall

Wenn Microsoft Teams-Integration für Insider Risk Management in Einstellungen aktiviert ist, wird ein Microsoft Teams-Team automatisch jedes Mal erstellt, wenn eine Warnung bestätigt wird und ein Fall erstellt wird. Risiko Ermittler und Analysten können Microsoft Teams schnell öffnen und direkt zum Team für einen Fall navigieren, indem Sie in der Symbolleiste für den Fall Aktion die Option **Microsoft Teams-Team anzeigen** auswählen.

Für Fälle, die vor dem Aktivieren der Microsoft-Team Integration geöffnet wurden, können Risiko Ermittler und Analysten ein neues Microsoft Teams-Team für einen Fall erstellen, indem Sie auf der Symbolleiste für den Fall Aktion die Option **Microsoft Teams-Team erstellen** auswählen.

Wenn ein Fall aufgelöst wird, wird das zugehörige Microsoft-Team automatisch archiviert (ausgeblendet und schreibgeschützt).

Weitere Informationen zu Microsoft Teams für das Insider Risikomanagement finden Sie unter [Erste Schritte mit Einstellungen für das Insider Risikomanagement](insider-risk-management-settings.md#microsoft-teams-preview).

### <a name="share-the-case"></a>Freigeben der Groß-/Kleinschreibung

Durch die Freigabe eines Insider Risikomanagement-Falles können Risikoprüfer und Analysten problemlos mit anderen Compliance-Beteiligten in Ihrer Organisation zusammenarbeiten. Sie können einen Link zu einem Insider Risk Management-Fall schnell für externe Beteiligte aus dem Fallmanagement Bereich freigeben. Für den Zugriff auf den Fall Insider Risk Management aus dem Link müssen Beteiligte in einer der Rollengruppen für Insider Risikomanagement enthalten sein.

>[!NOTE]
>Die ServiceNow-Vorschau endet am 30 2020. November und wird nicht fortgesetzt. Vielen Dank für Ihr Feedback und ihre Unterstützung, während wir die nächsten Schritte bestimmen.

Die folgenden Freigabeoptionen stehen zur Verfügung:

- **ServiceNow** : Nachdem Sie den Microsoft 365 ServiceNow-Connector für Ihre Microsoft 365-Organisation konfiguriert haben, können Sie problemlos einen Link für den Fall freigeben, einen Vorfall öffnen oder eine Änderung an ihrer ServiceNow-Organisation anfordern. Wenn Sie den Fall für ServiceNow freigeben möchten **Share** , wählen Sie  >  **ServiceNow** aus der Fall Aktion freigeben aus. Die ServiceNow-Integration mit Insider Risk Management-Unterstützung umfasst die folgenden Fall Informationen und Aktionen:
    - **Vorgangsname** : der Name für den neuen ServiceNow-Vorgang.
    - **Aufgabenbeschreibung** : die Beschreibung für den neuen ServiceNow-Vorgang. Dieses bearbeitbare Beschreibungsfeld enthält automatisch einen Link zum Fall "Insider Risk Management".
    - **Vorgangstyp** : der Vorgangstyp für den neuen ServiceNow-Vorgang, entweder *Vorfall* oder *Änderungsanforderung* .
    - **Priorität** : die Priorität für den neuen ServiceNow-Vorgang, entweder *Planung* , *niedrig* , *moderat* , *hoch* oder *kritisch* .
    - **Fälligkeitsdatum** : das angeforderte Datum für den Abschluss der ServiceNow-Aufgabe.

![Freigabe von Insider Risikomanagement mit ServiceNow](../media/insider-risk-share-servicenow.png)

- **E-Mail** : teilt einen Link zum Insider Risk Management-Fall in einer e-Mail. Sie können einen beliebigen lokal konfigurierten e-Mail-Client mit dieser Freigabeoption auswählen. Wenn Sie den Fall Link für e-Mail freigeben möchten **Share** , wählen Sie  >  in der Symbolleiste für den Fall Vorgang die Option **e-Mail** freigeben aus.
- **Link kopieren** : kopiert einen Link zum Insider Risikomanagement-Fall in Ihre Zwischenablage. Um den Fall Link in Ihre Zwischenablage zu kopieren **Share** , wählen Sie  >  **Link Kopie** freigeben in der Symbolleiste für den Fall Aktion aus.

### <a name="resolve-the-case"></a>Auflösen des Falls

Nachdem Risikoanalysten und Ermittler Ihre Überprüfung und Untersuchung abgeschlossen haben, kann ein Fall aufgelöst werden, um auf alle derzeit im Fall enthaltenen Benachrichtigungen zu reagieren. Durch das Auflösen eines Falls wird eine Auflösungs Klassifizierung hinzugefügt, der Fall Status in " *geschlossen* " geändert, und die Auflösungs Aktions Gründe werden automatisch der Warteschlange "Case Notes" im Dashboard " **Case Notes** " hinzugefügt. Fälle können auf zwei Arten aufgelöst werden:

- **Gutartig** : die Klassifizierung für Fälle, in denen Richtlinien Übereinstimmungs Warnungen als niedriges Risiko, nicht schwerwiegend oder falsch positiv bewertet werden.
- **Bestätigte Richtlinienverletzung** : die Klassifizierung für Fälle, in denen Richtlinien Übereinstimmungs Warnungen als riskant, schwerwiegend oder als Ergebnis böswilliger Absicht ausgewertet werden.

So lösen Sie einen Fall auf:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie eine Groß-/Kleinschreibung aus, und wählen Sie dann auf der Symbolleiste Fall Aktion die Schaltfläche **Auflösen groß** -/Kleinschreibung.
3. Wählen Sie im Dialogfeld **Auflösungs Fall** das Dropdown-Steuerelement **Auflösen** aus, um die Lösungs Klassifizierung für den Fall auszuwählen. Die Optionen sind eine **gutartige** oder **bestätigte Richtlinienverletzung** .
4. Geben Sie im Dialogfeld **Auflösungs Fall** die Gründe für die Klassifizierung der Auflösung im Textfeld **Aktion durchgeführt** ein.
5. Wählen Sie **Auflösen** aus, um den Fall zu schließen, oder wählen Sie **Abbrechen** schließen, ohne den Fall zu lösen.
