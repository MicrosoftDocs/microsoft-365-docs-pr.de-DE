---
title: Warnungen beim Insider Risikomanagement
description: Informationen zu Insider Risk Management-Warnungen in Microsoft 365
keywords: Microsoft 365, Insider Risiko, Risikomanagement, Compliance
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
ms.openlocfilehash: 7b7b6e15528d91a59575e2cfda5808106df7d61b
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199699"
---
# <a name="insider-risk-management-alerts"></a>Warnungen beim Insider Risikomanagement

Warnungen zum Insider-Risikomanagement werden automatisch durch Risikoindikatoren generiert, die in den Richtlinien zum Insider-Risikomanagement definiert sind. Diese Warnungen geben Compliance-Analysten und -Ermittlern einen umfassenden Überblick über den aktuellen Risikostatus und ermöglichen es Ihrem Unternehmen, eine Einstufung vorzunehmen und Maßnahmen für entdeckte Risiken zu ergreifen. Standardmäßig generieren Richtlinien eine bestimmte Menge an Warnungen mit niedrigem, mittlerem und hohem Schweregrad, aber Sie können [das Warnungs Volumen entsprechend Ihren Anforderungen erweitern oder verringern](insider-risk-management-settings.md#alert-volume) . Darüber hinaus können Sie den [Warnungsschwellenwert für Richtlinien Indikatoren](insider-risk-management-settings.md#indicator-level-settings-preview) beim Erstellen einer neuen Richtlinie mit dem Richtlinien-Assistenten konfigurieren.

## <a name="alert-dashboard"></a>Dashboard "Warnung"

Das Alert- **Dashboard** für Insider Risiken ermöglicht Ihnen das Anzeigen und Bearbeiten von Warnungen, die von Insider Risikorichtlinien generiert werden. Jedes Berichts-Widget zeigt Informationen für die letzten 30 Tage an.

- **Zu über**prüfende Warnungen: die Gesamtzahl der Warnungen, die Überprüfung und Selektierung erforderlich sind, wird aufgeführt, einschließlich einer Aufteilung nach Warnungsschweregrad.
- **Warnungen in den letzten 30 Tagen öffnen**: die Gesamtzahl der Warnungen, die von Richtlinien Übereinstimmungen in den letzten 30 Tagen erstellt wurden, sortiert nach hoch-, Mittel-und niedrigem Warnungsschweregrad.
- **Durchschnittliche Zeit zum Auflösen von Warnungen**: eine Zusammenfassung der nützlichen Warnungs Statistiken:
    - Durchschnittliche Zeit zur Behebung von Warnungen höheren Schweregrades, angegeben in Stunden, Tagen oder Monaten.
    - Durchschnittliche Zeit bis zur Behebung von Warnungen mittleren Schweregrades, angegeben in Stunden, Tagen oder Monaten.
    - Durchschnittliche Zeit bis zur Behebung von Warnungen niedrigen Schweregrades, angegeben in Stunden, Tagen oder Monaten.

![Alert-Dashboard für Insider-Risikomanagement](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>Bei der Verwaltung von Insider-Risiken wird eine integrierte Warnungsdrosselung verwendet, um Ihre Erfahrungen bei der Risikoermittlung und -prüfung zu schützen und zu optimieren. Diese Drosselung schützt vor Problemen, die zu einer Überlastung der Richtlinienwarnungen führen könnten, wie z. B. falsch konfigurierte Datenkonnektoren oder DLP-Richtlinien. Infolgedessen kann es zu einer Verzögerung bei der Anzeige neuer Warnungen für einen Benutzer kommen.

## <a name="alert-status-and-severity"></a>Warnungsstatus und Schweregrad

Sie können Warnungen in einem der folgenden Status selektieren:

- **Bestätigt**: eine Warnung wurde bestätigt und einem neuen oder vorhandenen Fall zugewiesen.
- **Entlassen**: eine Warnung wurde beim Triage-Prozess als gutartig zurückgewiesen.
- **Needs Review**: eine neue Warnung, bei der noch keine Triage-Aktionen durchgeführt wurden.
- **Aufgelöst**: eine Warnung, die Teil eines geschlossenen und aufgelösten Falls ist.

Warnungs Risikobewertungen werden automatisch aus mehreren Risiko Aktivitätsindikatoren berechnet. Diese Indikatoren umfassen den Typ der Risiko Aktivität, die Anzahl und Häufigkeit des Aktivitätsereignisses, den Verlauf der Benutzer Risiko Aktivität und das Hinzufügen von Aktivitäts Risiken, die die Ernsthaftigkeit der Aktivität erhöhen können. Die Risikoeinstufung der Warnung bestimmt die programmatische Zuweisung eines Risikoschweregrades für jede Warnung und kann nicht individuell angepasst werden. Wenn Warnungen nicht triaged bleiben und Risiko Aktivitäten weiterhin für die Warnung anfallen, kann der Schweregrad des Risikos zunehmen. Risikoanalysten und Ermittler können den Warnungs risikoschweregrad verwenden, um Warnungen in Übereinstimmung mit den Risikorichtlinien und-Standards Ihrer Organisation zu selektieren.

Schweregrade des Warnungs Risikos sind:

- **Hoher Schweregrad**: die Aktivitäten und Indikatoren für die Warnung sind ein erhebliches Risiko. Die zugehörigen Risiko Aktivitäten sind schwerwiegend, repetitiv und beziehen sich stark auf andere wichtige Risikofaktoren.
- **Mittlerer Schweregrad**: die Aktivitäten und Indikatoren für die Warnung sind ein moderates Risiko. Die damit verbundenen Risikoaktivitäten sind moderat, häufig und weisen eine gewisse Korrelation zu anderen Risikofaktoren auf.
- **Niedriger Schweregrad**: die Aktivitäten und Indikatoren für die Warnung sind ein geringfügiger Risiko. Die zugeordneten Risiko Aktivitäten sind geringfügig, seltener und beziehen sich nicht auf andere wichtige Risikofaktoren.

## <a name="filter-alerts"></a>Filtern von Warnungen

Je nach Anzahl und Art der aktiven Verwaltungsrichtlinien für Insider-Risiken in Ihrem Unternehmen kann die Überprüfung einer großen Warteschlange von Warnungen eine Herausforderung darstellen. Die Verwendung von Warnungs filtern kann Analysten und Ermittlern dabei helfen, Warnungen nach verschiedenen Attributen zu sortieren. Um Warnungen im **Alerts-Dashboard**zu filtern, wählen Sie das **Filter** -Steuerelement aus. Sie können Benachrichtigungen nach einem oder mehreren Attributen filtern:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen sind *Bestätigt*, *Abgelehnt*, *Überprüfung erforderlich* und *Behoben*.
- **Schweregrad**: Wählen Sie einen oder mehrere Warnungs Risikoschwere Grade aus, um die Warnungsliste zu filtern. Die Optionen sind *Hoch*, *Moderat* und *Niedrig*.
- **Erkannte Zeit**: Wählen Sie das Start-und Enddatum für die Erstellung der Warnung aus.
- **Richtlinie**: Wählen Sie eine oder mehrere Richtlinien aus, um die Warnungen zu filtern, die von den ausgewählten Richtlinien generiert wurden.

## <a name="search-alerts"></a>Suchbenachrichtigungen

Um den Warnungsnamen nach einem bestimmten Wort zu durchsuchen, wählen Sie das Steuerelement **Suchen** und geben Sie das zu suchende Wort ein. In den Suchergebnissen wird jede Richtlinienwarnung angezeigt, die das in der Suche definierte Wort enthält.

## <a name="triage-alerts"></a>Selektieren von Warnungen

Führen Sie die folgenden Schritte aus, um eine Insider Risiko Warnung zu selektieren:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Benachrichtigungen** aus.
2. Wählen Sie im **Alerts-Dashboard**die Warnung aus, die Sie selektieren möchten.
3. Im **Detailbereich Benachrichtigungen**können Sie die folgenden Registerkarten überprüfen und die Warnung selektieren:
    - **Übersicht**: Diese Registerkarte enthält allgemeine Informationen zur Warnung und ermöglicht es Ihnen, die Warnung zu bestätigen und einen neuen Fall zu erstellen, oder Sie können die Warnung schließen.
        - **Status**: der Status der Warnung
        - **Erkannte Zeit**: die Zeitdauer seit der Benachrichtigung generiert wurde.
        - **Richtlinien Übereinstimmungen**: die Richtlinien, die die Warnung generiert haben, werden aufgelistet. Jede Richtlinie wird als Link zu den Richtliniendetails aufgeführt.
        - **Schwere**Grad: der aktuelle Schweregrad des Warnungs Risikos, aufgeführt als *hoch*, *Mittel*oder *niedrig*. Der Schweregrad kann im Laufe der Zeit zunehmen oder sich verkürzen, wenn die Warnung nicht mit dem Alter abläuft.
        - **Fall**: Wenn bestätigt, wird der aus der Warnung generierte Fall aufgeführt. Für neue Warnungen wird im Feld **Fall** *keine*angezeigt.
    - **Benutzeraktivität**: auf dieser Registerkarte wird der Aktivitätsverlauf für den Benutzer angezeigt, der der Warnung zugeordnet ist. Dieser Verlauf enthält andere Warnungen und Aktivitäten im Zusammenhang mit Risikoindikatoren, die in der Vorlage definiert sind, die der Richtlinie für diese Warnung zugewiesen ist. In dieser Vorgehensweise können Risikoanalysten und Ermittler in jedem Risikoverhalten der Vergangenheit für den Mitarbeiter als Teil des Triage-Prozesses berücksichtigt werden.
    - **Benutzerprofil**: auf dieser Registerkarte werden die allgemeinen Informationen zu dem Mitarbeiter angezeigt, der der Warnung zugewiesen ist. Wenn die Anonymisierung aktiviert ist, werden der Benutzername, die e-Mail-Adresse, der Alias und die Organisationsfelder anonymisiert.
    - **Case bestätigen und erstellen**: auf allen Registerkarten sichtbar, verwenden Sie diese Schaltfläche, um eine neue Groß-/Kleinschreibung zu bestätigen und zu erstellen. Durch diese Aktion wird der Warnungsstatus automatisch in " *bestätigt*" geändert.
    - **Warnung ablehnen**: auf allen Registerkarten sichtbar, verwenden Sie diese Schaltfläche, um die Warnung zu schließen. Durch diese Aktion wird der Warnungsstatus in *aufgelöst*geändert.

## <a name="create-a-case-for-an-alert"></a>Erstellen einer Anfrage für eine Warnung

Wenn die Warnung überprüft und die Funktion "neu" angezeigt wird, können Sie einen neuen Fall erstellen, um die Risiko Aktivität weiter zu untersuchen. Führen Sie die folgenden Schritte aus, um einen Fall für eine Warnung zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Benachrichtigungen** aus.
2. Wählen Sie im **Alerts-Dashboard**die Warnung aus, die Sie bestätigen möchten, und erstellen Sie eine neue Groß-/Kleinschreibung für.
3. Wählen Sie im **Bereich Benachrichtigungsdetails**die Option **Case bestätigen und erstellen**aus.
4. Geben Sie im Dialogfeld **Warnung bestätigen und Insider Risiko erstellen** einen Namen für den Fall ein, wählen Sie die Benutzer aus, die als Mitwirkende hinzugefügt werden sollen, und fügen Sie gegebenenfalls Kommentare hinzu. Kommentare werden dem Fall automatisch als Fall Hinweis hinzugefügt.
5. Wählen Sie **Case erstellen** aus, um einen neuen Fall zu erstellen, oder wählen Sie **Abbrechen** aus, um das Dialogfeld zu schließen, ohne eine Anfrage zu erstellen.
