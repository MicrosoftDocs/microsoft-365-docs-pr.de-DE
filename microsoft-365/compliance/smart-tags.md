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
description: Mit Smarttags können Sie die Lernfunktionen für Computer anwenden, wenn Sie Inhalte in einem erweiterten eDiscovery-Fall überprüfen. Verwenden Sie smarttaggruppen, um die Ergebnisse von Computer Lern-Erkennungs Modellen anzuzeigen, beispielsweise das Anwalts-Client-Berechtigungsmodell.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081082"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="c8167-104">Einrichten von Smarttags in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c8167-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="c8167-105">Das maschinelle Lernen (ml) Funktionen in Advanced eDiscovery kann Ihnen helfen, den Entscheidungsprozess effizienter zu gestalten, wenn Sie Fall Dokumente in einem Überprüfungs Satzes überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c8167-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="c8167-106">Smarttags sind eine Möglichkeit, die ml-Funktionen an die Stelle zu bringen, an der die Entscheidungen aufgezeichnet werden: beim Markieren von Dokumenten während der Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="c8167-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="c8167-107">Wenn Sie eine smarttaggruppe erstellen, werden die Entscheidungen, die das Ergebnis des ml-Modells sind, das Sie der smarttaggruppe zugeordnet haben, Inline mit den Tags in der Tag-Gruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8167-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="c8167-108">Dadurch werden die Informationen zu ml-Ergebnissen Inline angezeigt, wenn Sie bestimmte Dokumente überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c8167-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="c8167-109">Vorgehensweise Einrichten einer smarttaggruppe</span><span class="sxs-lookup"><span data-stu-id="c8167-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="c8167-110">Klicken Sie in einem Überprüfungs Satzes auf **Überarbeitungs Gruppe verwalten** , und klicken Sie dann auf **Tags verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c8167-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="c8167-111">Klicken Sie auf **Tag-Gruppe hinzufügen** und dann auf **smarttaggruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c8167-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="c8167-112">Wählen Sie das ml-Modell aus, das Sie der Transpondergruppe zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="c8167-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="c8167-113">Dadurch werden eine Tag-Gruppe und *n* untergeordnete Tags erstellt, wobei *n* für die Anzahl der möglichen Ausgaben des Modells steht.</span><span class="sxs-lookup"><span data-stu-id="c8167-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="c8167-114">Beispielsweise weist das " [Attorney-Client-Berechtigungs Erkennungs Modell](attorney-privilege-detection.md) " zwei mögliche Ausgaben auf:</span><span class="sxs-lookup"><span data-stu-id="c8167-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="c8167-115">**Positiv** – verwenden Sie, um Dokumente zu markieren, die Inhalte für Rechtsanwälte-Clients enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8167-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="c8167-116">**Negativ** – verwenden Sie diese, um Dokumente zu markieren, die keinen Anwalt-Client-privilegierten Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8167-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="c8167-117">Wenn Sie dieses Modell auswählen, wird eine Transpondergruppe mit zwei untergeordneten Tags erstellt (ein untergeordnetes Tag mit dem Namen " **positive** " und das andere " **negative**") für die Überprüfungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="c8167-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="c8167-118">In diesem Beispiel entspricht jedes untergeordnete Tag einem der möglichen Ausgaben des Erkennungs Modells für das Anwalts Client-Privileg.</span><span class="sxs-lookup"><span data-stu-id="c8167-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="c8167-119">Optional können Sie die Tag-Gruppe und die untergeordneten Tags umbenennen.</span><span class="sxs-lookup"><span data-stu-id="c8167-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="c8167-120">Beispielsweise können Sie das **positive** -Tag in " **privileged** " und das **negative** -Tag auf " **nicht privilegierte**" umbenennen.</span><span class="sxs-lookup"><span data-stu-id="c8167-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="c8167-121">Verwenden von Smarttags</span><span class="sxs-lookup"><span data-stu-id="c8167-121">How to use smart tags</span></span>

<span data-ttu-id="c8167-122">Wenn Sie ein Dokument überprüfen, werden die Ergebnisse des Modells neben dem entsprechenden untergeordneten Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8167-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="c8167-123">Wenn Sie beispielsweise eine smarttaggruppe für die Erkennung von Anwalts Mandanten Berechtigungen haben und ein Dokument überprüfen, das potenziell privilegiert ist, wird der Grund für diese Schlussfolgerung neben dem entsprechenden Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8167-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="c8167-124">Es ist wichtig zu beachten, dass das Tag nicht automatisch auf das Dokument angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8167-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="c8167-125">Der Prüfer trifft die Entscheidung, wie das Dokument markiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8167-125">The reviewer makes the decision about how to tag the document.</span></span>
