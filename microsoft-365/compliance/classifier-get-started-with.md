---
title: Erste Schritte mit trainierbaren Klassifizierern
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
description: Ein Microsoft 365 Klassifikator ist ein Tool, das Sie schulen können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben. In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Klassifikator erstellen und schulen und umtrainieren, um die Genauigkeit zu erhöhen.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918179"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="985bf-104">Erste Schritte mit trainierbaren Klassifizierern</span><span class="sxs-lookup"><span data-stu-id="985bf-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="985bf-105">Ein Microsoft 365 trainierbarer Klassifikator ist ein Tool, das Sie schulen können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben.</span><span class="sxs-lookup"><span data-stu-id="985bf-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="985bf-106">Sobald Sie geschult sind, können Sie es verwenden, um Elemente für die Anwendung Office Vertraulichkeitsbezeichnungen, Kommunikationskonformitätsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="985bf-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="985bf-107">Das Erstellen eines benutzerdefinierten trainierbaren Klassifizierungsklassifikierers umfasst zunächst, ihm Beispiele zu geben, die vom Menschen ausgewählt und positiv mit der Kategorie übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="985bf-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="985bf-108">Nachdem sie diese verarbeitet haben, testen Sie die Klassifiziererfähigkeit, die vorherzusagen ist, indem Sie ihr eine Mischung aus positiven und negativen Beispielen geben.</span><span class="sxs-lookup"><span data-stu-id="985bf-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="985bf-109">In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Klassifikator erstellen und schulen und wie Sie die Leistung von benutzerdefinierten trainierbaren Klassifikatoren und vortrainierten Klassifikatoren über ihre Lebensdauer durch Umschulung verbessern.</span><span class="sxs-lookup"><span data-stu-id="985bf-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="985bf-110">Weitere Informationen zu den verschiedenen Typen von Klassifizierungen finden Sie [unter Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="985bf-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="985bf-111">Sehen Sie sich dieses Video an, um eine kurze Zusammenfassung des Erstellens eines trainierbaren Klassifizierers zu finden.</span><span class="sxs-lookup"><span data-stu-id="985bf-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="985bf-112">Sie müssen weiterhin diesen vollständigen Artikel lesen, um die Details zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="985bf-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="985bf-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="985bf-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="985bf-114">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="985bf-114">Licensing requirements</span></span>

<span data-ttu-id="985bf-115">Klassifizierungen sind eine Microsoft 365 E5 oder E5-Compliance-Funktion.</span><span class="sxs-lookup"><span data-stu-id="985bf-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="985bf-116">Sie müssen über eines dieser Abonnements verfügen, um sie nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="985bf-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="985bf-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="985bf-117">Permissions</span></span>

<span data-ttu-id="985bf-118">So greifen Sie auf Klassifikatoren in der Benutzeroberfläche zu:</span><span class="sxs-lookup"><span data-stu-id="985bf-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="985bf-119">Der globale Administrator muss sich dafür entscheiden, dass der Mandant benutzerdefinierte Klassifizierungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="985bf-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="985bf-120">Die Rolle "Complianceadministrator" ist erforderlich, um einen Klassifikator zu schulen.</span><span class="sxs-lookup"><span data-stu-id="985bf-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="985bf-121">Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierungen in den folgenden Szenarien verwenden zu können:</span><span class="sxs-lookup"><span data-stu-id="985bf-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="985bf-122">Szenario der Aufbewahrungsbezeichnungsrichtlinie: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung"</span><span class="sxs-lookup"><span data-stu-id="985bf-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="985bf-123">Szenario der Vertraulichkeitsbezeichnungsrichtlinie: Sicherheitsadministrator, Kompatibilitätsadministrator, Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="985bf-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="985bf-124">Szenario der Kommunikationskonformitätsrichtlinie: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="985bf-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="985bf-125">Standardmäßig kann nur der Benutzer, der einen benutzerdefinierten Klassifikator erstellt, Vorhersagen trainieren und überprüfen, die von diesem Klassifikator vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="985bf-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="985bf-126">Vorbereiten einer benutzerdefinierten trainierbaren Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="985bf-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="985bf-127">Es ist hilfreich zu verstehen, was beim Erstellen eines benutzerdefinierten trainierbaren Klassifizierungsklassifizierers vor dem Eintauchen dabei ist.</span><span class="sxs-lookup"><span data-stu-id="985bf-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="985bf-128">Zeitachse</span><span class="sxs-lookup"><span data-stu-id="985bf-128">Timeline</span></span>

