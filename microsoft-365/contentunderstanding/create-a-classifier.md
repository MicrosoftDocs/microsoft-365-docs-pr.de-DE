---
title: Erstellen eines Klassifizierers
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informationen zum Erstellen eines Klassifizierers
ms.openlocfilehash: 13ae099d051ac526dc5b13e4cb55a1dc10eec087
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925356"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d711a-103">Erstellen eines Klassifizierers in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d711a-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="d711a-104">Ein Klassifizierer ist ein Modelltyp, mit dem Sie die Identifizierung und Klassifizierung eines Dokumententyps automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="d711a-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="d711a-105">Sie können zum Beispiel alle Dokumente zur *Vertragsverlängerung* identifizieren, die Ihrer Dokumentbibliothek hinzugefügt werden, wie in der folgenden Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d711a-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Dokument "Vertragsverlängerung"](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="d711a-107">Das Erstellen eines Klassifizierers ermöglicht es Ihnen, einen neuen [SharePoint-Inhaltstyp](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) zu erstellen, der mit dem Modell verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="d711a-107">Creating a classifier enables you to create a new [SharePoint content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="d711a-108">Beim Erstellen des Klassifizierers müssen Sie *Erklärungen* erstellen, um das Modell zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="d711a-109">Auf diese Weise können Sie gemeinsame Daten vermerken, bei denen Sie erwarten würden, dass dieser Dokumenttyp konsistent entdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="d711a-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="d711a-110">Verwenden Sie Beispiele für den Dokumenttyp ("Beispieldateien"), um Ihr Modell zu "trainieren", um Dateien mit dem gleichen Inhaltstyp zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="d711a-111">Zum Erstellen eines Klassifizierers müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="d711a-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="d711a-112">Ihr Modell benennen.</span><span class="sxs-lookup"><span data-stu-id="d711a-112">Name your model.</span></span>
2. <span data-ttu-id="d711a-113">Ihre Beispieldateien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d711a-113">Add your example files.</span></span>
3. <span data-ttu-id="d711a-114">Ihre Beispieldateien bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="d711a-114">Label your example files.</span></span>
4. <span data-ttu-id="d711a-115">Erklärung erstellen.</span><span class="sxs-lookup"><span data-stu-id="d711a-115">Create an explanation.</span></span>
5. <span data-ttu-id="d711a-116">Ihr Modell testen.</span><span class="sxs-lookup"><span data-stu-id="d711a-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="d711a-117">Während Ihr Modell einen Klassifizierer verwendet, um Dokumenttypen zu identifizieren und zu klassifizieren, können Sie sich auch dafür entscheiden, bestimmte Informationen aus jeder durch das Modell identifizierten Datei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d711a-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="d711a-118">Erstellen Sie hierzu einen **Extraktor**, der dem Modell hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d711a-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="d711a-119">Siehe [Erstellen eines Extraktors](create-an-extractor.md)</span><span class="sxs-lookup"><span data-stu-id="d711a-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="d711a-120">Ihr Modell benennen</span><span class="sxs-lookup"><span data-stu-id="d711a-120">Name your model</span></span>

<span data-ttu-id="d711a-121">Der erste Schritt zum Erstellen Ihres Modells ist die Benennung:</span><span class="sxs-lookup"><span data-stu-id="d711a-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="d711a-122">Wählen Sie im Inhaltscenter **Neu** aus, und dann **Modell erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d711a-122">From the content center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="d711a-123">Geben Sie im Bereich **Neues "Document Understanding-Modell"** in das Feld **Name** den Namen des Modells ein.</span><span class="sxs-lookup"><span data-stu-id="d711a-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="d711a-124">Wenn Sie beispielsweise Vertragsverlängerungsdokumente identifizieren möchten, könnten Sie das Modell *Vertragsverlängerung* benennen.</span><span class="sxs-lookup"><span data-stu-id="d711a-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="d711a-125">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d711a-125">Choose **Create**.</span></span> <span data-ttu-id="d711a-126">Dadurch wird eine Homepage für das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="d711a-126">This creates a home page for the model.</span></span></br>

    ![Homepage des Klassifizierungsmodells](../media/content-understanding/model-home.png)

