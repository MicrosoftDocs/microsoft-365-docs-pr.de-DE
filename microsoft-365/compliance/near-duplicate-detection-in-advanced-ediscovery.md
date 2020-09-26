---
title: Nahe Duplicate Detection-eDiscovery
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
description: Verwenden Sie die nahezu doppelte Erkennung zum Gruppieren von textähnlichen Dokumenten bei der Analyse von Falldaten in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286021"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="a887f-103">Nahe doppelte Erkennung in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a887f-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="a887f-104">Betrachten Sie eine Reihe von Dokumenten, die überprüft werden sollen, in denen eine Teilmenge auf derselben Vorlage basiert und meist die gleiche Standardsprache mit einigen Unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a887f-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="a887f-105">Wenn ein Prüfer diese Teilmenge identifizieren konnte, überprüfen Sie eine von Ihnen gründlich, und überprüfen Sie die Unterschiede für den Rest, würden Sie keine eindeutigen Informationen verpasst haben, wobei nur ein Bruchteil der Zeit, die Sie zum Lesen aller Dokument Deckung zur Deckung genommen hätte.</span><span class="sxs-lookup"><span data-stu-id="a887f-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="a887f-106">Bei der Erkennung von Quasiduplikaten werden textuell ähnliche Dokumente gruppiert, um den Überprüfungsvorgang effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="a887f-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="a887f-107">Wie funktioniert das?</span><span class="sxs-lookup"><span data-stu-id="a887f-107">How does it work?</span></span>

<span data-ttu-id="a887f-108">Bei Ausführung der Erkennung von Quasiduplikaten analysiert das System jedes Dokument mit Text.</span><span class="sxs-lookup"><span data-stu-id="a887f-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="a887f-109">Anschließend werden alle Dokumente miteinander verglichen, um zu bestimmen, ob ihre Ähnlichkeit über dem Schwellenwert liegt.</span><span class="sxs-lookup"><span data-stu-id="a887f-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="a887f-110">Ist dies der Fall, werden die Dokumente gruppiert.</span><span class="sxs-lookup"><span data-stu-id="a887f-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="a887f-111">Nachdem alle Dokumente verglichen und gruppiert wurden, wird ein Dokument aus jeder Gruppe als „Pivot“ markiert. Wenn Sie Ihre Dokumente überprüfen, können Sie zuerst das Pivot-Dokument und anschließend die restlichen Dokumente im gleichen Quasiduplikat-Satz überprüfen und sich dabei auf den Unterschied zwischen dem Pivot und dem Dokument konzentrieren, das sich in der Überprüfung befindet.</span><span class="sxs-lookup"><span data-stu-id="a887f-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
