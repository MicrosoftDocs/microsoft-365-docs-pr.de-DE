---
title: Vorgehensweise Umschulung einer Klassifizierung in Communications Compliance (Vorschau)
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
description: Hier erfahren Sie, wie Sie Feedback für eine Lernende Klassifizierung in Communications Compliance bereitstellen.
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132324"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="78b49-103">Vorgehensweise Umschulung einer Klassifizierung in Communications Compliance (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="78b49-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="78b49-104">Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben.</span><span class="sxs-lookup"><span data-stu-id="78b49-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="78b49-105">Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="78b49-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="78b49-106">In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und einigen vorab ausgebildeten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bieten.</span><span class="sxs-lookup"><span data-stu-id="78b49-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="78b49-107">Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Learn about trainable Klassifizierers (Preview)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="78b49-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="78b49-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="78b49-108">Permissions</span></span>

<span data-ttu-id="78b49-109">So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierungen zu:</span><span class="sxs-lookup"><span data-stu-id="78b49-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="78b49-110">die Compliance-Administratorrolle oder der Compliance-Daten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="78b49-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="78b49-111">Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="78b49-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="78b49-112">Kommunikations Konformitätsrichtlinien Szenario: Administrator für Insider Risiko Management, Aufsichts Überprüfungs Administrator</span><span class="sxs-lookup"><span data-stu-id="78b49-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="78b49-113">Allgemeiner Workflow</span><span class="sxs-lookup"><span data-stu-id="78b49-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78b49-114">Sie geben Feedback in der kompatibilitätslösung an, die die Klassifizierung als Bedingung verwendet.</span><span class="sxs-lookup"><span data-stu-id="78b49-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="78b49-115">**Wenn Sie keine Communications-Konformitätsrichtlinie haben, die eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**</span><span class="sxs-lookup"><span data-stu-id="78b49-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="78b49-116">Wenn Sie Ihre Klassifizierungen verwenden, möchten Sie möglicherweise die Genauigkeit der Klassifizierungen verbessern, die Sie vornehmen.</span><span class="sxs-lookup"><span data-stu-id="78b49-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="78b49-117">Hierzu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder keine Übereinstimmung identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="78b49-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="78b49-118">Nachdem Sie 30 Auswertungen für eine Klassifizierung vorgenommen haben, wird dieses Feedback erstellt und automatisch umgeschult.</span><span class="sxs-lookup"><span data-stu-id="78b49-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="78b49-119">Weitere Informationen zum allgemeinen Workflow der Umschulung einer Klassifizierung finden Sie unter [Prozessablauf für die Umschulung einer Klassifizierung](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="78b49-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="78b49-120">Eine Klassifizierung muss bereits veröffentlicht und verwendet werden, bevor Sie neu trainiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="78b49-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="78b49-121">Vorgehensweise Umschulung einer Klassifizierung in Communication Compliance Policies (Preview)</span><span class="sxs-lookup"><span data-stu-id="78b49-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="78b49-122">Öffnen Sie die Kommunikations Konformitätsrichtlinie, die eine Klassifizierung als Bedingung verwendet, und wählen Sie eines der identifizierten Elemente aus der Liste **Ausstehend** aus.</span><span class="sxs-lookup"><span data-stu-id="78b49-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="78b49-123">Wählen Sie die Auslassungspunkte aus, und optimieren Sie die **Klassifizierung**.</span><span class="sxs-lookup"><span data-stu-id="78b49-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="78b49-124">Wählen Sie im **detailed Feedback** -Bereich, wenn das Element ein wahres positives Ergebnis ist, **übereinstimmen**aus.</span><span class="sxs-lookup"><span data-stu-id="78b49-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="78b49-125">Wenn es sich bei dem Element um ein falsch positives Ergebnis handelt, es in der Kategorie nicht korrekt enthalten war, wählen Sie **keine Übereinstimmung**aus.</span><span class="sxs-lookup"><span data-stu-id="78b49-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="78b49-126">Wenn es eine andere Klassifizierung gibt, die für das Element besser geeignet ist, können Sie es in der Liste **andere Auszubildende Klassifizierer vorschlagen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="78b49-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="78b49-127">Dadurch wird die andere Klassifizierung ausgelöst, um das Element auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="78b49-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="78b49-128">Sie können gleichzeitig Feedback zu mehreren Elementen geben, indem Sie Sie alle auswählen und dann in der Befehlsleiste **ausführliches Feedback** auswählen.</span><span class="sxs-lookup"><span data-stu-id="78b49-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="78b49-129">Wählen Sie **Feedback senden** aus, um eine Bewertung `match` der `not a match` Klassifizierungen zu senden und andere Schulungs Klassifizierer vorzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="78b49-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="78b49-130">Wenn Sie 30 Instanzen von Feedback für eine Klassifizierung bereitgestellt haben, wird Sie automatisch umgeschult.</span><span class="sxs-lookup"><span data-stu-id="78b49-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="78b49-131">Eine Umschulung kann von 1-4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="78b49-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="78b49-132">Klassifizierungen können nur zweimal pro Tag umgeschult werden.</span><span class="sxs-lookup"><span data-stu-id="78b49-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78b49-133">Diese Informationen werden in Ihrem Mandanten an die Klassifizierung weitergeleitet, und **es geht nicht zurück zu Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="78b49-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="78b49-134">Öffnen Sie die Seite **Datenklassifizierung** im **Microsoft 365 Compliance Center**.</span><span class="sxs-lookup"><span data-stu-id="78b49-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="78b49-135">Offene **Schulungs Klassifizierer (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="78b49-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="78b49-136">Die Klassifizierung, die in Ihrer Communications-Konformitätsrichtlinie verwendet wurde, wird unter der Überschrift " **Umschulung** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78b49-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Klassifizierung in Umschulungs Status](../media/classifier-retraining.png)

