---
title: Tagging und Bewertung in Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Überprüfen Sie die Schritte zum Durchführen von Bewertungsschulungen, einschließlich tagging dateien, und überprüfen Sie die Bewertungsergebnisse in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769190"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="122d8-103">Tagging und Bewertung im Relevanzmodul in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="122d8-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="122d8-104">In diesem Abschnitt wird das Verfahren für die Bewertung im Relevanzmodul in Advanced eDiscovery beschrieben.</span><span class="sxs-lookup"><span data-stu-id="122d8-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="122d8-105">Durchführen von Bewertungsschulungen und -analysen</span><span class="sxs-lookup"><span data-stu-id="122d8-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="122d8-106">Klicken Sie **auf der Registerkarte \> Relevanzspur** auf **Bewertung,** um die Fallbewertung zu starten.</span><span class="sxs-lookup"><span data-stu-id="122d8-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="122d8-107">In diesem Verfahren wird beispielsweise ein Beispielbewertungssatz von 500 Dateien erstellt, und die Registerkarte **Tag** wird angezeigt, die den Tagging-Bereich, den angezeigten Dateiinhalt und andere Taggingoptionen enthält.</span><span class="sxs-lookup"><span data-stu-id="122d8-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Registerkarte Relevanztag für die Bewertung](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="122d8-109">Überprüfen Sie jede Datei im Beispiel, bestimmen Sie die Relevanz der Datei für jedes Fallproblem, und markieren Sie die Datei mithilfe der Schaltflächen Relevanz (R), Nicht relevant (NR) und Überspringen im Bereich **Tagging.**</span><span class="sxs-lookup"><span data-stu-id="122d8-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="122d8-110">Für die Bewertung sind 500 markierte Dateien erforderlich.</span><span class="sxs-lookup"><span data-stu-id="122d8-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="122d8-111">Wenn Dateien "übersprungen" werden, erhalten Sie weitere Zu markierende Dateien.</span><span class="sxs-lookup"><span data-stu-id="122d8-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="122d8-112">Klicken Sie nach dem Taggen aller Dateien im Beispiel auf **Berechnen**.</span><span class="sxs-lookup"><span data-stu-id="122d8-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="122d8-113">Der aktuelle Fehlerrand und der Aktuelle Fehlerreichtheit der Bewertung werden berechnet und auf der Registerkarte **Relevanzspur** mit erweiterten Details pro Problem angezeigt, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="122d8-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="122d8-114">Weitere Details zu diesem Dialogfeld finden Sie im Abschnitt [Überprüfung der Bewertungsergebnisse.](#reviewing-assessment-results)</span><span class="sxs-lookup"><span data-stu-id="122d8-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Relevanzspur – Bewertung](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="122d8-116">Standardmäßig wird empfohlen, mit dem standardmäßigen Nächsten Schritt fortzufahren, wenn der Bewertungsfortschrittsindikator für das Problem abgeschlossen ist, der angibt, dass das Bewertungsbeispiel überprüft wurde und genügend relevante Dateien markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="122d8-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="122d8-117">> Wenn Sie andernfalls die Ergebnisse  der Registerkarte Nachverfolgen anzeigen und den Fehlerrand  und den nächsten Schritt steuern möchten, klicken Sie auf Neben nächstem Schritt **ändern,** wählen Sie Bewertung fortsetzen **aus,** und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="122d8-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="122d8-118">Klicken **Sie rechts** neben dem Kontrollkästchen **Bewertung** auf Ändern, um Bewertungsparameter pro Problem anzeigen und angeben zu können.</span><span class="sxs-lookup"><span data-stu-id="122d8-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="122d8-119">Wie **im folgenden Beispiel gezeigt,** wird ein Bewertungsebenendialogfeld für jedes Problem angezeigt:</span><span class="sxs-lookup"><span data-stu-id="122d8-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Fallproblem auf Bewertungsebene](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="122d8-121">Die folgenden Parameter für das Problem werden im Dialogfeld Bewertungsebene berechnet **und** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="122d8-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="122d8-122">**Zielfehlermarge für Rückrufschätzungen**: Basierend auf diesem Wert wird die geschätzte Anzahl zusätzlicher Dateien berechnet, die für die Überprüfung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="122d8-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="122d8-123">Die für den Rückruf verwendete Marge ist größer als 75 % und mit einem Konfidenzniveau von 95 %.</span><span class="sxs-lookup"><span data-stu-id="122d8-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="122d8-124">**Zusätzliche Bewertungsdateien erforderlich:** Gibt an, wie viele weitere Dateien erforderlich sind, wenn die Anforderungen der aktuellen Fehlerspanne nicht erfüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="122d8-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="122d8-125">So passen Sie den aktuellen Fehlerrand an, und sehen Sie sich die Auswirkungen verschiedener Fehlerränder (pro Problem) an:</span><span class="sxs-lookup"><span data-stu-id="122d8-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="122d8-126">Wählen Sie **in der Liste** Problem auswählen ein Problem aus.</span><span class="sxs-lookup"><span data-stu-id="122d8-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="122d8-127">Geben **Sie unter Zielfehlermarge für Rückrufschätzungen** einen neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="122d8-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="122d8-128">Klicken **Sie auf Werte aktualisieren,** um die Auswirkungen der Anpassungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="122d8-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="122d8-129">Klicken **Sie im** Dialogfeld **Bewertungsebene** auf Erweitert, um die folgenden zusätzlichen Parameter und Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="122d8-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Erweiterte Ansicht "Assessment Level Case Issue"](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="122d8-131">**Geschätzter Reichhaltiger**: Geschätzter Reichhaltiger Wert gemäß den aktuellen Bewertungsergebnissen</span><span class="sxs-lookup"><span data-stu-id="122d8-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="122d8-132">**Für den angenommenen Rückruf**: Standardmäßig gilt die Zielfehlermarge für Rückrufe über 75 %.</span><span class="sxs-lookup"><span data-stu-id="122d8-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="122d8-133">Klicken **Sie auf Bearbeiten,** wenn Sie diesen Parameter ändern und den Fehlerrand für einen anderen Bereich von Rückrufwerten steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="122d8-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="122d8-134">**Konfidenzniveau:** Standardmäßig beträgt die empfohlene Fehlermarge für die Konfidenz 95 %.</span><span class="sxs-lookup"><span data-stu-id="122d8-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="122d8-135">Klicken **Sie auf Bearbeiten,** wenn Sie diesen Parameter ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="122d8-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="122d8-136">**Erwartete Richness-Fehlermarge**: Angesichts der aktualisierten Werte ist dies der erwartete Fehlerrand des Richness-Werts, nachdem alle zusätzlichen Bewertungsdateien überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="122d8-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="122d8-137">**Zusätzliche Bewertungsdateien erforderlich:** Angesichts der aktualisierten Werte die Anzahl der zusätzlichen Bewertungsdateien, die überprüft werden müssen, um das Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="122d8-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="122d8-138">**Gesamtbewertungsdateien erforderlich:** Angesichts der aktualisierten Werte sind die Gesamtbewertungsdateien für die Überprüfung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="122d8-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="122d8-139">**Erwartete Anzahl relevanter** Dateien in der Bewertung: Angesichts der aktualisierten Werte die erwartete Anzahl relevanter Dateien in der gesamten Bewertung, nachdem alle zusätzlichen Bewertungsdateien überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="122d8-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="122d8-140">Klicken **Sie auf Werte neu berechnen,** wenn Parameter geändert werden.</span><span class="sxs-lookup"><span data-stu-id="122d8-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="122d8-141">Wenn sie fertig sind, klicken Sie bei einem Problem auf  **OK,** um die Änderungen zu speichern (oder Weiter, wenn mehrere Probleme zu überprüfen oder zu ändern sind und dann **Fertig stellen**).</span><span class="sxs-lookup"><span data-stu-id="122d8-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="122d8-142">Wenn mehrere Probleme auftreten, nachdem alle Probleme überprüft  oder angepasst wurden, wird ein Bewertungsdialogfeld angezeigt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="122d8-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Zusammenfassung der Bewertungsebene](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="122d8-144">Fahren Sie nach erfolgreichem Abschluss der Bewertung mit der nächsten Stufe der Relevanzschulung fort.</span><span class="sxs-lookup"><span data-stu-id="122d8-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="122d8-145">Überprüfen der Bewertungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="122d8-145">Reviewing assessment results</span></span>

<span data-ttu-id="122d8-146">Nachdem ein Bewertungsbeispiel markiert wurde, werden die Bewertungsergebnisse berechnet und auf der Registerkarte Relevanzspur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="122d8-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="122d8-147">Die folgenden Ergebnisse werden in der erweiterten Titelanzeige angezeigt:</span><span class="sxs-lookup"><span data-stu-id="122d8-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="122d8-148">Bewertung der aktuellen Fehlerspanne für Rückrufschätzungen</span><span class="sxs-lookup"><span data-stu-id="122d8-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="122d8-149">Geschätzter Reichhaltiger</span><span class="sxs-lookup"><span data-stu-id="122d8-149">Estimated richness</span></span>

- <span data-ttu-id="122d8-150">Zusätzliche Bewertungsdateien erforderlich (zur Überprüfung)</span><span class="sxs-lookup"><span data-stu-id="122d8-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="122d8-151">Die aktuelle Fehlerspanne der Bewertung ist die von Advanced eDiscovery empfohlene Fehlerspanne.</span><span class="sxs-lookup"><span data-stu-id="122d8-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="122d8-152">Die nummer, die für die "Zusätzlichen Bewertungsdateien erforderlich" angezeigt wird, entspricht dieser Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="122d8-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="122d8-153">Der Bewertungsfortschrittsindikator zeigt den Abschluss der Bewertung an, wenn die aktuelle Fehlerspanne angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="122d8-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="122d8-154">Wenn die Bewertung im Gange ist, tagg der Benutzer ein weiteres Bewertungsbeispiel.</span><span class="sxs-lookup"><span data-stu-id="122d8-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="122d8-155">Wenn der Bewertungsfortschrittsindikator die Bewertung als abgeschlossen anschaut, bedeutet dies, dass die Bewertungsbeispielüberprüfung abgeschlossen wurde und ausreichend relevante Dateien markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="122d8-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="122d8-156">Die erweiterte Titelanzeige zeigt den empfohlenen nächsten Schritt, die Bewertungsstatistiken und den Zugriff auf detaillierte Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="122d8-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="122d8-157">Wenn der Reichhaltige sehr gering ist, ist die Anzahl zusätzlicher Bewertungsdateien sehr hoch, um eine minimale Anzahl relevanter Dateien zu erreichen, um nützliche Statistiken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="122d8-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="122d8-158">Advanced eDiscovery empfiehlt dann den Wechsel zu Schulungen.</span><span class="sxs-lookup"><span data-stu-id="122d8-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="122d8-159">Der Bewertungsfortschrittsindikator wird schattiert, und es sind keine Statistiken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="122d8-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="122d8-160">Wenn es keine statistische Stabilisierung gibt, gibt es Ergebnisse mit einem niedrigeren Genauigkeits- und Zuverlässigkeitsgrad.</span><span class="sxs-lookup"><span data-stu-id="122d8-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="122d8-161">Diese Ergebnisse können jedoch verwendet werden, um relevante Dateien zu finden, wenn Sie den Prozentsatz der gefundenen relevanten Dateien nicht kennen müssen.</span><span class="sxs-lookup"><span data-stu-id="122d8-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="122d8-162">Auf ähnliche Weise kann dieser Status verwendet werden, um Probleme mit geringem Reichhaltigem zu trainieren, wobei Relevanzergebnisse den Zugriff auf Dateien beschleunigen können, die für ein bestimmtes Problem relevant sind.</span><span class="sxs-lookup"><span data-stu-id="122d8-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="122d8-163">Auf der **Registerkarte \> Relevanzspur,** erweiterte Problemanzeige, sind die folgenden Anzeigeoptionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="122d8-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="122d8-164">Der empfohlene nächste Schritt, z. B. **Nächster Schritt: Tagging**  kann (pro Problem) umgangen werden, indem rechts auf die Schaltfläche Ändern geklickt wird und dann im nächsten Schritt ein anderer Schritt ausgewählt **wird.**</span><span class="sxs-lookup"><span data-stu-id="122d8-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="122d8-165">Wenn der Bewertungsfortschrittsindikator noch nicht abgeschlossen ist, ist die Bewertung die nächste empfohlene Option, um mehr Bewertungsdateien zu kennzeichnen und die Genauigkeit der Statistiken zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="122d8-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="122d8-166">Sie können die Fehlermarge ändern und deren Auswirkungen bewerten, indem Sie im Dialogfeld Bewertungsebene auf **Ändern** **klicken,** die Fehlermarge Ziel für Rückrufschätzungen ändern und auf Werte **aktualisieren klicken.**</span><span class="sxs-lookup"><span data-stu-id="122d8-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="122d8-167">Darüber hinaus können Sie in diesem Dialogfeld erweiterte Optionen anzeigen, indem Sie auf **Erweitert klicken.**</span><span class="sxs-lookup"><span data-stu-id="122d8-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="122d8-168">Sie können zusätzliche Bewertungsebenenstatistiken und deren Auswirkungen anzeigen, indem Sie auf **Anzeigen klicken.**</span><span class="sxs-lookup"><span data-stu-id="122d8-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="122d8-169">Im Dialogfeld "Detailergebnisse" sind Statistiken pro Problem verfügbar, wenn mindestens 500 markierte Bewertungsdateien vorhanden sind und mindestens 18 Dateien als relevant für das Problem gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="122d8-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
