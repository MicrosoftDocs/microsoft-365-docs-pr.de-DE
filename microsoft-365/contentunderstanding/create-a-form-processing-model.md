---
title: Erstellen eines Formularverarbeitungsmodells
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Erstellen Sie ein Formularverarbeitungsmodell in Microsoft SharePoint Syntex.
ms.openlocfilehash: 27e80a7b3626170e45ceaa55f1269e50d8fdab9e
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337265"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d15d2-103">Erstellen eines Formularverarbeitungsmodells in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d15d2-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>


<span data-ttu-id="d15d2-104">Mithilfe von [AI Builder](https://docs.microsoft.com/ai-builder/overview) – ein Feature in Microsoft PowerApps – können SharePoint Syntex-Benutzer ein [Formularverarbeitungsmodell](form-processing-overview.md) direkt aus einer SharePoint-Dokumentbibliothek erstellen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="d15d2-105">Die Erstellung eines Formularverarbeitungsmodells umfasst folgende Schritte:</span><span class="sxs-lookup"><span data-stu-id="d15d2-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="d15d2-106">Schritt 1: Erstellen des Formularverarbeitungsmodells zur Erstellung des Inhaltstyps</span><span class="sxs-lookup"><span data-stu-id="d15d2-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="d15d2-107">Schritt 2: Hinzufügen und Analysieren von Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="d15d2-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="d15d2-108">Schritt 3: Auswählen der Formularfelder</span><span class="sxs-lookup"><span data-stu-id="d15d2-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="d15d2-109">Schritt 4: Trainieren und Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="d15d2-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="d15d2-110">Schritt 5: Veröffentlichen des Modells</span><span class="sxs-lookup"><span data-stu-id="d15d2-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="d15d2-111">Schritt 6: Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="d15d2-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="d15d2-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d15d2-112">Requirements</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>


<span data-ttu-id="d15d2-113">Formularverarbeitungsmodelle können nur in SharePoint-Dokumentbibliotheken mit entsprechend aktivierter Funktion erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="d15d2-114">Wenn die Formularverarbeitung aktiviert ist, wird in Ihrer Dokumentbibliothek die **AI Builder**-Option **"Formularverarbeitungsmodell erstellen"** im Menü **Automatisieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d15d2-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="d15d2-115">Wenn die Verarbeitung in Ihrer Dokumentbibliothek aktiviert sein muss, müssen Sie sich hierfür an Ihren SharePoint-Administrator wenden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Erstellen eines AI Builder-Modells](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="d15d2-117">Schritt 1: Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="d15d2-117">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="d15d2-118">Der erste Schritt zum Erstellen eines Formularverarbeitungsmodells besteht darin, es zu benennen, den neuen Inhaltstyp zu definieren und eine neue Dokumentbibliotheksansicht dafür zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="d15d2-119">Wählen Sie in der Dokumentbibliothek das Menü **Automatisieren**, dann **AI Builder** und anschließend **Formularverarbeitungsmodell erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Ein Modell erstellen](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="d15d2-121">Geben Sie im Bereich **Neues Formularverarbeitungsmodell** im Feld  **Name** einen Namen für das Modell ein (z. B. *Aufträge*).</span><span class="sxs-lookup"><span data-stu-id="d15d2-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Neues Formularverarbeitungsmodell](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="d15d2-123">Bei der Erstellung eines Formularverarbeitungsmodells erstellen Sie einen neuen SharePoint-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="d15d2-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="d15d2-124">Ein SharePoint-Inhaltstyp stellt eine Kategorie von Dokumenten dar, die gemeinsame Merkmale aufweisen und eine Reihe von Spalten oder Metadateneigenschaften für diesen bestimmten Inhalt gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="d15d2-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="d15d2-125">SharePoint-Inhaltstypen werden über den [Inhaltstypen-Katalog]() verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d15d2-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="d15d2-126">Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Inhaltstyp im SharePoint-Inhaltstypen-Katalog zuordnen möchten, um dessen Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="d15d2-127">Ihr Modell erstellt in Ihrer Dokumentbibliothek eine neue Ansicht für die extrahierten Daten.</span><span class="sxs-lookup"><span data-stu-id="d15d2-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="d15d2-128">Wenn Sie nicht möchten, dass sie in der Standardansicht angezeigt werden, deaktivieren Sie die Option **Ansicht als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="d15d2-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="d15d2-129">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="d15d2-130">Schritt 2: Hinzufügen und Analysieren von Dokumenten</span><span class="sxs-lookup"><span data-stu-id="d15d2-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="d15d2-131">Nachdem Sie Ihr neues Formularverarbeitungsmodell erstellt haben, öffnet Ihr Browser eine neue PowerApps AI Builder-Formularverarbeitungsmodellseite.</span><span class="sxs-lookup"><span data-stu-id="d15d2-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="d15d2-132">Auf dieser Seite können Sie Ihre Beispieldokumente hinzufügen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="d15d2-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="d15d2-133">Informationen zur Auswahl der Beispieldateien finden Sie unter [Eingabedokumente für Formularverarbeitungsmodelle – Anforderungen und Optimierungstipps ](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="d15d2-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="d15d2-135">Wählen Sie **Dokumente hinzufügen** aus, um mit dem Hinzufügen von analysierten Beispieldokumenten zu beginnen, um die benannten extrahierbaren Wertpaare zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d15d2-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="d15d2-136">Sie können dann **Von lokalem Speicher hochladen**, **SharePoint** oder **Azure-BLOB-Speicher** auswählen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="d15d2-137">Für das Trainieren müssen Sie mindestens fünf Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="d15d2-138">Wählen Sie nach dem Hinzufügen von Dateien **Analysieren** aus, um nach Informationen zu suchen, die alle Dateien aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="d15d2-139">Diese Analyse kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="d15d2-139">This may take several minutes to complete.</span></span></br> 
 
    ![Dateien analysieren](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="d15d2-141">Nachdem die Dateien analysiert wurden, wählen Sie auf der Seite **Zu speichernde Formularfelder auswählen** die Datei aus, um die gefundenen Felder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Formularfelder auswählen](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="d15d2-143">Schritt 3: Auswählen der Formularfelder</span><span class="sxs-lookup"><span data-stu-id="d15d2-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="d15d2-144">Nach der Analyse der Dokumente auf Felder hin werden die gefundenen Felder angezeigt, und Sie können jene auswählen, die gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="d15d2-145">Gespeicherte Felder werden in der Dokumentbibliotheksansicht des Modells als Spalten angezeigt, und darin werden die aus den einzelnen Dokumenten extrahierten Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d15d2-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="d15d2-146">Auf der nächsten Seite wird eine Ihrer Beispieldateien angezeigt, und es sind alle gemeinsamen Felder hervorgehoben, die vom System automatisch erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Seite "Felder auswählen"](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="d15d2-148">Wählen Sie die Felder aus, die gespeichert werden sollen, und aktivieren Sie das Kontrollkästchen, um Ihre Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="d15d2-149">Wählen Sie z. B. im Auftragsmodell die Felder *Datum*, *Auftrag* und *Gesamtbetrag* aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="d15d2-150">Sie können ein ausgewähltes Feld auch umbenennen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Auftragsnummer auswählen](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="d15d2-152">Sie können ein Feld, das während einer Analyse nicht erkannt wurde, trotzdem hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="d15d2-153">Markieren Sie die Informationen, die extrahiert werden sollen, und geben Sie im Feld "Name" den gewünschten Namen ein.</span><span class="sxs-lookup"><span data-stu-id="d15d2-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="d15d2-154">Aktivieren Sie dann das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-154">Then select the check box.</span></span> <span data-ttu-id="d15d2-155">Beachten Sie, dass Sie nicht erkannte Felder in den verbleibenden Beispieldateien bestätigen müssen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="d15d2-156">Klicken Sie nach der Auswahl der zu speichernden Felder auf **Felder bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="d15d2-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Bestätigen von Feldern nach deren Auswahl](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="d15d2-158">Auf der Seite **Zu speichernde Formularfelder auswählen** wird die Anzahl der von Ihnen ausgewählten Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d15d2-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="d15d2-159">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="d15d2-160">Schritt 4: Trainieren und Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="d15d2-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="d15d2-161">Nachdem Sie die zu speichernden Felder ausgewählt haben, können Sie auf der Seite **Modellzusammenfassung** das Modell trainieren und testen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="d15d2-162">Auf der Seite **Modellzusammenfassung** werden die gespeicherten Felder im Abschnitt **Ausgewählte Felder** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d15d2-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="d15d2-163">Wählen Sie **Trainieren** aus, um das Trainieren Ihrer Beispieldateien zu starten.</span><span class="sxs-lookup"><span data-stu-id="d15d2-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="d15d2-164">Dieser Vorgang kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="d15d2-164">Note that this may take a few minutes to complete.</span></span></br>

     ![Trainieren der Felder ausgewählt](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="d15d2-166">Wenn die Meldung angezeigt wird, dass das Trainieren abgeschlossen ist, wählen Sie **Zur Seite "Modelldetails" wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="d15d2-167">Auf der Seite **Modelldetails** können Sie **Schnelltest** auswählen, um das Modell zu testen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="d15d2-168">Dabei können Sie Dateien auf die Seite ziehen um zu sehen, ob die Felder erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Bestätigen von Feldern](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="d15d2-170">Wenn die Meldung angezeigt wird, dass das Trainieren abgeschlossen ist, wählen Sie **Zur Seite "Modelldetails" wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="d15d2-171">Wählen Sie auf der Seite **Modelldetails** die Option **Schnelltest** aus, um das Modell zu testen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="d15d2-172">Dabei können Sie Dateien auf die Seite ziehen um zu sehen, ob die Felder erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="d15d2-173">Schritt 5: Veröffentlichen des Modells</span><span class="sxs-lookup"><span data-stu-id="d15d2-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="d15d2-174">Wenn Sie mit den Ergebnissen Ihres Modells zufrieden sind, wählen Sie **Veröffentlichen** aus, um es verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="d15d2-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="d15d2-175">Wählen Sie nach der Veröffentlichung des Modells **Modell verwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="d15d2-176">Dadurch wird ein in Ihrer SharePoint-Dokumentbibliothek ausführbarer PowerAutomate-Ablauf erstellt, bei dem die im Modell erkannten Felder extrahiert werden. Wählen Sie anschließend **Ablauf erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="d15d2-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="d15d2-177">Nach Abschluss des Vorgangs wird die folgende Meldung angezeigt: **Ablauf wurde erstellt**.</span><span class="sxs-lookup"><span data-stu-id="d15d2-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="d15d2-178">Schritt 6: Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="d15d2-178">Step 6: Use your model</span></span>

<span data-ttu-id="d15d2-179">Nach der Veröffentlichung des Modells und der Erstellung des PowerAutomate-Ablaufs können Sie das Modell in Ihrer SharePoint-Dokumentbibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="d15d2-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="d15d2-180">Wählen Sie nach dem Veröffentlichen des Modells **Zu SharePoint wechseln** aus, um zu Ihrer Dokumentbibliothek zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d15d2-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="d15d2-181">In der Dokumentbibliotheksmodellansicht werden die von Ihnen ausgewählten Felder nun als Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d15d2-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Angewendetes Dokumentbibliotheksmodell](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="d15d2-183">Der Infolink neben **Dokumente** informiert darüber, dass auf diese Dokumentbibliothek ein Formularverarbeitungsmodell angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d15d2-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Schaltfläche "Informationen"](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="d15d2-185">Laden Sie Dateien in Ihre Dokumentbibliothek hoch.</span><span class="sxs-lookup"><span data-stu-id="d15d2-185">Upload files to your document library.</span></span> <span data-ttu-id="d15d2-186">Alle Dateien, die vom Modell als Inhaltstyp identifiziert werden, werden in Ihrer Ansicht aufgelistet, und die extrahierten Daten werden in den Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d15d2-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Fertig](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="d15d2-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d15d2-188">See Also</span></span>
  
[<span data-ttu-id="d15d2-189">Power Automate-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d15d2-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="d15d2-190">Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="d15d2-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
