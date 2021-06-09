---
title: Vorhersagecodierung in Advanced eDiscovery – Schnellstart
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
description: Erfahren Sie, wie Sie mit der Verwendung des Moduls für die Vorhersagecodierung in Advanced eDiscovery beginnen. Dieser Artikel führt Sie durch den End-to-End-Prozess der Verwendung von Vorhersagecodierung, um Inhalte in einem Prüfdateisatz zu identifizieren, der für Ihre Untersuchung am relevantesten ist.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822561"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>Schnellstart: Vorhersagecodierung in Advanced eDiscovery (Vorschau)

Dieser Artikel bietet einen Schnellstart für die Verwendung von Vorhersagecodierung in Advanced eDiscovery. Das Modul für prädiktive Codierung in Advanced eDiscovery verwendet die intelligenten maschinellen Lernfunktionen in Advanced eDiscovery, um die Menge der zu überprüfenden Inhalte zu reduzieren. Predictive Coding hilft Ihnen dabei, große Mengen von Fallinhalten auf eine relevante Gruppe von Elementen zu reduzieren und zu überschreiben, die Sie für die Überprüfung priorisieren können. Dazu erstellen und schulen Sie Ihre eigenen Modelle für die Vorhersagecodierung, die Ihnen helfen, die Überprüfung der relevantesten Elemente in einem Prüfdateisatz zu priorisieren.

Hier ist eine kurze Übersicht über den Prozess der Vorhersagecodierung:

![Schnellstartprozess für die Vorhersagecodierung](..\media\PredictiveCodingQuickStartProcess.png)

Zunächst erstellen Sie ein Modell, bezeichnen nur 50 Elemente als relevant oder nicht relevant. Das System verwendet diese Schulung dann, um Vorhersageergebnisse auf jedes Element im Prüfdateisatz anzuwenden. Auf diese Weise können Sie Elemente basierend auf der Vorhersagebewertung filtern, sodass Sie zuerst die relevantesten (oder nicht relevanten) Elemente überprüfen können. Wenn Sie Modelle mit höheren Genauigkeits- und Rückrufraten trainieren möchten, können Sie die Bezeichnung von Elementen in nachfolgenden Schulungsrunden fortsetzen, bis sich das Modell stabilisiert. Sobald das Modell stabil ist, können Sie den endgültigen Vorhersagefilter anwenden, um zu überprüfende Elemente zu priorisieren.

Eine detaillierte Übersicht über die Vorhersagecodierung finden Sie unter [Informationen zur Vorhersagecodierung in Advanced eDiscovery.](predictive-coding-overview.md)

## <a name="step-1-create-a-new-predictive-coding-model"></a>Schritt 1: Erstellen eines neuen Vorhersagecodierungsmodells

Der erste Schritt besteht darin, ein neues Vorhersagecodierungsmodell im Prüfdateisatz zu erstellen.

1. Öffnen Sie im Microsoft 365 Compliance Center einen Advanced eDiscovery Fall, und wählen Sie dann die Registerkarte **"Prüfdateisätze" aus.**

2. Öffnen Sie einen Prüfdateisatz, und klicken Sie dann auf   >  **Analytics-Vorhersagecodierung verwalten (Vorschau).**

   ![Klicken Sie im Prüfdateisatz auf das Dropdownmenü "Analysieren", um zur Seite "Vorhersagecodierung" zu wechseln.](..\media\ManagePredictiveCoding.png)

3. Klicken Sie auf der Seite **"Vorhersagecodierungsmodelle (Vorschau)** auf **"Neues Modell".**

4. Geben Sie auf der Flyoutseite einen Namen für das Modell und eine optionale Beschreibung ein.

5. Klicken Sie auf **"Speichern",** um das Modell zu erstellen.

   Es dauert ein paar Minuten, bis das System Ihr Modell vorbereitet hat. Nachdem sie fertig ist, können Sie die erste Schulungsrunde durchführen.

Ausführlichere Anweisungen finden Sie unter [Erstellen eines vorhersagebasierten Codierungsmodells.](predictive-coding-create-model.md)

## <a name="step-2-perform-the-first-training-round"></a>Schritt 2: Durchführen der ersten Schulungsrunde

Nachdem Sie das Modell erstellt haben, besteht der nächste Schritt darin, die erste Schulungsrunde abzuschließen, indem Elemente als relevant oder nicht relevant gekennzeichnet werden.

1. Öffnen Sie den Prüfdateisatz, und klicken Sie dann auf   >  **Analytics-Vorhersagecodierung verwalten (Vorschau).**

2. Wählen Sie auf der Seite **"Vorhersagecodierungsmodelle (Vorschau)** das Modell aus, das Sie trainieren möchten.

