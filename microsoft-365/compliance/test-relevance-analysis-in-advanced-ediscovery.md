---
title: Testen der Relevanzanalyse in Advanced eDiscovery
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
description: Erfahren Sie, wie Sie die Registerkarte Test nach der Batchberechnung in Advanced eDiscovery verwenden, um die Allgemeine Verarbeitungsqualität zu testen, zu vergleichen und zu überprüfen.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769170"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="1514a-103">Testen der Relevanzanalyse in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1514a-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="1514a-104">Auf der Registerkarte Test in Advanced eDiscovery können Sie die Allgemeine Verarbeitungsqualität testen, vergleichen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1514a-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="1514a-105">Diese Tests werden nach der Batchberechnung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1514a-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="1514a-106">Durch Markieren der Dateien in der Auflistung gibt ein Experte die endgültige Entscheidung darüber ab, ob jede markierte Datei für den Fall relevant ist.</span><span class="sxs-lookup"><span data-stu-id="1514a-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="1514a-107">In Einzel- und Multiple-Issue-Szenarien werden Tests in der Regel pro Problem durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1514a-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="1514a-108">Ergebnisse können nach jedem Test angezeigt werden, und Testergebnisse können mit angegebenen Beispieltestdateien überarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1514a-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="1514a-109">Testen des Rests</span><span class="sxs-lookup"><span data-stu-id="1514a-109">Testing the rest</span></span>

<span data-ttu-id="1514a-110">Der Test "Rest testen" dient zum Überprüfen von Entscheidungen zur Ausmerzung, z. B. zum Überprüfen nur von Dateien über einem bestimmten Relevanz-Cutoff-Wert basierend auf den endgültigen Advanced eDiscovery-Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="1514a-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="1514a-111">Der Experte überprüft ein Beispiel von Dateien unter einer ausgewählten Stichprobe, um die Anzahl relevanter Dateien innerhalb dieses Ausschnitts auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="1514a-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="1514a-112">Dieser Test bietet Statistiken und einen Vergleich zwischen dem Prüfsatz und der Rest-Test-Population.</span><span class="sxs-lookup"><span data-stu-id="1514a-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="1514a-113">Die Ergebnisse des Überprüfungssatzs sind diejenigen, die durch Relevanz während des Training berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="1514a-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="1514a-114">Die Ergebnisse umfassen Berechnungen basierend auf Einstellungen und Eingabeparametern, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1514a-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="1514a-115">Testen Sie Beispielstatistiken zur Anzahl der Dateien in einem Beispiel und identifizierten relevanten Dateien.</span><span class="sxs-lookup"><span data-stu-id="1514a-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="1514a-116">Tabellarischer Vergleich der Population-Parameter des Überprüfungssatzs und des Rests, z. B. die Anzahl der Dateien, die geschätzte Anzahl relevanter Dateien, der geschätzte Reichhaltige und die durchschnittlichen Kosten für die Suche nach einer anderen relevanten Datei.</span><span class="sxs-lookup"><span data-stu-id="1514a-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="1514a-117">Einstellungen für den Kostenparameter können vom Administrator festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1514a-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="1514a-118">So führen Sie den Test "Rest testen" aus:</span><span class="sxs-lookup"><span data-stu-id="1514a-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="1514a-119">Öffnen Sie die **Registerkarte \> Relevanztest.**</span><span class="sxs-lookup"><span data-stu-id="1514a-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="1514a-120">Klicken Sie **auf der** Registerkarte Test auf **Neuer Test**.</span><span class="sxs-lookup"><span data-stu-id="1514a-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="1514a-121">Das **Dialogfeld Test erstellen** wird angezeigt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1514a-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![RelevanzTest der Restergebnisse](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="1514a-123">Geben **Sie unter Testname** und **Beschreibung** den Namen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="1514a-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="1514a-124">Wählen Sie **in der Liste** Testtyp die Option Rest testen **aus.**</span><span class="sxs-lookup"><span data-stu-id="1514a-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="1514a-125">Wählen Sie **in der Liste Problem/Kategorie** den Problemnamen aus.</span><span class="sxs-lookup"><span data-stu-id="1514a-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="1514a-126">Wählen Sie **in der Liste** Laden die Last aus.</span><span class="sxs-lookup"><span data-stu-id="1514a-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="1514a-127">Akzeptieren **Sie in Read %** den Standardwert, oder wählen Sie einen Wert für die Relevanzsentwertung für die Stichwahl aus.</span><span class="sxs-lookup"><span data-stu-id="1514a-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="1514a-128">In **Set size** oder accept the default value.</span><span class="sxs-lookup"><span data-stu-id="1514a-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="1514a-129">Die Wiederherstellungssymbole stellen die Standardwerte wieder dar.</span><span class="sxs-lookup"><span data-stu-id="1514a-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="1514a-130">Klicken **Sie auf Starttagging**.</span><span class="sxs-lookup"><span data-stu-id="1514a-130">Click **Start tagging**.</span></span> <span data-ttu-id="1514a-131">Es wird ein Testbeispiel generiert.</span><span class="sxs-lookup"><span data-stu-id="1514a-131">A test sample is generated.</span></span>

