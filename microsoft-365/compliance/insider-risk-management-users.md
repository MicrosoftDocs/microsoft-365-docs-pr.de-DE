---
title: Insider-Risikomanagement-Benutzerdashboard
description: Erfahren Sie mehr über das Insider-Risikomanagement-Benutzerdashboard in Microsoft 365
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
ms.openlocfilehash: e59fb8a32275a2ef7c4865e93400b97ad5560df5
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819999"
---
# <a name="insider-risk-management-users-dashboard"></a>Insider-Risikomanagement-Benutzerdashboard

Das **Benutzerdashboard** ist ein wichtiges Tool im Insider-Risikomanagement-Workflow und hilft Ermittlern und Analysten, ein vollständigeres Verständnis der Risikoaktivitäten zu haben. Dieses Dashboard bietet Ansichten und Verwaltungsfeatures, um administrative Anforderungen zwischen der Erstellung von Insider-Risikomanagementrichtlinien und der Verwaltung von Insider-Risikomanagementfällen zu erfüllen.

Nachdem Benutzer zu Insider-Risikomanagementrichtlinien hinzugefügt wurden, werden in Hintergrundprozessen automatisch Benutzeraktivitäten für das Auslösen [von Indikatoren ausgewertet.](insider-risk-management-settings.md#indicators) Nachdem Auslösende Indikatoren vorhanden sind, werden Benutzeraktivitäten Risikoergebnisse zugewiesen. Einige dieser Aktivitäten können zu einer Warnung vor Insiderrisiken führen, aber einige Aktivitäten erfüllen möglicherweise nicht die Mindestrisikopunktzahl, und es wird keine Warnung für Insiderrisiken erstellt. Mit **dem Benutzerdashboard** können Sie Benutzer mit diesen Arten von Indikatoren und Risikoergebnissen sowie Benutzer mit aktiven Insiderrisikowarnungen anzeigen.

Erfahren Sie mehr darüber, wie das Benutzerdashboard Benutzer in den folgenden Szenarien anzeigt:

- Benutzer mit aktiven Insiderrisikorichtlinienwarnungen
- Benutzer mit auslösenden Ereignissen
- Vorübergehend zu Richtlinien hinzugefügte Benutzer

## <a name="users-with-active-insider-risk-policy-alerts"></a>Benutzer mit aktiven Insiderrisikorichtlinienwarnungen

Das **Benutzerdashboard** zeigt automatisch alle Benutzer mit aktiven Insiderrisikorichtlinienwarnungen an. Diese Benutzer mit Warnungen verfügen sowohl über einen auslösenden Indikator als auch über ein Aktivitätsrisiko, das die Anforderungen für die Erstellung einer Insiderrisikowarnung erfüllt. Aktivitäten für diese Benutzer werden angezeigt,  indem der Benutzer im Benutzerdashboard ausgewählt wird und zur Registerkarte **Benutzeraktivität navigiert** wird.

## <a name="users-with-triggering-events"></a>Benutzer mit auslösenden Ereignissen

Das **Benutzerdashboard** zeigt automatisch alle Benutzer mit auslösenden Ereignissen an, die jedoch keine Aktivitätsrisikosentwertung haben, die eine Insiderrisikowarnung erstellen würde. Beispielsweise wird ein Benutzer mit einem gemeldeten Kündigungsdatum angezeigt, da diese Aktivität ein auslösendes Ereignis ist, aber keine Aktivität mit einem Risikoergebnis ist. Aktivitäten für diese Benutzer werden angezeigt,  indem der Benutzer im Benutzerdashboard ausgewählt wird und zur Registerkarte **Benutzeraktivität navigiert** wird.

## <a name="users-added-temporarily-to-policies"></a>Vorübergehend zu Richtlinien hinzugefügte Benutzer

Das **Benutzerdashboard** enthält Benutzer, die insidern Risikomanagementrichtlinien nach einem ungewöhnlichen Ereignis außerhalb des Insider-Risikomanagementworkflows hinzugefügt wurden. Das vorübergehende Hinzufügen von Benutzern (aus dem Richtliniendashboard) ist auch eine Möglichkeit, mit der Bewertung von Benutzeraktivitäten für eine Insider-Risikomanagementrichtlinie zum Testen der Richtlinie zu beginnen, auch wenn kein erforderlicher Connector konfiguriert ist.

Wenn ein Benutzer manuell zu einer Richtlinie hinzugefügt wird, werden die Benutzeraktivitäten für die vorherigen 90 Tage als Bewertung und zur Zeitachse der **Benutzeraktivität** hinzugefügt. Beispielsweise wird einem Benutzer derzeit keine Risikopunkte für eine Insiderrisikorichtlinie zugewiesen, und dem Benutzer werden Datenleckaktivitäten an die Rechtsabteilung in Ihrer Organisation gemeldet. Die Rechtsabteilung empfiehlt, neue kurzfristige Überwachungsanforderungen für den Benutzer zu konfigurieren. Sie können den Benutzer für einen bestimmten Zeitraum (Aktivierungsfenster) vorübergehend Ihrer *Datenlecksrichtlinie* zuweisen. Alle vorübergehend hinzugefügten Benutzer werden  im Benutzerdashboard angezeigt, da auf auslösende Ereignisanforderungen verzichtet wird.

>[!NOTE]
>Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im Benutzerdashboard **angezeigt werden.** Die Anzeige von Aktivitäten für die vorherigen 90 Tage für diese Benutzer kann bis zu 24 Stunden dauern. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, wählen  Sie den Benutzer im Dashboard Benutzer **aus,** und öffnen Sie die Registerkarte Benutzeraktivität im Detailbereich.

Der Benutzer wird automatisch  aus dem Benutzerdashboard entfernt und die Bewertung wird beendet, wenn die im Aktivierungsfenster definierte Zeit **abläuft,** wenn:

- Der Benutzer hat keine zusätzlichen auslösenden Ereignisse oder Richtlinienwarnungen für Insiderrisiken und
- wenn die manuell definierte Dauer **des Aktivierungsfensters** länger als die Dauer des globalen Richtlinienfensters ist. 

Die **Einstellung des** Aktivierungsfensters mit  der längsten Dauer überschreibt immer die Einstellung des Aktivierungsfensters mit einer kürzeren Dauer. Sie haben z. B.  das **Aktivierungsfenster** auf der Registerkarte globale Zeitrahmen für Richtlinien in den globalen Einstellungen für insider risk management für 15 Tage konfiguriert, das automatisch auf alle Ihre Insiderrisikorichtlinien angewendet wird. 

Sie fügen ihrer Richtlinie für Insiderrisiken für *Datenlecks* vorübergehend einen Benutzer hinzu und definieren 30 Tage als Aktivierungsfenster **für** diesen Benutzer. Die Einstellung **des globalen** Aktivierungsfensters von 15 Tagen wird überschrieben, indem die Einstellung des Aktivierungsfensters von 30 Tagen für den vorübergehend hinzugefügten Benutzer definiert wird.  Der vorübergehend hinzugefügte Benutzer  bleibt im Benutzerdashboard und ist für die Richtlinie 30 Tage lang im Bereich.

Im gegenteiligen Szenario,  in dem die Einstellung des globalen Aktivierungsfensters länger  ist als die  Einstellung für das Aktivierungsfenster, die für einen vorübergehend hinzugefügten Benutzer definiert ist, würde die Einstellung des globalen Aktivierungsfensters die Einstellung Aktivierungsfenster für den vorübergehend hinzugefügten Benutzer außer Kraft setzen.  Der vorübergehend hinzugefügte Benutzer  bleibt im Benutzerdashboard und ist für die Richtlinie für die Anzahl der Tage, die in den einstellungen des globalen Aktivierungsfensters definiert sind, im **Bereich.**

## <a name="view-user-information-on-the-users-dashboard"></a>Anzeigen von Benutzerinformationen im Benutzerdashboard

Jeder Benutzer, der im **Benutzerdashboard angezeigt wird,** verfügt über die folgenden Informationen:

- **Benutzer**: Der Benutzername für einen Benutzer. Dieses Feld wird anonymisiert, wenn die globale Anonymisierungseinstellung für insider risk management aktiviert ist.
- **Risikostufe:** Die aktuelle berechnete Risikostufe des Benutzers. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein. Für Benutzer mit nur auslösenden Indikatoren ist die Risikostufe null.
- **Aktive Warnungen:** Die Anzahl der aktiven Warnungen für alle Richtlinien.
- **Bestätigte Verstöße:** Die Anzahl der Fälle, die als *bestätigter Richtlinienverstoß* für den Benutzer aufgelöst wurden.
- **Case**: Der aktuelle aktive Fall für den Benutzer.

![Dashboard für Insider-Risikomanagement-Benutzer](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>Die Anzahl der Benutzer,  die im Benutzerdashboard angezeigt werden, kann je nach Umfang der aktiven Warnungen und übereinstimmenden Richtlinien in einigen Fällen begrenzt sein. Benutzer mit aktiven Warnungen  werden im Benutzerdashboard angezeigt, wenn die Warnungen generiert werden, und es kann selten fälle sein, in denen die maximale Anzahl angezeigter Benutzer erreicht wird. Wenn dieser Grenzwert eintritt, werden Benutzer mit aktiven Warnungen,  die nicht angezeigt werden, dem Benutzerdashboard hinzugefügt, wenn vorhandene Benutzerwarnungen triaged werden.

## <a name="view-user-details"></a>Anzeigen von Benutzerdetails

Um weitere Details zu den Risikoaktivitäten für einen Benutzer anzuzeigen, öffnen Sie den Benutzerdetailsebereich, indem Sie im Benutzerdashboard auf einen **Benutzer doppelklicken.** Im Detailbereich können Sie die folgenden Informationen anzeigen:

- **Registerkarte "Benutzerprofil"**
    - **Name und Titel**: Der Name und der Positionstitel für den Benutzer aus Azure Active Directory. Diese Benutzerfelder werden anonymisiert oder leer, wenn die globale Anonymisierungseinstellung für das Insiderrisikomanagement aktiviert ist.
    - **Benutzer-E-Mail:** Die E-Mail-Adresse des Benutzers.
    - **Alias**: Der Netzwerkalias für den Benutzer.
    - **Organisation oder Abteilung:** Die Organisation oder Abteilung für den Benutzer.

- **Registerkarte "Benutzeraktivität"**
    - **Verlauf der letzten Benutzeraktivität:** Listet sowohl auslösende Indikatoren als auch Insiderrisikoindikatoren für Benutzeraktivitäten bis zu den letzten 180 Tagen auf. Alle Aktivitäten, die für Insiderrisikoindikatoren relevant sind, werden ebenfalls als Bewertungsergebnis verwendet, obwohl die Aktivitäten möglicherweise eine Warnung vor Insiderrisiken ausgelöst haben. Triggering indicator examples may be a resignation date or the last scheduled date of work for the user. Insider-Risikoindikatoren sind Aktivitäten, die bestimmt sind, dass sie ein Risikoelement haben und in Richtlinien definiert sind, in die der Benutzer einbezogen wird. Ereignis- und Risikoaktivitäten werden mit dem neuesten zuerst aufgeführten Element aufgelistet.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Entfernen von Benutzern aus der Bereichszuweisung zu Richtlinien

Es kann Szenarien gibt, in denen Sie die Zuweisung von Risikoergebnissen zu den Aktivitäten eines Benutzers in Insider-Risikomanagementrichtlinien beenden müssen. Verwenden Sie Benutzer  **auf** der Seite Benutzerdashboard entfernen, um die Zuweisung von Risikoergebnissen für einen oder mehrere Benutzer aus allen Insider-Risikomanagementrichtlinien zu beenden, für die sie sich derzeit befinden. Diese Aktion entfernt Benutzer nicht aus der allgemeinen Richtlinienzuweisung (wenn Sie Benutzer oder Gruppen zu einer Richtlinienkonfiguration hinzufügen), sondern entfernt die Benutzer einfach aus der aktiven Verarbeitung durch Richtlinien nach aktuellen auslösenden Ereignissen. Wenn die Benutzer in Zukunft über ein weiteres auslösendes Ereignis verfügen, werden die Risikoergebnisse aus Richtlinien automatisch wieder den Benutzern zugewiesen. Vorhandene Warnungen oder Fälle für diesen Benutzer werden nicht entfernt.

>[!NOTE]
>Das Entfernen eines Benutzers aus einer Richtlinie kann einige Minuten dauern. Sobald der Vorgang abgeschlossen ist, wird der Benutzer nicht mehr auf der Seite Benutzer aufgeführt. Wenn der entfernte Benutzer über aktive Warnungen oder Fälle verfügt, bleibt der Benutzer auf der Seite Benutzer, und die Details für den Benutzer zeigen, dass er für eine Richtlinie nicht mehr im Bereich ist.

Führen Sie die folgenden Schritte aus, um Benutzer manuell aus dem Bereichsstatus in allen Insider-Risikomanagementrichtlinien zu entfernen:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Benutzer** aus.
2. Wählen Sie **im Benutzerdashboard** den Benutzer oder die Benutzer aus, die In-Scope in Insider-Risikomanagementrichtlinien entfernt werden möchten.
3. Wählen **Sie Benutzer entfernen aus.**
4. Wählen Sie **im Bereich** Benutzer entfernen die Option **Entfernen** oder **Abbrechen** aus, um die Änderungen zu verwerfen und das Dialogfeld zu schließen.
5. Wählen **Sie im** Bestätigungsbereich Entfernen aus, um den Benutzer zu entfernen.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Ausführen automatisierter Aufgaben mit Power Automate für einen Benutzer

Mithilfe empfohlener Power Automate können Risikoermittler und Analysten schnell Maßnahmen ergreifen, um:

- Benachrichtigen von Benutzern, wenn sie einer Insiderrisikorichtlinie hinzugefügt werden

So führen, verwalten oder erstellen Power Automate für einen Insider-Risikomanagement-Benutzer:

1. Wählen **Sie automatisieren** auf der Symbolleiste für Benutzeraktion aus.
2. Wählen Sie den Power Automate, der ausgeführt werden soll, und wählen Sie **dann Fluss ausführen aus.**
3. Nachdem der Fluss abgeschlossen ist, wählen Sie **Fertig aus.**

Weitere Informationen zu Power Automate Abläufen für insider risk management finden Sie unter [Erste Schritte mit Insider-Risikomanagement-Einstellungen](insider-risk-management-settings.md#power-automate-flows-preview).
