---
title: Anwenden einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell
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
description: In diesem Artikel wird die Anwendung einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell erläutert.
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976555"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="6e221-103">Anwenden einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell</span><span class="sxs-lookup"><span data-stu-id="6e221-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="6e221-104">Sie können auf einfache Weise eine [Aufbewahrungsbezeichnung](https://docs.microsoft.com/microsoft-365/compliance/retention) auf ein Dokumentverständnismodell in Microsoft SharePoint Syntex anwenden.</span><span class="sxs-lookup"><span data-stu-id="6e221-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="6e221-105">Aufbewahrungsbezeichnungen ermöglichen es Ihnen, Aufbewahrungseinstellungen auf die Dokumente anzuwenden, die von Ihrem Dokumentverständnismodell identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="6e221-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="6e221-106">Sie könnten beispielsweise wollen, dass Ihr Modell nicht nur sämtliche *Versicherungsbestätigungen* erkennt, die in Ihre Dokumentbibliothek hochgeladen werden, sondern auf diese auch eine *Geschäftlich*-Aufbewahrungsbezeichnung anwendet, damit diese Dokumente für den angegebenen Zeitraum (beispielsweise für die nächsten fünf Monate) nicht gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="6e221-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="6e221-107">Über die Modelleinstellungen auf der Startseite Ihres Modells können Sie eine bereits vorhandene Aufbewahrungsbezeichnung auf Ihr Dokumentverständnismodell anwenden.</span><span class="sxs-lookup"><span data-stu-id="6e221-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="6e221-108">Damit Aufbewahrungsbezeichnungen für die Anwendung auf Ihre Inhaltsverständnismodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="6e221-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="6e221-109">So fügen Sie einem Dokumentverständnismodell eine Aufbewahrungsbezeichnung hinzu</span><span class="sxs-lookup"><span data-stu-id="6e221-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="6e221-110">Wählen Sie auf der Modell-Startseite **Modelleinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e221-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="6e221-111">Wählen Sie in den **Modelleinstellungen** im Abschnitt **Sicherheit und Compliance** das Menü **Aufbewahrungsbezeichnung** aus, um eine Liste der Aufbewahrungsbezeichnungen anzuzeigen, die auf das Modell angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6e221-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="6e221-112">![Menü "Aufbewahrungsbezeichnung"](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="6e221-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="6e221-113">Wählen Sie die Aufbewahrungsbezeichnung aus, die auf das Modell angewendet werden soll, und wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6e221-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="6e221-114">Nachdem Sie die Aufbewahrungsbezeichnung auf das Modell angewendet haben, kann sie auf Folgendes angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="6e221-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="6e221-115">Neue Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="6e221-115">New document library</span></span>
- <span data-ttu-id="6e221-116">Dokumentbibliothek, auf die das Modell bereits angewendet wird</span><span class="sxs-lookup"><span data-stu-id="6e221-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="6e221-117">Anwenden der Aufbewahrungsbezeichnung auf eine Dokumentbibliothek, auf die das Modell bereits angewendet wird</span><span class="sxs-lookup"><span data-stu-id="6e221-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="6e221-118">Wenn Ihr Dokumentverständnismodell bereits auf eine Dokumentbibliothek angewendet wurde, können Sie die folgenden Schritte ausführen, um das Aufbewahrungsbezeichnungsupdate mit Ihrem Modell zu synchronisieren, so dass es auf Ihre Dokumentbibliothek angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="6e221-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="6e221-119">Wählen Sie auf der Startseite Ihres Modells im Abschnitt **Bibliotheken mit diesem Modell** die Dokumentbibliothek aus, auf die das Aufbewahrungsbezeichnungsupdate angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e221-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="6e221-120">Wählen Sie **Synchronisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6e221-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="6e221-121">![Synchronisierungsmodell](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="6e221-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="6e221-122">Nachdem das Update angewendet und mit Ihrem Modell synchronisiert wurde, können Sie folgendermaßen vorgehen, um zu überprüfen, ob es angewendet wurde:</span><span class="sxs-lookup"><span data-stu-id="6e221-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="6e221-123">Klicken Sie im Inhaltscenter im Abschnitt **Bibliotheken mit diesem Modell** auf die Bibliothek, auf die das aktualisierte Modell angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6e221-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="6e221-124">Wählen Sie in der Dokumentbibliotheksansicht das Symbol "Informationen" aus, um die Modelleigenschaften zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6e221-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="6e221-125">Wählen Sie in der Liste **Aktive Modelle** das aktualisierte Modell aus.</span><span class="sxs-lookup"><span data-stu-id="6e221-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="6e221-126">Im Abschnitt **Aufbewahrungsbezeichnung** wird der Name der angewendeten Aufbewahrungsbezeichnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e221-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="6e221-127">Auf der Ansichtsseite Ihres Modells in Ihrer Dokumentbibliothek wird eine neue Spalte **Aufbewahrungsbezeichnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e221-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="6e221-128">Wenn Ihr Modell ermittelte Dateien als seinem Inhaltstyp zugeordnet klassifiziert und sie in der Bibliotheksansicht auflistet, wird in der Spalte "Aufbewahrungsbezeichnung" auch der Name der Aufbewahrungsbezeichnung angezeigt, das auf sie über das Modell angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6e221-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="6e221-129">So wird beispielsweise auf alle *Versicherungsbestätigungen*, die von Ihrem Modell identifiziert wurden, auch die *Geschäftlich*-Aufbewahrungsbezeichnung angewendet, wodurch sie für fünf Monate nicht aus der Dokumentbibliothek gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="6e221-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="6e221-130">Wenn versucht wird, eine solche Datei aus der Dokumentbibliothek zu löschen, wird eine Fehlermeldung angezeigt mit dem Hinweis, dass dies aufgrund der angewendeten Aufbewahrungsbezeichnung nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="6e221-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e221-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e221-131">See Also</span></span>
[<span data-ttu-id="6e221-132">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="6e221-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="6e221-133">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="6e221-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="6e221-134">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="6e221-134">Document Understanding overview</span></span>](document-understanding-overview.md)


