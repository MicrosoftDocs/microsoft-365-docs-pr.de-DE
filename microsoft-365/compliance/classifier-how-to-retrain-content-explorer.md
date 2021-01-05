---
title: Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer
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
description: Hier erfahren Sie, wie Sie Feedback für eine Lernende Klassifizierung im Inhalts-Explorer bereitstellen.
ms.openlocfilehash: 786ebb682e9cdd96c0c6503294bd4f316f777f68
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752623"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="29d07-103">Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="29d07-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="29d07-104">Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben.</span><span class="sxs-lookup"><span data-stu-id="29d07-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="29d07-105">Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="29d07-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="29d07-106">In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und einigen vorab ausgebildeten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bieten.</span><span class="sxs-lookup"><span data-stu-id="29d07-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="29d07-107">Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter erfahren Sie mehr [über Lernende Klassifizierungen](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="29d07-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="29d07-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d07-108">Permissions</span></span>

<span data-ttu-id="29d07-109">So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierungen zu:</span><span class="sxs-lookup"><span data-stu-id="29d07-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="29d07-110">die Compliance-Administratorrolle oder der Compliance-Daten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="29d07-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="29d07-111">Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="29d07-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="29d07-112">Richtlinien Szenario für Aufbewahrungs Bezeichnungen: Rollen für die Datensatzverwaltung und Aufbewahrungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="29d07-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="29d07-113">Allgemeiner Workflow</span><span class="sxs-lookup"><span data-stu-id="29d07-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29d07-114">Sie geben Feedback im Inhalts-Explorer für automatisch anzuwendende Aufbewahrungs Bezeichnungsrichtlinien auf Exchange-Elemente und verwenden die Klassifizierung als Bedingung.</span><span class="sxs-lookup"><span data-stu-id="29d07-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="29d07-115">**Wenn Sie keine Aufbewahrungsrichtlinie haben, die eine Aufbewahrungs Bezeichnung automatisch auf Exchange-Elemente anwendet und eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**</span><span class="sxs-lookup"><span data-stu-id="29d07-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="29d07-116">Wenn Sie Ihre Klassifizierungen verwenden, möchten Sie möglicherweise die Genauigkeit der Klassifizierungen verbessern, die Sie vornehmen.</span><span class="sxs-lookup"><span data-stu-id="29d07-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="29d07-117">Hierzu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder keine Übereinstimmung identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="29d07-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="29d07-118">Nachdem Sie 30 Auswertungen für eine Klassifizierung vorgenommen haben, wird dieses Feedback erstellt und automatisch umgeschult.</span><span class="sxs-lookup"><span data-stu-id="29d07-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="29d07-119">Weitere Informationen zum allgemeinen Workflow der Umschulung einer Klassifizierung finden Sie unter [Prozessablauf für die Umschulung einer Klassifizierung](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="29d07-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="29d07-120">Eine Klassifizierung muss bereits veröffentlicht und verwendet werden, bevor Sie neu trainiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="29d07-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="29d07-121">Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer</span><span class="sxs-lookup"><span data-stu-id="29d07-121">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="29d07-122">Melden Sie sich bei Microsoft 365 Compliance Center mit dem Compliance-Administrator oder der Rolle "Sicherheitsadministrator" an, und öffnen Sie **Microsoft 365 Compliance Center**  >  **Data Classification**  >  **Content Explorer**.</span><span class="sxs-lookup"><span data-stu-id="29d07-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="29d07-123">Erweitern Sie unter der Liste **Filtern nach Bezeichnungen, Informationstypen oder Kategorien** den Knoten erweiterbare **Klassifizierungen**.</span><span class="sxs-lookup"><span data-stu-id="29d07-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29d07-124">Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift "Auszubildende Klassifizierer" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="29d07-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="29d07-125">Wählen Sie die Schulungs Klassifizierung aus, die Sie in der Richtlinie für die automatische Beibehaltung von Aufbewahrungs Bezeichnungen verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="29d07-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="29d07-126">Dies ist die schulungsable Klassifizierung, der Sie Feedback geben werden.</span><span class="sxs-lookup"><span data-stu-id="29d07-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="29d07-127">Wenn ein Element in der Spalte **Aufbewahrungs Bezeichnung** einen Eintrag enthält, bedeutet dies, dass das Element als klassifiziert wurde `match` .</span><span class="sxs-lookup"><span data-stu-id="29d07-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="29d07-128">Wenn ein Element in der Spalte **Aufbewahrungs Bezeichnung** keinen Eintrag enthält, bedeutet dies, dass es als klassifiziert wurde `close match` .</span><span class="sxs-lookup"><span data-stu-id="29d07-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="29d07-129">Sie können die Klassifizierungs Genauigkeit am meisten verbessern, indem Sie Feedback zu Elementen bereitstellen `close match` .</span><span class="sxs-lookup"><span data-stu-id="29d07-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="29d07-130">Wählen Sie ein Element aus, und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="29d07-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="29d07-131">Sie können gleichzeitig Feedback zu mehreren Elementen geben, indem Sie Sie alle auswählen und dann in der Befehlsleiste die Option **Klassifizierung verbessern** auswählen.</span><span class="sxs-lookup"><span data-stu-id="29d07-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="29d07-132">Wählen Sie **Feedback bereitstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="29d07-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="29d07-133">Wählen Sie im **detailed Feedback** -Bereich, wenn das Element ein wahres positives Ergebnis ist, **übereinstimmen** aus.</span><span class="sxs-lookup"><span data-stu-id="29d07-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="29d07-134">Wenn es sich bei dem Element um ein falsch positives Ergebnis handelt, es in der Kategorie nicht korrekt enthalten war, wählen Sie **keine Übereinstimmung** aus.</span><span class="sxs-lookup"><span data-stu-id="29d07-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="29d07-135">Wenn es eine andere Klassifizierung gibt, die für das Element besser geeignet ist, können Sie es in der Liste **andere Auszubildende Klassifizierer vorschlagen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="29d07-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="29d07-136">Dadurch wird die andere Klassifizierung ausgelöst, um das Element auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="29d07-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="29d07-137">Wählen Sie **Feedback senden** aus, um eine Bewertung `match` der `not a match` Klassifizierungen zu senden und andere Schulungs Klassifizierer vorzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="29d07-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="29d07-138">Wenn Sie 30 Instanzen von Feedback für eine Klassifizierung bereitgestellt haben, wird Sie automatisch umgeschult.</span><span class="sxs-lookup"><span data-stu-id="29d07-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="29d07-139">Eine Umschulung kann eine bis vier Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="29d07-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="29d07-140">Klassifizierungen können nur zweimal pro Tag umgeschult werden.</span><span class="sxs-lookup"><span data-stu-id="29d07-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29d07-141">Diese Informationen werden in Ihrem Mandanten an die Klassifizierung weitergeleitet, und **es geht nicht zurück zu Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="29d07-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="29d07-142">Offene **Schulungs Klassifizierer**.</span><span class="sxs-lookup"><span data-stu-id="29d07-142">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="29d07-143">Die Klassifizierung, die in Ihrer Communications-Konformitätsrichtlinie verwendet wurde, wird unter der Überschrift " **Umschulung** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29d07-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Klassifizierung in Umschulungs Status](../media/classifier-retraining.png)