<span data-ttu-id="d711a-128">Wenn Sie ein Modell erstellen, erstellen Sie auch einen neuen Websiteinhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="d711a-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="d711a-129">Ein Inhaltstyp stellt eine Kategorie von Dokumenten dar, die gemeinsame Merkmale aufweisen und eine Sammlung von Spalten oder Metadateneigenschaften für diesen bestimmten Inhalt gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="d711a-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="d711a-130">SharePoint-Inhaltstypen werden über den [Inhaltstypen-Katalog](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d711a-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="d711a-131">In diesem Beispiel legen Sie beim Erstellen des Modells einen neuen Inhaltstyp *Vertragsverlängerung* an.</span><span class="sxs-lookup"><span data-stu-id="d711a-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="d711a-132">Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Unternehmensinhaltstyp im SharePoint-Inhaltstypen-Katalog zuordnen möchten, um sein Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d711a-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="d711a-133">Unternehmensinhaltstypen werden im Inhaltstyp-Hub im SharePoint Admin Center gespeichert und für alle Websites im Mandanten syndiziert.</span><span class="sxs-lookup"><span data-stu-id="d711a-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="d711a-134">Beachten Sie, dass Sie zwar einen vorhandenen Inhaltstyp verwenden können, um sein Schema zur Unterstützung der Identifizierung und Klassifizierung zu nutzen, dass Sie Ihr Modell jedoch noch darauf trainieren müssen, Informationen aus den von ihm identifizierten Dateien zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Erweiterte Einstellungen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="d711a-136">Ihre Beispieldateien hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d711a-136">Add your example files</span></span>

<span data-ttu-id="d711a-137">Fügen Sie auf der Homepage des Modells Ihre Beispieldateien hinzu, die Sie zum Trainieren des Modells benötigen, um Ihren Dokumenttyp zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="d711a-138">Sie sollten die gleichen Dateien sowohl für die Klassifizierer- als auch für die [Extraktor-Schulung](create-an-extractor.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d711a-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="d711a-139">Sie haben jederzeit die Möglichkeit, später weitere hinzuzufügen, aber in der Regel fügen Sie einen vollständigen Satz von Beispieldateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="d711a-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="d711a-140">Bezeichnen Sie einige, um Ihr Modell zu trainieren, und testen Sie die übrigen nicht bezeichneten, um die Modelleignung zu beurteilen.</span><span class="sxs-lookup"><span data-stu-id="d711a-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="d711a-141">Für Ihren Schulungssatz möchten Sie sowohl positive als auch negative Beispiele verwenden:</span><span class="sxs-lookup"><span data-stu-id="d711a-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="d711a-142">Positives Beispiel: Dokumente, die den Dokumenttyp darstellen.</span><span class="sxs-lookup"><span data-stu-id="d711a-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="d711a-143">Diese enthalten Zeichenfolgen und Informationen, die in diesem Dokumenttyp immer vorhanden wären.</span><span class="sxs-lookup"><span data-stu-id="d711a-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="d711a-144">Negatives Beispiel: Jedes andere Dokument, das nicht das Dokument darstellt, das Sie klassifizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d711a-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="d711a-145">Achten Sie darauf, mindestens fünf positive Beispiele und mindestens ein negatives Beispiel zu verwenden, um Ihr Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="d711a-146">Sie möchten weitere erstellen, um Ihr Modell nach dem Schulungsvorgang zu testen.</span><span class="sxs-lookup"><span data-stu-id="d711a-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="d711a-147">Hinzufügen von Beispieldateien:</span><span class="sxs-lookup"><span data-stu-id="d711a-147">To add example files:</span></span>

1. <span data-ttu-id="d711a-148">Klicken Sie auf der Homepage des Modells in der Kachel **Beispieldateien hinzufügen** auf **Dateien hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d711a-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="d711a-149">Wählen Sie auf der Seite **Beispieldateien für Ihr Modell auswählen** aus, und wählen Sie Ihre Beispieldateien aus der Bibliothek "Schulungsdateien" im Inhaltscenter aus.</span><span class="sxs-lookup"><span data-stu-id="d711a-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="d711a-150">Wenn Sie die Dateien dort noch nicht hochgeladen hatten, können Sie diese jetzt hochladen, indem Sie auf **Hochladen** klicken, um sie in die Bibliothek "Schulungsdateien" zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="d711a-151">Nachdem Sie die Beispieldateien ausgewählt haben, die zum Trainieren des Modells verwendet werden sollen, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d711a-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Ihre Beispieldateien auswählen](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="d711a-153">Ihre Beispieldateien bezeichnen</span><span class="sxs-lookup"><span data-stu-id="d711a-153">Label your example files</span></span>

<span data-ttu-id="d711a-154">Nachdem Sie Ihre Beispieldateien hinzugefügt haben, müssen Sie sie entweder als positive oder negative Beispiele bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="d711a-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="d711a-155">Klicken Sie auf der Homepage des Modells auf der Kachel **Dateien klassifizieren und Schulungen ausführen** auf **Klassifizierer trainieren**.</span><span class="sxs-lookup"><span data-stu-id="d711a-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier**.</span></span>
   <span data-ttu-id="d711a-156">Dadurch wird die Bezeichnungsseite angezeigt, die eine Liste Ihrer Beispieldateien enthält, wobei die erste Datei im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d711a-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="d711a-157">Im Viewer oben auf der ersten Beispieldatei sollten Sie einen Text sehen, der Sie fragt, ob die Datei ein Beispiel für das gerade erstellte Modell ist.</span><span class="sxs-lookup"><span data-stu-id="d711a-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="d711a-158">Wenn es sich um ein positives Beispiel handelt, wählen Sie **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="d711a-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="d711a-159">Wenn es sich um ein negatives Beispiel handelt, wählen Sie **Nein** aus.</span><span class="sxs-lookup"><span data-stu-id="d711a-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="d711a-160">Wählen Sie aus der Liste **Bezeichnete Beispiele** auf der linken Seite weitere Dateien aus, die Sie als Beispiele verwenden möchten, und bezeichnen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="d711a-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Homepage des Klassifizierers](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="d711a-162">Bezeichnen Sie mindestens fünf positive Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d711a-162">Label at least five positive examples.</span></span> <span data-ttu-id="d711a-163">Sie müssen außerdem mindestens ein negatives Beispiel bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="d711a-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="d711a-164">Erklärung erstellen</span><span class="sxs-lookup"><span data-stu-id="d711a-164">Create an explanation</span></span>

<span data-ttu-id="d711a-165">Der nächste Schritt besteht darin, auf der Seite "Trainieren" eine Erklärung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d711a-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="d711a-166">Eine Erklärung hilft dem Modell zu verstehen, wie das Dokument zu erkennen ist.</span><span class="sxs-lookup"><span data-stu-id="d711a-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="d711a-167">Beispielsweise enthalten die Dokumente "Vertragsverlängerung" immer eine Textzeichenfolge *Anforderung nach zusätzlicher Veröffentlichung*.</span><span class="sxs-lookup"><span data-stu-id="d711a-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="d711a-168">Bei Verwendung mit Extraktoren identifiziert eine Erklärung die Zeichenfolge, die Sie aus dem Dokument extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d711a-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="d711a-169">Erstellen einer Erklärung:</span><span class="sxs-lookup"><span data-stu-id="d711a-169">To create an explanation:</span></span>

1. <span data-ttu-id="d711a-170">Wählen Sie auf der Homepage des Modells die Registerkarte **Trainieren**, um zur Seite "Trainieren" zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d711a-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="d711a-171">Auf der Seite "Trainieren" sollten Sie im Abschnitt **Geschulte Dateien** eine Liste der Beispieldateien sehen, die Sie zuvor bezeichnet haben.</span><span class="sxs-lookup"><span data-stu-id="d711a-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="d711a-172">Wählen Sie eine der positiven Dateien aus der Liste aus, die im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d711a-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="d711a-173">Wählen Sie im Abschnitt "Erklärung" **Neu** aus und dann **Leerzeichen**.</span><span class="sxs-lookup"><span data-stu-id="d711a-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="d711a-174">Auf der Seite **Erklärung erstellen**:</span><span class="sxs-lookup"><span data-stu-id="d711a-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="d711a-175">a.</span><span class="sxs-lookup"><span data-stu-id="d711a-175">a.</span></span> <span data-ttu-id="d711a-176">Geben Sie den **Namen** ein (zum Beispiel "Veröffentlichungssperre").</span><span class="sxs-lookup"><span data-stu-id="d711a-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="d711a-177">b.</span><span class="sxs-lookup"><span data-stu-id="d711a-177">b.</span></span> <span data-ttu-id="d711a-178">Wählen Sie den **Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="d711a-178">Select the **Type**.</span></span> <span data-ttu-id="d711a-179">Wählen Sie für das Beispiel **Begriffsliste**, da Sie eine Textzeichenfolge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d711a-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="d711a-180">c.</span><span class="sxs-lookup"><span data-stu-id="d711a-180">c.</span></span> <span data-ttu-id="d711a-181">Geben Sie im Feld **Hier eingeben** die Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="d711a-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="d711a-182">Für das Beispiel fügen Sie "Anforderung nach zusätzlicher Veröffentlichung" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d711a-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="d711a-183">Sie können **Groß-/Kleinschreibung beachten**", wenn bei der Zeichenfolge zwischen Groß- und Kleinschreibung unterschieden werden muss.</span><span class="sxs-lookup"><span data-stu-id="d711a-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="d711a-184">d.</span><span class="sxs-lookup"><span data-stu-id="d711a-184">d.</span></span> <span data-ttu-id="d711a-185">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d711a-185">Click **Save**.</span></span>

    ![Erklärung erstellen](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="d711a-187">Das Inhaltscenter prüft nun, ob die von Ihnen erstellte Erklärung vollständig genug war, um die verbleibenden bezeichneten Beispieldateien korrekt als positive und negative Beispiele zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d711a-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="d711a-188">Markieren Sie im Abschnitt "Geschulte Dateien" die Spalte **Auswertung** nach Abschluss der Schulung, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d711a-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="d711a-189">Die Dateien zeigen den Wert **Übereinstimmung** an, wenn die Erklärungen, die Sie erstellt haben, ausreichend waren, um mit dem übereinzustimmen, was Sie als positiv oder negativ bezeichnet haben.</span><span class="sxs-lookup"><span data-stu-id="d711a-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Übereinstimmungswert](../media/content-understanding/match.png) 

<span data-ttu-id="d711a-191">Wenn Sie **Keine Übereinstimmung** bei den bezeichneten Dateien erhalten, müssen Sie möglicherweise eine zusätzliche Erklärung erstellen, um dem Modell weitere Informationen zur Identifizierung des Dokumententyps bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d711a-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="d711a-192">Wenn dies der Fall ist, klicken Sie auf die Datei, um weitere Informationen darüber zu erhalten, warum keine Übereinstimmung stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="d711a-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="d711a-193">Ihr Modell testen</span><span class="sxs-lookup"><span data-stu-id="d711a-193">Test your model</span></span>

<span data-ttu-id="d711a-194">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie nun das Modell für Ihre restlichen nicht beschrifteten Beispieldateien testen, die das Modell noch nicht kennt.</span><span class="sxs-lookup"><span data-stu-id="d711a-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="d711a-195">Das ist ein optionaler aber nützlicher Schritt, um die "Tauglichkeit" oder die Bereitschaft des Modells vor seiner Verwendung zu bewerten. Dazu wird es an Dateien getestet, die das Modell noch nie gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="d711a-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="d711a-196">Wählen Sie auf der Homepage des Modells die Registerkarte **Test**. Dadurch wird das Modell für Ihre nicht beschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d711a-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="d711a-197">In der Liste **Testdateien** werden Ihre Beispieldateien angezeigt und zeigen an, ob das Modell sie als positiv oder negativ vorhergesagt hat.</span><span class="sxs-lookup"><span data-stu-id="d711a-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="d711a-198">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="d711a-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test von nicht bezeichneten Dateien](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="d711a-200">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d711a-200">See Also</span></span>
[<span data-ttu-id="d711a-201">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="d711a-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d711a-202">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="d711a-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d711a-203">Beschreibungstypen</span><span class="sxs-lookup"><span data-stu-id="d711a-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="d711a-204">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="d711a-204">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="d711a-205">Barrierefreiheitsmodus für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d711a-205">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)