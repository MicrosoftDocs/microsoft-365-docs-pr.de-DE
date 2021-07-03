---
title: Schritt 1. Verwenden von SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Erfahren Sie, wie Sie SharePoint Syntex verwenden, um Vertragsdateien zu identifizieren und Daten mithilfe einer Microsoft 365 Lösung zu extrahieren.
ms.openlocfilehash: b73f7b96a1f1a9159770fb1bfb20bf2718f08c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287353"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="c9400-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="c9400-104">Step 1.</span></span> <span data-ttu-id="c9400-105">Verwenden von SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten</span><span class="sxs-lookup"><span data-stu-id="c9400-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="c9400-106">Ihre Organisation benötigt eine Möglichkeit, alle Vertragsdokumente aus den vielen empfangenen Dateien zu identifizieren und zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="c9400-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="c9400-107">Außerdem möchten Sie schnell mehrere wichtige Elemente in jeder der identifizierten Vertragsdateien anzeigen können (z. B. *Client,* *Auftragnehmer* und *Gebührenbetrag).*</span><span class="sxs-lookup"><span data-stu-id="c9400-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="c9400-108">Dazu können Sie [SharePoint Syntex](index.md) verwenden, um ein Dokumentverständnismodell zu erstellen und es auf eine Dokumentbibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c9400-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="c9400-109">Übersicht über den Vorgang</span><span class="sxs-lookup"><span data-stu-id="c9400-109">Overview of the process</span></span>

<span data-ttu-id="c9400-110">[Das Dokumentverständnis](document-understanding-overview.md) verwendet KI-Modelle (Künstliche Intelligenz), um die Klassifizierung von Dateien und die Extraktion von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c9400-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="c9400-111">Dokumentverständnismodelle sind auch optimal beim Extrahieren von Informationen aus unstrukturierten und halbstrukturierten Dokumenten, in denen die benötigten Informationen nicht in Tabellen oder Formularen, z. B. Verträgen, enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c9400-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span> 

<span data-ttu-id="c9400-112">Dokumentverständnismodelle nutzen die Technik der optischen Zeichenerkennung (OCR), um PDF-, Bild- und TIFF-Dateien zu scannen, und zwar sowohl beim Trainieren eines Modells mit Beispieldateien als auch beim Ausführen des Modells mit Dateien einer Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c9400-112">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

