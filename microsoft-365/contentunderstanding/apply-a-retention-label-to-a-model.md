---
title: Anwenden einer Aufbewahrungsbezeichnung auf ein Modell
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
localization_priority: Normal
description: In diesem Artikel wird die Anwendung einer Aufbewahrungsbezeichnung auf ein Modell in SharePoint Syntex erläutert.
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861611"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="e4a17-103">Anwenden einer Aufbewahrungsbezeichnung auf ein Modell in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e4a17-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="e4a17-104">Sie können auf einfache Weise eine [Aufbewahrungsbezeichnung](../compliance/retention.md) auf ein Modell in Microsoft SharePoint Syntex anwenden.</span><span class="sxs-lookup"><span data-stu-id="e4a17-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="e4a17-105">Sie können dies sowohl für Dokumentverständnis- als auch Formularverarbeitungsmodelle tun.</span><span class="sxs-lookup"><span data-stu-id="e4a17-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="e4a17-106">Aufbewahrungsbezeichnungen ermöglichen es Ihnen, Aufbewahrungseinstellungen auf die Dokumente anzuwenden, die von Ihrem Modell identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e4a17-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="e4a17-107">Sie könnten beispielsweise wollen, dass Ihr Modell nicht nur sämtliche *Versicherungsbestätigungen* erkennt, die in Ihre Dokumentbibliothek hochgeladen werden, sondern auf diese auch eine *Geschäftlich*-Aufbewahrungsbezeichnung anwendet, damit diese Dokumente für den angegebenen Zeitraum (beispielsweise für die nächsten fünf Monate) nicht gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="e4a17-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="e4a17-108">Über die Modelleinstellungen auf der Startseite Ihres Modells können Sie eine bereits vorhandene Aufbewahrungsbezeichnung auf Ihr Modell anwenden.</span><span class="sxs-lookup"><span data-stu-id="e4a17-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="e4a17-109">Damit Aufbewahrungsbezeichnungen für die Anwendung auf Ihre Dokumentverständnismodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="e4a17-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="e4a17-110">So fügen Sie einem Dokumentverständnismodell eine Aufbewahrungsbezeichnung hinzu</span><span class="sxs-lookup"><span data-stu-id="e4a17-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="e4a17-111">Wählen Sie auf der Modell-Startseite **Modelleinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e4a17-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="e4a17-112">Wählen Sie in den **Modelleinstellungen** im Abschnitt **Sicherheit und Compliance** das Menü **Aufbewahrungsbezeichnung** aus, um eine Liste der Aufbewahrungsbezeichnungen anzuzeigen, die auf das Modell angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e4a17-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="e4a17-113">![Menü "Aufbewahrungsbezeichnung"](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="e4a17-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="e4a17-114">Wählen Sie die Aufbewahrungsbezeichnung aus, die auf das Modell angewendet werden soll, und wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e4a17-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="e4a17-115">Nachdem Sie die Aufbewahrungsbezeichnung auf das Modell angewendet haben, kann sie auf Folgendes angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="e4a17-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="e4a17-116">Neue Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4a17-116">New document library</span></span>
- <span data-ttu-id="e4a17-117">Dokumentbibliothek, auf die das Modell bereits angewendet wird</span><span class="sxs-lookup"><span data-stu-id="e4a17-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="e4a17-118">Anwenden der Aufbewahrungsbezeichnung auf eine Dokumentbibliothek, auf die das Modell bereits angewendet wird</span><span class="sxs-lookup"><span data-stu-id="e4a17-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="e4a17-119">Wenn Ihr Dokumentverständnismodell bereits auf eine Dokumentbibliothek angewendet wurde, können Sie die folgenden Schritte ausführen, um das Aufbewahrungsbezeichnungsupdate mit Ihrem Modell zu synchronisieren, so dass es auf Ihre Dokumentbibliothek angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="e4a17-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="e4a17-120">Wählen Sie auf der Startseite Ihres Modells im Abschnitt **Bibliotheken mit diesem Modell** die Dokumentbibliothek aus, auf die das Aufbewahrungsbezeichnungsupdate angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4a17-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="e4a17-121">Wählen Sie **Synchronisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e4a17-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="e4a17-122">![Synchronisierungsmodell](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="e4a17-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="e4a17-123">Nachdem das Update angewendet und mit Ihrem Modell synchronisiert wurde, können Sie folgendermaßen vorgehen, um zu überprüfen, ob es angewendet wurde:</span><span class="sxs-lookup"><span data-stu-id="e4a17-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="e4a17-124">Klicken Sie im Inhaltscenter im Abschnitt **Bibliotheken mit diesem Modell** auf die Bibliothek, auf die das aktualisierte Modell angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e4a17-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="e4a17-125">Wählen Sie in der Dokumentbibliotheksansicht das Symbol "Informationen" aus, um die Modelleigenschaften zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e4a17-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="e4a17-126">Wählen Sie in der Liste **Aktive Modelle** das aktualisierte Modell aus.</span><span class="sxs-lookup"><span data-stu-id="e4a17-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="e4a17-127">Im Abschnitt **Aufbewahrungsbezeichnung** wird der Name der angewendeten Aufbewahrungsbezeichnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4a17-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="e4a17-128">Auf der Ansichtsseite Ihres Modells in Ihrer Dokumentbibliothek wird eine neue Spalte **Aufbewahrungsbezeichnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4a17-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="e4a17-129">Wenn Ihr Modell ermittelte Dateien als seinem Inhaltstyp zugeordnet klassifiziert und sie in der Bibliotheksansicht auflistet, wird in der Spalte "Aufbewahrungsbezeichnung" auch der Name der Aufbewahrungsbezeichnung angezeigt, das auf sie über das Modell angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e4a17-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="e4a17-130">So wird beispielsweise auf alle *Versicherungsbestätigungen*, die von Ihrem Modell identifiziert wurden, auch die *Geschäftlich*-Aufbewahrungsbezeichnung angewendet, wodurch sie für fünf Monate nicht aus der Dokumentbibliothek gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="e4a17-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="e4a17-131">Wenn versucht wird, eine solche Datei aus der Dokumentbibliothek zu löschen, wird eine Fehlermeldung angezeigt mit dem Hinweis, dass dies aufgrund der angewendeten Aufbewahrungsbezeichnung nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e4a17-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="e4a17-132">So fügen Sie einem Formularverarbeitungsmodell eine Aufbewahrungsbezeichnung hinzu</span><span class="sxs-lookup"><span data-stu-id="e4a17-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="e4a17-133">Damit Aufbewahrungsbezeichnungen für die Anwendung auf Ihre Formularverarbeitungsmodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="e4a17-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="e4a17-134">Sie können eine Aufbewahrungsbezeichnung entweder auf ein Formularverarbeitungsmodell anwenden, wenn Sie ein Modell erstellen, oder auf ein vorhandenes Modell anwenden.</span><span class="sxs-lookup"><span data-stu-id="e4a17-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="e4a17-135">So fügen Sie eine Aufbewahrungsbezeichnung hinzu, wenn Sie ein Formularverarbeitungsmodell erstellen</span><span class="sxs-lookup"><span data-stu-id="e4a17-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="e4a17-136">Wenn Sie ein [Formularverarbeitungsmodell erstellen](./create-a-form-processing-model.md), wählen Sie <b>erweiterte Einstellungen</b> aus.</span><span class="sxs-lookup"><span data-stu-id="e4a17-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="e4a17-137">Wählen Sie unter <b>Erweiterte Einstellungen</b> im Abschnitt <b>Aufbewahrungsbezeichnung</b> das Menü aus, und wählen Sie dann die Aufbewahrungsbezeichnung aus, die Sie auf das Modell anwenden möchten.</b></span><span class="sxs-lookup"><span data-stu-id="e4a17-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Hinzufügen zu einem neuen Formularverarbeitungsmodell](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="e4a17-139">Nachdem Sie die verbleibenden Modelleinstellungen abgeschlossen haben, wählen Sie <b>Erstellen</b> aus, um Ihr Modell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4a17-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="e4a17-140">So fügen Sie einem bestehenden Formularverarbeitungsmodell eine Aufbewahrungsbezeichnung hinzu</span><span class="sxs-lookup"><span data-stu-id="e4a17-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="e4a17-141">Sie können einem bestehenden Formularverarbeitungsmodell auf verschiedene Arten eine Aufbewahrungsbezeichnung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e4a17-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="e4a17-142">Über das Menü „Automatisieren“ in der Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4a17-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="e4a17-143">Über die Einstellungen der Aktiven Modelle in der Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="e4a17-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="e4a17-144">So fügen Sie einem bestehenden Formularverarbeitungsmodell über das Menü „Automatisieren“ eine Aufbewahrungsbezeichnung hinzu</span><span class="sxs-lookup"><span data-stu-id="e4a17-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="e4a17-145">Sie können einem vorhandenen Formularverarbeitungsmodell, das Ihnen gehört, über das Menü „Automatisieren“ in der Dokumentbibliothek, auf die das Modell angewendet wird, eine Aufbewahrungsbezeichnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e4a17-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="e4a17-146">Wählen Sie in Ihrer Dokumentbibliothek, auf die das Formularverarbeitungsmodell angewendet wird, das Menü <b>Automatisieren</b>, anschließend <b>KI-Generator</b> und dann <b>Formularverarbeitungsmodelldetails anzeigen</b> aus.</span><span class="sxs-lookup"><span data-stu-id="e4a17-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Menü „Automatisieren“](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="e4a17-148">Wählen Sie in den Modelldetails im Bereich <b>Aufbewahrungsbezeichnung</b> die Aufbewahrungsbezeichnung aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e4a17-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="e4a17-149">Klicken Sie dann auf <b>Speichern</b>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-149">Then select <b>Save</b>.</span></span>

     ![Hinzufügen zu einem bestehenden Formularverarbeitungsmodell](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="e4a17-151">So fügen Sie einem bestehenden Formularverarbeitungsmodell in Einstellungen der Aktiven Modelle eine Aufbewahrungsbezeichnung hinzu</span><span class="sxs-lookup"><span data-stu-id="e4a17-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="e4a17-152">Sie können einem vorhandenen Formularverarbeitungsmodell, das Ihnen gehört, über die Einstellungen der Aktiven Modelle in der Dokumentbibliothek, auf die das Modell angewendet wird, eine Aufbewahrungsbezeichnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e4a17-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="e4a17-153">Wählen Sie in der SharePoint-Dokumentbibliothek, auf die das Modell angewendet ist, das Symbol <b>Aktive Modelle anzeigen</b> und dann <b>Aktive Modelle anzeigen</b>.</b></span><span class="sxs-lookup"><span data-stu-id="e4a17-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Aktive Modelle anzeigen](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="e4a17-155">Wählen Sie unter <b>Aktive Modelle</b>das Formularverarbeitungsmodell aus, auf das Sie die Aufbewahrungsbezeichnung anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e4a17-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Modelldetails](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="e4a17-157">Wählen Sie in den Modelldetails im Bereich <b>Aufbewahrungsbezeichnung</b> die Aufbewahrungsbezeichnung aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e4a17-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="e4a17-158">Klicken Sie dann auf <b>Speichern</b>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="e4a17-159">Sie müssen der Modellbesitzer sein, damit der Bereich für Modelleinstellungen bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4a17-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e4a17-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4a17-160">See Also</span></span>
[<span data-ttu-id="e4a17-161">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="e4a17-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e4a17-162">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="e4a17-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e4a17-163">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="e4a17-163">Document Understanding overview</span></span>](document-understanding-overview.md)
