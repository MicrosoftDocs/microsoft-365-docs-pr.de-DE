---
title: Erstellen einer Schulungs klassifizierten Klassifizierung (Vorschau)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Verwenden Sie Schulungs fähige Klassifizierungen, wenn eine der Feld Klassifizierungen von Ready to use Ihren Anforderungen nicht entspricht. Eine Microsoft 365-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie sich Beispiele ansehen. In diesem Thema wird gezeigt, wie Sie eine benutzerdefinierte Klassifizierung erstellen.
ms.openlocfilehash: cb3cda9777d692a56263e92cd908eb09bfa99895
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813373"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="d3266-105">Erstellen einer Schulungs Klassifizierer (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d3266-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="d3266-106">Verwenden Sie schulungsable Klassifizierungen, wenn eine der Out-of-the-Box-Klassifizierungen Ihren Anforderungen nicht gerecht wird.</span><span class="sxs-lookup"><span data-stu-id="d3266-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="d3266-107">Eine Microsoft 365-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie sich Beispiele ansehen.</span><span class="sxs-lookup"><span data-stu-id="d3266-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="d3266-108">Training die Klassifizierung umfasst zunächst Stichproben, die von Menschen ausgewählt werden und der Kategorie positiv entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d3266-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="d3266-109">Anschließend testen Sie die Vorhersagen, nachdem Sie diese verarbeitet haben, indem Sie eine Mischung aus positiven und negativen Beispielen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d3266-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="d3266-110">Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Erste Schritte mit Lern baren Klassifizierungen (Vorschau)](classifier-getting-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="d3266-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="d3266-111">Diese Zeitachse spiegelt eine Beispielbereitstellung wider.</span><span class="sxs-lookup"><span data-stu-id="d3266-111">This timeline reflects a sample deployment.</span></span>

