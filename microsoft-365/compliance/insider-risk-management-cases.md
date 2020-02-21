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
ms.openlocfilehash: 6b5132cad5725e46a49b9010868ede423321f307
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179176"
---
# <a name="insider-risk-management-cases"></a>Insider Risikomanagement-Fälle

Fälle sind das Herzstück des Insider Risikomanagements und ermöglichen es Ihnen, Probleme, die durch in ihren Richtlinien definierte Risikoindikatoren generiert werden, eingehend zu untersuchen und Maßnahmen zu ergreifen. Fälle werden manuell aus Warnungen in den Situationen erstellt, in denen weitere Aktionen erforderlich sind, um ein Compliance-bezogenes Problem für einen Mitarbeiter zu beheben. Bei jedem Fall handelt es sich um einen einzelnen Mitarbeiter, und mehrere Benachrichtigungen für den Mitarbeiter können einem vorhandenen Fall oder einem neuen Fall hinzugefügt werden. Nachdem Sie die Details eines Falles untersucht haben, können Sie eine Aktion durchführen, indem Sie dem Mitarbeiter eine Benachrichtigung senden, den Fall als gutartig auflösen oder an eine Daten-oder Mitarbeiter Ermittlung eskalieren.

## <a name="case-dashboard"></a>Case-Dashboard

Im Dashboard für Insider Risikomanagement- **Fälle** können Sie Fälle anzeigen und Aktionen ausführen. Jedes Berichts-Widget auf dem Dashboard zeigt Informationen für die letzten 30 Tage an.

- **Aktive Fälle**: die Gesamtzahl der untersuchten aktiven Fälle.
- **Fälle in den letzten 30 Tagen**: die Gesamtzahl der erstellten Fälle, sortiert nach *aktivem* und *geschlossenem* Status.
- **Statistik**: durchschnittliche Zeit der aktiven Fälle, aufgeführt in Stunden, Tagen oder Monaten.

In der Fall Warteschlange werden alle aktiven und geschlossenen Fälle für Ihre Organisation neben dem aktuellen Status der folgenden Fall Attribute aufgeführt:

- **Case Name**: der Name des Falls, der definiert wird, wenn eine Warnung bestätigt wird und der Fall erstellt wird.  
- **Status**: der Status des Falls, entweder *aktiv* oder *geschlossen*.
- **User**: der Mitarbeiter für den Fall.
- **Geöffneter Zeitfall**: die Zeit, die seit dem Öffnen des Groß-/Kleinschreibung-Verfahrens vergangen ist.
- **Total Policy Alerts**: die Anzahl der Richtlinien Übereinstimmungen, die in der Anfrage enthalten sind. Diese Zahl kann zunehmen, wenn dem Fall neue Warnungen hinzugefügt werden.
- **Last updated**: die Zeit, die vergangen ist, seit es eine zusätzliche Groß-/Kleinschreibung oder Änderung im Fall Status gegeben hat.
- **Zuletzt aktualisiert von**: der Name des Insider Risk Management Analysts oder Investigators, der den Fall zuletzt aktualisiert hat.

![Insider Risk Management Cases-Dashboard](../media/insider-risk-cases-dashboard.png)

Verwenden Sie das **Search** -Steuerelement, um nach bestimmten Text zu suchen, und verwenden Sie den Fallfilter, um Fälle anhand der folgenden Attribute zu sortieren:

- Status
- Geöffnetes Zeit Verfahren, Startdatum und Enddatum
- Datum der letzten Aktualisierung, Anfangstermin und Enddatum

## <a name="investigate-a-case"></a>Untersuchen eines Falls

Eine eingehendere Untersuchung der Warnungen beim Insider Risikomanagement ist für die richtigen Korrekturmaßnahmen wichtig. Bei Insider Risk Management-Fällen handelt es sich um das zentrale Verwaltungstool, mit dem Sie tiefer in den Verlauf von Mitarbeiter Risiken und Warnungsdetails eintauchen und die Inhalte und Nachrichten untersuchen können, die Risiken ausgesetzt sind. Risikoanalysten und Ermittler verwenden auch Fälle, um Überprüfung Feedback und Notizen zu zentralisieren und die Fall Behebung zu verarbeiten. 

Wenn Sie einen Fall auswählen, werden die Fall Verwaltungstools geöffnet, und Analysten und Ermittler können sich eingehend mit den Details der Fälle beschäftigen.

### <a name="case-overview"></a>Fallübersicht

