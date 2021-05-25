---
title: Schritt 1. Verwenden SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten
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
description: Erfahren Sie, wie Sie SharePoint Syntex verwenden, um Vertragsdateien zu identifizieren und Daten mithilfe einer Microsoft 365 extrahieren.
ms.openlocfilehash: b4b11b1bdb980b0ee7629af0cbecbb126a5ae5e5
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636206"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="f07e9-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="f07e9-104">Step 1.</span></span> <span data-ttu-id="f07e9-105">Verwenden SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten</span><span class="sxs-lookup"><span data-stu-id="f07e9-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="f07e9-106">Ihre Organisation benötigt eine Möglichkeit, alle Vertragsdokumente aus den vielen empfangenen Dateien zu identifizieren und zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="f07e9-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="f07e9-107">Sie möchten auch in der Lage sein, schnell mehrere Schlüsselelemente in jeder der identifizierten Vertragsdateien (z. B. *Client,* *Auftragnehmer* und *Gebührenbetrag) anzeigen zu können.*</span><span class="sxs-lookup"><span data-stu-id="f07e9-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="f07e9-108">Verwenden Sie dazu SharePoint [Syntex,](index.md) um ein Dokumentverständnismodell zu erstellen und es auf eine Dokumentbibliothek zu anwenden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="f07e9-109">Übersicht über den Vorgang</span><span class="sxs-lookup"><span data-stu-id="f07e9-109">Overview of the process</span></span>

