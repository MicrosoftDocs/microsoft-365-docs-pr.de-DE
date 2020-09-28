---
title: Erstellen einer Klassifizierung
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Erstellen einer Klassifizierung
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294902"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="27a41-103">Erstellen einer Klassifizierung in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="27a41-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="27a41-104">Der Inhalt in diesem Artikel ist für die Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="27a41-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="27a41-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="27a41-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="27a41-106">Eine Klassifizierung ist ein Modelltyp, mit dem Sie die Identifizierung und Klassifizierung eines Dokumenttyps automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="27a41-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="27a41-107">Beispielsweise können Sie alle *Vertrags Erneuerungs* Dokumente identifizieren, die Ihrer Dokumentbibliothek hinzugefügt werden, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="27a41-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Vertrags Erneuerungs Dokument](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="27a41-109">Das Erstellen einer Klassifizierung ermöglicht Ihnen das Erstellen eines neuen [SharePoint-Inhaltstyps](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) , der dem Modell zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="27a41-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="27a41-110">Beim Erstellen der Klassifizierung müssen Sie *Erläuterungen* zum Definieren des Modells erstellen.</span><span class="sxs-lookup"><span data-stu-id="27a41-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="27a41-111">Auf diese Weise können Sie häufige Daten notieren, die Sie erwarten, dass dieser Dokumenttyp konsistent gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="27a41-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="27a41-112">Verwenden Sie Beispiele für den Dokumenttyp ("Beispieldateien"), um Ihr Modell zu "trainieren", um Dateien mit dem gleichen Inhaltstyp zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="27a41-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="27a41-113">Um eine Klassifizierung zu erstellen, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="27a41-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="27a41-114">Nennen Sie Ihr Modell.</span><span class="sxs-lookup"><span data-stu-id="27a41-114">Name your model.</span></span>
2. <span data-ttu-id="27a41-115">Fügen Sie Ihre Beispieldateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="27a41-115">Add your example files.</span></span>
3. <span data-ttu-id="27a41-116">Beschriften Sie Ihre Beispieldateien.</span><span class="sxs-lookup"><span data-stu-id="27a41-116">Label your example files.</span></span>
4. <span data-ttu-id="27a41-117">Erstellen Sie eine Erläuterung.</span><span class="sxs-lookup"><span data-stu-id="27a41-117">Create an explanation.</span></span>
5. <span data-ttu-id="27a41-118">Testen Sie Ihr Modell.</span><span class="sxs-lookup"><span data-stu-id="27a41-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="27a41-119">Während Ihr Modell eine Klassifizierung verwendet, um Dokumenttypen zu identifizieren und zu klassifizieren, können Sie auch auswählen, dass bestimmte Informationen aus jeder vom Modell identifizierten Datei abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="27a41-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="27a41-120">Erstellen Sie hierzu einen **Extraktor** , der dem Modell hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="27a41-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="27a41-121">Siehe [Erstellen eines Extraktors](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="27a41-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="27a41-122">Benennen Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="27a41-122">Name your model</span></span>

<span data-ttu-id="27a41-123">Der erste Schritt zum Erstellen des Modells besteht darin, ihm einen Namen zu geben:</span><span class="sxs-lookup"><span data-stu-id="27a41-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="27a41-124">Wählen Sie im Inhalts Center **neu**aus, und erstellen Sie dann **ein Modell**.</span><span class="sxs-lookup"><span data-stu-id="27a41-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="27a41-125">Geben Sie im Feld **Neues Dokument grundlegendes Modell** **den Namen des** Modells ein.</span><span class="sxs-lookup"><span data-stu-id="27a41-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="27a41-126">Wenn Sie beispielsweise Vertrags Erneuerungs Dokumente identifizieren möchten, können Sie die Modell *Vertragserneuerung*benennen.</span><span class="sxs-lookup"><span data-stu-id="27a41-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="27a41-127">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="27a41-127">Choose **Create**.</span></span> <span data-ttu-id="27a41-128">Dadurch wird eine Startseite für das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="27a41-128">This creates a home page for the model.</span></span></br>

    ![Klassifizierungsmodell-Startseite](../media/content-understanding/model-home.png)