Die Registerkarte **fallübersicht** fasst die Warnungs Aktivität und den Verlauf der Risikostufe für den Fall zusammen. Das Widget **Warnungen** zeigt die Richtlinien Übereinstimmungen für den Fall an, einschließlich des Status der Warnung, des Schweregrads des Warnungs Risikos und der Feststellung der Warnung. Das Diagramm **Risikoebene Verlauf** zeigt die Benutzer Risikostufe in den letzten 30 Tagen an. Mit dem Strecken Diagramm können Analysten und Ermittler schnell den Trend des allgemeinen Benutzer Risikos im Laufe der Zeit erkennen. Das Widget zur **Risiko Aktivität** enthält eine Zusammenfassung der Daten und Inhalte in Warnungen, die dem Fall hinzugefügt werden. Dieses Widget bietet eine Übersicht über die gesamten Daten und Inhaltssätze, die in dem Fall gefährdet sind.

Der Bereich **Fall Details** ist auf allen Registerkarten für die Fallverwaltung verfügbar und fasst die Fall Details für Risikoanalysten und Ermittler zusammen. Sie umfasst die folgenden Bereiche:

- **Case Name**: der Name der Groß-/Kleinschreibung mit einer automatisch generierten fallsequenz Nummer und dem Namen des Risikos, das der Richtlinienvorlage zugeordnet ist, die von der ersten bestätigten Warnung gefunden wurde. 
- **Case Status**: der aktuelle Status des Falls, entweder *aktiv* oder *geschlossen*.
- **Risikobewertung des Benutzers**: das aktuelle berechnete Risikoniveau des Benutzers für den Fall. Diese Bewertung wird alle 24 Stunden berechnet und verwendet die Warnungs Risikobewertungen aller aktiven Warnungen, die dem Benutzer zugeordnet sind.
- **Benachrichtigungen bestätigt**: Liste der Benachrichtigungen für den Benutzer, die für den Fall bestätigt wurden.
- **Inhalt in Gefahr**: Liste der Inhalte, sortiert nach Inhaltsquellen und Typen. Beispiel: für den Inhalt der Fall Benachrichtigung in SharePoint Online werden möglicherweise Ordner-oder Dateinamen aufgelistet, die der Risiko Aktivität für Warnungen in dem Fall zugeordnet sind.

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
- Erkannte Zeit, Startdatum und Enddatum

### <a name="user-activity"></a>Benutzeraktivität

Die Registerkarte **Benutzeraktivität** ist eines der leistungsstärksten Tools für die interne Risikoanalyse und-Untersuchung für Fälle in der Insider Risikomanagement-Lösung. Diese Registerkarte ist so strukturiert, dass eine schnelle Überprüfung eines Falls möglich ist, einschließlich einer Verlaufs Zeitachse aller Warnungen, aller Warnungsdetails, des aktuellen Risiko Werts für den Benutzer in dem Fall und der Steuerelemente, mit denen wirksame Maßnahmen zur Eindämmung der Risiken in dem Fall ergriffen werden.

![Insider Risk Management-Benutzeraktivität](../media/insider-risk-user-activities.png)

1. **Datums-und Fenster Zeitfilter**: Standardmäßig werden die letzten sechs Monate der im Fall bestätigten Benachrichtigungen im Diagramm Benutzeraktivität angezeigt. Sie können die Diagrammansicht ganz einfach mit dem Schieberegler an beiden Enden des Diagrammfensters filtern oder indem Sie ein bestimmtes Start-und Enddatum im Diagramm Filter-Steuerelement definieren.
2. **Risiko Warnungs Aktivität und Details**: Risiko Aktivitäten werden visuell als farbige Blasen im Diagramm Benutzeraktivität angezeigt. Blasen werden für verschiedene Risikokategorien erstellt, und die Blasengröße ist proportional zur Anzahl der Risiko Aktivitäten für die Kategorie. Wählen Sie eine Blase aus, um die Details für jede Risiko Aktivität anzuzeigen. Details umfassen:
    - **Datum** der Risiko Aktivität.
    - Die **Risiko Aktivitätskategorie**. *E-Mail-Nachrichten beispielsweise mit Anlagen, die außerhalb der Organisation* oder *von SharePoint Online heruntergeladen*wurden.
    - **Risikobewertung** für die Warnung. Diese Bewertung ist die numerische Bewertung für den Schweregrad des Warnungs Risikos.
    - Die Anzahl der Ereignisse, die der Warnung zugeordnet sind. Links zu jeder Datei oder e-Mail, die der Risiko Aktivität zugeordnet ist, sind ebenfalls verfügbar.
