---
title: Erstellen eines Extraktions Moduls
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
description: Erfahren Sie, wie Sie einen Extraktor in Microsoft SharePoint Syntex erstellen.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295456"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="8d2e9-103">Erstellen eines Extraktors (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="8d2e9-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="8d2e9-104">Der Inhalt in diesem Artikel ist für die Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="8d2e9-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="8d2e9-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="8d2e9-106">Bevor oder nachdem Sie ein Klassifizierungsmodell erstellt haben, um die Identifizierung und Klassifizierung bestimmter Dokumenttypen zu automatisieren, können Sie dem Modell optional Extraktoren hinzufügen, um bestimmte Informationen aus diesen Dokumenten herauszuziehen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="8d2e9-107">Möglicherweise möchten Sie, dass Ihr Modell nicht nur alle *Vertrags Erneuerungs* Dokumente identifiziert, die Ihrer Dokumentbibliothek hinzugefügt wurden, sondern auch das *Start Datum des Diensts* für jedes Dokument als Spalte in der Dokumentbibliothek anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="8d2e9-108">Sie müssen für jede Entität im Dokument, die extrahiert werden soll, einen Extraktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="8d2e9-109">Im Beispiel möchten Sie das *Start Datum des Diensts* für jedes *Vertrags Erneuerungs* Dokument extrahieren, das vom Modell identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="8d2e9-110">Dies muss geschehen, wenn Sie eine Ansicht in der Dokumentbibliothek aller *Vertrags Erneuerungs* Dokumente mit einer Spalte anzeigen möchten, die den Wert für das Start Datum des Diensts für jedes Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="8d2e9-111">Vor dem Erstellen eines Extraktors müssen Sie [Ihre Beispieldateien hinzufügen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) , um das Modell zu unterstützen, um die Informationen zu identifizieren, die extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="8d2e9-112">Verwenden Sie die gleichen Beispieldateien, die Sie zum Erstellen ihrer Klassifizierung verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="8d2e9-113">Nennen Sie den Extraktor</span><span class="sxs-lookup"><span data-stu-id="8d2e9-113">Name your extractor</span></span>

1. <span data-ttu-id="8d2e9-114">Klicken Sie auf der Modell Startseite in der Kachel **Erstellen und trainieren von Extraktions** Modulen auf **Train Extractor**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="8d2e9-115">Geben Sie auf dem Bildschirm **neuer Entitäts Extraktions** Modul den Namen Ihres Extraktors in das Feld **neuer Extraktions Name** ein.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="8d2e9-116">Nennen Sie beispielsweise den **Starttermin** für den IT-Dienst, wenn Sie den Starttermin des Diensts aus jedem Vertrags Erneuerungs Dokument extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="8d2e9-117">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="8d2e9-118">Hinzufügen einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="8d2e9-118">Add a label</span></span>

<span data-ttu-id="8d2e9-119">Im nächsten Schritt bezeichnen Sie die Informationen, die Sie extrahieren möchten, in den Beispiel Schulungsdateien.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="8d2e9-120">Durch Erstellen des Extraktions Moduls wird die Extraktions Seite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="8d2e9-121">Hier sehen Sie eine Liste der Beispieldateien, wobei die erste Datei in der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="8d2e9-122">Wählen Sie im Viewer die Daten aus, die Sie aus den Dateien extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="8d2e9-123">Wenn Sie beispielsweise den *Start Dienst Termin*extrahieren möchten, markieren Sie den Datumswert in der ersten Datei (*Montag, Oktober 14, 2019*).</span><span class="sxs-lookup"><span data-stu-id="8d2e9-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="8d2e9-124">und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-124">and then click **Save**.</span></span>  <span data-ttu-id="8d2e9-125">Sie sollten den Wert aus der Datei in der Liste mit den beschrifteten Beispielen unter der Spalte **Label** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="8d2e9-126">Wählen Sie die Option **nächste Datei** zum automatischen Speichern aus, und öffnen Sie die nächste Datei in der Liste im Viewer.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="8d2e9-127">Oder wählen Sie **Speichern** aus, und wählen Sie dann in der Liste mit den **beschrifteten Beispielen** eine andere Datei aus.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="8d2e9-128">Wiederholen Sie im Viewer die Schritte 1 und 2, und wiederholen Sie den Vorgang, bis Sie die Beschriftung in allen fünf Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="8d2e9-130">Hinzufügen eines negativen Beispiels</span><span class="sxs-lookup"><span data-stu-id="8d2e9-130">Add a negative example</span></span>