9. <span data-ttu-id="78b49-138">Nachdem die Umschulung abgeschlossen ist, wählen Sie die Klassifizierung aus, um die Umschulungs Übersicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="78b49-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Übersicht über Klassifizierungs-Umschulungs Ergebnisse](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="78b49-140">Überprüfen Sie die empfohlene Aktion und die Vorhersage Vergleiche der umgeschulten und derzeit veröffentlichten Versionen der Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="78b49-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="78b49-141">Wenn Sie mit den Ergebnissen der Umschulung zufrieden waren, wählen Sie **erneut veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="78b49-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="78b49-142">Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie der Klassifizierung in der Schnittstelle Communications Compliance zusätzliches Feedback geben und einen weiteren Umschulungs Zyklus starten oder nichts tun, wenn die aktuell veröffentlichte Version der Klassifizierung weiterhin verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78b49-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="78b49-143">Details zur erneuten Veröffentlichung von Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="78b49-143">Details on republishing recommendations</span></span>

<span data-ttu-id="78b49-144">Hier finden Sie einige Informationen darüber, wie wir die Empfehlung zur erneuten Veröffentlichung einer umgeschulten Klassifizierung formulieren oder eine weitere Umschulung vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="78b49-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="78b49-145">Dies erfordert ein wenig tieferes Verständnis der Funktionsweise von Schulungs fähigen Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="78b49-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="78b49-146">Nach einem umtrainieren bewerten wir die Leistung der Klassifizierung sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren der Klassifizierung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="78b49-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="78b49-147">Für integrierte Modelle sind Elemente, die zum Trainieren der Klassifizierung verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="78b49-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="78b49-148">Für benutzerdefinierte Modelle werden im ursprünglichen Training verwendete Elemente von den Websites verwendet, die Sie zum Testen und überprüfen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="78b49-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="78b49-149">Wir vergleichen die Leistungszahlen in beiden Elementgruppen für die umgeschulte und veröffentlichte Klassifizierung, um eine Empfehlung darüber zu geben, ob eine Verbesserung der erneuten Veröffentlichung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="78b49-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="78b49-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78b49-150">See also</span></span>

- [<span data-ttu-id="78b49-151">Informationen zu Schulungs Klassifizierern (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="78b49-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="78b49-152">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="78b49-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
