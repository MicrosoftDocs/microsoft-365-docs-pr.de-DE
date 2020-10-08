---
title: Erste Schritte mit trainierbaren Klassifizierern (Vorschau)
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Eine Microsoft 365-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie sich Beispiele ansehen. In diesem Artikel erfahren Sie, wie Sie eine benutzerdefinierte Klassifizierung erstellen und trainieren und Sie neu trainieren, um die Genauigkeit zu verbessern.
ms.openlocfilehash: 30f3c45945b4879be17eadfe04e8ccb8526df16a
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379257"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="1d026-104">Erste Schritte mit trainierbaren Klassifizierern (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1d026-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="1d026-105">Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben.</span><span class="sxs-lookup"><span data-stu-id="1d026-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="1d026-106">Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1d026-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="1d026-107">Das Erstellen einer benutzerdefinierten Klassifizierer-Klassifizierung umfasst zunächst das Erteilen von Stichproben, die von Menschen ausgewählt werden und der Kategorie positiv entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1d026-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="1d026-108">Nachdem Sie diese verarbeitet haben, testen Sie dann die Fähigkeit der Klassifizierungen, vorherzusagen, indem Sie eine Mischung aus positiven und negativen Beispielen geben.</span><span class="sxs-lookup"><span data-stu-id="1d026-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="1d026-109">In diesem Artikel erfahren Sie, wie Sie eine benutzerdefinierte Klassifizierung erstellen und trainieren und wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und vorab ausgebildeten Klassifizierungen über ihre Lebensdauer durch Umschulung verbessern können.</span><span class="sxs-lookup"><span data-stu-id="1d026-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="1d026-110">Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Learn about trainable Klassifizierers (Preview)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="1d026-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d026-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1d026-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="1d026-112">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="1d026-112">Licensing requirements</span></span>

<span data-ttu-id="1d026-113">Klassifizierungen sind ein Microsoft 365 E5-oder E5-Konformitäts Feature.</span><span class="sxs-lookup"><span data-stu-id="1d026-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="1d026-114">Sie müssen über eines dieser Abonnements verfügen, damit Sie Sie nutzen können.</span><span class="sxs-lookup"><span data-stu-id="1d026-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="1d026-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1d026-115">Permissions</span></span>

<span data-ttu-id="1d026-116">So greifen Sie auf die Klassifizierung in der Benutzeroberfläche zu:</span><span class="sxs-lookup"><span data-stu-id="1d026-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="1d026-117">der globale Administrator muss sich für den Mandanten anmelden, um benutzerdefinierte Klassifizierungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d026-117">the Global admin needs to opt in for the tenant to create custom classifiers</span></span>
- <span data-ttu-id="1d026-118">die Compliance-Administratorrolle oder der Compliance-Daten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="1d026-118">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="1d026-119">Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="1d026-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="1d026-120">Richtlinien Szenario für Aufbewahrungs Bezeichnungen: Rollen für die Datensatzverwaltung und Aufbewahrungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="1d026-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="1d026-121">Richtlinien Szenario für die Sensitivitäts Bezeichnung: Sicherheitsadministrator, Kompatibilitäts Administrator, Kompatibilitätsdaten Administrator</span><span class="sxs-lookup"><span data-stu-id="1d026-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="1d026-122">Kommunikations Konformitätsrichtlinien Szenario: Administrator für Insider Risiko Management, Aufsichts Überprüfungs Administrator</span><span class="sxs-lookup"><span data-stu-id="1d026-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1d026-123">Standardmäßig kann nur der Benutzer, der eine benutzerdefinierte Klassifizierung erstellt, die von dieser Klassifizierung vorgenommenen Vorhersagen trainieren und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1d026-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="1d026-124">Wenn andere Benutzer in der Lage sein sollen, Klassifizierungs Vorhersagen auszubilden und zu überprüfen, finden Sie weitere Informationen unter [Erteilen von Schulungs-und Überprüfungs rechten](#give-others-train-and-review-rights).</span><span class="sxs-lookup"><span data-stu-id="1d026-124">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](#give-others-train-and-review-rights).</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="1d026-125">Vorbereiten auf eine benutzerdefinierte Schulungs Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="1d026-125">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="1d026-126">Es ist hilfreich zu verstehen, was am Erstellen einer benutzerdefinierten Klassifizierer-Klassifizierung beteiligt ist, bevor Sie eintauchen.</span><span class="sxs-lookup"><span data-stu-id="1d026-126">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="1d026-127">Zeitachse</span><span class="sxs-lookup"><span data-stu-id="1d026-127">Timeline</span></span>