3. **Legende zur Risiko Aktivität**: am unteren Rand des Benutzer Aktivitätsdiagramms können Sie mit einer farbcodierten Legende schnell die Risikokategorie für jede Warnung bestimmen.
4. **Chronologie der Risiko Aktivität**: die vollständige Chronologie aller mit dem Fall verbundenen Risikowarnungen wird aufgeführt, einschließlich aller Details, die in der entsprechenden Warnungs Blase verfügbar sind.
5. **Case-Aktionen**: Optionen zum Auflösen der Groß-/Kleinschreibung befinden sich auf der Symbolleiste für den Fall Vorgang. Sie können einen Fall lösen, eine e-Mail-Nachricht an den Mitarbeiter senden oder den Fall für eine Daten-oder Mitarbeiter Ermittlung eskalieren.

### <a name="content-explorer"></a>Inhalts-Explorer

Auf der Registerkarte **Inhalts-Explorer** können Risikoanalysten und Ermittler Kopien aller einzelnen Dateien und e-Mail-Nachrichten überprüfen, die mit Risikowarnungen verbunden sind. Wenn beispielsweise eine Warnung erstellt wird, wenn ein Mitarbeiter Hunderte von Dateien aus SharePoint Online auf ein USB-Gerät herunterlädt und die Aktivität eine Richtlinien Warnung auslöst, werden alle heruntergeladenen Dateien für die Warnung erfasst und in den Fall Insider Risk Management aus kopiert. ursprüngliche Speicherquellen.

Der Inhalts-Explorer ist ein leistungsfähiges Tool mit einfachen und erweiterten Such-und Filterfunktionen. Weitere Informationen zur Verwendung des Inhalts-Explorers finden Sie unter [Insider Risk Management Content Explorer](insider-risk-management-content-explorer.md).

