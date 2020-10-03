---
title: Erstellen eines Extraktors
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Erfahren Sie, wie Sie in Microsoft Office SharePoint Syntex einen Extraktor erstellen.
ms.openlocfilehash: 260486c128ce76c31fe5f4a0994b4e103687b829
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338649"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="293d1-103">Extraktor in Microsoft SharePoint Syntex erstellen</span><span class="sxs-lookup"><span data-stu-id="293d1-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="293d1-104">Vor oder nach der Erstellung eines Klassifizierermodells zur Automatisierung der Identifikation und Klassifizierung bestimmter Dokumenttypen können Sie dem Modell optional Extraktoren hinzufügen, um diesen Dokumenten spezifische Informationen zu entnehmen.</span><span class="sxs-lookup"><span data-stu-id="293d1-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="293d1-105">Vielleicht möchten Sie zum Beispiel, dass Ihr Modell nicht nur alle Dokumente zu *Vertragsverlängerungen* in Ihrer Dokumentbibliothek auffindet, sondern es soll auch für jedes Dokument das *Startdatum der Inbetriebnahme* als Spaltenwert in der Dokumentbibliothek angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="293d1-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="293d1-106">Dazu müssen Sie für jede Entität, die aus dem Dokument extrahiert werden soll, einen Extraktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="293d1-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="293d1-107">In unserem Beispiel möchten wir das  **Startdatum der Inbetriebnahme** für jedes Dokument zu  **Vertragsverlängerungen** , das von dem Modell identifiziert wird, extrahieren.</span><span class="sxs-lookup"><span data-stu-id="293d1-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="293d1-108">Wir möchten in der Dokumentbibliothek eine Ansicht aller Dokumente zu  **Vertragsverlängerungen** und dazu eine Spalte, die den Wert für das **Startdatum der Inbetriebnahme** für jedes Dokument anzeigt.</span><span class="sxs-lookup"><span data-stu-id="293d1-108">We want to be able to see a view in the document library of all **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="293d1-109">Für die Erstellung eines Extraktors benutzen Sie dieselben Dateien, die Sie zuvor hochgeladen haben, um den Klassifizierer zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="293d1-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="293d1-110">Benennen des Extraktors</span><span class="sxs-lookup"><span data-stu-id="293d1-110">Name your extractor</span></span>

1. <span data-ttu-id="293d1-111">Klicken Sie auf der Startseite des Modells auf den Titel **Extraktoren erstellen und trainieren**, und wählen Sie dann**Extraktor trainieren** aus.</span><span class="sxs-lookup"><span data-stu-id="293d1-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="293d1-112">Geben Sie in der Anzeige **Neue Entitätsextraktionsfunktion** den Namen Ihres Extraktors in das Feld **Neuer Extraktorname** ein.</span><span class="sxs-lookup"><span data-stu-id="293d1-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="293d1-113">Vergeben Sie beispielsweise den Namen **Startdatum der Inbetriebnahme**, wenn Sie das Startdatum der Inbetriebnahme aus jedem Dokument zu Vertragsverlängerungen extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="293d1-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="293d1-114">Sie können auch eine bereits erstellte Spalte wiederverwenden (beispielsweise eine Spalte mit verwalteten Metadaten).</span><span class="sxs-lookup"><span data-stu-id="293d1-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
3. <span data-ttu-id="293d1-115">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="293d1-115">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="293d1-116">Hinzufügen einer Beschriftung</span><span class="sxs-lookup"><span data-stu-id="293d1-116">Add a label</span></span>

