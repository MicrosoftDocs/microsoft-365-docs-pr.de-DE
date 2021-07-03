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
description: Ein Microsoft 365 Klassifizierer ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele geben, die Sie sich ansehen können. In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Klassifizierer erstellen und trainieren und sie neu trainieren, um die Genauigkeit zu erhöhen.
ms.openlocfilehash: 3053e5154fb4e1ff39ce7db366ce4679bbb8911d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286633"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="6823f-104">Erste Schritte mit trainierbaren Klassifizierern</span><span class="sxs-lookup"><span data-stu-id="6823f-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="6823f-105">Ein Microsoft 365 trainierbarer Klassifizierer ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben.</span><span class="sxs-lookup"><span data-stu-id="6823f-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6823f-106">Sobald Sie geschult sind, können Sie damit Elemente für die Anwendung von Office Vertraulichkeitsbezeichnungen, Kommunikationscompliancerichtlinien und Aufbewahrungsbezeichnungsrichtlinien identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6823f-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6823f-107">Zum Erstellen eines benutzerdefinierten trainierbaren Klassifizierers müssen Sie zunächst Beispiele bereitstellen, die vom Menschen ausgewählt und positiv mit der Kategorie übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6823f-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="6823f-108">Nachdem diese verarbeitet wurden, testen Sie die Fähigkeit der Klassifizierer, vorherzusagen, indem Sie eine Mischung aus positiven und negativen Stichproben erhalten.</span><span class="sxs-lookup"><span data-stu-id="6823f-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="6823f-109">In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Klassifizierer erstellen und trainieren und die Leistung von benutzerdefinierten trainierbaren Klassifizierern und vorab trainierten Klassifizierern während ihrer Lebensdauer durch Umschulung verbessern.</span><span class="sxs-lookup"><span data-stu-id="6823f-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="6823f-110">Weitere Informationen zu den verschiedenen Typen von Klassifizierern finden Sie unter [Informationen zu trainierbaren Klassifizierern.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="6823f-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="6823f-111">Sehen Sie sich dieses Video an, um eine kurze Zusammenfassung der Erstellung eines trainierbaren Klassifizierers zu sehen.</span><span class="sxs-lookup"><span data-stu-id="6823f-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="6823f-112">Sie müssen immer noch diesen vollständigen Artikel lesen, um die Details zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6823f-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="6823f-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6823f-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="6823f-114">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6823f-114">Licensing requirements</span></span>

<span data-ttu-id="6823f-115">Klassifizierungen sind ein Microsoft 365 E5- oder E5-Compliance-Feature.</span><span class="sxs-lookup"><span data-stu-id="6823f-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="6823f-116">Sie müssen über eines dieser Abonnements verfügen, um sie nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="6823f-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="6823f-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6823f-117">Permissions</span></span>

<span data-ttu-id="6823f-118">So greifen Sie auf Klassifizierer in der Benutzeroberfläche zu:</span><span class="sxs-lookup"><span data-stu-id="6823f-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="6823f-119">Der globale Administrator muss sich dafür entscheiden, dass der Mandant benutzerdefinierte Klassifizierer erstellt.</span><span class="sxs-lookup"><span data-stu-id="6823f-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="6823f-120">Die Rolle "Complianceadministrator" ist erforderlich, um einen Klassifizierer zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="6823f-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="6823f-121">Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierer in diesen Szenarien zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6823f-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6823f-122">Szenario mit Aufbewahrungsbezeichnungsrichtlinien: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung"</span><span class="sxs-lookup"><span data-stu-id="6823f-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="6823f-123">Richtlinienszenario für Vertraulichkeitsbezeichnungen: Sicherheitsadministrator, Complianceadministrator, Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="6823f-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="6823f-124">Szenario der Kommunikationscompliance-Richtlinie: Administrator des Insider-Risikomanagements, Administrator für aufsichtsrechtliche Überprüfung</span><span class="sxs-lookup"><span data-stu-id="6823f-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6823f-125">Standardmäßig kann nur der Benutzer, der einen benutzerdefinierten Klassifizierer erstellt, die von diesem Klassifizierer erstellten Vorhersagen trainieren und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6823f-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="6823f-126">Vorbereiten eines benutzerdefinierten trainierbaren Klassifizierers</span><span class="sxs-lookup"><span data-stu-id="6823f-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="6823f-127">Es ist hilfreich zu verstehen, was bei der Erstellung eines benutzerdefinierten trainierbaren Klassifizierers vor dem Einlassen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6823f-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="6823f-128">Zeitachse</span><span class="sxs-lookup"><span data-stu-id="6823f-128">Timeline</span></span>

