---
title: Duplizieren eines Modells in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Erfahren Sie, wie und warum Sie ein Modell in Microsoft SharePoint Syntex duplizieren können.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446035"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="a4417-103">Duplizieren eines Modells in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a4417-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="a4417-104">Das Duplizieren eines Dokumentverständnismodells kann Ihnen Zeit und Mühe ersparen, wenn Sie ein neues Modell erstellen müssen und wissen, dass ein vorhandenes Modell dem, was Sie benötigen, sehr ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="a4417-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="a4417-105">Ein vorhandenes Modell mit dem Namen „Verträge“ klassifiziert zum Beispiel die gleichen Dateien, mit denen Sie arbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="a4417-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="a4417-106">Ihr neues Modell wird einige der vorhandenen Daten extrahieren, muss aber aktualisiert werden, um einige zusätzliche Daten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="a4417-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="a4417-107">Anstatt ein neues Modell von Grund auf zu erstellen und zu trainieren, können Sie die Funktion „Modell duplizieren“ verwenden, um eine Kopie des Vertragsmodells zu erstellen, die auch alle zugehörigen Schulungselemente wie Beispieldateien und Entitätsextraktionsfunktionen kopiert.</span><span class="sxs-lookup"><span data-stu-id="a4417-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="a4417-108">Wenn Sie das Modell duplizieren, können Sie, nachdem Sie es umbenannt haben (z. B. in „Vertragsverlängerungen“), Aktualisierungen daran vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a4417-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="a4417-109">Sie können z. B. einige der vorhandenen extrahierten Felder entfernen, die Sie nicht benötigen, und dann das Modell trainieren, um ein neues zu extrahieren (z. B. „Verlängerungsdatum“).</span><span class="sxs-lookup"><span data-stu-id="a4417-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="a4417-110">Ein Modell duplizieren</span><span class="sxs-lookup"><span data-stu-id="a4417-110">Duplicate a model</span></span>

<span data-ttu-id="a4417-111">Führen Sie die folgenden Schritte aus, um ein Document Understanding Model zu duplizieren.</span><span class="sxs-lookup"><span data-stu-id="a4417-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="a4417-112">Wählen Sie im Inhaltscenter **Modelle** aus, um die Liste ihrer Modelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a4417-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="a4417-113">Wählen Sie auf der Seite **Modelle** das Modell aus, das Sie duplizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a4417-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="a4417-114">Wählen Sie entweder über das Menüband oder über die Schaltfläche **Aktionen anzeigen** (neben dem Modellnamen) die Option **Duplizieren**.</span><span class="sxs-lookup"><span data-stu-id="a4417-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Screenshot der Seite „Modelle“ mit einem ausgewählten Modell, bei dem die Optionen „Duplizieren“ hervorgehoben sind.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="a4417-116">Im Bedienfeld **Modell duplizieren**:</span><span class="sxs-lookup"><span data-stu-id="a4417-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="a4417-117">a.</span><span class="sxs-lookup"><span data-stu-id="a4417-117">a.</span></span> <span data-ttu-id="a4417-118">Geben Sie unter **Name** den neuen Namen des Modells ein, das Sie duplizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a4417-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Screenshot, der das Bedienfeld "Modell duplizieren" zeigt.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="a4417-120">b.</span><span class="sxs-lookup"><span data-stu-id="a4417-120">b.</span></span> <span data-ttu-id="a4417-121">Fügen Sie unter **Beschreibung** eine Beschreibung Ihres neuen Modells hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4417-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="a4417-122">c.</span><span class="sxs-lookup"><span data-stu-id="a4417-122">c.</span></span> <span data-ttu-id="a4417-123">(Optional) Wählen Sie unter **Erweiterte Einstellungen**, ob Sie einen vorhandenen [Inhaltstyp](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="a4417-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="a4417-124">Wählen Sie **Duplizieren**.</span><span class="sxs-lookup"><span data-stu-id="a4417-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4417-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4417-125">See Also</span></span>
[<span data-ttu-id="a4417-126">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="a4417-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a4417-127">Ein Modell umbenennen</span><span class="sxs-lookup"><span data-stu-id="a4417-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="a4417-128">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="a4417-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a4417-129">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="a4417-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="a4417-130">Beschreibungstypen</span><span class="sxs-lookup"><span data-stu-id="a4417-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="a4417-131">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="a4417-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="a4417-132">Barrierefreiheitsmodus für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a4417-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)