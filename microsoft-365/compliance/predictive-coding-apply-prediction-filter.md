---
title: Anwenden des Filter für die Vorhersagebewertung auf Elemente in einem Prüfdateisatz
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
description: Verwenden Sie einen Filter für die Vorhersagebewertung, um Elemente anzuzeigen, die von einem vorhersagebasierten Codierungsmodell als relevant oder nicht relevant prognostiziert werden.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822529"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Anwenden eines Filter für die Vorhersagebewertung auf einen Prüfdateisatz (Vorschau)

Nachdem Sie in Advanced eDiscovery ein Modell für die prädiktive Codierung erstellt und so trainiert haben, dass es stabil ist, können Sie den Filter für die Vorhersagebewertung anwenden, um die vom Modell ermittelten Prüfdateisatzelemente anzuzeigen, die relevant (oder nicht relevant) sind. Wenn Sie ein Modell erstellen, wird auch ein entsprechender Filter für die Vorhersagebewertung erstellt. Sie können diesen Filter verwenden, um Elemente anzuzeigen, denen eine Vorhersagebewertung innerhalb eines bestimmten Bereichs zugewiesen ist. Im Allgemeinen sind Vorhersageergebnisse zwischen **0** und **5** Elementen zugewiesen, die vom Modell vorhergesagt wurden, sind nicht relevant. Elemente, denen Vorhersageergebnisse zwischen **0,5** und **1,0** zugewiesen wurden, sind Elemente, die vom Modell vorhergesagt wurden, sind relevant.

Hier sind zwei Möglichkeiten, wie Sie den Filter für die Vorhersagebewertung verwenden können:

- Priorisieren Der Überprüfung von Elementen in einem Prüfdateisatz, den das Modell vorausgesagt hat, ist relevant.

- Elemente aus dem Prüfdateisatz, den das Modell vorhergesagt hat, zu entfernen, sind nicht relevant. Alternativ können Sie den Filter für die Vorhersagebewertung verwenden, um die Überprüfung von nicht relevanten Elementen zu depriorisieren.

## <a name="before-you-apply-a-prediction-score-filter"></a>Bevor Sie einen Filter für die Vorhersagebewertung anwenden

- Erstellen Sie ein Modell für die Vorhersagecodierung, sodass ein entsprechender Filter für die Vorhersagebewertung erstellt wird.

- Sie können einen Filter für die Vorhersagebewertung nach einer der Schulungsrunden anwenden. Sie können jedoch warten, nachdem Sie mehrere Runden ausgeführt haben, oder bis das Modell stabil ist, bevor Sie den Filter für die Vorhersagebewertung verwenden.

## <a name="apply-a-prediction-score-filter"></a>Anwenden eines Filter für die Vorhersagebewertung

1. Öffnen Sie im Microsoft 365 Compliance Center die Advanced eDiscovery Fall, wählen Sie die Registerkarte **"Prüfdateisätze"** aus, und öffnen Sie dann den Prüfdateisatz.

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

  > [!TIP]
  > Um die tatsächliche Vorhersagebewertung anzuzeigen, die einem Dokument zugewiesen ist, können Sie im Lesebereich auf die Registerkarte **"Metadaten"** klicken. Die Vorhersageergebnisse für alle Modelle im Prüfdateisatz werden in der **RelevanceScores-Metadateneigenschaft** angezeigt.

## <a name="more-information"></a>Weitere Informationen

- Weitere Informationen zur Verwendung von Filtern finden Sie unter [Abfragen und Filtern von Inhalten in einem Prüfdateisatz.](review-set-search.md)
