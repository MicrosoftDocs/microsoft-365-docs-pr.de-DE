---
title: Benutzerdashboard für das Insider Risikomanagement
description: Informationen zum benutzerdashboard für das Insider Risikomanagement in Microsoft 365
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
ms.openlocfilehash: c2b1a229bad5bc82f61227bd5a273af1aefb3481
ms.sourcegitcommit: 2e9e309ec09e5275ac6b3b425fba48a9ffce8eb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44900809"
---
# <a name="insider-risk-management-users-dashboard"></a>Benutzerdashboard für das Insider Risikomanagement

Das **benutzerdashboard** ist ein wichtiges Tool im Insider Risk Management-Workflow und hilft Ermittlern und Analysten, ein vollständigeres Verständnis der Risiko Aktivitäten zu haben. Dieses Dashboard bietet Ansichten und Verwaltungsfunktionen zur Erfüllung der administrativen Anforderungen zwischen dem Erstellen von Richtlinien für Insider Risiken und der Verwaltung von Insider Risiko-Management-Fällen.

Nachdem Benutzer den Richtlinien für das Insider Risikomanagement hinzugefügt wurden, evaluieren Hintergrundprozesse automatisch Benutzeraktivitäten für [auslösende Indikatoren](insider-risk-management-policies.md#indicators). Nachdem Auslöse Indikatoren vorhanden sind, werden Benutzeraktivitäten Risikobewertungen zugeordnet. Einige dieser Aktivitäten führen möglicherweise zu einer Warnung bei Insider Risiken, aber einige Aktivitäten entsprechen möglicherweise nicht einer minimalen Risiko Bewertungsstufe, und es wird keine Insider Risiko Warnung erstellt. Das **benutzerdashboard** ermöglicht es Ihnen, Benutzer mit diesen Indikatoren und Risikobewertungen sowie Benutzern mit aktiven Insider Risikowarnungen anzuzeigen.

Darüber hinaus gibt es möglicherweise Szenarien, in denen Sie den Insider Risikorichtlinien vorübergehend Benutzer hinzufügen müssen, nachdem außerhalb des Insider Risikomanagement-Workflows ein ungewöhnliches Ereignis gemeldet wurde. Das **benutzerdashboard** ermöglicht Ihnen das manuelle Hinzufügen eines Benutzers zu einer Insider Risiko Richtlinie für einen bestimmten Zeitraum und die Umgehung der Anforderung, dass ein Benutzer über ein auslösendes Symbol verfügt. Diese Benutzer werden immer im Dashboard Benutzer angezeigt, wenn Sie einer Richtlinie aktiv zugewiesen sind.

Erfahren Sie mehr darüber, wie das benutzerdashboard Benutzer in den folgenden Szenarien anzeigt:

- Dashboard-Benutzer mit aktiven Insider-Risikorichtlinien Warnungen
- Dashboard-Benutzer mit auslösenden Indikatoren
- Dashboard-Benutzer wurden vorübergehend zu Richtlinien hinzugefügt

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Dashboard-Benutzer mit aktiven Insider-Risikorichtlinien Warnungen

Das **benutzerdashboard** zeigt automatisch alle Benutzer mit aktiven Insider Risikorichtlinien Warnungen an. Diese Benutzer mit Warnungen haben sowohl einen Auslöse Indikator als auch eine Aktivitäts Risikobewertung, die die Anforderungen für die Erstellung einer Insider Risiko Warnung erfüllt. Aktivitäten für diese Benutzer werden angezeigt, indem der Benutzer im **Dashboard Benutzer** ausgewählt und zur Registerkarte **Benutzeraktivität** navigiert wird.

## <a name="dashboard-users-with-triggering-indicators"></a>Dashboard-Benutzer mit auslösenden Indikatoren

Das **benutzerdashboard** zeigt automatisch alle Benutzer mit auslösenden Indikatoren an, die jedoch keine Aktivitäts Risikobewertung aufweisen, die eine Insider Risiko Aktivität verursachen würde. Beispielsweise wird ein Benutzer mit einem gemeldeten Rücktrittsdatum angezeigt, da es sich bei diesem Ereignis um einen Auslöse Indikator handelt, es sich aber nicht um eine Aktivität mit einem Risikofaktor handelt. Aktivitäten für diese Benutzer werden angezeigt, indem der Benutzer im **Dashboard Benutzer** ausgewählt und zur Registerkarte **Benutzeraktivität** navigiert wird.

## <a name="dashboard-users-added-temporarily-to-policies"></a>Dashboard-Benutzer wurden vorübergehend zu Richtlinien hinzugefügt

Das **benutzerdashboard** ermöglicht das vorübergehende Hinzufügen von Benutzern zu einer vorhandenen Insider Risiko-Verwaltungsrichtlinie nach einem ungewöhnlichen Ereignis außerhalb des Insider Risikomanagement-Workflows. Das vorübergehende Hinzufügen von Benutzern ist auch eine Möglichkeit zum Hinzufügen von Benutzern zu einer Richtlinie für das Insider Risikomanagement zum Testen der Richtlinie, selbst wenn kein erforderlicher Connector konfiguriert ist.

Wenn ein Benutzer einer Richtlinie manuell hinzugefügt wird, werden die Benutzeraktivitäten für die vorhergehenden 90 Tage ausgewertet und zur Zeitachse der **Benutzeraktivität** hinzugefügt. Beispiel: ein Benutzer, der sich derzeit nicht in einer Insider Risiko Richtlinie befindet und der Benutzer über Datenverlust Aktivitäten verfügt, die der Rechtsabteilung in Ihrer Organisation gemeldet wurden. Die Rechtsabteilung empfiehlt, dass Sie neue kurzfristige Überwachungsanforderungen für den Benutzer konfigurieren. Sie können den Benutzer vorübergehend Ihrer *Datenverlust* Richtlinie für einen bestimmten Zeitraum (Aktivierungsfenster) zuweisen. Alle Benutzer, die vorübergehend hinzugefügt werden, werden im **benutzerdashboard** angezeigt, da für die Auslöse Indikator Anforderungen verzichtet wird.

>[!NOTE]
>Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im **Dashboard Benutzer**angezeigt werden. Aktivitäten für die letzten 90 Tage für diese Benutzer können bis zu 24 Stunden dauern, bis Sie angezeigt werden. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, wählen Sie den Benutzer im **Dashboard Benutzer** aus, und öffnen Sie die Registerkarte **Benutzeraktivität** im Detailbereich.

Der Benutzer wird automatisch aus der Richtlinie "Insider" und dem **benutzerdashboard** entfernt, wenn die im **Aktivierungsfenster** definierte Zeit abläuft, wenn:

- der Benutzer hat keine auslösenden Indikatoren oder Warnungen bei Insider Risikorichtlinien und
- Wenn die Dauer des manuell definierten **Aktivierungsfensters** länger ist als die Dauer des globalen Richtlinien **Aktivierungsfensters** . 

Die Einstellung für das **Aktivierungsfenster** mit der längsten Dauer überschreibt immer die Einstellung für das **Aktivierungsfenster** mit kürzerer Dauer. Sie haben beispielsweise das **Fenster Aktivierung** auf der Registerkarte globale **Richtlinie Zeitrahmen** in den globalen Einstellungen für das Insider Risikomanagement für 15 Tage konfiguriert, das automatisch auf alle ihre Insider Risikorichtlinien angewendet wird. 

Sie fügen vorübergehend einen Benutzer zu Ihren *Datenlecks* Insider Risiko Richtlinie hinzu und definieren 30 Tage als **Aktivierungsfenster** für diesen Benutzer. Die Einstellung des globalen **Aktivierungsfensters** von 15 Tagen wird durch Definieren der Einstellung für das **Aktivierungsfenster** von 30 Tagen für den vorübergehend hinzugefügten Benutzer außer Kraft gesetzt. Der vorübergehend hinzugefügte Benutzer verbleiben im **Dashboard Benutzer** und sind für die Richtlinie 30 Tage im Bereich.

Im umgekehrten Szenario, in dem die Einstellung für das globale **Aktivierungs** Fenster länger ist als die Einstellung für das **Aktivierungsfenster** , die für einen temporär hinzugefügten Benutzerdefiniert wurde, würde die Einstellung des globalen **Aktivierungs** Fensters die Einstellung des **Aktivierungsfensters** für den vorübergehend hinzugefügten Benutzer außer Kraft setzen Der vorübergehend hinzugefügte Benutzer verbleiben im **Dashboard Benutzer** und werden im Bereich für die Richtlinie für die Anzahl der Tage, die in den Einstellungen für das globale **Aktivierungsfenster** definiert sind.

## <a name="view-user-information-on-the-users-dashboard"></a>Anzeigen von Benutzerinformationen im Dashboard "Benutzer"

Jeder Benutzer, der im **Dashboard Benutzer** angezeigt wird, verfügt über die folgenden Informationen:

- **Users**: der Benutzername für einen Benutzer. Dieses Feld wird anonymisiert, wenn die globale Anonymisierungs Einstellung für das Insider Risikomanagement aktiviert ist.
- **Risikostufe**: das aktuelle berechnete Risikoniveau des Benutzers. Dieser Wert wird alle 24 Stunden berechnet, und bezieht die Risikobewertungen aller aktiver Warnungen für den betreffenden Benutzer in die Berechnung mit ein. Für Benutzer mit nur auslösenden Indikatoren ist die Risikostufe gleich NULL.
- **Aktive Warnungen**: die Anzahl der aktiven Warnungen für alle Richtlinien.
- **Bestätigte Verstöße**: die Anzahl der Fälle, die als *bestätigte Richtlinienverletzung* für den Benutzer aufgelöst wurden.
- **Case**: der aktuell aktive Fall für den Benutzer.

![Benutzerdashboard für das Insider Risikomanagement](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>Die Anzahl der Benutzer, die im **Dashboard Benutzer** angezeigt werden, ist möglicherweise in einigen Fällen, abhängig vom Umfang aktiver Warnungen und übereinstimmender Richtlinien, limitiert. Benutzer mit aktiven Warnungen werden im **Dashboard Benutzer** angezeigt, wenn die Warnungen generiert werden, und es kann in seltenen Fällen vorkommen, dass die maximale Anzahl angezeigter Benutzer erreicht wird. In diesem Fall werden Benutzer mit aktiven Warnungen, die nicht angezeigt werden, dem **Dashboard "Benutzer** " hinzugefügt, da vorhandene Benachrichtigungen für Benutzer noch älter sind.

## <a name="view-user-details"></a>Anzeigen von Benutzer Details

Wenn Sie weitere Details zur Risiko Aktivität für einen Benutzer anzeigen möchten, öffnen Sie den Bereich Benutzer Details, indem Sie auf einen Benutzer im **Dashboard Benutzer**doppelklicken. Im Detailbereich können Sie die folgenden Informationen anzeigen:

- Registerkarte ' **Benutzerprofil** '
    - **Name und Title**: der Name und der Position-Titel für den Benutzer aus Azure Active Directory. Diese Benutzerfelder werden anonymisiert oder leer, wenn die globale Anonymisierungs Einstellung für das Insider Risikomanagement aktiviert ist.
    - **Benutzer-e-Mail**: die e-Mail-Adresse für den Benutzer.
    - **Alias**: der Netzwerk Alias für den Benutzer.
    - **Organisation oder Abteilung**: die Organisation oder Abteilung für den Benutzer.

- Registerkarte " **Benutzeraktivität** "
    - **Verlauf der letzten Benutzeraktivität**: listet sowohl auslösende Indikatoren als auch Insider Risikoindikatoren für Benutzeraktivitäten bis zu den letzten 180 Tagen auf. Alle Aktivitäten, die für Insider Risikoindikatoren relevant sind, werden ebenfalls bewertet, obwohl die Aktivitäten möglicherweise eine Insider Risiko Warnung ausgelöst haben. Beispiele für auslösende Indikatoren sind möglicherweise ein Rücktrittsdatum oder das letzte geplante Arbeitsdatum für den Benutzer. Bei Insider Risikoindikatoren handelt es sich um Aktivitäten, die für ein Element des Risikos bestimmt sind und in Richtlinien definiert sind, in denen der Benutzer enthalten ist. Ereignis-und Risiko Aktivitäten werden mit dem letzten Element aufgeführt, das zuerst aufgeführt wird.

## <a name="temporarily-add-a-user-to-a-policy"></a>Vorübergehendes Hinzufügen eines Benutzers zu einer Richtlinie

Wenn Sie einen Benutzer vorübergehend zu einer Richtlinie für Insider Risiken hinzufügen möchten, verwenden Sie die Registerkarte **Benutzer** in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center. Benutzer haben die Anforderungen für die Richtlinie, der Sie hinzugefügt wurden, manuell für die Umgehung von Auslösern hinzugefügt und werden im **Dashboard Benutzer**angezeigt. Wenn Sie einen Benutzer dauerhaft zu einer Richtlinie für Insider Risiken hinzufügen möchten, verwenden Sie den Richtlinien-Assistenten.

Führen Sie die folgenden Schritte aus, um einen Benutzer zu einer vorhandenen Insider Risiko Richtlinie hinzuzufügen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Benutzer** aus.
2. Wählen Sie auf der Symbolleiste **einen Benutzer zu einer Richtlinie hinzufügen** aus.
3. Beginnen Sie im Dialogfeld **neuen Benutzer hinzufügen** mit der Eingabe eines Benutzernamens in das Feld **Benutzer** . Wählen Sie den Benutzer aus, den Sie einer Richtlinie hinzufügen möchten.
4. Wählen Sie den Dropdownpfeil für das Feld **Richtlinie** aus, um konfigurierte Richtlinien für die Verwaltung von Insider Risiken anzuzeigen. Wählen Sie die Richtlinie aus, der der Benutzer hinzugefügt werden soll.
5. Verwenden Sie das Slider-Steuerelement des **Aktivierungsfensters** , um zu definieren, wie lange der Benutzer in eine Richtlinie aufgenommen und im benutzerdashboard angezeigt wird. Die von Ihnen angegebene Zeit legt fest, wie lange die Richtlinie für diesen Benutzer aktiv ist und beginnt, wenn die erste Warnung generiert wird oder wenn ein auslösender Indikator (wie eine DLP-Richtlinienübereinstimmung) erkannt wird. Der Bereich für das **Aktivierungsfenster** beträgt 5 bis 30 Tage.
6. Wählen Sie **Hinzufügen** und **bestätigen** Sie dann, um den Benutzer zur Richtlinie hinzuzufügen.

>[!NOTE]
>Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im **Dashboard Benutzer**angezeigt werden. Aktivitäten für die letzten 90 Tage für diese Benutzer können bis zu 24 Stunden dauern, bis Sie angezeigt werden. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, wählen Sie den Benutzer im **Dashboard Benutzer** aus, und öffnen Sie die Registerkarte **Benutzeraktivität** im Detailbereich.
