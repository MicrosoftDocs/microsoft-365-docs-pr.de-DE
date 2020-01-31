---
title: Insider Risk Management-Benutzer (Vorschau)
description: Erfahren Sie mehr über Insider Risk Management-Benutzer in Microsoft 365
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
ms.openlocfilehash: f79fcebf220f1aee98ba97c537ff80b65b6e3881
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582854"
---
# <a name="insider-risk-management-users-preview"></a>Insider Risk Management-Benutzer (Vorschau)

Insider Risk Management-Benutzer sind Mitarbeiter in Ihrer Organisation, die in einem oder mehreren Richtlinien für das Insider Risikomanagement enthalten sind. Verwenden Sie das **benutzerdashboard** , um Risikoinformationen zu Mitarbeitern schnell zu überprüfen und einen Mitarbeiter zu einer vorhandenen Richtlinie für Insider Risikomanagement hinzuzufügen. Für jeden Benutzer, der in eine Richtlinie für das Insider Risikomanagement eingeschlossen ist, werden im **benutzerdashboard**folgende Informationen angezeigt:

- **Users**: der Benutzername für einen Benutzer.
- **Risikostufe**: 
- **Aktive Warnungen**: die Anzahl der aktiven Warnungen für alle Richtlinien.
- **Bestätigte Verstöße**: die Anzahl der Fälle, die als *bestätigte Richtlinienverletzung* für den Benutzer aufgelöst wurden.
- **Case**: der aktuell aktive Fall für den Benutzer.

![Benutzerdashboard für das Insider Risikomanagement](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a>Anzeigen von Benutzer Details

Wenn Sie weitere Details zur Risiko Aktivität für einen Benutzer anzeigen möchten, öffnen Sie den Bereich Benutzer Details, indem Sie auf einen Benutzer im **Dashboard Benutzer**doppelklicken. Im Detailbereich können Sie die folgenden Informationen anzeigen:

- Registerkarte ' **Benutzerprofil** '
    - **Name und Title**: der Name und der Position-Titel für den Benutzer.
    - **Benutzer-e-Mail**: die e-Mail-Adresse für den Benutzer.
    - **Alias**: der Netzwerk Alias für den Benutzer.
    - **Organisation oder Abteilung**: die Organisation oder Abteilung für den Benutzer.

- Registerkarte " **Benutzeraktivität** "
    - **Verlauf der letzten Benutzeraktivität**: listet sowohl Richtlinien auslösende Ereignisse als auch Risikoindikatoren für Benutzeraktivitäten auf. Ein auslösendes Ereignis kann die Annahme eines Rücktritts Datums oder des letzten geplanten Arbeitsdatums für den Mitarbeiter sein. Risikoindikatoren sind Aktivitäten, die für ein Element des Risikos bestimmt sind und mit Richtlinien abgeglichen werden, in denen der Benutzer enthalten ist. Ereignisse und Risiko Aktivitäten werden mit dem letzten Element aufgeführt, das zuerst aufgeführt wird.

## <a name="add-a-user-to-a-policy"></a>Hinzufügen eines Benutzers zu einer Richtlinie

Zum Hinzufügen eines Benutzers zu einer Richtlinie für Insider Risiken verwenden Sie entweder den Assistenten für neue Richtlinien oder die Registerkarte **Benutzer** in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.

Führen Sie die folgenden Schritte aus, um einen Benutzer zu einer vorhandenen Insider Risiko Richtlinie hinzuzufügen:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Benutzer** aus.
2. Wählen Sie auf der Symbolleiste **einen Benutzer zu einer Richtlinie hinzufügen** aus.
3. Beginnen Sie im Dialogfeld **neuen Benutzer hinzufügen** mit der Eingabe eines Benutzernamens in das Feld **Benutzer** . Wählen Sie den Benutzer aus, den Sie einer Richtlinie hinzufügen möchten.
4. Wählen Sie den Dropdownpfeil für das Feld **Richtlinie** aus, um konfigurierte Richtlinien für die Verwaltung von Insider Risiken anzuzeigen. Wählen Sie die Richtlinie aus, der der Benutzer hinzugefügt werden soll.
5. Definieren Sie mit dem Slider-Steuerelement des **Überwachungsfensters** die...... Der Bereich für das Überwachungsfenster beträgt 5 bis 30 Tage.
6. Wählen Sie **Hinzufügen** und **bestätigen** Sie dann, um den Benutzer zur Richtlinie hinzuzufügen.
