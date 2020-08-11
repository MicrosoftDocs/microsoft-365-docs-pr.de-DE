---
title: Erstellen eines Formular Verarbeitungsmodells (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erstellen Sie ein Formular Verarbeitungsmodell in Project Cortex.
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612774"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="6b5a0-103">Erstellen eines Formular Verarbeitungsmodells (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6b5a0-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="6b5a0-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="6b5a0-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="6b5a0-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="6b5a0-106">Verwenden von [AI Builder](https://docs.microsoft.com/ai-builder/overview) -ein Feature in Microsoft PowerApps-Project Cortex Benutzer können ein [Formular Verarbeitungsmodell](form-processing-overview.md) direkt aus einer SharePoint-Dokumentbibliothek erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="6b5a0-107">Das Erstellen eines Formular Verarbeitungsmodells umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6b5a0-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="6b5a0-108">Schritt 1: Erstellen des von-Verarbeitungsmodells zum Erstellen des Inhaltstyps</span><span class="sxs-lookup"><span data-stu-id="6b5a0-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="6b5a0-109">Schritt 2: Hinzufügen und Analysieren von Beispieldateien</span><span class="sxs-lookup"><span data-stu-id="6b5a0-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="6b5a0-110">Schritt 3: Auswählen der Formularfelder</span><span class="sxs-lookup"><span data-stu-id="6b5a0-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="6b5a0-111">Schritt 4: trainieren und Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="6b5a0-112">Schritt 5: Veröffentlichen des Modells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="6b5a0-113">Schritt 6: Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="6b5a0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b5a0-114">Requirements</span></span>

<span data-ttu-id="6b5a0-115">Sie können nur ein Formular Verarbeitungsmodell in SharePoint-Dokumentbibliotheken erstellen, in denen es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="6b5a0-116">Wenn die Formularverarbeitung aktiviert ist, können Sie den **AI-Generator** **"Erstellen eines Formular Verarbeitungsmodells"** im Menü " **automatisieren** " in Ihrer Dokumentbibliothek anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="6b5a0-117">Wenn Sie die in Ihrer Dokumentbibliothek aktivierte Verarbeitung benötigen, wenden Sie sich an Ihren Administrator.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Erstellen eines AI-Generator Modells](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="6b5a0-119">Schritt 1: Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="6b5a0-120">Der erste Schritt beim Erstellen eines Formular Verarbeitungsmodells besteht darin, den Namen zum Definieren des neuen Inhaltstyps und zum Erstellen einer neuen Dokumentbibliotheksansicht dafür zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="6b5a0-121">Wählen Sie in Ihrer Dokumentbibliothek das Menü **automatisieren** aus, wählen Sie **AI Builder**aus, und wählen Sie dann **Formular Verarbeitungsmodell erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Erstellen eines AI-Generator Modells](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="6b5a0-123">Geben Sie im Bereich **Neues Formular Verarbeitungsmodell** im Feld **Name** einen Namen für Ihr Modell ein (beispielsweise Bestel *Lungen*).</span><span class="sxs-lookup"><span data-stu-id="6b5a0-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Neues Formular Verarbeitungsmodell](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="6b5a0-125">Wenn Sie ein Formular Verarbeitungsmodell erstellen, erstellen Sie einen neuen SharePoint-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="6b5a0-126">Ein SharePoint-Inhaltstyp stellt eine Kategorie von Dokumenten dar, die allgemeine Merkmale aufweisen und eine Auflistung von Spalten oder Metadaten-Eigenschaften für diesen bestimmten Inhalt gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="6b5a0-127">SharePoint-Inhaltstypen werden über den [Inhaltstypen Katalog]()verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="6b5a0-128">Wählen Sie **Erweiterte Einstellungen** aus, wenn Sie dieses Modell einem vorhandenen Inhaltstyp im SharePoint-Inhaltstypen Katalog zuordnen möchten, um sein Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="6b5a0-129">Ihr Modell erstellt eine neue Ansicht in Ihrer Dokumentbibliothek für die extrahierten Daten.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="6b5a0-130">Wenn die Standardansicht nicht angezeigt werden soll, deaktivieren Sie die Option **als Standardansicht festlegen**.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="6b5a0-131">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="6b5a0-132">Schritt 2: Hinzufügen und Analysieren von Dokumenten</span><span class="sxs-lookup"><span data-stu-id="6b5a0-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="6b5a0-133">Nachdem Sie Ihr neues Formular Verarbeitungsmodell erstellt haben, wird von Ihrem Browser eine neue Seite des PowerApps AI Builder-Formular Verarbeitungsmodells geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="6b5a0-134">Auf dieser Seite können Sie Ihre Beispiel Dokumente hinzufügen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="6b5a0-135">Wenn Sie nach Beispieldateien suchen, die verwendet werden sollen, lesen Sie das [Formular Verarbeitungsmodell Eingabedokument Anforderungen und Optimierungstipps](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="6b5a0-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power apps AI-Generator](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="6b5a0-137">Klicken Sie auf **Dokumente hinzufügen** , um das Hinzufügen von Beispiel Dokumenten zu beginnen, die analysiert werden, um zu ermitteln, welche benannten Wert-Paare extrahiert werden können</span><span class="sxs-lookup"><span data-stu-id="6b5a0-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="6b5a0-138">Sie können entweder **aus dem lokalen Speicher**, **SharePoint**oder **Azure-BLOB-Speicher**Hochladen auswählen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="6b5a0-139">Sie müssen mindestens fünf Dateien für die Schulung verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="6b5a0-140">Nachdem Sie Ihre Dateien hinzugefügt haben, wählen Sie **analyze** aus, um nach allen gängigen Informationen zu suchen, die alle Dateien aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="6b5a0-141">Beachten Sie, dass dieser Vorgang einige Minuten dauern kann.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Analysieren von Dateien](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="6b5a0-143">Nachdem Sie analysiert wurden, klicken Sie auf der Seite **Formularfelder, die Sie speichern möchten** auf die Datei, um die Felder anzuzeigen, die erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Auswählen von Formularfeldern](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="6b5a0-145">Schritt 3: Auswählen der Formularfelder</span><span class="sxs-lookup"><span data-stu-id="6b5a0-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="6b5a0-146">Nachdem Sie Ihre Dokumente für Felder analysiert haben, können Sie nun sehen, welche Felder gefunden wurden und welche Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="6b5a0-147">Gespeicherte Felder werden als Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt und zeigen die Werte an, die aus den einzelnen Dokumenten extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="6b5a0-148">Auf der nächsten Seite wird eine der Beispieldateien angezeigt, und es werden alle gängigen Felder hervorgehoben, die vom System automatisch erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Auswählen von Formularfeldern](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="6b5a0-150">Wählen Sie die Felder aus, die Sie speichern möchten, und aktivieren Sie das Kontrollkästchen, um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="6b5a0-151">Beispielsweise können Sie im Bestell Modell auswählen, dass die Felder *Datum*, *po*und *Summe* ausgewählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="6b5a0-152">Beachten Sie, dass Sie auch auswählen können, ein Feld umzubenennen, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Po auswählen #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="6b5a0-154">Wenn ein Feld nicht von der Analyse erkannt wurde, können Sie es dennoch hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="6b5a0-155">Markieren Sie die Informationen, die extrahiert werden sollen, und geben Sie im Feld Name den Namen ein, den Sie eingeben möchten.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="6b5a0-156">Wählen Sie dann den Scheck aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-156">Then select the check.</span></span> <span data-ttu-id="6b5a0-157">Beachten Sie, dass Sie unerkannte Felder in ihren restlichen Beispieldateien bestätigen müssen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="6b5a0-158">Klicken Sie auf **Felder bestätigen** , nachdem Sie die Felder ausgewählt haben, die Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Felder bestätigen](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="6b5a0-160">Auf der Seite **Wählen Sie die Formularfelder aus, die Sie speichern möchten** , wird die Anzahl der Felder angezeigt, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="6b5a0-161">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="6b5a0-162">Schritt 4: trainieren und Testen des Modells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="6b5a0-163">Nachdem Sie die Felder ausgewählt haben, die Sie speichern möchten, können Sie mit der **Modell Zusammenfassungs** Seite trainieren und Ihr Modell testen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="6b5a0-164">Auf der Seite **Modellzusammenfassung** werden die gespeicherten Felder im Abschnitt **Ausgewählte Felder** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="6b5a0-165">Wählen Sie **Train** aus, um mit der Schulung in ihren Beispieldateien zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="6b5a0-166">Beachten Sie, dass dieser Vorgang einige Minuten dauern kann.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="6b5a0-167">![Felder bestätigen](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="6b5a0-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="6b5a0-168">Wenn die Benachrichtigung angezeigt wird, dass die Schulung abgeschlossen ist, wählen Sie **zur Seite Details wechseln**aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="6b5a0-169">Auf der Seite **Modelldetails** können Sie die Funktionsweise des Modells testen, indem Sie auf **Schnelltest**klicken.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="6b5a0-170">Auf diese Weise können Sie Dateien per Drag & Drop auf die Seite ziehen und prüfen, ob die Felder erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="6b5a0-171">Schritt 5: Veröffentlichen des Modells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="6b5a0-172">Wenn Sie mit den Ergebnissen Ihres Modells zufrieden sind, wählen Sie **veröffentlichen** aus, um es zur Verwendung zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="6b5a0-173">Wählen Sie nach dem Veröffentlichen des Modells **Modell verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="6b5a0-174">Dadurch wird ein PowerAutomate-Fluss erstellt, der in Ihrer SharePoint-Dokumentbibliothek ausgeführt wird und die Felder extrahiert, die im Modell identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="6b5a0-175">Wählen Sie **Flow erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="6b5a0-176">Wenn dieser Vorgang abgeschlossen ist, wird die Meldung angezeigt, dass **Ihr Flow erfolgreich erstellt**wurde.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="6b5a0-177">Schritt 6: Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="6b5a0-177">Step 6: Use your model</span></span>

<span data-ttu-id="6b5a0-178">Nachdem Sie Ihr Modell veröffentlicht und den PowerAutomate-Fluss erstellt haben, können Sie Ihr Modell in Ihrer SharePoint-Dokumentbibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="6b5a0-179">Wählen Sie nach der Veröffentlichung Ihres Modells zu **SharePoint wechseln** aus, um zu Ihrer Dokumentbibliothek zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="6b5a0-180">Beachten Sie, dass die von Ihnen ausgewählten Felder in der Ansicht Dokument Bibliotheksmodell jetzt als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Dokumentbibliothek mit angewendetem Modell](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="6b5a0-182">Beachten Sie außerdem, dass der Informations Link neben **Dokumenten** darauf hinweist, dass auf diese Dokumentbibliothek ein Formular Verarbeitungsmodell angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Extrahiert](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="6b5a0-184">Laden Sie Dateien in Ihre Dokumentbibliothek hoch.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-184">Upload files to your document library.</span></span> <span data-ttu-id="6b5a0-185">Alle Dateien, die vom Modell als Inhaltstyp identifiziert werden, werden die Dateien in der Ansicht auflisten, und die extrahierten Daten werden in den Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Extrahiert](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="6b5a0-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b5a0-187">See Also</span></span>
  
[<span data-ttu-id="6b5a0-188">Power Automation-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6b5a0-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="6b5a0-189">Schulung: verbessern der Geschäftsleistung mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="6b5a0-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




