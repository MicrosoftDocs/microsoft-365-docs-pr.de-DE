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
description: Lesen Sie die Schritte zum Durchführen von Assessment-Schulungen, einschließlich Tagging-Dateien und Überprüfen der Bewertungsergebnisse in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769190"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="e19b6-103">Tagging und Bewertung im Modul "Relevanz" in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e19b6-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="e19b6-104">In diesem Abschnitt wird das Verfahren für die Bewertung im Modul "Relevanz" in Advanced eDiscovery beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e19b6-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="e19b6-105">Durchführen von Schulungs-und Analyse Tests</span><span class="sxs-lookup"><span data-stu-id="e19b6-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="e19b6-106">Klicken Sie auf der Registerkarte **Relevanz \> Track** auf **Bewertung** , um die Fall Bewertung zu starten.</span><span class="sxs-lookup"><span data-stu-id="e19b6-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="e19b6-107">In diesem Verfahren wird beispielsweise ein Beispiel für einen assessmentsatz von 500-Dateien erstellt, und die Registerkarte " **Tag** " wird angezeigt, die den Markierungsbereich, den angezeigten Dateiinhalt und andere Kennzeichnungs Optionen enthält.</span><span class="sxs-lookup"><span data-stu-id="e19b6-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Registerkarte "Relevanz-Tag" für Bewertung](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="e19b6-109">Überprüfen Sie jede Datei im Beispiel, bestimmen Sie die Relevanz der Datei für die einzelnen Fall Probleme, und markieren Sie die Datei mit den Schaltflächen Relevanz (R), nicht relevant (Nr) und überspringen im Bereich **Tagging Panel** .</span><span class="sxs-lookup"><span data-stu-id="e19b6-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="e19b6-110">Die Bewertung erfordert 500 getaggte Dateien.</span><span class="sxs-lookup"><span data-stu-id="e19b6-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="e19b6-111">Wenn Dateien "übersprungen" werden, erhalten Sie weitere Dateien, die Tags hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e19b6-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="e19b6-112">Klicken Sie nach dem Markieren aller Dateien im Beispiel auf **berechnen**.</span><span class="sxs-lookup"><span data-stu-id="e19b6-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="e19b6-113">Die Bewertung Current Error Margin and Reichhaltigkeit werden berechnet und auf der Registerkarte **Relevanz Track** mit erweiterten Details pro Problem angezeigt, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e19b6-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="e19b6-114">Weitere Details zu diesem Dialogfeld finden Sie im Abschnitt über [Prüfen von Bewertungsergebnissen](#reviewing-assessment-results) .</span><span class="sxs-lookup"><span data-stu-id="e19b6-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Relevanz Track-Assessment](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="e19b6-116">Standardmäßig wird empfohlen, mit dem standardmäßigen nächsten Schritt fortzufahren, wenn der Indikator für die Status Bewertung des Problems abgeschlossen wurde, was bedeutet, dass das Bewertungs Beispiel überprüft und ausreichende relevante Dateien markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e19b6-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="e19b6-117">> andernfalls können Sie, wenn Sie die Ergebnisse der Registerkarte **Track** anzeigen und den Fehlerbereich und den nächsten Schritt steuern möchten, auf neben **Nächster Schritt** **ändern** klicken, **Bewertung fortsetzen** auswählen und dann auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="e19b6-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="e19b6-118">Klicken Sie rechts neben dem Kontrollkästchen **Bewertung** auf **ändern** , um die Bewertungsparameter pro Problem anzuzeigen und anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e19b6-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="e19b6-119">Es wird ein Dialogfeld **Bewertungsebene** für jedes Problem angezeigt, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e19b6-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Fall Problem bei Bewertungsebene](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="e19b6-121">Die folgenden Parameter für das Problem werden berechnet und im Dialogfeld " **Bewertungsstufe** " angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e19b6-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="e19b6-122">**Ziel Fehlermarge für Rückruf Schätzungen**: basierend auf diesem Wert wird die geschätzte Anzahl zusätzlicher Dateien berechnet, die für die Überprüfung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e19b6-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="e19b6-123">Der für Rückruf verwendete Rand ist größer als 75% und mit einem Konfidenzniveau von 95%.</span><span class="sxs-lookup"><span data-stu-id="e19b6-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="e19b6-124">**Erforderliche zusätzliche Testdateien**: gibt an, wie viele weitere Dateien erforderlich sind, wenn die Anforderungen des aktuellen Fehler Rands nicht erfüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="e19b6-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="e19b6-125">So passen Sie den aktuellen Fehler Rand an und sehen den Effekt unterschiedlicher Fehler Ränder (pro Problem):</span><span class="sxs-lookup"><span data-stu-id="e19b6-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="e19b6-126">Wählen Sie in der Liste **Problem auswählen** ein Problem aus.</span><span class="sxs-lookup"><span data-stu-id="e19b6-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="e19b6-127">Geben Sie unter **Ziel Fehlermarge für Rückruf Schätzungen** einen neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="e19b6-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="e19b6-128">Klicken Sie auf **Werte aktualisieren** , um die Auswirkungen der Anpassungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e19b6-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="e19b6-129">Klicken Sie im Dialogfeld **Bewertungsebene** auf **erweitert** , um die folgenden zusätzlichen Parameter und Details anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e19b6-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Fallbeispiel für Bewertungsebene erweiterte Ansicht](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="e19b6-131">**Geschätzter Reichtum**: Geschätzter Umfang gemäß den aktuellen Bewertungsergebnissen</span><span class="sxs-lookup"><span data-stu-id="e19b6-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="e19b6-132">**Für angenommene Rückruf**: Standardmäßig gilt die Ziel Fehlermarge für Rückrufe über 75%.</span><span class="sxs-lookup"><span data-stu-id="e19b6-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="e19b6-133">Klicken Sie auf **Bearbeiten** , wenn Sie diesen Parameter ändern und die Fehlergrenze für einen anderen Bereich von Rückruf Werten steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="e19b6-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="e19b6-134">**Konfidenz Stufe**: Standardmäßig beträgt der empfohlene Fehler Rand für das Vertrauen 95%.</span><span class="sxs-lookup"><span data-stu-id="e19b6-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="e19b6-135">Klicken Sie auf **Bearbeiten** , wenn Sie diesen Parameter ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="e19b6-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="e19b6-136">**Rand des erwarteten** Umfangs des Umfangs: bei den aktualisierten Werten ist dies der erwartete Fehlerbereich des Reichtums, nachdem alle zusätzlichen Bewertungsdateien überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="e19b6-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="e19b6-137">**Zusätzliche Bewertungsdateien erforderlich**: bei den aktualisierten Werten ist die Anzahl der zusätzlichen Bewertungsdateien, die überprüft werden müssen, um das Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="e19b6-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="e19b6-138">**Erforderliche Gesamt Wertungs Dateien**: bei den aktualisierten Werten werden Gesamt Bewertungsdateien für die Überprüfung benötigt.</span><span class="sxs-lookup"><span data-stu-id="e19b6-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="e19b6-139">**Erwartete Anzahl relevanter Dateien in der Bewertung**: bei den aktualisierten Werten wird die erwartete Anzahl relevanter Dateien in der gesamten Bewertung nach der Überprüfung aller zusätzlichen Bewertungsdateien berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e19b6-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="e19b6-140">Klicken Sie auf **Werte neu berechnen**, wenn Parameter geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e19b6-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="e19b6-141">Wenn Sie fertig sind, wenn ein Problem vorliegt, klicken Sie auf **OK** , um die Änderungen zu speichern (oder als **nächstes** , wenn mehrere Probleme zu überprüfen oder zu ändern sind, und klicken Sie dann auf **Fertig stellen**).</span><span class="sxs-lookup"><span data-stu-id="e19b6-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="e19b6-142">Wenn es mehrere Probleme gibt, wird, nachdem alle Probleme überprüft oder angepasst wurden, ein Dialogfeld " **Bewertungsstufe: Zusammenfassung** " angezeigt, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e19b6-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Zusammenfassung der Bewertungsebene](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="e19b6-144">Bei erfolgreichem Abschluss der Bewertung fahren Sie mit dem nächsten Schritt in Relevanz Training fort.</span><span class="sxs-lookup"><span data-stu-id="e19b6-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="e19b6-145">Überprüfen der Bewertungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="e19b6-145">Reviewing assessment results</span></span>

<span data-ttu-id="e19b6-146">Nachdem ein Bewertungs Beispiel markiert wurde, werden die Bewertungsergebnisse berechnet und auf der Registerkarte Relevanz Track angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e19b6-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="e19b6-147">Die folgenden Ergebnisse werden in der erweiterten Spuranzeige angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e19b6-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="e19b6-148">Bewertung der aktuellen Fehlermarge für Rückruf Schätzungen</span><span class="sxs-lookup"><span data-stu-id="e19b6-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="e19b6-149">Geschätzte Reichhaltigkeit</span><span class="sxs-lookup"><span data-stu-id="e19b6-149">Estimated richness</span></span>

- <span data-ttu-id="e19b6-150">Erforderliche zusätzliche Bewertungsdateien (zur Überarbeitung)</span><span class="sxs-lookup"><span data-stu-id="e19b6-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="e19b6-151">Der Rand der Bewertung des aktuellen Fehlers ist die von Advanced eDiscovery Empfohlene Fehlermarge.</span><span class="sxs-lookup"><span data-stu-id="e19b6-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="e19b6-152">Die Nummer, die für die erforderlichen "zusätzlichen Beurteilungs Dateien" angezeigt wird, entspricht dieser Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="e19b6-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="e19b6-153">Die Statusanzeige des Assessments zeigt den Grad des Abschlusses der Bewertung bei der aktuellen Fehlermarge an.</span><span class="sxs-lookup"><span data-stu-id="e19b6-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="e19b6-154">Wenn die Bewertung fortgeschritten ist, wird der Benutzer ein anderes Bewertungs Beispiel markieren.</span><span class="sxs-lookup"><span data-stu-id="e19b6-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="e19b6-155">Wenn die Statusanzeige Assessment als abgeschlossen angezeigt wird, bedeutet dies, dass die Bewertungs Beispiel Überprüfung abgeschlossen wurde und ausreichende relevante Dateien markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e19b6-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="e19b6-156">Die erweiterte Spuranzeige zeigt den empfohlenen nächsten Schritt, die Bewertungsstatistiken und den Zugriff auf detaillierte Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e19b6-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="e19b6-157">Wenn die Reichweite sehr gering ist, ist die Anzahl der zusätzlichen assessmentdateien, die für eine minimale Anzahl relevanter Dateien zur Erstellung nützlicher Statistiken benötigt werden, sehr hoch.</span><span class="sxs-lookup"><span data-stu-id="e19b6-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="e19b6-158">Advanced eDiscovery empfiehlt dann die Weiterbildung.</span><span class="sxs-lookup"><span data-stu-id="e19b6-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="e19b6-159">Der Statusindikator für die Bewertung wird schattiert angezeigt, und es werden keine Statistiken verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="e19b6-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="e19b6-160">In Ermangelung einer statistisch basierten Stabilisierung werden Ergebnisse mit einer niedrigeren Genauigkeitsstufe und Zuverlässigkeitsstufe erzielt.</span><span class="sxs-lookup"><span data-stu-id="e19b6-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="e19b6-161">Diese Ergebnisse können jedoch zum Auffinden relevanter Dateien verwendet werden, wenn Sie den Prozentsatz relevanter gefundener Dateien nicht kennen müssen.</span><span class="sxs-lookup"><span data-stu-id="e19b6-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="e19b6-162">In ähnlicher Weise kann dieser Status verwendet werden, um Probleme mit niedrigem Umfang auszubilden, wobei Relevanz Scores den Zugriff auf Dateien beschleunigen kann, die für ein bestimmtes Problem relevant sind.</span><span class="sxs-lookup"><span data-stu-id="e19b6-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="e19b6-163">Auf der **Register \> Karte relevanzstatus** , erweiterte Ausgabe Anzeige, stehen die folgenden Anzeigeoptionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e19b6-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="e19b6-164">Der Empfohlene nächste Schritt, wie der **nächste Schritt: die Kennzeichnung** kann umgangen werden (pro Problem), indem Sie rechts auf die Schaltfläche **ändern** klicken und dann im **nächsten Schritt** einen anderen Schritt auswählen.</span><span class="sxs-lookup"><span data-stu-id="e19b6-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="e19b6-165">Wenn der Statusindikator für die Bewertung nicht abgeschlossen ist, wird die nächste empfohlene Option verwendet, um weitere Bewertungsdateien zu markieren und die Genauigkeit der Statistik zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e19b6-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="e19b6-166">Sie können den Fehler Rand ändern und seine Auswirkung bewerten, indem Sie auf **ändern** klicken und im **Dialogfeld Bewertungsebene** den **Ziel Fehler Rand für Rückruf Schätzungen** ändern und auf **Werte aktualisieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="e19b6-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="e19b6-167">Außerdem können Sie in diesem Dialogfeld Erweiterte Optionen anzeigen, indem Sie auf **erweitert** klicken.</span><span class="sxs-lookup"><span data-stu-id="e19b6-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="e19b6-168">Sie können zusätzliche Statistiken zur Bewertungsebene und deren Auswirkungen anzeigen, indem Sie auf **Ansicht** klicken.</span><span class="sxs-lookup"><span data-stu-id="e19b6-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="e19b6-169">Im Dialogfeld Detail Ergebnisse werden Statistiken pro Problem angezeigt, wenn mindestens 500 getaggte Bewertungsdateien vorhanden sind und mindestens 18 Dateien als relevant für das Problem gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="e19b6-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