10. <span data-ttu-id="1514a-132">Überprüfen und kennzeichnen Sie die einzelnen Dateien auf der Registerkarte **\> Relevanztag,** und klicken Sie nach Getan auf **Berechnen**.</span><span class="sxs-lookup"><span data-stu-id="1514a-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="1514a-133">Klicken Sie auf der Registerkarte Test auf Ergebnisse **anzeigen,** um die Testergebnisse zu sehen.</span><span class="sxs-lookup"><span data-stu-id="1514a-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="1514a-134">Ein Beispiel ist im folgenden Screenshot dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1514a-134">An example is shown in the following screenshot.</span></span>

    ![Testen der restlichen Ergebnisse](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="1514a-136">Im vorherigen Screenshot  enthält der Abschnitt Beispielparameter der Tabelle Details zur Anzahl der Dateien im Beispiel, die vom Experten markiert wurden, und zur Anzahl der relevanten Dateien in diesem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="1514a-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="1514a-137">Der **Abschnitt Population-Parameter** der Tabelle enthält die Testergebnisse, einschließlich der Prüfsatzgesamtheit von Dateien mit einer Bewertung unterhalb des ausgewählten Cutoffs und der "Rest"-Aufgesamtheit von Dateien mit einer Bewertung über dem ausgewählten Cutoff.</span><span class="sxs-lookup"><span data-stu-id="1514a-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="1514a-138">Für jede Grundgesamtheit werden die folgenden Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1514a-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="1514a-139">Enthält Dateien mit "% gelesen" – Angegebener Cutoff</span><span class="sxs-lookup"><span data-stu-id="1514a-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="1514a-140">Die Gesamtanzahl der Dateien</span><span class="sxs-lookup"><span data-stu-id="1514a-140">The total number of files</span></span>

- <span data-ttu-id="1514a-141">Die geschätzte Anzahl relevanter Dateien</span><span class="sxs-lookup"><span data-stu-id="1514a-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="1514a-142">Der geschätzte Reichhaltige</span><span class="sxs-lookup"><span data-stu-id="1514a-142">The estimated richness</span></span>

- <span data-ttu-id="1514a-143">Die durchschnittlichen Überprüfungskosten für die Suche nach einer anderen relevanten Datei</span><span class="sxs-lookup"><span data-stu-id="1514a-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="1514a-144">Testen des Datenschnitts</span><span class="sxs-lookup"><span data-stu-id="1514a-144">Testing the slice</span></span>

<span data-ttu-id="1514a-145">Der Test "Test the Slice" führt Tests ähnlich dem Test "Test the Rest" durch, aber mit einem Abschnitt der Datei, wie durch Relevanz read %angegeben.</span><span class="sxs-lookup"><span data-stu-id="1514a-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="1514a-146">So führen Sie den Test "Test the Slice" aus:</span><span class="sxs-lookup"><span data-stu-id="1514a-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="1514a-147">Öffnen Sie die **Registerkarte \> Relevanztest.**</span><span class="sxs-lookup"><span data-stu-id="1514a-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="1514a-148">Klicken Sie **auf der** Registerkarte Test auf **Neuer Test**.</span><span class="sxs-lookup"><span data-stu-id="1514a-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="1514a-149">Das **Dialogfeld Test erstellen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1514a-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="1514a-150">Geben **Sie unter Testname** **und Beschreibung** die Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="1514a-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="1514a-151">Wählen Sie **in der Liste Testtyp** die Option **Slice testen aus.**</span><span class="sxs-lookup"><span data-stu-id="1514a-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="1514a-152">Wählen Sie **in der** Liste Problem den Problemnamen aus.</span><span class="sxs-lookup"><span data-stu-id="1514a-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="1514a-153">Wählen Sie **in der Liste** Laden die Last aus.</span><span class="sxs-lookup"><span data-stu-id="1514a-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="1514a-154">Akzeptieren **Sie in Read % between** die Standardmäßigen Werte für niedrigen und hohen Bereich oder wählen Sie Werte für die Stichwahlrelevanzwerte aus.</span><span class="sxs-lookup"><span data-stu-id="1514a-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="1514a-155">Wählen **Sie unter Größe festlegen** einen Wert aus, oder akzeptieren Sie den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="1514a-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="1514a-156">Mit den Wiederherstellungssymbolen wird der Standardwert wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="1514a-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="1514a-157">Klicken **Sie auf Starttagging**.</span><span class="sxs-lookup"><span data-stu-id="1514a-157">Click **Start tagging**.</span></span> <span data-ttu-id="1514a-158">Es wird ein Testbeispiel generiert.</span><span class="sxs-lookup"><span data-stu-id="1514a-158">A test sample is generated.</span></span>

10. <span data-ttu-id="1514a-159">Überprüfen und kennzeichnen Sie die einzelnen Dateien auf der Registerkarte **\> Relevanztag,** und klicken Sie nach Getan auf **Berechnen**.</span><span class="sxs-lookup"><span data-stu-id="1514a-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="1514a-160">Klicken Sie auf der Registerkarte Test auf Ergebnisse **anzeigen,** um die Testergebnisse zu sehen.</span><span class="sxs-lookup"><span data-stu-id="1514a-160">In the Test tab, you can click **View results** to see the test results.</span></span>
