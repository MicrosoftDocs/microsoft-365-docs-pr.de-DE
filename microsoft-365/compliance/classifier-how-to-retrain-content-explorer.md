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
description: Erfahren Sie, wie Sie einem trainierbaren Klassifikator im Inhalts-Explorer Feedback geben.
ms.openlocfilehash: fabfe8e4df377c25012b358960d7f7ff7ff994bc
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423262"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="75cb0-103">Neutrainieren eines Klassifizierers im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="75cb0-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="75cb0-104">Ein trainierbarer Microsoft 365-Klassifikator ist ein Tool, das Sie schulen können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben.</span><span class="sxs-lookup"><span data-stu-id="75cb0-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="75cb0-105">Nach der Ausbildung können Sie es verwenden, um Elemente für die Anwendung von Office-Vertraulichkeitsbezeichnungen, Richtlinien zur Kommunikationskonformität und Aufbewahrungsbezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="75cb0-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="75cb0-106">In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifikatoren und einigen vordefinierten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="75cb0-107">Weitere Informationen zu den verschiedenen Typen von Klassifizierungen finden Sie [unter Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="75cb0-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="75cb0-108">Sehen Sie sich dieses Video an, um eine kurze Zusammenfassung des Optimierungs- und Umschulungsprozesses zu finden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="75cb0-109">Sie müssen weiterhin diesen vollständigen Artikel lesen, um die Details zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75cb0-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="75cb0-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="75cb0-110">Permissions</span></span>

<span data-ttu-id="75cb0-111">So greifen Sie auf Klassifikatoren im Microsoft 365 Compliance Center zu:</span><span class="sxs-lookup"><span data-stu-id="75cb0-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="75cb0-112">Die Rolle des Complianceadministrators oder der Compliancedatenadministrator ist erforderlich, um einen Klassifizierer zu schulen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="75cb0-113">Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierungen in den folgenden Szenarien verwenden zu können:</span><span class="sxs-lookup"><span data-stu-id="75cb0-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="75cb0-114">Szenario der Aufbewahrungsbezeichnungsrichtlinie: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung"</span><span class="sxs-lookup"><span data-stu-id="75cb0-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="75cb0-115">Gesamtworkflow</span><span class="sxs-lookup"><span data-stu-id="75cb0-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75cb0-116">Sie geben Feedback im Inhalts-Explorer für die automatische Anwendung von Aufbewahrungsbezeichnungsrichtlinien auf Exchange-Elemente und verwenden den Klassifikator als Bedingung.</span><span class="sxs-lookup"><span data-stu-id="75cb0-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="75cb0-117">**Wenn Sie nicht über eine Aufbewahrungsrichtlinie verfügen, die eine Aufbewahrungsbezeichnung automatisch auf Exchange-Elemente angewendet und einen Klassifizierungsaufbewahrungszeichen als Bedingung verwendet, beenden Sie hier.**</span><span class="sxs-lookup"><span data-stu-id="75cb0-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="75cb0-118">Wenn Sie Ihre Klassifizierungen verwenden, können Sie die Genauigkeit der Klassifizierungen erhöhen, die sie machen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="75cb0-119">Dazu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder nicht übereinstimmend identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="75cb0-120">Nachdem Sie 30 Auswertungen für einen Klassifikator erstellt haben, wird dieses Feedback benötigt und automatisch neu trainiert.</span><span class="sxs-lookup"><span data-stu-id="75cb0-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="75cb0-121">Weitere Informationen zum allgemeinen Workflow zum Umschulungstraining eines Klassifikierers finden Sie unter [Prozessablauf zum Umschulungen eines Klassifizierers](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="75cb0-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="75cb0-122">Ein Klassifikator muss bereits veröffentlicht und verwendet werden, bevor er umtrainiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="75cb0-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="75cb0-123">Neutrainieren eines Klassifizierers im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="75cb0-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="75cb0-124">Melden Sie sich beim Microsoft 365 Compliance Center mit Dem Zugriff auf die Rolle des Complianceadministrators oder Sicherheitsadministrators an, und öffnen Sie **Microsoft 365 Compliance Center**  >  **Datenklassifizierung**  >  **Inhalts-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="75cb0-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="75cb0-125">Erweitern Sie **unter Filter on labels, info types, or categories list** **trainable classifiers**.</span><span class="sxs-lookup"><span data-stu-id="75cb0-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75cb0-126">Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift trainierbare Klassifizierungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="75cb0-127">Wählen Sie den trainierbaren Klassifikator aus, den Sie in Der Aufbewahrungsbezeichnungsrichtlinie automatisch anwenden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="75cb0-128">Dies ist der trainierbare Klassifikator, zu dem Sie Feedback geben.</span><span class="sxs-lookup"><span data-stu-id="75cb0-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="75cb0-129">Wenn ein Element über einen Eintrag in der **Spalte** Aufbewahrungsbezeichnung verfügt, bedeutet dies, dass das Element als klassifiziert `match` wurde.</span><span class="sxs-lookup"><span data-stu-id="75cb0-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="75cb0-130">Wenn ein Element keinen Eintrag in der Spalte Aufbewahrungsbezeichnung **hat,** bedeutet dies, dass es als klassifiziert `close match` wurde.</span><span class="sxs-lookup"><span data-stu-id="75cb0-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="75cb0-131">Sie können die Klassifiziergenauigkeit am besten verbessern, indem Sie Feedback zu Elementen `close match` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="75cb0-132">Wählen Sie ein Element aus, und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="75cb0-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="75cb0-133">Sie können Feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann **in** der Befehlsleiste die Klassifizierung verbessern auswählen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="75cb0-134">Wählen **Sie Feedback bereitstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="75cb0-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="75cb0-135">Wenn das **Element im Bereich** Detailliertes Feedback ein echtes Positives ist, wählen Sie Match **aus.**</span><span class="sxs-lookup"><span data-stu-id="75cb0-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="75cb0-136">Wenn das Element ein falsch positives Element ist, d. h. es wurde fälschlicherweise in die Kategorie eingeschlossen, wählen Sie **Keine Übereinstimmung aus.**</span><span class="sxs-lookup"><span data-stu-id="75cb0-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="75cb0-137">Wenn es einen anderen Klassifikator gibt, der für das Element geeigneter wäre, können Sie ihn in der Liste **Andere trainierbare Klassifikatoren** vorschlagen auswählen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="75cb0-138">Dadurch wird der andere Klassifikator ausgelöst, um das Element auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="75cb0-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="75cb0-139">Wählen **Sie Feedback senden** aus, um Ihre Bewertung der , Klassifizierungen zu senden und andere `match` `not a match` trainierbare Klassifikatoren vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="75cb0-140">Wenn Sie einem Klassifikator 30 Feedbackinstanzen bereitgestellt haben, wird dieser automatisch umtrainiert.</span><span class="sxs-lookup"><span data-stu-id="75cb0-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="75cb0-141">Eine Umschulung kann zwischen ein und vier Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="75cb0-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="75cb0-142">Klassifizierungen können nur zweimal pro Tag umtrainiert werden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75cb0-143">Diese Informationen werden an den Klassifikator in Ihrem Mandanten gesendet, **sie gehen nicht zurück zu Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="75cb0-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="75cb0-144">Öffnen **Sie Trainable-Klassifikatoren**.</span><span class="sxs-lookup"><span data-stu-id="75cb0-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="75cb0-145">Der Klassifikator, der in Ihrer Kommunikationskonformitätsrichtlinie verwendet wurde, wird unter der Überschrift **Neuschulung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75cb0-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Klassifizierung im Umschulungsstatus](../media/classifier-retraining.png)

