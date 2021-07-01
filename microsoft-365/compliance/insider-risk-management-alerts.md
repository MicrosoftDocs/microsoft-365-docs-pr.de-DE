---
title: Warnungen zum Insider-Risikomanagement
description: Erfahren Sie mehr über Warnungen zum Insider-Risikomanagement in Microsoft 365
keywords: Microsoft 365, Insider-Risiko, Risikomanagement, Compliance
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
ms.openlocfilehash: 0ee3fdf19552ee80737f6758e655d297228c469e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226551"
---
# <a name="insider-risk-management-alerts"></a>Warnungen zum Insider-Risikomanagement

Warnungen zum Insider-Risikomanagement werden automatisch durch Risikoindikatoren generiert, die in den Richtlinien zum Insider-Risikomanagement definiert sind. Diese Warnungen geben Compliance-Analysten und -Ermittlern einen umfassenden Überblick über den aktuellen Risikostatus und ermöglichen es Ihrem Unternehmen, eine Einstufung vorzunehmen und Maßnahmen für entdeckte Risiken zu ergreifen. Standardmäßig generieren Richtlinien eine bestimmte Anzahl von Warnungen mit geringem, mittlerem und hohem Schweregrad, Sie können das [Warnungsvolumen](insider-risk-management-settings.md#alert-volume) jedoch entsprechend Ihren Anforderungen erhöhen oder verringern. Darüber hinaus können Sie den [Warnungsschwellenwert für Richtlinienindikatoren](insider-risk-management-settings.md#indicator-level-settings-preview) konfigurieren, wenn Sie eine neue Richtlinie mit dem Richtlinien-Assistenten erstellen.

Sehen Sie sich das [Video "Triage Experience für Insider-Risikomanagement-Warnungen"](https://www.youtube.com/watch?v=KgmpxBLJLPI) an, um einen Überblick darüber zu erhalten, wie Warnungen Details, Kontext und verwandte Inhalte für riskante Aktivitäten bereitstellen und wie Sie Ihren Untersuchungsprozess effektiver gestalten können.

## <a name="alert-dashboard"></a>Dashboard "Warnung"

Mit dem Dashboard für **Insider-Risikowarnungen** können Sie Warnungen anzeigen und darauf reagieren, die von Insider-Risikorichtlinien generiert werden. Jedes Berichts-Widget zeigt Informationen für die letzten 30 Tage an.

- **Gesamtanzahl der Warnungen, die überprüft werden müssen:** Die Gesamtzahl der Warnungen, die überprüft und überprüft werden müssen, einschließlich einer Aufschlüsselung nach Warnungsschweregrad.
- **Offene Warnungen in den letzten 30 Tagen:** Die Gesamtzahl der Warnungen, die von Richtlinienübereinstimmungen in den letzten 30 Tagen erstellt wurden, sortiert nach hohen, mittleren und niedrigen Warnungsschweregraden.
- **Durchschnittliche Zeit zum Beheben von Warnungen:** Eine Zusammenfassung nützlicher Warnungsstatistiken:
  - Durchschnittliche Zeit zur Behebung von Warnungen höheren Schweregrades, angegeben in Stunden, Tagen oder Monaten.
  - Durchschnittliche Zeit bis zur Behebung von Warnungen mittleren Schweregrades, angegeben in Stunden, Tagen oder Monaten.
  - Durchschnittliche Zeit bis zur Behebung von Warnungen niedrigen Schweregrades, angegeben in Stunden, Tagen oder Monaten.

![Dashboard mit Warnungen zum Insider-Risikomanagement](../media/insider-risk-alerts-dashboard.png)

> [!NOTE]
> Bei der Verwaltung von Insider-Risiken wird eine integrierte Warnungsdrosselung verwendet, um Ihre Erfahrungen bei der Risikoermittlung und -prüfung zu schützen und zu optimieren. Diese Drosselung schützt vor Problemen, die zu einer Überlastung der Richtlinienwarnungen führen könnten, wie z. B. falsch konfigurierte Datenkonnektoren oder DLP-Richtlinien. Infolgedessen kann es zu einer Verzögerung bei der Anzeige neuer Warnungen für einen Benutzer kommen.

## <a name="alert-status-and-severity"></a>Warnungsstatus und Schweregrad

Sie können Warnungen in einen der folgenden Status überprüfen:

- **Bestätigt:** Eine Warnung, die bestätigt und einem neuen oder vorhandenen Fall zugewiesen wurde.
- **Geschlossen:** Eine Warnung, die im Triageprozess als gutartig geschlossen wird.
- **Muss überprüft** werden: Eine neue Warnung, bei der noch keine Triageaktionen ausgeführt wurden.
- **Behoben:** Eine Warnung, die Teil eines geschlossenen und aufgelösten Falls ist.

Warnungsrisikobewertungen werden automatisch aus mehreren Risikoaktivitätsindikatoren berechnet. Diese Indikatoren umfassen die Art der Risikoaktivität, die Anzahl und Häufigkeit des Aktivitätsvorkommens, den Verlauf der Benutzerrisikoaktivität und das Hinzufügen von Aktivitätsrisiken, die den Schweregrad der Aktivität erhöhen können. Die Risikoeinstufung der Warnung bestimmt die programmatische Zuweisung eines Risikoschweregrades für jede Warnung und kann nicht individuell angepasst werden. Wenn Warnungen unerreicht bleiben und weiterhin Risikoaktivitäten für die Warnung anfallen, kann der Risikoschweregrad zunehmen. Risikoanalysten und Ermittler können den Risikoschweregrad der Warnung verwenden, um Warnungen in Übereinstimmung mit den Risikorichtlinien und Standards Ihrer Organisation zu selektieren.

Die Schweregrade der Warnungsrisiken sind:

- **Hoher Schweregrad:** Die Aktivitäten und Indikatoren für die Warnung stellen ein erhebliches Risiko dar. Die damit verbundenen Risikoaktivitäten sind schwerwiegend, wiederholen sich wiederholt und hängen stark mit anderen wichtigen Risikofaktoren ab.
- **Mittlerer Schweregrad:** Die Aktivitäten und Indikatoren für die Warnung stellen ein moderates Risiko dar. Die damit verbundenen Risikoaktivitäten sind moderat, häufig und weisen eine gewisse Korrelation zu anderen Risikofaktoren auf.
- **Niedriger Schweregrad:** Die Aktivitäten und Indikatoren für die Warnung stellen ein geringes Risiko dar. Die damit verbundenen Risikoaktivitäten sind geringfügig, seltener und hängen nicht mit anderen wichtigen Risikofaktoren ab.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtern von Warnungen im Warnungsdashboard

Je nach Anzahl und Art der aktiven Verwaltungsrichtlinien für Insider-Risiken in Ihrem Unternehmen kann die Überprüfung einer großen Warteschlange von Warnungen eine Herausforderung darstellen. Die Verwendung von Warnungsfiltern kann Analysten und Ermittlern helfen, Warnungen nach mehreren Attributen zu sortieren. Um Warnungen im **Warnungsdashboard** zu filtern, wählen Sie das **Filtersteuerelement** aus. Sie können Warnungen nach einem oder mehreren Attributen filtern:

- **Status:** Wählen Sie einen oder mehrere Statuswerte aus, um die Warnungsliste zu filtern. Die Optionen sind *Bestätigt*, *Abgelehnt*, *Überprüfung erforderlich* und *Behoben*.
- **Schweregrad:** Wählen Sie eine oder mehrere Warnungsrisikoschweregrade aus, um die Warnungsliste zu filtern. Die Optionen sind *Hoch*, *Moderat* und *Niedrig*.
- **Erkannter Zeitpunkt:** Wählen Sie das Start- und Enddatum für den Zeitpunkt aus, zu dem die Warnung erstellt wurde.
- **Richtlinie:** Wählen Sie eine oder mehrere Richtlinien aus, um die von den ausgewählten Richtlinien generierten Warnungen zu filtern.

## <a name="search-alerts-on-the-alert-dashboard"></a>Suchen von Warnungen im Warnungsdashboard

Um den Warnungsnamen nach einem bestimmten Wort zu durchsuchen, wählen Sie das Steuerelement **Suchen** und geben Sie das zu suchende Wort ein. In den Suchergebnissen wird jede Richtlinienwarnung angezeigt, die das in der Suche definierte Wort enthält.

## <a name="triage-alerts"></a>Triage-Warnungen

Führen Sie die folgenden Schritte aus, um eine Insider-Risikowarnung zu triagen:

1. Wechseln [Sie im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zum **Insider-Risikomanagement,** und wählen Sie die Registerkarte **"Warnungen" aus.**
2. Wählen Sie im **Warnungsdashboard** die Warnung aus, die Sie selektieren möchten.
3. Im **Detailbereich "Warnungen"** können Sie die folgenden Registerkarten überprüfen und die Warnung triagen:
    - **Zusammenfassung:** Diese Registerkarte enthält allgemeine Informationen zu der Warnung und ermöglicht es Ihnen, die Warnung zu bestätigen und einen neuen Fall zu erstellen oder die Warnung zu schließen. Es enthält den aktuellen Status für die Warnung und den Schweregrad des Warnungsrisikos, aufgelistet als *Hoch,* *Mittel* oder *Niedrig.* Der Schweregrad kann sich im Laufe der Zeit erhöhen oder verringern, wenn die Warnung nicht triaged ist.
        - **Was passiert ist (Vorschau):** Zeigt die drei wichtigsten Risikoaktivitäten und Richtlinienübersprechungen während des Zeitraums der Aktivitätsauswertung an, einschließlich der Art des mit der Aktivität verbundenen Verstoßes und der Anzahl der Vorkommen.
        - **Benutzerdetails:** Zeigt allgemeine Informationen über den Benutzer an, der der Warnung zugewiesen ist. Wenn die Anonymisierung aktiviert ist, werden der Benutzername, die E-Mail-Adresse, der Alias und die Organisationsfelder anonymisiert.
        - **Warnungsdetails:** Enthält die Zeitspanne seit der Generierung der Warnung, die Richtlinien, die die Warnung generiert haben, und den fall, der aus der Warnung generiert wurde, wird aufgelistet. Bei neuen Warnungen zeigt das **Feld "Groß-/Kleinschreibung"** "None" an.
        - **Erkannter Inhalt (Vorschau):** Enthält Inhalte, die mit den Risikoaktivitäten für die Warnung verknüpft sind, und fasst Aktivitätsereignisse nach Schlüsselbereichen zusammen. Wenn Sie einen Aktivitätslink auswählen, wird der Aktivitäten-Explorer geöffnet, und es werden weitere Details zur Aktivität angezeigt.
    - **Benutzeraktivität:** Auf dieser Registerkarte wird der Aktivitätsverlauf für den Benutzer angezeigt, der der Warnung zugeordnet ist. Dieser Verlauf enthält andere Warnungen und Aktivitäten im Zusammenhang mit Risikoindikatoren, die in der Vorlage definiert sind, die der Richtlinie für diese Warnung zugewiesen ist. Dieser Verlauf ermöglicht es Risikoanalysten und Ermittlern, jedes riskante Verhalten der Vergangenheit für den Mitarbeiter im Rahmen des Triageprozesses zu berücksichtigen.
    - **Aktionen:** Die folgenden Aktionen sind für jede Warnung verfügbar:
        - **Erweiterte Ansicht öffnen:** Öffnet das Dashboard des **Aktivitäts-Explorers.**
        - **Bestätigen und Erstellen eines Falls:** Verwenden Sie diese Aktion, um einen neuen Fall für alle Warnungen zu bestätigen und zu erstellen, die einem Benutzer zugeordnet sind. Mit dieser Aktion wird der Warnungsstatus automatisch in *"Bestätigt"* geändert.
        - **Warnung schließen:** Verwenden Sie diese Aktion, um die Warnung zu schließen. Mit dieser Aktion wird der Warnungsstatus in *"Aufgelöst"* geändert.

## <a name="activity-explorer-preview"></a>Aktivitäten-Explorer (Vorschau)

> [!NOTE]
> Der Aktivitäten-Explorer ist im Warnungsverwaltungsbereich für Benutzer mit auslösenden Ereignissen verfügbar, nachdem dieses Feature in Ihrer Organisation verfügbar ist.

Der Aktivitäten-Explorer bietet Risikoermittlern und Analysten ein umfassendes Analysetool, das detaillierte Informationen zu Warnungen bereitstellt. Mit dem Aktivitäten-Explorer können Prüfer schnell eine Zeitachse erkannter riskanter Aktivitäten überprüfen und alle Risikoaktivitäten im Zusammenhang mit Warnungen identifizieren und filtern. Um Warnungen im Aktivitäten-Explorer zu filtern, wählen Sie das Filtersteuerelement aus. Sie können Warnungen nach einem oder mehreren Attributen filtern, die im Detailbereich für die Warnung aufgeführt sind. Der Aktivitäten-Explorer unterstützt auch anpassbare Spalten, damit Ermittler und Analysten das Dashboard auf die für sie wichtigsten Informationen konzentrieren können.

![Übersicht über den Aktivitäten-Explorer für Insider-Risikomanagement](../media/insider-risk-activity-explorer.png)

Führen Sie die folgenden Schritte aus, um den **Aktivitäten-Explorer** zu verwenden:

1. Wechseln Sie im Microsoft 365 Compliance Center zum **Insider-Risikomanagement,** und wählen Sie die Registerkarte **"Warnungen" aus.**
2. Wählen Sie im **Warnungsdashboard** die Warnung aus, die Sie selektieren möchten.
3. Wählen Sie im **Detailbereich "Warnungen"** die **Option "Erweiterte Ansicht öffnen"** aus.
4. Wählen Sie auf der Seite für die ausgewählte Warnung die Registerkarte **"Aktivitäten-Explorer"** aus.

Beim Überprüfen von Aktivitäten im Aktivitäten-Explorer können Ermittler und Analysten eine bestimmte Aktivität auswählen und den Aktivitätsdetailsbereich öffnen. Im Bereich werden detaillierte Informationen zu den Aktivitäten angezeigt, die Ermittler und Analysten während der Benachrichtigungstriage verwenden können. Die detaillierten Informationen können den Kontext für die Warnung bereitstellen und dabei helfen, den vollständigen Umfang der Risikoaktivität zu identifizieren, die die Warnung ausgelöst hat.

![Details zum Aktivitäten-Explorer für Insider-Risikomanagement](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Erstellen eines Falls für eine Warnung

Wenn die Warnung überprüft und triaget wird, können Sie einen neuen Fall erstellen, um die Risikoaktivität weiter zu untersuchen. Führen Sie die folgenden Schritte aus, um einen Fall für eine Warnung zu erstellen:

1. Wechseln [Sie im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zum **Insider-Risikomanagement,** und wählen Sie die Registerkarte **"Warnungen" aus.**
2. Wählen Sie im **Warnungsdashboard** die Warnung aus, die Sie bestätigen möchten, und erstellen Sie einen neuen Fall für.
3. Wählen Sie im **Detailbereich "Warnungen"** die Option **"Aktionen**  >  **bestätigen" aus, & Groß-/Kleinschreibung erstellen.**
4. Geben Sie im Dialogfeld **"Warnung bestätigen und Insider-Risikofall erstellen"** einen Namen für den Fall ein, wählen Sie Benutzer aus, die als Mitwirkende hinzugefügt werden sollen, und fügen Sie ggf. Kommentare hinzu. Kommentare werden dem Fall automatisch als Fallnotiz hinzugefügt.
5. Wählen Sie **"Groß-/Kleinschreibung erstellen"** aus, um einen neuen Fall zu erstellen, oder wählen Sie **"Abbrechen"** aus, um das Dialogfeld zu schließen, ohne einen Fall zu erstellen.

Nachdem der Fall erstellt wurde, können Ermittler und Analysten den Fall verwalten und darauf reagieren. Weitere Informationen finden Sie im Fallartikel zum [Insider-Risikomanagement.](insider-risk-management-cases.md)
