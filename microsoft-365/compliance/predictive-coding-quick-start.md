---
title: Vorhersagecodierung in Advanced eDiscovery – Schnellstart
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
description: Erfahren Sie, wie Sie mit der Verwendung des Moduls für die Vorhersagecodierung in Advanced eDiscovery beginnen. Dieser Artikel führt Sie durch den End-to-End-Prozess der Verwendung von Vorhersagecodierung, um Inhalte in einem Prüfdateisatz zu identifizieren, der für Ihre Untersuchung am relevantesten ist.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822561"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="1d2f4-104">Schnellstart: Vorhersagecodierung in Advanced eDiscovery (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1d2f4-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="1d2f4-105">Dieser Artikel bietet einen Schnellstart für die Verwendung von Vorhersagecodierung in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="1d2f4-106">Das Modul für prädiktive Codierung in Advanced eDiscovery verwendet die intelligenten maschinellen Lernfunktionen in Advanced eDiscovery, um die Menge der zu überprüfenden Inhalte zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="1d2f4-107">Predictive Coding hilft Ihnen dabei, große Mengen von Fallinhalten auf eine relevante Gruppe von Elementen zu reduzieren und zu überschreiben, die Sie für die Überprüfung priorisieren können.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="1d2f4-108">Dazu erstellen und schulen Sie Ihre eigenen Modelle für die Vorhersagecodierung, die Ihnen helfen, die Überprüfung der relevantesten Elemente in einem Prüfdateisatz zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="1d2f4-109">Hier ist eine kurze Übersicht über den Prozess der Vorhersagecodierung:</span><span class="sxs-lookup"><span data-stu-id="1d2f4-109">Here's an a quick overview of the predictive coding process:</span></span>

