---
title: Anwenden des Filter für die Vorhersagebewertung auf Elemente in einem Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Verwenden Sie einen Filter für die Vorhersagebewertung, um Elemente anzuzeigen, die von einem vorhersagebasierten Codierungsmodell als relevant oder nicht relevant prognostiziert werden.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822529"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="012ca-103">Anwenden eines Filter für die Vorhersagebewertung auf einen Prüfdateisatz (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="012ca-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="012ca-104">Nachdem Sie in Advanced eDiscovery ein Modell für die prädiktive Codierung erstellt und so trainiert haben, dass es stabil ist, können Sie den Filter für die Vorhersagebewertung anwenden, um die vom Modell ermittelten Prüfdateisatzelemente anzuzeigen, die relevant (oder nicht relevant) sind.</span><span class="sxs-lookup"><span data-stu-id="012ca-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="012ca-105">Wenn Sie ein Modell erstellen, wird auch ein entsprechender Filter für die Vorhersagebewertung erstellt.</span><span class="sxs-lookup"><span data-stu-id="012ca-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="012ca-106">Sie können diesen Filter verwenden, um Elemente anzuzeigen, denen eine Vorhersagebewertung innerhalb eines bestimmten Bereichs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="012ca-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="012ca-107">Im Allgemeinen sind Vorhersageergebnisse zwischen **0** und **5** Elementen zugewiesen, die vom Modell vorhergesagt wurden, sind nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="012ca-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="012ca-108">Elemente, denen Vorhersageergebnisse zwischen **0,5** und **1,0** zugewiesen wurden, sind Elemente, die vom Modell vorhergesagt wurden, sind relevant.</span><span class="sxs-lookup"><span data-stu-id="012ca-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="012ca-109">Hier sind zwei Möglichkeiten, wie Sie den Filter für die Vorhersagebewertung verwenden können:</span><span class="sxs-lookup"><span data-stu-id="012ca-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="012ca-110">Priorisieren Der Überprüfung von Elementen in einem Prüfdateisatz, den das Modell vorausgesagt hat, ist relevant.</span><span class="sxs-lookup"><span data-stu-id="012ca-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="012ca-111">Elemente aus dem Prüfdateisatz, den das Modell vorhergesagt hat, zu entfernen, sind nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="012ca-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="012ca-112">Alternativ können Sie den Filter für die Vorhersagebewertung verwenden, um die Überprüfung von nicht relevanten Elementen zu depriorisieren.</span><span class="sxs-lookup"><span data-stu-id="012ca-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="012ca-113">Bevor Sie einen Filter für die Vorhersagebewertung anwenden</span><span class="sxs-lookup"><span data-stu-id="012ca-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="012ca-114">Erstellen Sie ein Modell für die Vorhersagecodierung, sodass ein entsprechender Filter für die Vorhersagebewertung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="012ca-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="012ca-115">Sie können einen Filter für die Vorhersagebewertung nach einer der Schulungsrunden anwenden.</span><span class="sxs-lookup"><span data-stu-id="012ca-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="012ca-116">Sie können jedoch warten, nachdem Sie mehrere Runden ausgeführt haben, oder bis das Modell stabil ist, bevor Sie den Filter für die Vorhersagebewertung verwenden.</span><span class="sxs-lookup"><span data-stu-id="012ca-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="012ca-117">Anwenden eines Filter für die Vorhersagebewertung</span><span class="sxs-lookup"><span data-stu-id="012ca-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="012ca-118">Öffnen Sie im Microsoft 365 Compliance Center die Advanced eDiscovery Fall, wählen Sie die Registerkarte **"Prüfdateisätze"** aus, und öffnen Sie dann den Prüfdateisatz.</span><span class="sxs-lookup"><span data-stu-id="012ca-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Klicken Sie auf "Filter", um die Flyoutseite "Filter" anzuzeigen.](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="012ca-120">Die vorinstallierten Standardfilter werden oben auf der Seite mit dem Prüfdateisatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="012ca-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="012ca-121">Sie können diese Einstellung auf **Any** belassen.</span><span class="sxs-lookup"><span data-stu-id="012ca-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="012ca-122">Klicken Sie auf Filter , um die Flyoutseite Filter anzuzeigen.  </span><span class="sxs-lookup"><span data-stu-id="012ca-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="012ca-123">Erweitern Sie den Abschnitt **"Analyse & Vorhersagecodierung",** um eine Reihe von Filtern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="012ca-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filter für die Vorhersagebewertung im Abschnitt "Analyse & Vorhersagecodierung"](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="012ca-125">Die Benennungskonvention für Filter für die Vorhersagebewertung ist **die Vorhersagebewertung (Modellname).**</span><span class="sxs-lookup"><span data-stu-id="012ca-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="012ca-126">Beispielsweise ist der Filtername der Vorhersagebewertung für ein Modell mit dem Namen **Modell A** **die Vorhersagebewertung (Modell A).**</span><span class="sxs-lookup"><span data-stu-id="012ca-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="012ca-127">Wählen Sie den Filter für die Vorhersagebewertung aus, den Sie verwenden möchten, und klicken Sie dann auf **"Fertig".**</span><span class="sxs-lookup"><span data-stu-id="012ca-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="012ca-128">Klicken Sie auf der Seite mit dem Prüfdateisatz auf die Dropdownliste für den Filter für die Vorhersagebewertung, und geben Sie die Mindest- und Höchstwerte für den Bereich der Vorhersagebewertung ein.</span><span class="sxs-lookup"><span data-stu-id="012ca-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="012ca-129">Der folgende Screenshot zeigt beispielsweise einen Vorhersagebewertungsbereich zwischen **0,5** und **1,0.**</span><span class="sxs-lookup"><span data-stu-id="012ca-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Mindest- und Höchstwerte für den Filter für die Vorhersagebewertung](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="012ca-131">Klicken Sie außerhalb des Filters, um den Filter automatisch auf den Prüfdateisatz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="012ca-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="012ca-132">Eine Liste der Dokumente mit einer Vorhersagebewertung innerhalb des angegebenen Bereichs wird auf der Seite mit dem Prüfdateisatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="012ca-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="012ca-133">Um die tatsächliche Vorhersagebewertung anzuzeigen, die einem Dokument zugewiesen ist, können Sie im Lesebereich auf die Registerkarte **"Metadaten"** klicken.</span><span class="sxs-lookup"><span data-stu-id="012ca-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="012ca-134">Die Vorhersageergebnisse für alle Modelle im Prüfdateisatz werden in der **RelevanceScores-Metadateneigenschaft** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="012ca-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="012ca-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="012ca-135">More information</span></span>

- <span data-ttu-id="012ca-136">Weitere Informationen zur Verwendung von Filtern finden Sie unter [Abfragen und Filtern von Inhalten in einem Prüfdateisatz.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="012ca-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
