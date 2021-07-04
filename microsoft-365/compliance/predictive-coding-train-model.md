---
title: Trainieren eines vorhersagebasierten Codierungsmodells in Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288191"
---
# <a name="train-a-predictive-coding-model-preview"></a>Trainieren eines vorhersagebasierten Codierungsmodells (Vorschau)

Nachdem Sie in Advanced eDiscovery ein Modell für die Vorhersagecodierung erstellt haben, besteht der nächste Schritt darin, die erste Schulungsrunde durchzuführen, um das Modell zu relevanten und nicht relevanten Inhalten in Ihrem Prüfdateisatz zu schulen. Nachdem Sie die erste Schulungsrunde abgeschlossen haben, können Sie nachfolgende Schulungsrunden durchführen, um die Fähigkeit des Modells zu verbessern, relevante und nicht relevante Inhalte vorherzusagen.

Informationen zum Überprüfen des Workflows für die Vorhersagecodierung finden Sie unter ["Informationen zur Vorhersage von Codierung in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>Vor dem Trainieren eines Modells

- Kennzeichnen Sie während einer Schulungsrunde Elemente basierend auf der Relevanz des Inhalts im Dokument als **relevant** oder **nicht relevant.** Basieren Sie Ihre Entscheidung nicht auf den Werten in den Metadatenfeldern. Wenn Sie z. B. E-Mail-Nachrichten oder Teams Unterhaltungen verwenden möchten, basieren Sie ihre Bezeichnungsentscheidung nicht auf den Teilnehmern der Nachricht.

## <a name="train-a-model-for-the-first-time"></a>Erstmaliges Trainieren eines Modells

1. Öffnen Sie im Microsoft 365 Compliance Center einen Advanced eDiscovery Fall, und wählen Sie dann die Registerkarte **"Prüfdateisätze" aus.**

2. Öffnen Sie einen Prüfdateisatz, und klicken Sie dann auf   >  **Analytics-Vorhersagecodierung verwalten (Vorschau).**

3. Wählen Sie auf der Seite **"Vorhersagecodierungsmodelle (Vorschau)** das Modell aus, das Sie trainieren möchten.

4. Klicken Sie auf der Registerkarte **"Übersicht"** unter **"Runde 1"** auf **"Nächste Schulungsrunde starten".**

   Die Registerkarte **"Schulung"** wird angezeigt und enthält 50 Elemente, die Sie bezeichnen können.

5. Überprüfen Sie jedes Dokument,  und wählen Sie dann unten im Lesebereich die Schaltfläche Relevant oder Nicht relevant aus, um es zu bezeichnen. 

   ![Jedes Dokument als relevant oder nicht relevant kennzeichnen](..\media\TrainModel1.png)

6. Nachdem Sie alle 50 Elemente beschriftet haben, klicken Sie auf **Fertig stellen.**

    Es dauert ein paar Minuten, bis das System aus Ihrer Bezeichnung "lernen" und das Modell aktualisieren kann. Wenn dieser Vorgang abgeschlossen ist, wird der Status **"Bereit"** für das Modell auf der **Vorschauseite (Predictive Coding Models)** angezeigt.

## <a name="perform-additional-training-rounds"></a>Durchführen zusätzlicher Schulungsrunden

Nachdem Sie die erste Schulungsrunde durchgeführt haben, können Sie nachfolgende Schulungsrunden durchführen, indem Sie die Schritte im vorherigen Abschnitt ausführen. Der einzige Unterschied besteht darin, dass die Anzahl der Schulungsrunden auf der Registerkarte **"Modellübersicht"** aktualisiert wird. Wenn Sie beispielsweise die erste Schulungsrunde durchgeführt haben, können Sie auf **"Nächste Schulungsrunde starten"** klicken, um die zweite Schulungsrunde zu starten. Und so weiter.

Jede Schulungsrunde (sowohl die laufenden als auch die abgeschlossenen) wird auf der Registerkarte **"Schulung"** für das Modell angezeigt. Wenn Sie eine Schulungsrunde auswählen, wird eine Flyoutseite mit Informationen und Metriken für die Runde angezeigt.

## <a name="what-happens-after-you-perform-a-training-round"></a>Was geschieht, nachdem Sie eine Schulungsrunde durchgeführt haben

Nachdem Sie die erste Schulungsrunde durchgeführt haben, wird ein Auftrag gestartet, der die folgenden Aufgaben ausführt:

- Basierend auf der Art und Weise, wie Sie die 40 Elemente im Schulungssatz beschriftet haben, lernt das Modell aus Ihrer Bezeichnung und aktualisiert sich, um genauer zu werden.

- Das Modell verarbeitet dann jedes Element im gesamten Prüfdateisatz und weist eine Vorhersagebewertung zwischen **0** (nicht relevant) und **1** (relevant) zu.

- Das Modell weist den 10 Elementen in der Steuerelementgruppe, die Sie während der Schulungsrunde bezeichnet haben, eine Vorhersagebewertung zu. Das Modell vergleicht die Vorhersagebewertung dieser 10 Elemente mit der tatsächlichen Bezeichnung, die Sie dem Element während der Schulungsrunde zugewiesen haben. Basierend auf diesem Vergleich identifiziert das Modell die folgende Klassifizierung (die so genannte *Steuerelementsatz-Verwechslungsmatrix),* um die Vorhersageleistung des Modells zu bewerten:

  <br>

  ****

  |Label|Modell prognostiziert Element ist relevant|Modell prognostiziert Element ist nicht relevant|
  |---|---|---|
  |**Bearbeiterbeschriftungselement als relevant**|True positive|Falsch positiv|
  |**Bearbeiter bezeichnet Element als nicht relevant**|Falsch negativ|True negativ|
  |

  Basierend auf diesen Vergleichen leitet das Modell Werte für die Metriken F-Bewertung, Genauigkeit und Rückruf sowie den Fehlerrand für jeden ab. Bewertungen für diese Modellleistungsmetriken werden auf einer Flyoutseite für die Schulungsrunde angezeigt. Eine Beschreibung dieser Metriken finden Sie unter ["Referenz zur prädiktiven Codierung".](predictive-coding-reference.md)

- Schließlich bestimmt das Modell die nächsten 50 Elemente, die für die nächste Schulungsrunde verwendet werden. Dieses Mal kann das Modell 20 Elemente aus der Steuerelementgruppe und 30 neue Elemente aus dem Prüfdateisatz auswählen und als Schulungssatz für die nächste Runde festlegen. Das Sampling für die nächste Schulungsrunde wird nicht einheitlich stichprobeniert. Das Modell optimiert die Samplingauswahl von Elementen aus dem Prüfdateisatz, um Elemente auszuwählen, bei denen die Vorhersage mehrdeutig ist, was bedeutet, dass sich die Vorhersagebewertung im Bereich von 0,5 befindet. Dieser Vorgang wird als *voreingenommene Auswahl* bezeichnet.

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>Was geschieht, nachdem Sie nachfolgende Schulungsrunden durchgeführt haben

Nachdem Sie nachfolgende Schulungsrunden (nach der ersten Schulungsrunde) durchgeführt haben, führt das Modell folgende Aktionen aus:

- Das Modell wird basierend auf den Bezeichnungen aktualisiert, die Sie auf den Schulungssatz in dieser Schulungsrunde angewendet haben.

- Das System wertet die Vorhersagebewertung des Modells für die Elemente im Steuerelementsatz aus und überprüft, ob die Bewertung mit der Bezeichnung von Elementen in der Steuerelementgruppe übereinstimmt. Die Auswertung wird für alle bezeichneten Elemente aus dem Steuerelementsatz für alle Schulungsrunden durchgeführt. Die Ergebnisse dieser Auswertung sind in das Dashboard auf der Registerkarte **"Übersicht"** für das Modell integriert.

- Das aktualisierte Modell verarbeitet jedes Element im Prüfdateisatz erneut und weist jedem Element eine aktualisierte Vorhersagebewertung zu.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die erste Schulungsrunde durchgeführt haben, können Sie weitere Schulungsrunden durchführen oder den Filter für die Vorhersagebewertung des Modells auf den Prüfdateisatz anwenden, um die Elemente anzuzeigen, die das Modell als relevant oder nicht relevant vorausgesagt hat. Weitere Informationen finden Sie unter [Anwenden eines Vorhersagebewertungsfilters auf einen Prüfdateisatz.](predictive-coding-apply-prediction-filter.md)
