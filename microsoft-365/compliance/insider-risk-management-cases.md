---
title: Insider Risikomanagement-Fälle
description: Informationen zu Insider Risikomanagement-Fällen in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: d4c2ed423743bb0f7a9c4550421c5266cc5d08b0
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091952"
---
# <a name="insider-risk-management-cases"></a>Insider Risikomanagement-Fälle

Fälle sind das Herzstück des Insider Risikomanagements und ermöglichen es Ihnen, Probleme, die durch in ihren Richtlinien definierte Risikoindikatoren generiert werden, eingehend zu untersuchen und Maßnahmen zu ergreifen. Fälle werden manuell aus Warnungen in den Situationen erstellt, in denen weitere Aktionen erforderlich sind, um ein Compliance-bezogenes Problem für einen Mitarbeiter zu beheben. Bei jedem Fall handelt es sich um einen einzelnen Mitarbeiter, und mehrere Benachrichtigungen für den Mitarbeiter können einem vorhandenen Fall oder einem neuen Fall hinzugefügt werden. Nach der Untersuchung der Einzelheiten eines Falls können Sie Maßnahmen ergreifen, indem Sie dem Mitarbeiter eine Mitteilung schicken, den Fall als gutartig lösen oder zu einer Daten- oder Mitarbeiteruntersuchung eskalieren.

## <a name="case-dashboard"></a>Fall-Dashboard

Im Dashboard**Fälle** im Insider-Risikomanagement können Sie Fälle anzeigen und entsprechende Maßnahmen ergreifen. Jedes Berichts-Widget auf dem Dashboard zeigt Informationen für die letzten 30 Tage an.

- **Aktive Fälle**: die Gesamtzahl der untersuchten aktiven Fälle.
- **Fälle in den letzten 30 Tagen**: die Gesamtzahl der erstellten Fälle, sortiert nach *aktivem* und *geschlossenem* Status.
- **Statistik**: durchschnittliche Zeit der aktiven Fälle, aufgeführt in Stunden, Tagen oder Monaten.

In der Fall-Warteschlange befinden sich alle aktiven und abgeschlossenen Fälle Ihres Unternehmens sowie der aktuelle Zustand der folgenden Fall-Attribute:

- **Case Name**: der Name des Falls, der definiert wird, wenn eine Warnung bestätigt wird und der Fall erstellt wird.  
- **Status**: der Status des Falls, entweder *aktiv* oder *geschlossen*.
- **User**: der Mitarbeiter für den Fall.
- **Geöffneter Zeitfall**: die Zeit, die seit dem Öffnen des Groß-/Kleinschreibung-Verfahrens vergangen ist.
- **Total Policy Alerts**: die Anzahl der Richtlinien Übereinstimmungen, die in der Anfrage enthalten sind. Diese Zahl kann steigen, wenn neue Warnungen zu dem Fall hinzugefügt werden.
- **Last updated**: die Zeit, die vergangen ist, seit es eine zusätzliche Groß-/Kleinschreibung oder Änderung im Fall Status gegeben hat.
- **Zuletzt aktualisiert von**: der Name des Insider Risk Management Analysts oder Investigators, der den Fall zuletzt aktualisiert hat.

![Insider Risk Management Cases-Dashboard](../media/insider-risk-cases-dashboard.png)

Verwenden Sie das **Search** -Steuerelement, um nach bestimmten Text zu suchen, und verwenden Sie den Fallfilter, um Fälle anhand der folgenden Attribute zu sortieren:

- Status
- Öffnung des Falls, Startdatum und Enddatum
- Letzte Aktualisierung, Startdatum und Enddatum

## <a name="investigate-a-case"></a>Untersuchen eines Falls

