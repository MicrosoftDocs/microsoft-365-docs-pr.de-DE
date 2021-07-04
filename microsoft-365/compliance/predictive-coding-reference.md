---
title: Predictive Coding-Referenz
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
ms.openlocfilehash: ad9bf2ba40ede2d76246c56bf94b90e0e96aeeff
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288275"
---
# <a name="predictive-coding-reference-preview"></a>Referenz zur prädiktiven Codierung (Vorschau)

In diesem Artikel werden die wichtigsten Konzepte und Metriken des Tools für die Vorhersagecodierung in Advanced eDiscovery beschrieben. Die Abschnitte in diesem Artikel sind in alphabetischer Reihenfolge aufgeführt.

## <a name="confidence-level"></a>Zuverlässigkeitsstufe

Das Vertrauensniveau ist eine erweiterte Einstellung, wenn Sie ein Modell für die Vorhersagecodierung erstellen. Es definiert, dass die Leistungsmetriken des Modells (z. B. Umfang, Genauigkeit und Rückruf) in einen bestimmten Bereich fallen (der den für das Modell definierten Fehlerrand bestimmt), der für die tatsächlichen Werte der Vorhersageergebnisse repräsentativ ist, die das Modell Elementen im Prüfdateisatz zuweist. Die Werte für die Konfidenzstufe und den Fehlerrand helfen auch zu bestimmen, wie viele Elemente in den Steuerelementsatz einbezogen werden. Der Standardwert für die Konfidenzstufe ist 0,95 oder 95 %.

## <a name="control-set"></a>Steuerelementsatz

Während des Schulungsprozesses eines vorhersagebasierten Codierungsmodells wird ein Steuerelementsatz verwendet. Der Steuerelementsatz dient zum Auswerten der Vorhersageergebnisse, die das Modell Elementen mit der Bezeichnung zuweist, die Sie während Schulungsrunden ausführen. Die Größe des Steuerelementsatzes basiert auf der Anzahl der Elemente im Prüfdateisatz sowie der Konfidenzstufe und dem Rand von Fehlerwerten, die beim Erstellen des Modells festgelegt werden. Elemente im Steuerelementsatz ändern sich nie und sind für Benutzer nicht identifizierbar. Die Gesamtanzahl der Elemente im Steuerelementsatz wird auf der Flyoutseite für eine Schulungsrunde angezeigt.

## <a name="control-set-confusion-matrix"></a>Matrix der Steuerelementsatz-Verwirrung

Nachdem Sie eine Schulungsrunde abgeschlossen haben, weist das Modell den 10 Elementen im Steuerelementsatz, die Sie während der Schulungsrunde bezeichnet haben, eine Vorhersagebewertung zu. Das Modell vergleicht die Vorhersagebewertung dieser 10 Elemente mit der tatsächlichen Bezeichnung, die Sie dem Element während der Schulungsrunde zugewiesen haben. Basierend auf diesem Vergleich identifiziert das Modell die folgenden Klassifizierungen, um die Vorhersageleistung des Modells zu bewerten:

<br>

****

|Label|Modell prognostiziert Element ist relevant|Modell prognostiziert Element ist nicht relevant|
|---|---|---|
|**Bearbeiterbeschriftungselement als relevant**|True positive|Falsch positiv|
|**Bearbeiter bezeichnet Element als nicht relevant**|Falsch negativ|True negativ|
|

Basierend auf diesen Vergleichen leitet das Modell Werte für die Metriken F-Bewertung, Genauigkeit und Rückruf sowie den Fehlerrand für jeden ab. Die Anzahl der einzelnen Verwechslungstypen aus der Matrix wird auf der Flyoutseite für eine Schulungsrunde angezeigt.

## <a name="f-score"></a>F-Bewertung

Die F-Bewertung ist ein gewichteter Durchschnitt der Bewertungen für die Genauigkeits- und Rückrufmetriken.  Der Bereich der Bewertungen für diese Metrik liegt zwischen **0** und **1.** Ein Wert näher an **1** gibt an, dass das Modell relevante Elemente genauer erkennt. Die F-Bewertungsmetrik wird im Modelldashboard und auf der Flyoutseite für jede Schulungsrunde angezeigt.

## <a name="margin-of-error"></a>Fehlerrand

Der Fehlerrand ist eine erweiterte Einstellung, wenn Sie einen vorhersagebasierten Codierungsmodus erstellen. Es gibt den Fehlergrad der Leistungsmetriken an (z. B. Umfang, Genauigkeit und Rückruf), der aus dem zufälligen Sampling von Elementen in Ihrem Steuerelementsatz abgeleitet wird. Ein niedrigerer Fehlerrand erfordert einen größeren Steuerelementsatz, um sicherzustellen, dass die Leistungsmetriken des Modells in einen kleineren Bereich fallen. Die Werte für den Rand der Fehler- und Konfidenzstufe helfen auch zu bestimmen, wie viele Elemente in den Steuerelementsatz einbezogen werden. Der Standardwert für den Fehlerrand ist 0,05 oder 5 %.

## <a name="model-stability"></a>Modellstabilität

Die Modellstabilität gibt die Fähigkeit des Modells an, genau vorherzusagen, ob ein Dokument in einem Prüfdateisatz relevant oder nicht relevant ist. Wenn ein Modell instabil ist, müssen möglicherweise weitere Schulungsrunden durchgeführt werden, um die Stabilität des Modells einzuschließen. Wenn das Modell stabil ist, müssen möglicherweise keine weiteren Schulungsrunden durchgeführt werden. Das Modelldashboard gibt den aktuellen Status der Modellstabilität an. Wenn ein Modell stabil ist, haben die Leistungsmetriken ein Level erreicht, das den Einstellungen für das Konfidenzniveau und den Fehlerrand entspricht.

