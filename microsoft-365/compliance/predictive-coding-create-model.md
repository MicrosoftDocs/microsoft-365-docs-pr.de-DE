---
title: Erstellen eines vorhersagebasierten Codierungsmodells in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Erfahren Sie, wie Sie in Advanced eDiscovery ein Vorhersagecodierungsmodell erstellen. Dies ist der erste Schritt bei der Verwendung der Machine Learning-Funktionen in Advanced eDiscovery, mit denen Sie relevante und nicht relevante Inhalte in einem Prüfdateisatz identifizieren können.
ms.openlocfilehash: 7724062848d8d757fbfd3a7870853d6f2c409d84
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822572"
---
# <a name="create-a-predictive-coding-model-preview"></a>Erstellen eines vorhersagebasierten Codierungsmodells (Vorschau)

Der erste Schritt bei der Verwendung der Machine Learning-Funktionen der Vorhersagecodierung in Advanced eDiscovery besteht darin, ein Modell für die Vorhersagecodierung zu erstellen. Nachdem Sie ein Modell erstellt haben, können Sie es trainieren, um die relevanten und nicht relevanten Inhalte in einem Prüfdateisatz zu identifizieren.

Informationen zum Überprüfen des Workflows für die Vorhersagecodierung finden Sie unter ["Informationen zur vorhersagebasierten Codierung in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>Vor dem Erstellen eines Modells

- Es müssen mindestens 2.000 Elemente in einem Prüfdateisatz vorhanden sein, um ein Modell für die Vorhersagecodierung zu erstellen.

- Stellen Sie sicher, dass Sie alle Auflistungen in den Prüfdateisatz übernehmen, bevor Sie ein Modell erstellen. Elemente, die einem Prüfdateisatz hinzugefügt werden, nachdem das Modell erstellt wurde, werden nicht verarbeitet und erhalten eine vom Modell generierte Vorhersagebewertung.

- Jedes Element im Prüfdateisatz, das keinen Text enthält, wird nicht vom Modell verarbeitet oder erhält eine Vorhersagebewertung. Elemente mit Text werden in den Steuerelementsatz oder einen Schulungssatz aufgenommen.

## <a name="create-a-model"></a>Ein Modell erstellen

1. Öffnen Sie im Microsoft 365 Compliance Center einen Advanced eDiscovery Fall, und wählen Sie dann die Registerkarte **"Prüfdateisätze" aus.**

2. Öffnen Sie einen Prüfdateisatz, und klicken Sie dann auf   >  **Analytics-Vorhersagecodierung verwalten (Vorschau).**

   ![Klicken Sie im Prüfdateisatz auf das Dropdownmenü "Analysieren", um zur Seite "Vorhersagecodierung" zu wechseln.](..\media\ManagePredictiveCoding.png)

3. Klicken Sie auf der Seite **"Vorhersagecodierungsmodelle (Vorschau)** auf **"Neues Modell".**

4. Geben Sie auf der Flyoutseite einen Namen für das Modell und eine optionale Beschreibung ein.

5. Optional können Sie erweiterte Einstellungen konfigurieren (indem Sie auf der Flyoutseite auf **"Erweiterte Optionen"** klicken), die sich auf die Konfidenzstufe und den Fehlerrand beziehen. Diese Einstellungen wirken sich auf die Anzahl der in der Steuerelementgruppe enthaltenen Elemente aus. Der *Steuerelementsatz* wird während des Schulungsprozesses verwendet, um die Vorhersageergebnisse auszuwerten, die das Modell Elementen mit der Bezeichnung zuweist, die Sie während der Schulungsrunden ausführen. Wenn Ihre Organisation Richtlinien für das Konfidenzniveau und den Fehlerrand für die Dokumentüberprüfung hat, geben Sie diese in den entsprechenden Feldern an. Verwenden Sie andernfalls die Standardeinstellungen.

6. Klicken Sie auf **"Speichern",** um das Modell zu erstellen.

   Es dauert ein paar Minuten, bis das System Ihr Modell vorbereitet hat. Nachdem sie fertig ist, können Sie die erste Schulungsrunde durchführen.

## <a name="what-happens-after-you-create-a-model"></a>Was geschieht, nachdem Sie ein Modell erstellt haben

Nachdem Sie ein Modell erstellt haben, treten während der Erstellung und Vorbereitung des Modells folgende Dinge im Hintergrund auf:

- Das System berechnet die Anzahl der Elemente für den Steuerelementsatz. Diese Größe basiert auf der Anzahl der Elemente im Prüfdateisatz und den Einstellungen für die Konfidenzstufe und den Fehlerrand. Elemente für den Steuerelementsatz werden nach dem Zufallsprinzip ausgewählt und als Steuerelementsatzelemente festgelegt. Das System enthält 10 Elemente aus dem Steuerelementsatz in der ersten Schulungsrunde.

- Das System wählt nach dem Zufallsprinzip 40 Elemente aus dem Prüfdateisatz aus, die in den Schulungssatz für die erste Schulungsrunde aufgenommen werden sollen. Daher umfasst die erste Schulungsrunde 50 Elemente für die Bezeichnung: 40 Elemente aus dem Schulungssatz und 10 Elemente aus dem Steuerelementsatz.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie ein Modell für einen Prüfdateisatz erstellt haben, führen Sie im nächsten Schritt Schulungsrunden durch, um das Modell zu "schulen", um Inhalte zu identifizieren, die für Ihre Untersuchung relevant sind. Weitere Informationen finden Sie unter ["Trainieren eines vorhersagebasierten Codierungsmodells".](predictive-coding-train-model.md)
