---
title: Deversion des Relevanzmoduls in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Das Relevanzmodul in Advanced eDiscovery wird am 10. März 2021 eingestellt. In diesem Artikel wird erläutert, was sie tun müssen, bevor die Relevanz eingestellt wird. Insbesondere müssen Sie alle noch nicht fertig gestellten Modelle fertig gestellt haben, indem Sie die Batchberechnung ausführen, damit Sie die Metadaten aus dem Modell beibehalten können.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122529"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Deversion des Relevanzmoduls in Advanced eDiscovery

Am 10. März 2021 wird das Relevanzmodul in Advanced eDiscovery zurück weiterentwickelt. Diese Deversion bedeutet, dass Organisationen keinen Zugriff mehr auf das Relevanzmodul haben (indem sie die Relevanz des Überprüfungssatzs in einem  >   Advanced eDiscovery-Fall verwalten) oder auf vorhandene Relevanzmodelle zugreifen können. Das aktuelle Relevanzmodul, das eingestellt wird, wird in Q2 CY 2021 durch eine neue Vorhersagecodierungslösung ersetzt. Mit dieser neuen Funktion können Organisationen ihre eigenen Vorhersagecodierungsmodelle in einem einfacheren und intuitiveren Workflow erstellen.

Zur Vorbereitung auf diese bevorstehende Ausmusterung wird empfohlen, dass Organisationen, die das Relevanzmodul verwenden, die Ausgabe ihres Modells vor dem Ausmusterungsdatum exportieren, indem sie eine Batchberechnung für alle vorhandenen Modelle ausführen. Alle Relevanzbewertung aus Ihrem Modell wird dauerhaft im entsprechenden Überprüfungssatz gespeichert und kann beim Exportieren von Dokumenten darauf zugegriffen werden. Relevanzergebnisse werden auch als Metadaten in der Ladedatei beibehalten. Außerdem können Sie weiterhin Inhalte im Überprüfungssatz basierend auf der Relevanzbewertung filtern und haben Zugriff auf alle Metadaten, die von Ihren Relevanzmodellen erstellt werden.

## <a name="complete-unfinished-models"></a>Vollständige noch nicht fertig gestellte Modelle

Führen Sie für alle noch nicht abgeschlossenen Relevanzmodelle die Bewertung, Schulung und Batchberechnung aus, damit Sie das Modell auf die Dokumente in einem Überprüfungssatz anwenden können. Wenn Sie die Batchberechnung abschließen, werden die Informationen nach dem Beendigungsdatum des Relevanzmoduls beibehalten.

Hier sind die Schritte zum Abschließen noch nicht fertig gestellter Modelle:

1. Schulen Sie Ihr Modell, bis es stabilisiert und für die Batchberechnung bereit ist. Siehe [Tagging und Relevanztraining.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   Der folgende Screenshot zeigt ein Modul, das für eine Batchberechnung bereit ist. Beachten Sie, dass die Bewertung und Schulung abgeschlossen ist und der nächste Schritt das Ausführen der Batchberechnung ist.

   ![Screenshot des Modells, das für die Batchberechnung bereit ist](../media/ReadyForBatchCalculation.png)

2. Führen Sie die Batchberechnung aus. Siehe ["Ausführen der Batchberechnung".](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. Überprüfen Sie, ob die Batchberechnung erfolgreich war. Siehe [Ergebnisse der Batchberechnung.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)

Wenn Sie Hilfe beim Abschließen noch nicht fertig gestellter Relevanzmodelle erhalten, wenden Sie sich an den Microsoft-Support.