<span data-ttu-id="293d1-117">Im nächsten Schritt beschriften Sie die Entität, die Sie aus Ihren Beispiel-Schulungsdateien extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="293d1-117">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="293d1-118">Durch das Erstellen eines Extraktors wird die Extraktorseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="293d1-118">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="293d1-119">Dort sehen Sie eine Liste Ihrer Beispieldateien, wobei die erste Datei auf der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="293d1-119">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="293d1-120">Wählen Sie im Viewer die Daten, die aus den Dateien extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="293d1-120">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="293d1-121">Möchten Sie beispielsweise das *Startdatum der Inbetriebnahme* extrahieren, markieren Sie den Datumswert in der ersten Datei (*Montag, 14. Oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="293d1-121">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="293d1-122">Klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="293d1-122">and then click **Save**.</span></span>  <span data-ttu-id="293d1-123">Der Wert sollte in der Liste mit beschrifteten Beispielen in der Spalte **Beschriftung** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="293d1-123">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="293d1-124">Wählen Sie **Nächste Datei** aus, um die Datei automatisch zu speichern und die nächste Datei der Liste im Viewer anzeigen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="293d1-124">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="293d1-125">Oder wählen Sie **Speichern**, und wählen Sie dann eine andere Datei aus der Liste **Beschriftete Beispiele** aus.</span><span class="sxs-lookup"><span data-stu-id="293d1-125">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="293d1-126">Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie dann den gesamten Vorgang, bis Sie die Beschriftung aller fünf Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="293d1-126">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="293d1-128">Wenn Sie die Beschriftung der Dateien abgeschlossen haben, zeigt ein Benachrichtigungsbanner an, dass Sie zur Schulung fortfahren können. </span><span class="sxs-lookup"><span data-stu-id="293d1-128">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="293d1-129">Sie können noch weitere Dokumente beschriften oder mit der Schulung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="293d1-129">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="293d1-130">Hinzufügen einer Erläuterung</span><span class="sxs-lookup"><span data-stu-id="293d1-130">Add an explanation</span></span>

<span data-ttu-id="293d1-131">Für unser Beispiel erstellen wir eine Erläuterung, die Hinweise auf das Format der Entität selbst und auf etwaige Varianten in den Beispieldokumenten gibt.</span><span class="sxs-lookup"><span data-stu-id="293d1-131">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="293d1-132">Beispielsweise kann ein Datum in unterschiedlichen Formaten angegeben werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="293d1-132">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="293d1-133">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="293d1-133">10/14/2019</span></span>
- <span data-ttu-id="293d1-134">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="293d1-134">October 14, 2019</span></span>
- <span data-ttu-id="293d1-135">Montag, 14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="293d1-135">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="293d1-136">Um die Erkennung des *Startdatums der Inbetriebnahme* zu unterstützen, können Sie eine Erläuterung des Musters hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="293d1-136">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="293d1-137">Wählen Sie im Abschnitt Erläuterung **Neu** und geben Sie einen Namen ein (beispielsweise *Datum*).</span><span class="sxs-lookup"><span data-stu-id="293d1-137">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="293d1-138">Wählen Sie als Typ **Musterliste**.</span><span class="sxs-lookup"><span data-stu-id="293d1-138">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="293d1-139">Geben Sie als Wert die Datenvarianten an, wie sie in den Beispieldateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="293d1-139">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="293d1-140">Wenn Sie z. B. Daten im Format 0/00/0000 haben, geben Sie sämtliche Varianten ein, die in Ihren Dokumenten angezeigt werden, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="293d1-140">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="293d1-141">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="293d1-141">0/0/0000</span></span>
    - <span data-ttu-id="293d1-142">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="293d1-142">0/00/0000</span></span>
    - <span data-ttu-id="293d1-143">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="293d1-143">00/0/0000</span></span>
    - <span data-ttu-id="293d1-144">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="293d1-144">00/00/0000</span></span>
4. <span data-ttu-id="293d1-145">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="293d1-145">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="293d1-146">Weitere Informationen zu Erläuterungstypen erhalten Sie unter [Erläuterungstypen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span><span class="sxs-lookup"><span data-stu-id="293d1-146">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="293d1-147">Verwenden der Erläuterungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="293d1-147">Use the Explanation library</span></span>

<span data-ttu-id="293d1-148">Um Erläuterungen für Elemente wie Daten zu erstellen, ist es einfacher [die Erläuterungsbibliothek zu verwenden](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library), als manuell alle Varianten einzugeben.</span><span class="sxs-lookup"><span data-stu-id="293d1-148">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="293d1-149">Die Erläuterungsbibliothek ist eine Zusammenstellung vordefinierter Erläuterungen zu Begriffen und Mustern.</span><span class="sxs-lookup"><span data-stu-id="293d1-149">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="293d1-150">In der Bibliothek wird versucht, alle Formate für häufige Begriffs- oder Musterlisten bereitzustellen, wie z. B. Telefonnummern, Postleitzahlen, und viele andere.</span><span class="sxs-lookup"><span data-stu-id="293d1-150">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="293d1-151">FÜr das Beispiel mit dem *Startdatum der Inbetriebnahme* ist es effizienter, die vordefinierte Erläuterung für das *Datum* in der Erläuterungsbibliothek zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="293d1-151">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="293d1-152">Wählen Sie im **Abschnitt Erläuterung**die Option **Neu**, und wählen Sie dann **Aus der Erläuterungsbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="293d1-152">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="293d1-153">Wählen Sie in der Erläuterungsbibliothek **Datum**.</span><span class="sxs-lookup"><span data-stu-id="293d1-153">From the explanation library, select **Date**.</span></span> <span data-ttu-id="293d1-154">Sie können alle Varianten von Datumsangaben anzeigen lassen, die erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="293d1-154">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="293d1-155">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="293d1-155">Select **Add**.</span></span></br>

    ![Erläuterungsbibliothek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="293d1-157">Auf der Seite **Eine Erläuterung erstellen** werden die Felder automatisch mit Informationen zum *Datum* aus der Erläuterungsbibliothek ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="293d1-157">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="293d1-158">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="293d1-158">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="293d1-160">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="293d1-160">Train the model</span></span> 

<span data-ttu-id="293d1-161">Durch das Speichern Ihrer Erläuterung starten Sie die Schulung.</span><span class="sxs-lookup"><span data-stu-id="293d1-161">Saving your explanation start the training.</span></span> <span data-ttu-id="293d1-162">Wenn Ihr Modell über ausreichend Informationen verfügt, um Daten aus Ihrer Liste beschrifteter Beispiele zu extrahieren, wird jede Datei mit **Übereinstimmung** beschriftet.</span><span class="sxs-lookup"><span data-stu-id="293d1-162">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Übereinstimmung](../media/content-understanding/match2.png) 

<span data-ttu-id="293d1-164">Wenn die Erläuterung nicht genügend Informationen enthält, um die Daten zu finden, die Sie extrahieren möchten, erhält jede Datei die Beschriftung **Keine Übereinstimmung**.</span><span class="sxs-lookup"><span data-stu-id="293d1-164">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="293d1-165">Sie können auf die **Dateien ohne Übereinstimmung** klicken, um weitere Informationen darüber zu erhalten, warum keine Übereinstimmung gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="293d1-165">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="293d1-166">Hinzufügen einer weiteren Erläuterung</span><span class="sxs-lookup"><span data-stu-id="293d1-166">Add another explanation</span></span>

<span data-ttu-id="293d1-167">Häufig ist die fehlende Übereinstimmung ein Hinweis darauf, dass die bereitgestellte Erläuterung nicht ausreichend Informationen zur Verfügung stellte, um das Startdatum für die Inbetriebnahme so zu extrahieren, dass es unseren beschrifteten Dateien entspricht.</span><span class="sxs-lookup"><span data-stu-id="293d1-167">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="293d1-168">Möglicherweise müssen Sie die Erläuterung bearbeiten, oder eine weitere hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="293d1-168">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="293d1-169">In unserem Beispiel können Sie sehen dass die Textzeichenfolge *Startdatum für die Inbetriebnahme von* immer vor dem tatsächlichen Wert steht.</span><span class="sxs-lookup"><span data-stu-id="293d1-169">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="293d1-170">Um die Erkennung des Startdatums der Inbetriebnahme zu unterstützen, müssen Sie eine Erläuterung des Musters hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="293d1-170">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="293d1-171">Wählen Sie im Abschnitt Erläuterung **Neu** und geben Sie einen Namen ein (beispielsweise *Präfixzeichenfolge*).</span><span class="sxs-lookup"><span data-stu-id="293d1-171">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="293d1-172">Wählen Sie als Typ **Begriffsliste**.</span><span class="sxs-lookup"><span data-stu-id="293d1-172">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="293d1-173">Verwenden Sie *Startdatum für die Inbetriebnahme von* als Wert.</span><span class="sxs-lookup"><span data-stu-id="293d1-173">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="293d1-174">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="293d1-174">Select **Save**.</span></span>

    ![Präfixzeichenfolge](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="293d1-176">Erneutes Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="293d1-176">Train the model again</span></span>

<span data-ttu-id="293d1-177">Durch das Speichern der Erläuterung wird die Schulung erneut gestartet. Dieses Mal werden beide Erläuterungen in dem Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="293d1-177">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="293d1-178">Wenn Ihr Modell über ausreichend Informationen verfügt, um Daten aus der Liste beschrifteter Beispiele zu extrahieren, wird jede Datei mit **Übereinstimmung** beschriftet.</span><span class="sxs-lookup"><span data-stu-id="293d1-178">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="293d1-179">Wenn Sie erneut **Keine Übereinstimmung** für Ihre beschrifteten Dateien erhalten, müssen Sie wahrscheinlich eine weitere Erläuterung erstellen, um dem Modell mehr Informationen zu liefern, mithilfe derer es den Dokumenttyp identifizieren kann, oder Änderungen an Ihren bestehenden Erläuterungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="293d1-179">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="293d1-180">Testen Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="293d1-180">Test your model</span></span>

<span data-ttu-id="293d1-181">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie nun das Modell für die restlichen nicht beschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="293d1-181">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="293d1-182">Das ist ein optionaler aber nützlicher Schritt, um die "Tauglichkeit" oder die Bereitschaft des Modells vor seiner Verwendung zu bewerten. Dazu wird es an Dateien getestet, die das Modell noch nie gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="293d1-182">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="293d1-183">Klicken Sie auf der Startseite des Modells auf die Registerkarte **Test**. Dadurch wird das Modell für Ihre nicht beschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="293d1-183">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="293d1-184">In der Liste der **Testdateien** werden Ihre Beispieldateien angezeigt, um zu zeigen, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="293d1-184">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="293d1-185">Mithilfe dieser Informationen können Sie ermitteln, wie effektiv Ihr Klassifizierer bei der Identifizierung Ihrer Dokumente ist.</span><span class="sxs-lookup"><span data-stu-id="293d1-185">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen Ihrer Dateien](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="293d1-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="293d1-187">See Also</span></span>
[<span data-ttu-id="293d1-188">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="293d1-188">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="293d1-189">Beschreibungstypen</span><span class="sxs-lookup"><span data-stu-id="293d1-189">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="293d1-190">Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="293d1-190">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="293d1-191">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="293d1-191">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="293d1-192">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="293d1-192">Apply a model</span></span>](apply-a-model.md) 
