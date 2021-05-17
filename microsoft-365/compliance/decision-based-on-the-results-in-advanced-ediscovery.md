---
title: Entscheidung basierend auf den Ergebnissen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Erfahren Sie, wie die Registerkarte "Entscheiden" in Advanced eDiscovery Daten enthält, mit deren Hilfe Sie die richtige Größe der Falldateien für die Überprüfung ermitteln können.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769150"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="bec78-103">Entscheidungen basierend auf Relevanzergebnissen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bec78-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="bec78-104">Im Relevanzmodul in Advanced eDiscovery enthält die Registerkarte Entscheiden zusätzliche Informationen zum Anzeigen und Verwenden von Entscheidungsunterstützungsstatistiken zum Bestimmen der Größe des Überprüfungssatz von Falldateien.</span><span class="sxs-lookup"><span data-stu-id="bec78-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="bec78-105">Verwenden der Registerkarte Entscheiden</span><span class="sxs-lookup"><span data-stu-id="bec78-105">Using the Decide tab</span></span>

![Relevanz entscheiden](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="bec78-107">Diese Registerkarte enthält die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="bec78-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="bec78-108">**Problem**: Hier können Sie das problem von Interesse aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="bec78-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="bec78-109">**Review-Recall-Verhältnis:** Vergleiche der Erweiterten eDiscovery-Überprüfung gemäß Relevanzbewertung.</span><span class="sxs-lookup"><span data-stu-id="bec78-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="bec78-110">Der Cutoff-Punkt im Diagramm stellt den Prozentsatz der zu überprüfende Dateien dar, die einer Relevanzbewertung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bec78-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="bec78-111">Dies wird in der Relevanztestphase und als Exportschwellenwert für das Culling verwendet.</span><span class="sxs-lookup"><span data-stu-id="bec78-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="bec78-112">Der Standardschnittpunkt für die Anzahl der zu überprüfenden Dateien ist an dem Punkt, an dem das Gleichgewicht zwischen Rückruf und Genauigkeit optimal ist.</span><span class="sxs-lookup"><span data-stu-id="bec78-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="bec78-113">Der tatsächliche Stichpunkt sollte vom Benutzer abhängig von den Zielen und dem Kostenabschneiden (%review) und dem Risiko (%recall) bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="bec78-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="bec78-114">Mit dem Schieberegler können Sie den Stichpunkt anpassen und die Auswirkungen auf das Diagramm und die Parameter anzeigen, wenn Sie den Prozentteil der abzurufenden relevanten Dateien anpassen und bevor Sie eine Entscheidung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bec78-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="bec78-115">**Parameter**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics relation to the review set in relation to the collection for the entire case.</span><span class="sxs-lookup"><span data-stu-id="bec78-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="bec78-116">Die Definitionen für diese Parameter sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bec78-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="bec78-117">**Review**: Prozentsatz der Dateien, die basierend auf dieser Stichwahl überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="bec78-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="bec78-118">**Rückruf**: Prozentsatz der relevanten Dateien im Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="bec78-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="bec78-119">**Next relevant:** Kosten für die Überprüfung und Identifizierung einer anderen relevanten Datei, die sich derzeit nicht im Überprüfungssatz befindet.</span><span class="sxs-lookup"><span data-stu-id="bec78-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="bec78-120">**Gesamtkosten**: Kosten für die Überprüfung dieses Prozentsatzes der Falldateien.</span><span class="sxs-lookup"><span data-stu-id="bec78-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="bec78-121">Einstellungen für den Cost-Parameter können vom Case-Manager festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bec78-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="bec78-122">**Verteilung nach Relevanzpunktzahl:** Dateien in der dunkelgrauen Anzeige auf der linken Seite liegen unterhalb der Cutoff-Bewertung.</span><span class="sxs-lookup"><span data-stu-id="bec78-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="bec78-123">Eine QuickInfo zeigt die Relevanzbewertung und den zugehörigen Prozentsatz der Dateien in der Überprüfungsdatei im Verhältnis zu den Gesamtdateien an.</span><span class="sxs-lookup"><span data-stu-id="bec78-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="bec78-124">Im **erweiterten Detailbereich** werden weitere Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bec78-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="bec78-125">Dateien in Sammlungsfiguren enthalten keine leeren oder nebuischen Dateien.</span><span class="sxs-lookup"><span data-stu-id="bec78-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="bec78-126">Abbildungen von Familiendateien stellen Dateien dar, die nicht in Relevanz geladen, aber dennoch als Teil der Familie gezählt werden.</span><span class="sxs-lookup"><span data-stu-id="bec78-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
