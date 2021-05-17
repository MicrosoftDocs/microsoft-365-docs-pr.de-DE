---
title: Hinzufügen von Daten aus einem Überprüfungssatz zu einem anderen Überprüfungssatz
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
description: Erfahren Sie, wie Sie Dokumente aus einem Überprüfungssatz auswählen und in einem anderen Satz in einem anderen Fall einzeln Advanced eDiscovery können.
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
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="fb835-103">Hinzufügen von Daten aus einem Prüfdateisatz zu einem anderen Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="fb835-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="fb835-104">In einigen Fällen kann es erforderlich sein, Dokumente aus einem Überprüfungssatz auszuwählen und einzeln in einem anderen Überprüfungssatz zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb835-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="fb835-105">Dies ist besonders hilfreich, wenn Sie Inhalte in einem Prüfdateisatz gefiltert haben und Analysen für die Teilmenge der Daten ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb835-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="fb835-106">Folgen Sie dem Workflow in diesem Artikel, um Inhalte aus einem Überprüfungssatz zu einem anderen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb835-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="fb835-107">Erstellen eines Überprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="fb835-107">Create a review set</span></span>

<span data-ttu-id="fb835-108">Bevor Sie beginnen, müssen Sie einen Überprüfungssatz erstellen, um die Daten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb835-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="fb835-109">Ein neuer Überprüfungssatz kann auf der Registerkarte **Überprüfungssätze** des Falls hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fb835-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="fb835-110">Weitere Informationen finden Sie unter [Create a review set](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="fb835-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="fb835-111">Schritt 1: Identifizieren von Inhalten, die einem anderen Überprüfungssatz hinzugefügt werden sollen</span><span class="sxs-lookup"><span data-stu-id="fb835-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="fb835-112">Sie können Inhalte aus einem Prüfdateisatz zu einem anderen Prüfdateisatz hinzufügen, indem Sie bestimmte Dokumente im ursprünglichen Prüfdateisatz oder alle von der Prüfdateisatzabfrage zurückgegeben Elemente auswählen.</span><span class="sxs-lookup"><span data-stu-id="fb835-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="fb835-113">Wenn Sie ausgewählte Elemente hinzufügen, wählen Sie die Elemente aus, wählen Sie **Aktion** aus, und wählen Sie dann Hinzufügen zu einem anderen **Überprüfungssatz aus.**</span><span class="sxs-lookup"><span data-stu-id="fb835-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Hinzufügen zu einem anderen Überprüfungssatz im Menü Aktion](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="fb835-115">Schritt 2: Angeben von Optionen zum Hinzufügen zu einem anderen Überprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="fb835-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="fb835-116">Wählen Sie auf der Flyoutseite Add **to another review set options** den Überprüfungssatz aus, dem Sie die Elemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb835-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="fb835-117">Wählen Sie aus, ob **Alle Suchergebnisse oder ausgewählte** Elemente hinzugefügt werden **sollen.**</span><span class="sxs-lookup"><span data-stu-id="fb835-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="fb835-118">**Zusätzliche Informationen** bieten Optionen zum Hinzufügen aller Metadaten aus den Elementen  und zum Hinzufügen der Tags (durch Aktivieren des Kontrollkästchens Bezeichnungen) aus dem Quellüberprüfungssatz, wenn die Dokumente dem neuen Prüfsatz hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fb835-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Optionen zum Hinzufügen von Daten zu einem anderen Überprüfungssatz](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="fb835-120">Nachdem Sie auf **Ok** geklickt haben, wird ein neuer Auftrag mit dem Namen **Hinzufügen** von Daten zu einem anderen Überprüfungssatz erstellt, um den Inhalt einem anderen Überprüfungssatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb835-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="fb835-121">Sie können zur Registerkarte **Aufträge wechseln** und den Fortschritt dieses Auftrags überwachen.</span><span class="sxs-lookup"><span data-stu-id="fb835-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="fb835-122">Weitere Informationen finden Sie unter [Manage jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="fb835-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
