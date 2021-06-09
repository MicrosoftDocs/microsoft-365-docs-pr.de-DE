---
title: Einstellung des Relevanzmoduls in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Das Relevanzmodul in Advanced eDiscovery wird am 10. März 2021 eingestellt. In diesem Artikel wird erläutert, was Sie tun müssen, bevor die Relevanz eingestellt wird. Insbesondere müssen alle nicht fertig gestellten Modelle fertig gestellt werden, indem Batchberechnungen ausgeführt werden, damit Sie die Metadaten aus dem Modell beibehalten können.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821997"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="7ddaf-105">Einstellung des Relevanzmoduls in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7ddaf-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="7ddaf-106">Am 10. März 2021 werden wir das Relevanzmodul in Advanced eDiscovery zurückziehen.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="7ddaf-107">Diese Einstellung bedeutet, dass Organisationen keinen Zugriff mehr auf das Relevanzmodul haben (indem sie den **Prüfdateisatz**  >  **"Relevanz"** in einem Advanced eDiscovery Fall verwalten) oder auf vorhandene Relevanzmodelle zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="7ddaf-108">Das aktuelle Relevanzmodul, das eingestellt wird, wird in Q2 CY 2021 durch eine neue Lösung für die Vorhersagecodierung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="7ddaf-109">Mit dieser neuen Funktionalität können Organisationen ihre eigenen Modelle für die Vorhersagecodierung in einem einfacheren und intuitiveren Workflow erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="7ddaf-110">Um sich auf diese bevorstehende Einstellung vorzubereiten, empfehlen wir Organisationen, die das Relevanzmodul verwenden, die Ausgabe ihres Modells vor dem Einstellungsdatum zu exportieren, indem Sie eine Batchberechnung für alle vorhandenen Modelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="7ddaf-111">Alle Relevanzbewertungen aus Ihrem Modell werden dauerhaft im entsprechenden Prüfdateisatz gespeichert und können beim Exportieren von Dokumenten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="7ddaf-112">Relevanzbewertungen werden auch als Metadaten in der Ladedatei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="7ddaf-113">Außerdem können Sie weiterhin Inhalte im Prüfdateisatz basierend auf der Relevanzbewertung filtern und haben Zugriff auf alle Metadaten, die von Ihren Relevanzmodellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="7ddaf-114">Vollständige nicht fertige Modelle</span><span class="sxs-lookup"><span data-stu-id="7ddaf-114">Complete unfinished models</span></span>

<span data-ttu-id="7ddaf-115">Führen Sie für alle nicht fertig gestellten Relevanzmodelle die Bewertung, Schulung und Batchberechnung durch, damit Sie das Modell auf die Dokumente in einem Prüfdateisatz anwenden können.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="7ddaf-116">Wenn Sie die Batchberechnung abschließen, bleiben die Informationen nach dem Einstellungsdatum des Relevanzmoduls erhalten.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="7ddaf-117">Hier sind die Schritte zum Abschließen aller nicht fertig gestellten Modelle:</span><span class="sxs-lookup"><span data-stu-id="7ddaf-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="7ddaf-118">Schulen Sie Ihr Modell, bis es stabil ist und für die Batchberechnung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="7ddaf-119">Siehe ["Tagging" und "Relevanzschulung".](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="7ddaf-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="7ddaf-120">Der folgende Screenshot zeigt ein Modul, das für eine Batchberechnung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="7ddaf-121">Beachten Sie, dass die Bewertung und Schulung abgeschlossen ist und der nächste Schritt die Batchberechnung ist.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Screenshot des Modells, das für die Batchberechnung bereit ist](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="7ddaf-123">Führen Sie die Batchberechnung aus.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-123">Run the Batch calculation.</span></span> <span data-ttu-id="7ddaf-124">Weitere Informationen finden Sie unter [Ausführen der Batchberechnung.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="7ddaf-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="7ddaf-125">Stellen Sie sicher, dass die Batchberechnung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="7ddaf-126">Siehe [Batchberechnungsergebnisse.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="7ddaf-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="7ddaf-127">Wenn Sie Hilfe zum Abschließen nicht fertiger Relevanzmodelle haben, wenden Sie sich an den Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="7ddaf-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
