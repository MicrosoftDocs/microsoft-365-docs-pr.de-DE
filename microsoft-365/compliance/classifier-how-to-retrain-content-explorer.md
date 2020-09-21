---
title: Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer (Vorschau)
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
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132327"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="f135d-103">Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f135d-103">How to retrain a classifier in content explorer (preview)</span></span>

<span data-ttu-id="f135d-104">Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben.</span><span class="sxs-lookup"><span data-stu-id="f135d-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="f135d-105">Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f135d-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="f135d-106">In diesem Artikel erfahren Sie, wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und einigen vorab ausgebildeten Klassifizierungen verbessern können, indem Sie ihnen zusätzliches Feedback bieten.</span><span class="sxs-lookup"><span data-stu-id="f135d-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="f135d-107">Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Learn about trainable Klassifizierers (Preview)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="f135d-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="f135d-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f135d-108">Permissions</span></span>

<span data-ttu-id="f135d-109">So greifen Sie im Microsoft 365 Compliance Center auf Klassifizierungen zu:</span><span class="sxs-lookup"><span data-stu-id="f135d-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="f135d-110">die Compliance-Administratorrolle oder der Compliance-Daten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="f135d-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="f135d-111">Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="f135d-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="f135d-112">Richtlinien Szenario für Aufbewahrungs Bezeichnungen: Rollen für die Datensatzverwaltung und Aufbewahrungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f135d-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="f135d-113">Allgemeiner Workflow</span><span class="sxs-lookup"><span data-stu-id="f135d-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f135d-114">Sie geben Feedback im Inhalts-Explorer für automatisch anzuwendende Aufbewahrungs Bezeichnungsrichtlinien auf Exchange-Elemente und verwenden die Klassifizierung als Bedingung.</span><span class="sxs-lookup"><span data-stu-id="f135d-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="f135d-115">**Wenn Sie keine Aufbewahrungsrichtlinie haben, die eine Aufbewahrungs Bezeichnung automatisch auf Exchange-Elemente anwendet und eine Klassifizierung als Bedingung verwendet, beenden Sie hier.**</span><span class="sxs-lookup"><span data-stu-id="f135d-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="f135d-116">Wenn Sie Ihre Klassifizierungen verwenden, möchten Sie möglicherweise die Genauigkeit der Klassifizierungen verbessern, die Sie vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f135d-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="f135d-117">Hierzu bewerten Sie die Qualität der Klassifizierungen, die für Elemente vorgenommen wurden, die als Übereinstimmung oder keine Übereinstimmung identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="f135d-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="f135d-118">Nachdem Sie 30 Auswertungen für eine Klassifizierung vorgenommen haben, wird dieses Feedback erstellt und automatisch umgeschult.</span><span class="sxs-lookup"><span data-stu-id="f135d-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="f135d-119">Weitere Informationen zum allgemeinen Workflow der Umschulung einer Klassifizierung finden Sie unter [Prozessablauf für die Umschulung einer Klassifizierung](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="f135d-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="f135d-120">Eine Klassifizierung muss bereits veröffentlicht und verwendet werden, bevor Sie neu trainiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f135d-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="f135d-121">Vorgehensweise Umschulung einer Klassifizierung im Inhalts-Explorer (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f135d-121">How to retrain a classifier in content explorer (preview)</span></span>

1. <span data-ttu-id="f135d-122">Melden Sie sich bei Microsoft 365 Compliance Center mit dem Compliance-Administrator oder der Rolle "Sicherheitsadministrator" an, und öffnen Sie **Microsoft 365 Compliance Center**  >  **Data Classification**  >  **Content Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f135d-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="f135d-123">Erweitern Sie unter der Liste **Filtern nach Bezeichnungen, Informationstypen oder Kategorien** den Knoten erweiterbare **Klassifizierungen**.</span><span class="sxs-lookup"><span data-stu-id="f135d-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f135d-124">Es kann bis zu acht Tage dauern, bis aggregierte Elemente unter der Überschrift "Auszubildende Klassifizierer" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f135d-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="f135d-125">Wählen Sie die Schulungs Klassifizierung aus, die Sie in der Richtlinie für die automatische Beibehaltung von Aufbewahrungs Bezeichnungen verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="f135d-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="f135d-126">Dies ist die schulungsable Klassifizierung, der Sie Feedback geben werden.</span><span class="sxs-lookup"><span data-stu-id="f135d-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="f135d-127">Wenn ein Element in der Spalte **Aufbewahrungs Bezeichnung** einen Eintrag enthält, bedeutet dies, dass das Element als klassifiziert wurde `match` .</span><span class="sxs-lookup"><span data-stu-id="f135d-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="f135d-128">Wenn ein Element in der Spalte **Aufbewahrungs Bezeichnung** keinen Eintrag enthält, bedeutet dies, dass es als klassifiziert wurde `close match` .</span><span class="sxs-lookup"><span data-stu-id="f135d-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="f135d-129">Sie können die Klassifizierungs Genauigkeit am meisten verbessern, indem Sie Feedback zu Elementen bereitstellen `close match` .</span><span class="sxs-lookup"><span data-stu-id="f135d-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="f135d-130">Wählen Sie ein Element aus, und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="f135d-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="f135d-131">Sie können gleichzeitig Feedback zu mehreren Elementen geben, indem Sie Sie alle auswählen und dann in der Befehlsleiste die Option **Klassifizierung verbessern** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f135d-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="f135d-132">Wählen Sie **Feedback bereitstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="f135d-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="f135d-133">Wählen Sie im **detailed Feedback** -Bereich, wenn das Element ein wahres positives Ergebnis ist, **übereinstimmen**aus.</span><span class="sxs-lookup"><span data-stu-id="f135d-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="f135d-134">Wenn es sich bei dem Element um ein falsch positives Ergebnis handelt, es in der Kategorie nicht korrekt enthalten war, wählen Sie **keine Übereinstimmung**aus.</span><span class="sxs-lookup"><span data-stu-id="f135d-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="f135d-135">Wenn es eine andere Klassifizierung gibt, die für das Element besser geeignet ist, können Sie es in der Liste **andere Auszubildende Klassifizierer vorschlagen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f135d-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="f135d-136">Dadurch wird die andere Klassifizierung ausgelöst, um das Element auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="f135d-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="f135d-137">Wählen Sie **Feedback senden** aus, um eine Bewertung `match` der `not a match` Klassifizierungen zu senden und andere Schulungs Klassifizierer vorzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="f135d-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="f135d-138">Wenn Sie 30 Instanzen von Feedback für eine Klassifizierung bereitgestellt haben, wird Sie automatisch umgeschult.</span><span class="sxs-lookup"><span data-stu-id="f135d-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="f135d-139">Eine Umschulung kann eine bis vier Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="f135d-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="f135d-140">Klassifizierungen können nur zweimal pro Tag umgeschult werden.</span><span class="sxs-lookup"><span data-stu-id="f135d-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f135d-141">Diese Informationen werden in Ihrem Mandanten an die Klassifizierung weitergeleitet, und **es geht nicht zurück zu Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f135d-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="f135d-142">Offene **Schulungs Klassifizierer (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="f135d-142">Open **Trainable classifiers (preview)**.</span></span>
10. <span data-ttu-id="f135d-143">Die Klassifizierung, die in Ihrer Communications-Konformitätsrichtlinie verwendet wurde, wird unter der Überschrift " **Umschulung** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f135d-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Klassifizierung in Umschulungs Status](../media/classifier-retraining.png)

11. <span data-ttu-id="f135d-145">Nachdem die Umschulung abgeschlossen ist, wählen Sie die Klassifizierung aus, um die Umschulungs Übersicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f135d-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Übersicht über Klassifizierungs-Umschulungs Ergebnisse](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="f135d-147">Überprüfen Sie die empfohlene Aktion und die Vorhersage Vergleiche der umgeschulten und derzeit veröffentlichten Versionen der Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="f135d-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="f135d-148">Wenn Sie mit den Ergebnissen der Umschulung zufrieden waren, wählen Sie **erneut veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="f135d-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="f135d-149">Wenn Sie mit den Ergebnissen der Umschulung nicht zufrieden sind, können Sie der Klassifizierung in der Schnittstelle Communications Compliance zusätzliches Feedback geben und einen weiteren Umschulungs Zyklus starten oder nichts tun, wenn die aktuell veröffentlichte Version der Klassifizierung weiterhin verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f135d-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="f135d-150">Details zur erneuten Veröffentlichung von Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f135d-150">Details on republishing recommendations</span></span>

<span data-ttu-id="f135d-151">Hier finden Sie einige Informationen darüber, wie wir die Empfehlung zur erneuten Veröffentlichung einer umgeschulten Klassifizierung formulieren oder eine weitere Umschulung vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="f135d-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="f135d-152">Dies erfordert ein wenig tieferes Verständnis der Funktionsweise von Schulungs fähigen Klassifizierungen.</span><span class="sxs-lookup"><span data-stu-id="f135d-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="f135d-153">Nach einem umtrainieren bewerten wir die Leistung der Klassifizierung sowohl für die Elemente mit Feedback als auch für alle Elemente, die ursprünglich zum Trainieren der Klassifizierung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f135d-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="f135d-154">Für integrierte Modelle sind Elemente, die zum Trainieren der Klassifizierung verwendet werden, die Elemente, die von Microsoft zum Erstellen des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f135d-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="f135d-155">Für benutzerdefinierte Modelle werden im ursprünglichen Training verwendete Elemente von den Websites verwendet, die Sie zum Testen und überprüfen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="f135d-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="f135d-156">Wir vergleichen die Leistungszahlen in beiden Elementgruppen für die umgeschulte und veröffentlichte Klassifizierung, um eine Empfehlung darüber zu geben, ob eine Verbesserung der erneuten Veröffentlichung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="f135d-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f135d-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f135d-157">See also</span></span>

- [<span data-ttu-id="f135d-158">Informationen zu Schulungs Klassifizierern (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f135d-158">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="f135d-159">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="f135d-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