<span data-ttu-id="8d2e9-131">Ähnlich wie beim Erstellen einer Klassifizierung eine negative Beispieldatei hinzugefügt wird, müssen Sie ein negatives Beispiel für den Extraktor hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="8d2e9-132">Es sollte sich um eine Datei handeln, die keinen Date-Wert vom "Dienst Start" enthält.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="8d2e9-133">Wählen Sie in der Liste mit den **beschrifteten Beispielen** ein negatives Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="8d2e9-134">Wählen Sie im Viewer oben im Artikel **keine Beschriftung vorhanden**aus.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="8d2e9-135">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-135">Click **Save**.</span></span>
 
<span data-ttu-id="8d2e9-136">Nachdem Sie fünf Dateien markiert haben, wird ein Benachrichtigungs Banner angezeigt, in dem Sie informiert werden, dass Sie zur Schulung übergehen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="8d2e9-137">Sie können mehr Dokumente auswählen oder zur Schulung wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="8d2e9-138">Hinzufügen einer Erklärung</span><span class="sxs-lookup"><span data-stu-id="8d2e9-138">Add an explanation</span></span>

<span data-ttu-id="8d2e9-139">Für das Beispiel erstellen Sie eine Erläuterung, die einen Hinweis auf das Entitäts Format selbst und Variationen in den Beispiel Dokumenten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="8d2e9-140">Beispielsweise kann ein Date-Wert in einer Reihe von unterschiedlichen Formaten vorliegen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="8d2e9-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="8d2e9-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="8d2e9-141">10/14/2019</span></span>
- <span data-ttu-id="8d2e9-142">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="8d2e9-142">October 14, 2019</span></span>
- <span data-ttu-id="8d2e9-143">Montag, Oktober 14, 2019</span><span class="sxs-lookup"><span data-stu-id="8d2e9-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="8d2e9-144">Um den *Start Termin des Diensts* zu identifizieren, erstellen Sie eine Mustererklärung.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="8d2e9-145">Wählen Sie im Abschnitt Erklärung die Option **neu** aus, und geben Sie einen Namen ein (beispielsweise *Date*).</span><span class="sxs-lookup"><span data-stu-id="8d2e9-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="8d2e9-146">Wählen Sie unter Typ die Option **Musterliste**aus.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="8d2e9-147">Geben Sie als Wert die Datums Variation so an, wie Sie in den Beispieldateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="8d2e9-148">Wenn beispielsweise Datumsformate als 0/00/0000 angezeigt werden, geben Sie alle Variationen ein, die in Ihren Dokumenten angezeigt werden, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="8d2e9-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="8d2e9-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="8d2e9-149">0/0/0000</span></span>
    - <span data-ttu-id="8d2e9-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="8d2e9-150">0/00/0000</span></span>
    - <span data-ttu-id="8d2e9-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="8d2e9-151">00/0/0000</span></span>
    - <span data-ttu-id="8d2e9-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="8d2e9-152">00/00/0000</span></span>
4. <span data-ttu-id="8d2e9-153">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="8d2e9-154">Verwenden der Erklärungs Bibliothek</span><span class="sxs-lookup"><span data-stu-id="8d2e9-154">Use the Explanation library</span></span>

