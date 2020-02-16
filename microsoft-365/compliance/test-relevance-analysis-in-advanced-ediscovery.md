---
title: Test Relevanz Analysis in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Erfahren Sie, wie Sie die Registerkarte "Test" nach der Batch Berechnung in Office 365 Advanced eDiscovery verwenden, um die Gesamtqualität der Verarbeitung zu testen, zu vergleichen und zu validieren.  '
ms.openlocfilehash: e07d02a0eff1e07cacbce5debd27d4057fe40db2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080932"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7dfb0-103">Test Relevanz Analysis in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7dfb0-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="7dfb0-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="7dfb0-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7dfb0-106">Auf der Registerkarte Test in Advanced eDiscovery können Sie die Gesamtqualität der Verarbeitung testen, vergleichen und validieren.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="7dfb0-107">Diese Tests werden nach der Batch Berechnung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="7dfb0-108">Durch das Markieren der Dateien in der Sammlung entscheidet ein Experte darüber, ob jede markierte Datei tatsächlich für den Fall relevant ist.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="7dfb0-109">Bei Szenarien mit einem oder mehreren Problemen werden normalerweise Tests pro Problem durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="7dfb0-110">Ergebnisse können nach jedem Test angezeigt werden, und die Testergebnisse können mit den angegebenen Beispiel Testdateien überarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="7dfb0-111">Testen des Rests</span><span class="sxs-lookup"><span data-stu-id="7dfb0-111">Testing the rest</span></span>

