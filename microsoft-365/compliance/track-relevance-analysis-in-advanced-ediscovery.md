---
title: Nachverfolgen der Relevanzanalyse in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie den Status und die Ergebnisse des Relevanztrainings für Fallprobleme in Advanced eDiscovery anzeigen und interpretieren.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769180"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="f0a9c-103">Nachverfolgen der Relevanzanalyse in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f0a9c-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="f0a9c-104">In Advanced eDiscovery zeigt die Registerkarte Relevanzspur die berechnete Gültigkeit der Relevanzschulung an, die auf der Registerkarte Tag durchgeführt wurde, und gibt den nächsten Schritt im iterativen Schulungsprozess in Relevanz an.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="f0a9c-105">Nachverfolgen des Relevanzschulungsstatus</span><span class="sxs-lookup"><span data-stu-id="f0a9c-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="f0a9c-106">Sehen Sie sich die folgenden Details in Relevanzspur für die Fallprobleme an, wie im folgenden Beispiel eines Dialogfelds **Problemname unten** gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="f0a9c-107">**Bewertung**: Dieser Fortschrittsindikator zeigt, in welchem Umfang die bisher durchgeführte Relevanzschulung das Bewertungsziel hinsichtlich der Fehlermarge erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="f0a9c-108">Der Reichhaltige der Relevanztrainingsergebnisse wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="f0a9c-109">**Schulung**: Diese farbcodete Fortschrittsanzeige und Tooltipps gibt die Stabilität der Relevanztrainingsergebnisse und eine numerische Skalierung an, die die Anzahl der Relevanzschulungsbeispiele angibt, die für jedes Problem markiert sind.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="f0a9c-110">Der Experte überwacht den Fortschritt des iterativen Relevanzschulungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="f0a9c-111">**Batchberechnung**: Diese Statusanzeige enthält Informationen zum Abschluss der Batchberechnung.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="f0a9c-112">**Nächster Schritt**: Zeigt die Empfehlung für den nächsten Schritt an.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="f0a9c-113">Im Beispiel wird eine erfolgreich abgeschlossene Bewertung für ein Problem angezeigt, die durch die Statusanzeige für den abgeschlossenen Farbfortschritt und das Häkchen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="f0a9c-114">Tagging ist im Gange, aber der Fall wird weiterhin als instabil betrachtet (Stabilitätsstatus wird auch in einer QuickInfo angezeigt).</span><span class="sxs-lookup"><span data-stu-id="f0a9c-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="f0a9c-115">Die nächste Schrittempfehlung ist "Schulung".</span><span class="sxs-lookup"><span data-stu-id="f0a9c-115">The next step recommendation is "Training".</span></span> 
  
    ![Relevanz verfolgen Schulungsschritt 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="f0a9c-117">In der erweiterten Ansicht werden zusätzliche Informationen und Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="f0a9c-118">Die angezeigte aktuelle Fehlerspanne ist die Fehlermarge des Rückrufs im aktuellen Bewertungsstatus, wenn die vorhandenen (bereits markierten) Bewertungsdateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="f0a9c-119">Die Bewertungsphase kann umgangen werden, indem sie das Kontrollkästchen **Bewertung** pro Problem und dann für "alle Probleme" ausräumt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="f0a9c-120">Daher gibt es jedoch keine Statistiken für dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="f0a9c-121">> Das Löschen des **Kontrollkästchens Bewertung** kann nur durchgeführt werden, bevor die Bewertung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="f0a9c-122">Wenn in einem Fall mehrere Probleme vorhanden sind, wird die Bewertung nur umgangen, wenn das Kontrollkästchen für jedes Problem behoben ist.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="f0a9c-123">Wenn die Bewertung nicht mit dem ersten Beispielsatz von Dateien abgeschlossen ist, kann die Bewertung der nächste Schritt zum Markieren weiterer Dateien sein.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="f0a9c-124">In **Relevanzspur** geben die Fortschrittsanzeige und die QuickInfo der Schulung die geschätzte Anzahl zusätzlicher Beispiele an, die zum Erreichen der \> Stabilität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="f0a9c-125">Diese Schätzung bietet eine Richtlinie für die erforderlichen zusätzlichen Schulungen.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Relevanz-Track-Schulung](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="f0a9c-127">Wenn Sie das Tagging fertig haben und die Schulung fortsetzen müssen, klicken Sie auf **Schulung**.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="f0a9c-128">Ein weiterer Beispielsatz von Dateien wird aus dem geladenen Dateisatz für zusätzliche Schulungen generiert.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="f0a9c-129">Anschließend werden Sie zur Registerkarte Tag zurückgegeben, um weitere Dateien zu kennzeichnen und zu schulen.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="f0a9c-130">Erreichen stabiler Schulungsstufen</span><span class="sxs-lookup"><span data-stu-id="f0a9c-130">Reaching stable training levels</span></span>

<span data-ttu-id="f0a9c-131">Nachdem die Bewertungsdateien ein stabiles Schulungsniveau erreicht haben, ist Advanced eDiscovery für die Batchberechnung bereit.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0a9c-132">In der Regel ist nach drei stabilen Schulungsbeispielen der nächste Schritt "Batchberechnung".</span><span class="sxs-lookup"><span data-stu-id="f0a9c-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="f0a9c-133">Es kann Ausnahmen geben, z. B. wenn änderungen am Tagging von Dateien aus früheren Beispielen vorgenommen wurden oder wenn Seeddateien hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="f0a9c-134">Ausführen von Batchberechnungen</span><span class="sxs-lookup"><span data-stu-id="f0a9c-134">Performing Batch calculation</span></span>

<span data-ttu-id="f0a9c-135">Die Batchberechnung wird als nächster Schritt nach erfolgreichem Abschluss der Schulung ausgeführt (wenn ein stabiler Schulungsstatus in der Statusleiste angezeigt wird, ein Häkchen und ein Stable-Status in der QuickInfo).) Die Batchberechnung wendet die während der Relevanzschulung erworbenen Kenntnisse auf die gesamte Dateigesamtheit an, um die Relevanz der Dateien zu bewerten und Relevanzergebnisse zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="f0a9c-136">Wenn mehr als ein Problem vor liegt, wird die Batchberechnung pro Problem ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="f0a9c-137">Während der Batchberechnung wird der Fortschritt überwacht, während alle Dateien verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="f0a9c-138">Hier ist der empfohlene nächste Schritt "None", der angibt, dass derzeit keine zusätzlichen iterativen Relevanzschulungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="f0a9c-139">Die nächste Phase ist die **Registerkarte Relevanz \> entscheiden.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="f0a9c-140">Wenn Sie neue Dateien nach der Batchberechnung importieren möchten, kann der Administrator die importierten Dateien einer neuen Last hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0a9c-141">Wenn Sie während **der Batchberechnung** auf Abbrechen klicken, speichert der Prozess, was bereits ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="f0a9c-142">Wenn Sie die Batchberechnung erneut ausführen, wird der Vorgang ab dem letzten ausgeführten Punkt fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="f0a9c-143">Bewerten der Taggingkonsistenz</span><span class="sxs-lookup"><span data-stu-id="f0a9c-143">Assessing tagging consistency</span></span>

