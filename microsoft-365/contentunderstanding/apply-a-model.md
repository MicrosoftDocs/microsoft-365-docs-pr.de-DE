---
title: Anwenden eines Dokumentverständnismodells auf eine Dokumentbibliothek
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
description: Informationen zum Anwenden eines veröffentlichten Modells auf eine SharePoint-Dokumentbibliothek
ms.openlocfilehash: 17da1e37f72504ac5e0e26c0dd190efced08d285
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080788"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="052e0-103">Anwenden eines Dokumentverständnismodells in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="052e0-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="052e0-104">Nach der Veröffentlichung des Dokumentverständnismodells können Sie es auf eine oder mehrere SharePoint-Dokumentbibliotheken in Ihrem Microsoft 365-Mandanten anwenden.</span><span class="sxs-lookup"><span data-stu-id="052e0-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="052e0-105">Sie können das Modell nur auf Dokumentbibliotheken anwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="052e0-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="052e0-106">Wenden Sie Ihr Modell auf eine Dokumentbibliothek an.</span><span class="sxs-lookup"><span data-stu-id="052e0-106">Apply your model to a document library.</span></span>

<span data-ttu-id="052e0-107">So wenden Sie Ihr Modell auf eine SharePoint-Dokumentbibliothek an:</span><span class="sxs-lookup"><span data-stu-id="052e0-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="052e0-108">Wählen Sie auf der Modellstartseite auf der Kachel **Modell auf Bibliotheken anwenden** die Option **Modell veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="052e0-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="052e0-109">Sie können auch  **+ Bibliothek hinzufügen** im Abschnitt **Bibliotheken mit diesem Modell** auswählen.</span><span class="sxs-lookup"><span data-stu-id="052e0-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Hinzufügen des Modells zur Bibliothek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="052e0-111">Sie können dann die SharePoint-Website auswählen, die die Dokumentbibliothek enthält, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="052e0-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="052e0-112">Wenn die Website in der Liste nicht angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</span><span class="sxs-lookup"><span data-stu-id="052e0-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Auswählen einer Website](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="052e0-114">Sie müssen über die Berechtigung *Listen verwalten* oder *Bearbeiten* für die Dokumentbibliothek verfügen, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="052e0-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="052e0-115">Nachdem Sie die Website ausgewählt haben, wählen Sie die Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="052e0-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="052e0-116">Wählen Sie im Beispiel die Dokumentbibliothek *Dokumente* auf der Website *Contoso-Fallnachverfolgung* aus.</span><span class="sxs-lookup"><span data-stu-id="052e0-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Auswählen einer Dokumentbibliothek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="052e0-118">Da das Modell einem Inhaltstyp zugeordnet ist, fügt es, wenn Sie es auf die Bibliothek anwenden, den Inhaltstyp und dessen Ansicht hinzu, wobei die Bezeichnungen, die Sie extrahiert haben, als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="052e0-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="052e0-119">Diese Ansicht ist die Standardansicht der Bibliothek. Sie können aber auch eine andere Aussicht auswählen, indem Sie **Erweiterte Einstellungen** auswählen und die Auswahl für **Diese neue Anzeige als Standard festlegen** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="052e0-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Bibliotheksansicht](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="052e0-121">Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="052e0-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="052e0-122">Auf der Modellstartseite sollte im Abschnitt **Bibliotheken mit diesem Modell** die URL der aufgelisteten SharePoint-Website angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="052e0-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Ausgewählte Bibliothek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="052e0-124">Wechseln Sie zu Ihrer Dokumentbibliothek, und vergewissern Sie sich, dass Sie sich in der Dokumentbibliotheksanzeige des Modells befinden.</span><span class="sxs-lookup"><span data-stu-id="052e0-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="052e0-125">Wenn Sie die Informationsschaltfläche neben dem Namen der Dokumentbibliothek auswählen, wird eine Nachricht angezeigt, die besagt, dass ein Modell auf die Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="052e0-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![Informationsansicht](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="052e0-127">Sie können **Aktiven Modelle anzeigen** auswählen, um Details zu allen Modellen anzuzeigen, die auf die Dokumentbibliothek angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="052e0-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="052e0-128">Im Bereich **Aktive Modelle** werden die Modelle angezeigt, die auf die Dokumentbibliothek angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="052e0-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="052e0-129">Wählen Sie ein Modell aus, um weitere Details dazu anzuzeigen, z. B. eine Beschreibung des Modells, wer das Modell veröffentlicht hat und ob das Modell eine Aufbewahrungsbezeichnung auf die von ihm klassifizierten Dateien zutrifft.</span><span class="sxs-lookup"><span data-stu-id="052e0-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![Bereich „Aktive Modelle“](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="052e0-131">Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="052e0-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="052e0-132">Das Modell identifiziert alle Dateien mit dem zugeordneten Inhaltstyp des Modells und listet sie in Ihrer Ansicht auf.</span><span class="sxs-lookup"><span data-stu-id="052e0-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="052e0-133">Wenn Ihr Modell Extraktoren enthält, werden in der Ansicht Spalten für die Daten angezeigt, die Sie aus den einzelnen Dateien extrahieren.</span><span class="sxs-lookup"><span data-stu-id="052e0-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="052e0-134">Anwenden des Modells auf Dateien, die sich bereits in der Dokumentbibliothek befinden</span><span class="sxs-lookup"><span data-stu-id="052e0-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="052e0-135">Während ein angewendetes Modell alle Dateien verarbeitet, die nach der Anwendung in die Dokumentbibliothek hochgeladen wurden, können Sie auch die folgenden Schritte ausführen, um das Modell für Dateien auszuführen, die bereits vor dem Anwenden des Modells in der Dokumentbibliothek vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="052e0-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="052e0-136">Wählen Sie in Ihrer Dokumentbibliothek die Dateien aus, die vom Modell verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="052e0-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="052e0-137">Nach dem Auswählen der Dateien wird **Klassifizieren und extrahieren** im Menüband der Dokumentbibliothek angezeigt.</span><span class="sxs-lookup"><span data-stu-id="052e0-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="052e0-138">Wählen Sie **Klassifizieren und extrahieren** aus.</span><span class="sxs-lookup"><span data-stu-id="052e0-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="052e0-139">Die ausgewählten Dateien werden der Warteschlange zur Verarbeitung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="052e0-139">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassifizieren und extrahieren](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="052e0-141">Sie können einzelne Dateien in eine Bibliothek kopieren und auf ein Modell anwenden, aber keine Ordner.</span><span class="sxs-lookup"><span data-stu-id="052e0-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="052e0-142">Das Feld „Klassifizierungsdatum“</span><span class="sxs-lookup"><span data-stu-id="052e0-142">The Classification Date field</span></span>

<span data-ttu-id="052e0-143">Wenn ein SharePoint Syntex-Dokumentverständnis oder ein Formularverarbeitungsmodell auf eine Dokumentbibliothek angewendet wird, wird in das Bibliotheksschema ein Feld <b>Klassifizierungsdatum </b> aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="052e0-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="052e0-144">Dieses Feld ist standardmäßig leer, aber wenn Dokumente von einem Modell verarbeitet und klassifiziert werden, wird dieses Feld mit einem Datums-/Uhrzeitstempel der Fertigstellung aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="052e0-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![Die Spalte „Klassifizierungsdatum“](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="052e0-146">Das Feld für das Klassifizierungsdatum wird vom Trigger [<b>Wenn eine Datei von einem Inhaltsverständnismodell klassifiziert wird</b> verwendet, ](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) um einen Power Automate-Ablauf auszuführen, nachdem ein Syntex-Modell für das Verstehen von Inhalten die Verarbeitung einer Datei abgeschlossen und das Feld „Klassifizierungsdatum“ aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="052e0-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![Flusstrigger](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="052e0-148">Der Trigger <b>Wenn eine Datei von einem Inhaltsverständnissmodell klassifiziert wird</b> kann dann verwendet werden, um einen anderen Workflow unter Verwendung extrahierter Informationen aus der Datei zu starten.</span><span class="sxs-lookup"><span data-stu-id="052e0-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="052e0-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="052e0-149">See Also</span></span>
[<span data-ttu-id="052e0-150">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="052e0-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="052e0-151">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="052e0-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="052e0-152">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="052e0-152">Document Understanding overview</span></span>](document-understanding-overview.md)


