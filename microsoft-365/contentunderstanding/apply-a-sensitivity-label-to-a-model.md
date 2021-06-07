---
title: Anwenden einer Vertraulichkeitsbezeichnung auf ein Modell in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Erfahren Sie, wie Sie eine Vertraulichkeitsbezeichnung auf ein Modell in SharePoint Syntex anwenden.
ms.openlocfilehash: 799ab3fa0fcdc9af9d227428056d2cd7abeaf539
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706701"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="92174-103">Anwenden einer Vertraulichkeitsbezeichnung auf ein Modell in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="92174-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="92174-104">Sie können auf einfache Weise eine [Vertraulichkeitsbezeichnung](../compliance/sensitivity-labels.md) auf Dokumentverständnismodelle in Microsoft SharePoint Syntex anwenden.</span><span class="sxs-lookup"><span data-stu-id="92174-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="92174-105">Dieses Feature ist in Formularverarbeitungsmodellen noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="92174-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="92174-106">Mit Vertraulichkeitsbezeichnungen können Sie Richtlinien für Verschlüsselung, Freigabe und bedingten Zugriff auf Dokumente anwenden, die Ihr Modell identifiziert.</span><span class="sxs-lookup"><span data-stu-id="92174-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="92174-107">Sie möchten zum Beispiel, dass Ihr Modell nicht nur alle Finanzdokumente identifiziert, die Bankkontonummern oder Kreditkartennummern enthalten, die in Ihre Dokumentbibliothek hochgeladen werden, sondern auch eine Vertraulichkeitsbezeichnung für die *Verschlüsselung* auf diese Dokumente anwendet, um einzuschränken, wer auf diese Inhalte zugreifen kann und wie sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="92174-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span>

<span data-ttu-id="92174-108">Über die Modelleinstellungen auf der Startseite Ihres Modells können Sie eine bereits vorhandene Vertraulichkeitsbezeichnung auf Ihr Modell anwenden.</span><span class="sxs-lookup"><span data-stu-id="92174-108">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="92174-109">Die Bezeichnung muss bereits veröffentlicht sein, um für die Auswahl in „Modelleinstellungen“ verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="92174-109">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="92174-110">Damit Vertraulichkeitsbezeichnungen für die Anwendung auf Ihre Dokumentverständnismodelle verfügbar sind, müssen sie [im Microsoft 365 Compliance Center erstellt und veröffentlicht werden](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="92174-110">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="92174-111">Hinzufügen einer Vertraulichkeitsbezeichnung auf ein Dokumentverständnismodell</span><span class="sxs-lookup"><span data-stu-id="92174-111">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="92174-112">Wählen Sie auf der Modell-Startseite **Modelleinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="92174-112">From the model home page, select **Model settings**.</span></span>

   ![Screenshot der Modellseite mit der hervorgehobenen Option „Modelleinstellungen“.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="92174-114">Wählen Sie im Bereich **Modelleinstellungen** im Abschnitt **Compliance** das Menü **Vertraulichkeitsbezeichnung** aus, um eine Liste der Vertraulichkeitsbezeichnungen anzuzeigen, die Sie auf das Modell anwenden können.</span><span class="sxs-lookup"><span data-stu-id="92174-114">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Screenshot des Bereichs „Modelleinstellungen“ zeigt das Menü „Vertraulichkeitsbezeichnung“.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="92174-116">Wählen Sie die Vertraulichkeitsbezeichnung aus, die auf das Modell angewendet werden soll, und wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="92174-116">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="92174-117">Nachdem Sie die Vertraulichkeitsbezeichnung auf Ihr Modell angewandt haben, können Sie es auf Folgendes anwenden:</span><span class="sxs-lookup"><span data-stu-id="92174-117">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="92174-118">Neue Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="92174-118">New document library</span></span>
- <span data-ttu-id="92174-119">Dokumentbibliothek, auf die das Modell bereits angewendet wird</span><span class="sxs-lookup"><span data-stu-id="92174-119">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="92174-120">Anwenden der Vertraulichkeitsbezeichnung auf eine Dokumentbibliothek, auf die das Modell bereits angewendet wird</span><span class="sxs-lookup"><span data-stu-id="92174-120">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="92174-121">Wenn Ihr Dokumentverständnismodell bereits auf eine Dokumentbibliothek angewendet wurde, können Sie die folgenden Schritte ausführen, um die Aktualisierung Ihrer Vertraulichkeitsbezeichnung mit Ihrem Modell zu synchronisieren, so dass diese auf Ihre Dokumentbibliothek angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="92174-121">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="92174-122">Wählen Sie auf der Startseite Ihres Modells im Abschnitt **Bibliotheken mit diesem Modell** die Dokumentbibliothek aus, auf welche die Aktualisierung der Vertraulichkeitsbezeichnung angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="92174-122">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="92174-123">Wählen Sie **Synchronisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="92174-123">Select **Sync**.</span></span>

   ![Screenshot zeigt den Abschnitt „Bibliotheken mit diesem Modell“ mit der hervorgehobenen Option „Synchronisieren“.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="92174-125">Nachdem Sie die Aktualisierung angewendet und mit Ihrem Modell synchronisiert haben, können Sie die folgenden Schritte ausführen, um zu überprüfen, ob es angewendet wurde:</span><span class="sxs-lookup"><span data-stu-id="92174-125">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="92174-126">Wählen Sie im Inhaltscenter im Abschnitt **Bibliotheken mit diesem Modell** die Bibliothek aus, auf die das aktualisierte Modell angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="92174-126">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="92174-127">Wählen Sie in der Dokumentbibliotheksansicht das Symbol "Informationen" aus, um die Modelleigenschaften zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="92174-127">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="92174-128">Wählen Sie in der Liste **Aktive Modelle** das aktualisierte Modell aus.</span><span class="sxs-lookup"><span data-stu-id="92174-128">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="92174-129">Im Abschnitt **Vertraulichkeitsbezeichnung** werden Sie den Namen der angewendeten Vertraulichkeitsbezeichnung sehen.</span><span class="sxs-lookup"><span data-stu-id="92174-129">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="92174-130">Auf der Ansichtsseite Ihres Modells in Ihrer Dokumentbibliothek wird eine neue Spalte **Vertraulichkeitsbezeichnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92174-130">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="92174-131">Wenn Ihr Modell identifizierte Dateien als seinem Inhaltstyp zugeordnet klassifiziert und sie in der Bibliotheksansicht auflistet, wird in der Spalte **Vertraulichkeitsbezeichnung** auch der Name der Vertraulichkeitsbezeichnung angezeigt, die über das Modell auf die Dateien angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="92174-131">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="92174-132">Beispielsweise werden alle Finanzdokumente, die Ihr Modell identifiziert, ebenfalls mit der Vertraulichkeitsbezeichnung *Verschlüsselung* versehen, um zu verhindern, dass nicht autorisierte Personen auf sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="92174-132">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="92174-133">Wenn eine nicht autorisierte Person versucht, auf die Datei in der Dokumentbibliothek zuzugreifen, wird eine Fehlermeldung angezeigt, die besagt, dass der Zugriff aufgrund der angewendeten Vertraulichkeitsbezeichnung nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="92174-133">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="92174-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92174-134">See also</span></span>

[<span data-ttu-id="92174-135">Anwenden einer Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="92174-135">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="92174-136">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="92174-136">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="92174-137">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="92174-137">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="92174-138">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="92174-138">Document Understanding overview</span></span>](document-understanding-overview.md)