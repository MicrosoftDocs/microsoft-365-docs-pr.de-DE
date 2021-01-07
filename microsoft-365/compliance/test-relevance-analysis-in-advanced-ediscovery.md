---
title: Testen der Relevanz-Analyse in Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie die Registerkarte "Test" nach der Batch Berechnung in Advanced eDiscovery verwenden, um die Gesamtqualität der Verarbeitung zu testen, zu vergleichen und zu validieren.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769170"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="f3ab4-103">Testen der Relevanz-Analyse in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f3ab4-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="f3ab4-104">Auf der Registerkarte Test in Advanced eDiscovery können Sie die Gesamtqualität der Verarbeitung testen, vergleichen und validieren.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="f3ab4-105">Diese Tests werden nach der Batch Berechnung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="f3ab4-106">Durch das Markieren der Dateien in der Sammlung entscheidet ein Experte darüber, ob jede markierte Datei für den Fall relevant ist.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="f3ab4-107">Bei Szenarien mit einem oder mehreren Problemen werden normalerweise Tests pro Problem durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="f3ab4-108">Ergebnisse können nach jedem Test angezeigt werden, und die Testergebnisse können mit den angegebenen Beispiel Testdateien überarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="f3ab4-109">Testen des Rests</span><span class="sxs-lookup"><span data-stu-id="f3ab4-109">Testing the rest</span></span>

<span data-ttu-id="f3ab4-110">Der Test "Rest testen" wird zum Validieren von Culling-Entscheidungen verwendet, zum Beispiel, um nur Dateien über einem bestimmten Relevanz-Cutoff-Ergebnis basierend auf den endgültigen erweiterten eDiscovery-Ergebnissen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="f3ab4-111">Der Experte überprüft ein Beispiel von Dateien unter einem ausgewählten Cutoff-Ergebnis, um die Anzahl der relevanten Dateien innerhalb dieses Satzes auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="f3ab4-112">Dieser Test enthält Statistiken und einen Vergleich zwischen dem Überprüfungs Sätze und dem Test der Rest-Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="f3ab4-113">Die Ergebnisse des Überprüfungs Satzes werden von Relevanz während der Schulung berechnet.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="f3ab4-114">Die Ergebnisse umfassen Berechnungen basierend auf Einstellungen und Eingabeparametern, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="f3ab4-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="f3ab4-115">Testen Sie die Beispiel Statistiken über die Anzahl der Dateien in einem Beispiel und die identifizierten relevanten Dateien.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="f3ab4-116">Tabellarischer Vergleich der Populations Parameter des Überprüfungs Satzes und des Rests, beispielsweise die Anzahl der Dateien, die geschätzte Anzahl relevanter Dateien, die geschätzte Reichhaltigkeit und die durchschnittlichen Kosten für die Suche nach einer anderen relevanten Datei.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="f3ab4-117">Kosten Parametereinstellungen können vom Administrator festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="f3ab4-118">So führen Sie den Test "Test the Rest" aus:</span><span class="sxs-lookup"><span data-stu-id="f3ab4-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="f3ab4-119">Öffnen Sie die Registerkarte **Relevanz- \> Test** .</span><span class="sxs-lookup"><span data-stu-id="f3ab4-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="f3ab4-120">Klicken Sie auf der Registerkarte **Test** auf **neuer Test**.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="f3ab4-121">Das Dialogfeld zum **Erstellen eines Tests** wird angezeigt, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Relevanz Testen der Rest-Ergebnisse](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="f3ab4-123">Geben Sie unter **Test Name** und **Beschreibung** den Namen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="f3ab4-124">Wählen Sie in der Liste **Testtyp** **die Option Rest testen** aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="f3ab4-125">Wählen Sie in der Liste **Problem/Kategorie** den Namen des Problems aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="f3ab4-126">Wählen Sie in der Liste **Laden** die Option Laden aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="f3ab4-127">Übernehmen Sie in **Read%** den Standardwert, oder wählen Sie einen Wert für das Ergebnis der Cutoff-Relevanz aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="f3ab4-128">Legen Sie die **Größe fest**, oder übernehmen Sie den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="f3ab4-129">Mit den Wiederherstellungs Symbolen werden die Standardwerte wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="f3ab4-130">Klicken Sie auf **Tagging starten**.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-130">Click **Start tagging**.</span></span> <span data-ttu-id="f3ab4-131">Ein Test Beispiel wird generiert.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-131">A test sample is generated.</span></span>