11. <span data-ttu-id="75cb0-147">Nachdem die Umschulung abgeschlossen ist, wählen Sie den Klassifikator aus, um die Übersicht über die Umschulung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Übersicht über die Klassifizierer-Umschulungsergebnisse](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="75cb0-149">Überprüfen Sie die empfohlene Aktion und die Vorhersagevergleiche der umtrainierten und aktuell veröffentlichten Versionen des Klassifizierungsklassifikierers.</span><span class="sxs-lookup"><span data-stu-id="75cb0-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="75cb0-150">Wenn Sie mit den Ergebnissen der Umschulung zufrieden sind, wählen Sie **Erneut veröffentlichen aus.**</span><span class="sxs-lookup"><span data-stu-id="75cb0-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="75cb0-151">Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie zusätzliches Feedback an den Klassifikator in der Kommunikationskonformitätsschnittstelle senden und einen weiteren Umschulungszyklus starten oder nichts tun. In diesem Fall wird die aktuell veröffentlichte Version des Klassifizierungsmoduls weiterhin verwendet.</span><span class="sxs-lookup"><span data-stu-id="75cb0-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="75cb0-152">Details zur erneuten Veröffentlichen von Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="75cb0-152">Details on republishing recommendations</span></span>

<span data-ttu-id="75cb0-153">Hier finden Sie ein wenig Informationen dazu, wie wir die Empfehlung formulieren, einen umtrainierten Klassifizierer erneut zu veröffentlichen oder weitere Umschulungen vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="75cb0-154">Dies erfordert ein wenig tieferes Verständnis der Funktionsweise trainierbarer Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="75cb0-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="75cb0-155">Nach einer Umschulung bewerten wir die Leistung des Klassifikierers sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren des Klassifizierungsfeeders verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="75cb0-156">Bei integrierten Modellen sind Elemente, die zum Trainieren des Klassifizierers verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75cb0-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="75cb0-157">Bei benutzerdefinierten Modellen werden elemente, die in der ursprünglichen Schulung verwendet werden, von den Websites, die Sie zum Testen und Überprüfen hinzugefügt haben, verwendet.</span><span class="sxs-lookup"><span data-stu-id="75cb0-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="75cb0-158">Wir vergleichen die Leistungszahlen für beide Gruppen von Elementen für den umtrainierten und veröffentlichten Klassifikator, um eine Empfehlung zur Verbesserung der Veröffentlichung zu geben.</span><span class="sxs-lookup"><span data-stu-id="75cb0-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="75cb0-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75cb0-159">See also</span></span>

- [<span data-ttu-id="75cb0-160">Weitere Informationen zu trainierbaren Klassifizierern</span><span class="sxs-lookup"><span data-stu-id="75cb0-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="75cb0-161">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="75cb0-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