<span data-ttu-id="27a41-130">Wenn Sie ein Modell erstellen, erstellen Sie auch einen neuen SharePoint-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="27a41-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="27a41-131">Ein SharePoint-Inhaltstyp stellt eine Kategorie von Dokumenten dar, die allgemeine Merkmale aufweisen und eine Auflistung von Spalten oder Metadaten-Eigenschaften für diesen bestimmten Inhalt gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="27a41-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="27a41-132">SharePoint-Inhaltstypen werden über den [Inhaltstypen Katalog](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)verwaltet.</span><span class="sxs-lookup"><span data-stu-id="27a41-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="27a41-133">In diesem Beispiel erstellen Sie beim Erstellen des Modells einen neuen Inhaltstyp für die *Vertragserneuerung* .</span><span class="sxs-lookup"><span data-stu-id="27a41-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="27a41-134">Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Inhaltstyp im SharePoint-Inhaltstypen Katalog zuordnen möchten, um sein Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="27a41-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="27a41-135">Beachten Sie, dass Sie zwar einen vorhandenen Inhaltstyp verwenden können, um sein Schema zur Unterstützung bei der Identifizierung und Klassifizierung zu nutzen, aber Sie müssen Ihr Modell dennoch trainieren, um Informationen aus den identifizierten Dateien zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="27a41-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Erweiterte Einstellungen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="27a41-137">Hinzufügen von Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="27a41-137">Add your example files</span></span>

<span data-ttu-id="27a41-138">Fügen Sie auf der Modell Homepage Ihre Beispieldateien hinzu, die Sie bei der Schulung des Modells zur Identifizierung Ihres Dokumenttyps unterstützen müssen.</span><span class="sxs-lookup"><span data-stu-id="27a41-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="27a41-139">Sie sollten die gleichen Dateien für die Klassifizierung und [Extraktions Schulung](create-an-extractor.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="27a41-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="27a41-140">Sie haben immer die Möglichkeit, später hinzuzufügen, aber in der Regel fügen Sie einen vollständigen Sammlung von Beispieldateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="27a41-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="27a41-141">Beschriften Sie einige, um Ihr Modell zu trainieren, und testen Sie die restlichen unbeschrifteten, um die Modell Fitness auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="27a41-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="27a41-142">Für Ihre Trainingsgruppe möchten Sie sowohl positive als auch negative Beispiele verwenden:</span><span class="sxs-lookup"><span data-stu-id="27a41-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="27a41-143">Positives Beispiel: Dokumente, die den Dokumenttyp darstellen.</span><span class="sxs-lookup"><span data-stu-id="27a41-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="27a41-144">Diese enthalten Zeichenfolgen und Informationen, die immer in dieser Art von Dokument sein würden.</span><span class="sxs-lookup"><span data-stu-id="27a41-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="27a41-145">Negatives Beispiel: Dokumente, die nicht den Dokumenttyp darstellen.</span><span class="sxs-lookup"><span data-stu-id="27a41-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="27a41-146">Dabei handelt es sich um fehlende Zeichenfolgen und Informationen, die in dieser Art von Dokument vorhanden sein müssen.</span><span class="sxs-lookup"><span data-stu-id="27a41-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="27a41-147">Stellen Sie sicher, dass Sie mindestens fünf positive Beispiele und mindestens ein negatives Beispiel zur Schulung Ihres Modells verwenden.</span><span class="sxs-lookup"><span data-stu-id="27a41-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="27a41-148">Sie möchten zusätzliche erstellen, um Ihr Modell nach dem Schulungsprozess zu testen.</span><span class="sxs-lookup"><span data-stu-id="27a41-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="27a41-149">So fügen Sie Beispieldateien hinzu:</span><span class="sxs-lookup"><span data-stu-id="27a41-149">To add sample files:</span></span>

