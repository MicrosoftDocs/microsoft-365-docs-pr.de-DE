---
title: Modul für prädiktive Codierung für Advanced eDiscovery (Vorschau)
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
description: Das neue Modul für die vorhersagebasierte Codierung in Advanced eDiscovery verwendet maschinelles Lernen, um Elemente in einem Prüfdateisatz so zu analysieren, dass die Elemente, die für Ihren Fall oder Ihre Untersuchung relevant sind, vorhersageweise analysiert werden.
ms.openlocfilehash: 3c8fbd75bd585dd6ae722bf17deea906611d8df6
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822038"
---
# <a name="learn-about-predictive-coding-in-advanced-ediscovery-preview"></a>Erfahren Sie mehr über Vorhersagecodierung in Advanced eDiscovery (Vorschau)

Das Modul für prädiktive Codierung in Advanced eDiscovery verwendet die intelligenten Maschinellen Lernfunktionen, um die Menge der zu überprüfenden Inhalte zu reduzieren. Predictive Coding hilft Ihnen dabei, große Mengen von Fallinhalten auf eine relevante Gruppe von Elementen zu reduzieren und zu überschreiben, die Sie für die Überprüfung priorisieren können. Dazu erstellen und schulen Sie Ihre eigenen Modelle für die Vorhersagecodierung, die Ihnen helfen, die Überprüfung der relevantesten Elemente in einem Prüfdateisatz zu priorisieren.

Das Modul für die vorhersagebasierte Codierung wurde entwickelt, um die Komplexität der Verwaltung eines Modells innerhalb eines Prüfdateisatzes zu optimieren und einen iterativen Ansatz für die Schulung Ihres Modells bereitzustellen, damit Sie schneller mit den Machine Learning-Funktionen in Advanced eDiscovery beginnen können. Um zu beginnen, können Sie ein Modell erstellen und bis zu 50 Elemente als relevant oder nicht relevant bezeichnen. Das System verwendet diese Schulung, um Vorhersageergebnisse auf jedes Element im Prüfdateisatz anzuwenden. Auf diese Weise können Sie Elemente basierend auf der Vorhersagebewertung filtern, sodass Sie zuerst die relevantesten (oder nicht relevanten) Elemente überprüfen können. Wenn Sie Modelle mit höheren Genauigkeits- und Rückrufraten trainieren möchten, können Sie die Bezeichnung von Elementen in nachfolgenden Schulungsrunden fortsetzen, bis sich das Modell stabilisiert.  

## <a name="the-predictive-coding-workflow"></a>Der Workflow für die Vorhersagecodierung

Hier finden Sie eine Übersicht und Beschreibung der einzelnen Schritte des Workflows für die Vorhersagecodierung. Eine ausführlichere Beschreibung der Konzepte und der Terminologie des Vorhersagecodierungsprozesses finden Sie in der Referenz zur [prädiktiven Codierung.](predictive-coding-reference.md)

![Workflow für prädiktive Codierung](..\media\PredictiveCodingWorkflow.png)

1. **Erstellen Sie ein neues Modell für die Vorhersagecodierung im Prüfdateisatz.** Der erste Schritt besteht darin, ein neues Vorhersagecodierungsmodell im Prüfdateisatz zu erstellen. Sie müssen mindestens 2.000 Elemente im Prüfdateisatz haben, um ein Modell zu erstellen. Nachdem Sie ein Modell erstellt haben, bestimmt das System die Anzahl der Elemente, die als *Steuerelementsatz* verwendet werden sollen. Der Steuerelementsatz wird während des Schulungsprozesses verwendet, um die Vorhersageergebnisse zu bewerten, die das Modell Elementen mit der Bezeichnung zuweist, die Sie während der Schulungsrunden ausführen. Die Größe des Steuerelementsatzes basiert auf der Anzahl der Elemente im Prüfdateisatz sowie der Konfidenzstufe und dem Rand von Fehlerwerten, die beim Erstellen des Modells festgelegt werden. Elemente im Steuerelementsatz ändern sich nie und sind für Benutzer nicht identifizierbar.

   Weitere Informationen finden Sie unter [Erstellen eines vorhersagebasierten Codierungsmodells.](predictive-coding-create-model.md)