1. <span data-ttu-id="c9400-113">Zuerst müssen Sie mindestens fünf Beispieldateien finden, mit denen Sie das Modell "trainieren" können, um nach Merkmalen zu suchen, die für den zu identifizierenden Inhaltstyp (einen Vertrag) spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c9400-113">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="c9400-114">Erstellen Sie mit SharePoint Syntex ein neues Dokumentverständnismodell.</span><span class="sxs-lookup"><span data-stu-id="c9400-114">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="c9400-115">Mithilfe Ihrer Beispieldateien müssen Sie [einen Klassifizierer erstellen.](create-a-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="c9400-115">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="c9400-116">Indem Sie den Klassifizierer mit Ihren Beispieldateien schulen, lernen Sie, nach Merkmalen zu suchen, die spezifisch für die in den Verträgen Ihres Unternehmens angezeigten Merkmale sind.</span><span class="sxs-lookup"><span data-stu-id="c9400-116">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="c9400-117">Erstellen Sie beispielsweise [eine "Erklärung",](create-a-classifier.md#create-an-explanation) die nach bestimmten Zeichenfolgen sucht, die in Ihren Verträgen enthalten sind, z. B. *Servicevertrag,* *Vertragsbedingungen* und *Vergütung.*</span><span class="sxs-lookup"><span data-stu-id="c9400-117">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="c9400-118">Sie können ihre Erklärung sogar trainieren, um nach diesen Zeichenfolgen in bestimmten Abschnitten des Dokuments zu suchen oder sich neben anderen Zeichenfolgen zu befinden.</span><span class="sxs-lookup"><span data-stu-id="c9400-118">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="c9400-119">Wenn Sie der Meinung sind, dass Sie Ihren Klassifizierer mit den benötigten Informationen geschult haben, können Sie Ihr Modell anhand einer Beispielgruppe von Beispieldateien testen, um zu sehen, wie effizient er ist.</span><span class="sxs-lookup"><span data-stu-id="c9400-119">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="c9400-120">Nach dem Testen können Sie bei Bedarf Änderungen an Ihren Erläuterungen vornehmen, um sie effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="c9400-120">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="c9400-121">In Ihrem Modell können Sie [einen Extraktor erstellen,](create-an-extractor.md) um bestimmte Datenelemente aus jedem Vertrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c9400-121">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="c9400-122">Für jeden Vertrag sind beispielsweise die Informationen, um die Sie sich am meisten sorgen, die Person, die der Kunde ist, der Name des Vertrags und die Gesamtkosten.</span><span class="sxs-lookup"><span data-stu-id="c9400-122">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="c9400-123">Nachdem Sie das Modell erfolgreich erstellt haben, wenden Sie [es auf eine SharePoint Dokumentbibliothek an.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="c9400-123">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="c9400-124">Beim Hochladen von Dokumenten in die Dokumentbibliothek wird Ihr Dokumentverständnismodell ausgeführt und identifiziert und klassifiziert alle Dateien, die dem in Ihrem Modell definierten Vertragsinhaltstyp entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c9400-124">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="c9400-125">Alle Dateien, die als Verträge klassifiziert sind, werden in einer benutzerdefinierten Bibliotheksansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9400-125">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="c9400-126">Die Dateien zeigen auch die Werte aus jedem Vertrag an, den Sie in Ihrem Extraktor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="c9400-126">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Verträge in dokumentbibliothek](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="c9400-128">Wenn Sie Aufbewahrungs- oder Sicherheitsanforderungen für Ihre Verträge haben, können Sie Ihr Modell auch verwenden, um eine [Aufbewahrungsbezeichnung](apply-a-retention-label-to-a-model.md) oder eine [Vertraulichkeitsbezeichnung](apply-a-sensitivity-label-to-a-model.md) anzuwenden, die verhindert, dass Ihre Verträge für einen bestimmten Zeitraum gelöscht werden, oder um einzuschränken, wer auf die Verträge zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c9400-128">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="c9400-129">Schritte zum Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="c9400-129">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="c9400-130">Für diese Schritte können Sie die Beispieldateien im [Repository "Contracts Management Solution Assets"](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9400-130">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="c9400-131">Die Beispiele in diesem Repository enthalten sowohl die Dokumentverständnismodelldateien als auch die Dateien, die zum Trainieren des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9400-131">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="c9400-132">Erstellen eines Vertragsmodells</span><span class="sxs-lookup"><span data-stu-id="c9400-132">Create a Contract model</span></span>

<span data-ttu-id="c9400-133">Der erste Schritt besteht darin, Das Vertragsmodell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9400-133">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="c9400-134">Wählen Sie im Inhaltscenter **Neu** aus, und dann **Modell erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c9400-134">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="c9400-135">Geben Sie im **Modellbereich "Neues Dokumentverständnis"** im Feld **"Name"** den Namen des Modells ein.</span><span class="sxs-lookup"><span data-stu-id="c9400-135">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="c9400-136">Für diese Vertragsverwaltungslösung können Sie das Modell *"Vertrag"* benennen.</span><span class="sxs-lookup"><span data-stu-id="c9400-136">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="c9400-137">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c9400-137">Choose **Create**.</span></span> <span data-ttu-id="c9400-138">Dadurch wird eine Homepage für das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="c9400-138">This creates a home page for the model.</span></span></br>

    ![Screenshot der Startseite des Vertrags.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="c9400-140">Trainieren Des Modells zum Klassifizieren eines Dateityps</span><span class="sxs-lookup"><span data-stu-id="c9400-140">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="c9400-141">Hinzufügen von Beispieldateien für Ihr Modell</span><span class="sxs-lookup"><span data-stu-id="c9400-141">Add example files for your model</span></span>

<span data-ttu-id="c9400-142">Sie müssen mindestens fünf Beispieldateien hinzufügen, bei denen es sich um Vertragsdokumente handelt, und eine Beispieldatei, bei der es sich nicht um ein Vertragsdokument handelt (z. B. eine Arbeitserklärung).</span><span class="sxs-lookup"><span data-stu-id="c9400-142">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="c9400-143">On the **Models > Contract** page, under Key **actions** Add  >  **example files,** select Add **files**.</span><span class="sxs-lookup"><span data-stu-id="c9400-143">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Screenshot der Seite "Verträge" mit hervorgehobener Option "Beispieldateien hinzufügen".](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="c9400-145">Öffnen Sie auf der Seite **"Beispieldateien für Ihr Modell auswählen"** den Ordner "Vertrag", wählen Sie dateien aus, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-145">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="c9400-146">Wenn Sie dort keine Beispieldateien haben, wählen Sie **Hochladen** aus, um sie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9400-146">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="c9400-147">Beschriften Sie die Dateien als positive oder negative Beispiele</span><span class="sxs-lookup"><span data-stu-id="c9400-147">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="c9400-148">Wählen Sie auf der Seite **"Modelle > Vertrag"** unter **"Schlüsselaktionen**  >  **Dateien klassifizieren" und "Schulung ausführen"** die Option **"Klassifizierer trainieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-148">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Screenshot der Seite "Verträge" mit hervorgehobener Option "Dateien klassifizieren" und "Training ausführen".](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="c9400-150">Auf der Seite **"Modelle > Vertrag > Vertragsklassifizierung"** wird im Viewer oben in der ersten Beispieldatei Text angezeigt, in dem Sie gefragt werden, ob die Datei ein Beispiel für das von Ihnen erstellte Vertragsmodell ist.</span><span class="sxs-lookup"><span data-stu-id="c9400-150">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="c9400-151">Wenn es sich um ein positives Beispiel handelt, wählen Sie **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-151">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="c9400-152">Wenn es sich um ein negatives Beispiel handelt, wählen Sie **Nein** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-152">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="c9400-153">Wählen Sie in der Liste **mit bezeichnungsierten Beispielen** auf der linken Seite andere Dateien aus, die Sie als Beispiele verwenden möchten, und bezeichnen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="c9400-153">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Homepage des Klassifizierers](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;c9400-155&quot;>Fügen Sie mindestens eine Erklärung hinzu, um den Klassifizierer zu trainieren.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-155&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;c9400-156&quot;>Wählen Sie auf der Seite **&quot;Modelle > Vertrag > Klassifizierer&quot;** die Registerkarte **&quot;Trainieren&quot;** aus.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-156&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;c9400-157&quot;>Im Abschnitt **&quot;Trainierte Dateien&quot;** wird eine Liste der Beispieldateien angezeigt, die Sie zuvor bezeichnet haben.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-157&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;c9400-158&quot;>Wählen Sie eine der positiven Dateien aus der Liste aus, um sie im Viewer anzuzeigen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-158&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;c9400-159&quot;>Wählen Sie im Abschnitt **&quot;Erklärungen&quot;** die Option **&quot;Neu&quot;** und dann **&quot;Leer&quot;** aus.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-159&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;c9400-160&quot;>Auf der Seite **Erklärung erstellen**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-160&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;c9400-161&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-161&quot;>a.</span></span> <span data-ttu-id=&quot;c9400-162&quot;>Geben Sie im **Feld &quot;Name&quot;** den Namen der Erklärung ein (z. B. &quot;Vereinbarung").</span><span class="sxs-lookup"><span data-stu-id="c9400-162">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="c9400-163">b.</span><span class="sxs-lookup"><span data-stu-id="c9400-163">b.</span></span> <span data-ttu-id="c9400-164">Wählen Sie im Feld **"Erklärungstyp"** **die Begriffsliste** aus, da Sie eine Textzeichenfolge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9400-164">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="c9400-165">c.</span><span class="sxs-lookup"><span data-stu-id="c9400-165">c.</span></span> <span data-ttu-id="c9400-166">Geben Sie im **Listenfeld Phrase** die Zeichenfolge ein (z. B. "AGREEMENT").</span><span class="sxs-lookup"><span data-stu-id="c9400-166">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="c9400-167">Sie können die **Groß-/Kleinschreibung** auswählen, wenn bei der Zeichenfolge die Groß-/Kleinschreibung beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c9400-167">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="c9400-168">d.</span><span class="sxs-lookup"><span data-stu-id="c9400-168">d.</span></span> <span data-ttu-id="c9400-169">Wählen Sie **"Speichern" und "Trainieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-169">Select **Save and train**.</span></span>

    ![Screenshot des Bereichs "Erklärung erstellen".](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="c9400-171">Ihr Modell testen</span><span class="sxs-lookup"><span data-stu-id="c9400-171">Test your model</span></span>

<span data-ttu-id="c9400-172">Sie können Ihr Vertragsmodell mit Beispieldateien testen, die es noch nicht gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="c9400-172">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="c9400-173">Dies ist optional, kann aber eine nützliche bewährte Methode sein.</span><span class="sxs-lookup"><span data-stu-id="c9400-173">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="c9400-174">Wählen Sie auf der Seite **"Modelle > Vertrag > Vertragsklassifizierung"** die Registerkarte **"Test"** aus. Dadurch wird das Modell für ihre nicht bezeichneten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c9400-174">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="c9400-175">In der Liste **"Testdateien"** werden die Beispieldateien angezeigt und angezeigt, ob das Modell sie als positiv oder negativ vorausgesagt hat.</span><span class="sxs-lookup"><span data-stu-id="c9400-175">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="c9400-176">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="c9400-176">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Screenshot der nicht bezeichneten Dateien in der Liste "Textdateien"](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="c9400-178">Wenn Sie fertig sind, wählen Sie **"Schulung beenden" aus.**</span><span class="sxs-lookup"><span data-stu-id="c9400-178">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="c9400-179">Erstellen und Trainieren eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="c9400-179">Create and train an extractor</span></span>

1. <span data-ttu-id="c9400-180">Wählen Sie auf der Seite **"Modelle > Vertrag"** unter **"Wichtige Aktionen**  >  **Erstellen und Trainieren von Extraktoren"** die Option **"Extraktor erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-180">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Screenshot der Seite "Verträge" mit hervorgehobener Option "Extraktoren erstellen und trainieren".](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="c9400-182">Geben Sie im Feld **Neuer Entitätsextraktionsmodul** im Feld **Neuer** Name den Namen des Extraktors ein.</span><span class="sxs-lookup"><span data-stu-id="c9400-182">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="c9400-183">Nennen Sie ihn beispielsweise *Client,* wenn Sie den Namen des Clients aus jedem Vertrag extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c9400-183">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="c9400-184">Wenn Sie fertig sind, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-184">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="c9400-185">Beschriften Sie die Entität, die Sie extrahieren möchten</span><span class="sxs-lookup"><span data-stu-id="c9400-185">Label the entity you want to extract</span></span>

<span data-ttu-id="c9400-186">Wenn Sie den Extraktor erstellen, wird die Extraktorseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c9400-186">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="c9400-187">Dort sehen Sie eine Liste Ihrer Beispieldateien, wobei die erste Datei auf der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c9400-187">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Screenshot der Seite "Beispiele für Clientextraktionsmodul mit Bezeichnungen".](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="c9400-189&quot;>So bezeichnen Sie die Entität:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-189&quot;>To label the entity:</span></span>

1. <span data-ttu-id=&quot;c9400-190&quot;>Wählen Sie im Viewer die Daten, die aus den Dateien extrahiert werden sollen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c9400-190&quot;>From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id=&quot;c9400-191&quot;>Wenn Sie z. B. den *Client* extrahieren möchten, markieren Sie den Clientwert in der ersten Datei (in diesem Beispiel *&quot;Best For You Organics"),* und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-191">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="c9400-192">Sie sehen den Wert, der aus der Datei in der Liste **der bezeichneten Beispiele** unter der Spalte **"Bezeichnung"** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c9400-192">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="c9400-193">Wählen Sie **"Nächste Datei"** aus, um die nächste Datei automatisch zu speichern und die nächste Datei in der Liste im Viewer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c9400-193">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="c9400-194">Oder wählen Sie **"Speichern"** aus, und wählen Sie dann eine andere Datei aus der Liste **der beschrifteten Beispiele** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-194">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="c9400-195">Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie dann, bis Sie die Bezeichnung in allen Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="c9400-195">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="c9400-196">Nachdem Sie die Dateien beschriftet haben, wird ein Benachrichtigungsbanner angezeigt, das Sie informiert, zum Training zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="c9400-196">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="c9400-197">Sie können auswählen, ob Sie weitere Dokumente bezeichnen oder mit dem Training fortsteigen möchten.</span><span class="sxs-lookup"><span data-stu-id="c9400-197">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="c9400-198">Hinzufügen einer Erläuterung</span><span class="sxs-lookup"><span data-stu-id="c9400-198">Add an explanation</span></span>

<span data-ttu-id="c9400-199">Sie können eine Erklärung erstellen, die einen Hinweis auf das Entitätsformat selbst und mögliche Variationen in den Beispieldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="c9400-199">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="c9400-200">Beispielsweise kann ein Datumswert in vielen verschiedenen Formaten vorliegen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="c9400-200">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="c9400-201">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="c9400-201">10/14/2019</span></span>
- <span data-ttu-id="c9400-202">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="c9400-202">October 14, 2019</span></span>
- <span data-ttu-id="c9400-203">Montag, 14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="c9400-203">Monday, October 14, 2019</span></span>

<span data-ttu-id="c9400-204">Um das *Startdatum* des Vertrags zu identifizieren, können Sie eine Mustererklärung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9400-204">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="c9400-205">Wählen Sie im Abschnitt **"Erklärungen"** die Option **"Neu"** und dann **"Leer"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-205">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="c9400-206">Auf der Seite **Erklärung erstellen**:</span><span class="sxs-lookup"><span data-stu-id="c9400-206">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="c9400-207">a.</span><span class="sxs-lookup"><span data-stu-id="c9400-207">a.</span></span> <span data-ttu-id="c9400-208">Geben Sie im **Feld "Name"** den Namen der Erklärung ein (z. *B. Datum).*</span><span class="sxs-lookup"><span data-stu-id="c9400-208">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="c9400-209">b.</span><span class="sxs-lookup"><span data-stu-id="c9400-209">b.</span></span> <span data-ttu-id="c9400-210">Wählen Sie im Feld **Erklärungstyp** **die Liste Muster** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-210">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="c9400-211">c.</span><span class="sxs-lookup"><span data-stu-id="c9400-211">c.</span></span> <span data-ttu-id="c9400-212">Geben Sie im **Feld Wert** die Datumsvariation an, wie sie in den Beispieldateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9400-212">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="c9400-213">Wenn Sie z. B. Daten im Format 0/00/0000 haben, geben Sie sämtliche Varianten ein, die in Ihren Dokumenten angezeigt werden, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="c9400-213">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="c9400-214">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="c9400-214">0/0/0000</span></span>
    - <span data-ttu-id="c9400-215">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="c9400-215">0/00/0000</span></span>
    - <span data-ttu-id="c9400-216">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="c9400-216">00/0/0000</span></span>
    - <span data-ttu-id="c9400-217">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="c9400-217">00/00/0000</span></span>

4. <span data-ttu-id="c9400-218">Wählen Sie **"Speichern" und "Trainieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-218">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="c9400-219">Testen Sie Ihr Modell erneut</span><span class="sxs-lookup"><span data-stu-id="c9400-219">Test your model again</span></span>

<span data-ttu-id="c9400-220">Sie können Ihr Vertragsmodell mit Beispieldateien testen, die es noch nicht gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="c9400-220">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="c9400-221">Dies ist optional, kann aber eine nützliche bewährte Methode sein.</span><span class="sxs-lookup"><span data-stu-id="c9400-221">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="c9400-222">Wählen Sie auf der Seite **"Modelle > Vertrag > Vertragsklassifizierung"** die Registerkarte **"Test"** aus. Dadurch wird das Modell für ihre nicht bezeichneten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c9400-222">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="c9400-223">In der Liste **"Testdateien"** werden die Beispieldateien angezeigt, und es wird angezeigt, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="c9400-223">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="c9400-224">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="c9400-224">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="c9400-225">Wenn Sie fertig sind, wählen Sie **"Schulung beenden" aus.**</span><span class="sxs-lookup"><span data-stu-id="c9400-225">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="c9400-226">Anwenden ihres Modells auf eine Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="c9400-226">Apply your model to a document library</span></span>

<span data-ttu-id="c9400-227">So wenden Sie Ihr Modell auf eine SharePoint Dokumentbibliothek an:</span><span class="sxs-lookup"><span data-stu-id="c9400-227">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="c9400-228">Wählen Sie auf der Seite **"Modelle > Vertrag"** unter **"Schlüsselaktionen**  >  **Modell auf Bibliotheken anwenden"** die Option **"Modell anwenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-228">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Screenshot der Seite "Verträge" mit hervorgehobener Option "Modell auf Bibliotheken anwenden".](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="c9400-230">Wählen Sie im Bereich **"Vertrag hinzufügen"** die SharePoint Website aus, die die Dokumentbibliothek enthält, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9400-230">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="c9400-231">Wenn die Website in der Liste nicht angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</span><span class="sxs-lookup"><span data-stu-id="c9400-231">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="c9400-232">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c9400-232">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9400-233">Sie müssen über die Berechtigung *Listen verwalten* oder *Bearbeiten* für die Dokumentbibliothek verfügen, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9400-233">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="c9400-234">Nachdem Sie die Website ausgewählt haben, wählen Sie die Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9400-234">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="c9400-235">Da das Modell einem Inhaltstyp zugeordnet ist, fügt es, wenn Sie es auf die Bibliothek anwenden, den Inhaltstyp und seine Ansicht mit den extrahierten Bezeichnungen hinzu, die als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9400-235">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="c9400-236">Diese Ansicht ist standardmäßig die Standardansicht der Bibliothek. Optional können Sie jedoch festlegen, dass es sich nicht um die Standardansicht handelt, indem Sie **die erweiterten Einstellungen** auswählen und das **Kontrollkästchen "Neue Ansicht als Standard** festlegen" deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9400-236">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="c9400-237">Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c9400-237">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="c9400-238">Auf der Seite **"Modelle > Vertrag"** wird im Abschnitt **"Bibliotheken mit diesem Modell"** die URL zur SharePoint Website aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c9400-238">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Screenshot der Startseite "Vertrag" mit den Bibliotheken mit diesem Modellabschnitt.](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="c9400-240">Unter **Einstellungen**  >  **Bibliothekseinstellungen:**</span><span class="sxs-lookup"><span data-stu-id="c9400-240">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="c9400-241">Fügen Sie eine Spalte mit dem Namen **Status hinzu,** und wählen Sie **"Auswahl"** als Spaltentyp aus.</span><span class="sxs-lookup"><span data-stu-id="c9400-241">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="c9400-242">Wenden Sie die Werte **"In",** **"Genehmigt"** und **"Abgelehnt"** an.</span><span class="sxs-lookup"><span data-stu-id="c9400-242">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="c9400-243">Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c9400-243">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="c9400-244">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c9400-244">Next step</span></span>

[<span data-ttu-id="c9400-245">Schritt 2. Verwenden von Microsoft Teams zum Erstellen Ihres Vertragsverwaltungskanals</span><span class="sxs-lookup"><span data-stu-id="c9400-245">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)