3. Klicken Sie auf der Registerkarte **"Übersicht"** unter **"Runde 1"** auf **"Nächste Schulungsrunde starten".**

   Die Registerkarte **"Schulung"** wird angezeigt und enthält 50 Elemente, die Sie bezeichnen können.

4. Überprüfen Sie jedes Dokument,  und wählen Sie dann unten im Lesebereich die Schaltfläche Relevant oder Nicht relevant aus, um es zu bezeichnen. 

   ![Beschriften Sie jedes Dokument als relevant oder nicht relevant](..\media\TrainModel1.png)

5. Nachdem Sie alle 50 Elemente beschriftet haben, klicken Sie auf **Fertig stellen.**

    Es dauert ein paar Minuten, bis das System aus Ihrer Bezeichnung "lernen" und das Modell aktualisieren kann. Wenn dieser Vorgang abgeschlossen ist, wird der Status **"Bereit"** für das Modell auf der **Vorschauseite (Predictive Coding Models)** angezeigt.

Ausführlichere Anweisungen finden Sie unter ["Trainieren eines vorhersagebasierten Codierungsmodells".](predictive-coding-train-model.md)

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Schritt 3: Anwenden des Vorhersagebewertungsfilters auf Elemente im Prüfdateisatz

Nachdem Sie beim Leasen einer Schulungsrunde ausgeführt haben, können Sie den Filter für die Vorhersagebewertung auf Elemente im Prüfdateisatz anwenden. Auf diese Weise können Sie die Elemente überprüfen, die das Modell als relevant oder nicht relevant prognostiziert hat.   

1. Öffnen Sie den Prüfdateisatz.

   ![Klicken Sie auf "Filter", um die Flyoutseite "Filter" anzuzeigen.](..\media\PredictionScoreFilter0.png)

   Die vorinstallierten Standardfilter werden oben auf der Seite mit dem Prüfdateisatz angezeigt. Sie können diese Einstellung auf **Any** belassen.

2. Klicken Sie auf Filter , um die Flyoutseite Filter anzuzeigen.  

3. Erweitern Sie den Abschnitt **"Analyse & Vorhersagecodierung",** um eine Reihe von Filtern anzuzeigen.

      ![Filter für die Vorhersagebewertung im Abschnitt "Analyse & Vorhersagecodierung"](..\media\PredictionScoreFilter1.png)

   Die Benennungskonvention für Filter für die Vorhersagebewertung ist **die Vorhersagebewertung (Modellname).** Beispielsweise ist der Filtername der Vorhersagebewertung für ein Modell mit dem Namen **Modell A** **die Vorhersagebewertung (Modell A).**

4. Wählen Sie den Filter für die Vorhersagebewertung aus, den Sie verwenden möchten, und klicken Sie dann auf **"Fertig".**

5. Klicken Sie auf der Seite mit dem Prüfdateisatz auf die Dropdownliste für den Filter für die Vorhersagebewertung, und geben Sie die Mindest- und Höchstwerte für den Bereich der Vorhersagebewertung ein. Der folgende Screenshot zeigt beispielsweise einen Vorhersagebewertungsbereich zwischen **0,5** und **1,0.**

   ![Mindest- und Höchstwerte für den Filter für die Vorhersagebewertung](..\media\PredictionScoreFilter2.png)

6. Klicken Sie außerhalb des Filters, um den Filter automatisch auf den Prüfdateisatz anzuwenden.

  Eine Liste der Dokumente mit einer Vorhersagebewertung innerhalb des angegebenen Bereichs wird auf der Seite mit dem Prüfdateisatz angezeigt.

Ausführlichere Anweisungen finden Sie unter [Anwenden eines Vorhersagefilters auf einen Prüfdateisatz.](predictive-coding-apply-prediction-filter.md)

## <a name="step-4-perform-more-training-rounds"></a>Schritt 4: Durchführen weiterer Schulungsrunden

Höchstwahrscheinlich müssen Sie mehr Schulungsrunden durchführen, um das Modul zu schulen, um relevante und nicht relevante Elemente im Prüfdateisatz besser vorherzusagen. Im Allgemeinen trainieren Sie das Modell so lange, bis es ausreichend stabil ist, um Ihre Anforderungen zu erfüllen.

Weitere Informationen finden Sie unter ["Durchführen zusätzlicher Schulungsrunden"](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Schritt 5: Anwenden des endgültigen Filter für die Vorhersagebewertung zur Priorisierung der Überprüfung

Wiederholen Sie die Anweisungen in Schritt 3, um die endgültige Vorhersagebewertung auf den Prüfdateisatz anzuwenden, um die Überprüfung relevanter und nicht relevanter Elemente zu priorisieren, nachdem Sie alle Schulungsrunden abgeschlossen und das Modell stabilisiert haben.
