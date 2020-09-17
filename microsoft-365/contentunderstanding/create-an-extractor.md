---
title: Erstellen eines Extraktors (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Erstellen eines Extraktions Moduls
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950084"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="c4692-103">Erstellen eines Extraktors (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c4692-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="c4692-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="c4692-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c4692-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c4692-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="c4692-106">Bevor oder nachdem Sie ein Klassifizierungsmodell erstellt haben, um die Identifizierung und Klassifizierung bestimmter Dokumenttypen zu automatisieren, können Sie dem Modell optional Extraktoren hinzufügen, um bestimmte Informationen aus diesen Dokumenten herauszuziehen.</span><span class="sxs-lookup"><span data-stu-id="c4692-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="c4692-107">Möglicherweise möchten Sie, dass Ihr Modell nicht nur alle *Vertrags Erneuerungs* Dokumente identifiziert, die Ihrer Dokumentbibliothek hinzugefügt werden, sondern auch das *Start Datum des Diensts* für jedes Dokument als Spalte in der Dokumentbibliothek anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c4692-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="c4692-108">Sie müssen für jede Entität im Dokument, die extrahiert werden soll, einen Extraktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4692-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="c4692-109">In unserem Beispiel möchten wir das *Start Datum des Diensts* für jedes *Vertrags Erneuerungs* Dokument extrahieren, das vom Modell identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c4692-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="c4692-110">Wir möchten in der Lage sein, eine Ansicht in der Dokumentbibliothek aller *Vertrags Erneuerungs* Dokumente mit einer Spalte anzuzeigen, in der der Wert des Dienst Anfangsdatums jedes Dokuments angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4692-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="c4692-111">Vor dem Erstellen eines Extraktors müssen Sie [Ihre Beispieldateien hinzufügen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) , die Sie beim Trainieren des Modells unterstützen müssen, um die Informationen zu identifizieren, die extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c4692-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="c4692-112">Verwenden Sie die gleichen Beispieldateien, die Sie zum Erstellen ihrer Klassifizierung verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c4692-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="c4692-113">Nennen Sie den Extraktor</span><span class="sxs-lookup"><span data-stu-id="c4692-113">Name your extractor</span></span>

1. <span data-ttu-id="c4692-114">Klicken Sie auf der Modell Startseite in der Kachel **Erstellen und trainieren von Extraktions** Modulen auf **Zug-Extraktor**.</span><span class="sxs-lookup"><span data-stu-id="c4692-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="c4692-115">Geben Sie auf dem Bildschirm **neuer Entitäts Extraktions** Modul den Namen Ihres Extraktors in das Feld **neuer Extraktions Name** ein.</span><span class="sxs-lookup"><span data-stu-id="c4692-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="c4692-116">Beispielsweise können wir den **Starttermin** für den IT-Dienst benennen, wenn der Starttermin des Diensts aus jedem Vertrags Erneuerungs Dokument extrahiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4692-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="c4692-117">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c4692-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="c4692-118">Hinzufügen einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="c4692-118">Add a label</span></span>

<span data-ttu-id="c4692-119">Im nächsten Schritt bezeichnen Sie die Informationen, die Sie extrahieren möchten, in ihren Übungsbeispiel Dateien.</span><span class="sxs-lookup"><span data-stu-id="c4692-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="c4692-120">Beim Erstellen des Extraktors wird die Extraktions Seite geöffnet, auf der Sie eine Liste mit den Beispieldateien sehen, wobei die erste Datei in der Liste im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4692-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="c4692-121">Wählen Sie im Viewer die Daten aus, die Sie aus den Dateien extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c4692-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="c4692-122">Wenn Sie beispielsweise das *Datum des Start Diensts*extrahieren möchten, markieren Sie den Datumswert in der ersten Datei (*Montag, Oktober 14, 2019*).</span><span class="sxs-lookup"><span data-stu-id="c4692-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="c4692-123">Klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c4692-123">Then click **Save**.</span></span>  <span data-ttu-id="c4692-124">Der Wert für die Datei wird in der Liste mit den beschrifteten Beispielen unter der Spalte **Label** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4692-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="c4692-125">Wählen Sie **nächste Datei** zum automatischen Speichern aus, und öffnen Sie die nächste Datei in der Liste im Viewer, oder wählen Sie **Speichern** aus, und wählen Sie in der Liste mit den **beschrifteten Beispielen** eine andere Datei aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="c4692-126">Wiederholen Sie im Viewer die Schritte 1 und 2, und gehen Sie so vor, bis Sie die Beschriftung in fünf Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="c4692-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Erweiterte Einstellungen](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="c4692-128">Hinzufügen eines negativen Beispiels</span><span class="sxs-lookup"><span data-stu-id="c4692-128">Add a negative example</span></span>

<span data-ttu-id="c4692-129">Ähnlich wie beim Erstellen einer Klassifizierung eine negative Beispieldatei hinzugefügt werden soll, müssen Sie ein negatives Beispiel für den Extraktor hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4692-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="c4692-130">Für unser Beispiel sollte es eine Datei sein, die keinen Start Datumswert des Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="c4692-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="c4692-131">Wählen Sie in der Liste mit den **beschrifteten Beispielen** ein negatives Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="c4692-132">Wählen Sie im Viewer oben im Artikel **keine Beschriftung vorhanden**aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="c4692-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c4692-133">Click **Save**.</span></span>
 
<span data-ttu-id="c4692-134">Nachdem Sie fünf Dateien markiert haben, wird ein Benachrichtigungs Banner angezeigt, in dem Sie informiert werden, dass Sie zur Schulung übergehen möchten.</span><span class="sxs-lookup"><span data-stu-id="c4692-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="c4692-135">Sie können mehr Dokumente auswählen oder zur Schulung wechseln.</span><span class="sxs-lookup"><span data-stu-id="c4692-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="c4692-136">Hinzufügen einer Erklärung</span><span class="sxs-lookup"><span data-stu-id="c4692-136">Add an explanation</span></span>

<span data-ttu-id="c4692-137">Für unser Beispiel werden wir eine Erklärung erstellen, die einen Hinweis auf das Entitäts Format selbst und in den Beispiel Dokumenten möglicherweise Variationen enthält.</span><span class="sxs-lookup"><span data-stu-id="c4692-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="c4692-138">Beispielsweise kann ein Date-Wert in einer Reihe von unterschiedlichen Formaten vorliegen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="c4692-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="c4692-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="c4692-139">10/14/2019</span></span>
- <span data-ttu-id="c4692-140">14. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="c4692-140">October 14, 2019</span></span>
- <span data-ttu-id="c4692-141">Montag, Oktober 14, 2019</span><span class="sxs-lookup"><span data-stu-id="c4692-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="c4692-142">Um den *Start Termin des Diensts* zu ermitteln, können Sie eine Mustererklärung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4692-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="c4692-143">Wählen Sie im Abschnitt Erklärung die Option **neu**aus, und geben Sie dann einen Namen ein (beispielsweise *Date*).</span><span class="sxs-lookup"><span data-stu-id="c4692-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="c4692-144">Wählen Sie für den Typ die Option **Musterliste**aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="c4692-145">Für den Wert müssen Sie die Datums Variation angeben, die in den Beispieldateien angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4692-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="c4692-146">Wenn beispielsweise Datumsformate als 0/00/0000 angezeigt werden, geben Sie alle Variationen ein, die in Ihren Dokumenten angezeigt werden können, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="c4692-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="c4692-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="c4692-147">0/0/0000</span></span>
    - <span data-ttu-id="c4692-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="c4692-148">0/00/0000</span></span>
    - <span data-ttu-id="c4692-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="c4692-149">00/0/0000</span></span>
    - <span data-ttu-id="c4692-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="c4692-150">00/00/0000</span></span>
4. <span data-ttu-id="c4692-151">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="c4692-152">Verwenden der Erklärungs Bibliothek</span><span class="sxs-lookup"><span data-stu-id="c4692-152">Use the Explanation library</span></span>

<span data-ttu-id="c4692-153">Für das Erstellen von Erläuterungen zu Dingen wie Datumsangaben ist es wesentlich einfacher, die Erklärungs Bibliothek zu verwenden, als alle Variationen manuell einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c4692-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="c4692-154">Die Erklärungs Bibliothek ist ein Satz von vordefinierten Phrasen-und Muster Erläuterungen.</span><span class="sxs-lookup"><span data-stu-id="c4692-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="c4692-155">Die Bibliothek versucht, alle Formate für allgemeine Phrasen-oder Muster Listen bereitzustellen, wie Datumsangaben, Telefonnummern, Postleitzahlen und viele andere.</span><span class="sxs-lookup"><span data-stu-id="c4692-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="c4692-156">Für unser Beispiel zum *Start Datum von Diensten* ist es effizienter, die vordefinierte Erläuterung für *Date* in der Erklärungs Bibliothek zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="c4692-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="c4692-157">Wählen Sie im **Abschnitt Erläuterung**die Option **neu**aus, und wählen Sie dann **aus Erklärungs Bibliothek**.</span><span class="sxs-lookup"><span data-stu-id="c4692-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="c4692-158">Wählen Sie in der Erklärungs Bibliothek **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="c4692-159">Sie können alle Datums Variationen anzeigen, die erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c4692-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="c4692-160">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c4692-160">Select **Add**.</span></span></br>

    ![Erklärungs Bibliothek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="c4692-162">Auf der Seite **eine Erklärung erstellen** werden die *Datums* Angaben aus der Erklärungs Bibliothek die Felder automatisch ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="c4692-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="c4692-163">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-163">Select **Save**.</span></span></br>

    ![Erklärungs Bibliothek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="c4692-165">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="c4692-165">Train the model</span></span> 

<span data-ttu-id="c4692-166">Wenn Sie Ihre Erklärung speichern, wird die Schulung gestartet.</span><span class="sxs-lookup"><span data-stu-id="c4692-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="c4692-167">Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus ihren beschrifteten Beispieldateien zu extrahieren, wird jede Datei mit der Bezeichnung **Match**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4692-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Erklärungs Bibliothek](../media/content-understanding/match2.png) 

<span data-ttu-id="c4692-169">Wenn die Erklärung nicht über genügend Informationen verfügt, um die Daten zu finden, die Sie extrahieren möchten, wird jede Datei mit einem **Missverhältnis**versehen.</span><span class="sxs-lookup"><span data-stu-id="c4692-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="c4692-170">Sie können auf die nicht übereinstimmenden Dateien klicken, um weitere Informationen dazu zu erhalten, warum ein Konflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c4692-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="c4692-171">Hinzufügen einer weiteren Erläuterung</span><span class="sxs-lookup"><span data-stu-id="c4692-171">Add another explanation</span></span>

<span data-ttu-id="c4692-172">Häufig ist die Übereinstimmung ein Hinweis darauf, dass die von uns angegebene Erklärung nicht genügend Informationen bereitgestellt hat, um den Wert für das Startdatum des Diensts zu extrahieren und mit unseren beschrifteten Dateien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c4692-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="c4692-173">Möglicherweise müssen Sie es bearbeiten oder eine weitere Erklärung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4692-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="c4692-174">Für unser Beispiel stellen wir fest, dass der *anfangs Dienst Datum* der Textzeichenfolge immer dem tatsächlichen Wert vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="c4692-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="c4692-175">Um den Start Termin des Diensts zu identifizieren, können wir eine Phrasen Erklärung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4692-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="c4692-176">Wählen Sie im Abschnitt Erklärung die Option **neu**aus, und geben Sie dann einen Namen ein (beispielsweise *Präfixzeichenfolge*).</span><span class="sxs-lookup"><span data-stu-id="c4692-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="c4692-177">Wählen Sie für den Typ die Option **Phrase List**aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="c4692-178">Verwenden Sie das *Start Datum des Diensts* als Wert.</span><span class="sxs-lookup"><span data-stu-id="c4692-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="c4692-179">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c4692-179">Select **Save**.</span></span>

    ![Erklärungs Bibliothek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="c4692-181">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="c4692-181">Train the model</span></span>

<span data-ttu-id="c4692-182">Wenn Sie Ihre Erklärung speichern, wird das Training erneut gestartet, wobei beide Erläuterungen in unserem Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4692-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="c4692-183">Wenn Ihr Modell über genügend Informationen verfügt, um die Daten aus ihren beschrifteten Beispieldateien zu extrahieren, wird jede Datei mit der Bezeichnung **Match**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4692-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="c4692-184">Wenn Sie erneut eine **Übereinstimmung** bei ihren beschrifteten Dateien erhalten, müssen Sie möglicherweise eine weitere Erklärung erstellen, um das Modell mit weiteren Informationen zum Identifizieren des Dokumenttyps zu versehen oder um Änderungen an Ihren vorhandenen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c4692-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="c4692-185">Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="c4692-185">Test your model</span></span>

<span data-ttu-id="c4692-186">Wenn Sie eine Übereinstimmung mit den beschrifteten Beispieldateien erhalten haben, können Sie Ihr Modell nun auf ihren restlichen unbeschrifteten Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="c4692-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="c4692-187">Klicken Sie auf der Modell Startseite auf die Registerkarte **Test** .  Dadurch wird das Modell für Ihre unbeschrifteten Beispieldateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4692-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="c4692-188">In der Liste **Test Dateien** werden Ihre Beispieldateien angezeigt, und es wird angezeigt, ob das Modell die benötigten Informationen extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="c4692-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="c4692-189">Anhand dieser Informationen können Sie die Effektivität ihrer Klassifizierung bei der Identifizierung Ihrer Dokumente ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c4692-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen der Dateien](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="c4692-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4692-191">See Also</span></span>
  