Eine eingehendere Untersuchung der Warnungen beim Insider Risikomanagement ist für die richtigen Korrekturmaßnahmen wichtig. Bei Insider Risk Management-Fällen handelt es sich um das zentrale Verwaltungstool, mit dem Sie tiefer in den Verlauf von Mitarbeiter Risiken und Warnungsdetails eintauchen und die Inhalte und Nachrichten untersuchen können, die Risiken ausgesetzt sind. Risikoanalysten und Ermittler verwenden auch Fälle, um Überprüfung Feedback und Notizen zu zentralisieren und die Fall Behebung zu verarbeiten. 

Wenn Sie einen Fall auswählen, werden die Fall-Verwaltungstool geöffnet. Diese ermöglichen es Analysten und Ermittlern, sich den Fall bis ins kleinste Detail anzeigen zu lassen.

### <a name="case-overview"></a>Fallübersicht

Die Registerkarte **Fallübersicht** fasst die Warnungsaktivitäten und den Verlauf der Risikostufe für jeden Fall zusammen. Das Widget **Warnungen** zeigt die Richtlinien Übereinstimmungen für den Fall an, einschließlich des Status der Warnung, des Schweregrads des Warnungs Risikos und der Feststellung der Warnung. Das Diagramm **Risikostufenverlauf** zeigt die Risikostufe des entsprechenden Benutzers in den letzten 30 Tagen. Das Liniendiagramm ermöglicht es Analysten und Ermittlern, die Entwicklung des allgemeinen Benutzerrisikos im Laufe der Zeit schnell auf einen Blick zu erfassen. Das Widget **Inhalt der Risikoaktivität** fasst die Daten- und Inhaltstypen zusammen, die in Fall-Warnungen enthalten sind. Dieses Widget bietet einen Gesamtüberblick über alle Daten und Inhalte, die in diesem Fall gefährdet sind.

Der Bereich **Fall Details** ist auf allen Registerkarten für die Fallverwaltung verfügbar und fasst die Fall Details für Risikoanalysten und Ermittler zusammen. Sie umfasst die folgenden Bereiche:

- **Case Name**: der Name der Groß-/Kleinschreibung mit einer automatisch generierten fallsequenz Nummer und dem Namen des Risikos, das der Richtlinienvorlage zugeordnet ist, die von der ersten bestätigten Warnung gefunden wurde. 
- **Case Status**: der aktuelle Status des Falls, entweder *aktiv* oder *geschlossen*.
- **Risikobewertung des Benutzers**: das aktuelle berechnete Risikoniveau des Benutzers für den Fall. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein.
- **Benachrichtigungen bestätigt**: Liste der Benachrichtigungen für den Benutzer, die für den Fall bestätigt wurden.
- **Inhalt in Gefahr**: Liste der Inhalte, sortiert nach Inhaltsquellen und Typen. Beispielsweise würden Sie für gefährdete Inhalte in SharePoint Online eine Liste mit Ordner- oder Dateinamen sehen, die der Risikoaktivität für Warnungen im entsprechenden Fall zugeordnet sind.