<span data-ttu-id="8d2e9-155">Zum Erstellen von Erläuterungen für Elemente wie Datumsangaben ist es einfacher, die Erklärungs Bibliothek zu verwenden, als alle Variationen manuell einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="8d2e9-156">Die Erklärungs Bibliothek ist ein Satz von vordefinierten Phrasen-und Muster Erläuterungen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="8d2e9-157">Die Bibliothek bietet alle Formate für allgemeine Phrasen-oder Muster Listen wie Datumsangaben, Telefonnummern, Postleitzahlen usw.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="8d2e9-158">Für das Beispiel für den *Start Termin des Diensts* ist es effizienter, die vordefinierte Erläuterung für *Date* in der Erklärungs Bibliothek zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="8d2e9-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="8d2e9-159">Wählen Sie im **Abschnitt Erklärung**die Option **neu**aus, und wählen Sie dann **aus Erklärungs Bibliothek aus**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="8d2e9-160">Wählen Sie in der Erklärungs Bibliothek **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="8d2e9-161">Sie können alle erkannten Datums Variationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="8d2e9-162">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-162">Select **Add**.</span></span></br>

    ![Erklärungs Bibliothek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="8d2e9-164">Auf der Seite **Erklärung erstellen** werden die Felder in den *Datums* Angaben aus der Erklärungs Bibliothek automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="8d2e9-165">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-165">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="8d2e9-167">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="8d2e9-167">Train the model</span></span> 

<span data-ttu-id="8d2e9-168">Speichern Ihrer Erklärung beginnen Sie das Training.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-168">Saving your explanation start the training.</span></span> <span data-ttu-id="8d2e9-169">Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus ihren beschrifteten Beispieldateien zu extrahieren, wird jede Datei mit der Bezeichnung **Match**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Vergleich](../media/content-understanding/match2.png) 

<span data-ttu-id="8d2e9-171">Wenn die Erklärung nicht über genügend Informationen verfügt, um die Daten zu finden, die Sie extrahieren möchten, wird jede Datei mit einem **Missverhältnis**versehen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="8d2e9-172">Sie können auf die nicht **übereinstimmenden** Dateien klicken, um weitere Informationen dazu zu erhalten, warum ein Konflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="8d2e9-173">Hinzufügen einer weiteren Erläuterung</span><span class="sxs-lookup"><span data-stu-id="8d2e9-173">Add another explanation</span></span>

<span data-ttu-id="8d2e9-174">Häufig ist die Übereinstimmung ein Hinweis darauf, dass die von uns angegebene Erklärung nicht genügend Informationen bereitgestellt hat, um den Wert für das Startdatum des Diensts zu extrahieren und mit unseren beschrifteten Dateien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="8d2e9-175">Möglicherweise müssen Sie es bearbeiten oder eine weitere Erklärung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="8d2e9-176">Beachten Sie für das Beispiel, dass der *anfangs Dienst Datum* der Textzeichenfolge immer dem tatsächlichen Wert vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="8d2e9-177">Um den Start Termin des Diensts zu identifizieren, müssen Sie eine Phrasen Erklärung erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="8d2e9-178">Wählen Sie im Abschnitt Erklärung die Option **neu**aus, und geben Sie dann einen Namen ein (beispielsweise *Präfixzeichenfolge*).</span><span class="sxs-lookup"><span data-stu-id="8d2e9-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="8d2e9-179">Wählen Sie für den Typ die Option **Phrase List**aus.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="8d2e9-180">Verwenden Sie das *Start Datum des Diensts* als Wert.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="8d2e9-181">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-181">Select **Save**.</span></span>

    ![Präfixzeichenfolge](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="8d2e9-183">Modell erneut trainieren</span><span class="sxs-lookup"><span data-stu-id="8d2e9-183">Train the model again</span></span>

<span data-ttu-id="8d2e9-184">Wenn Sie die Erläuterung speichern, wird das Training erneut gestartet, wobei beide Erläuterungen im Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="8d2e9-185">Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus den beschrifteten Beispieldateien zu extrahieren, sehen Sie jede Datei mit der Bezeichnung **Match**.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="8d2e9-186">Wenn Sie erneut eine **Übereinstimmung** bei ihren beschrifteten Dateien erhalten, müssen Sie wahrscheinlich eine weitere Erklärung erstellen, um das Modell mit weiteren Informationen zum Identifizieren des Dokumenttyps zu versehen oder Änderungen am Beispielmodell vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="8d2e9-187">Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="8d2e9-187">Test your model</span></span>

<span data-ttu-id="8d2e9-188">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten, können Sie Ihr Modell nun auf den verbleibenden unbeschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="8d2e9-189">Klicken Sie auf der Modell Startseite auf die Registerkarte **Test** .  Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="8d2e9-190">In der Liste **Test Dateien** werden Ihre Beispieldateien angezeigt, um anzuzeigen, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="8d2e9-191">Anhand dieser Informationen können Sie die Effektivität ihrer Klassifizierung bei der Identifizierung Ihrer Dokumente ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8d2e9-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen der Dateien](../media/content-understanding/test-filies-extractor.png) 
