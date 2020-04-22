---
title: Grundlegendes zur Ähnlichkeit von Dokumenten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Lesen Sie, wie der Ähnlichkeitswert von Dokumenten, die minimale Ähnlichkeit zweier Dateien, die als nahe Duplikate betrachtet werden müssen, in Advanced eDiscovery verwendet werden kann. '
ms.openlocfilehash: bfce2e3018c690fc0a25bcda8e2c03690a334dc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633410"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a><span data-ttu-id="2c6cb-103">Grundlegendes zur Ähnlichkeit von Dokumenten in Advanced eDiscovery (klassisch)</span><span class="sxs-lookup"><span data-stu-id="2c6cb-103">Understand document similarity in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="2c6cb-p101">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2c6cb-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2c6cb-106">In Advanced eDiscovery ist die Ähnlichkeit mit Dokumenten die minimale Ähnlichkeits Stufe, die erforderlich ist, damit zwei Dokumente als nahe Duplikate betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="2c6cb-107">Für die meisten Geschäftsanwendungen empfiehlt es sich, einen Ähnlichkeitswert von 60%-75% zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="2c6cb-108">Bei sehr schlechter Qualität des optischen Zeichen Erkennungs Materials (Optical Character Recognition, OCR) können niedrigere ähnlichkeitswerte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2c6cb-109">Nachdem Sie für einen bestimmten Fall festgelegt und ausgeführt wurde, kann der Ähnlichkeitswert nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="2c6cb-110">In einem nahe gelegenen Duplikat (ND) können Dokumente mit einer Ähnlichkeits Ebene unterhalb des Schwellenwerts für die Ähnlichkeit vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="2c6cb-111">Damit ein Dokument einer ND-Gruppe beitreten kann, muss mindestens ein Dokument im ND-Paket mit einer Ähnlichkeits Ebene vorhanden sein, die die Ähnlichkeit überschreitet.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="2c6cb-112">Angenommen, die Ähnlichkeit wird auf 80% festgelegt, Dokument F1 ähnelt dem Dokument F2 auf einer Ebene von 85%, und das Dokument F2 ähnelt dem Dokument F3 auf einer Ebene von 90%.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="2c6cb-113">Das Dokument F1 ähnelt jedoch möglicherweise dem Dokument F3 auf einer Ebene von nur 70%, die sich unterhalb des Schwellenwerts befindet.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="2c6cb-114">In diesem Beispiel werden jedoch alle Dokumente F1, F2 und F3 in dem ersten ND-festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="2c6cb-115">Ähnlich haben wir unter Verwendung eines Ähnlichkeits Werts von 80% möglicherweise zwei Sätze erstellt, EquiSet-1 und EquiSet-2.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="2c6cb-116">EquiSet-1 enthält die Dokumente E1 und E2.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="2c6cb-117">Equiset-2 enthält die Dokumente F1, F2 und F3.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="2c6cb-118">Die Ähnlichkeits Grade werden wie folgt dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2c6cb-118">The levels of resemblance are illustrated as follows:</span></span>
  
![Dokument Ähnlichkeit](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="2c6cb-120">Es wird davon ausgegangen, dass ein anderes Dokument, x1, jetzt eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="2c6cb-121">Die Ähnlichkeit zwischen x1 und E3 beträgt 87%.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="2c6cb-122">Ähnlich ist die Ähnlichkeit zwischen x1 und F1 92%.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="2c6cb-123">Dadurch werden EquiSet-1, EquiSet-2 und x1 nun zu einem ND-Paket zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![Dokument Ähnlichkeit](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="2c6cb-125">Wenn zwei Dokumente einem ND-Satz zugewiesen werden, bleiben Sie in demselben ND-Satz zusammen, auch wenn dem Satz zusätzliche Dokumente hinzugefügt werden oder wenn die Sätze zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="2c6cb-126">Nachdem Mengen zusammengeführt wurden, kann sich das Pivot-Dokument ändern, wenn einem Satz neue Dokumente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cb-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2c6cb-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c6cb-127">See also</span></span>

[<span data-ttu-id="2c6cb-128">Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="2c6cb-128">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2c6cb-129">Festlegen von Analyseoptionen</span><span class="sxs-lookup"><span data-stu-id="2c6cb-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2c6cb-130">Festlegen von Text ignorieren</span><span class="sxs-lookup"><span data-stu-id="2c6cb-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2c6cb-131">Einstellungen für die erweiterte Analyse Einstellung</span><span class="sxs-lookup"><span data-stu-id="2c6cb-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2c6cb-132">Anzeigen von Analyseergebnissen</span><span class="sxs-lookup"><span data-stu-id="2c6cb-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

