---
title: Dashboard für Benutzer des Insider-Risikomanagements
description: Erfahren Sie mehr über das Dashboard "Benutzer im Insider-Risikomanagement" in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Compliance
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
ms.openlocfilehash: 802f3fdacba62839b93b8441502334ae486cdacc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226323"
---
# <a name="insider-risk-management-users-dashboard"></a>Dashboard für Benutzer des Insider-Risikomanagements

Das **Benutzerdashboard** ist ein wichtiges Tool im Workflow des Insider-Risikomanagements und hilft Ermittlern und Analysten, die Risikoaktivitäten besser zu verstehen. Dieses Dashboard bietet Ansichten und Verwaltungsfeatures, um die administrativen Anforderungen zwischen der Erstellung von Insider-Risikomanagementrichtlinien und der Verwaltung von Insider-Risikomanagementfällen zu erfüllen.

Nachdem Benutzer zu Insider-Risikomanagementrichtlinien hinzugefügt wurden, werden Benutzeraktivitäten automatisch von Hintergrundprozessen ausgewertet, [um Indikatoren auszulösen.](insider-risk-management-settings.md#indicators) Nachdem auslösende Indikatoren vorhanden sind, werden Benutzeraktivitäten Risikobewertungen zugewiesen. Einige dieser Aktivitäten können zu einer Insider-Risikowarnung führen, aber einige Aktivitäten erfüllen möglicherweise keine Mindestrisikobewertungsstufe, und es wird keine Insider-Risikowarnung erstellt. Über **das Benutzerdashboard** können Sie Benutzer mit diesen Arten von Indikatoren und Risikobewertungen sowie Benutzer mit aktiven Insider-Risikowarnungen anzeigen.

Erfahren Sie mehr darüber, wie das Benutzerdashboard Benutzer in den folgenden Szenarien anzeigt:

- Benutzer mit warnungen zu aktiven Insider-Risikorichtlinien
- Benutzer mit auslösenden Ereignissen
- Benutzer, die vorübergehend zu Richtlinien hinzugefügt wurden

## <a name="users-with-active-insider-risk-policy-alerts"></a>Benutzer mit warnungen zu aktiven Insider-Risikorichtlinien

Im **Dashboard "Benutzer"** werden automatisch alle Benutzer mit aktiven Warnungen zu Insider-Risikorichtlinien angezeigt. Diese Benutzer mit Warnungen verfügen sowohl über einen auslösenden Indikator als auch über eine Aktivitätsrisikobewertung, die die Anforderungen für die Erstellung einer Insider-Risikowarnung erfüllt. Aktivitäten für diese Benutzer werden angezeigt, indem Sie den Benutzer im **Benutzerdashboard** auswählen und zur Registerkarte **"Benutzeraktivität"** navigieren.

## <a name="users-with-triggering-events"></a>Benutzer mit auslösenden Ereignissen

Das **Benutzerdashboard** zeigt automatisch alle Benutzer mit auslösenden Ereignissen an, die jedoch keine Aktivitätsrisikobewertung aufweisen, die eine Insider-Risikowarnung erstellen würde. Beispielsweise wird ein Benutzer mit einem gemeldeten Ablaufdatum angezeigt, da es sich bei dieser Aktivität um ein auslösendes Ereignis handelt, es sich jedoch nicht um eine Aktivität mit einer Risikobewertung handelt. Aktivitäten für diese Benutzer werden angezeigt, indem Sie den Benutzer im **Benutzerdashboard** auswählen und zur Registerkarte **"Benutzeraktivität"** navigieren.

## <a name="users-added-temporarily-to-policies"></a>Benutzer, die vorübergehend zu Richtlinien hinzugefügt wurden

Das **Benutzerdashboard** enthält Benutzer, die nach einem ungewöhnlichen Ereignis außerhalb des Insider-Risikomanagement-Workflows zu Insider-Risikomanagementrichtlinien hinzugefügt wurden. Das vorübergehende Hinzufügen von Benutzern (über das Richtliniendashboard) ist auch eine Möglichkeit, mit der Bewertung von Benutzeraktivitäten für eine Insider-Risikomanagementrichtlinie zum Testen der Richtlinie zu beginnen, auch wenn kein erforderlicher Connector konfiguriert ist.

Wenn ein Benutzer manuell zu einer Richtlinie hinzugefügt wird, werden die Benutzeraktivitäten für die vorherigen 90 Tage bewertet und zur Zeitachse der **Benutzeraktivität** hinzugefügt. Beispielsweise haben Sie einen Benutzer, dem derzeit keine Risikobewertungen für eine Insider-Risikorichtlinie zugewiesen werden, und der Benutzer hat Datenleckaktivitäten, die an die Rechtsabteilung in Ihrer Organisation gemeldet werden. Die Rechtsabteilung empfiehlt, neue kurzfristige Überwachungsanforderungen für den Benutzer zu konfigurieren. Sie können den Benutzer ihrer Richtlinie für *Datenlecks* vorübergehend für einen bestimmten Zeitraum (Aktivierungsfenster) zuweisen. Alle vorübergehend hinzugefügten Benutzer werden im **Benutzerdashboard** angezeigt, da die Anforderungen an auslösende Ereignisse nicht erfüllt werden.

> [!NOTE]
> Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im **Benutzerdashboard** angezeigt werden. Die Anzeige von Aktivitäten für die vorherigen 90 Tage für diese Benutzer kann bis zu 24 Stunden dauern. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, wählen Sie den Benutzer im **Benutzerdashboard** aus, und öffnen Sie die Registerkarte **"Benutzeraktivität"** im Detailbereich.

Der Benutzer wird automatisch aus dem **Benutzerdashboard** entfernt, und die Bewertung wird beendet, wenn die im **Aktivierungsfenster** definierte Zeit abläuft, wenn:

- der Benutzer keine zusätzlichen auslösenden Ereignisse oder Warnungen zu Insider-Risikorichtlinien hat und
- wenn die dauer des manuell definierten **Aktivierungsfensters** länger als die Dauer des Globalen **Richtlinienaktivierungsfensters** ist.

Die Einstellung des **Aktivierungsfensters** mit der längsten Dauer überschreibt immer die Einstellung des **Aktivierungsfensters** mit einer kürzeren Dauer. Sie haben beispielsweise das **Aktivierungsfenster** auf der Registerkarte "Globale **Richtlinien-Zeitrahmen"** in den globalen Einstellungen für das Insider-Risikomanagement für 15 Tage konfiguriert, das automatisch auf alle Ihre Insider-Risikorichtlinien angewendet wird.

Sie fügen vorübergehend einen Benutzer zu Ihrer Richtlinie für Insider-Risiken für *Datenlecks* hinzu und definieren 30 Tage als **Aktivierungsfenster** für diesen Benutzer. Die globale Einstellung des **Aktivierungsfensters** von 15 Tagen wird überschrieben, indem die Einstellung des **Aktivierungsfensters** von 30 Tagen für den vorübergehend hinzugefügten Benutzer definiert wird. Der vorübergehend hinzugefügte Benutzer verbleibt im **Benutzerdashboard** und gilt 30 Tage lang für die Richtlinie.

Im entgegengesetzten Szenario, in dem die Einstellung des globalen **Aktivierungsfensters** länger als die für einen vorübergehend hinzugefügten Benutzer definierte Einstellung des **Aktivierungsfensters** ist, würde die Einstellung des globalen **Aktivierungsfensters** die Einstellung des **Aktivierungsfensters** für den vorübergehend hinzugefügten Benutzer außer Kraft setzen. Der vorübergehend hinzugefügte Benutzer verbleibt im **Benutzerdashboard** und gilt für die Richtlinie für die Anzahl der Tage, die in den einstellungen des globalen **Aktivierungsfensters** definiert sind.

## <a name="view-user-information-on-the-users-dashboard"></a>Anzeigen von Benutzerinformationen im Benutzerdashboard

Jeder Benutzer, der im **Benutzerdashboard** angezeigt wird, verfügt über die folgenden Informationen:

- **Benutzer:** Der Benutzername für einen Benutzer. Dieses Feld wird anonymisiert, wenn die globale Anonymisierungseinstellung für das Insider-Risikomanagement aktiviert ist.
- **Risikostufe:** Die aktuelle berechnete Risikostufe des Benutzers. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein. Für Benutzer, die nur Indikatoren auslösen, ist die Risikostufe null.
- **Aktive Warnungen:** Die Anzahl der aktiven Warnungen für alle Richtlinien.
- **Bestätigte Verstöße:** Die Anzahl der Fälle, die als *bestätigter Richtlinienverstoß* für den Benutzer behoben wurden.
- **Case**: Der aktuelle aktive Fall für den Benutzer.

![Dashboard für Benutzer des Insider-Risikomanagements](../media/insider-risk-users-dashboard.png)

> [!NOTE]
> Die Anzahl der Benutzer, die im **Benutzerdashboard** angezeigt werden, kann in einigen Fällen begrenzt sein, je nach Anzahl der aktiven Warnungen und übereinstimmenden Richtlinien. Benutzer mit aktiven Warnungen werden im **Benutzerdashboard** angezeigt, wenn die Warnungen generiert werden, und es kann vorkommen, dass die maximale Anzahl der angezeigten Benutzer erreicht wird. Wenn dieser Grenzwert erreicht wird, werden Benutzer mit aktiven Warnungen, die nicht angezeigt werden, dem **Benutzerdashboard** hinzugefügt, wenn vorhandene Benutzerwarnungen triaget werden.

## <a name="view-user-details"></a>Anzeigen von Benutzerdetails

Wenn Sie weitere Details zu Risikoaktivitäten für einen Benutzer anzeigen möchten, öffnen Sie den Bereich "Benutzerdetails", indem Sie im **Benutzerdashboard** auf einen Benutzer doppelklicken. Im Detailbereich können Sie die folgenden Informationen anzeigen:

- **Registerkarte "Benutzerprofil"**
  - **Name und Titel:** Name und Position des Benutzers aus Azure Active Directory. Diese Benutzerfelder werden anonymisiert oder leer, wenn die globale Anonymisierungseinstellung für das Insider-Risikomanagement aktiviert ist.
  - **Benutzer-E-Mail:** Die E-Mail-Adresse des Benutzers.
  - **Alias:** Der Netzwerkalias für den Benutzer.
  - **Organisation oder Abteilung:** Die Organisation oder Abteilung für den Benutzer.

- Registerkarte **"Benutzeraktivität"**
  - **Verlauf der letzten Benutzeraktivität:** Listet sowohl auslösende Indikatoren als auch Insider-Risikoindikatoren für Benutzeraktivitäten bis zu den letzten 180 Tagen auf. Alle Aktivitäten, die für Insider-Risikoindikatoren relevant sind, werden ebenfalls bewertet, obwohl die Aktivitäten möglicherweise eine Insider-Risikowarnung generiert haben. Triggering indicator examples may be a date date or the last scheduled date of work for the user. Bei Insider-Risikoindikatoren handelt es sich um Aktivitäten, die als Risikoelement festgelegt sind, und werden in Richtlinien definiert, in denen der Benutzer enthalten ist. Ereignis- und Risikoaktivitäten werden mit dem zuletzt aufgeführten Element zuerst aufgeführt.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Entfernen von Benutzern aus der Bereichszuweisung zu Richtlinien

Es kann Szenarien geben, in denen Sie die Zuweisung von Risikobewertungen zur Aktivität eines Benutzers in Insider-Risikomanagementrichtlinien beenden müssen. Verwenden Sie **"Benutzer entfernen"** auf der **Seite "Benutzerdashboard",** um die Zuweisung von Risikobewertungen für einen oder mehrere Benutzer aus allen Insider-Risikomanagementrichtlinien zu beenden, für die sie derzeit gelten. Diese Aktion entfernt keine Benutzer aus der allgemeinen Richtlinienzuweisung (wenn Sie Benutzer oder Gruppen zu einer Richtlinienkonfiguration hinzufügen), sondern entfernt die Benutzer einfach aus der aktiven Verarbeitung durch Richtlinien nach aktuellen auslösenden Ereignissen. Wenn die Benutzer in Zukunft über ein weiteres auslösende Ereignis verfügen, werden die Risikobewertungen aus Richtlinien automatisch erneut den Benutzern zugewiesen. Vorhandene Warnungen oder Fälle für diesen Benutzer werden nicht entfernt.

> [!NOTE]
> Das Entfernen eines Benutzers aus einer Richtlinie kann mehrere Minuten dauern. Nach Abschluss des Vorgangs wird der Benutzer nicht mehr auf der Seite "Benutzer" aufgeführt. Wenn der entfernte Benutzer über aktive Warnungen oder Fälle verfügt, bleibt der Benutzer auf der Seite "Benutzer", und die Details für den Benutzer zeigen an, dass er nicht mehr im Bereich einer Richtlinie liegt.

Führen Sie die folgenden Schritte aus, um Benutzer in allen Insider-Risikomanagementrichtlinien manuell aus dem Bereichsstatus zu entfernen:

1. Wechseln [Sie](https://compliance.microsoft.com)im Microsoft 365 Compliance Center zum **Insider-Risikomanagement,** und wählen Sie die Registerkarte **"Benutzer"** aus.
2. Wählen Sie im **Benutzerdashboard** den Benutzer aus, den Sie in Insider-Risikomanagementrichtlinien entfernen möchten.
3. Wählen Sie **"Benutzer entfernen" aus.**
4. Wählen Sie im **Bereich "Benutzer entfernen"** die Option **"Entfernen"** oder **"Abbrechen"** aus, um die Änderungen zu verwerfen, und schließen Sie das Dialogfeld.
5. Wählen Sie im Bestätigungsbereich **"Entfernen"** aus, um den Benutzer zu entfernen.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Ausführen automatisierter Aufgaben mit Power Automate Flüssen für einen Benutzer

Mit den empfohlenen Power Automate Flüssen können Risikoermittler und Analysten schnell Maßnahmen ergreifen, um:

- Benutzer benachrichtigen, wenn sie einer Insider-Risikorichtlinie hinzugefügt werden

So führen Sie Power Automate Flüsse für einen Benutzer des Insider-Risikomanagements aus, verwalten oder erstellen sie:

1. Wählen Sie **"Automatisieren"** auf der Symbolleiste für Benutzeraktionen aus.
2. Wählen Sie den auszuführenden Power Automate Fluss aus, und wählen Sie dann **"Ausführungsablauf"** aus.
3. Wählen Sie nach Abschluss des Flusses **"Fertig"** aus.

Weitere Informationen zu Power Automate Abläufen für das Insider-Risikomanagement finden Sie unter "Erste Schritte mit Einstellungen für [das Insider-Risikomanagement".](insider-risk-management-settings.md#power-automate-flows-preview)
