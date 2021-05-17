---
title: Einrichten von Smarttags in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Mit Smarttags können Sie die Machine Learning-Funktionen beim Überprüfen von Inhalten in einem Advanced eDiscovery anwenden. Verwenden Sie Smarttaggruppen, um die Ergebnisse von Machine-Learning-Erkennungsmodellen wie dem Anwalts-Client-Berechtigungsmodell anzeigen zu können.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081082"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="057b0-104">Einrichten von Smarttags in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="057b0-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="057b0-105">Maschinelles Lernen (ML)-Funktionen in Advanced eDiscovery können Ihnen helfen, den Entscheidungsprozess effizienter zu gestalten, wenn Sie Falldokumente in einem Überprüfungssatz überprüfen.</span><span class="sxs-lookup"><span data-stu-id="057b0-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="057b0-106">Smarttags sind eine Möglichkeit, die Funktionen ML, wo die Entscheidungen aufgezeichnet werden: beim Taggen von Dokumenten während der Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="057b0-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="057b0-107">Wenn Sie eine Smarttaggruppe erstellen, werden die Entscheidungen, die das Ergebnis des ML-Modells sind, das Sie der Smarttaggruppe zugeordnet haben, in der Zeile mit den Tags in der Taggruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="057b0-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="057b0-108">Dies hilft ihnen, ML informationen in der Zeile zu sehen, wenn Sie bestimmte Dokumente überprüfen.</span><span class="sxs-lookup"><span data-stu-id="057b0-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="057b0-109">Einrichten einer Smarttaggruppe</span><span class="sxs-lookup"><span data-stu-id="057b0-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="057b0-110">Klicken Sie in einem Überprüfungssatz auf **Überprüfungssatz verwalten,** und klicken Sie dann **auf Tags verwalten.**</span><span class="sxs-lookup"><span data-stu-id="057b0-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="057b0-111">Klicken **Sie auf Taggruppe hinzufügen,** und wählen Sie **dann Smarttaggruppe hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="057b0-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="057b0-112">Wählen Sie das ML aus, das Sie der Taggruppe zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="057b0-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="057b0-113">Dadurch werden eine Taggruppe und *untergeordnete N-Tags* erstellt, wobei *N* die Anzahl möglicher Ausgaben des Modells ist.</span><span class="sxs-lookup"><span data-stu-id="057b0-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="057b0-114">Das Erkennungsmodell der [Anwalts-Client-Rechte verfügt](attorney-privilege-detection.md) beispielsweise über zwei mögliche Ausgaben:</span><span class="sxs-lookup"><span data-stu-id="057b0-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="057b0-115">**Positiv** – Verwenden Sie zum Markieren von Dokumenten, die privilegierte Inhalte des Anwaltsclients enthalten.</span><span class="sxs-lookup"><span data-stu-id="057b0-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="057b0-116">**Negativ** – Verwenden Sie zum Markieren von Dokumenten, die keine privilegierten Inhalte des Anwaltsclients enthalten.</span><span class="sxs-lookup"><span data-stu-id="057b0-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="057b0-117">Wenn Sie dieses Modell auswählen, wird eine Taggruppe mit zwei untergeordneten Tags erstellt (ein untergeordnetes Tag mit dem Namen **Positive** und das andere mit dem Namen **Negative**) für den Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="057b0-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="057b0-118">In diesem Beispiel entspricht jedes untergeordnete Tag einer der möglichen Ausgaben aus dem Erkennungsmodell für Anwalts-Client-Rechte.</span><span class="sxs-lookup"><span data-stu-id="057b0-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="057b0-119">Optional können Sie die Taggruppe und die untergeordneten Tags umbenennen.</span><span class="sxs-lookup"><span data-stu-id="057b0-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="057b0-120">Beispielsweise könnten Sie das **Positive-Tag** in **Privileged** und **das Negative-Tag** in **Not privileged umbenennen.**</span><span class="sxs-lookup"><span data-stu-id="057b0-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="057b0-121">Verwenden von Smarttags</span><span class="sxs-lookup"><span data-stu-id="057b0-121">How to use smart tags</span></span>

<span data-ttu-id="057b0-122">Beim Überprüfen eines Dokuments werden die Ergebnisse des Modells neben dem entsprechenden untergeordneten Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="057b0-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="057b0-123">Wenn Sie beispielsweise über eine Smarttaggruppe für die Erkennung von Anwalts-Client-Berechtigungen verfügen und ein Dokument überprüfen, das potenziell privilegierte Berechtigungen hat, wird der Grund für diese Schlussfolgerung neben dem entsprechenden Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="057b0-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="057b0-124">Beachten Sie, dass das Tag nicht automatisch auf das Dokument angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="057b0-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="057b0-125">Der Prüfer entscheidet über das Taggen des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="057b0-125">The reviewer makes the decision about how to tag the document.</span></span>
