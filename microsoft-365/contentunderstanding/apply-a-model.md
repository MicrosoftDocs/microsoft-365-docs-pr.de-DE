---
title: Anwenden eines Dokument Verständnisses-Modells auf eine Dokumentbibliothek (Vorschau)
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
description: Hier erfahren Sie, wie Sie ein veröffentlichtes Modell auf eine SharePoint-Dokumentbibliothek anwenden.
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950248"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="e799c-103">Anwenden eines Dokument Verständnisses für das Modell (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="e799c-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="e799c-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="e799c-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="e799c-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="e799c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="e799c-106">Nachdem Sie Ihr Dokument grundlegendes Modell veröffentlicht haben, können Sie es auf eine SharePoint-Dokumentbibliothek in Ihrem Microsoft 365-Mandanten anwenden.</span><span class="sxs-lookup"><span data-stu-id="e799c-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="e799c-107">Sie können das Modell nur auf Dokumentbibliotheken anwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="e799c-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="e799c-108">Wenden Sie Ihr Modell auf eine Dokumentbibliothek an.</span><span class="sxs-lookup"><span data-stu-id="e799c-108">Apply your model to a document library.</span></span>

<span data-ttu-id="e799c-109">So wenden Sie Ihr Modell auf eine SharePoint-Dokumentbibliothek an:</span><span class="sxs-lookup"><span data-stu-id="e799c-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="e799c-110">Wählen Sie auf der Modell Startseite auf der Kachel **Modell auf Bibliotheken anwenden** die Option **Modell veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="e799c-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="e799c-111">Sie können auch im Abschnitt **Bibliotheken mit diesem Modell** die Option **+ Bibliothek hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e799c-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Hinzufügen eines Modells zur Bibliothek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="e799c-113">Anschließend können Sie die SharePoint-Website auswählen, die die Dokumentbibliothek enthält, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e799c-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="e799c-114">Wenn die Website nicht in der Liste angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</span><span class="sxs-lookup"><span data-stu-id="e799c-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Website auswählen](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="e799c-116">Sie müssen *Listenberechtigungen verwalten* oder *Bearbeitungs* Rechte für die Dokumentbibliothek haben, auf die Sie das Modell anwenden.</span><span class="sxs-lookup"><span data-stu-id="e799c-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="e799c-117">Nachdem Sie die Website ausgewählt haben, müssen Sie die Dokumentbibliothek auswählen, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e799c-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="e799c-118">Im Beispiel wählen wir die Dokumentbibliothek *Dokumente* auf der *Fall Verfolgungs* Website von Contoso aus.</span><span class="sxs-lookup"><span data-stu-id="e799c-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Auswählen einer doc-Bibliothek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="e799c-120">Da das Modell einem Inhaltstyp zugeordnet ist, wird beim Anwenden des Modells auf die Bibliothek eine Ansicht für den Inhaltstyp erstellt, wobei die von Ihnen extrahierten Beschriftungen als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e799c-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="e799c-121">Diese Ansicht ist standardmäßig die Standardansicht der Bibliothek, Sie können jedoch optional festlegen, dass Sie nicht die Standardansicht sein soll, indem Sie **Erweiterte Einstellungen** auswählen und die Option **Diese neue Ansicht als Standard festlegen**deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e799c-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Bibliotheksansicht](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="e799c-123">Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e799c-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="e799c-124">Auf der Modell Homepage wird im Abschnitt **Bibliotheken mit diesem Modell** die URL zur SharePoint-Website angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e799c-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Bibliotheksansicht](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="e799c-126">Wechseln Sie zu Ihrer Dokumentbibliothek, und stellen Sie sicher, dass Sie sich in der Dokumentbibliotheksansicht des Modells befinden.</span><span class="sxs-lookup"><span data-stu-id="e799c-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="e799c-127">Wenn Sie die Schaltfläche Informationen neben dem Namen der Dokumentbibliothek auswählen, wird in einer Meldung darauf hingewiesen, dass Ihr Modell auf die Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e799c-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Bibliotheksansicht](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="e799c-129">Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e799c-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="e799c-130">Das Modell identifiziert alle Dateien mit dem Modell zugeordneten Inhaltstyp und listet sie in ihrer Ansicht auf.</span><span class="sxs-lookup"><span data-stu-id="e799c-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="e799c-131">Wenn Ihr Modell über Extraktoren verfügt, werden in der Ansicht Spalten für die Daten angezeigt, die Sie aus jeder Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="e799c-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="e799c-132">Anwenden des Modells auf Dateien, die sich bereits in der Dokumentbibliothek befinden</span><span class="sxs-lookup"><span data-stu-id="e799c-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="e799c-133">Während ein angegebenes Modell alle Dateien verarbeitet, die nach der Anwendung in die Dokumentbibliothek hochgeladen wurden, können Sie auch die folgenden Schritte ausführen, um das Modell für Dateien auszuführen, die bereits in der Dokumentbibliothek vor dem Anwenden des Modells vorhanden waren:</span><span class="sxs-lookup"><span data-stu-id="e799c-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="e799c-134">Wählen Sie in Ihrer Dokumentbibliothek die Dateien aus, die von Ihrem Modell verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e799c-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="e799c-135">Nachdem Sie Ihre Dateien ausgewählt haben, werden **klassifizieren und extrahieren** im Menüband der Dokumentbibliothek angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e799c-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="e799c-136">Wählen Sie **klassifizieren und extrahieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e799c-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="e799c-137">Die ausgewählten Dateien werden der Warteschlange hinzugefügt, die verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e799c-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassifizieren und extrahieren](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="e799c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e799c-139">See Also</span></span>
[<span data-ttu-id="e799c-140">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="e799c-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="e799c-141">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="e799c-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="e799c-142">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="e799c-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="e799c-143">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="e799c-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




