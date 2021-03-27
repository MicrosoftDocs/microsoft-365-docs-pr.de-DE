---
title: Vorhersagecodierungsmodul für Advanced eDiscovery (Vorschau)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Das neue Vorhersagecodierungsmodul in Advanced eDiscovery verwendet maschinelles Lernen, um Dokumente in einem Überprüfungssatz auf Vorhersage zu analysieren, welche Dokumente für Ihren Fall oder Ihre Untersuchung relevant sind.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382960"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="c84c3-103">Vorhersagecodierungsmodul für Advanced eDiscovery (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c84c3-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="c84c3-104">Mithilfe des neuen Vorhersagecodierungsmoduls in Advanced eDiscovery können Sie ein Modell erstellen und erstellen, um die Überprüfung von Dokumenten beginnend mit den relevantesten Dokumenten zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="c84c3-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="c84c3-105">Zu Beginn können Sie ein Modell erstellen, bis zu 50 Dokumente beschriften und dann Dokumente nach Modellvorhersageergebnissen filtern, um relevante nicht relevante Dokumente zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c84c3-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="c84c3-106">Hier finden Sie eine kurze Übersicht über den Workflow:</span><span class="sxs-lookup"><span data-stu-id="c84c3-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="c84c3-107">Öffnen Sie das Vorhersagecodierungsmodul in einem Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="c84c3-107">Open the predictive coding module in a review set.</span></span>

   ![Klicken Sie in einer Rezension auf die Dropdownliste Analysieren, um zum Vorhersagecodierungsmodul zu wechseln.](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="c84c3-109">Klicken Sie auf der Seite **Vorhersagecodierungsmodelle** auf **Neues Modell,** um ein neues Vorhersagecodierungsmodell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c84c3-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Erstellen eines neuen Modells](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="c84c3-111">Beschriften Sie mindestens 50 Dokumente **als relevant** oder **Nicht relevant.**</span><span class="sxs-lookup"><span data-stu-id="c84c3-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="c84c3-112">Diese Bezeichnung wird zum Trainieren des Systems verwendet.</span><span class="sxs-lookup"><span data-stu-id="c84c3-112">This labeling is used to train the system.</span></span>

   ![Bezeichnung von Dokumenten als relevant oder nicht relevant für die Ausbildung des Systems](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="c84c3-114">Wenden Sie **den Vorhersagebewertungsfilter** für Ihr Modell auf den Überprüfungssatz an.</span><span class="sxs-lookup"><span data-stu-id="c84c3-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="c84c3-115">Gehen Sie hierfür folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c84c3-115">To do this:</span></span>

   1. <span data-ttu-id="c84c3-116">Klicken Sie im Überprüfungssatz auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="c84c3-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="c84c3-117">Erweitern Sie **auf** der Seite Filterflyout den  Abschnitt **Analytics/ML,** und aktivieren Sie dann das Kontrollkästchen Vorhersageergebnis für das Modell, das Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c84c3-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="c84c3-118">Geben Sie **im Filter Prognoseergebnis** eine Vorhersageergebnis an.</span><span class="sxs-lookup"><span data-stu-id="c84c3-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="c84c3-119">Der Filter zeigt die Dokumente im Überprüfungssatz an, die mit der Vorhersagebewertung übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c84c3-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Angeben eines Vorhersageergebniss zum Filtern von Dokumenten](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="c84c3-121">Überwachen Sie die Leistung, den Status und die Stabilität Ihres Modells.</span><span class="sxs-lookup"><span data-stu-id="c84c3-121">Monitor the performance, status, and stability of your model.</span></span>

   ![Überwachen der Leistung, des Status und der Stabilität Ihres Modells](..\media\PredictiveCoding5.png)