2. **Schließen Sie die erste Schulungsrunde ab, indem Sie Elemente als relevant oder nicht relevant bezeichnen.** Der nächste Schritt besteht darin, das Modell zu trainieren, indem Sie mit der ersten Schulungsrunde beginnen. Wenn Sie eine Schulungsrunde starten, wählt das Modell nach dem Zufallsprinzip zusätzliche Elemente aus dem Prüfdateisatz aus, der als *Schulungssatz* bezeichnet wird. Diese Elemente (sowohl aus dem Steuerelementsatz als auch aus dem Schulungssatz) werden Ihnen angezeigt, sodass Sie jedes Element als "relevant" oder "nicht relevant" bezeichnen können. Die Relevanz basiert auf dem Inhalt des Elements und nicht auf den Dokumentmetadaten. Nachdem Sie den Bezeichnungsprozess in der Schulungsrunde abgeschlossen haben, wird das Modell basierend auf der Bezeichnung der Elemente im Schulungssatz "lernen". Basierend auf dieser Schulung verarbeitet das Modell die Elemente im Prüfdateisatz und wendet jeweils eine Vorhersagebewertung an.

   Weitere Informationen finden Sie unter ["Trainieren eines vorhersagebasierten Codierungsmodells".](predictive-coding-train-model.md)

3. **Wenden Sie den Filter für die Vorhersagebewertung auf Elemente im Prüfdateisatz an.** Nach Abschluss des vorherigen Schulungsschritts besteht der nächste Schritt darin, den Filter für die Vorhersagebewertung auf die Elemente in der Rezension anzuwenden, um die elemente anzuzeigen, die das Modell als "am relevantesten" festgelegt hat (alternativ können Sie auch einen Vorhersagefilter verwenden, um Elemente anzuzeigen, die "nicht relevant" sind). Wenn Sie den Vorhersagefilter anwenden, geben Sie einen Bereich von Vorhersageergebnissen an, die gefiltert werden sollen. Der Bereich der Vorhersageergebnisse liegt zwischen **0** und **1,** wobei **0** "nicht relevant" und **1** relevant sind. Im Allgemeinen werden Elemente mit Vorhersageergebnissen zwischen **0** und **0,5** als "nicht relevant" betrachtet, und Elemente mit Vorhersageergebnissen zwischen **0,5** und **1** werden als relevant betrachtet.

   Weitere Informationen finden Sie unter [Anwenden eines Vorhersagefilters auf einen Prüfdateisatz.](predictive-coding-apply-prediction-filter.md)

4. **Führen Sie weitere Schulungsrunden durch, bis das Modell stabil ist.** Sie können zusätzliche Schulungsrunden durchführen, wenn Sie ein Modell mit einer höheren Genauigkeit der Vorhersage und erhöhten Rückrufraten erstellen möchten. *Die Rückrufrate* misst den Anteil der Elemente, die das Modell prognostiziert hat, zwischen elementen, die tatsächlich relevant sind (die Elemente, die Sie während der Schulung als relevant markiert haben). Die Bewertung der Rückrufrate liegt zwischen **0** und **1.** Ein Wert näher an **1** gibt an, dass das Modell relevantere Elemente identifiziert. In einer neuen Schulungsrunde bezeichnen Sie zusätzliche Elemente in einem neuen Schulungssatz. Nachdem Sie diese Schulungsrunde abgeschlossen haben, wird das Modell basierend auf neuen Erkenntnissen aus Ihrer letzten Runde der Bezeichnungselemente im Schulungssatz aktualisiert. Das Modell verarbeitet die Elemente im Prüfdateisatz erneut und wendet neue Vorhersageergebnisse an. Sie können die Schulung fortsetzen, bis sich Ihr Modell stabilisiert. Ein Modell gilt als stabil, wenn die Änderungsrate nach der letzten Schulungsrunde unter 5 % liegt. *Die Änderungsrate* wird als Prozentsatz der Elemente in einem Prüfdateisatz definiert, bei dem sich die Vorhersagebewertung zwischen Schulungsrunden geändert hat. Das Dashboard für die Vorhersagecodierung zeigt Informationen und Statistiken an, mit denen Sie die Stabilität eines Modells bewerten können.

5. **Wenden Sie den Filter für die "endgültige" Vorhersagebewertung an, um festgelegte Elemente zu überprüfen, um die Überprüfung zu priorisieren.** Nachdem Sie alle Schulungsrunden abgeschlossen und das Modell stabilisiert haben, besteht der letzte Schritt darin, die endgültige Vorhersagebewertung auf den Prüfdateisatz anzuwenden, um die Überprüfung relevanter und nicht relevanter Elemente zu priorisieren. Dies ist die gleiche Aufgabe, die Sie in Schritt 3 ausgeführt haben, aber an diesem Punkt ist das Modell stabil, und Sie planen keine weiteren Schulungsrunden.
