---
title: Extraktor in Microsoft SharePoint Syntex umbenennen
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
description: Erfahren Sie, wie und warum Sie einen Extraktor in Microsoft SharePoint Syntex umbenennen.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445996"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="81702-103">Extraktor in Microsoft SharePoint Syntex umbenennen</span><span class="sxs-lookup"><span data-stu-id="81702-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="81702-104">Irgendwann müssen Sie möglicherweise einen Extraktor umbenennen, wenn Sie auf ein extrahiertes Datenfeld mit einem anderen Namen verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="81702-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="81702-105">Beispielsweise beschließt Ihre Organisation, Änderungen an ihren Vertragsdokumenten vorzunehmen, und bezeichnet "Käufer" in ihren Dokumenten als "Kunden".</span><span class="sxs-lookup"><span data-stu-id="81702-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="81702-106">Wenn Sie in Ihrem Modell ein Feld "Käufer" extrahiert haben, können Sie es in "Kunde" umbenennen.</span><span class="sxs-lookup"><span data-stu-id="81702-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="81702-107">Wenn Sie Ihr aktualisiertes Modell mit Ihrer SharePoint-Dokumentbibliothek synchronisieren, wird in Ihrer Dokumentbibliotheksansicht eine neue Spalte "Kunde" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="81702-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="81702-108">In Ihrer Ansicht wird die Spalte "Käufer" für frühere Aktivitäten beibehalten, die neue Spalte "Kunde" wird jedoch für alle neuen Dokumente aktualisiert, die von Ihrem Modell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="81702-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="81702-109">Stellen Sie sicher, dass Sie Ihr aktualisiertes Modell mit den Dokumentbibliotheken synchronisieren, in denen Sie es zuvor angewendet haben, damit der neue Spaltenname angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="81702-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="81702-110">Umbenennen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="81702-110">Rename an extractor</span></span>

<span data-ttu-id="81702-111">Führen Sie die folgenden Schritte aus, um einen Entitätsextraktor umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="81702-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="81702-112">Wählen Sie im Inhaltscenter **Modelle** aus, um die Liste ihrer Modelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="81702-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="81702-113">Wählen Sie auf der Seite **Modelle** in der Spalte **Name** das Modell aus, für das Sie einen Extraktor umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="81702-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="81702-114">Wählen Sie unter **Entitätsextraktoren** den Namen des Extraktors aus, den Sie umbenennen möchten, und wählen Sie dann **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="81702-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Screenshot des Abschnitts "Entitätsextraktoren" mit einem ausgewählten Extraktor mit hervorgehobener Option "Umbenennen".](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="81702-116">Im Bereich **Entitätsextraktor umbenennen**:</span><span class="sxs-lookup"><span data-stu-id="81702-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="81702-117">a.</span><span class="sxs-lookup"><span data-stu-id="81702-117">a.</span></span> <span data-ttu-id="81702-118">Geben Sie unter **Neuer Name** den neuen Namen des Extraktors ein.</span><span class="sxs-lookup"><span data-stu-id="81702-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Screenshot mit dem Entitätsextraktions-Bedienfeld.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="81702-120">b.</span><span class="sxs-lookup"><span data-stu-id="81702-120">b.</span></span> <span data-ttu-id="81702-121">(Optional) Wählen Sie unter **Erweiterte Einstellungen**, ob Sie eine vorhandene Sitespalte zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="81702-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="81702-122">Wählen Sie **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="81702-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="81702-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81702-123">See Also</span></span>
[<span data-ttu-id="81702-124">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="81702-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="81702-125">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="81702-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="81702-126">Ein Modell umbenennen</span><span class="sxs-lookup"><span data-stu-id="81702-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="81702-127">Beschreibungstypen</span><span class="sxs-lookup"><span data-stu-id="81702-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="81702-128">Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="81702-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="81702-129">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="81702-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="81702-130">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="81702-130">Apply a model</span></span>](apply-a-model.md) 
