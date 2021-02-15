---
title: Erstellen eines Extraktors
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
description: Erfahren Sie, wie Sie in Microsoft Office SharePoint Syntex einen Extraktor erstellen.
ms.openlocfilehash: b0b03d0e8804097f34f9cd5b17504263097d8696
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242500"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="6d712-103">Extraktor in Microsoft SharePoint Syntex erstellen</span><span class="sxs-lookup"><span data-stu-id="6d712-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="6d712-104">Vor oder nach der Erstellung eines Klassifizierermodells zur Automatisierung der Identifikation und Klassifizierung bestimmter Dokumenttypen können Sie dem Modell optional Extraktoren hinzufügen, um diesen Dokumenten spezifische Informationen zu entnehmen.</span><span class="sxs-lookup"><span data-stu-id="6d712-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="6d712-105">Vielleicht möchten Sie zum Beispiel, dass Ihr Modell nicht nur alle Dokumente zu *Vertragsverlängerungen* in Ihrer Dokumentbibliothek auffindet, sondern es soll auch für jedes Dokument das *Startdatum der Inbetriebnahme* als Spaltenwert in der Dokumentbibliothek angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d712-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="6d712-106">Dazu müssen Sie für jede Entität, die aus dem Dokument extrahiert werden soll, einen Extraktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d712-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="6d712-107">In unserem Beispiel möchten wir das  **Startdatum der Inbetriebnahme** für jedes Dokument zu  **Vertragsverlängerungen** , das von dem Modell identifiziert wird, extrahieren.</span><span class="sxs-lookup"><span data-stu-id="6d712-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="6d712-108">Wir möchten in der Dokumentbibliothek eine Ansicht aller Dokumente zu  **Vertragsverlängerungen** und dazu eine Spalte, die den Wert für das **Startdatum der Inbetriebnahme** für jedes Dokument anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6d712-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="6d712-109">Für die Erstellung eines Extraktors benutzen Sie dieselben Dateien, die Sie zuvor hochgeladen haben, um den Klassifizierer zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="6d712-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="6d712-110">Benennen des Extraktors</span><span class="sxs-lookup"><span data-stu-id="6d712-110">Name your extractor</span></span>

1. <span data-ttu-id="6d712-111">Klicken Sie auf der Startseite des Modells auf den Titel **Extraktoren erstellen und trainieren**, und wählen Sie dann **Extraktor trainieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6d712-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="6d712-112">Geben Sie in der Anzeige **Neue Entitätsextraktionsfunktion** den Namen Ihres Extraktors in das Feld **Neuer Extraktorname** ein.</span><span class="sxs-lookup"><span data-stu-id="6d712-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="6d712-113">Vergeben Sie beispielsweise den Namen **Startdatum der Inbetriebnahme**, wenn Sie das Startdatum der Inbetriebnahme aus jedem Dokument zu Vertragsverlängerungen extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6d712-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="6d712-114">Sie können auch eine bereits erstellte Spalte wiederverwenden (beispielsweise eine Spalte mit verwalteten Metadaten).</span><span class="sxs-lookup"><span data-stu-id="6d712-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="6d712-115">Wenn Sie einen neuen Extraktor erstellen, dann **Neuer Spaltentyp** und **Einzelne Textzeile** auswählen, beträgt die maximale Anzahl von Zeichen 255.</span><span class="sxs-lookup"><span data-stu-id="6d712-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="6d712-116">Alle Zeichen, die Sie eingeben und die das Limit überschreiten, werden abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="6d712-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="6d712-117">Wenn Sie fertig sind, klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6d712-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="6d712-118">Hinzufügen einer Beschriftung</span><span class="sxs-lookup"><span data-stu-id="6d712-118">Add a label</span></span>