<span data-ttu-id="985bf-129">Diese Zeitachse spiegelt eine Beispielbereitstellung trainierbarer Klassifizierungen wider.</span><span class="sxs-lookup"><span data-stu-id="985bf-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="985bf-131">Das erste Mal ist die Opt-In für trainierbare Klassifizierungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="985bf-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="985bf-132">Es dauert zwölf Tage, bis Microsoft 365 eine grundlegende Auswertung der Inhalte Ihrer Organisation abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="985bf-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="985bf-133">Wenden Sie sich an Ihren globalen Administrator, um den Opt-In-Prozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="985bf-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="985bf-134">Gesamtworkflow</span><span class="sxs-lookup"><span data-stu-id="985bf-134">Overall workflow</span></span>

<span data-ttu-id="985bf-135">Weitere Informationen zum allgemeinen Workflow zum Erstellen benutzerdefinierter trainierbarer Klassifizierungen finden Sie unter Prozessablauf zum Erstellen von kunden [trainierbaren Klassifizierungen](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="985bf-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="985bf-136">Seedinhalt</span><span class="sxs-lookup"><span data-stu-id="985bf-136">Seed content</span></span>

<span data-ttu-id="985bf-137">Wenn ein trainierbarer Klassifikator ein Element unabhängig und präzise als eine bestimmte Kategorie von Inhalten identifizieren soll, müssen Sie es zunächst mit vielen Beispielen des Inhaltstyps in der Kategorie präsentieren.</span><span class="sxs-lookup"><span data-stu-id="985bf-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="985bf-138">Diese Zufuhr von Beispielen an den trainierbaren Klassifikator wird als *Seeding bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="985bf-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="985bf-139">Seedinhalt wird von einem Menschen ausgewählt und als Die Kategorie von Inhalten bewertet.</span><span class="sxs-lookup"><span data-stu-id="985bf-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="985bf-140">Sie benötigen mindestens 50 positive Beispiele und bis zu 500.</span><span class="sxs-lookup"><span data-stu-id="985bf-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="985bf-141">Der trainierbare Klassifikator wird bis zu den 500 zuletzt erstellten Beispielen verarbeiten (nach Datei erstellter Datums-/Zeitstempel).</span><span class="sxs-lookup"><span data-stu-id="985bf-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="985bf-142">Mit den mehr Beispielen, die Sie bereitstellen, werden die Vorhersagen, die der Klassifikator treffen wird, genauer.</span><span class="sxs-lookup"><span data-stu-id="985bf-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="985bf-143">Testen von Inhalten</span><span class="sxs-lookup"><span data-stu-id="985bf-143">Testing content</span></span>

<span data-ttu-id="985bf-144">Nachdem der trainierbare Klassifikator genügend positive Beispiele zum Erstellen eines Vorhersagemodells verarbeitet hat, müssen Sie die Vorhersagen testen, um zu prüfen, ob der Klassifikator korrekt zwischen Elementen unterscheiden kann, die der Kategorie entsprechen, und Elementen, die nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="985bf-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="985bf-145">Wählen Sie dazu einen anderen, hoffentlich größeren Satz von vom Menschen ausgewählten Inhalten aus, der aus Beispielen besteht, die in die Kategorie fallen sollen, und Beispielen, die dies nicht tun.</span><span class="sxs-lookup"><span data-stu-id="985bf-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="985bf-146">Sie sollten mit anderen Daten als die ursprünglichen Seeddaten testen, die Sie zuerst bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="985bf-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="985bf-147">Sobald sie diese verarbeitet haben, führen Sie die Ergebnisse manuell durch und überprüfen, ob jede Vorhersage richtig, falsch oder nicht sicher ist.</span><span class="sxs-lookup"><span data-stu-id="985bf-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="985bf-148">Der trainierbare Klassifikator verwendet dieses Feedback, um sein Vorhersagemodell zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="985bf-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="985bf-149">Um die besten Ergebnisse zu erzielen, müssen Sie mindestens 200 Elemente im Testbeispielsatz mit einer gleichmäßigen Verteilung positiver und negativer Übereinstimmungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="985bf-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="985bf-150">Erstellen eines trainierbaren Klassifizierers</span><span class="sxs-lookup"><span data-stu-id="985bf-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="985bf-151">Sammeln sie zwischen 50 und 500 Seedinhaltselemente.</span><span class="sxs-lookup"><span data-stu-id="985bf-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="985bf-152">Dabei darf es sich nur um Beispiele handelt, die den Inhaltstyp stark darstellen, den der trainierbare Klassifikator positiv als In der Klassifizierungskategorie identifizieren soll.</span><span class="sxs-lookup"><span data-stu-id="985bf-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="985bf-153">Unter [Standarddurchforstung von Dateinamenerweiterungen und analysierten Dateitypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) finden Sie die unterstützten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="985bf-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="985bf-154">Die Seed- und Testbeispielelemente dürfen nicht verschlüsselt sein und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="985bf-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="985bf-155">Stellen Sie sicher, dass die Elemente in Ihrem Seedset **starke Beispiele** für die Kategorie sind.</span><span class="sxs-lookup"><span data-stu-id="985bf-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="985bf-156">Der trainierbare Klassifikator erstellt sein Modell zunächst basierend auf dem Seeding.</span><span class="sxs-lookup"><span data-stu-id="985bf-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="985bf-157">Der Klassifikator geht davon aus, dass alle Seedbeispiele starke positive Ergebnisse sind und keine Möglichkeit hat, zu wissen, ob eine Stichprobe eine schwache oder negative Übereinstimmung mit der Kategorie ist.</span><span class="sxs-lookup"><span data-stu-id="985bf-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="985bf-158">Platzieren Sie den Seedinhalt in SharePoint Onlineordner, der nur für das Speichern *des Seedinhalts verwendet wird.*</span><span class="sxs-lookup"><span data-stu-id="985bf-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="985bf-159">Notieren Sie sich die Website-, Bibliotheks- und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="985bf-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="985bf-160">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Seeddaten erstellen, lassen Sie mindestens eine Stunde zeit, bis dieser Speicherort indiziert wird, bevor Sie die trainierbare Klassifizierung erstellen, die diese Seeddaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="985bf-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="985bf-161">Melden Sie sich Microsoft 365 Compliance Center mit Zugriff auf die Rolle des Complianceadministrators oder Sicherheitsadministrators an, und öffnen Sie **Microsoft 365 Compliance Center** oder Microsoft 365 Security **Center**  >  **Datenklassifizierung**.</span><span class="sxs-lookup"><span data-stu-id="985bf-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="985bf-162">Wählen Sie die **Registerkarte Trainable classifiers** aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="985bf-163">Wählen **Sie Trainierbare Klassifizierung erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="985bf-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="985bf-164">Geben Sie die entsprechenden Werte für die Felder der Kategorie der Elemente ein, die von `Name` `Description` diesem trainierbaren Klassifizierungstyp identifiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="985bf-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="985bf-165">Wählen Sie SharePoint Schritt 2 die Url der Onlinewebsite, Bibliothek und Ordner für die Seedinhaltswebsite aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="985bf-166">Wählen Sie `Add` aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-166">Choose `Add`.</span></span>

8. <span data-ttu-id="985bf-167">Überprüfen Sie die Einstellungen, und wählen Sie `Create trainable classifier` aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="985bf-168">Innerhalb von 24 Stunden wird der trainierbare Klassifikator die Seeddaten verarbeiten und ein Vorhersagemodell erstellen.</span><span class="sxs-lookup"><span data-stu-id="985bf-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="985bf-169">Der Klassifizierungsstatus `In progress` ist, während die Seeddaten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="985bf-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="985bf-170">Wenn der Klassifikator die Verarbeitung der Seeddaten abgeschlossen hat, ändert sich der Status in `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="985bf-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="985bf-171">Sie können nun die Detailseite anzeigen, indem Sie den Klassifikator auswählen.</span><span class="sxs-lookup"><span data-stu-id="985bf-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="985bf-172">![Trainierbare Klassifikatoren, die für Tests bereit sind](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="985bf-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="985bf-173">Sammeln Sie mindestens 200 Testinhaltselemente (max. 10.000) für optimale Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="985bf-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="985bf-174">Dies sollte eine Mischung aus Elementen sein, die starke Positive, starke Negative und einige sind, die in ihrer Natur etwas weniger offensichtlich sind.</span><span class="sxs-lookup"><span data-stu-id="985bf-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="985bf-175">Unter [Standarddurchforstung von Dateinamenerweiterungen und analysierten Dateitypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) finden Sie die unterstützten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="985bf-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="985bf-176">Die Beispielelemente dürfen nicht verschlüsselt sein und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="985bf-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="985bf-177">Platzieren Sie den Testinhalt in einem SharePoint Onlineordner, der nur für das Speichern *der Testinhalte verwendet wird.*</span><span class="sxs-lookup"><span data-stu-id="985bf-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="985bf-178">Notieren Sie sich die SharePoint Onlinewebsite, Bibliothek und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="985bf-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="985bf-179">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Testdaten erstellen, lassen Sie mindestens eine Stunde zeit, bis dieser Speicherort indiziert wird, bevor Sie den trainierbaren Klassifikator erstellen, der diese Seeddaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="985bf-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="985bf-180">Wählen Sie `Add items to test` aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="985bf-181">Wählen Sie SharePoint Schritt 12 die URL der Onlinewebsite, Bibliothek und ordner für die Testinhaltswebsite aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="985bf-182">Wählen Sie `Add` aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-182">Choose `Add`.</span></span>

15. <span data-ttu-id="985bf-183">Beenden Sie den Assistenten, indem Sie `Done` auswählen.</span><span class="sxs-lookup"><span data-stu-id="985bf-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="985bf-184">Ihre trainierbare Klassifizierung dauert bis zu einer Stunde, um die Testdateien zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="985bf-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="985bf-185">Wenn der trainierbare Klassifikator ihre Testdateien verarbeitet hat, ändert sich der Status auf der Detailseite in `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="985bf-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="985bf-186">Wenn Sie die Größe des Testbeispiels erhöhen müssen, wählen Sie den trainierbaren Klassifikator aus, um die `Add items to test` zusätzlichen Elemente zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="985bf-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="985bf-187">![Bereit zum Überprüfen des Screenshots](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="985bf-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="985bf-188">Wählen `Tested items to review` Sie die Registerkarte aus, um Elemente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="985bf-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="985bf-189">Microsoft 365 werden 30 Elemente gleichzeitig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="985bf-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="985bf-190">Überprüfen Sie sie, und wählen `We predict this item is "Relevant". Do you agree?` Sie im Feld entweder oder oder `Yes` `No` `Not sure, skip to next item` aus.</span><span class="sxs-lookup"><span data-stu-id="985bf-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="985bf-191">Die Modellgenauigkeit wird nach allen 30 Elementen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="985bf-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="985bf-192">![Feld Elemente überprüfen](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="985bf-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="985bf-193">Überprüfen *Sie mindestens* 200 Elemente.</span><span class="sxs-lookup"><span data-stu-id="985bf-193">Review *at least* 200 items.</span></span> <span data-ttu-id="985bf-194">Sobald sich die Genauigkeitsergebnis stabilisiert hat, wird **die** Veröffentlichungsoption verfügbar, und der Klassifizierungsstatus sagt `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="985bf-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="985bf-195">![Genauigkeitsergebnis und bereit zur Veröffentlichung](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="985bf-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="985bf-196">Veröffentlichen Sie den Klassifizierer.</span><span class="sxs-lookup"><span data-stu-id="985bf-196">Publish the classifier.</span></span>

21. <span data-ttu-id="985bf-197">Nach der Veröffentlichung steht Ihr Klassifikator als Bedingung in [Office](apply-sensitivity-label-automatically.md)automatischen Bezeichnungen mit Vertraulichkeitsbezeichnungen, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) automatischer Anwenden einer Aufbewahrungsbezeichnungsrichtlinie basierend auf einer Bedingung und in Kommunikationskonformität zur [Verfügung.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="985bf-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>