![Insider Risk Management-Fall Details](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Warnungen

Auf der Registerkarte **Benachrichtigungen** werden die aktuellen Warnungen zusammengefasst, die in der Anfrage enthalten sind. Neue Warnungen werden möglicherweise zu einem vorhandenen Fall hinzugefügt, und Sie werden der **Benachrichtigungs** Warteschlange hinzugefügt, sobald Sie zugewiesen sind. Die folgenden Warnungs Attribute werden in der Warteschlange aufgeführt:

- Status
- Schweregrad
- Erkannte Zeit

Wählen Sie in der Warteschlange eine Warnung aus, um die **Warnungs Detail** Seite anzuzeigen.

Verwenden Sie das Search-Steuerelement, um Warnungsnamen nach bestimmten Text zu durchsuchen, und verwenden Sie den Warnungsfilter, um Fälle anhand der folgenden Attribute zu sortieren:

- Status
- Schweregrad
- Zeitpunkt der Erkennung, Startdatum und Enddatum

### <a name="user-activity"></a>Benutzeraktivität

Die Registerkarte**Benutzeraktivität** ist eines der leistungsstärksten Werkzeuge für die Analyse und Untersuchung interner Risiken bei Föllen in der Insider-Risikomanagement-Lösung. Diese Registerkarte ist so strukturiert, dass eine schnelle Überprüfung eines Falls möglich ist, einschließlich einer Verlaufs Zeitachse aller Warnungen, aller Warnungsdetails, des aktuellen Risiko Werts für den Benutzer in dem Fall und der Steuerelemente, mit denen wirksame Maßnahmen zur Eindämmung der Risiken in dem Fall ergriffen werden.

![Insider Risk Management-Benutzeraktivität](../media/insider-risk-user-activities.png)

1. **Datums-und Fenster Zeitfilter**: Standardmäßig werden die letzten sechs Monate der im Fall bestätigten Benachrichtigungen im Diagramm Benutzeraktivität angezeigt. Sie können die Diagrammansicht ganz einfach mit dem Schieberegler an beiden Enden des Diagrammfensters filtern oder indem Sie ein bestimmtes Start-und Enddatum im Diagramm Filter-Steuerelement definieren.
2. **Risiko Warnungs Aktivität und Details**: Risiko Aktivitäten werden visuell als farbige Blasen im Diagramm Benutzeraktivität angezeigt. Blasen werden für verschiedene Risikokategorien erstellt, und die Blasengröße ist proportional zur Anzahl der Risiko Aktivitäten für die Kategorie. Wählen Sie eine Blase aus, um die Details für jede Risiko Aktivität anzuzeigen. Details umfassen:
    - **Datum** der Risikoaktivität.
    - Die **Risiko Aktivitätskategorie**. *E-Mail-Nachrichten beispielsweise mit Anlagen, die außerhalb der Organisation* oder *von SharePoint Online heruntergeladen*wurden.
    - **Risikobewertung** für die Warnung. Diese Bewertung ist der numerische Wert für den Schweregrad des Risikos.
    - Anzahl der Ereignisse, die mit der Warnung verknüpft sind. Links zu jeder Datei oder E-Mail, die mit der Risikoaktivität verknüpft sind, können ebenfalls abgerufen werden.
3. **Legende zur Risiko Aktivität**: am unteren Rand des Benutzer Aktivitätsdiagramms können Sie mit einer farbcodierten Legende schnell die Risikokategorie für jede Warnung bestimmen.
4. **Chronologie der Risiko Aktivität**: die vollständige Chronologie aller mit dem Fall verbundenen Risikowarnungen wird aufgeführt, einschließlich aller Details, die in der entsprechenden Warnungs Blase verfügbar sind.
5. **Case-Aktionen**: Optionen zum Auflösen der Groß-/Kleinschreibung befinden sich auf der Symbolleiste für den Fall Vorgang. Sie können einen Fall auflösen, eine E-Mail-Benachrichtigung an den betreffenden Mitarbeiter senden, oder den Fall für eine Daten- oder Mitarbeiteruntersuchung eskalieren.

### <a name="content-explorer"></a>Inhalts-Explorer

Auf der Registerkarte **Inhalts-Explorer** können Risikoanalysten und Ermittler Kopien aller einzelnen Dateien und e-Mail-Nachrichten überprüfen, die mit Risikowarnungen verbunden sind. Wenn beispielsweise eine Warnung erstellt wird, wenn ein Mitarbeiter Hunderte von Dateien aus SharePoint Online herunterlädt und die Aktivität eine Richtlinien Warnung auslöst, werden alle heruntergeladenen Dateien für die Warnung erfasst und aus den ursprünglichen Speicherquellen in den Fall Insider Risk Management kopiert.

Der Inhalts-Explorer ist ein leistungsfähiges Tool mit einfachen und erweiterten Such-und Filterfunktionen. Weitere Informationen zur Verwendung des Inhalts-Explorers finden Sie unter [Insider Risk Management Content Explorer](insider-risk-management-content-explorer.md).

![Risikomanagement für Insider Fälle Inhalts-Explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Fallnotizen

Die Registerkarte **fallnotizen** in dem Fall besteht darin, dass Risikoanalysten und Ermittler Kommentare, Feedback und Einblicke in Ihre Arbeit für den Fall freigeben. Notizen sind dauerhafte Ergänzungen zu einem Fall und können nicht mehr bearbeitet oder gelöscht werden, sobald sie gespeichert wurden. Wenn ein Fall aus einer Warnung erstellt wird, werden die im Dialogfeld **Benachrichtigung bestätigen und Insider-Risikofall erstellen** eingegebenen Kommentare automatisch als Fallnotiz hinzugefügt.

Das Case Notes-Dashboard zeigt Notizen des Benutzers an, der die Notiz erstellt hat, und die Zeit, die seit dem Speichern der Notiz verstrichen ist. Verwenden Sie zum Durchsuchen des Textfeldes Groß-/Kleinschreibung für ein bestimmtes Stichwort die Schaltfläche **Suchen** im Fall Dashboard, und geben Sie ein bestimmtes Stichwort ein.

So fügen Sie einer Anfrage eine Notiz hinzu:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **fallnotizen** aus.
3. Wählen Sie **Fall Hinweis hinzufügen**aus.
4. Geben Sie im Dialogfeld **Fall Hinweis hinzufügen** den Hinweis für den Fall ein. Wählen Sie **Speichern** aus, um den Hinweis zur Anfrage hinzuzufügen, oder wählen Sie **Abbrechen** schließen, ohne die Notiz in den Fall zu speichern.

### <a name="contributors"></a>Mitwirkende

Auf der Registerkarte **Mitwirkende**können Risikoanalysten und Ermittler weitere Mitwirkende zu dem Fall hinzufügen. Standardmäßig werden alle Benutzer, denen die **Insider Risk Management Analysts** und **Insider Risk Management Investigators** -Rollen zugewiesen sind, als Mitwirkende für jeden aktiven und geschlossenen Fall aufgeführt.

Alle Fälle des Insider-Risikomanagements müssen mit angemessenen Zugriffssteuerungen verwaltet werden, damit die Vertraulichkeit und Integrität der Untersuchung aufrechterhalten wird. Um die Zugriffssteuerung für Fälle aufrechtzuerhalten, werden Benutzern ein oder zwei Arten von Zugriff auf Fälle zugewiesen:

- **Permanenter Zugriff**: für Benutzer mit den **Insider Risk Management Analysts** und **Insider Risk Management Investigators** -Rollen wird automatisch ein dauerhafter Zugriff gewährt, wenn der Fall aus einer Warnung erstellt wird. Dauerhafter Zugriff gewährt den vollständigen Zugriff auf den Fall während der Lebensdauer des Falls, und ermöglicht es der Person, weitere Mitwirkende zu dem Fall hinzuzufügen.
- **Vorübergehender Zugriff**: der temporäre Zugriff wird nur Benutzern von Mitwirkenden gewährt, die permanenten Zugriff für den Fall haben. Normalerweise wird diese Zugriffsebene dem Benutzer erteilt, der einer Anfrage Notizen hinzufügen muss. Mitwirkende mit temporärem Zugriff können auf alle Steuerelemente für das Fallmanagement zugreifen, ausgenommen:
    - Die Berechtigung, Warnungen zu bestätigen oder zu verwerfen
    - Die Berechtigung, die Mitwirkenden eines Falles zu bearbeiten
    - Die Berechtigung, Dateien und Nachrichten im Inhaltsexplorer anzuzeigen

So fügen Sie einem Fall einen Mitwirkenden hinzu:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **mitwirk** Ende aus.
3. Wählen Sie **Add Contributor**aus.
4. Geben Sie im Dialogfeld **Mitwirkender hinzufügen** den Namen des Benutzers ein, den Sie hinzufügen möchten, und wählen Sie dann den Benutzer in der Liste vorgeschlagener Benutzer aus. Diese Liste wird aus dem Azure-Active Directory Ihres Mandanten Abonnements generiert.
5. Wählen Sie im Dialogfeld **Mitwirkender hinzufügen** die Zugriffsebene für den Mitwirkenden aus. Sie können **dauerhaft** oder **temporär**auswählen.
6. Wählen Sie **Hinzufügen** aus, um den Benutzer als Teilnehmer hinzuzufügen, oder wählen Sie **Abbrechen** schließen, ohne den Benutzer als Mitwirkenden hinzuzufügen.

## <a name="case-actions"></a>Fallmaßnahmen

Risikoanalysten und Ermittler können abhängig vom Schweregrad des Falles, vom Risikoverlauf des betreffenden Benutzers, und von den Risikorichtlinien der Organisation Maßnahmen für einen Fall mithilfe einer von verschiedenen Methoden ergreifen. In einigen Fällen müssen Sie möglicherweise einen Fall eine Mitarbeiter- oder Datenermittlung eskalieren, um mit anderen Bereichen Ihrer Organisation zusammenzuarbeiten und sich tiefgreifender mit den Risikoaktivitäten zu befassen. Das Insider Risikomanagement ist eng mit anderen Microsoft 365-Kompatibilitätsfeatures integriert, die Ihnen bei der End-to-End-Lösung helfen.

### <a name="send-a-notice"></a>Senden einer Notiz

In den meisten Fällen sind Handlungen von Mitarbeitern, die Warnungen vor Richtlinienverstößen hervorrufen, unabsichtlich oder versehentlich. Das Senden einer Erinnerung an den Mitarbeiter per E-Mail ist eine effektive Methode zur Dokumentation der Fallüberprüfung und der Maßnahmen sowie eine Methode, um die Mitarbeiter an Unternehmensrichtlinien zu erinnern oder auf Auffrischungsschulungen hinzuweisen. Benachrichtigungen werden aus [Benachrichtigungsvorlagen generiert, die Sie](insider-risk-management-notices.md) für ihre Insider Risk Management-Infrastruktur erstellen.

Denken Sie daran, dass das Senden einer Erinnerung an einen Mitarbeiter ***den Fall nicht***als *abgeschlossen* markiert. In einigen Fällen möchten Sie möglicherweise einen Fall geöffnet lassen, auch nachdem Sie eine Benachrichtigung an den Mitarbeiter gesendet haben, um potentielle weitere Risikoaktivitäten nachvollziehen zu können, ohne einen neuen Fall zu öffnen. Wenn Sie einen Fall nach dem Senden einer Benachrichtigung auflösen möchten, müssen Sie **Fall lösen** als Folgeschritt nach dem Senden einer Benachrichtigung auswählen.

So senden Sie eine Benachrichtigung an den einem Fall zugewiesenen Mitarbeiter:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und klicken Sie dann auf der Symbolleiste für den Fall Aktion auf die Schaltfläche **e-Mail-Nachricht senden**
3. Wählen Sie im Dialogfeld **e-Mail-Nachricht senden** das Dropdown-Steuerelement **Hinweis Vorlage** auswählen aus, um die Benachrichtigungsvorlage für den Hinweis auszuwählen. Mit dieser Auswahl werden die anderen Felder im Hinweis vorab ausgefüllt.
4. Überprüfen Sie die Hinweis Felder, und aktualisieren Sie nach Bedarf. Durch die hier eingegebenen Werte werden die Werte der Vorlage außer Kraft gesetzt.
5. Wählen Sie **senden** aus, um den Hinweis an den Mitarbeiter zu senden, oder wählen Sie **Abbrechen** , um das Dialogfeld zu schließen, ohne den Hinweis an den Mitarbeiter zu senden. Alle gesendeten Benachrichtigungen werden der Fall Notes-Warteschlange im **Case Notes** -Dashboard hinzugefügt.

### <a name="escalate-for-investigation"></a>Eskalieren zur Überprüfung

In Situationen, in denen eine zusätzliche rechtliche Überprüfung für die Risikoaktivitäten des Mitarbeiters erforderlich ist, eskalieren Sie den Fall an die Mitarbeiteruntersuchung. Diese Eskalation öffnet einen neuen Advanced eDiscovery-Fall in Ihrer Microsoft 365-Organisation. Advanced eDiscovery bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen rechtlichen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem kann Ihr Rechtsteam den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren. Das Zuweisen eines Überprüfers als Verwahrer in einem Advanced eDiscovery-Fall, der aus einem Fall im Insider-Risikomanagement erstellt wurde, hilft Ihrem Rechtsteam dabei, angemessene Maßnahmen zu ergreifen, und die Erhaltung von Inhalten zu verwalten. Weitere Informationen zu den Advanced eDiscovery-Fällen finden Sie unter [Übersicht über Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).

So eskalieren Sie einen Fall an eine Untersuchung durch Mitarbeiter:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann auf der Symbolleiste für den Fall Vorgang die Schaltfläche **zur Untersuchung eskalieren aus** .
3. Geben Sie im Dialogfeld **zur Untersuchung eskalieren** einen Namen für die neue Mitarbeiter Ermittlung ein. Geben Sie bei Bedarf Hinweise zu dem Fall ein, und wählen Sie **eskalieren**aus.
5. Wählen Sie **bestätigen** aus, um den Ermittlungs Fall für Mitarbeiter zu erstellen, oder wählen Sie **Abbrechen** , um das Dialogfeld zu schließen, ohne einen neuen Ermittlungs Fall für Mitarbeiter zu erstellen.

Nachdem der Fall des Insider Risikomanagements an einen neuen Ermittlungs Fall für Mitarbeiter eskaliert wurde, können Sie den neuen Fall im **eDiscovery**  >  Microsoft 365 Compliance Center im eDiscovery**Advanced** -Bereich überprüfen.

### <a name="resolve-the-case"></a>Auflösen des Falls

Wenn die Überprüfung und Untersuchung durch die Risikoanalysten und Ermittler abgeschlossen wurde, kann ein Fall aufgelöst werden, um Maßnahmen als Reaktion auf alle Warnungen zu ergreifen, die aktuell im Fall enthalten sind. Durch das Auflösen eines Falls wird eine Auflösungs Klassifizierung hinzugefügt, der Fall Status in " *geschlossen*" geändert, und die Auflösungs Aktions Gründe werden automatisch der Warteschlange "Case Notes" im Dashboard " **Case Notes** " hinzugefügt. Fälle können auf zwei Arten aufgelöst werden:

- **Gutartig**: die Klassifizierung für Fälle, in denen Richtlinien Übereinstimmungs Warnungen als niedriges Risiko, nicht schwerwiegend oder falsch positiv bewertet werden.
- **Bestätigte Richtlinienverletzung**: die Klassifizierung für Fälle, in denen Richtlinien Übereinstimmungs Warnungen als riskant, schwerwiegend oder als Ergebnis böswilliger Absicht ausgewertet werden.

So lösen Sie einen Fall auf:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie eine Groß-/Kleinschreibung aus, und wählen Sie dann auf der Symbolleiste Fall Aktion die Schaltfläche **Auflösen groß** -/Kleinschreibung.
3. Wählen Sie im Dialogfeld **Auflösungs Fall** das Dropdown-Steuerelement **Auflösen** aus, um die Lösungs Klassifizierung für den Fall auszuwählen. Die Optionen sind eine **gutartige** oder **bestätigte Richtlinienverletzung**.
4. Geben Sie im Dialogfeld **Auflösungs Fall** die Gründe für die Klassifizierung der Auflösung im Textfeld **Aktion durchgeführt** ein.
5. Wählen Sie **Auflösen** aus, um den Fall zu schließen, oder wählen Sie **Abbrechen** schließen, ohne den Fall zu lösen.