<span data-ttu-id="6823f-129">Diese Zeitachse spiegelt eine Beispielbereitstellung trainierbarer Klassifizierer wider.</span><span class="sxs-lookup"><span data-stu-id="6823f-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="6823f-131">Die Erstmalige Anmeldung für trainierbare Klassifizierer ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6823f-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="6823f-132">Es dauert zwölf Tage, bis Microsoft 365 eine Grundlegende Auswertung der Inhalte Ihrer Organisation durchführen.</span><span class="sxs-lookup"><span data-stu-id="6823f-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="6823f-133">Wenden Sie sich an Ihren globalen Administrator, um den Anmeldevorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="6823f-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="6823f-134">Gesamter Workflow</span><span class="sxs-lookup"><span data-stu-id="6823f-134">Overall workflow</span></span>

<span data-ttu-id="6823f-135">Weitere Informationen zum Gesamtworkflow der Erstellung benutzerdefinierter trainierbarer Klassifizierer finden Sie unter [Prozessablauf zum Erstellen von trainierbaren Klassifizierern für Kunden.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="6823f-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="6823f-136">Ausgangsinhalt</span><span class="sxs-lookup"><span data-stu-id="6823f-136">Seed content</span></span>

<span data-ttu-id="6823f-137">Wenn ein trainierbarer Klassifizierer ein Element unabhängig und genau als eine bestimmte Kategorie von Inhalten identifizieren soll, müssen Sie es zunächst mit vielen Beispielen des Inhaltstyps in der Kategorie präsentieren.</span><span class="sxs-lookup"><span data-stu-id="6823f-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="6823f-138">Diese Zufuhr von Beispielen an den trainierbaren Klassifizierer wird als *Seeding* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6823f-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="6823f-139">Ausgangsinhalte werden von einem Menschen ausgewählt und stehen für die Kategorie der Inhalte.</span><span class="sxs-lookup"><span data-stu-id="6823f-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="6823f-140">Sie benötigen mindestens 50 positive Beispiele und bis zu 500.</span><span class="sxs-lookup"><span data-stu-id="6823f-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="6823f-141">Der trainierbare Klassifizierer verarbeitet bis zu den 500 zuletzt erstellten Beispielen (nach Datums-/Zeitstempel der Datei).</span><span class="sxs-lookup"><span data-stu-id="6823f-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="6823f-142">Je mehr Beispiele Sie bereitstellen, desto genauer sind die Vorhersagen, die der Klassifizierer macht.</span><span class="sxs-lookup"><span data-stu-id="6823f-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="6823f-143">Testen von Inhalten</span><span class="sxs-lookup"><span data-stu-id="6823f-143">Testing content</span></span>

<span data-ttu-id="6823f-144">Nachdem der trainierbare Klassifizierer genügend positive Beispiele verarbeitet hat, um ein Vorhersagemodell zu erstellen, müssen Sie die getroffenen Vorhersagen testen, um festzustellen, ob der Klassifizierer zwischen Elementen, die der Kategorie entsprechen, und Elementen, die nicht übereinstimmen, ordnungsgemäß unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="6823f-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="6823f-145">Dazu wählen Sie einen weiteren, hoffentlich größeren Satz von vom Menschen ausgewählten Inhalten aus, die aus Beispielen bestehen, die in die Kategorie fallen sollten, und Beispielen, die nicht in die Kategorie fallen.</span><span class="sxs-lookup"><span data-stu-id="6823f-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="6823f-146">Sie sollten mit anderen Daten als die anfänglichen Startdaten testen, die Sie zuerst angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6823f-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="6823f-147">Nachdem diese verarbeitet wurden, durchlaufen Sie die Ergebnisse manuell und überprüfen, ob jede Vorhersage korrekt, falsch oder nicht sicher ist.</span><span class="sxs-lookup"><span data-stu-id="6823f-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="6823f-148">Der trainierbare Klassifizierer verwendet dieses Feedback, um sein Vorhersagemodell zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6823f-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="6823f-149">Um optimale Ergebnisse zu erzielen, müssen Sie mindestens 200 Elemente in Ihrem Testbeispiel mit einer gleichmäßigen Verteilung positiver und negativer Übereinstimmungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="6823f-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="6823f-150">So erstellen Sie einen trainierbaren Klassifizierer</span><span class="sxs-lookup"><span data-stu-id="6823f-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="6823f-151">Sammeln sie zwischen 50 und 500 Startinhaltselementen.</span><span class="sxs-lookup"><span data-stu-id="6823f-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="6823f-152">Hierbei darf es sich nur um Beispiele handeln, die den Inhaltstyp stark darstellen, den der trainierbare Klassifizierer positiv als in der Klassifizierungskategorie identifizieren soll.</span><span class="sxs-lookup"><span data-stu-id="6823f-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="6823f-153">Die unterstützten Dateitypen finden Sie [unter "Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server".](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="6823f-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6823f-154">Die Ausgangs- und Testbeispielelemente dürfen nicht verschlüsselt werden, und sie müssen englisch sein.</span><span class="sxs-lookup"><span data-stu-id="6823f-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6823f-155">Stellen Sie sicher, dass die Elemente in Ihrem Startset **starke** Beispiele für die Kategorie sind.</span><span class="sxs-lookup"><span data-stu-id="6823f-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="6823f-156">Der trainierbare Klassifizierer erstellt zunächst sein Modell basierend auf dem Ausgangswert.</span><span class="sxs-lookup"><span data-stu-id="6823f-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="6823f-157">Der Klassifizierer geht davon aus, dass alle Ausgangsbeispiele starke positive Ergebnisse sind und keine Möglichkeit hat zu wissen, ob es sich bei einer Stichprobe um eine schwache oder negative Übereinstimmung mit der Kategorie handelt.</span><span class="sxs-lookup"><span data-stu-id="6823f-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="6823f-158">Platzieren Sie den Startinhalt in einem SharePoint Online-Ordner, *der nur den Startinhalt* enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="6823f-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="6823f-159">Notieren Sie sich die Website, Bibliothek und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="6823f-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="6823f-160">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Startdaten erstellen, lassen Sie die Indizierung dieses Speicherorts mindestens eine Stunde zu, bevor Sie den trainierbaren Klassifizierer erstellen, der diese Startdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="6823f-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="6823f-161">Melden Sie sich bei Microsoft 365 Compliance Center mit Complianceadministrator- oder Sicherheitsadministratorrollenzugriff an, und öffnen **Sie Microsoft 365 Compliance Center** oder **Microsoft 365** Sicherheitscenter-Datenklassifizierung.  >  </span><span class="sxs-lookup"><span data-stu-id="6823f-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="6823f-162">Wählen Sie die Registerkarte **"Trainierbare Klassifizierer" aus.**</span><span class="sxs-lookup"><span data-stu-id="6823f-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="6823f-163">Wählen Sie **trainierbaren Klassifizierer erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="6823f-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="6823f-164">Geben Sie die entsprechenden Werte für die und die Felder der Kategorie der Elemente ein, die `Name` dieser `Description` trainierbare Klassifizierer identifizieren soll.</span><span class="sxs-lookup"><span data-stu-id="6823f-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="6823f-165">Wählen Sie die SharePoint Onlinewebsite, Bibliothek und Ordner-URL für die Ausgangsinhaltswebsite aus Schritt 2 aus.</span><span class="sxs-lookup"><span data-stu-id="6823f-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="6823f-166">Wählen Sie `Add` .</span><span class="sxs-lookup"><span data-stu-id="6823f-166">Choose `Add`.</span></span>

8. <span data-ttu-id="6823f-167">Überprüfen Sie die Einstellungen, und wählen Sie `Create trainable classifier` aus.</span><span class="sxs-lookup"><span data-stu-id="6823f-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="6823f-168">Innerhalb von 24 Stunden verarbeitet der trainierbare Klassifizierer die Startdaten und erstellt ein Vorhersagemodell.</span><span class="sxs-lookup"><span data-stu-id="6823f-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="6823f-169">Der Klassifizierungsstatus `In progress` ist, während die Startdaten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6823f-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="6823f-170">Wenn der Klassifizierer die Verarbeitung der Startdaten abgeschlossen hat, ändert sich der Status in `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="6823f-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="6823f-171">Sie können jetzt die Detailseite anzeigen, indem Sie den Klassifizierer auswählen.</span><span class="sxs-lookup"><span data-stu-id="6823f-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6823f-172">![Trainierbarer Klassifizierer, der für Tests bereit ist](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6823f-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="6823f-173">Sammeln Sie mindestens 200 Testinhaltselemente (maximal 10.000), um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="6823f-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="6823f-174">Hierbei sollte es sich um eine Mischung aus Elementen mit starken positiven, starken negativen und einigen Elementen handelt, die ihrer Natur nach etwas weniger offensichtlich sind.</span><span class="sxs-lookup"><span data-stu-id="6823f-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="6823f-175">Die unterstützten Dateitypen finden Sie [unter "Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server".](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="6823f-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6823f-176">Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="6823f-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="6823f-177">Platzieren Sie den Testinhalt in einem SharePoint Online-Ordner, *der nur den Testinhalt* enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="6823f-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="6823f-178">Notieren Sie sich die SharePoint Onlinewebsite, Bibliothek und Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="6823f-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="6823f-179">Wenn Sie eine neue Website und einen neuen Ordner für Ihre Testdaten erstellen, lassen Sie die Indizierung dieses Speicherorts mindestens eine Stunde zu, bevor Sie den trainierbaren Klassifizierer erstellen, der diese Startdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="6823f-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="6823f-180">Wählen Sie `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="6823f-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="6823f-181">Wählen Sie die SharePoint Onlinewebsite, Bibliothek und Ordner-URL für die Testinhaltswebsite aus Schritt 12 aus.</span><span class="sxs-lookup"><span data-stu-id="6823f-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="6823f-182">Wählen Sie `Add` .</span><span class="sxs-lookup"><span data-stu-id="6823f-182">Choose `Add`.</span></span>

15. <span data-ttu-id="6823f-183">Schließen Sie den Assistenten ab, indem Sie . `Done` auswählen.</span><span class="sxs-lookup"><span data-stu-id="6823f-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="6823f-184">Die Verarbeitung der Testdateien durch den trainierbaren Klassifizierer dauert bis zu einer Stunde.</span><span class="sxs-lookup"><span data-stu-id="6823f-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="6823f-185">Wenn der trainierbare Klassifizierer die Verarbeitung Ihrer Testdateien abgeschlossen hat, ändert sich der Status auf der Detailseite in `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="6823f-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="6823f-186">Wenn Sie die Testbeispielgröße erhöhen müssen, wählen `Add items to test` Sie den trainierbaren Klassifizierer aus, und lassen Sie es zu, um die zusätzlichen Elemente zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6823f-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6823f-187">![bereit zum Überprüfen des Screenshots](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6823f-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="6823f-188">Wählen Sie `Tested items to review` die Registerkarte aus, um Elemente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6823f-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="6823f-189">Microsoft 365 werden jeweils 30 Elemente präsentieren.</span><span class="sxs-lookup"><span data-stu-id="6823f-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="6823f-190">Überprüfen Sie sie, und wählen Sie im `We predict this item is "Relevant". Do you agree?` Feld entweder `Yes` oder `No` `Not sure, skip to next item` aus.</span><span class="sxs-lookup"><span data-stu-id="6823f-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="6823f-191">Die Modellgenauigkeit wird nach 30 Elementen automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6823f-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6823f-192">![Feld "Elemente überprüfen"](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6823f-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="6823f-193">Überprüfen Sie *mindestens* 200 Elemente.</span><span class="sxs-lookup"><span data-stu-id="6823f-193">Review *at least* 200 items.</span></span> <span data-ttu-id="6823f-194">Sobald sich die Genauigkeitsbewertung stabilisiert hat, wird die **Veröffentlichungsoption** verfügbar sein, und der Klassifizierungsstatus wird `Ready to use` sagen.</span><span class="sxs-lookup"><span data-stu-id="6823f-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6823f-195">![Genauigkeitsbewertung und Veröffentlichungsbereitschaft](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="6823f-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="6823f-196">Veröffentlichen Sie den Klassifizierer.</span><span class="sxs-lookup"><span data-stu-id="6823f-196">Publish the classifier.</span></span>

21. <span data-ttu-id="6823f-197">Nach der Veröffentlichung steht Der Klassifizierer als Bedingung in [Office automatischen Bezeichnung mit Vertraulichkeitsbezeichnungen,](apply-sensitivity-label-automatically.md) [automatisch angewendeter Aufbewahrungsbezeichnungsrichtlinie basierend auf einer Bedingung](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) und in der [Kommunikationscompliance](communication-compliance.md)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6823f-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
