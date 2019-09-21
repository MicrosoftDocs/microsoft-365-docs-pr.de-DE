---
title: Hinzufügen von Daten aus einem Überprüfungs Sätze zu einem anderen Überprüfungs Satzes
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: bd33d57380e99225d741b9c38677c2b49694139a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081183"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="ae0bb-102">Hinzufügen von Daten zu einem Überprüfungs Satzes aus einer anderen Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="ae0bb-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="ae0bb-103">In einigen Fällen kann es erforderlich sein, einen Teil von Dokumenten aus einer Überprüfungsgruppe zu schnitzen und einzeln in einem anderen Überprüfungs Satzes zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="ae0bb-104">Dies ist besonders nützlich, wenn Sie Inhalte in einem Überprüfungs Satz ausgemerzt haben und Analysen für die Teilmenge der Daten ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="ae0bb-105">Führen Sie den Workflow in diesem Artikel aus, um Inhalte aus einem Überprüfungs Satz zu einem anderen zu hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-105">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ae0bb-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="ae0bb-106">Before you begin</span></span>

<span data-ttu-id="ae0bb-107">Bevor Sie beginnen, müssen Sie eine neue Überprüfungsgruppe erstellen, der die Daten hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="ae0bb-108">Auf der Registerkarte **Überprüfungs Sätze** der Groß-/Kleinschreibung kann ein neuer Überprüfungs Satz hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="ae0bb-109">Weitere Informationen finden Sie unter [Erstellen eines Überprüfungs Satzes](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="ae0bb-109">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="ae0bb-110">Schritt 1: Identifizieren von Inhalten, die zu einem anderen Überprüfungs Sätze hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="ae0bb-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="ae0bb-111">Sie können Inhalte aus einer Überprüfungsgruppe zu einem anderen hinzufügen, indem Sie bestimmte Dokumente in der Quell Überprüfungsgruppe oder b seleting alle Elemente, die von der Abfrage zum Überprüfen zurückgegeben werden, auswählen.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-111">You can add content from one review set to another one by selecting specific documents in the source review set or b seleting all items returned by review set query.</span></span>  <span data-ttu-id="ae0bb-112">Wenn Sie ausgewählte Elemente hinzufügen, wählen Sie die Elemente aus, klicken Sie auf **Aktion**, und klicken Sie dann auf **zu einem anderen Überprüfungs Satzes hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-112">If you're adding selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![Zu einem anderen Überprüfungs Satzes hinzufügen](media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="ae0bb-114">Schritt 2: Angeben von Optionen für das Hinzufügen zu einer anderen Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="ae0bb-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="ae0bb-115">Wählen Sie auf der Flyout-Seite **Add to other Review Sets Options** die Überprüfungsgruppe aus, der Sie die Elemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-115">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="ae0bb-116">Wählen Sie aus, ob **alle Suchergebnisse** oder **ausgewählten Elemente**hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="ae0bb-117">Zusätzliche Informationen bieten Optionen zum Einschließen aller Metadaten aus den Elementen und zum Einschließen der Tags (durch Aktivieren des Kontrollkästchens **Beschriftungen** ) aus dem Quell Überprüfungs Satzes, wenn die Dokumente zum neuen Überprüfungs Sätzen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-117">Additional information provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** checkbox) from the source review set when the documents are added to the new review set.</span></span>  

![Zu einem anderen Überprüfungs Satzes hinzufügen](media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="ae0bb-119">Nachdem Sie auf **OK**geklickt haben, wird ein neuer Auftrag (benanntes **Hinzufügen von Daten zu einem anderen Überprüfungs Sätze**) erstellt, um den Inhalt zu einem anderen Überprüfungs hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-119">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to a another review set.</span></span>  <span data-ttu-id="ae0bb-120">Sie können zur Registerkarte **Aufträge** wechseln und den Status dieses Auftrags überwachen.</span><span class="sxs-lookup"><span data-stu-id="ae0bb-120">You can go to **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="ae0bb-121">Weitere Informationen finden Sie unter [Manage Jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="ae0bb-121">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