<span data-ttu-id="1d026-128">Diese Zeitachse reflektiert eine Beispielbereitstellung von Schulungs Klassifizierern.</span><span class="sxs-lookup"><span data-stu-id="1d026-128">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![Schulungs-und Klassifizierungs Zeitplan](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="1d026-130">Das Anmelden ist zum ersten Mal für Schulungs orientierte Klassifizierungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1d026-130">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="1d026-131">Es dauert zwölf Tage, bis Microsoft 365 eine Basisbewertung ihrer organisationsinhalte abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="1d026-131">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="1d026-132">Wenden Sie sich an ihren globalen Administrator, um den Opt-in-Prozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="1d026-132">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="1d026-133">Allgemeiner Workflow</span><span class="sxs-lookup"><span data-stu-id="1d026-133">Overall workflow</span></span>

<span data-ttu-id="1d026-134">Weitere Informationen zum Gesamtworkflow beim Erstellen von benutzerdefinierten Schulungs Klassifizierern finden Sie unter [Prozessablauf zum Erstellen von Kunden Schulungs Klassifizierern](classifier-learn-about.md#process-flow-for-creating-custom-classifiers) .</span><span class="sxs-lookup"><span data-stu-id="1d026-134">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span></span>

### <a name="seed-content"></a><span data-ttu-id="1d026-135">Seed-Inhalt</span><span class="sxs-lookup"><span data-stu-id="1d026-135">Seed content</span></span>

<span data-ttu-id="1d026-136">Wenn Sie möchten, dass eine Lernende Klassifizierung ein Element in einer bestimmten Inhaltskategorie unabhängig und genau identifiziert, müssen Sie es zunächst mit vielen Beispielen des Inhaltstyps in der Kategorie präsentieren.</span><span class="sxs-lookup"><span data-stu-id="1d026-136">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="1d026-137">Diese Fütterung von Proben zur Klassifizierer-Schulung wird als *Seeding*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1d026-137">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="1d026-138">Seed-Inhalt wird von einem Menschen ausgewählt und wird bewertet, um die Kategorie des Inhalts darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1d026-138">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="1d026-139">Sie benötigen mindestens 50 positive Beispiele und bis zu 500.</span><span class="sxs-lookup"><span data-stu-id="1d026-139">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="1d026-140">Die eingestufte Klassifizierung wird bis zu den 500 zuletzt erstellten Beispielen verarbeitet (nach Dateierstellungsdatum/Zeitstempel).</span><span class="sxs-lookup"><span data-stu-id="1d026-140">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="1d026-141">Je mehr Beispiele Sie bereitstellen, desto genauer sind die Vorhersagen, die von der Klassifizierung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="1d026-141">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="1d026-142">Testen von Inhalten</span><span class="sxs-lookup"><span data-stu-id="1d026-142">Testing content</span></span>

<span data-ttu-id="1d026-143">Nachdem die Schulungs fähigen Klassifizierung genügend positive Beispiele zum Erstellen eines Vorhersagemodells verarbeitet hat, müssen Sie die vorher gestellten Voraussagen testen, um zu ermitteln, ob die Klassifizierung ordnungsgemäß zwischen Elementen unterscheiden kann, die der Kategorie und den Elementen entsprechen, die nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1d026-143">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="1d026-144">Sie tun dies, indem Sie es eine andere, hoffentlich größere, Reihe von Menschen gepflückten Inhalte, die aus Beispielen, die in der Kategorie und Beispiele, die nicht fallen sollte.</span><span class="sxs-lookup"><span data-stu-id="1d026-144">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="1d026-145">Nachdem Sie diese verarbeitet haben, gehen Sie die Ergebnisse manuell durch und überprüfen, ob jede Vorhersage korrekt, falsch oder nicht sicher ist.</span><span class="sxs-lookup"><span data-stu-id="1d026-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="1d026-146">Die Schulungs-Klassifizierung verwendet dieses Feedback, um das Vorhersagemodell zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="1d026-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="1d026-147">Die besten Ergebnisse erzielen Sie, wenn Ihr Test Beispiel mindestens 200 Elemente mit einer gleichmäßigen Verteilung positiver und negativer Übereinstimmungen auflistet.</span><span class="sxs-lookup"><span data-stu-id="1d026-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="1d026-148">Vorgehensweise Erstellen einer Schulungs Klassifizierer</span><span class="sxs-lookup"><span data-stu-id="1d026-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="1d026-149">Sammeln zwischen 50-500-Seed-Inhaltselementen.</span><span class="sxs-lookup"><span data-stu-id="1d026-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="1d026-150">Hierbei muss es sich nur um Beispiele handeln, die den Typ des Inhalts, den die Lernenden Klassifizierung positiv als in der Kategorie Klassifizierung identifiziert werden soll, stark darstellen.</span><span class="sxs-lookup"><span data-stu-id="1d026-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="1d026-151">Weitere Informationen finden Sie unter [standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) für die unterstützten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="1d026-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d026-152">Die Ausgangs-und Test Beispielelemente dürfen nicht verschlüsselt sein und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="1d026-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d026-153">Stellen Sie sicher, dass die Elemente im seedsatz **starke** Beispiele für die Kategorie sind.</span><span class="sxs-lookup"><span data-stu-id="1d026-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="1d026-154">Die eingestufte Klassifizierung erstellt zunächst Ihr Modell basierend auf dem, was Sie mit dem Seeding beginnen.</span><span class="sxs-lookup"><span data-stu-id="1d026-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="1d026-155">Bei der Klassifizierung wird davon ausgegangen, dass alle Seed-Beispiele starke positive Ergebnisse aufweisen und keine Möglichkeit haben zu wissen, ob ein Beispiel einer schwachen oder negativen Übereinstimmung mit der Kategorie entspricht.</span><span class="sxs-lookup"><span data-stu-id="1d026-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="1d026-156">Platzieren Sie den Ausgangs Inhalt in einem SharePoint Online Ordner, *der ausschließlich für den Inhalt des Seeds*reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="1d026-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="1d026-157">Notieren Sie sich die Website-, Bibliotheks-und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="1d026-157">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="1d026-158">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Seed-Daten erstellen, lassen Sie mindestens eine Stunde für diesen Standort indiziert werden, bevor Sie die Schulungs Klassifizierung erstellen, die diese Startdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d026-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="1d026-159">Melden Sie sich bei Microsoft 365 Compliance Center mit dem Compliance-Administrator oder der Rolle "Sicherheitsadministrator" an, und öffnen Sie **Microsoft 365 Compliance Center** oder **Microsoft 365 Security Center**-  >  **Datenklassifizierung** .</span><span class="sxs-lookup"><span data-stu-id="1d026-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="1d026-160">Klicken Sie auf die Registerkarte **Schulungs Klassifizierung** .</span><span class="sxs-lookup"><span data-stu-id="1d026-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="1d026-161">Wählen Sie **Create trainable Klassifizierer**aus.</span><span class="sxs-lookup"><span data-stu-id="1d026-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="1d026-162">Geben Sie die entsprechenden Werte für die `Name` Felder der Kategorie der Elemente ein, die diese lernbaren `Description` Klassifizierung identifizieren sollen.</span><span class="sxs-lookup"><span data-stu-id="1d026-162">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="1d026-163">Wählen Sie in Schritt 2 die SharePoint Online Website, Bibliothek und Ordner-URL für die Seed-Inhaltswebsite aus.</span><span class="sxs-lookup"><span data-stu-id="1d026-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="1d026-164">Wählen Sie aus `Add` .</span><span class="sxs-lookup"><span data-stu-id="1d026-164">Choose `Add`.</span></span>

8. <span data-ttu-id="1d026-165">Überprüfen Sie die Einstellungen, und wählen Sie `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="1d026-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="1d026-166">Innerhalb von 24 Stunden verarbeitet die Schulungs-und Klassifizierungs Stelle die seeddaten und erstellt ein Vorhersagemodell.</span><span class="sxs-lookup"><span data-stu-id="1d026-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="1d026-167">Der Klassifizierungsstatus ist `In progress` , während er die seeddaten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1d026-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="1d026-168">Wenn die Klassifizierung die Verarbeitung der seeddaten abgeschlossen hat, wird der Status in geändert `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="1d026-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="1d026-169">Sie können die Seite Details jetzt anzeigen, indem Sie die Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="1d026-169">You can now view the details page by choosing the classifier.</span></span>


![Schulungs fähige Klassifizierung zum Testen verfügbar](../media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="1d026-171">Sammeln Sie mindestens 200 Testinhalts Elemente (10.000 max), um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1d026-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="1d026-172">Dabei muss es sich um eine Mischung von Elementen handeln, die starke positive Ergebnisse aufweisen, starke negative und einige, die in ihrer Natur etwas weniger offensichtlich sind.</span><span class="sxs-lookup"><span data-stu-id="1d026-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="1d026-173">Weitere Informationen finden Sie unter [standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) für die unterstützten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="1d026-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d026-174">Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="1d026-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="1d026-175">Platzieren Sie den Testinhalt in einem SharePoint Online Ordner, *der ausschließlich für den Testinhalt*reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="1d026-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="1d026-176">Notieren Sie sich die SharePoint Online Website, Bibliothek und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="1d026-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="1d026-177">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Testdaten erstellen, lassen Sie mindestens eine Stunde für diesen Ort indiziert werden, bevor Sie die Schulungs Klassifizierung erstellen, die diese Startdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d026-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="1d026-178">Wählen Sie aus `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="1d026-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="1d026-179">Wählen Sie die SharePoint Online Website, Bibliothek und Ordner-URL für die Testinhalts Website aus Schritt 12 aus.</span><span class="sxs-lookup"><span data-stu-id="1d026-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="1d026-180">Wählen Sie aus `Add` .</span><span class="sxs-lookup"><span data-stu-id="1d026-180">Choose `Add`.</span></span>

15. <span data-ttu-id="1d026-181">Beenden Sie den Assistenten, indem Sie auswählen `Done` .</span><span class="sxs-lookup"><span data-stu-id="1d026-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="1d026-182">Ihre Schulungs-Klassifizierung dauert bis zu einer Stunde, um die Testdateien zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d026-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="1d026-183">Wenn die ausbildende Klassifizierung die Verarbeitung Ihrer Testdateien abgeschlossen hat, wird der Status auf der Seite Details in geändert `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="1d026-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="1d026-184">Wenn Sie die Größe des testsamples vergrößern möchten, wählen Sie aus, `Add items to test` und lassen Sie die Schulungs-Klassifizierung die zusätzlichen Elemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d026-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![zur Überprüfung des Screenshot verfügbar](../media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="1d026-186">Klicken Sie `Tested items to review` auf die Registerkarte, um Elemente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1d026-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="1d026-187">Microsoft 365 wird 30 Elemente gleichzeitig darstellen.</span><span class="sxs-lookup"><span data-stu-id="1d026-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="1d026-188">Überprüfen Sie diese, und `We predict this item is "Relevant". Do you agree?` Wählen Sie im Feld entweder `Yes` oder `No` oder aus `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="1d026-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="1d026-189">Die Modellgenauigkeit wird nach jeweils 30 Elementen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1d026-189">Model accuracy is automatically updated after every 30 items.</span></span>

![Feld "Elemente überprüfen"](../media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="1d026-191">Über *prüfen Sie mindestens 200* Elemente.</span><span class="sxs-lookup"><span data-stu-id="1d026-191">Review *at least* 200 items.</span></span> <span data-ttu-id="1d026-192">Nachdem das Genauigkeits Ergebnis stabilisiert wurde, wird die Option **veröffentlichen** verfügbar sein, und der Status der Klassifizierung wird sagen `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="1d026-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

![Genauigkeits Bewertung und Veröffentlichungs bereit](../media/classifier-trainable-review-ready-to-publish.png)

20. <span data-ttu-id="1d026-194">Veröffentlichen Sie die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="1d026-194">Publish the classifier.</span></span>

21. <span data-ttu-id="1d026-195">Nachdem Ihre Klassifizierung veröffentlicht wurde, wird Sie als Bedingung in der [automatischen Office-Bezeichnungsrichtlinie mit Vertraulichkeits Bezeichnungen](apply-sensitivity-label-automatically.md), [automatisch angewendeten Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) und in der [Kommunikations Konformität](communication-compliance.md)verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="1d026-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

## <a name="give-others-train-and-review-rights"></a><span data-ttu-id="1d026-196">Erteilen von anderen Schulungs-und Überprüfungs rechten</span><span class="sxs-lookup"><span data-stu-id="1d026-196">Give others train and review rights</span></span>

<span data-ttu-id="1d026-197">Verwenden Sie dieses Verfahren, um anderen Benutzern die Berechtigung zum trainieren, überprüfen und Optimieren Ihrer benutzerdefinierten Schulungs Klassifizierung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="1d026-197">Use this procedure to give others permissions to train, review and tune your custom trainable classifier.</span></span>  
 
1. <span data-ttu-id="1d026-198">Als Ersteller der Klassifizierung verbindet sich ein globaler Administrator oder eDiscovery-Administrator mit dem Compliance Center mithilfe von PowerShell mit den Verfahren unter [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="1d026-198">As the creator of the classifier, a global admin or eDiscovery admin connect to the Compliance center using PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span></span>
2. <span data-ttu-id="1d026-199">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1d026-199">Run this command:</span></span>
```powershell
Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
```
<span data-ttu-id="1d026-200">Beispiel: `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1d026-200">For example: `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span></span>

<span data-ttu-id="1d026-201">Sie können diesen Befehl mehrmals ausführen, um mehrere Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1d026-201">You can run this command multiple times to add multiple users.</span></span> <span data-ttu-id="1d026-202">Beachten Sie, dass Sie nur Exchange Online-Schutz (EoP)-Rollengruppen und keine Azure-Rollengruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="1d026-202">Note that you can only add Exchange Online Protection (EOP) Role Groups and not Azure Role Groups.</span></span>
