---
title: Erstellen eines Extraktors
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Erfahren Sie, wie Sie in Microsoft Office SharePoint Syntex einen Extraktor erstellen.
ms.openlocfilehash: b957d905f3807f6007ebeb742d9b56d81ea38ac2
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701129"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="dea37-103">Extraktor in Microsoft SharePoint Syntex erstellen</span><span class="sxs-lookup"><span data-stu-id="dea37-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="dea37-104">Vor oder nach der Erstellung eines Klassifizierermodells zur Automatisierung der Identifikation und Klassifizierung bestimmter Dokumenttypen können Sie dem Modell optional Extraktoren hinzufügen, um diesen Dokumenten spezifische Informationen zu entnehmen.</span><span class="sxs-lookup"><span data-stu-id="dea37-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="dea37-105">Vielleicht möchten Sie zum Beispiel, dass Ihr Modell nicht nur alle Dokumente zu *Vertragsverlängerungen* in Ihrer Dokumentbibliothek auffindet, sondern es soll auch für jedes Dokument das *Startdatum der Inbetriebnahme* als Spaltenwert in der Dokumentbibliothek angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dea37-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="dea37-106">Dazu müssen Sie für jede Entität, die aus dem Dokument extrahiert werden soll, einen Extraktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="dea37-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="dea37-107">In unserem Beispiel möchten wir das  **Startdatum der Inbetriebnahme** für jedes Dokument zu  **Vertragsverlängerungen** , das von dem Modell identifiziert wird, extrahieren.</span><span class="sxs-lookup"><span data-stu-id="dea37-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="dea37-108">Wir möchten in der Dokumentbibliothek eine Ansicht aller Dokumente zu  **Vertragsverlängerungen** und dazu eine Spalte, die den Wert für das **Startdatum der Inbetriebnahme** für jedes Dokument anzeigt.</span><span class="sxs-lookup"><span data-stu-id="dea37-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="dea37-109">Für die Erstellung eines Extraktors benutzen Sie dieselben Dateien, die Sie zuvor hochgeladen haben, um den Klassifizierer zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="dea37-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="dea37-110">Benennen des Extraktors</span><span class="sxs-lookup"><span data-stu-id="dea37-110">Name your extractor</span></span>

1. <span data-ttu-id="dea37-111">Klicken Sie auf der Startseite des Modells auf den Titel **Extraktoren erstellen und trainieren**, und wählen Sie dann **Extraktor trainieren** aus.</span><span class="sxs-lookup"><span data-stu-id="dea37-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="dea37-112">Geben Sie in der Anzeige **Neue Entitätsextraktionsfunktion** den Namen Ihres Extraktors in das Feld **Neuer Extraktorname** ein.</span><span class="sxs-lookup"><span data-stu-id="dea37-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="dea37-113">Vergeben Sie beispielsweise den Namen **Startdatum der Inbetriebnahme**, wenn Sie das Startdatum der Inbetriebnahme aus jedem Dokument zu Vertragsverlängerungen extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dea37-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="dea37-114">Sie können auch eine bereits erstellte Spalte wiederverwenden (beispielsweise eine Spalte mit verwalteten Metadaten).</span><span class="sxs-lookup"><span data-stu-id="dea37-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="dea37-115">Wenn Sie einen neuen Extraktor erstellen, dann **Neuer Spaltentyp** und **Einzelne Textzeile** auswählen, beträgt die maximale Anzahl von Zeichen 255.</span><span class="sxs-lookup"><span data-stu-id="dea37-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="dea37-116">Alle Zeichen, die Sie eingeben und die das Limit überschreiten, werden abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="dea37-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="dea37-117">Wenn Sie fertig sind, klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="dea37-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="dea37-118">Hinzufügen einer Beschriftung</span><span class="sxs-lookup"><span data-stu-id="dea37-118">Add a label</span></span>

