---
title: Erstellen eines Formular Verarbeitungsmodells
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
description: Erstellen Sie ein Formular Verarbeitungsmodell in Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295478"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d29a9-103">Erstellen eines Formular Verarbeitungsmodells in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d29a9-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="d29a9-104">Der Inhalt in diesem Artikel ist für die Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="d29a9-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="d29a9-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d29a9-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d29a9-106">Verwenden von [AI Builder](https://docs.microsoft.com/ai-builder/overview) -ein Feature in Microsoft PowerApps-Project Cortex Benutzer können ein [Formular Verarbeitungsmodell](form-processing-overview.md) direkt aus einer SharePoint-Dokumentbibliothek erstellen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="d29a9-107">Das Erstellen eines Formular Verarbeitungsmodells umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d29a9-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="d29a9-108">Schritt 1: Erstellen des von-Verarbeitungsmodells zum Erstellen des Inhaltstyps</span><span class="sxs-lookup"><span data-stu-id="d29a9-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="d29a9-109">Schritt 2: Hinzufügen und Analysieren von Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="d29a9-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="d29a9-110">Schritt 3: Auswählen der Formularfelder</span><span class="sxs-lookup"><span data-stu-id="d29a9-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="d29a9-111">Schritt 4: trainieren und Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="d29a9-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="d29a9-112">Schritt 5: Veröffentlichen des Modells</span><span class="sxs-lookup"><span data-stu-id="d29a9-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="d29a9-113">Schritt 6: Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="d29a9-113">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="d29a9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d29a9-114">Requirements</span></span>