![Schulungs-und Klassifizierungs Zeitplan](media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="d3266-113">Das Anmelden ist zum ersten Mal für Schulungs orientierte Klassifizierungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3266-113">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="d3266-114">Es dauert zwölf Tage, bis Microsoft 365 eine Basisbewertung ihrer organisationsinhalte abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="d3266-114">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span>

## <a name="seed-content"></a><span data-ttu-id="d3266-115">Seed-Inhalt</span><span class="sxs-lookup"><span data-stu-id="d3266-115">Seed content</span></span>

<span data-ttu-id="d3266-116">Wenn Sie möchten, dass eine Lernende Klassifizierung ein Element in einer bestimmten Inhaltskategorie unabhängig und genau identifiziert, müssen Sie es zunächst mit vielen Beispielen des Inhaltstyps in der Kategorie präsentieren.</span><span class="sxs-lookup"><span data-stu-id="d3266-116">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="d3266-117">Diese Fütterung von Proben zur Klassifizierer-Schulung wird als *Seeding*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d3266-117">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="d3266-118">Seed-Inhalt wird von einem Menschen ausgewählt und wird bewertet, um die Kategorie des Inhalts darzustellen.</span><span class="sxs-lookup"><span data-stu-id="d3266-118">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="d3266-119">Sie benötigen mindestens 50 positive Beispiele und bis zu 500.</span><span class="sxs-lookup"><span data-stu-id="d3266-119">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="d3266-120">Die eingestufte Klassifizierung wird bis zu den 500 zuletzt erstellten Beispielen verarbeitet (nach Dateierstellungsdatum/Zeitstempel).</span><span class="sxs-lookup"><span data-stu-id="d3266-120">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="d3266-121">Je mehr Beispiele Sie bereitstellen, desto genauer sind die Vorhersagen, die von der Klassifizierung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="d3266-121">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="d3266-122">Testen von Inhalten</span><span class="sxs-lookup"><span data-stu-id="d3266-122">Testing content</span></span>

<span data-ttu-id="d3266-123">Nachdem die Schulungs fähigen Klassifizierung genügend positive Beispiele zum Erstellen eines Vorhersagemodells verarbeitet hat, müssen Sie die vorher gestellten Voraussagen testen, um zu ermitteln, ob die Klassifizierung ordnungsgemäß zwischen Elementen unterscheiden kann, die der Kategorie und den Elementen entsprechen, die nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d3266-123">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="d3266-124">Sie tun dies, indem Sie es eine andere, hoffentlich größere, Reihe von Menschen gepflückten Inhalte, die aus Beispielen, die in der Kategorie und Beispiele, die nicht fallen sollte.</span><span class="sxs-lookup"><span data-stu-id="d3266-124">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="d3266-125">Nachdem Sie diese verarbeitet haben, gehen Sie die Ergebnisse manuell durch und überprüfen, ob jede Vorhersage korrekt, falsch oder nicht sicher ist.</span><span class="sxs-lookup"><span data-stu-id="d3266-125">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="d3266-126">Die Schulungs-Klassifizierung verwendet dieses Feedback, um das Vorhersagemodell zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d3266-126">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="d3266-127">Optimale Ergebnisse erzielen Sie, wenn Sie 10.000 Elemente in Ihrem Test Beispiel mit einer gleichmäßigen Verteilung positiver und negativer Übereinstimmungen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="d3266-127">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="d3266-128">Vorgehensweise Erstellen einer Schulungs Klassifizierer</span><span class="sxs-lookup"><span data-stu-id="d3266-128">How to create a trainable classifier</span></span>

1. <span data-ttu-id="d3266-129">Sammeln zwischen 50-500-Seed-Inhaltselementen.</span><span class="sxs-lookup"><span data-stu-id="d3266-129">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="d3266-130">Hierbei muss es sich nur um Beispiele handeln, die den Typ des Inhalts, den die Lernenden Klassifizierung positiv als in der Kategorie Klassifizierung identifiziert werden soll, stark darstellen.</span><span class="sxs-lookup"><span data-stu-id="d3266-130">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="d3266-131">Weitere Informationen finden Sie unter [standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) für die unterstützten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="d3266-131">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3266-132">Die Ausgangs-und Test Beispielelemente dürfen nicht verschlüsselt sein und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="d3266-132">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3266-133">Stellen Sie sicher, dass die Elemente im seedsatz **starke** Beispiele für die Kategorie sind.</span><span class="sxs-lookup"><span data-stu-id="d3266-133">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="d3266-134">Die eingestufte Klassifizierung erstellt zunächst Ihr Modell basierend auf dem, was Sie mit dem Seeding beginnen.</span><span class="sxs-lookup"><span data-stu-id="d3266-134">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="d3266-135">Bei der Klassifizierung wird davon ausgegangen, dass alle Seed-Beispiele starke positive Ergebnisse aufweisen und keine Möglichkeit haben zu wissen, ob ein Beispiel einer schwachen oder negativen Übereinstimmung mit der Kategorie entspricht.</span><span class="sxs-lookup"><span data-stu-id="d3266-135">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="d3266-136">Platzieren Sie den Ausgangs Inhalt in einem SharePoint Online Ordner, *der ausschließlich für den Inhalt des Seeds*reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3266-136">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="d3266-137">Notieren Sie sich die Website-, Bibliotheks-und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="d3266-137">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="d3266-138">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Seed-Daten erstellen, lassen Sie mindestens eine Stunde für diesen Standort indiziert werden, bevor Sie die Schulungs Klassifizierung erstellen, die diese Startdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3266-138">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="d3266-139">Melden Sie sich bei Microsoft 365 Compliance Center mit dem Compliance-Administrator oder der Rolle "Sicherheitsadministrator" an, und öffnen Sie **Microsoft 365 Compliance Center** oder **Microsoft 365 Security Center** > -**Datenklassifizierung** .</span><span class="sxs-lookup"><span data-stu-id="d3266-139">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="d3266-140">Klicken Sie auf die Registerkarte **Schulungs Klassifizierung** .</span><span class="sxs-lookup"><span data-stu-id="d3266-140">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="d3266-141">Wählen Sie **Create trainable Klassifizierer**aus.</span><span class="sxs-lookup"><span data-stu-id="d3266-141">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="d3266-142">Geben Sie die entsprechenden Werte für `Name`die `Description` Felder der Kategorie der Elemente ein, die diese lernbaren Klassifizierung identifizieren sollen.</span><span class="sxs-lookup"><span data-stu-id="d3266-142">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="d3266-143">Geben Sie in Schritt 2 die exakte SharePoint Online Website, Bibliothek und Ordner-URL für die Seed-Inhaltswebsite ein.</span><span class="sxs-lookup"><span data-stu-id="d3266-143">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="d3266-144">Wählen `Add`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="d3266-144">Choose `Add`.</span></span>

8. <span data-ttu-id="d3266-145">Überprüfen Sie die Einstellungen `Create trainable classifier`, und wählen Sie.</span><span class="sxs-lookup"><span data-stu-id="d3266-145">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="d3266-146">Innerhalb von 24 Stunden verarbeitet die Schulungs-und Klassifizierungs Stelle die seeddaten und erstellt ein Vorhersagemodell.</span><span class="sxs-lookup"><span data-stu-id="d3266-146">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="d3266-147">Der Klassifizierungsstatus ist `In progress` , während er die seeddaten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d3266-147">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="d3266-148">Wenn die Klassifizierung die Verarbeitung der seeddaten abgeschlossen hat, wird der Status in `Need test items`geändert.</span><span class="sxs-lookup"><span data-stu-id="d3266-148">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="d3266-149">Sie können die Seite Details jetzt anzeigen, indem Sie die Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="d3266-149">You can now view the details page by choosing the classifier.</span></span>


![Schulungs fähige Klassifizierung zum Testen verfügbar](media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="d3266-151">Sammeln Sie mindestens 200 Testinhalts Elemente.</span><span class="sxs-lookup"><span data-stu-id="d3266-151">Collect at least 200 test content items.</span></span> <span data-ttu-id="d3266-152">Microsoft empfiehlt 10.000, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="d3266-152">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="d3266-153">Dabei muss es sich um eine Mischung von Elementen handeln, die starke positive Ergebnisse aufweisen, starke negative und einige, die in ihrer Natur etwas weniger offensichtlich sind.</span><span class="sxs-lookup"><span data-stu-id="d3266-153">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="d3266-154">Weitere Informationen finden Sie unter [standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) für die unterstützten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="d3266-154">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3266-155">Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="d3266-155">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="d3266-156">Platzieren Sie den Testinhalt in einem SharePoint Online Ordner, *der ausschließlich für den Testinhalt*reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3266-156">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="d3266-157">Notieren Sie sich die SharePoint Online Website, Bibliothek und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="d3266-157">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="d3266-158">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Testdaten erstellen, lassen Sie mindestens eine Stunde für diesen Ort indiziert werden, bevor Sie die Schulungs Klassifizierung erstellen, die diese Startdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3266-158">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="d3266-159">Wählen `Add items to test`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="d3266-159">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="d3266-160">Geben Sie in Schritt 12 die exakte SharePoint Online Website, Bibliothek und Ordner-URL für die Testinhalts Website ein.</span><span class="sxs-lookup"><span data-stu-id="d3266-160">Enter the exact SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="d3266-161">Wählen `Add`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="d3266-161">Choose `Add`.</span></span>

15. <span data-ttu-id="d3266-162">Beenden Sie den Assistenten, `Done`indem Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="d3266-162">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="d3266-163">Ihre Schulungs-Klassifizierung dauert bis zu einer Stunde, um die Testdateien zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3266-163">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="d3266-164">Wenn die ausbildende Klassifizierung die Verarbeitung Ihrer Testdateien abgeschlossen hat, wird der Status auf der Seite Details in `Ready to review`geändert.</span><span class="sxs-lookup"><span data-stu-id="d3266-164">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="d3266-165">Wenn Sie die Größe des testsamples vergrößern möchten, `Add items to test` wählen Sie aus, und lassen Sie die Schulungs-Klassifizierung die zusätzlichen Elemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3266-165">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![zur Überprüfung des Screenshot verfügbar](media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="d3266-167">Klicken `Tested items to review` Sie auf die Registerkarte, um Elemente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d3266-167">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="d3266-168">Microsoft 365 wird 30 Elemente gleichzeitig darstellen.</span><span class="sxs-lookup"><span data-stu-id="d3266-168">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="d3266-169">Überprüfen Sie diese, `We predict this item is "Relevant". Do you agree?` und wählen Sie `Yes` im `No` Feld `Not sure, skip to next item`entweder oder oder aus.</span><span class="sxs-lookup"><span data-stu-id="d3266-169">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="d3266-170">Die Modellgenauigkeit wird nach jeweils 30 Elementen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d3266-170">Model accuracy is automatically updated after every 30 items.</span></span>

![Feld "Elemente überprüfen"](media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="d3266-172">Über *prüfen Sie mindestens 200* Elemente.</span><span class="sxs-lookup"><span data-stu-id="d3266-172">Review *at least* 200 items.</span></span>

<!-- insert Analyze steps here-->

20. <span data-ttu-id="d3266-173">Überprüfen Sie weiter, bis die Genauigkeit mindestens 70% erreicht und `Publish the classifier` der Status `Ready to use`lautet.</span><span class="sxs-lookup"><span data-stu-id="d3266-173">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![Genauigkeit und Veröffentlichungs bereit](media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="d3266-175">Veröffentlichen Sie die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="d3266-175">Publish the classifier.</span></span>

22. <span data-ttu-id="d3266-176">Nach der Veröffentlichung ist Ihre Klassifizierung als Bedingung in der [Richtlinie für die automatische Beibehaltung von Aufbewahrungs Bezeichnungen verfügbar, die auf einer Bedingung](labels.md#applying-a-retention-label-automatically-based-on-conditions) und in der [Kommunikations Konformität](communication-compliance.md)basiert.</span><span class="sxs-lookup"><span data-stu-id="d3266-176">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="d3266-177">Sobald eine Klassifizierung veröffentlicht wurde, kann Sie keine zusätzliche Schulung durchlaufen, daher sollten Sie sicherstellen, dass Sie so viele Elemente wie möglich getestet und überprüft haben, um sicherzustellen, dass die Genauigkeit so hoch wie möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d3266-177">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3266-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3266-178">See also</span></span>

- [<span data-ttu-id="d3266-179">Erste Schritte mit lernbaren Klassifizierungen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d3266-179">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="d3266-180">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="d3266-180">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