10. <span data-ttu-id="f3ab4-132">Überprüfen und markieren Sie die Dateien auf der Registerkarte **Relevanz- \> Tag** , und klicken Sie dann auf **berechnen**.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="f3ab4-133">Auf der Registerkarte Test können Sie auf **Ergebnisse anzeigen** klicken, um die Testergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="f3ab4-134">Ein Beispiel ist im folgenden Screenshot dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-134">An example is shown in the following screenshot.</span></span>

    ![Testen der Rest-Ergebnisse](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="f3ab4-136">Im vorherigen Screenshot enthält der Abschnitt " **Sample Parameters** " der Tabelle Details zur Anzahl der Dateien im Beispiel, die vom Experten markiert wurden, sowie die Anzahl relevanter Dateien, die in diesem Beispiel gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="f3ab4-137">Der Abschnitt " **Population Parameters** " der Tabelle enthält die Testergebnisse, einschließlich der Überprüfungsgruppen Auffüllung von Dateien mit einer Partitur unter dem ausgewählten Cutoff und der "Rest"-Auffüllung von Dateien mit einer Bewertung über dem ausgewählten Cutoff.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="f3ab4-138">Für jede Auffüllung werden die folgenden Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3ab4-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="f3ab4-139">Enthält Dateien mit dem Read%-angegebenen Cutoff</span><span class="sxs-lookup"><span data-stu-id="f3ab4-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="f3ab4-140">Die Gesamtzahl der Dateien</span><span class="sxs-lookup"><span data-stu-id="f3ab4-140">The total number of files</span></span>

- <span data-ttu-id="f3ab4-141">Die geschätzte Anzahl relevanter Dateien</span><span class="sxs-lookup"><span data-stu-id="f3ab4-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="f3ab4-142">Die geschätzte Reichhaltigkeit</span><span class="sxs-lookup"><span data-stu-id="f3ab4-142">The estimated richness</span></span>

- <span data-ttu-id="f3ab4-143">Durchschnittliche Überprüfungskosten für die Suche nach einer anderen relevanten Datei</span><span class="sxs-lookup"><span data-stu-id="f3ab4-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="f3ab4-144">Testen des Slices</span><span class="sxs-lookup"><span data-stu-id="f3ab4-144">Testing the slice</span></span>

<span data-ttu-id="f3ab4-145">Der Test "Test the Slice" führt Tests aus, die dem Test "Test the Rest" ähneln, jedoch auf ein Segment des Dateisatzes, wie von Relevanz Read% angegeben.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="f3ab4-146">So führen Sie den Test "Test the Slice" aus:</span><span class="sxs-lookup"><span data-stu-id="f3ab4-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="f3ab4-147">Öffnen Sie die Registerkarte **Relevanz- \> Test** .</span><span class="sxs-lookup"><span data-stu-id="f3ab4-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="f3ab4-148">Klicken Sie auf der Registerkarte **Test** auf **neuer Test**.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="f3ab4-149">Das Dialogfeld **Test erstellen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="f3ab4-150">Geben Sie unter Name und **Beschreibung** **Testen** die Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="f3ab4-151">Wählen Sie in der Liste **Testtyp** **die Option Segment testen** aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="f3ab4-152">Wählen Sie in der Liste **Problem** den Namen des Problems aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="f3ab4-153">Wählen Sie in der Liste **Laden** die Option Laden aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="f3ab4-154">Akzeptieren Sie in **Read% zwischen** die Standardwerte Low und High Range, oder wählen Sie Werte für die Punkte für die Grenz Wert Relevanz aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="f3ab4-155">Wählen Sie unter **festgelegte Größe** einen Wert aus, oder übernehmen Sie den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="f3ab4-156">Mit den Wiederherstellungs Symbolen wird der Standardwert wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="f3ab4-157">Klicken Sie auf **Tagging starten**.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-157">Click **Start tagging**.</span></span> <span data-ttu-id="f3ab4-158">Ein Test Beispiel wird generiert.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-158">A test sample is generated.</span></span>

10. <span data-ttu-id="f3ab4-159">Überprüfen und markieren Sie die Dateien auf der Registerkarte **Relevanz- \> Tag** , und klicken Sie dann auf **berechnen**.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="f3ab4-160">Auf der Registerkarte Test können Sie auf **Ergebnisse anzeigen** klicken, um die Testergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f3ab4-160">In the Test tab, you can click **View results** to see the test results.</span></span>
