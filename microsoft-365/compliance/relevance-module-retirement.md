---
title: Einstellung des Relevanzmoduls in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Das Relevanzmodul in Advanced eDiscovery wird am 10. März 2021 eingestellt. In diesem Artikel wird erläutert, was Sie tun müssen, bevor die Relevanz eingestellt wird. Insbesondere müssen alle nicht fertig gestellten Modelle fertig gestellt werden, indem Batchberechnungen ausgeführt werden, damit Sie die Metadaten aus dem Modell beibehalten können.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821997"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Einstellung des Relevanzmoduls in Advanced eDiscovery

Am 10. März 2021 werden wir das Relevanzmodul in Advanced eDiscovery zurückziehen. Diese Einstellung bedeutet, dass Organisationen keinen Zugriff mehr auf das Relevanzmodul haben (indem sie den **Prüfdateisatz**  >  **"Relevanz"** in einem Advanced eDiscovery Fall verwalten) oder auf vorhandene Relevanzmodelle zugreifen können. Das aktuelle Relevanzmodul, das eingestellt wird, wird in Q2 CY 2021 durch eine neue Lösung für die Vorhersagecodierung ersetzt. Mit dieser neuen Funktionalität können Organisationen ihre eigenen Modelle für die Vorhersagecodierung in einem einfacheren und intuitiveren Workflow erstellen.

Um sich auf diese bevorstehende Einstellung vorzubereiten, empfehlen wir Organisationen, die das Relevanzmodul verwenden, die Ausgabe ihres Modells vor dem Einstellungsdatum zu exportieren, indem Sie eine Batchberechnung für alle vorhandenen Modelle ausführen. Alle Relevanzbewertungen aus Ihrem Modell werden dauerhaft im entsprechenden Prüfdateisatz gespeichert und können beim Exportieren von Dokumenten abgerufen werden. Relevanzbewertungen werden auch als Metadaten in der Ladedatei beibehalten. Außerdem können Sie weiterhin Inhalte im Prüfdateisatz basierend auf der Relevanzbewertung filtern und haben Zugriff auf alle Metadaten, die von Ihren Relevanzmodellen erstellt werden.

## <a name="complete-unfinished-models"></a>Vollständige nicht fertige Modelle

Führen Sie für alle nicht fertig gestellten Relevanzmodelle die Bewertung, Schulung und Batchberechnung durch, damit Sie das Modell auf die Dokumente in einem Prüfdateisatz anwenden können. Wenn Sie die Batchberechnung abschließen, bleiben die Informationen nach dem Einstellungsdatum des Relevanzmoduls erhalten.

Hier sind die Schritte zum Abschließen aller nicht fertig gestellten Modelle:

1. Schulen Sie Ihr Modell, bis es stabil ist und für die Batchberechnung bereit ist. Siehe ["Tagging" und "Relevanzschulung".](tagging-and-relevance-training-in-advanced-ediscovery.md)

   Der folgende Screenshot zeigt ein Modul, das für eine Batchberechnung bereit ist. Beachten Sie, dass die Bewertung und Schulung abgeschlossen ist und der nächste Schritt die Batchberechnung ist.

   ![Screenshot des Modells, das für die Batchberechnung bereit ist](../media/ReadyForBatchCalculation.png)

2. Führen Sie die Batchberechnung aus. Weitere Informationen finden Sie unter [Ausführen der Batchberechnung.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. Stellen Sie sicher, dass die Batchberechnung erfolgreich war. Siehe [Batchberechnungsergebnisse.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)

Wenn Sie Hilfe zum Abschließen nicht fertiger Relevanzmodelle haben, wenden Sie sich an den Microsoft-Support.
