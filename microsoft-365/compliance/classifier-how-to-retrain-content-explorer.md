---
title: Neutrainieren eines Klassifizierers im Inhalts-Explorer
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Feedback an einen trainierbaren Klassifizierer im Inhalts-Explorer senden.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793064"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="e9579-103">Neutrainieren eines Klassifizierers im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="e9579-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="e9579-104">Ein Microsoft 365 trainierbarer Klassifizierer ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben.</span><span class="sxs-lookup"><span data-stu-id="e9579-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="e9579-105">Sobald Sie geschult sind, können Sie damit Elemente für die Anwendung von Office Vertraulichkeitsbezeichnungen, Kommunikationscompliancerichtlinien und Aufbewahrungsbezeichnungsrichtlinien identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9579-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="e9579-106">In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifizierern und einigen bereits trainierten Klassifizierern durch zusätzliches Feedback verbessern.</span><span class="sxs-lookup"><span data-stu-id="e9579-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="e9579-107">Weitere Informationen zu den verschiedenen Typen von Klassifizierern finden Sie unter [Informationen zu trainierbaren Klassifizierern.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="e9579-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="e9579-108">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Optimierungs- und Umschulungsprozess zu geben.</span><span class="sxs-lookup"><span data-stu-id="e9579-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="e9579-109">Sie müssen immer noch diesen vollständigen Artikel lesen, um die Details zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e9579-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="e9579-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e9579-110">Permissions</span></span>

<span data-ttu-id="e9579-111">So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierer zu:</span><span class="sxs-lookup"><span data-stu-id="e9579-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="e9579-112">Die Rolle "Complianceadministrator" oder "Compliancedatenadministrator" ist erforderlich, um einen Klassifizierer zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="e9579-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="e9579-113">Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierer in diesen Szenarien zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="e9579-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="e9579-114">Szenario mit Aufbewahrungsbezeichnungsrichtlinien: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung"</span><span class="sxs-lookup"><span data-stu-id="e9579-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="e9579-115">Gesamter Workflow</span><span class="sxs-lookup"><span data-stu-id="e9579-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9579-116">Sie geben im Inhalts-Explorer Feedback für die automatische Anwendung von Aufbewahrungsbezeichnungsrichtlinien auf Exchange Elemente und verwenden den Klassifizierer als Bedingung.</span><span class="sxs-lookup"><span data-stu-id="e9579-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="e9579-117">**Wenn Sie keine Aufbewahrungsrichtlinie haben, die automatisch eine Aufbewahrungsbezeichnung auf Exchange Elemente anwendet und eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**</span><span class="sxs-lookup"><span data-stu-id="e9579-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="e9579-118">Wenn Sie Ihre Klassifizierer verwenden, sollten Sie die Genauigkeit der Klassifizierungen erhöhen, die sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9579-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="e9579-119">Dazu bewerten Sie die Qualität der Klassifizierungen, die für Elemente erstellt wurden, die als Übereinstimmung oder nicht als Übereinstimmung identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="e9579-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="e9579-120">Nachdem Sie 30 Auswertungen für einen Klassifizierer durchgeführt haben, nimmt er dieses Feedback und trainiert sich automatisch neu.</span><span class="sxs-lookup"><span data-stu-id="e9579-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="e9579-121">Weitere Informationen zum allgemeinen Workflow der Umschulung eines Klassifizierers finden Sie unter [Prozessablauf für die Umschulung eines Klassifizierers.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="e9579-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="e9579-122">Ein Klassifizierer muss bereits veröffentlicht und verwendet werden, bevor er umgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9579-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="e9579-123">Neutrainieren eines Klassifizierers im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="e9579-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="e9579-124">Melden Sie sich bei Microsoft 365 Compliance Center mit Compliance-Administrator- oder Sicherheitsadministratorrollenzugriff an, und öffnen **Sie Microsoft 365 Compliance Center Data**  >  **classification**  >  **Content Explorer.**</span><span class="sxs-lookup"><span data-stu-id="e9579-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="e9579-125">Erweitern Sie unter dem **Filter nach Bezeichnungen, Informationstypen oder Kategorienlisten** **trainierbare Klassifizierer.**</span><span class="sxs-lookup"><span data-stu-id="e9579-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9579-126">Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift der trainierbaren Klassifizierer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9579-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="e9579-127">Wählen Sie den trainierbaren Klassifizierer aus, den Sie bei der automatischen Anwendung der Aufbewahrungsbezeichnungsrichtlinie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="e9579-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="e9579-128">Dies ist der trainierbare Klassifizierer, zu dem Sie Feedback geben.</span><span class="sxs-lookup"><span data-stu-id="e9579-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="e9579-129">Wenn ein Element einen Eintrag in der Spalte **"Aufbewahrungsbezeichnung"** aufweist, bedeutet dies, dass das Element als . `match`</span><span class="sxs-lookup"><span data-stu-id="e9579-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="e9579-130">Wenn ein Element keinen Eintrag in der Spalte **"Aufbewahrungsbezeichnung"** enthält, bedeutet dies, dass es als klassifiziert `close match` wurde.</span><span class="sxs-lookup"><span data-stu-id="e9579-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="e9579-131">Sie können die Klassifizierergenauigkeit am besten verbessern, indem Sie Feedback zu `close match` Elementen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e9579-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="e9579-132">Wählen Sie ein Element aus, und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="e9579-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="e9579-133">Sie können Feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann in der Befehlsleiste **"Klassifizierung verbessern"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e9579-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="e9579-134">Wählen Sie **"Feedback bereitstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="e9579-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="e9579-135">Wenn das Element ein echtes Positives ist, wählen Sie im Bereich **"Detailliertes Feedback"** die Option **"Übereinstimmung"** aus.</span><span class="sxs-lookup"><span data-stu-id="e9579-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="e9579-136">Wenn das Element ein falsch positives Ergebnis ist, d. h. es wurde nicht ordnungsgemäß in die Kategorie aufgenommen, wählen Sie **"Nicht übereinstimmend"** aus.</span><span class="sxs-lookup"><span data-stu-id="e9579-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="e9579-137">Wenn es einen anderen Klassifizierer gibt, der für das Element besser geeignet wäre, können Sie ihn aus der Liste **"Andere trainierbare Klassifizierer vorschlagen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e9579-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="e9579-138">Dadurch wird der andere Klassifizierer ausgelöst, um das Element auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="e9579-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="e9579-139">Wählen Sie **"Feedback senden"** aus, um Ihre Auswertung der Klassifizierungen zu senden `match` und andere `not a match` trainierbare Klassifizierer vorzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="e9579-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="e9579-140">Wenn Sie 30 Instanzen von Feedback an einen Klassifizierer übermittelt haben, wird er automatisch neu trainiert.</span><span class="sxs-lookup"><span data-stu-id="e9579-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="e9579-141">Die Umschulung kann zwischen 1 und 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="e9579-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="e9579-142">Klassifizierer können nur zweimal pro Tag trainiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9579-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9579-143">Diese Informationen werden an den Klassifizierer in Ihrem Mandanten weitergeleitet, **sie gehen nicht an Microsoft zurück.**</span><span class="sxs-lookup"><span data-stu-id="e9579-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="e9579-144">Öffnen **Sie trainierbare Klassifizierer.**</span><span class="sxs-lookup"><span data-stu-id="e9579-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="e9579-145">Der Klassifizierer, der in Ihrer Kommunikationscompliancerichtlinie verwendet wurde, wird unter der Überschrift **"Erneute Schulung"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9579-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Klassifizierer im Umschulungsstatus](../media/classifier-retraining.png)

11. <span data-ttu-id="e9579-147">Nachdem die Umschulung abgeschlossen ist, wählen Sie den Klassifizierer aus, um die Übersicht über die Umschulung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e9579-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Übersicht über die Klassifizierer-Neuschulungsergebnisse](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="e9579-149">Überprüfen Sie die empfohlene Aktion und die Vorhersagevergleiche der umgeleiteten und aktuell veröffentlichten Versionen des Klassifizierers.</span><span class="sxs-lookup"><span data-stu-id="e9579-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="e9579-150">Wenn Sie mit den Ergebnissen der Umschulung zufrieden sind, wählen Sie **"Erneut veröffentlichen"** aus.</span><span class="sxs-lookup"><span data-stu-id="e9579-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="e9579-151">Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie zusätzliches Feedback an den Klassifizierer in der Benutzeroberfläche des Inhalts-Explorers senden und einen weiteren Umschulungszyklus starten oder nichts unternehmen, in diesem Fall wird die derzeit veröffentlichte Version des Klassifizierers weiterhin verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9579-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="e9579-152">Details zu Empfehlungen zur erneuten Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="e9579-152">Details on republishing recommendations</span></span>

<span data-ttu-id="e9579-153">Hier finden Sie einige Informationen dazu, wie wir die Empfehlung formulieren, einen umgeleiteten Klassifizierer erneut zu veröffentlichen oder eine weitere Umschulung vorzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="e9579-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="e9579-154">Dies erfordert ein wenig tieferes Verständnis der Funktionsweise trainierbarer Klassifizierer.</span><span class="sxs-lookup"><span data-stu-id="e9579-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="e9579-155">Nach einer Neuschulung bewerten wir die Leistung des Klassifizierers sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren des Klassifizierers verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e9579-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="e9579-156">Bei integrierten Modellen sind Elemente, die zum Trainieren des Klassifizierers verwendet werden, die Von Microsoft zum Erstellen des Modells verwendeten Elemente.</span><span class="sxs-lookup"><span data-stu-id="e9579-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="e9579-157">Bei benutzerdefinierten Modellen stammen die Elemente, die in der ursprünglichen Schulung verwendet werden, von den Websites, die Sie zum Testen und Überprüfen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="e9579-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="e9579-158">Wir vergleichen die Leistungsnummern für beide Gruppen von Elementen für den neu geschulten und veröffentlichten Klassifizierer, um eine Empfehlung zu geben, ob eine erneute Veröffentlichung verbessert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="e9579-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e9579-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9579-159">See also</span></span>

- [<span data-ttu-id="e9579-160">Weitere Informationen zu trainierbaren Klassifizierern</span><span class="sxs-lookup"><span data-stu-id="e9579-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="e9579-161">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="e9579-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)