<span data-ttu-id="f07e9-110">[Zur Dokumenterteilung](document-understanding-overview.md) werden KI-Modelle (Artificial Intelligence) verwendet, um die Klassifizierung von Dateien und die Extraktion von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="f07e9-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="f07e9-111">Dokumentverständnismodelle sind auch optimal beim Extrahieren von Informationen aus unstrukturierten und semistrukturierten Dokumenten, bei denen die benötigten Informationen nicht in Tabellen oder Formularen enthalten sind, z. B. Verträgen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="f07e9-112">Zunächst müssen Sie mindestens fünf Beispieldateien finden, mit deren Hilfe Sie das Modell "schulen" können, um nach Merkmalen zu suchen, die spezifisch für den Inhaltstyp sind, den Sie identifizieren möchten (ein Vertrag).</span><span class="sxs-lookup"><span data-stu-id="f07e9-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="f07e9-113">Erstellen SharePoint Syntex ein neues Dokumentverständnismodell.</span><span class="sxs-lookup"><span data-stu-id="f07e9-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="f07e9-114">Mithilfe Ihrer Beispieldateien müssen Sie [einen Klassifikator erstellen.](create-a-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="f07e9-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="f07e9-115">Indem Sie den Klassifikator mit Ihren Beispieldateien trainieren, vermitteln Sie ihm, nach Merkmalen zu suchen, die speziell für die Verträge Ihres Unternehmens spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="f07e9-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="f07e9-116">Erstellen Sie beispielsweise [eine "Erläuterung",](create-a-classifier.md#create-an-explanation) die nach bestimmten Zeichenfolgen in Ihren Verträgen sucht, z. B. *Servicevertrag,* Vertragsbedingungen *und* *Vergütung.*</span><span class="sxs-lookup"><span data-stu-id="f07e9-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="f07e9-117">Sie können Ihre Erklärung sogar so schulen, dass sie in bestimmten Abschnitten des Dokuments oder neben anderen Zeichenfolgen nach diesen Zeichenfolgen sucht.</span><span class="sxs-lookup"><span data-stu-id="f07e9-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="f07e9-118">Wenn Sie denken, Dass Sie Ihren Klassifikator mit den benötigten Informationen geschult haben, können Sie Ihr Modell in einem Beispielsatz von Beispieldateien testen, um zu sehen, wie effizient es ist.</span><span class="sxs-lookup"><span data-stu-id="f07e9-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="f07e9-119">Nach dem Testen können Sie bei Bedarf Änderungen an Ihren Erläuterungen vornehmen, um sie effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="f07e9-120">In Ihrem Modell können Sie einen [Extractor](create-an-extractor.md) erstellen, um bestimmte Datenteile aus jedem Vertrag herausziehen zu können.</span><span class="sxs-lookup"><span data-stu-id="f07e9-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="f07e9-121">Für jeden Vertrag sind z. B. die Informationen, über die Sie sich am meisten Gedanken machen, wer der Kunde ist, der Name des Auftragnehmers und die Gesamtkosten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="f07e9-122">Nachdem Sie ihr Modell erfolgreich erstellt haben, wenden Sie es auf [eine SharePoint Dokumentbibliothek an.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="f07e9-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="f07e9-123">Beim Hochladen von Dokumenten in die Dokumentbibliothek wird Ihr Dokumentverständnismodell ausgeführt und identifiziert und klassifiziert alle Dateien, die dem vertragsinhaltstyp entsprechen, den Sie in Ihrem Modell definiert haben.</span><span class="sxs-lookup"><span data-stu-id="f07e9-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="f07e9-124">Alle Als Verträge klassifizierten Dateien werden in einer benutzerdefinierten Bibliotheksansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f07e9-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="f07e9-125">Die Dateien zeigen auch die Werte aus jedem Vertrag an, den Sie in Ihrem Extractor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="f07e9-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Verträge in der Dokumentbibliothek](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="f07e9-127">Wenn Sie Aufbewahrungsanforderungen für Ihre Verträge haben, [](apply-a-retention-label-to-a-model.md) können Sie ihr Modell auch verwenden, um eine Aufbewahrungsbezeichnung anzuwenden, die verhindert, dass Ihre Verträge für einen bestimmten Zeitraum gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-127">If you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="f07e9-128">Schritte zum Erstellen und Trainieren Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="f07e9-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="f07e9-129">Für diese Schritte können Sie die Beispieldateien im [Repository "Contracts Management Solution Assets" verwenden.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="f07e9-129">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="f07e9-130">Die Beispiele in diesem Repository enthalten sowohl die Dokumentverständnismodelldateien als auch die Dateien, die zum Trainieren des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-130">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="f07e9-131">Erstellen eines Vertragsmodells</span><span class="sxs-lookup"><span data-stu-id="f07e9-131">Create a Contract model</span></span>

<span data-ttu-id="f07e9-132">Der erste Schritt besteht im Erstellen Ihres Vertragsmodells.</span><span class="sxs-lookup"><span data-stu-id="f07e9-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="f07e9-133">Wählen Sie im Inhaltscenter **Neu** aus, und dann **Modell erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f07e9-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="f07e9-134">Geben Sie **im Modellbereich** Neues Dokumentverständnis im Feld **Name** den Namen des Modells ein.</span><span class="sxs-lookup"><span data-stu-id="f07e9-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="f07e9-135">Für diese Vertragsverwaltungslösung können Sie den Modellvertrag *benennen.*</span><span class="sxs-lookup"><span data-stu-id="f07e9-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="f07e9-136">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f07e9-136">Choose **Create**.</span></span> <span data-ttu-id="f07e9-137">Dadurch wird eine Homepage für das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="f07e9-137">This creates a home page for the model.</span></span></br>

    ![Screenshot der Homepage des Vertrags.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="f07e9-139">Schulen des Modells zum Klassifizieren eines Dateityps</span><span class="sxs-lookup"><span data-stu-id="f07e9-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="f07e9-140">Hinzufügen von Beispieldateien für Ihr Modell</span><span class="sxs-lookup"><span data-stu-id="f07e9-140">Add example files for your model</span></span>

<span data-ttu-id="f07e9-141">Sie müssen mindestens fünf Beispieldateien hinzufügen, die Vertragsdokumente sind, und eine Beispieldatei, die kein Vertragsdokument ist (z. B. eine Arbeitsserklärung).</span><span class="sxs-lookup"><span data-stu-id="f07e9-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="f07e9-142">Wählen Sie **auf > Seite Modelle und Vertrag** unter **Schlüsselaktionen**  >  **Beispieldateien hinzufügen** die Option Dateien hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Screenshot der Seite Verträge mit hervorgehobener Option "Beispieldateien hinzufügen".](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="f07e9-144">Öffnen Sie auf der Seite **Beispieldateien** für Ihr Modell auswählen den Ordner Vertrag, wählen Sie Dateien aus, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="f07e9-145">Wenn Sie dort keine Beispieldateien haben, wählen Sie Hochladen **aus,** um sie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="f07e9-146">Beschriften der Dateien als positive oder negative Beispiele</span><span class="sxs-lookup"><span data-stu-id="f07e9-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="f07e9-147">Wählen Sie **auf > Seite Modelle** und Vertrag unter **Schlüsselaktionen** Dateien klassifizieren und Schulung ausführen die Option  >   **Train classifier aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Screenshot der Seite Verträge mit hervorgehobener Option zum Klassifizieren von Dateien und Ausführen der Schulungsoption.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="f07e9-149">Auf der Seite Models **> Contract > Contract classifier** sehen Sie im Viewer oben in der ersten Beispieldatei Text mit der Frage, ob die Datei ein Beispiel für das von Ihnen erstellte Vertragsmodell ist.</span><span class="sxs-lookup"><span data-stu-id="f07e9-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="f07e9-150">Wenn es sich um ein positives Beispiel handelt, wählen Sie **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="f07e9-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="f07e9-151">Wenn es sich um ein negatives Beispiel handelt, wählen Sie **Nein** aus.</span><span class="sxs-lookup"><span data-stu-id="f07e9-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="f07e9-152">Wählen Sie **in** der Liste Beschriftungsbeispiele auf der linken Seite andere Dateien aus, die Sie als Beispiele verwenden möchten, und beschriften Sie sie.</span><span class="sxs-lookup"><span data-stu-id="f07e9-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Homepage des Klassifizierers](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;f07e9-154&quot;>Hinzufügen von mindestens einer Erläuterung zum Trainieren des Klassifizierers</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;f07e9-155&quot;>Wählen Sie **auf > Seite > Vertragsklassifikator** die Registerkarte **Train** aus.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;f07e9-156&quot;>Im Abschnitt **Trainierte** Dateien wird eine Liste der Beispieldateien angezeigt, die Sie zuvor beschriftet haben.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;f07e9-157&quot;>Wählen Sie eine der positiven Dateien aus der Liste aus, um sie im Viewer anzeigen zu können.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;f07e9-158&quot;>Wählen Sie **im Abschnitt Erläuterungen** **die Option Neu** und dann Leer **aus.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;f07e9-159&quot;>Auf der Seite **Erklärung erstellen**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;f07e9-160&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f07e9-160&quot;>a.</span></span> <span data-ttu-id=&quot;f07e9-161&quot;>Geben Sie **im Feld Name** den Namen der Erläuterung ein (z. B. &quot;Vereinbarung").</span><span class="sxs-lookup"><span data-stu-id="f07e9-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="f07e9-162">b.</span><span class="sxs-lookup"><span data-stu-id="f07e9-162">b.</span></span> <span data-ttu-id="f07e9-163">Wählen Sie **im Feld Erläuterungstyp** **die Option Phrasenliste** aus, da Sie eine Textzeichenfolge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="f07e9-164">c.</span><span class="sxs-lookup"><span data-stu-id="f07e9-164">c.</span></span> <span data-ttu-id="f07e9-165">Geben Sie **im Listenfeld Phrase** die Zeichenfolge ein (z. B. "AGREEMENT").</span><span class="sxs-lookup"><span data-stu-id="f07e9-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="f07e9-166">Sie können die Option **Kleinschreibung als vertraulich auswählen,** wenn die Zeichenfolge auf die Zwischen-/Kleinschreibung reagieren muss.</span><span class="sxs-lookup"><span data-stu-id="f07e9-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="f07e9-167">d.</span><span class="sxs-lookup"><span data-stu-id="f07e9-167">d.</span></span> <span data-ttu-id="f07e9-168">Wählen **Sie Speichern und Trainieren aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-168">Select **Save and train**.</span></span>

    ![Screenshot des Erklärungspanels erstellen.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="f07e9-170">Ihr Modell testen</span><span class="sxs-lookup"><span data-stu-id="f07e9-170">Test your model</span></span>

<span data-ttu-id="f07e9-171">Sie können Ihr Vertragsmodell an Beispieldateien testen, die noch nicht gesehen wurden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="f07e9-172">Dies ist optional, kann jedoch eine bewährte Methode sein.</span><span class="sxs-lookup"><span data-stu-id="f07e9-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="f07e9-173">Wählen Sie **auf > Seite > Vertrags > klassifikator** die Registerkarte **Test** aus. Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f07e9-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="f07e9-174">In der **Liste Testdateien** werden ihre Beispieldateien angezeigt und angezeigt, ob sie vom Modell als positiv oder negativ vorhergesagt wurden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="f07e9-175">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="f07e9-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Screenshot der nicht gekennzeichneten Dateien in der Liste Textdateien](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="f07e9-177">Wenn sie fertig sind, wählen Sie **Training beenden aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="f07e9-178">Erstellen und Schulen eines Extractors</span><span class="sxs-lookup"><span data-stu-id="f07e9-178">Create and train an extractor</span></span>

1. <span data-ttu-id="f07e9-179">Wählen Sie **auf > Seite** Modelle und Vertrag unter **Schlüsselaktionen** Extrahieren erstellen und trainieren die Option  >  Extrahieren erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Screenshot der Seite Verträge mit hervorgehobener Option Zum Erstellen und Trainieren von Extraktionen.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="f07e9-181">Geben Sie **im Bereich Neue Entitätsextraktor** im Feld **Neuer Name** den Namen des Extraktionselements ein.</span><span class="sxs-lookup"><span data-stu-id="f07e9-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="f07e9-182">Nennen Sie es beispielsweise *Client,* wenn Sie den Namen des Clients aus jedem Vertrag extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="f07e9-183">Wenn Sie fertig sind, wählen Sie **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="f07e9-184">Beschriften der Entität, die Extrahiert werden soll</span><span class="sxs-lookup"><span data-stu-id="f07e9-184">Label the entity you want to extract</span></span>

<span data-ttu-id="f07e9-185">Wenn Sie den Extractor erstellen, wird die Extraktionsseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f07e9-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="f07e9-186">Dort sehen Sie eine Liste Ihrer Beispieldateien, wobei die erste Datei auf der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f07e9-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Screenshot der Beispielseite Clientextraktor mit Bezeichnungen.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="f07e9-188">So beschriften Sie die Entität:</span><span class="sxs-lookup"><span data-stu-id="f07e9-188">To label the entity:</span></span>

1. <span data-ttu-id="f07e9-189">Wählen Sie im Viewer die Daten, die aus den Dateien extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="f07e9-190">Wenn Sie z. B. den *Client* extrahieren möchten, markieren Sie den Clientwert in der ersten Datei (in diesem Beispiel *Best For You Organics*), und wählen Sie dann Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="f07e9-191">Der Wert wird aus der Datei  in der Liste Beschriftungsbeispiele unter der **Spalte Bezeichnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f07e9-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="f07e9-192">Wählen **Sie Nächste Datei** aus, um die Datei automatisch zu speichern und die nächste Datei in der Liste im Viewer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="f07e9-193">Oder wählen **Sie Speichern** aus, und wählen Sie dann eine andere Datei aus der Liste **Beschriftungsbeispiele** aus.</span><span class="sxs-lookup"><span data-stu-id="f07e9-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="f07e9-194">Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie dann, bis Sie die Bezeichnung in allen Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f07e9-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="f07e9-195">Nachdem Sie die Dateien gekennzeichnet haben, wird ein Benachrichtigungsbanner angezeigt, in dem Sie zum Training wechseln.</span><span class="sxs-lookup"><span data-stu-id="f07e9-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="f07e9-196">Sie können wählen, ob Sie weitere Dokumente beschriften oder zu Schulungen weiterkommen möchten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="f07e9-197">Hinzufügen einer Erläuterung</span><span class="sxs-lookup"><span data-stu-id="f07e9-197">Add an explanation</span></span>

<span data-ttu-id="f07e9-198">Sie können eine Erläuterung erstellen, die einen Hinweis auf das Entitätsformat selbst und mögliche Variationen in den Beispieldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="f07e9-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="f07e9-199">Beispielsweise kann ein Datumswert in vielen verschiedenen Formaten vorliegen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="f07e9-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="f07e9-200">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="f07e9-200">10/14/2019</span></span>
- <span data-ttu-id="f07e9-201">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="f07e9-201">October 14, 2019</span></span>
- <span data-ttu-id="f07e9-202">Montag, 14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="f07e9-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="f07e9-203">Um das Startdatum des *Vertrags zu* identifizieren, können Sie eine Muster erläuterung erstellen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="f07e9-204">Wählen Sie **im Abschnitt Erläuterungen** **die Option Neu** und dann Leer **aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="f07e9-205">Auf der Seite **Erklärung erstellen**:</span><span class="sxs-lookup"><span data-stu-id="f07e9-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="f07e9-206">a.</span><span class="sxs-lookup"><span data-stu-id="f07e9-206">a.</span></span> <span data-ttu-id="f07e9-207">Geben Sie **im Feld Name** den Namen der Erläuterung ein (z. B. *Date*).</span><span class="sxs-lookup"><span data-stu-id="f07e9-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="f07e9-208">b.</span><span class="sxs-lookup"><span data-stu-id="f07e9-208">b.</span></span> <span data-ttu-id="f07e9-209">Wählen Sie **im Feld Erläuterungstyp** die Option **Musterliste aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="f07e9-210">c.</span><span class="sxs-lookup"><span data-stu-id="f07e9-210">c.</span></span> <span data-ttu-id="f07e9-211">Geben Sie **im Feld Wert** die Datumsvariation an, wie sie in den Beispieldateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="f07e9-212">Wenn Sie z. B. Daten im Format 0/00/0000 haben, geben Sie sämtliche Varianten ein, die in Ihren Dokumenten angezeigt werden, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="f07e9-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="f07e9-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="f07e9-213">0/0/0000</span></span>
    - <span data-ttu-id="f07e9-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="f07e9-214">0/00/0000</span></span>
    - <span data-ttu-id="f07e9-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="f07e9-215">00/0/0000</span></span>
    - <span data-ttu-id="f07e9-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="f07e9-216">00/00/0000</span></span>

4. <span data-ttu-id="f07e9-217">Wählen **Sie Speichern und Trainieren aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="f07e9-218">Testen Des Modells erneut</span><span class="sxs-lookup"><span data-stu-id="f07e9-218">Test your model again</span></span>

<span data-ttu-id="f07e9-219">Sie können Ihr Vertragsmodell an Beispieldateien testen, die noch nicht gesehen wurden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="f07e9-220">Dies ist optional, kann jedoch eine bewährte Methode sein.</span><span class="sxs-lookup"><span data-stu-id="f07e9-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="f07e9-221">Wählen Sie **auf > Seite > Vertrags > klassifikator** die Registerkarte **Test** aus. Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f07e9-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="f07e9-222">In der **Liste Testdateien** werden ihre Beispieldateien angezeigt und angezeigt, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="f07e9-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="f07e9-223">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="f07e9-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="f07e9-224">Wenn sie fertig sind, wählen Sie **Training beenden aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="f07e9-225">Anwenden des Modells auf eine Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="f07e9-225">Apply your model to a document library</span></span>

<span data-ttu-id="f07e9-226">So wenden Sie Ihr Modell auf SharePoint Dokumentbibliothek an:</span><span class="sxs-lookup"><span data-stu-id="f07e9-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="f07e9-227">Wählen Sie **auf > Seite Modelle** und Vertrag unter **Schlüsselaktionen** Modell auf Bibliotheken anwenden die Option  >  Modell anwenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="f07e9-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Screenshot der Seite Verträge mit der Option Modell auf Bibliotheken anwenden hervorgehoben.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="f07e9-229">Wählen Sie **im** Bereich Vertrag hinzufügen die SharePoint aus, die die Dokumentbibliothek enthält, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="f07e9-230">Wenn die Website in der Liste nicht angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="f07e9-231">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f07e9-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f07e9-232">Sie müssen über die Berechtigung *Listen verwalten* oder *Bearbeiten* für die Dokumentbibliothek verfügen, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="f07e9-233">Nachdem Sie die Website ausgewählt haben, wählen Sie die Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f07e9-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="f07e9-234">Da das Modell einem Inhaltstyp zugeordnet ist, fügt es beim Anwenden auf die Bibliothek den Inhaltstyp und dessen Ansicht mit den extrahierten Bezeichnungen hinzu, die als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="f07e9-235">Diese Ansicht ist standardmäßig die Standardansicht der Bibliothek, Sie können jedoch optional festlegen,  dass sie nicht die Standardansicht ist, indem Sie Erweiterte Einstellungen auswählen und das **Kontrollkästchen** Diese neue Ansicht als Standardansicht festlegen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f07e9-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="f07e9-236">Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="f07e9-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="f07e9-237">Auf der **Seite Modelle >** Vertrag  wird im Abschnitt Bibliotheken mit diesem Modell die URL zur SharePoint angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f07e9-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Screenshot der Homepage "Vertrag", auf der die Bibliotheken mit diesem Modellabschnitt angezeigt werden.](../media/content-understanding/contract-libraries-with-this-model.png)

<span data-ttu-id="f07e9-239">Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse sehen.</span><span class="sxs-lookup"><span data-stu-id="f07e9-239">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="f07e9-240">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f07e9-240">Next step</span></span>

[<span data-ttu-id="f07e9-241">Schritt 2. Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f07e9-241">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)