<span data-ttu-id="d29a9-115">Sie können nur ein Formular Verarbeitungsmodell in SharePoint-Dokumentbibliotheken erstellen, für die es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d29a9-115">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="d29a9-116">Wenn die Formularverarbeitung aktiviert ist, können Sie den AI- **Generator** **"Erstellen eines Formular Verarbeitungsmodells"** im Menü " **automatisieren** " in Ihrer Dokumentbibliothek anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-116">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="d29a9-117">Wenn Sie die Verarbeitung in Ihrer Dokumentbibliothek aktivieren müssen, müssen Sie sich an Ihren SharePoint-Administrator wenden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-117">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Erstellen eines AI-Generator Modells](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="d29a9-119">Schritt 1: Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="d29a9-119">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="d29a9-120">Der erste Schritt beim Erstellen eines Formular Verarbeitungsmodells besteht darin, diesen Namen zu benennen und den neuen Inhaltstyp define zu erstellen und eine neue Dokumentbibliotheksansicht dafür zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-120">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="d29a9-121">Wählen Sie in der Dokumentbibliothek das Menü **automatisieren** aus, wählen Sie **AI Builder**aus, und wählen Sie dann **Formular Verarbeitungsmodell erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-121">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Erstellen eines Modells](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="d29a9-123">Geben Sie im Bereich **Neues Formular Verarbeitungsmodell** im Feld  **Name** einen Namen für Ihr Modell ein (beispielsweise Bestel *Lungen*).</span><span class="sxs-lookup"><span data-stu-id="d29a9-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Neues Formular Verarbeitungsmodell](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="d29a9-125">Wenn Sie ein Formular Verarbeitungsmodell erstellen, erstellen Sie einen neuen SharePoint-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="d29a9-125">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="d29a9-126">Ein SharePoint-Inhaltstyp stellt eine Kategorie von Dokumenten dar, die allgemeine Merkmale aufweisen und eine Auflistung von Spalten oder Metadaten-Eigenschaften für diesen bestimmten Inhalt gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="d29a9-127">SharePoint-Inhaltstypen werden über den [Inhaltstypen Katalog]()verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d29a9-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="d29a9-128">Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Inhaltstyp im SharePoint-Inhaltstypen Katalog zuordnen möchten, um sein Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="d29a9-129">Ihr Modell erstellt eine neue Ansicht in Ihrer Dokumentbibliothek für die extrahierten Daten.</span><span class="sxs-lookup"><span data-stu-id="d29a9-129">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="d29a9-130">Wenn die Standardansicht nicht angezeigt werden soll, deaktivieren Sie die Option **als Standardansicht festlegen**.</span><span class="sxs-lookup"><span data-stu-id="d29a9-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="d29a9-131">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-131">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="d29a9-132">Schritt 2: Hinzufügen und Analysieren von Dokumenten</span><span class="sxs-lookup"><span data-stu-id="d29a9-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="d29a9-133">Nachdem Sie Ihr neues Formular Verarbeitungsmodell erstellt haben, öffnet Ihr Browser eine neue Seite des PowerApps AI Builder-Formular Verarbeitungsmodells.</span><span class="sxs-lookup"><span data-stu-id="d29a9-133">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="d29a9-134">Auf dieser Seite können Sie Ihre Beispiel Dokumente hinzufügen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="d29a9-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="d29a9-135">Wenn Sie nach Beispieldateien suchen, die verwendet werden sollen, lesen Sie das [Formular Verarbeitungsmodell Eingabedokument Anforderungen und Optimierungstipps](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="d29a9-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power apps AI-Generator](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="d29a9-137">Wählen Sie **Dokumente hinzufügen** aus, um das Hinzufügen von Beispiel Dokumenten zu beginnen, mit denen die benannten Wert Paare ermittelt werden, die extrahiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d29a9-137">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="d29a9-138">Sie können dann entweder **aus lokalem Speicher**, **SharePoint**oder **Azure-BLOB-Speicher**Hochladen auswählen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-138">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="d29a9-139">Sie müssen mindestens fünf Dateien für die Schulung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-139">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="d29a9-140">Wählen Sie nach dem Hinzufügen von Dateien **analyze** aus, um nach allen Informationen zu suchen, die bei allen Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-140">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="d29a9-141">Dieser Vorgang kann einige Minuten in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-141">This may take several minutes to complete.</span></span></br> 
 
    ![Analysieren von Dateien](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="d29a9-143">Nachdem Sie die Dateien analysiert haben, wählen Sie auf der Seite **Formularfelder, die Sie speichern möchten** die Datei aus, um die erkannten Felder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-143">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Auswählen von Formularfeldern](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="d29a9-145">Schritt 3: Auswählen der Formularfelder</span><span class="sxs-lookup"><span data-stu-id="d29a9-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="d29a9-146">Nachdem Sie die Dokumente für Felder analysiert haben, können Sie nun die gefundenen Felder anzeigen und diejenigen identifizieren, die Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="d29a9-146">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="d29a9-147">Gespeicherte Felder werden als Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt und zeigen die aus jedem Dokument extrahierten Werte an.</span><span class="sxs-lookup"><span data-stu-id="d29a9-147">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="d29a9-148">Auf der nächsten Seite wird eine der Beispieldateien angezeigt, und es werden alle gängigen Felder hervorgehoben, die vom System automatisch erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-148">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Seite "Felder auswählen"](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="d29a9-150">Wählen Sie die Felder aus, die Sie speichern möchten, und aktivieren Sie das Kontrollkästchen, um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-150">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="d29a9-151">Wählen Sie beispielsweise im Bestell Modell die Felder *Datum*, *po*und *Summe* aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-151">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="d29a9-152">Beachten Sie, dass Sie auch auswählen können, ein Feld umzubenennen, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="d29a9-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Po auswählen #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="d29a9-154">Wenn ein Feld nicht von der Analyse erkannt wurde, können Sie es dennoch hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="d29a9-155">Markieren Sie die Informationen, die extrahiert werden sollen, und geben Sie im Feld Name den gewünschten Namen ein.</span><span class="sxs-lookup"><span data-stu-id="d29a9-155">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="d29a9-156">Aktivieren Sie dann das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-156">Then select the check box.</span></span> <span data-ttu-id="d29a9-157">Beachten Sie, dass Sie unerkannte Felder in ihren verbleibenden Beispieldateien bestätigen müssen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-157">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="d29a9-158">Klicken Sie auf **Felder bestätigen** , nachdem Sie die Felder ausgewählt haben, die Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="d29a9-158">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Felder bestätigen nach dem Auswählen von Feldern](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="d29a9-160">Auf der Seite **Wählen Sie die Formularfelder aus, die Sie speichern möchten** , wird die Anzahl der Felder angezeigt, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="d29a9-160">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="d29a9-161">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="d29a9-162">Schritt 4: trainieren und Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="d29a9-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="d29a9-163">Nachdem Sie die Felder ausgewählt haben, die Sie speichern möchten, können Sie mit der **Modell Zusammenfassungs** Seite trainieren und Ihr Modell testen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-163">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="d29a9-164">Auf der Seite **Modellzusammenfassung** werden die gespeicherten Felder im Abschnitt **Ausgewählte Felder** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d29a9-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="d29a9-165">Wählen Sie **Train** aus, um mit der Schulung in ihren Beispieldateien zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="d29a9-166">Beachten Sie, dass dieser Vorgang einige Minuten dauern kann.</span><span class="sxs-lookup"><span data-stu-id="d29a9-166">Note that this may take a few minutes to complete.</span></span></br>

     ![Auswählen von Feldern "Zug"](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="d29a9-168">Wenn die Benachrichtigung angezeigt wird, dass die Schulung abgeschlossen ist, wählen Sie **zur Seite Details wechseln**aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="d29a9-169">Auf der Seite **Modelldetails** können Sie die Funktionsweise des Modells testen, indem Sie auf **Schnelltest**klicken.</span><span class="sxs-lookup"><span data-stu-id="d29a9-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="d29a9-170">Auf diese Weise können Sie Dateien per Drag & Drop auf die Seite ziehen und prüfen, ob die Felder erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Felder bestätigen](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="d29a9-172">Wenn die Benachrichtigung angezeigt wird, dass die Schulung abgeschlossen ist, wählen Sie **zur Seite Details wechseln**aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-172">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="d29a9-173">Wählen Sie auf der Seite **Modelldetails** die Option **Schnelltest**aus, um zu testen, wie das Modell funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d29a9-173">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="d29a9-174">Auf diese Weise können Sie Dateien per Drag & Drop auf die Seite ziehen und prüfen, ob die Felder erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-174">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="d29a9-175">Schritt 5: Veröffentlichen des Modells</span><span class="sxs-lookup"><span data-stu-id="d29a9-175">Step 5: Publish your model</span></span>

1. <span data-ttu-id="d29a9-176">Wenn Sie mit den Ergebnissen Ihres Modells zufrieden sind, wählen Sie **veröffentlichen** aus, um es zur Verwendung zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="d29a9-176">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="d29a9-177">Wählen Sie nach dem Veröffentlichen des Modells **Modell verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-177">After the model is published, select **Use model**.</span></span> <span data-ttu-id="d29a9-178">Dadurch wird ein PowerAutomate-Fluss erstellt, der in Ihrer SharePoint-Dokumentbibliothek ausgeführt werden kann, und extrahiert die Felder, die im Modell identifiziert wurden, und wählen Sie dann **Flow erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="d29a9-178">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="d29a9-179">Wenn dieser Vorgang abgeschlossen ist, wird die Meldung angezeigt, dass **Ihr Flow erfolgreich erstellt**wurde.</span><span class="sxs-lookup"><span data-stu-id="d29a9-179">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="d29a9-180">Schritt 6: Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="d29a9-180">Step 6: Use your model</span></span>

<span data-ttu-id="d29a9-181">Nachdem Sie Ihr Modell veröffentlicht und den PowerAutomate-Fluss erstellt haben, können Sie Ihr Modell in Ihrer SharePoint-Dokumentbibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-181">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="d29a9-182">Wählen Sie nach der Veröffentlichung Ihres Modells zu **SharePoint wechseln** aus, um zu Ihrer Dokumentbibliothek zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d29a9-182">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="d29a9-183">Beachten Sie in der Ansicht Dokumentbibliothek Modell, dass die von Ihnen ausgewählten Felder jetzt als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d29a9-183">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Dokument Bibliotheksmodell angewendet](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="d29a9-185">Beachten Sie, dass der Link Informationen neben **Dokumenten** darauf hinweist, dass auf diese Dokumentbibliothek ein Formular Verarbeitungsmodell angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d29a9-185">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Schaltfläche "Info"](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="d29a9-187">Laden Sie Dateien in Ihre Dokumentbibliothek hoch.</span><span class="sxs-lookup"><span data-stu-id="d29a9-187">Upload files to your document library.</span></span> <span data-ttu-id="d29a9-188">Alle Dateien, die vom Modell als Inhaltstyp identifiziert werden, Listen die Dateien in ihrer Ansicht auf und zeigen die extrahierten Daten in den Spalten an.</span><span class="sxs-lookup"><span data-stu-id="d29a9-188">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Fertig](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="d29a9-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d29a9-190">See Also</span></span>
  
[<span data-ttu-id="d29a9-191">Power Automation-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d29a9-191">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="d29a9-192">Schulung: verbessern der Geschäftsleistung mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="d29a9-192">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