![Schnellstartprozess für die Vorhersagecodierung](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="1d2f4-111">Zunächst erstellen Sie ein Modell, bezeichnen nur 50 Elemente als relevant oder nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="1d2f4-112">Das System verwendet diese Schulung dann, um Vorhersageergebnisse auf jedes Element im Prüfdateisatz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="1d2f4-113">Auf diese Weise können Sie Elemente basierend auf der Vorhersagebewertung filtern, sodass Sie zuerst die relevantesten (oder nicht relevanten) Elemente überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="1d2f4-114">Wenn Sie Modelle mit höheren Genauigkeits- und Rückrufraten trainieren möchten, können Sie die Bezeichnung von Elementen in nachfolgenden Schulungsrunden fortsetzen, bis sich das Modell stabilisiert.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="1d2f4-115">Sobald das Modell stabil ist, können Sie den endgültigen Vorhersagefilter anwenden, um zu überprüfende Elemente zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="1d2f4-116">Eine detaillierte Übersicht über die Vorhersagecodierung finden Sie unter [Informationen zur Vorhersagecodierung in Advanced eDiscovery.](predictive-coding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1d2f4-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="1d2f4-117">Schritt 1: Erstellen eines neuen Vorhersagecodierungsmodells</span><span class="sxs-lookup"><span data-stu-id="1d2f4-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="1d2f4-118">Der erste Schritt besteht darin, ein neues Vorhersagecodierungsmodell im Prüfdateisatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="1d2f4-119">Öffnen Sie im Microsoft 365 Compliance Center einen Advanced eDiscovery Fall, und wählen Sie dann die Registerkarte **"Prüfdateisätze" aus.**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="1d2f4-120">Öffnen Sie einen Prüfdateisatz, und klicken Sie dann auf   >  **Analytics-Vorhersagecodierung verwalten (Vorschau).**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Klicken Sie im Prüfdateisatz auf das Dropdownmenü "Analysieren", um zur Seite "Vorhersagecodierung" zu wechseln.](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="1d2f4-122">Klicken Sie auf der Seite **"Vorhersagecodierungsmodelle (Vorschau)** auf **"Neues Modell".**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="1d2f4-123">Geben Sie auf der Flyoutseite einen Namen für das Modell und eine optionale Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="1d2f4-124">Klicken Sie auf **"Speichern",** um das Modell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="1d2f4-125">Es dauert ein paar Minuten, bis das System Ihr Modell vorbereitet hat.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="1d2f4-126">Nachdem sie fertig ist, können Sie die erste Schulungsrunde durchführen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="1d2f4-127">Ausführlichere Anweisungen finden Sie unter [Erstellen eines vorhersagebasierten Codierungsmodells.](predictive-coding-create-model.md)</span><span class="sxs-lookup"><span data-stu-id="1d2f4-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="1d2f4-128">Schritt 2: Durchführen der ersten Schulungsrunde</span><span class="sxs-lookup"><span data-stu-id="1d2f4-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="1d2f4-129">Nachdem Sie das Modell erstellt haben, besteht der nächste Schritt darin, die erste Schulungsrunde abzuschließen, indem Elemente als relevant oder nicht relevant gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="1d2f4-130">Öffnen Sie den Prüfdateisatz, und klicken Sie dann auf   >  **Analytics-Vorhersagecodierung verwalten (Vorschau).**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="1d2f4-131">Wählen Sie auf der Seite **"Vorhersagecodierungsmodelle (Vorschau)** das Modell aus, das Sie trainieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="1d2f4-132">Klicken Sie auf der Registerkarte **"Übersicht"** unter **"Runde 1"** auf **"Nächste Schulungsrunde starten".**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="1d2f4-133">Die Registerkarte **"Schulung"** wird angezeigt und enthält 50 Elemente, die Sie bezeichnen können.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="1d2f4-134">Überprüfen Sie jedes Dokument,  und wählen Sie dann unten im Lesebereich die Schaltfläche Relevant oder Nicht relevant aus, um es zu bezeichnen. </span><span class="sxs-lookup"><span data-stu-id="1d2f4-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Beschriften Sie jedes Dokument als relevant oder nicht relevant](..\media\TrainModel1.png)

5. <span data-ttu-id="1d2f4-136">Nachdem Sie alle 50 Elemente beschriftet haben, klicken Sie auf **Fertig stellen.**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="1d2f4-137">Es dauert ein paar Minuten, bis das System aus Ihrer Bezeichnung "lernen" und das Modell aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="1d2f4-138">Wenn dieser Vorgang abgeschlossen ist, wird der Status **"Bereit"** für das Modell auf der **Vorschauseite (Predictive Coding Models)** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="1d2f4-139">Ausführlichere Anweisungen finden Sie unter ["Trainieren eines vorhersagebasierten Codierungsmodells".](predictive-coding-train-model.md)</span><span class="sxs-lookup"><span data-stu-id="1d2f4-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="1d2f4-140">Schritt 3: Anwenden des Vorhersagebewertungsfilters auf Elemente im Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="1d2f4-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="1d2f4-141">Nachdem Sie beim Leasen einer Schulungsrunde ausgeführt haben, können Sie den Filter für die Vorhersagebewertung auf Elemente im Prüfdateisatz anwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="1d2f4-142">Auf diese Weise können Sie die Elemente überprüfen, die das Modell als relevant oder nicht relevant prognostiziert hat.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="1d2f4-143">Öffnen Sie den Prüfdateisatz.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-143">Open the review set.</span></span>

   ![Klicken Sie auf "Filter", um die Flyoutseite "Filter" anzuzeigen.](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="1d2f4-145">Die vorinstallierten Standardfilter werden oben auf der Seite mit dem Prüfdateisatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="1d2f4-146">Sie können diese Einstellung auf **Any** belassen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="1d2f4-147">Klicken Sie auf Filter , um die Flyoutseite Filter anzuzeigen.  </span><span class="sxs-lookup"><span data-stu-id="1d2f4-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="1d2f4-148">Erweitern Sie den Abschnitt **"Analyse & Vorhersagecodierung",** um eine Reihe von Filtern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filter für die Vorhersagebewertung im Abschnitt "Analyse & Vorhersagecodierung"](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="1d2f4-150">Die Benennungskonvention für Filter für die Vorhersagebewertung ist **die Vorhersagebewertung (Modellname).**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="1d2f4-151">Beispielsweise ist der Filtername der Vorhersagebewertung für ein Modell mit dem Namen **Modell A** **die Vorhersagebewertung (Modell A).**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="1d2f4-152">Wählen Sie den Filter für die Vorhersagebewertung aus, den Sie verwenden möchten, und klicken Sie dann auf **"Fertig".**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="1d2f4-153">Klicken Sie auf der Seite mit dem Prüfdateisatz auf die Dropdownliste für den Filter für die Vorhersagebewertung, und geben Sie die Mindest- und Höchstwerte für den Bereich der Vorhersagebewertung ein.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="1d2f4-154">Der folgende Screenshot zeigt beispielsweise einen Vorhersagebewertungsbereich zwischen **0,5** und **1,0.**</span><span class="sxs-lookup"><span data-stu-id="1d2f4-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Mindest- und Höchstwerte für den Filter für die Vorhersagebewertung](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="1d2f4-156">Klicken Sie außerhalb des Filters, um den Filter automatisch auf den Prüfdateisatz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="1d2f4-157">Eine Liste der Dokumente mit einer Vorhersagebewertung innerhalb des angegebenen Bereichs wird auf der Seite mit dem Prüfdateisatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="1d2f4-158">Ausführlichere Anweisungen finden Sie unter [Anwenden eines Vorhersagefilters auf einen Prüfdateisatz.](predictive-coding-apply-prediction-filter.md)</span><span class="sxs-lookup"><span data-stu-id="1d2f4-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="1d2f4-159">Schritt 4: Durchführen weiterer Schulungsrunden</span><span class="sxs-lookup"><span data-stu-id="1d2f4-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="1d2f4-160">Höchstwahrscheinlich müssen Sie mehr Schulungsrunden durchführen, um das Modul zu schulen, um relevante und nicht relevante Elemente im Prüfdateisatz besser vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="1d2f4-161">Im Allgemeinen trainieren Sie das Modell so lange, bis es ausreichend stabil ist, um Ihre Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="1d2f4-162">Weitere Informationen finden Sie unter ["Durchführen zusätzlicher Schulungsrunden"](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="1d2f4-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="1d2f4-163">Schritt 5: Anwenden des endgültigen Filter für die Vorhersagebewertung zur Priorisierung der Überprüfung</span><span class="sxs-lookup"><span data-stu-id="1d2f4-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="1d2f4-164">Wiederholen Sie die Anweisungen in Schritt 3, um die endgültige Vorhersagebewertung auf den Prüfdateisatz anzuwenden, um die Überprüfung relevanter und nicht relevanter Elemente zu priorisieren, nachdem Sie alle Schulungsrunden abgeschlossen und das Modell stabilisiert haben.</span><span class="sxs-lookup"><span data-stu-id="1d2f4-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