![Risikomanagement für Insider Fälle Inhalts-Explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Fallnotizen

Die Registerkarte **fallnotizen** in dem Fall besteht darin, dass Risikoanalysten und Ermittler Kommentare, Feedback und Einblicke in Ihre Arbeit für den Fall freigeben. Notizen sind permanente Ergänzungen zu einem Fall und können nicht bearbeitet oder gelöscht werden, nachdem die Notiz gespeichert wurde. Wenn ein Fall aus einer Warnung erstellt wird, werden die im Dialogfeld " **Warnung bestätigen" und "Insider Risiko erstellen** " angegebenen Kommentare automatisch als Fall Hinweis hinzugefügt.

Das Case Notes-Dashboard zeigt Notizen des Benutzers an, der die Notiz erstellt hat, und die Zeit, die seit dem Speichern der Notiz verstrichen ist. Verwenden Sie zum Durchsuchen des Textfeldes Groß-/Kleinschreibung für ein bestimmtes Stichwort die Schaltfläche **Suchen** im Fall Dashboard, und geben Sie ein bestimmtes Stichwort ein.

So fügen Sie einer Anfrage eine Notiz hinzu:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **fallnotizen** aus.
3. Wählen Sie **Fall Hinweis hinzufügen**aus.
4. Geben Sie im Dialogfeld **Fall Hinweis hinzufügen** den Hinweis für den Fall ein. Wählen Sie **Speichern** aus, um den Hinweis zur Anfrage hinzuzufügen, oder wählen Sie **Abbrechen** schließen, ohne die Notiz in den Fall zu speichern.

### <a name="contributors"></a>Mitwirkende

Die Registerkarte **mitwirk** Ende in dem Fall ist, wo Risikoanalysten und Ermittler können weitere Bearbeiter zu dem Fall hinzufügen. Standardmäßig werden alle Benutzer, denen die **Insider Risk Management Analysts** und **Insider Risk Management Investigators** -Rollen zugewiesen sind, als Mitwirkende für jeden aktiven und geschlossenen Fall aufgeführt.

Alle Insider Risk Management-Fälle müssen mit entsprechenden Zugriffskontrollen verwaltet werden, um die Vertraulichkeit und Integrität der Untersuchung aufrechtzuerhalten. Um die Zugriffssteuerung für Fälle aufrechtzuerhalten, wird Benutzern ein von zwei Arten von Zugriff auf Fälle zugewiesen:

- **Permanenter Zugriff**: für Benutzer mit den **Insider Risk Management Analysts** und **Insider Risk Management Investigators** -Rollen wird automatisch ein dauerhafter Zugriff gewährt, wenn der Fall aus einer Warnung erstellt wird. Der permanente Zugriff gewährt die vollständige Kontrolle über den Fall für die Lebensdauer des Falles und ermöglicht das Hinzufügen weiterer Fall Mitwirkenden.
- **Vorübergehender Zugriff**: der temporäre Zugriff wird nur Benutzern von Mitwirkenden gewährt, die permanenten Zugriff für den Fall haben. Normalerweise wird diese Zugriffsebene dem Benutzer erteilt, der einer Anfrage Notizen hinzufügen muss. Mitwirkende mit temporärem Zugriff haben alle Fall Verwaltungssteuerung außer:
    - Berechtigung zum bestätigen oder ablehnen von Benachrichtigungen
    - Berechtigung zum Bearbeiten der Mitwirkenden für Fälle
    - Berechtigung zum Anzeigen von Dateien und Nachrichten im Inhalts-Explorer

So fügen Sie einem Fall einen Mitwirkenden hinzu:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann die Registerkarte **mitwirk** Ende aus.
3. Wählen Sie **Add Contributor**aus.
4. Geben Sie im Dialogfeld **Mitwirkender hinzufügen** den Namen des Benutzers ein, den Sie hinzufügen möchten, und wählen Sie dann den Benutzer in der Liste vorgeschlagener Benutzer aus. Diese Liste wird aus dem Azure-Active Directory Ihres Mandanten Abonnements generiert.
5. Wählen Sie im Dialogfeld **Mitwirkender hinzufügen** die Zugriffsebene für den Mitwirkenden aus. Sie können **dauerhaft** oder **temporär**auswählen.
6. Wählen Sie **Hinzufügen** aus, um den Benutzer als Teilnehmer hinzuzufügen, oder wählen Sie **Abbrechen** schließen, ohne den Benutzer als Mitwirkenden hinzuzufügen.

## <a name="case-actions"></a>Fall Aktionen

Risikoanalysten und Ermittler können in einer von mehreren Methoden, abhängig vom Schweregrad des Falles, der Risiko Historie des Mitarbeiters und den Risikorichtlinien Ihrer Organisation, Aktionen für einen Fall durchführen. In einigen Situationen müssen Sie möglicherweise einen Fall an einen Mitarbeiter oder eine Datenermittlung eskalieren, um mit anderen Bereichen Ihrer Organisation zusammenzuarbeiten und tiefer in Risiko Aktivitäten einzutauchen. Das Insider Risikomanagement ist eng mit anderen Microsoft 365-Kompatibilitätsfeatures integriert, die Ihnen bei der End-to-End-Lösung helfen.

### <a name="send-a-notice"></a>Senden einer Nachricht

In den meisten Fällen sind Mitarbeiter Aktionen, mit denen Richtlinien Übereinstimmungs Warnungen erstellt werden, versehentlich oder versehentlich. Das Senden einer Mahnungsbenachrichtigung an den Mitarbeiter per e-Mail ist eine effektive Methode zum Dokumentieren der Fall Überprüfung und-Aktion sowie eine Methode, um Mitarbeiter an Unternehmensrichtlinien zu erinnern oder Sie auf eine Auffrischungsschulung hinzuweisen. Benachrichtigungen werden aus [Benachrichtigungsvorlagen generiert, die Sie](insider-risk-management-notices.md) für ihre Insider Risk Management-Infrastruktur erstellen.

Beachten Sie, dass das Senden einer Benachrichtigung an einen Mitarbeiter den Fall ***nicht*** als *geschlossen*auflöst. In einigen Fällen möchten Sie möglicherweise einen Fall nach dem Senden einer Nachricht an einen Mitarbeiter offen lassen, um nach weiteren Risiko Aktivitäten zu suchen, ohne einen neuen Fall zu öffnen. Wenn Sie einen Fall nach dem Senden eines Hinweises beheben möchten, müssen Sie den **Lösungs Fall** nach dem Senden einer Nachricht als Folgeschritt auswählen.

So senden Sie eine Benachrichtigung an den einem Fall zugewiesenen Mitarbeiter:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und klicken Sie dann auf der Symbolleiste für den Fall Aktion auf die Schaltfläche **e-Mail-Nachricht senden**
3. Wählen Sie im Dialogfeld **e-Mail-Nachricht senden** das Dropdown-Steuerelement **Hinweis Vorlage** auswählen aus, um die Benachrichtigungsvorlage für den Hinweis auszuwählen. Mit dieser Auswahl werden die anderen Felder im Hinweis vorab ausgefüllt.
4. Überprüfen Sie die Hinweis Felder, und aktualisieren Sie nach Bedarf. Durch die hier eingegebenen Werte werden die Werte der Vorlage außer Kraft gesetzt.
5. Wählen Sie **senden** aus, um den Hinweis an den Mitarbeiter zu senden, oder wählen Sie **Abbrechen** , um das Dialogfeld zu schließen, ohne den Hinweis an den Mitarbeiter zu senden. Alle gesendeten Benachrichtigungen werden der Fall Notes-Warteschlange im **Case Notes** -Dashboard hinzugefügt.

### <a name="escalate-for-investigation"></a>Eskalieren zur Untersuchung

Eskalieren Sie den Fall für die Untersuchung von Mitarbeitern in Situationen, in denen zusätzliche rechtliche Überprüfungen für die Risiko Aktivität des Mitarbeiters erforderlich sind. Durch diese Eskalation wird ein neuer erweiterter eDiscovery-Fall in Ihrer Microsoft 365-Organisation geöffnet. Advanced eDiscovery bietet einen End-to-End-Workflow zum aufbewahren, sammeln, überprüfen, analysieren und Exportieren von Inhalten, die auf interne und externe rechtliche Untersuchungen in Ihrer Organisation reagieren. Außerdem kann Ihr juristisches Team den gesamten Workflow für rechtliche Aufbewahrungs Benachrichtigungen verwalten, um mit in einem Fall beteiligten Verwaltern zu kommunizieren. Das Zuweisen eines Bearbeiters als depotverwalter in einem erweiterten eDiscovery-Fall, der aus einem Insider Risikomanagement-Fall erstellt wurde, hilft Ihrem juristischen Team, geeignete Maßnahmen zu ergreifen und die Aufbewahrung von Inhalten zu verwalten. Weitere Informationen zu erweiterten eDiscovery-Fällen finden Sie unter [Overview of Advanced eDsicovery in Microsoft 365](overview-ediscovery-20.md).

So eskalieren Sie einen Fall an eine Untersuchung durch Mitarbeiter:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie einen Fall aus, und wählen Sie dann auf der Symbolleiste für den Fall Vorgang die Schaltfläche **zur Untersuchung eskalieren aus** .
3. Geben Sie im Dialogfeld **zur Untersuchung eskalieren** einen Namen für die neue Mitarbeiter Ermittlung ein. Geben Sie bei Bedarf Hinweise zu dem Fall ein, und wählen Sie **eskalieren**aus.
5. Wählen Sie **bestätigen** aus, um den Ermittlungs Fall für Mitarbeiter zu erstellen, oder wählen Sie **Abbrechen** , um das Dialogfeld zu schließen, ohne einen neuen Ermittlungs Fall für Mitarbeiter zu erstellen.

Nachdem der Fall des Insider Risikomanagements an einen neuen Ermittlungs Fall für Mitarbeiter eskaliert wurde, können Sie den neuen Fall im Microsoft 365 Compliance Center im **eDiscovery** > **Advanced** -Bereich überprüfen.

### <a name="resolve-the-case"></a>Auflösen der Groß-/Kleinschreibung

Nachdem Risikoanalysten und Ermittler Ihre Überprüfung und Untersuchung abgeschlossen haben, kann ein Fall aufgelöst werden, um Aktionen für alle derzeit in der Anfrage enthaltenen Benachrichtigungen durchführen zu können. Durch das Auflösen eines Falls wird eine Auflösungs Klassifizierung hinzugefügt, der Fall Status in " *geschlossen*" geändert, und die Auflösungs Aktions Gründe werden automatisch der Warteschlange "Case Notes" im Dashboard " **Case Notes** " hinzugefügt. Fälle werden entweder wie folgt aufgelöst:

- **Gutartig**: die Klassifizierung für Fälle, in denen Richtlinien Übereinstimmungs Warnungen als niedriges Risiko, nicht schwerwiegend oder falsch positiv bewertet werden.
- **Bestätigte Richtlinienverletzung**: die Klassifizierung für Fälle, in denen Richtlinien Übereinstimmungs Warnungen als riskant, schwerwiegend oder als Ergebnis böswilliger Absicht ausgewertet werden.

So lösen Sie einen Fall auf:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Fälle** aus.
2. Wählen Sie eine Groß-/Kleinschreibung aus, und wählen Sie dann auf der Symbolleiste Fall Aktion die Schaltfläche **Auflösen groß** -/Kleinschreibung.
3. Wählen Sie im Dialogfeld **Auflösungs Fall** das Dropdown-Steuerelement **Auflösen** aus, um die Lösungs Klassifizierung für den Fall auszuwählen. Die Optionen sind eine **gutartige** oder **bestätigte Richtlinienverletzung**.
4. Geben Sie im Dialogfeld **Auflösungs Fall** die Gründe für die Klassifizierung der Auflösung im Textfeld **Aktion durchgeführt** ein.
5. Wählen Sie **Auflösen** aus, um den Fall zu schließen, oder wählen Sie **Abbrechen** schließen, ohne den Fall zu lösen.
