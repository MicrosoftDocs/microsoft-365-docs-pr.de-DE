---
title: Neutrainieren eines Klassifizierers in der Kommunikationscompliance
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
description: Erfahren Sie, wie Sie Feedback zu einem trainierbaren Klassifikator in der Kommunikationskonformität bereitstellen.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918146"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="39843-103">Neutrainieren eines Klassifizierers in der Kommunikationscompliance</span><span class="sxs-lookup"><span data-stu-id="39843-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="39843-104">Ein trainierbarer Microsoft 365-Klassifikator ist ein Tool, das Sie schulen können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben.</span><span class="sxs-lookup"><span data-stu-id="39843-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="39843-105">Nach der Ausbildung können Sie es verwenden, um Elemente für die Anwendung von Office-Vertraulichkeitsbezeichnungen, Richtlinien zur Kommunikationskonformität und Aufbewahrungsbezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="39843-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="39843-106">In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifikatoren und einigen vordefinierten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="39843-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="39843-107">Weitere Informationen zu den verschiedenen Typen von Klassifizierungen finden Sie [unter Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="39843-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="39843-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39843-108">Permissions</span></span>

<span data-ttu-id="39843-109">So greifen Sie auf Klassifikatoren im Microsoft 365 Compliance Center zu:</span><span class="sxs-lookup"><span data-stu-id="39843-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="39843-110">Die Rolle des Complianceadministrators oder der Compliancedatenadministrator ist erforderlich, um einen Klassifizierer zu schulen.</span><span class="sxs-lookup"><span data-stu-id="39843-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="39843-111">Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierungen in den folgenden Szenarien verwenden zu können:</span><span class="sxs-lookup"><span data-stu-id="39843-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="39843-112">Szenario der Kommunikationskonformitätsrichtlinie: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="39843-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="39843-113">Gesamtworkflow</span><span class="sxs-lookup"><span data-stu-id="39843-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39843-114">Sie geben Feedback in der Compliancelösung, die den Klassifizierungs-Klassifikator als Bedingung verwendet.</span><span class="sxs-lookup"><span data-stu-id="39843-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="39843-115">**Wenn Sie nicht über eine Kommunikationskonformitätsrichtlinie verfügen, die einen Klassifikator als Bedingung verwendet, beenden Sie hier.**</span><span class="sxs-lookup"><span data-stu-id="39843-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="39843-116">Wenn Sie Ihre Klassifizierungen verwenden, können Sie die Genauigkeit der Klassifizierungen erhöhen, die sie machen.</span><span class="sxs-lookup"><span data-stu-id="39843-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="39843-117">Dazu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder nicht übereinstimmend identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="39843-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="39843-118">Nachdem Sie 30 Auswertungen für einen Klassifikator erstellt haben, wird dieses Feedback benötigt und automatisch neu trainiert.</span><span class="sxs-lookup"><span data-stu-id="39843-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="39843-119">Weitere Informationen zum allgemeinen Workflow zum Umschulungstraining eines Klassifikierers finden Sie unter [Prozessablauf zum Umschulungen eines Klassifizierers](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="39843-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="39843-120">Ein Klassifikator muss bereits veröffentlicht und verwendet werden, bevor er umtrainiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="39843-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="39843-121">So umtrainieren Sie einen Klassifizierer in Kommunikationskonformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="39843-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="39843-122">Öffnen Sie die Kommunikationskonformitätsrichtlinie, die einen Klassifikator als Bedingung verwendet, und wählen Sie eines der identifizierten Elemente aus der **Liste Ausstehend** aus.</span><span class="sxs-lookup"><span data-stu-id="39843-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="39843-123">Wählen Sie die Auslassungs- und **Verbesserungsklassifikation aus.**</span><span class="sxs-lookup"><span data-stu-id="39843-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="39843-124">Wenn das **Element im Bereich** Detailliertes Feedback ein echtes Positives ist, wählen Sie Match **aus.**</span><span class="sxs-lookup"><span data-stu-id="39843-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="39843-125">Wenn das Element ein falsch positives Element ist, d. h. es wurde fälschlicherweise in die Kategorie eingeschlossen, wählen Sie **Keine Übereinstimmung aus.**</span><span class="sxs-lookup"><span data-stu-id="39843-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="39843-126">Wenn es einen anderen Klassifikator gibt, der für das Element geeigneter wäre, können Sie ihn in der Liste **Andere trainierbare Klassifikatoren** vorschlagen auswählen.</span><span class="sxs-lookup"><span data-stu-id="39843-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="39843-127">Dadurch wird der andere Klassifikator ausgelöst, um das Element auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="39843-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="39843-128">Sie können Feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann **detailliertes** Feedback in der Befehlsleiste bereitstellen auswählen.</span><span class="sxs-lookup"><span data-stu-id="39843-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="39843-129">Wählen **Sie Feedback senden** aus, um Ihre Bewertung der , Klassifizierungen zu senden und andere `match` `not a match` trainierbare Klassifikatoren vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="39843-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="39843-130">Wenn Sie einem Klassifikator 30 Feedbackinstanzen bereitgestellt haben, wird dieser automatisch umtrainiert.</span><span class="sxs-lookup"><span data-stu-id="39843-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="39843-131">Eine Umschulung kann zwischen 1 und 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="39843-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="39843-132">Klassifizierungen können nur zweimal pro Tag umtrainiert werden.</span><span class="sxs-lookup"><span data-stu-id="39843-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39843-133">Diese Informationen werden an den Klassifikator in Ihrem Mandanten gesendet, **sie gehen nicht zurück zu Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="39843-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="39843-134">Öffnen Sie **die Seite Datenklassifizierung** im **Microsoft 365 Compliance Center**.</span><span class="sxs-lookup"><span data-stu-id="39843-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="39843-135">Öffnen **Sie Trainable-Klassifikatoren**.</span><span class="sxs-lookup"><span data-stu-id="39843-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="39843-136">Der Klassifikator, der in Ihrer Kommunikationskonformitätsrichtlinie verwendet wurde, wird unter der Überschrift **Neuschulung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39843-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Klassifizierung im Umschulungsstatus](../media/classifier-retraining.png)

