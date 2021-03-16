---
title: Warnungen zum Risikomanagement von Insidern
description: Erfahren Sie mehr über Insider-Risikomanagementwarnungen in Microsoft 365
keywords: Microsoft 365, Insiderrisiko, Risikomanagement, Compliance
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
ms.openlocfilehash: 2a21dfead9b1f1ba2f05fc7629ce4fcda9991017
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819970"
---
# <a name="insider-risk-management-alerts"></a>Warnungen zum Risikomanagement von Insidern

Warnungen zum Insider-Risikomanagement werden automatisch durch Risikoindikatoren generiert, die in den Richtlinien zum Insider-Risikomanagement definiert sind. Diese Warnungen geben Compliance-Analysten und -Ermittlern einen umfassenden Überblick über den aktuellen Risikostatus und ermöglichen es Ihrem Unternehmen, eine Einstufung vorzunehmen und Maßnahmen für entdeckte Risiken zu ergreifen. Standardmäßig generieren Richtlinien eine bestimmte Menge von Warnungen mit niedrigem, [](insider-risk-management-settings.md#alert-volume) mittlerem und hohem Schweregrad, Sie können jedoch das Benachrichtigungsvolumen entsprechend Ihren Anforderungen erhöhen oder verringern. Darüber hinaus können Sie den Warnungsschwellenwert für [Richtlinienindikatoren](insider-risk-management-settings.md#indicator-level-settings-preview) beim Erstellen einer neuen Richtlinie mit dem Richtlinienassistenten konfigurieren.

## <a name="alert-dashboard"></a>Dashboard "Warnung"

Mit dem Dashboard für **Insiderrisiken können** Sie Warnungen anzeigen und reagieren, die durch Insiderrisikorichtlinien generiert werden. Jedes Berichts-Widget zeigt Informationen für die letzten 30 Tage an.

- **Gesamtwarnungen, die überprüft werden müssen:** Die Gesamtanzahl der Warnungen, die überprüft und geschlüsselt werden müssen, werden aufgelistet, einschließlich einer Aufschlüsselung nach Warnungsschweregrad.
- Warnungen in den letzten **30** Tagen öffnen: Die Gesamtzahl der von richtlinien erstellten Warnungen entspricht den letzten 30 Tagen, sortiert nach hohen, mittleren und niedrigen Schweregraden.
- **Durchschnittliche Zeit zum Beheben von Warnungen**: Eine Zusammenfassung der nützlichen Warnungsstatistiken:
    - Durchschnittliche Zeit zur Behebung von Warnungen höheren Schweregrades, angegeben in Stunden, Tagen oder Monaten.
    - Durchschnittliche Zeit bis zur Behebung von Warnungen mittleren Schweregrades, angegeben in Stunden, Tagen oder Monaten.
    - Durchschnittliche Zeit bis zur Behebung von Warnungen niedrigen Schweregrades, angegeben in Stunden, Tagen oder Monaten.

![Benachrichtigungsdashboard für Insider-Risikomanagement](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>Bei der Verwaltung von Insider-Risiken wird eine integrierte Warnungsdrosselung verwendet, um Ihre Erfahrungen bei der Risikoermittlung und -prüfung zu schützen und zu optimieren. Diese Drosselung schützt vor Problemen, die zu einer Überlastung der Richtlinienwarnungen führen könnten, wie z. B. falsch konfigurierte Datenkonnektoren oder DLP-Richtlinien. Infolgedessen kann es zu einer Verzögerung bei der Anzeige neuer Warnungen für einen Benutzer kommen.

## <a name="alert-status-and-severity"></a>Warnungsstatus und Schweregrad

Sie können Warnungen in einen der folgenden Status 3dnen:

- **Bestätigt**: Eine Benachrichtigung bestätigt und einem neuen oder vorhandenen Fall zugewiesen.
- **Dismissed**: Eine Warnung, die im Triageprozess als gutartig zurückgewiesen wurde.
- **Überprüfung der Anforderungen:** Eine neue Warnung, bei der noch keine Dreieraktionen ergriffen wurden.
- **Resolved**: Eine Warnung, die Teil eines geschlossenen und aufgelösten Falls ist.

Warnungsrisikowerte werden automatisch aus mehreren Risikoaktivitätsindikatoren berechnet. Diese Indikatoren umfassen die Art der Risikoaktivität, die Anzahl und Häufigkeit des Aktivitätsvorkommens, den Verlauf der Benutzerrisikoaktivität und das Hinzuzahlen von Aktivitätsrisiken, die die Schwere der Aktivität erhöhen können. Die Risikoeinstufung der Warnung bestimmt die programmatische Zuweisung eines Risikoschweregrades für jede Warnung und kann nicht individuell angepasst werden. Wenn Warnungen nicht ausgelöst werden und Risikoaktivitäten weiterhin für die Warnung anfallen, kann der Risikoschweregrad steigen. Risikoanalysten und Ermittler können den Schweregrad des Warnungsrisikos verwenden, um Warnungen in Übereinstimmung mit den Risikorichtlinien und Standards Ihrer Organisation zu verdingen.

Schweregrade des Warnungsrisikos sind:

- **Hoher Schweregrad:** Die Aktivitäten und Indikatoren für die Warnung stellen ein erhebliches Risiko dar. Die damit verbundenen Risikoaktivitäten sind schwerwiegend, wiederholend und konzentrieren sich stark auf andere wichtige Risikofaktoren.
- **Mittlerer Schweregrad:** Die Aktivitäten und Indikatoren für die Warnung stellen ein moderates Risiko dar. Die damit verbundenen Risikoaktivitäten sind moderat, häufig und weisen eine gewisse Korrelation zu anderen Risikofaktoren auf.
- **Niedriger Schweregrad:** Die Aktivitäten und Indikatoren für die Warnung stellen ein geringfügiges Risiko dar. Die zugeordneten Risikoaktivitäten sind geringfügiger, seltener und konzentrieren sich nicht auf andere wichtige Risikofaktoren.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtern von Warnungen im Warnungsdashboard

Je nach Anzahl und Art der aktiven Verwaltungsrichtlinien für Insider-Risiken in Ihrem Unternehmen kann die Überprüfung einer großen Warteschlange von Warnungen eine Herausforderung darstellen. Mithilfe von Warnungsfiltern können Analysten und Ermittler Warnungen nach mehreren Attributen sortieren. Wählen Sie zum Filtern von Warnungen **im Benachrichtigungsdashboard** das **Steuerelement Filter** aus. Sie können Warnungen nach einem oder mehreren Attributen filtern:

- **Status**: Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen sind *Bestätigt*, *Abgelehnt*, *Überprüfung erforderlich* und *Behoben*.
- **Schweregrad**: Wählen Sie einen oder mehrere Schweregrade des Warnungsrisikos aus, um die Warnungsliste zu filtern. Die Optionen sind *Hoch*, *Moderat* und *Niedrig*.
- **Erkannte Uhrzeit**: Wählen Sie das Start- und Enddatum für den Zeitpunkt der Warnungs erstellen aus.
- **Richtlinie**: Wählen Sie eine oder mehrere Richtlinien aus, um die von den ausgewählten Richtlinien generierten Warnungen zu filtern.

## <a name="search-alerts-on-the-alert-dashboard"></a>Suchwarnungen im Benachrichtigungsdashboard

Um den Warnungsnamen nach einem bestimmten Wort zu durchsuchen, wählen Sie das Steuerelement **Suchen** und geben Sie das zu suchende Wort ein. In den Suchergebnissen wird jede Richtlinienwarnung angezeigt, die das in der Suche definierte Wort enthält.

## <a name="triage-alerts"></a>Triagewarnungen

Führen Sie die folgenden Schritte aus, um eine Insiderrisikowarnung zu verdingen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Warnungen** aus.
2. Wählen Sie **im Benachrichtigungsdashboard** die Warnung aus, die Sie triagen möchten.
3. Im **Detailbereich Warnungen** können Sie die folgenden Registerkarten überprüfen und die Warnung triagen:
    - **Zusammenfassung**: Diese Registerkarte enthält allgemeine Informationen zur Warnung und ermöglicht Ihnen, die Warnung zu bestätigen und einen neuen Fall zu erstellen oder die Warnung zu schließen. Sie enthält den aktuellen Status für die Warnung und den Schweregrad des Warnungsrisikos, die als *Hoch,* *Mittel* oder *Niedrig aufgeführt sind.* Der Schweregrad kann im Laufe der Zeit zunehmen oder abnehmen, wenn die Warnung nicht triaged ist.
        - **Was passiert ist (Vorschau):** Zeigt während des Aktivitätsauswertungszeitraums die drei am meisten gefährdeten Aktivitäten und Richtlinien übereinstimmungen an, einschließlich der Art der Verletzung, die der Aktivität zugeordnet ist, und der Anzahl der Vorkommen.
        - **Benutzerdetails**: Zeigt allgemeine Informationen über den Benutzer an, der der Warnung zugewiesen ist. Wenn die Anonymisierung aktiviert ist, werden der Benutzername, die E-Mail-Adresse, der Alias und die Organisationsfelder anonymisiert.
        - **Warnungsdetails:** Enthält die Dauer seit dem Generierten der Warnung, die Richtlinien, die die Warnung generiert haben, werden aufgelistet, und der von der Warnung generierte Fall wird aufgelistet. Bei neuen Warnungen wird **im Feld Fall** Keine angezeigt.
        - **Erkannter Inhalt (Vorschau):** Enthält Inhalte, die den Risikoaktivitäten für die Warnung zugeordnet sind, und fasst Aktivitätsereignisse nach Schlüsselbereichen zusammen. Wenn Sie einen Aktivitätslink auswählen, wird der Aktivitäts-Explorer geöffnet und zusätzliche Details zur Aktivität angezeigt.
    - **Benutzeraktivität**: Auf dieser Registerkarte wird der Aktivitätsverlauf für den Benutzer angezeigt, der der Warnung zugeordnet ist. Dieser Verlauf enthält weitere Warnungen und Aktivitäten im Zusammenhang mit Risikoindikatoren, die in der Vorlage definiert sind, die der Richtlinie für diese Warnung zugewiesen ist. Dieser Verlauf ermöglicht Es Risikoanalysten und Ermittlern, jedes risikoante Verhalten der Vergangenheit für den Mitarbeiter im Rahmen des Triageprozesses zu beeinflussen.
    - **Aktionen**: Die folgenden Aktionen sind für jede Warnung verfügbar:
        - **Erweiterte Ansicht öffnen:** Öffnet das **Aktivitäts-Explorer-Dashboard.**
        - **Bestätigen und Erstellen von Fall**: Verwenden Sie diese Aktion, um einen neuen Fall für alle Warnungen zu bestätigen und zu erstellen, die einem Benutzer zugeordnet sind. Durch diese Aktion wird der Warnungsstatus automatisch in *Bestätigt geändert.*
        - **Warnung schließen:** Verwenden Sie diese Aktion, um die Warnung zu schließen. Durch diese Aktion wird der Warnungsstatus in *Resolved geändert.*

## <a name="activity-explorer-preview"></a>Aktivitäts-Explorer (Vorschau)

>[!NOTE]
>Der Aktivitäts-Explorer ist im Warnungsverwaltungsbereich für Benutzer mit auslösenden Ereignissen verfügbar, nachdem dieses Feature in Ihrer Organisation verfügbar ist.

Der Aktivitäts-Explorer stellt Risikoermittlern und Analysten ein umfassendes Analysetool zur Verfügung, das detaillierte Informationen zu Warnungen enthält. Mit dem Aktivitäts-Explorer können Prüfer schnell eine Zeitachse erkannter riskanter Aktivitäten überprüfen und alle Risikoaktivitäten identifizieren und filtern, die mit Warnungen verbunden sind. Wählen Sie zum Filtern von Warnungen im Aktivitäts-Explorer das Steuerelement Filter aus. Sie können Warnungen nach einem oder mehreren Attributen filtern, die im Detailbereich für die Warnung aufgeführt sind. Der Aktivitäts-Explorer unterstützt auch anpassbare Spalten, um Ermittlern und Analysten zu helfen, das Dashboard auf die für sie wichtigsten Informationen zu konzentrieren.

![Übersicht über insider risk management activity explorer](../media/insider-risk-activity-explorer.png)

Führen Sie die folgenden Schritte **aus,** um den Aktivitäts-Explorer zu verwenden:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **Insider Risk Management,** und wählen Sie die Registerkarte **Warnungen** aus.
2. Wählen Sie **im Benachrichtigungsdashboard** die Warnung aus, die Sie triagen möchten.
3. Wählen Sie **im Detailbereich Warnungen** die Option **Erweiterte Ansicht öffnen aus.**
4. Wählen Sie auf der Seite für die ausgewählte Warnung die Registerkarte **Aktivitäts-Explorer** aus.

Beim Überprüfen von Aktivitäten im Aktivitäts-Explorer können Ermittler und Analysten eine bestimmte Aktivität auswählen und den Aktivitätsdetailsebereich öffnen. Im Bereich werden detaillierte Informationen zu den Aktivitäten angezeigt, die Ermittler und Analysten während des Warnungstriageprozesses verwenden können. Die detaillierten Informationen können den Kontext für die Warnung bereitstellen und dabei helfen, den vollständigen Umfang der Risikoaktivität zu identifizieren, die die Warnung ausgelöst hat.

![Insider-Risikomanagement-Aktivitäts-Explorer-Details](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Erstellen eines Falls für eine Warnung

Wenn die Warnung überprüft und triaged wird, können Sie einen neuen Fall erstellen, um die Risikoaktivität weiter zu untersuchen. Führen Sie die folgenden Schritte aus, um einen Fall für eine Warnung zu erstellen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Warnungen** aus.
2. Wählen Sie **im Benachrichtigungsdashboard** die Warnung aus, die Sie bestätigen möchten, und erstellen Sie einen neuen Fall für.
3. Wählen Sie **im Detailbereich Benachrichtigungen** die Option **Aktionen**  >  **Warnungen bestätigen & Erstellen von Fall aus.**
4. Geben Sie im Dialogfeld **Benachrichtigung bestätigen** und Insiderrisikofall erstellen einen Namen für den Fall ein, wählen Sie Benutzer aus, die als Mitwirkende hinzugefügt werden, und fügen Sie kommentare hinzu, falls zutreffend. Kommentare werden dem Fall automatisch als Fallnotiz hinzugefügt.
5. Wählen **Sie Fall erstellen** aus, um einen neuen Fall zu erstellen, oder wählen Sie **Abbrechen** aus, um das Dialogfeld zu schließen, ohne einen Fall zu erstellen.

Nachdem der Fall erstellt wurde, können Ermittler und Analysten den Fall verwalten und entsprechend handeln. Weitere Informationen finden Sie im Artikel insider [risk management case.](insider-risk-management-cases.md)