11. <span data-ttu-id="29d07-145">Nachdem die Umschulung abgeschlossen ist, wählen Sie die Klassifizierung aus, um die Umschulungs Übersicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="29d07-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Übersicht über Klassifizierungs-Umschulungs Ergebnisse](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="29d07-147">Überprüfen Sie die empfohlene Aktion und die Vorhersage Vergleiche der umgeschulten und derzeit veröffentlichten Versionen der Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="29d07-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="29d07-148">Wenn Sie mit den Ergebnissen der Umschulung zufrieden waren, wählen Sie **erneut veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="29d07-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="29d07-149">Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie der Klassifizierung in der Schnittstelle Communications Compliance zusätzliches Feedback geben und einen weiteren Umschulungs Zyklus starten oder nichts tun, wenn die aktuell veröffentlichte Version der Klassifizierung weiterhin verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29d07-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="29d07-150">Details zur erneuten Veröffentlichung von Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="29d07-150">Details on republishing recommendations</span></span>

<span data-ttu-id="29d07-151">Hier finden Sie einige Informationen darüber, wie wir die Empfehlung zur erneuten Veröffentlichung einer umgeschulten Klassifizierung formulieren oder eine weitere Umschulung vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="29d07-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="29d07-152">Dies erfordert ein wenig tieferes Verständnis der Funktionsweise von Schulungs fähigen Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="29d07-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="29d07-153">Nach einem umtrainieren bewerten wir die Leistung der Klassifizierung sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren der Klassifizierung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="29d07-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="29d07-154">Für integrierte Modelle sind Elemente, die zum Trainieren der Klassifizierung verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29d07-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="29d07-155">Für benutzerdefinierte Modelle werden im ursprünglichen Training verwendete Elemente von den Websites verwendet, die Sie zum Testen und überprüfen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="29d07-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="29d07-156">Wir vergleichen die Leistungszahlen in beiden Elementgruppen für die umgeschulte und veröffentlichte Klassifizierung, um eine Empfehlung darüber zu geben, ob eine Verbesserung der erneuten Veröffentlichung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="29d07-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="29d07-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29d07-157">See also</span></span>

- [<span data-ttu-id="29d07-158">Informationen zu Schulungs Klassifizierern</span><span class="sxs-lookup"><span data-stu-id="29d07-158">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="29d07-159">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="29d07-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