<span data-ttu-id="dea37-119">Im nächsten Schritt beschriften Sie die Entität, die Sie aus Ihren Beispiel-Schulungsdateien extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dea37-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="dea37-120">Durch das Erstellen eines Extraktors wird die Extraktorseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dea37-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="dea37-121">Dort sehen Sie eine Liste Ihrer Beispieldateien, wobei die erste Datei auf der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dea37-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="dea37-122">Wählen Sie im Viewer die Daten, die aus den Dateien extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dea37-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="dea37-123">Möchten Sie beispielsweise das *Startdatum der Inbetriebnahme* extrahieren, markieren Sie den Datumswert in der ersten Datei (*Montag, 14. Oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="dea37-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="dea37-124">Klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dea37-124">and then click **Save**.</span></span>  <span data-ttu-id="dea37-125">Der Wert sollte in der Liste mit beschrifteten Beispielen in der Spalte **Beschriftung** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dea37-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="dea37-126">Wählen Sie **Nächste Datei** aus, um die Datei automatisch zu speichern und die nächste Datei der Liste im Viewer anzeigen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="dea37-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="dea37-127">Oder wählen Sie **Speichern**, und wählen Sie dann eine andere Datei aus der Liste **Beschriftete Beispiele** aus.</span><span class="sxs-lookup"><span data-stu-id="dea37-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="dea37-128">Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie dann den gesamten Vorgang, bis Sie die Beschriftung aller fünf Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="dea37-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="dea37-130">Wenn Sie die Beschriftung der Dateien abgeschlossen haben, zeigt ein Benachrichtigungsbanner an, dass Sie zur Schulung fortfahren können. </span><span class="sxs-lookup"><span data-stu-id="dea37-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="dea37-131">Sie können noch weitere Dokumente beschriften oder mit der Schulung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dea37-131">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="dea37-132">Hinzufügen einer Erläuterung</span><span class="sxs-lookup"><span data-stu-id="dea37-132">Add an explanation</span></span>

<span data-ttu-id="dea37-133">Für unser Beispiel erstellen wir eine Erläuterung, die Hinweise auf das Format der Entität selbst und auf etwaige Varianten in den Beispieldokumenten gibt.</span><span class="sxs-lookup"><span data-stu-id="dea37-133">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="dea37-134">Beispielsweise kann ein Datum in unterschiedlichen Formaten angegeben werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="dea37-134">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="dea37-135">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="dea37-135">10/14/2019</span></span>
- <span data-ttu-id="dea37-136">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="dea37-136">October 14, 2019</span></span>
- <span data-ttu-id="dea37-137">Montag, 14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="dea37-137">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="dea37-138">Um die Erkennung des *Startdatums der Inbetriebnahme* zu unterstützen, können Sie eine Erläuterung des Musters hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dea37-138">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="dea37-139">Wählen Sie im Abschnitt Erläuterung **Neu** und geben Sie einen Namen ein (beispielsweise *Datum*).</span><span class="sxs-lookup"><span data-stu-id="dea37-139">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="dea37-140">Wählen Sie als Typ **Musterliste**.</span><span class="sxs-lookup"><span data-stu-id="dea37-140">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="dea37-141">Geben Sie als Wert die Datenvarianten an, wie sie in den Beispieldateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dea37-141">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="dea37-142">Wenn Sie z. B. Daten im Format 0/00/0000 haben, geben Sie sämtliche Varianten ein, die in Ihren Dokumenten angezeigt werden, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="dea37-142">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="dea37-143">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="dea37-143">0/0/0000</span></span>
    - <span data-ttu-id="dea37-144">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="dea37-144">0/00/0000</span></span>
    - <span data-ttu-id="dea37-145">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="dea37-145">00/0/0000</span></span>
    - <span data-ttu-id="dea37-146">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="dea37-146">00/00/0000</span></span>
4. <span data-ttu-id="dea37-147">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="dea37-147">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="dea37-148">Weitere Informationen zu Erläuterungstypen erhalten Sie unter [Erläuterungstypen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span><span class="sxs-lookup"><span data-stu-id="dea37-148">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="dea37-149">Verwenden der Erläuterungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="dea37-149">Use the Explanation library</span></span>

<span data-ttu-id="dea37-150">Um Erläuterungen für Elemente wie Daten zu erstellen, ist es einfacher [die Erläuterungsbibliothek zu verwenden](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library), als manuell alle Varianten einzugeben.</span><span class="sxs-lookup"><span data-stu-id="dea37-150">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="dea37-151">Die Erläuterungsbibliothek ist eine Zusammenstellung vordefinierter Erläuterungen zu Begriffen und Mustern.</span><span class="sxs-lookup"><span data-stu-id="dea37-151">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="dea37-152">In der Bibliothek wird versucht, alle Formate für häufige Begriffs- oder Musterlisten bereitzustellen, wie z. B. Telefonnummern, Postleitzahlen, und viele andere.</span><span class="sxs-lookup"><span data-stu-id="dea37-152">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="dea37-153">FÜr das Beispiel mit dem *Startdatum der Inbetriebnahme* ist es effizienter, die vordefinierte Erläuterung für das *Datum* in der Erläuterungsbibliothek zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="dea37-153">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="dea37-154">Wählen Sie im **Abschnitt Erläuterung** die Option **Neu**, und wählen Sie dann **Aus der Erläuterungsbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="dea37-154">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="dea37-155">Wählen Sie in der Erläuterungsbibliothek **Datum**.</span><span class="sxs-lookup"><span data-stu-id="dea37-155">From the explanation library, select **Date**.</span></span> <span data-ttu-id="dea37-156">Sie können alle Varianten von Datumsangaben anzeigen lassen, die erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="dea37-156">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="dea37-157">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dea37-157">Select **Add**.</span></span></br>

    ![Erläuterungsbibliothek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="dea37-159">Auf der Seite **Eine Erläuterung erstellen** werden die Felder automatisch mit Informationen zum *Datum* aus der Erläuterungsbibliothek ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="dea37-159">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="dea37-160">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="dea37-160">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="dea37-162">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="dea37-162">Train the model</span></span> 

<span data-ttu-id="dea37-163">Durch das Speichern Ihrer Erläuterung starten Sie die Schulung.</span><span class="sxs-lookup"><span data-stu-id="dea37-163">Saving your explanation start the training.</span></span> <span data-ttu-id="dea37-164">Wenn Ihr Modell über ausreichend Informationen verfügt, um Daten aus Ihrer Liste beschrifteter Beispiele zu extrahieren, wird jede Datei mit **Übereinstimmung** beschriftet.</span><span class="sxs-lookup"><span data-stu-id="dea37-164">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Übereinstimmung](../media/content-understanding/match2.png) 

<span data-ttu-id="dea37-166">Wenn die Erläuterung nicht genügend Informationen enthält, um die Daten zu finden, die Sie extrahieren möchten, erhält jede Datei die Beschriftung **Keine Übereinstimmung**.</span><span class="sxs-lookup"><span data-stu-id="dea37-166">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="dea37-167">Sie können auf die **Dateien ohne Übereinstimmung** klicken, um weitere Informationen darüber zu erhalten, warum keine Übereinstimmung gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="dea37-167">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="dea37-168">Hinzufügen einer weiteren Erläuterung</span><span class="sxs-lookup"><span data-stu-id="dea37-168">Add another explanation</span></span>

<span data-ttu-id="dea37-169">Häufig ist die fehlende Übereinstimmung ein Hinweis darauf, dass die bereitgestellte Erläuterung nicht ausreichend Informationen zur Verfügung stellte, um das Startdatum für die Inbetriebnahme so zu extrahieren, dass es unseren beschrifteten Dateien entspricht.</span><span class="sxs-lookup"><span data-stu-id="dea37-169">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="dea37-170">Möglicherweise müssen Sie die Erläuterung bearbeiten, oder eine weitere hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dea37-170">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="dea37-171">In unserem Beispiel können Sie sehen dass die Textzeichenfolge *Startdatum für die Inbetriebnahme von* immer vor dem tatsächlichen Wert steht.</span><span class="sxs-lookup"><span data-stu-id="dea37-171">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="dea37-172">Um die Erkennung des Startdatums der Inbetriebnahme zu unterstützen, müssen Sie eine Erläuterung des Musters hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dea37-172">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="dea37-173">Wählen Sie im Abschnitt Erläuterung **Neu** und geben Sie einen Namen ein (beispielsweise *Präfixzeichenfolge*).</span><span class="sxs-lookup"><span data-stu-id="dea37-173">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="dea37-174">Wählen Sie als Typ **Begriffsliste**.</span><span class="sxs-lookup"><span data-stu-id="dea37-174">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="dea37-175">Verwenden Sie *Startdatum für die Inbetriebnahme von* als Wert.</span><span class="sxs-lookup"><span data-stu-id="dea37-175">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="dea37-176">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="dea37-176">Select **Save**.</span></span>

    ![Präfixzeichenfolge](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="dea37-178">Erneutes Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="dea37-178">Train the model again</span></span>

<span data-ttu-id="dea37-179">Durch das Speichern der Erläuterung wird die Schulung erneut gestartet. Dieses Mal werden beide Erläuterungen in dem Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="dea37-179">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="dea37-180">Wenn Ihr Modell über ausreichend Informationen verfügt, um Daten aus der Liste beschrifteter Beispiele zu extrahieren, wird jede Datei mit **Übereinstimmung** beschriftet.</span><span class="sxs-lookup"><span data-stu-id="dea37-180">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="dea37-181">Wenn Sie erneut **Keine Übereinstimmung** für Ihre beschrifteten Dateien erhalten, müssen Sie wahrscheinlich eine weitere Erläuterung erstellen, um dem Modell mehr Informationen zu liefern, mithilfe derer es den Dokumenttyp identifizieren kann, oder Änderungen an Ihren bestehenden Erläuterungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="dea37-181">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="dea37-182">Testen Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="dea37-182">Test your model</span></span>

<span data-ttu-id="dea37-183">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie nun das Modell für die restlichen nicht beschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="dea37-183">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="dea37-184">Das ist ein optionaler aber nützlicher Schritt, um die "Tauglichkeit" oder die Bereitschaft des Modells vor seiner Verwendung zu bewerten. Dazu wird es an Dateien getestet, die das Modell noch nie gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="dea37-184">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="dea37-185">Klicken Sie auf der Startseite des Modells auf die Registerkarte **Test**. Dadurch wird das Modell für Ihre nicht beschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dea37-185">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="dea37-186">In der Liste der **Testdateien** werden Ihre Beispieldateien angezeigt, um zu zeigen, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="dea37-186">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="dea37-187">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="dea37-187">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen Ihrer Dateien](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="dea37-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dea37-189">See Also</span></span>
[<span data-ttu-id="dea37-190">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="dea37-190">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="dea37-191">Beschreibungstypen</span><span class="sxs-lookup"><span data-stu-id="dea37-191">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="dea37-192">Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="dea37-192">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="dea37-193">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="dea37-193">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="dea37-194">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="dea37-194">Apply a model</span></span>](apply-a-model.md) 
