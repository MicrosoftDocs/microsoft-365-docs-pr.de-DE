---
title: Deversion des Relevanzmoduls in Advanced eDiscovery
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
ms.collection: M365-security-compliance
description: Das Relevanzmodul in Advanced eDiscovery wird am 10. März 2021 eingestellt. In diesem Artikel wird erläutert, was sie tun müssen, bevor die Relevanz eingestellt wird. Insbesondere müssen Sie alle noch nicht fertig gestellten Modelle fertig gestellt haben, indem Sie die Batchberechnung ausführen, damit Sie die Metadaten aus dem Modell beibehalten können.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122529"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="d9acd-105">Deversion des Relevanzmoduls in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d9acd-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="d9acd-106">Am 10. März 2021 wird das Relevanzmodul in Advanced eDiscovery zurück weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="d9acd-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="d9acd-107">Diese Deversion bedeutet, dass Organisationen keinen Zugriff mehr auf das Relevanzmodul haben (indem sie die Relevanz des Überprüfungssatzs in einem  >   Advanced eDiscovery-Fall verwalten) oder auf vorhandene Relevanzmodelle zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d9acd-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="d9acd-108">Das aktuelle Relevanzmodul, das eingestellt wird, wird in Q2 CY 2021 durch eine neue Vorhersagecodierungslösung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="d9acd-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="d9acd-109">Mit dieser neuen Funktion können Organisationen ihre eigenen Vorhersagecodierungsmodelle in einem einfacheren und intuitiveren Workflow erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9acd-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="d9acd-110">Zur Vorbereitung auf diese bevorstehende Ausmusterung wird empfohlen, dass Organisationen, die das Relevanzmodul verwenden, die Ausgabe ihres Modells vor dem Ausmusterungsdatum exportieren, indem sie eine Batchberechnung für alle vorhandenen Modelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9acd-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="d9acd-111">Alle Relevanzbewertung aus Ihrem Modell wird dauerhaft im entsprechenden Überprüfungssatz gespeichert und kann beim Exportieren von Dokumenten darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d9acd-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="d9acd-112">Relevanzergebnisse werden auch als Metadaten in der Ladedatei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d9acd-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="d9acd-113">Außerdem können Sie weiterhin Inhalte im Überprüfungssatz basierend auf der Relevanzbewertung filtern und haben Zugriff auf alle Metadaten, die von Ihren Relevanzmodellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d9acd-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="d9acd-114">Vollständige noch nicht fertig gestellte Modelle</span><span class="sxs-lookup"><span data-stu-id="d9acd-114">Complete unfinished models</span></span>

<span data-ttu-id="d9acd-115">Führen Sie für alle noch nicht abgeschlossenen Relevanzmodelle die Bewertung, Schulung und Batchberechnung aus, damit Sie das Modell auf die Dokumente in einem Überprüfungssatz anwenden können.</span><span class="sxs-lookup"><span data-stu-id="d9acd-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="d9acd-116">Wenn Sie die Batchberechnung abschließen, werden die Informationen nach dem Beendigungsdatum des Relevanzmoduls beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d9acd-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="d9acd-117">Hier sind die Schritte zum Abschließen noch nicht fertig gestellter Modelle:</span><span class="sxs-lookup"><span data-stu-id="d9acd-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="d9acd-118">Schulen Sie Ihr Modell, bis es stabilisiert und für die Batchberechnung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="d9acd-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="d9acd-119">Siehe [Tagging und Relevanztraining.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d9acd-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="d9acd-120">Der folgende Screenshot zeigt ein Modul, das für eine Batchberechnung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="d9acd-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="d9acd-121">Beachten Sie, dass die Bewertung und Schulung abgeschlossen ist und der nächste Schritt das Ausführen der Batchberechnung ist.</span><span class="sxs-lookup"><span data-stu-id="d9acd-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Screenshot des Modells, das für die Batchberechnung bereit ist](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="d9acd-123">Führen Sie die Batchberechnung aus.</span><span class="sxs-lookup"><span data-stu-id="d9acd-123">Run the Batch calculation.</span></span> <span data-ttu-id="d9acd-124">Siehe ["Ausführen der Batchberechnung".](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="d9acd-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="d9acd-125">Überprüfen Sie, ob die Batchberechnung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d9acd-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="d9acd-126">Siehe [Ergebnisse der Batchberechnung.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="d9acd-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="d9acd-127">Wenn Sie Hilfe beim Abschließen noch nicht fertig gestellter Relevanzmodelle erhalten, wenden Sie sich an den Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="d9acd-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
