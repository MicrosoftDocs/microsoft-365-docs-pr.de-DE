---
title: Hinzufügen von Daten aus einem Überprüfungs Sätze zu einem anderen Überprüfungs Satzes
f1.keywords:
- NOCSH
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
description: Hier erfahren Sie, wie Sie Dokumente aus einer Überprüfungsgruppe auswählen und mit diesen einzeln in einer anderen Gruppe in einem erweiterten eDiscovery-Fall arbeiten.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285179"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="d3c53-103">Hinzufügen von Daten aus einem Prüfdateisatz zu einem anderen Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="d3c53-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="d3c53-104">In einigen Fällen kann es erforderlich sein, Dokumente aus einer Überprüfungsgruppe auszuwählen und einzeln in einem anderen Überprüfungs Satzes zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3c53-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="d3c53-105">Dies ist besonders hilfreich, wenn Sie Inhalte in einem Prüfdateisatz gefiltert haben und Analysen für die Teilmenge der Daten ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d3c53-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="d3c53-106">Führen Sie den Workflow in diesem Artikel aus, um Inhalte aus einem Überprüfungs Satz zu einem anderen zu hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3c53-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="d3c53-107">Erstellen eines Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="d3c53-107">Create a review set</span></span>

<span data-ttu-id="d3c53-108">Bevor Sie beginnen, müssen Sie eine Überprüfungsgruppe erstellen, der die Daten hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3c53-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="d3c53-109">Auf der Registerkarte **Überprüfungs Sätze** der Groß-/Kleinschreibung kann ein neuer Überprüfungs Satz hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d3c53-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="d3c53-110">Weitere Informationen finden Sie unter [Erstellen eines Überprüfungs Satzes](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="d3c53-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="d3c53-111">Schritt 1: Identifizieren von Inhalten, die zu einem anderen Überprüfungs Sätze hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="d3c53-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="d3c53-112">Sie können Inhalte aus einem Prüfdateisatz zu einem anderen Prüfdateisatz hinzufügen, indem Sie bestimmte Dokumente im ursprünglichen Prüfdateisatz oder alle von der Prüfdateisatzabfrage zurückgegeben Elemente auswählen.</span><span class="sxs-lookup"><span data-stu-id="d3c53-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="d3c53-113">Wenn Sie ausgewählte Elemente hinzufügen, wählen Sie die Elemente aus, wählen Sie **Aktion**aus, und wählen Sie dann **zu einem anderen Überprüfungs Satzes hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="d3c53-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Zu einem anderen Überprüfungs Satzes im Menü "Aktion" hinzufügen](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="d3c53-115">Schritt 2: Angeben von Optionen für das Hinzufügen zu einer anderen Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="d3c53-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="d3c53-116">Wählen Sie auf der Flyout-Seite **Add to other Review Sets Options** die Überprüfungsgruppe aus, der Sie die Elemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d3c53-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="d3c53-117">Wählen Sie aus, ob **alle Suchergebnisse** oder **ausgewählten Elemente**hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3c53-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="d3c53-118">**Zusätzliche Informationen** bieten Optionen zum Einschließen aller Metadaten aus den Elementen und zum Einschließen der Tags (durch Aktivieren des Kontrollkästchens **Beschriftungen** ) aus dem Quell Überprüfungs Satzes, wenn die Dokumente zum neuen Überprüfungs Sätzen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d3c53-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Optionen zum Hinzufügen von Daten zu einem anderen Überprüfungs Satzes](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="d3c53-120">Nachdem Sie auf **OK**geklickt haben, wird ein neuer Auftrag (mit dem Namen **Hinzufügen von Daten zu einem anderen Überprüfungs Sätze**) erstellt, um den Inhalt zu einem anderen Überprüfungs Satzes hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3c53-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="d3c53-121">Sie können auf die Registerkarte **Aufträge** wechseln und den Status dieses Auftrags überwachen.</span><span class="sxs-lookup"><span data-stu-id="d3c53-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="d3c53-122">Weitere Informationen finden Sie unter [Manage Jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="d3c53-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
