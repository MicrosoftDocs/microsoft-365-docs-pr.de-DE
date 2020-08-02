---
title: Erstellen einer Klassifizierung (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Erstellen einer Klassifizierung
ms.openlocfilehash: 029ac16310f8e95a69a713896b1109a778eb3b8d
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537220"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="5dca8-103">Erstellen einer Klassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="5dca8-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="5dca8-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="5dca8-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="5dca8-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="5dca8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="5dca8-106">Eine Klassifizierung ist ein Modelltyp, der die Identifizierung und Klassifizierung eines Dokumenttyps automatisiert.</span><span class="sxs-lookup"><span data-stu-id="5dca8-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="5dca8-107">Beispielsweise können Sie alle *Vertrags Erneuerungs* Dokumente identifizieren, die Ihrer Dokumentbibliothek hinzugefügt werden, beispielsweise die folgenden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Vertrags Erneuerungs Dokument](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="5dca8-109">Durch das Erstellen einer Klassifizierung wird ein neuer [SharePoint-Inhaltstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) erstellt, der dem Modell zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="5dca8-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="5dca8-110">Beim Erstellen der Klassifizierung müssen Sie *Erläuterungen* erstellen, mit denen das Modell definiert wird, indem Sie allgemeine Daten notieren, die Sie für diesen Dokumenttyp einheitlich finden würden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="5dca8-111">Sie verwenden Beispiele für den Dokumenttyp ("Beispieldateien"), um Ihr Modell zu unterstützen, um Dateien mit dem gleichen Inhaltstyp zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5dca8-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="5dca8-112">Um eine Klassifizierung zu erstellen, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="5dca8-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="5dca8-113">Benennen Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="5dca8-113">Name your model</span></span>
2. <span data-ttu-id="5dca8-114">Hinzufügen von Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="5dca8-114">Add your example files</span></span>
3. <span data-ttu-id="5dca8-115">Bezeichnen der Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="5dca8-115">Label your example files</span></span>
4. <span data-ttu-id="5dca8-116">Erstellen einer Erklärung</span><span class="sxs-lookup"><span data-stu-id="5dca8-116">Create an explanation</span></span>
5. <span data-ttu-id="5dca8-117">Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="5dca8-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="5dca8-118">Während eine Klassifizierung von Ihrem Modell zum Identifizieren und Klassifizieren von Dokumenttypen verwendet wird, können Sie auch auswählen, dass bestimmte Informationen aus jeder Datei abgerufen werden, die vom Modell identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="5dca8-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="5dca8-119">Erstellen Sie dazu einen **Extraktor** , der zu Ihrem Modell hinzugefügt werden soll, und dies wird unter [Create a Extractor](create-an-extractor.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5dca8-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="5dca8-120">Benennen Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="5dca8-120">Name your model</span></span>

<span data-ttu-id="5dca8-121">Der erste Schritt besteht darin, Ihr Modell im Inhalts Center zu erstellen, indem Sie ihm einen Namen geben:</span><span class="sxs-lookup"><span data-stu-id="5dca8-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="5dca8-122">Klicken Sie in Ihrem Inhalts Center auf **neu**, und klicken Sie dann auf **Modell erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="5dca8-123">Geben Sie im **neuen Dokument grundlegendes Modell** im Feld **Name** den Namen des Modells ein.</span><span class="sxs-lookup"><span data-stu-id="5dca8-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="5dca8-124">Wenn wir zum Beispiel Vertrags Erneuerungs Dokumente identifizieren möchten, können wir diese Modell *Vertragserneuerung*nennen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="5dca8-125">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-125">Click **Create**.</span></span> <span data-ttu-id="5dca8-126">Dadurch wird eine Startseite für das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="5dca8-126">This will create a home page for the model.</span></span></br>

    ![Klassifizierungsmodell-Startseite](../media/content-understanding/model-home.png)

<span data-ttu-id="5dca8-128">Wenn Sie ein Modell erstellen, erstellen Sie einen neuen SharePoint-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="5dca8-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="5dca8-129">Ein SharePoint-Inhaltstyp stellt eine Kategorie von Dokumenten dar, die allgemeine Merkmale aufweisen und eine Auflistung von Spalten oder Metadaten-Eigenschaften für diesen bestimmten Inhalt gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="5dca8-130">SharePoint-Inhaltstypen werden über den [Inhaltstypen Katalog]()verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5dca8-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="5dca8-131">Für unser Beispiel wird beim Erstellen des Modells ein neuer Inhaltstyp für die *Vertragserneuerung* erstellt.</span><span class="sxs-lookup"><span data-stu-id="5dca8-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="5dca8-132">Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Inhaltstyp im SharePoint-Inhaltstypen Katalog zuordnen möchten, um sein Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="5dca8-133">Beachten Sie, dass Sie zwar einen vorhandenen Inhaltstyp verwenden können, um sein Schema zur Unterstützung bei der Identifizierung und Klassifizierung zu nutzen, aber Sie müssen Ihr Modell dennoch trainieren, um Informationen aus den identifizierten Dateien zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="5dca8-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Erweiterte Einstellungen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="5dca8-135">Hinzufügen von Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="5dca8-135">Add your example files</span></span>

<span data-ttu-id="5dca8-136">Auf der Modell Homepage können Sie Ihre Beispieldateien hinzufügen, die Sie bei der Schulung des Modells zur Identifizierung Ihres Dokumenttyps unterstützen müssen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="5dca8-137">Die gleichen Dateien sollten sowohl für die Klassifizierung als auch für [Extraktions Schulungen](create-an-extractor.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="5dca8-138">Sie haben immer die Option, später hinzuzufügen, aber in der Regel sollten Sie einen vollständigen Reihe von Beispieldateien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="5dca8-139">Sie bezeichnen einige zur Schulung Ihres Modells und testen die restlichen unbeschrifteten, um die Modell Eignung auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="5dca8-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="5dca8-140">Für Ihr Schulungspaket sollten Sie sowohl positive Beispiele als auch negative Beispiele verwenden:</span><span class="sxs-lookup"><span data-stu-id="5dca8-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="5dca8-141">Positives Beispiel: Dokumente, die den Dokumenttyp darstellen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="5dca8-142">Sie enthalten Zeichenfolgen und Informationen, die immer in dieser Art von Dokument sein würden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="5dca8-143">Negatives Beispiel: Dokumente, die nicht den Dokumenttyp darstellen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="5dca8-144">Es fehlen Zeichenfolgen und Informationen, die in dieser Art von Dokument vorhanden sein müssen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="5dca8-145">Sie sollten mindestens fünf positive Beispiele und ein negatives Beispiel zur Schulung Ihres Modells verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dca8-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="5dca8-146">Sie benötigen zusätzliche, um Ihr Modell nach dem Training zu testen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="5dca8-147">So fügen Sie Beispieldateien hinzu:</span><span class="sxs-lookup"><span data-stu-id="5dca8-147">To add sample files:</span></span>

1. <span data-ttu-id="5dca8-148">Klicken Sie auf der Modell Startseite in der Kachel **Beispielbibliothek erstellen** auf **Dateien hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="5dca8-149">Wählen Sie auf der Seite **Beispieldateien für Ihr Modell auswählen** ihre Beispieldateien aus der Bibliothek Beispieldateien im Inhalts Center aus.</span><span class="sxs-lookup"><span data-stu-id="5dca8-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="5dca8-150">Wenn Sie Sie nicht bereits hochgeladen haben, können Sie Sie jetzt hochladen, indem Sie auf **hochladen** klicken, um Sie in die Beispieldatei Bibliothek zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="5dca8-151">Nachdem Sie Ihre Beispieldateien ausgewählt haben, die zum Trainieren des Modells verwendet werden sollen, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Auswählen von Beispieldateien](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="5dca8-153">Bezeichnen der Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="5dca8-153">Label your example files</span></span>

<span data-ttu-id="5dca8-154">Nachdem Sie Ihre Beispieldateien hinzugefügt haben, müssen Sie Sie als positive Beispiele oder negative Beispiele bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="5dca8-155">Klicken Sie auf der Modell Homepage auf der Kachel **Dateien klassifizieren und Schulungsverlauf ausführen** auf **Klassifizierung Klassifizierer**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="5dca8-156">Dadurch wird die Bezeichnungs Seite angezeigt, auf der eine Liste der Beispieldateien angezeigt wird, wobei die erste Datei im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5dca8-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="5dca8-157">Im Viewer wird am Anfang der ersten Beispieldatei der Text angezeigt, in dem Sie gefragt werden, ob es sich bei der Datei um ein Beispiel des soeben erstellten Modells handelt.</span><span class="sxs-lookup"><span data-stu-id="5dca8-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="5dca8-158">Wenn es sich um ein positives Beispiel handelt, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="5dca8-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="5dca8-159">Wenn es sich um ein negatives Beispiel handelt, wählen Sie **Nein**aus.</span><span class="sxs-lookup"><span data-stu-id="5dca8-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="5dca8-160">Wählen Sie in der Liste mit den **beschrifteten Beispielen** auf der linken Seite zusätzliche Dateien aus, die Sie als Beispiele verwenden möchten, und beschriften Sie diese ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="5dca8-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Klassifizierungsmodell-Startseite](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="5dca8-162">Beschriften Sie mindestens fünf positive Beispiele und ein negatives Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5dca8-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="5dca8-163">Erstellen einer Erklärung</span><span class="sxs-lookup"><span data-stu-id="5dca8-163">Create an explanation</span></span>

<span data-ttu-id="5dca8-164">Der nächste Schritt besteht darin, eine Erläuterung auf der Seite "Train" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="5dca8-165">Eine Erklärung ist ein Hinweis oder Anhaltspunkt, um dem Modell zu helfen, zu verstehen, wie dieses Dokument erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="5dca8-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="5dca8-166">Beispielsweise enthalten unsere Vertrags Erneuerungs Dokumente immer eine *Anforderung für zusätzliche Textzeichenfolge für die Offenlegung* .</span><span class="sxs-lookup"><span data-stu-id="5dca8-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="5dca8-167">Bei Verwendung mit Extraktoren wird eine Erläuterung verwendet, um die Zeichenfolge zu identifizieren, die Sie aus dem Dokument extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5dca8-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="5dca8-168">So erstellen Sie eine Erläuterung:</span><span class="sxs-lookup"><span data-stu-id="5dca8-168">To create an explanation:</span></span>

1. <span data-ttu-id="5dca8-169">Klicken Sie auf der Modell Startseite auf die Registerkarte **Zug** , um zur Seite Zug zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="5dca8-170">Auf der Seite "Train" im Abschnitt " **geschulte Dateien** " wird eine Liste der Beispieldateien angezeigt, die Sie zuvor beschriftet hatten.</span><span class="sxs-lookup"><span data-stu-id="5dca8-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="5dca8-171">Wählen Sie eine der positiven Dateien aus der Liste aus, die im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5dca8-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="5dca8-172">Klicken Sie im Abschnitt Erläuterung auf **neu**, und klicken Sie dann auf **leer**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="5dca8-173">Auf der Seite **Erklärung erstellen** :</span><span class="sxs-lookup"><span data-stu-id="5dca8-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="5dca8-174">a.</span><span class="sxs-lookup"><span data-stu-id="5dca8-174">a.</span></span> <span data-ttu-id="5dca8-175">Geben Sie den **Namen** ein (beispielsweise "Offenlegungs Block").</span><span class="sxs-lookup"><span data-stu-id="5dca8-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="5dca8-176">b.</span><span class="sxs-lookup"><span data-stu-id="5dca8-176">b.</span></span> <span data-ttu-id="5dca8-177">Wählen Sie den **Typ**aus.</span><span class="sxs-lookup"><span data-stu-id="5dca8-177">Select the **Type**.</span></span> <span data-ttu-id="5dca8-178">Für unser Beispiel wählen wir " **Phrase List**" aus, da wir eine Textzeichenfolge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="5dca8-179">c.</span><span class="sxs-lookup"><span data-stu-id="5dca8-179">c.</span></span> <span data-ttu-id="5dca8-180">Geben Sie im Feld **Typ hier** die Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="5dca8-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="5dca8-181">Für unser Beispiel fügen wir "Anforderung zusätzlicher Offenlegung" hinzu.</span><span class="sxs-lookup"><span data-stu-id="5dca8-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="5dca8-182">Sie können die **groß** -/Kleinschreibung beachten, wenn bei der Zeichenfolge die Groß-/Kleinschreibung beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5dca8-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="5dca8-183">d.</span><span class="sxs-lookup"><span data-stu-id="5dca8-183">d.</span></span> <span data-ttu-id="5dca8-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5dca8-184">Click **Save**.</span></span>

    ![Erläuterung erstellen](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="5dca8-186">Das Modell überprüft nun, ob die von Ihnen erstellte Erklärung gut genug ist, um die verbleibenden beschrifteten Beispieldateien ordnungsgemäß als positive und negative Beispiele zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5dca8-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="5dca8-187">Überprüfen Sie im Abschnitt ausgebildete Dateien nach Abschluss der Schulung die Spalte **Auswertung** , um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="5dca8-188">Die Dateien zeigen den Wert **Match** an, wenn die von Ihnen erstellte Erklärung genug entspricht, was Sie als (positiv oder negativ) bezeichnet haben.</span><span class="sxs-lookup"><span data-stu-id="5dca8-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Erläuterung erstellen](../media/content-understanding/match.png) 

<span data-ttu-id="5dca8-190">Wenn Sie eine **Übereinstimmung** bei ihren beschrifteten Dateien erhalten, müssen Sie möglicherweise eine zusätzliche Erläuterung erstellen, um das Modell mit weiteren Informationen zum Identifizieren des Dokumenttyps zu versehen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="5dca8-191">Sie können auf die Datei klicken, um weitere Informationen dazu zu erhalten, warum der Konflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5dca8-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="5dca8-192">Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="5dca8-192">Test your model</span></span>

<span data-ttu-id="5dca8-193">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie Ihr Modell nun auf ihren restlichen unbeschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="5dca8-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="5dca8-194">Klicken Sie auf der Modell Startseite auf die Registerkarte **Test** .  Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5dca8-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="5dca8-195">In der Liste **Test Dateien** werden Ihre Beispieldateien angezeigt, und es wird angezeigt, ob das Modell positive oder negative Beispiele vorausgesagt hat.</span><span class="sxs-lookup"><span data-stu-id="5dca8-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="5dca8-196">Anhand dieser Informationen können Sie die Effektivität ihrer Klassifizierung bei der Identifizierung Ihrer Dokumente ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5dca8-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen von nicht beschrifteten Dateien](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="5dca8-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dca8-198">See Also</span></span>
[<span data-ttu-id="5dca8-199">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="5dca8-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="5dca8-200">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="5dca8-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="5dca8-201">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="5dca8-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="5dca8-202">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="5dca8-202">Apply a model</span></span>](apply-a-model.md) 