<span data-ttu-id="7dfb0-112">Der Test "Rest testen" wird zum Validieren von Culling-Entscheidungen verwendet, zum Beispiel, um nur Dateien über einem bestimmten Relevanz-Cutoff-Ergebnis basierend auf den endgültigen erweiterten eDiscovery-Ergebnissen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="7dfb0-113">Der Experte überprüft ein Beispiel von Dateien unter einem ausgewählten Cutoff-Ergebnis, um die Anzahl der relevanten Dateien innerhalb dieses Satzes auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="7dfb0-114">Dieser Test enthält Statistiken und einen Vergleich zwischen dem Überprüfungs Sätze und dem Test der Rest-Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="7dfb0-115">Die Ergebnisse des Überprüfungs Satzes werden von Relevanz während der Schulung berechnet.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="7dfb0-116">Die Ergebnisse umfassen Berechnungen basierend auf Einstellungen und Eingabeparametern, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="7dfb0-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="7dfb0-117">Testen Sie die Beispiel Statistiken über die Anzahl der Dateien in einem Beispiel und die identifizierten relevanten Dateien.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="7dfb0-118">Tabellarischer Vergleich der Populations Parameter des Überprüfungs Satzes und des Rests, beispielsweise die Anzahl der Dateien, die geschätzte Anzahl relevanter Dateien, die geschätzte Reichhaltigkeit und die durchschnittlichen Kosten für die Suche nach einer zusätzlichen relevanten Datei.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="7dfb0-119">Kosten Parametereinstellungen können vom Administrator festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="7dfb0-120">Öffnen Sie die Registerkarte **Relevanz \> -Test** .</span><span class="sxs-lookup"><span data-stu-id="7dfb0-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="7dfb0-121">Klicken Sie auf der Registerkarte **Test** auf **neuer Test**.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="7dfb0-122">Das Dialogfeld zum **Erstellen eines Tests** wird angezeigt, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Relevanz Testen der Rest-Ergebnisse](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="7dfb0-124">Geben Sie unter **Test Name**und **Beschreibung**den Namen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="7dfb0-125">Wählen Sie in der Liste **Testtyp** **die Option Rest testen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="7dfb0-126">Wählen Sie in der Liste **Problem/Kategorie** den Namen des Problems aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="7dfb0-127">Wählen Sie in der Liste **Laden** die Option Laden aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="7dfb0-128">Übernehmen Sie in **Read%** den Standardwert, oder wählen Sie einen Wert für das Ergebnis der Cutoff-Relevanz aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="7dfb0-129">Legen Sie die **Größe fest**, oder übernehmen Sie den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="7dfb0-130">Beachten Sie, dass die Wiederherstellungs Symbole die Standardwerte wiederherstellen werden.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="7dfb0-131">Klicken Sie auf **Tagging starten**.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-131">Click **Start tagging**.</span></span> <span data-ttu-id="7dfb0-132">Ein Test Beispiel wird generiert.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="7dfb0-133">Überprüfen und markieren Sie die Dateien auf der Registerkarte \*\* \> Relevanz-Tag\*\* , und klicken Sie dann auf **berechnen**.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="7dfb0-134">Auf der Registerkarte Test können Sie auf **Ergebnisse anzeigen** klicken, um die Testergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="7dfb0-135">In der folgenden Abbildung ist ein Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-135">An example is shown in the following figure.</span></span> 
    
    ![Testen der Rest-Ergebnisse](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="7dfb0-137">In der obigen Abbildung enthält der Abschnitt " **Sample Parameters** " der Tabelle Details zur Anzahl der Dateien im Beispiel, die vom Experten markiert wurden, sowie die Anzahl relevanter Dateien, die in diesem Beispiel gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="7dfb0-138">Der Abschnitt " **Population Parameters** " der Tabelle enthält die Testergebnisse, einschließlich der Überprüfungsgruppen Auffüllung von Dateien mit einer Partitur unter dem ausgewählten Cutoff und der "Rest"-Auffüllung von Dateien mit einer Bewertung über dem ausgewählten Cutoff.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="7dfb0-139">Für jede Auffüllung werden die folgenden Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7dfb0-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="7dfb0-140">Enthält Dateien mit dem Read%-angegebenen Cutoff</span><span class="sxs-lookup"><span data-stu-id="7dfb0-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="7dfb0-141">Die Gesamtzahl der Dateien</span><span class="sxs-lookup"><span data-stu-id="7dfb0-141">The total number of files</span></span> 
    
- <span data-ttu-id="7dfb0-142">Die geschätzte Anzahl relevanter Dateien</span><span class="sxs-lookup"><span data-stu-id="7dfb0-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="7dfb0-143">Die geschätzte Reichhaltigkeit</span><span class="sxs-lookup"><span data-stu-id="7dfb0-143">The estimated richness</span></span> 
    
- <span data-ttu-id="7dfb0-144">Durchschnittliche Überprüfungskosten für die Suche nach einer anderen relevanten Datei</span><span class="sxs-lookup"><span data-stu-id="7dfb0-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="7dfb0-145">Testen des Slices</span><span class="sxs-lookup"><span data-stu-id="7dfb0-145">Testing the slice</span></span>

<span data-ttu-id="7dfb0-146">Der Test "Test the Slice" führt Tests aus, die dem Test "Test the Rest" ähneln, jedoch auf ein Segment des Dateisatzes, wie von Relevanz Read% angegeben.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="7dfb0-147">Öffnen Sie die Registerkarte **Relevanz \> -Test** .</span><span class="sxs-lookup"><span data-stu-id="7dfb0-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="7dfb0-148">Klicken Sie auf der Registerkarte **Test** auf **neuer Test**.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="7dfb0-149">Das Dialogfeld **Test erstellen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="7dfb0-150">Geben Sie unter Name und **Beschreibung** **Testen** die Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="7dfb0-151">Wählen Sie in der Liste **Testtyp** **die Option Segment testen**aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="7dfb0-152">Wählen Sie in der Liste **Problem** den Namen des Problems aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="7dfb0-153">Wählen Sie in der Liste **Laden** die Option Laden aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="7dfb0-154">Akzeptieren Sie in **Read% zwischen**die Standardwerte Low und High Range, oder wählen Sie Werte für die Punkte für die Grenz Wert Relevanz aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="7dfb0-155">Wählen Sie unter **festgelegte Größe**einen Wert aus, oder übernehmen Sie den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="7dfb0-156">Mit den Wiederherstellungs Symbolen wird der Standardwert wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="7dfb0-157">Klicken Sie auf **Tagging starten**.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-157">Click **Start tagging**.</span></span> <span data-ttu-id="7dfb0-158">Ein Test Beispiel wird generiert.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="7dfb0-159">Überprüfen und markieren Sie die Dateien auf der Registerkarte \*\* \> Relevanz-Tag\*\* , und klicken Sie dann auf **berechnen**.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="7dfb0-160">Auf der Registerkarte Test können Sie auf **Ergebnisse anzeigen** klicken, um die Testergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dfb0-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7dfb0-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dfb0-161">See also</span></span>

[<span data-ttu-id="7dfb0-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7dfb0-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7dfb0-163">Grundlegendes zur Relevanz der Bewertung</span><span class="sxs-lookup"><span data-stu-id="7dfb0-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7dfb0-164">Tagging und Bewertung</span><span class="sxs-lookup"><span data-stu-id="7dfb0-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7dfb0-165">Tagging und Relevanz Training</span><span class="sxs-lookup"><span data-stu-id="7dfb0-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7dfb0-166">Analyse der nach Verfolgungs Relevanz</span><span class="sxs-lookup"><span data-stu-id="7dfb0-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7dfb0-167">Entscheidung basierend auf den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="7dfb0-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