9. <span data-ttu-id="39843-138">Nachdem die Umschulung abgeschlossen ist, wählen Sie den Klassifikator aus, um die Übersicht über die Umschulung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="39843-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Übersicht über die Klassifizierer-Umschulungsergebnisse](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="39843-140">Überprüfen Sie die empfohlene Aktion und die Vorhersagevergleiche der umtrainierten und aktuell veröffentlichten Versionen des Klassifizierungsklassifikierers.</span><span class="sxs-lookup"><span data-stu-id="39843-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="39843-141">Wenn Sie mit den Ergebnissen der Umschulung zufrieden sind, wählen Sie **Erneut veröffentlichen aus.**</span><span class="sxs-lookup"><span data-stu-id="39843-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="39843-142">Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie zusätzliches Feedback an den Klassifikator in der Kommunikationskonformitätsschnittstelle senden und einen weiteren Umschulungszyklus starten oder nichts tun. In diesem Fall wird die aktuell veröffentlichte Version des Klassifizierungsmoduls weiterhin verwendet.</span><span class="sxs-lookup"><span data-stu-id="39843-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="39843-143">Details zur erneuten Veröffentlichen von Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="39843-143">Details on republishing recommendations</span></span>

<span data-ttu-id="39843-144">Hier finden Sie ein wenig Informationen dazu, wie wir die Empfehlung formulieren, einen umtrainierten Klassifizierer erneut zu veröffentlichen oder weitere Umschulungen vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="39843-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="39843-145">Dies erfordert ein wenig tieferes Verständnis der Funktionsweise trainierbarer Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="39843-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="39843-146">Nach einer Umschulung bewerten wir die Leistung des Klassifikierers sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren des Klassifizierungsfeeders verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="39843-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="39843-147">Bei integrierten Modellen sind Elemente, die zum Trainieren des Klassifizierers verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39843-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="39843-148">Bei benutzerdefinierten Modellen werden elemente, die in der ursprünglichen Schulung verwendet werden, von den Websites, die Sie zum Testen und Überprüfen hinzugefügt haben, verwendet.</span><span class="sxs-lookup"><span data-stu-id="39843-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="39843-149">Wir vergleichen die Leistungszahlen für beide Gruppen von Elementen für den umtrainierten und veröffentlichten Klassifikator, um eine Empfehlung zur Verbesserung der Veröffentlichung zu geben.</span><span class="sxs-lookup"><span data-stu-id="39843-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="39843-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39843-150">See also</span></span>

- [<span data-ttu-id="39843-151">Weitere Informationen zu trainierbaren Klassifizierern</span><span class="sxs-lookup"><span data-stu-id="39843-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="39843-152">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="39843-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)