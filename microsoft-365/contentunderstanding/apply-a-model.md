---
title: Anwenden eines Dokument Verständnisses-Modells auf eine Dokumentbibliothek
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
description: Informationen zum Anwenden eines veröffentlichten Modells auf eine SharePoint-Dokumentbibliothek
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295490"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="ff0a3-103">Anwenden eines Dokument Verständnisses für das Modell in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="ff0a3-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="ff0a3-104">Der Inhalt dieses Artikels ist für die Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="ff0a3-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="ff0a3-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="ff0a3-106">Nachdem Sie Ihr Dokument grundlegendes Modell veröffentlicht haben, können Sie es auf eine SharePoint-Dokumentbibliothek in Ihrem Microsoft 365-Mandanten anwenden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="ff0a3-107">Sie können das Modell nur auf Dokumentbibliotheken anwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="ff0a3-108">Wenden Sie Ihr Modell auf eine Dokumentbibliothek an.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-108">Apply your model to a document library.</span></span>

<span data-ttu-id="ff0a3-109">So wenden Sie Ihr Modell auf eine SharePoint-Dokumentbibliothek an:</span><span class="sxs-lookup"><span data-stu-id="ff0a3-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="ff0a3-110">Wählen Sie auf der Startseite des Modells auf der Kachel **Modell auf Bibliotheken anwenden** die Option **Modell veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="ff0a3-111">Sie können auch im Abschnitt **Bibliotheken mit diesem Modell** die Option **+ Bibliothek hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Hinzufügen eines Modells zur Bibliothek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="ff0a3-113">Wählen Sie die SharePoint-Website mit der Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="ff0a3-114">Wenn die Website nicht in der Liste angezeigt wird, verwenden Sie das Suchfeld, um Sie zu finden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Website auswählen](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="ff0a3-116">Sie müssen *Listenberechtigungen verwalten* oder *Bearbeitungs* Rechte für die Dokumentbibliothek haben, auf die Sie das Modell anwenden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="ff0a3-117">Nachdem Sie die Website ausgewählt haben, wählen Sie die Dokumentbibliothek aus, auf die Sie das Modell anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="ff0a3-118">Wählen Sie im Beispiel die Dokumentbibliothek *Dokumente* auf der *Fall Verfolgungs* Website von Contoso aus.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Auswählen einer doc-Bibliothek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="ff0a3-120">Da das Modell einem Inhaltstyp zugeordnet ist, wird beim Anwenden auf die Bibliothek eine Ansicht für den Inhaltstyp erstellt, wobei die von Ihnen extrahierten Beschriftungen als Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="ff0a3-121">Diese Ansicht ist standardmäßig die Standardansicht der Bibliothek, Sie können jedoch optional festlegen, dass Sie nicht die Standardansicht sein soll, indem Sie **Erweiterte Einstellungen** auswählen und die Option **Diese neue Ansicht als Standard festlegen**deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Bibliotheksansicht](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="ff0a3-123">Wählen Sie **Hinzufügen** aus, um das Modell auf die Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="ff0a3-124">Auf der Modell Startseite sollte im Abschnitt **Bibliotheken mit diesem Modell** die URL der SharePoint-Website angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Ausgewählte Bibliothek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="ff0a3-126">Wechseln Sie zu Ihrer Dokumentbibliothek, und stellen Sie sicher, dass Sie sich in der Dokumentbibliotheksansicht des Modells befinden.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="ff0a3-127">Beachten Sie, dass bei Auswahl der Schaltfläche Informationen neben dem Namen der Dokumentbibliothek eine Meldung darauf hinweist, dass Ihr Modell auf die Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Informationsansicht](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="ff0a3-129">Nachdem Sie das Modell auf die Dokumentbibliothek angewendet haben, können Sie mit dem Hochladen von Dokumenten auf die Website beginnen und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="ff0a3-130">Das Modell identifiziert alle Dateien mit dem Modell zugeordneten Inhaltstyp und listet diese in ihrer Ansicht auf.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="ff0a3-131">Wenn Ihr Modell über Extraktoren verfügt, werden in der Ansicht Spalten für die Daten angezeigt, die Sie aus jeder Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="ff0a3-132">Anwenden des Modells auf Dateien, die sich bereits in der Dokumentbibliothek befinden</span><span class="sxs-lookup"><span data-stu-id="ff0a3-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="ff0a3-133">Während ein angewendetes Modell alle Dateien verarbeitet, die nach der Anwendung in die Dokumentbibliothek hochgeladen wurden, können Sie auch die folgenden Schritte ausführen, um das Modell für Dateien auszuführen, die bereits in der Dokumentbibliothek vorhanden sind, bevor das Modell angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="ff0a3-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="ff0a3-134">Wählen Sie in Ihrer Dokumentbibliothek die Dateien aus, die von Ihrem Modell verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="ff0a3-135">Nachdem Sie Ihre Dateien ausgewählt haben, werden **klassifizieren und extrahieren** im Menüband der Dokumentbibliothek angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="ff0a3-136">Wählen Sie **klassifizieren und extrahieren**aus.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="ff0a3-137">Die ausgewählten Dateien werden der Warteschlange hinzugefügt, die verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff0a3-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassifizieren und extrahieren](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="ff0a3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff0a3-139">See Also</span></span>
[<span data-ttu-id="ff0a3-140">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="ff0a3-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="ff0a3-141">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="ff0a3-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="ff0a3-142">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="ff0a3-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="ff0a3-143">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="ff0a3-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