1. <span data-ttu-id="27a41-150">Klicken Sie auf der Modell Startseite in der Kachel **Beispielbibliothek erstellen** auf **Dateien hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="27a41-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="27a41-151">Wählen Sie auf der Seite **Beispieldateien für Ihr Modell auswählen** ihre Beispieldateien aus der Bibliothek Beispieldateien im Inhalts Center aus.</span><span class="sxs-lookup"><span data-stu-id="27a41-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="27a41-152">Wenn Sie Sie nicht bereits hochgeladen haben, wählen Sie, um Sie jetzt hochzuladen, indem Sie auf **hochladen** klicken, um Sie in die Beispieldatei Bibliothek zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="27a41-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="27a41-153">Nachdem Sie Ihre Beispieldateien ausgewählt haben, die zum Trainieren des Modells verwendet werden sollen, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="27a41-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Auswählen von Beispieldateien](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="27a41-155">Bezeichnen der Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="27a41-155">Label your example files</span></span>

<span data-ttu-id="27a41-156">Nachdem Sie Ihre Beispieldateien hinzugefügt haben, müssen Sie Sie als positive oder negative Beispiele bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="27a41-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="27a41-157">Klicken Sie auf der Modell Homepage auf der Kachel **Dateien klassifizieren und Übungsverlauf ausführen** auf **Klassifizierung Klassifizierer**.</span><span class="sxs-lookup"><span data-stu-id="27a41-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="27a41-158">Dadurch wird die Bezeichnungs Seite angezeigt, die eine Liste der Beispieldateien enthält, wobei die erste Datei im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="27a41-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="27a41-159">Im Viewer am oberen Rand der ersten Beispieldatei sollte Text gefragt werden, ob es sich bei der Datei um ein Beispiel des soeben erstellten Modells handelt.</span><span class="sxs-lookup"><span data-stu-id="27a41-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="27a41-160">Wenn es sich um ein positives Beispiel handelt, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="27a41-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="27a41-161">Wenn es sich um ein negatives Beispiel handelt, wählen Sie **Nein**aus.</span><span class="sxs-lookup"><span data-stu-id="27a41-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="27a41-162">Wählen Sie in der Liste mit den **beschrifteten Beispielen** auf der linken Seite zusätzliche Dateien aus, die Sie als Beispiele verwenden möchten, und beschriften Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="27a41-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Klassifizierungs Homepage](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="27a41-164">Beschriften Sie mindestens fünf positive Beispiele und ein negatives Beispiel.</span><span class="sxs-lookup"><span data-stu-id="27a41-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="27a41-165">Erstellen einer Erklärung</span><span class="sxs-lookup"><span data-stu-id="27a41-165">Create an explanation</span></span>

<span data-ttu-id="27a41-166">Im nächsten Schritt erstellen Sie eine Erläuterung auf der Seite "Train".</span><span class="sxs-lookup"><span data-stu-id="27a41-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="27a41-167">Eine Erläuterung hilft dem Modell zu verstehen, wie das Dokument erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="27a41-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="27a41-168">Beispielsweise enthalten die Vertrags Erneuerungs Dokumente immer eine *Anforderung für zusätzliche Textzeichenfolge für die Offenlegung* .</span><span class="sxs-lookup"><span data-stu-id="27a41-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="27a41-169">Bei Verwendung mit Extraktoren identifiziert eine Erklärung die Zeichenfolge, die Sie aus dem Dokument extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="27a41-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="27a41-170">So erstellen Sie eine Erläuterung:</span><span class="sxs-lookup"><span data-stu-id="27a41-170">To create an explanation:</span></span>

1. <span data-ttu-id="27a41-171">Wählen Sie auf der Modell Startseite die Registerkarte **Zug** aus, um zur Seite Zug zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="27a41-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="27a41-172">Auf der Seite "Train" im Abschnitt " **geschulte Dateien** " sollte eine Liste der Beispieldateien angezeigt werden, die Sie zuvor beschriftet haben.</span><span class="sxs-lookup"><span data-stu-id="27a41-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="27a41-173">Wählen Sie eine der positiven Dateien aus der Liste aus, die im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="27a41-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="27a41-174">Wählen Sie im Abschnitt Erklärung die Option **neu** und dann **leer**aus.</span><span class="sxs-lookup"><span data-stu-id="27a41-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="27a41-175">Auf der Seite **Erklärung erstellen** :</span><span class="sxs-lookup"><span data-stu-id="27a41-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="27a41-176">a.</span><span class="sxs-lookup"><span data-stu-id="27a41-176">a.</span></span> <span data-ttu-id="27a41-177">Geben Sie den **Namen** ein (beispielsweise "Offenlegungs Block").</span><span class="sxs-lookup"><span data-stu-id="27a41-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="27a41-178">b.</span><span class="sxs-lookup"><span data-stu-id="27a41-178">b.</span></span> <span data-ttu-id="27a41-179">Wählen Sie den **Typ**aus.</span><span class="sxs-lookup"><span data-stu-id="27a41-179">Select the **Type**.</span></span> <span data-ttu-id="27a41-180">Wählen Sie für das Beispiel " **Phrase List**" aus, da Sie eine Textzeichenfolge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="27a41-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="27a41-181">c.</span><span class="sxs-lookup"><span data-stu-id="27a41-181">c.</span></span> <span data-ttu-id="27a41-182">Geben Sie im Feld **Typ hier** die Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="27a41-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="27a41-183">Fügen Sie für das Beispiel "Anforderung zusätzlicher Offenlegung" hinzu.</span><span class="sxs-lookup"><span data-stu-id="27a41-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="27a41-184">Sie können die **groß** -/Kleinschreibung beachten, wenn bei der Zeichenfolge die Groß-/Kleinschreibung beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="27a41-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="27a41-185">d.</span><span class="sxs-lookup"><span data-stu-id="27a41-185">d.</span></span> <span data-ttu-id="27a41-186">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="27a41-186">Click **Save**.</span></span>

    ![Erläuterung erstellen](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="27a41-188">Das Modell überprüft jetzt, ob die von Ihnen erstellte Erklärung gut genug ist, um die verbleibenden beschrifteten Beispieldateien ordnungsgemäß zu identifizieren, als positive und negative Beispiele.</span><span class="sxs-lookup"><span data-stu-id="27a41-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="27a41-189">Überprüfen Sie im Abschnitt ausgebildete Dateien nach Abschluss der Schulung die Spalte **Evaluierung** , um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27a41-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="27a41-190">Die Dateien zeigen einen Wert von **Match**an, wenn die von Ihnen erstellten Erklärungen genug übereinstimmen, was Sie als positiv oder negativ bezeichnet haben.</span><span class="sxs-lookup"><span data-stu-id="27a41-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Übereinstimmungs Wert](../media/content-understanding/match.png) 

<span data-ttu-id="27a41-192">Wenn Sie eine **Übereinstimmung** mit den beschrifteten Dateien erhalten, müssen Sie möglicherweise eine zusätzliche Erläuterung erstellen, um das Modell mit weiteren Informationen zum Identifizieren des Dokumenttyps zu versehen.</span><span class="sxs-lookup"><span data-stu-id="27a41-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="27a41-193">Wenn dies geschieht, klicken Sie auf die Datei, um weitere Informationen dazu zu erhalten, warum der Konflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="27a41-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="27a41-194">Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="27a41-194">Test your model</span></span>

<span data-ttu-id="27a41-195">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie Ihr Modell nun auf ihren restlichen unbeschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="27a41-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="27a41-196">Wählen Sie auf der Modell Startseite die Registerkarte **Test** aus.  Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="27a41-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="27a41-197">In der Liste **Test Dateien** werden Ihre Beispieldateien angezeigt und angezeigt, wenn das Modell Sie als positiv oder negativ prognostiziert.</span><span class="sxs-lookup"><span data-stu-id="27a41-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="27a41-198">Anhand dieser Informationen können Sie die Effektivität ihrer Klassifizierung bei der Identifizierung Ihrer Dokumente ermitteln.</span><span class="sxs-lookup"><span data-stu-id="27a41-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen von nicht beschrifteten Dateien](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="27a41-200">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27a41-200">See Also</span></span>
[<span data-ttu-id="27a41-201">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="27a41-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="27a41-202">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="27a41-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="27a41-203">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="27a41-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="27a41-204">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="27a41-204">Apply a model</span></span>](apply-a-model.md) 
