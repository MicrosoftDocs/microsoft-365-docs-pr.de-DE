---
title: Entscheidung basierend auf den Ergebnissen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Erfahren Sie, wie die Registerkarte entscheiden in Advanced eDiscovery Daten bereitstellt, mit denen Sie die richtige Größe des Überprüfungs Satzes von Fall Dateien ermitteln können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 04c6f0c8fede315f175e0ed6ae265c7463405a62
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528005"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="64406-103">Entscheidung basierend auf den Ergebnissen in Advanced eDiscovery (klassisch)</span><span class="sxs-lookup"><span data-stu-id="64406-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="64406-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="64406-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="64406-106">In Advanced eDiscovery bietet die Registerkarte entscheiden zusätzliche Informationen zum Anzeigen und Verwenden von Statistiken zur Entscheidungsunterstützung zur Bestimmung der Größe des Überprüfungs Satzes von Fall Dateien.</span><span class="sxs-lookup"><span data-stu-id="64406-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="64406-107">Verwenden der Registerkarte "entscheiden"</span><span class="sxs-lookup"><span data-stu-id="64406-107">Using the Decide tab</span></span>

![Relevanz entscheiden](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="64406-109">Diese Registerkarte umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="64406-109">This tab includes the following components:</span></span>
  
- <span data-ttu-id="64406-110">**Problem**: von hier aus können Sie das Interesse aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="64406-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="64406-111">**Review-Rückruf Verhältnis**: Vergleiche der erweiterten eDiscovery-Überprüfung entsprechend den Relevanz-Bewertungen.</span><span class="sxs-lookup"><span data-stu-id="64406-111">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="64406-112">Der Cutoff-Punkt im Diagramm stellt den Prozentsatz der zu überprüfenden Dateien dar, der einem Relevanz-Ergebnis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="64406-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="64406-113">Dies wird in der Phase für die Relevanzprüfung und als Export Schwellenwert für das Culling verwendet.</span><span class="sxs-lookup"><span data-stu-id="64406-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="64406-114">Der Standardgrenzwert für die Anzahl der zu überprüfenden Dateien liegt an dem Ort, an dem die Balance Zwischenrückruf und Genauigkeit optimal ist.</span><span class="sxs-lookup"><span data-stu-id="64406-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="64406-115">Der tatsächliche Sperrpunkt sollte vom Benutzer abhängig von den Zielen und dem Kosten Kompromiss (% Review) und dem Risiko (% Rückruf) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="64406-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="64406-116">Mithilfe des Schiebereglers können Sie den abgrenzpunkt anpassen und die Auswirkung auf das Diagramm und die Parameter anzeigen, wenn Sie den Prozentsatz relevanter Dateien anpassen, die abgerufen werden sollen, und vor dem Validieren einer Entscheidung.</span><span class="sxs-lookup"><span data-stu-id="64406-116">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="64406-117">**Parameter**: Review, Recall, Next relevant and Total Cost Parameters sind kumulierte berechnete Statistiken im Zusammenhang mit der Überprüfungsgruppe im Verhältnis zur Sammlung für den gesamten Fall.</span><span class="sxs-lookup"><span data-stu-id="64406-117">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="64406-118">Definitionen für diese Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="64406-118">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="64406-119">**Review**: Prozentsatz der zu überprüfenden Dateien basierend auf diesem Cutoff.</span><span class="sxs-lookup"><span data-stu-id="64406-119">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="64406-120">**Rückruf**: Prozentsatz relevanter Dateien im Überprüfungs Satz.</span><span class="sxs-lookup"><span data-stu-id="64406-120">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="64406-121">**Next relevant**: Kosten für die Überprüfung und Identifizierung einer zusätzlichen relevanten Datei, die derzeit nicht im Überprüfungs ist.</span><span class="sxs-lookup"><span data-stu-id="64406-121">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="64406-122">**Gesamtkosten**: Kosten für die Überprüfung dieses Prozentsatzes der Fall Dateien.</span><span class="sxs-lookup"><span data-stu-id="64406-122">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="64406-123">Kosten Parametereinstellungen können vom Case Manager festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="64406-123">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="64406-124">**Verteilung nach Relevanz-Ergebnis**: Dateien in der dunkelgrauen Anzeige links liegen unterhalb der Cutoff-Punktzahl.</span><span class="sxs-lookup"><span data-stu-id="64406-124">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="64406-125">Ein QuickInfo zeigt das Relevanz-Ergebnis und den zugehörigen Prozentsatz der Dateien im Überprüfungs Dateisatz im Verhältnis zu den Gesamtdateien an.</span><span class="sxs-lookup"><span data-stu-id="64406-125">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="64406-126">Im erweiterten Detailbereich werden zusätzliche Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64406-126">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="64406-127">Dateien in Sammlungs Abbildungen enthalten keine leeren oder nebligen Dateien.</span><span class="sxs-lookup"><span data-stu-id="64406-127">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="64406-128">Familiendateien Abbildungen stellen Dateien dar, die nicht relevant geladen werden, aber dennoch als Teil der Familie gezählt werden.</span><span class="sxs-lookup"><span data-stu-id="64406-128">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="64406-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="64406-129">Related topics</span></span>

[<span data-ttu-id="64406-130">Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="64406-130">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="64406-131">Grundlegendes zur Relevanz der Bewertung</span><span class="sxs-lookup"><span data-stu-id="64406-131">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="64406-132">Tagging und Bewertung</span><span class="sxs-lookup"><span data-stu-id="64406-132">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="64406-133">Durchführen von Relevanz-Schulungen</span><span class="sxs-lookup"><span data-stu-id="64406-133">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="64406-134">Analyse der nach Verfolgungs Relevanz</span><span class="sxs-lookup"><span data-stu-id="64406-134">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="64406-135">Testen der Relevanz-Analyse</span><span class="sxs-lookup"><span data-stu-id="64406-135">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

