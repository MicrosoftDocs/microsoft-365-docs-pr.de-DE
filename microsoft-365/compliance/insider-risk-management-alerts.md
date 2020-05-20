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
ms.openlocfilehash: 0618eb6b68f5753ea6af2469e3487eabfe566450
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292483"
---
# <a name="insider-risk-management-alerts"></a>Warnungen beim Insider Risikomanagement

Alerts für Insider Risikomanagement werden automatisch durch Risikoindikatoren generiert, die in Richtlinien für das Insider Risikomanagement definiert sind. Diese Warnungen bieten Compliance-Analysten und Ermittlern eine Übersicht über den aktuellen Risikostatus und ermöglichen Ihrer Organisation das selektieren und Ausführen von Aktionen für entdeckte Risiken. Standardmäßig generieren Richtlinien eine bestimmte Menge an Warnungen mit niedrigem, mittlerem und hohem Schweregrad, aber Sie können [das Warnungs Volumen entsprechend Ihren Anforderungen erweitern oder verringern](insider-risk-management-policies.md#alert-volume) .

## <a name="alert-dashboard"></a>Benachrichtigungs Dashboard

Das Alert- **Dashboard** für Insider Risiken ermöglicht Ihnen das Anzeigen und Ausführen von Warnungen, die von Insider Risikorichtlinien generiert werden. Jedes Berichts-Widget zeigt Informationen für die letzten 30 Tage an.

- **Zu über**prüfende Warnungen: die Gesamtzahl der Warnungen, die Überprüfung und Selektierung erforderlich sind, wird aufgeführt, einschließlich einer Aufteilung nach Warnungsschweregrad.
- **Warnungen in den letzten 30 Tagen öffnen**: die Gesamtzahl der Warnungen, die von Richtlinien Übereinstimmungen in den letzten 30 Tagen erstellt wurden, sortiert nach hoch-, Mittel-und niedrigem Warnungsschweregrad.
- **Durchschnittliche Zeit zum Auflösen von Warnungen**: eine Zusammenfassung der nützlichen Warnungs Statistiken:
    - Durchschnittliche Zeit zum Auflösen von Warnungen mit hohem Schweregrad, aufgeführt in Stunden, Tagen oder Monaten.
    - Durchschnittliche Zeit zum Auflösen mittlerer Dringlichkeits Warnungen, aufgeführt in Stunden, Tagen oder Monaten.
    - Durchschnittliche Zeit zum Beheben von Warnungen mit niedrigem Schweregrad, aufgeführt in Stunden, Tagen oder Monaten.

![Alert-Dashboard für Insider-Risikomanagement](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>Das Insider-Risikomanagement verwendet die integrierte Warnungs Drosselung, um Ihre Risiko Ermittlungen zu schützen und zu optimieren und die Erfahrung zu überprüfen. Diese Einschränkung schützt vor Problemen, die zu einer Überlastung von Richtlinienwarnungen führen können, wie beispielsweise falsch konfigurierte Daten-Konnektoren oder DLP-Richtlinien. Dadurch kann es zu Verzögerungen beim Anzeigen neuer Benachrichtigungen für einen Benutzer kommen.

## <a name="alert-status-and-severity"></a>Warnungsstatus und-Schweregrad

Sie können Warnungen in einem der folgenden Status selektieren:

- **Bestätigt**: eine Warnung wurde bestätigt und einem neuen oder vorhandenen Fall zugewiesen.
- **Entlassen**: eine Warnung wurde beim Triage-Prozess als gutartig zurückgewiesen.
- **Needs Review**: eine neue Warnung, bei der noch keine Triage-Aktionen durchgeführt wurden.
- **Aufgelöst**: eine Warnung, die Teil eines geschlossenen und aufgelösten Falls ist.

Warnungs Risikobewertungen werden automatisch aus mehreren Aktivitäts Attributen für Risiken berechnet. Diese Attribute umfassen den Typ der Risiko Aktivität, die Anzahl und Häufigkeit des Aktivitätsereignisses, den Verlauf der Benutzer Risiko Aktivität und das Hinzufügen von Aktivitäts Risiken, die die Schwere der Aktivität erhöhen können. Das Warnungs Risiko-Score steuert die programmgesteuerte Zuweisung eines Risikoschwere Grads für jede Warnung und kann nicht angepasst werden. Wenn Warnungen nicht triaged bleiben und Risiko Aktivitäten weiterhin für die Warnung anfallen, kann der Schweregrad des Risikos zunehmen. Risikoanalysten und Ermittler können den Warnungs risikoschweregrad verwenden, um Warnungen in Übereinstimmung mit den Risikorichtlinien und-Standards Ihrer Organisation zu selektieren.

Der Schweregrad des Warnungs Risikos lautet:

- **Hoher Schweregrad**: die Aktivität und die Indikatoren für die Warnung sind ein erhebliches Risiko. Die zugehörigen Risiko Aktivitäten sind schwerwiegend, repetitiv und beziehen sich stark auf andere wichtige Risikofaktoren.
- **Mittlerer Schweregrad**: die Aktivität und die Indikatoren für die Warnung sind ein moderates Risiko. Die zugeordneten Risiko Aktivitäten sind moderat, häufig und weisen eine gewisse Korrelation mit anderen Risikofaktoren auf.
- **Niedriger Schweregrad**: die Aktivität und die Indikatoren für die Warnung sind ein geringfügiger Risiko. Die zugeordneten Risiko Aktivitäten sind geringfügig, seltener und beziehen sich nicht auf andere wichtige Risikofaktoren.

## <a name="filter-alerts"></a>Filtern von Warnungen

Je nach Anzahl und Typ der aktiven Insider Risiko-Verwaltungsrichtlinien in Ihrer Organisation kann die Überprüfung einer großen Warnungs Warteschlange eine Herausforderung darstellen. Die Verwendung von Warnungs filtern kann Analysten und Ermittlern dabei helfen, Warnungen nach verschiedenen Attributen zu sortieren. Um Warnungen im Alerts-Dashboard zu filtern, wählen Sie das **Filter** -Steuerelement aus. Sie können Benachrichtigungen nach einem oder mehreren Attributen filtern:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen werden *bestätigt*, *geschlossen*, *überprüft*und *aufgelöst*.
- **Schweregrad**: Wählen Sie einen oder mehrere Warnungs Risikoschwere Grade aus, um die Warnungsliste zu filtern. Die Optionen sind *hoch*, *Mittel*und *niedrig*.
- **Erkannte Zeit**: Wählen Sie das Start-und Enddatum für die Erstellung der Warnung aus.
- **Richtlinie**: Wählen Sie eine oder mehrere Richtlinien aus, um die Warnungen zu filtern, die von den ausgewählten Richtlinien generiert wurden.

## <a name="search-alerts"></a>Suchbenachrichtigungen

Wenn Sie den Warnungsnamen nach einem bestimmten Wort durchsuchen möchten, wählen Sie das **Such** Steuerelement aus, und geben Sie das zu durchsuchende Wort ein. In den Suchergebnissen werden alle Richtlinienwarnungen angezeigt, die das in der Suche definierte Wort enthalten.

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
        - **Fall**: Wenn bestätigt, wird der aus der Warnung generierte Fall aufgeführt. Für neue Warnungen weist das Feld Case einen *None* -Wert auf.
    - **Benutzeraktivität**: auf dieser Registerkarte wird der Aktivitätsverlauf für den Benutzer angezeigt, der der Warnung zugeordnet ist. Dieser Verlauf umfasst andere Warnungen und Ereignis Aktivitäten im Zusammenhang mit Risikoindikatoren, die in der Vorlage definiert sind, die der Richtlinie für diese Warnung zugewiesen ist. In dieser Vorgehensweise können Risikoanalysten und Ermittler in jedem Risikoverhalten der Vergangenheit für den Mitarbeiter als Teil des Triage-Prozesses berücksichtigt werden.
    - **Benutzerprofil**: auf dieser Registerkarte werden die allgemeinen Informationen zu dem Mitarbeiter angezeigt, der der Warnung zugewiesen ist.
    - **Case bestätigen und erstellen**: auf allen Registerkarten sichtbar, verwenden Sie diese Schaltfläche, um eine neue Groß-/Kleinschreibung zu bestätigen und zu erstellen. Dadurch wird der Warnungsstatus automatisch in " *bestätigt*" geändert.
    - **Abtun**: auf allen Registerkarten sichtbar, verwenden Sie diese Schaltfläche, um die Warnung zu schließen. Dadurch wird der Warnungsstatus in *aufgelöst*geändert.

## <a name="create-a-case-for-an-alert"></a>Erstellen einer Anfrage für eine Warnung

Nachdem Sie eine Warnung überprüft und mit einem neuen Szenario erstellt haben, können Sie eine neue Anfrage erstellen, um die Risiko Aktivität weiter zu untersuchen. Führen Sie die folgenden Schritte aus, um einen Fall für eine Warnung zu erstellen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Benachrichtigungen** aus.
2. Wählen Sie im **Alerts-Dashboard**die Warnung aus, die Sie bestätigen möchten, und erstellen Sie eine neue Groß-/Kleinschreibung für.
3. Wählen Sie im **Bereich Benachrichtigungsdetails**die Option **Case bestätigen und erstellen**aus.
4. Geben Sie im Dialogfeld **Warnung bestätigen und Insider Risiko erstellen** einen Namen für den Fall ein, wählen Sie die Benutzer aus, die als Mitwirkende hinzugefügt werden sollen, und fügen Sie gegebenenfalls Kommentare hinzu. Kommentare werden dem Fall automatisch als Fall Hinweis hinzugefügt.
5. Wählen Sie **Case erstellen** aus, um einen neuen Fall zu erstellen, oder wählen Sie **Abbrechen** aus, um das Dialogfeld zu schließen, ohne eine Anfrage zu erstellen.