<span data-ttu-id="f0a9c-144">Wenn beim Tagging von Dateien Inkonsistenzen vorhanden sind, kann sich dies auf die Analyse auswirken.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="f0a9c-145">Der Advanced eDiscovery-Taggingkonsistenzprozess kann verwendet werden, wenn die Ergebnisse nicht optimal sind oder die Konsistenz in Frage kommt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="f0a9c-146">Es wird eine Liste möglicher inkonsistent markierter Dateien zurückgegeben, die bei Bedarf überprüft und erneut erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0a9c-147">Nach sieben oder mehr Schulungsrunden nach der Bewertung  kann die Kennzeichnungskonsistenz unter \> **Relevanzspurproblem** Detaillierte Ergebnisse \>  \>  \> **Schulungsfortschritt angezeigt werden.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="f0a9c-148">Diese Überprüfung wird für ein Problem nach dem anderen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="f0a9c-149">Erweitern **Sie in \> Relevanzspur** die Zeile eines Problems.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="f0a9c-150">Klicken Sie rechts neben **Nächster Schritt** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="f0a9c-151">Wählen **Sie nach sieben Schulungsbeispielen** die Option Inkonsistenzen als **Nächster** Schritt markieren aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="f0a9c-152">Wählen **Sie Tag inconsistencies aus.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="f0a9c-153">Die **Registerkarte Tag** wird geöffnet und zeigt eine Liste der Inkonsistenzen an, die bei Bedarf neu zentriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="f0a9c-154">Klicken Sie **auf Berechnen,** um die Änderungen zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="f0a9c-155">Der nächste Schritt nach dem Taggen von Inkonsistenzen ist "Training".</span><span class="sxs-lookup"><span data-stu-id="f0a9c-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="f0a9c-156">Anzeigen und Verwenden von Relevanzergebnissen</span><span class="sxs-lookup"><span data-stu-id="f0a9c-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="f0a9c-157">Erweitern Sie **auf \> der** Registerkarte Relevanzspur die Zeile eines Problems, und klicken Sie neben **Detaillierte** Ergebnisse auf **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="f0a9c-158">Die Detaillierten Ergebnisbereiche werden angezeigt, wie unten gezeigt und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Detaillierte Ergebnisse der Relevanzschulung](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="f0a9c-160">Zusammenfassung des Taggings</span><span class="sxs-lookup"><span data-stu-id="f0a9c-160">Tagging summary</span></span>

 <span data-ttu-id="f0a9c-161">Im unten gezeigten Beispiel zeigt die **Zusammenfassung tagging** Summen für jeden Bewertungs-, Schulungs- und Nachholdateitaggingprozess an.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Zusammenfassung der Relevanz-Track-Tagging](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="f0a9c-163">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0a9c-163">Keywords</span></span>

<span data-ttu-id="f0a9c-164">Ein Schlüsselwort ist eine eindeutige Zeichenfolge, ein Wort, eine Phrase oder eine Sequenz von Wörtern in einer Datei, die von Advanced eDiscovery als wichtiger Indikator dafür identifiziert wird, ob eine Datei relevant ist.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="f0a9c-165">Die Spaltenliste "Include" listet Schlüsselwort und Gewichtungen in Dateien auf, die als relevant gekennzeichnet sind, und die Spalten "Exclude" listet Schlüsselwörter und Gewichtungen in Dateien auf, die als Nicht relevant gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="f0a9c-166">Advanced eDiscovery weist negative oder positive Schlüsselwortgewichtungswerte zu.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="f0a9c-167">Je höher die Gewichtung, desto höher ist die Wahrscheinlichkeit, dass einer Datei, in der das Schlüsselwort angezeigt wird, während der Batchberechnung eine höhere Relevanznote zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="f0a9c-168">Die Advanced eDiscovery-Liste mit Schlüsselwörtern kann verwendet werden, um eine liste zu ergänzen, die von einem Experten erstellt wurde, oder als indirekte Überprüfung der Sanität an jedem Punkt des Dateiüberprüfungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="f0a9c-169">Schulungsfortschritt</span><span class="sxs-lookup"><span data-stu-id="f0a9c-169">Training progress</span></span>

<span data-ttu-id="f0a9c-170">Der **Bereich Schulungsfortschritt** enthält ein Schulungsfortschrittsdiagramm und eine Qualitätsindikatoranzeige, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Relevanz Nachverfolgen des Schulungsfortschritts](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="f0a9c-172">**Indikator für die** Schulungsqualität : Zeigt die Bewertung der Taggingkonsistenz wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="f0a9c-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="f0a9c-173">**Gut:** Dateien werden konsistent markiert.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="f0a9c-174">(Grünes Licht wird angezeigt)</span><span class="sxs-lookup"><span data-stu-id="f0a9c-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="f0a9c-175">**Medium**: Einige Dateien können inkonsistent markiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="f0a9c-176">(Gelbes Licht angezeigt)</span><span class="sxs-lookup"><span data-stu-id="f0a9c-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="f0a9c-177">**Warnung:** Viele Dateien können inkonsistent markiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="f0a9c-178">(Rotes Licht angezeigt)</span><span class="sxs-lookup"><span data-stu-id="f0a9c-178">(Red light displayed)</span></span>

<span data-ttu-id="f0a9c-179">**Abbildung des Schulungsfortschritts**: Zeigt den Grad der Relevanztrainingsstabilität nach vielen Relevanztrainingszyklen im Vergleich zum F-Measure-Wert an.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="f0a9c-180">Während wir uns von links nach rechts im Diagramm bewegen, wird das Konfidenzintervall verengt und zusammen mit dem F-Measure von Advanced eDiscovery Relevance verwendet, um die Stabilität zu bestimmen, wenn die Relevanztrainingsergebnisse optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0a9c-181">Relevanz verwendet F2, eine F-Measure-Metrik, bei der Rückruf doppelt so viel Gewicht wie Precision erhält.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="f0a9c-182">Für Fälle mit hoher Reicherkeit (über 25 %) verwendet relevanz F1 (Verhältnis 1:1).</span><span class="sxs-lookup"><span data-stu-id="f0a9c-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="f0a9c-183">Das F-Measure-Verhältnis kann  unter Relevanzeinrichtung Erweiterte \> **Einstellungen konfiguriert werden.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="f0a9c-184">Ergebnisse der Batchberechnung</span><span class="sxs-lookup"><span data-stu-id="f0a9c-184">Batch calculation results</span></span>

<span data-ttu-id="f0a9c-185">Der **Ergebnisbereich** Batchberechnung enthält die Anzahl der Dateien, die wie folgt für relevanzpunktiert wurden:</span><span class="sxs-lookup"><span data-stu-id="f0a9c-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="f0a9c-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-186">**Success**</span></span>
  
- <span data-ttu-id="f0a9c-187">**Leer**: Enthält keinen Text, z. B. nur Leerzeichen/Registerkarten</span><span class="sxs-lookup"><span data-stu-id="f0a9c-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="f0a9c-188">**Failed**: Due to excessive size or could not be read</span><span class="sxs-lookup"><span data-stu-id="f0a9c-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="f0a9c-189">**Ignoriert:** Aufgrund einer übermäßig hohen Größe</span><span class="sxs-lookup"><span data-stu-id="f0a9c-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="f0a9c-190">**Nebulous**: Enthält bedeutungslosen Text oder keine für das Problem relevanten Features.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0a9c-191">Leer, Fehlgeschlagen, Ignoriert oder Nebulous erhält die Relevanznote -1.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="f0a9c-192">Schulungsstatistiken</span><span class="sxs-lookup"><span data-stu-id="f0a9c-192">Training statistics</span></span>

<span data-ttu-id="f0a9c-193">Im **Bereich Schulungsstatistik** werden Statistiken und Diagramme basierend auf den Ergebnissen von Advanced eDiscovery Relevance Training angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Relevanz nachverfolgen von Schulungsstatistiken](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="f0a9c-195">Diese Ansicht zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f0a9c-195">This view shows the following:</span></span>
  
- <span data-ttu-id="f0a9c-196">**Review-Recall-Verhältnis:** Vergleich der Ergebnisse nach Relevanzbewertung in einer hypothetisch linearen Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="f0a9c-197">Der Rückruf wird geschätzt, wenn die Größe des Überprüfungssatzs festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="f0a9c-198">**Parameter**: Kumulierte berechnete Statistiken im Zusammenhang mit dem Überprüfungssatz in Bezug auf die Dateigesamtheit für den gesamten Fall.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="f0a9c-199">**Review**: Prozentsatz der Dateien, die basierend auf dieser Stichwahl überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="f0a9c-200">**Rückruf**: Prozentsatz der relevanten Dateien im Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="f0a9c-201">**Verteilung nach Relevanzpunktzahl:** Dateien in der dunkelgrauen Anzeige auf der linken Seite liegen unterhalb der Cutoff-Bewertung.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="f0a9c-202">Eine QuickInfo zeigt die Relevanzbewertung und den zugehörigen Prozentsatz der Dateien in der Überprüfungsdatei im Verhältnis zu den Gesamtdateien an.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