## <a name="overturn-rate"></a>Umdrehungsrate

Die Umdrehungsrate ist der Prozentsatz der Elemente im Prüfdateisatz, bei denen sich das Vorhersageergebnis zwischen Schulungsrunden geändert hat. Ein Modell gilt als stabil, wenn die Umdrehungsrate unter 5 % liegt. Die Übersprungsrate wird im Modelldashboard und auf der Flyoutseite für jede Schulungsrunde angezeigt. Die Überschreitungsrate für die erste Schulungsrunde ist Null, da kein vorheriger Vorhersagewert zum Kippen vorhanden ist.

## <a name="precision"></a>Präzision

Die Genauigkeitsmetrik misst den Anteil der Elemente, die tatsächlich unter den elementen relevant sind, die das Modell vorhergesagt hat. Dies bedeutet, dass Elemente im Steuerelement festlegen, wo die Bezeichnung vom Prüfer als relevant und vom Modell als relevant vorausgesagt wird. Der Bereich der Bewertungen für diese Metrik liegt zwischen **0** und **1.** Ein Wert näher an **1** gibt an, dass das Modell weniger nicht relevante Elemente identifiziert. Die Genauigkeitsmetrik wird im Modelldashboard und auf der Flyoutseite für jede Schulungsrunde angezeigt.

## <a name="prediction-score"></a>Vorhersagebewertung

Dies ist die Bewertung, die ein Modell jedem Dokument in einem Prüfdateisatz zuweist. Die Bewertung basiert auf der Relevanz des Dokuments im Vergleich zum Lernen des Modells aus den Schulungsrunden. Im Allgemeinen werden Elemente mit Vorhersageergebnissen zwischen **0** und **0,5** als nicht relevant betrachtet, und Elemente mit Vorhersageergebnissen zwischen **0,5** und **1** werden als relevant betrachtet. Die Vorhersagebewertung ist in einem Dokumentmetadatenfeld enthalten. Sie können einen Vorhersagefilter verwenden, um die Elemente in einem Prüfdateisatz anzuzeigen, die in einen angegebenen Vorhersagebereich fallen.

## <a name="recall"></a>Erinnern

Die Rückrufmetrik misst den Anteil der Elemente, die das Modell prognostiziert hat, zwischen elementen, die tatsächlich relevant sind. Dies bedeutet, dass Elemente im Steuerelementsatz, für die das modell vorhergesagt wurde, auch vom Prüfer als relevant gekennzeichnet wurden. Der Bereich der Bewertungen für diese Metrik liegt zwischen **0** und **1.** Ein Wert näher an **1** gibt an, dass das Modell einen größeren Teil der relevanten Elemente identifiziert. Die Rückrufmetrik wird im Modelldashboard und auf der Flyoutseite für jede Schulungsrunde angezeigt.

## <a name="review-set"></a>Prüfdateisatz

Ein Prüfdateisatz bietet den Umfang eines vorhersagebasierten Codierungsmodells. Wenn Sie ein neues Modell für den Prüfdateisatz erstellen, werden Elemente für den Steuerelementsatz und Schulungssätze aus dem Prüfdateisatz ausgewählt. Wenn das Modell Vorhersageergebnisse zuweist, weist es diese Bewertungen den Elementen in der Rezension zu. Sie müssen alle Elemente zum Prüfdateisatz hinzufügen, bevor Sie ein Modell für die Vorhersagecodierung erstellen. Wenn Sie Elemente hinzufügen, nachdem Sie ein Modell erstellt haben, wird diesen Elementen keine Vorhersagebewertung zugewiesen.

## <a name="richness"></a>Reichtum

Die Richness-Metrik misst den Prozentsatz der Prüfdateisatzelemente, die das Modell als relevant prognostiziert. Der Bereich der Bewertungen für diese Metrik liegt zwischen **0** und **1.** Die Richness-Metrik wird im Modelldashboard angezeigt.

## <a name="sampled-items"></a>Beispielelemente

Der Begriff *"Stichprobenelemente"* ist ein Verweis auf zufällige Beispiele von Elementen in einem Prüfdateisatz (die Text enthalten), die ausgewählt und dem Steuerelementsatz zugeordnet sind, wenn Sie ein Vorhersagecodierungsmodell erstellen. Für jede Schulungsrunde wird auch ein zufälliges Beispiel von Elementen ausgewählt. Elemente, die für den Steuerelementsatz eines Modells ausgewählt wurden, sind nie in einem Schulungssatz für dasselbe Modell enthalten. Das Gegenteil ist auch der Fall: Schulungssatzelemente sind nie im Steuerelementsatz enthalten.

## <a name="training-set"></a>Schulungssatz

Das Modell wählt nach dem Zufallsprinzip Elemente aus dem Prüfdateisatz aus und fügt sie einem Schulungssatz hinzu. Während einer Schulungsrunde werden Ihnen Elemente aus dem Schulungssatz (zusätzlich zu Elementen aus dem Steuerelementsatz) angezeigt, sodass Sie jedes Element als "relevant" oder "nicht relevant" bezeichnen können. Dieser Bezeichnungs- oder "Schulungs"-Prozess hilft dem Modell, vorherzusagen, welche Elemente in der Rezension relevant oder nicht relevant sind. Jedes Mal, wenn Sie eine Schulungsrunde durchführen, wählt das Modell weitere Elemente aus der Rezension aus und fügt sie dem Schulungssatz für diese Schulungsrunde hinzu. Elemente aus dem Steuerelementsatz werden nie für einen Schulungssatz ausgewählt.