<span data-ttu-id="6d712-119">Im nächsten Schritt beschriften Sie die Entität, die Sie aus Ihren Beispiel-Schulungsdateien extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6d712-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="6d712-120">Durch das Erstellen eines Extraktors wird die Extraktorseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6d712-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="6d712-121">Dort sehen Sie eine Liste Ihrer Beispieldateien, wobei die erste Datei auf der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6d712-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="6d712-122">Wählen Sie im Viewer die Daten, die aus den Dateien extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6d712-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="6d712-123">Möchten Sie beispielsweise das *Startdatum der Inbetriebnahme* extrahieren, markieren Sie den Datumswert in der ersten Datei (*Montag, 14. Oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="6d712-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="6d712-124">Klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6d712-124">and then click **Save**.</span></span>  <span data-ttu-id="6d712-125">Der Wert sollte in der Liste mit beschrifteten Beispielen in der Spalte **Beschriftung** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d712-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="6d712-126">Wählen Sie **Nächste Datei** aus, um die Datei automatisch zu speichern und die nächste Datei der Liste im Viewer anzeigen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="6d712-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="6d712-127">Oder wählen Sie **Speichern**, und wählen Sie dann eine andere Datei aus der Liste **Beschriftete Beispiele** aus.</span><span class="sxs-lookup"><span data-stu-id="6d712-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="6d712-128">Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie dann den gesamten Vorgang, bis Sie die Beschriftung aller fünf Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="6d712-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="6d712-130">Wenn Sie die Beschriftung der Dateien abgeschlossen haben, zeigt ein Benachrichtigungsbanner an, dass Sie zur Schulung fortfahren können. </span><span class="sxs-lookup"><span data-stu-id="6d712-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="6d712-131">Sie können noch weitere Dokumente beschriften oder mit der Schulung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6d712-131">You can choose to more label more documents or advance to training.</span></span> 

### <a name="use-find-to-search-your-file"></a><span data-ttu-id="6d712-132">Verwenden Sie „Suchen“, um Ihre Datei zu durchsuchen</span><span class="sxs-lookup"><span data-stu-id="6d712-132">Use Find to search your file</span></span>
<span data-ttu-id="6d712-133">Sie können das Feature <b>Suchen</b> verwenden, um nach einer Entität in Ihrem Dokument zu suchen, die Sie beschriften möchten.</span><span class="sxs-lookup"><span data-stu-id="6d712-133">You can use the <b>Find</b> feature to search for an entity in your document that you want to label.</span></span>

   ![In Datei suchen](../media/content-understanding/find-feature.png) 

<span data-ttu-id="6d712-135">Das Feature „Suchen“ ist hilfreich, wenn Sie ein großes Dokument durchsuchen oder wenn es mehrere Instanzen der Entität im Dokument gibt.</span><span class="sxs-lookup"><span data-stu-id="6d712-135">The Find feature is useful if you are searching a large document or if there are multiple instances of the entity in the document.</span></span> <span data-ttu-id="6d712-136">Wenn Sie mehrere Instanzen finden, können Sie in den Suchergebnissen die Instanz auswählen, die Sie benötigen, um zu diesem Ort im Viewer zu wechseln, sodass Sie sie beschriften können.</span><span class="sxs-lookup"><span data-stu-id="6d712-136">If you find multiple instances, you can select the one you need in the search results to go to that location in the viewer to label it.</span></span>


## <a name="add-an-explanation"></a><span data-ttu-id="6d712-137">Hinzufügen einer Erläuterung</span><span class="sxs-lookup"><span data-stu-id="6d712-137">Add an explanation</span></span>

<span data-ttu-id="6d712-138">Für unser Beispiel erstellen wir eine Erläuterung, die Hinweise auf das Format der Entität selbst und auf etwaige Varianten in den Beispieldokumenten gibt.</span><span class="sxs-lookup"><span data-stu-id="6d712-138">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="6d712-139">Beispielsweise kann ein Datum in unterschiedlichen Formaten angegeben werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="6d712-139">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="6d712-140">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="6d712-140">10/14/2019</span></span>
- <span data-ttu-id="6d712-141">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="6d712-141">October 14, 2019</span></span>
- <span data-ttu-id="6d712-142">Montag, 14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="6d712-142">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="6d712-143">Um die Erkennung des *Startdatums der Inbetriebnahme* zu unterstützen, können Sie eine Erläuterung des Musters hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d712-143">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="6d712-144">Wählen Sie im Abschnitt Erläuterung **Neu** und geben Sie einen Namen ein (beispielsweise *Datum*).</span><span class="sxs-lookup"><span data-stu-id="6d712-144">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="6d712-145">Wählen Sie als Typ **Musterliste**.</span><span class="sxs-lookup"><span data-stu-id="6d712-145">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="6d712-146">Geben Sie als Wert die Datenvarianten an, wie sie in den Beispieldateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d712-146">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="6d712-147">Wenn Sie z. B. Daten im Format 0/00/0000 haben, geben Sie sämtliche Varianten ein, die in Ihren Dokumenten angezeigt werden, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="6d712-147">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="6d712-148">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="6d712-148">0/0/0000</span></span>
    - <span data-ttu-id="6d712-149">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="6d712-149">0/00/0000</span></span>
    - <span data-ttu-id="6d712-150">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="6d712-150">00/0/0000</span></span>
    - <span data-ttu-id="6d712-151">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="6d712-151">00/00/0000</span></span>
4. <span data-ttu-id="6d712-152">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6d712-152">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6d712-153">Weitere Informationen zu Erläuterungstypen erhalten Sie unter [Erläuterungstypen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span><span class="sxs-lookup"><span data-stu-id="6d712-153">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="6d712-154">Verwenden der Erläuterungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="6d712-154">Use the Explanation library</span></span>

<span data-ttu-id="6d712-155">Um Erläuterungen für Elemente wie Daten zu erstellen, ist es einfacher [die Erläuterungsbibliothek zu verwenden](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library), als manuell alle Varianten einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d712-155">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="6d712-156">Die Erläuterungsbibliothek ist eine Zusammenstellung vordefinierter Erläuterungen zu Begriffen und Mustern.</span><span class="sxs-lookup"><span data-stu-id="6d712-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="6d712-157">In der Bibliothek wird versucht, alle Formate für häufige Begriffs- oder Musterlisten bereitzustellen, wie z. B. Telefonnummern, Postleitzahlen, und viele andere.</span><span class="sxs-lookup"><span data-stu-id="6d712-157">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="6d712-158">FÜr das Beispiel mit dem *Startdatum der Inbetriebnahme* ist es effizienter, die vordefinierte Erläuterung für das *Datum* in der Erläuterungsbibliothek zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6d712-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="6d712-159">Wählen Sie im **Abschnitt Erläuterung** die Option **Neu**, und wählen Sie dann **Aus der Erläuterungsbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="6d712-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="6d712-160">Wählen Sie in der Erläuterungsbibliothek **Datum**.</span><span class="sxs-lookup"><span data-stu-id="6d712-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="6d712-161">Sie können alle Varianten von Datumsangaben anzeigen lassen, die erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="6d712-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="6d712-162">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6d712-162">Select **Add**.</span></span></br>

    ![Erläuterungsbibliothek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="6d712-164">Auf der Seite **Eine Erläuterung erstellen** werden die Felder automatisch mit Informationen zum *Datum* aus der Erläuterungsbibliothek ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="6d712-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="6d712-165">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6d712-165">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="6d712-167">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6d712-167">Train the model</span></span> 

<span data-ttu-id="6d712-168">Durch das Speichern Ihrer Erläuterung starten Sie die Schulung.</span><span class="sxs-lookup"><span data-stu-id="6d712-168">Saving your explanation start the training.</span></span> <span data-ttu-id="6d712-169">Wenn Ihr Modell über ausreichend Informationen verfügt, um Daten aus Ihrer Liste beschrifteter Beispiele zu extrahieren, wird jede Datei mit **Übereinstimmung** beschriftet.</span><span class="sxs-lookup"><span data-stu-id="6d712-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Übereinstimmung](../media/content-understanding/match2.png) 

<span data-ttu-id="6d712-171">Wenn die Erläuterung nicht genügend Informationen enthält, um die Daten zu finden, die Sie extrahieren möchten, erhält jede Datei die Beschriftung **Keine Übereinstimmung**.</span><span class="sxs-lookup"><span data-stu-id="6d712-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="6d712-172">Sie können auf die **Dateien ohne Übereinstimmung** klicken, um weitere Informationen darüber zu erhalten, warum keine Übereinstimmung gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="6d712-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="6d712-173">Hinzufügen einer weiteren Erläuterung</span><span class="sxs-lookup"><span data-stu-id="6d712-173">Add another explanation</span></span>

<span data-ttu-id="6d712-174">Häufig ist die fehlende Übereinstimmung ein Hinweis darauf, dass die bereitgestellte Erläuterung nicht ausreichend Informationen zur Verfügung stellte, um das Startdatum für die Inbetriebnahme so zu extrahieren, dass es unseren beschrifteten Dateien entspricht.</span><span class="sxs-lookup"><span data-stu-id="6d712-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="6d712-175">Möglicherweise müssen Sie die Erläuterung bearbeiten, oder eine weitere hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d712-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="6d712-176">In unserem Beispiel können Sie sehen dass die Textzeichenfolge *Startdatum für die Inbetriebnahme von* immer vor dem tatsächlichen Wert steht.</span><span class="sxs-lookup"><span data-stu-id="6d712-176">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="6d712-177">Um die Erkennung des Startdatums der Inbetriebnahme zu unterstützen, müssen Sie eine Erläuterung des Musters hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d712-177">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="6d712-178">Wählen Sie im Abschnitt Erläuterung **Neu** und geben Sie einen Namen ein (beispielsweise *Präfixzeichenfolge*).</span><span class="sxs-lookup"><span data-stu-id="6d712-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="6d712-179">Wählen Sie als Typ **Begriffsliste**.</span><span class="sxs-lookup"><span data-stu-id="6d712-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="6d712-180">Verwenden Sie *Startdatum für die Inbetriebnahme von* als Wert.</span><span class="sxs-lookup"><span data-stu-id="6d712-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="6d712-181">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6d712-181">Select **Save**.</span></span>

    ![Präfixzeichenfolge](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="6d712-183">Erneutes Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6d712-183">Train the model again</span></span>

<span data-ttu-id="6d712-184">Durch das Speichern der Erläuterung wird die Schulung erneut gestartet. Dieses Mal werden beide Erläuterungen in dem Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d712-184">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="6d712-185">Wenn Ihr Modell über ausreichend Informationen verfügt, um Daten aus der Liste beschrifteter Beispiele zu extrahieren, wird jede Datei mit **Übereinstimmung** beschriftet.</span><span class="sxs-lookup"><span data-stu-id="6d712-185">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="6d712-186">Wenn Sie erneut **Keine Übereinstimmung** für Ihre beschrifteten Dateien erhalten, müssen Sie wahrscheinlich eine weitere Erläuterung erstellen, um dem Modell mehr Informationen zu liefern, mithilfe derer es den Dokumenttyp identifizieren kann, oder Änderungen an Ihren bestehenden Erläuterungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="6d712-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="6d712-187">Testen Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="6d712-187">Test your model</span></span>

<span data-ttu-id="6d712-188">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie nun das Modell für die restlichen nicht beschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="6d712-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="6d712-189">Das ist ein optionaler aber nützlicher Schritt, um die "Tauglichkeit" oder die Bereitschaft des Modells vor seiner Verwendung zu bewerten. Dazu wird es an Dateien getestet, die das Modell noch nie gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="6d712-189">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="6d712-190">Klicken Sie auf der Startseite des Modells auf die Registerkarte **Test**. Dadurch wird das Modell für Ihre nicht beschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d712-190">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="6d712-191">In der Liste der **Testdateien** werden Ihre Beispieldateien angezeigt, um zu zeigen, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="6d712-191">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="6d712-192">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="6d712-192">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen Ihrer Dateien](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="6d712-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d712-194">See Also</span></span>
[<span data-ttu-id="6d712-195">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="6d712-195">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="6d712-196">Beschreibungstypen</span><span class="sxs-lookup"><span data-stu-id="6d712-196">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="6d712-197">Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="6d712-197">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="6d712-198">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="6d712-198">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="6d712-199">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="6d712-199">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="6d712-200">Barrierefreiheitsmodus für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="6d712-200">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
