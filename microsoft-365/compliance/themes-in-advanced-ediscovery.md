---
title: Designs
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082549"
---
# <a name="themes"></a><span data-ttu-id="b87ef-102">Designs</span><span class="sxs-lookup"><span data-stu-id="b87ef-102">Themes</span></span>
<span data-ttu-id="b87ef-103">Wie schreibt eine Person ein Dokument?</span><span class="sxs-lookup"><span data-stu-id="b87ef-103">How does a person write a document?</span></span> <span data-ttu-id="b87ef-104">Sie beginnen im Allgemeinen mit einem oder mehreren Ideen, die Sie im Dokument vermitteln möchten, und verfassen sich mit Wörtern, die mit den Ideen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b87ef-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="b87ef-105">Je häufiger eine Idee ist, desto häufiger sind die Wörter, die mit dieser Idee verwandt sind, eher.</span><span class="sxs-lookup"><span data-stu-id="b87ef-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="b87ef-106">Dies informiert darüber, wie Personen Dokumente auch nutzen; Das wichtigste beim Lesen eines Dokuments sind die Ideen, die das Dokument zu vermitteln versucht, und welche Ideen angezeigt werden und welche Beziehungen zwischen den Ideen bestehen.</span><span class="sxs-lookup"><span data-stu-id="b87ef-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="b87ef-107">Dies kann erweitert werden, um zu erfahren, wie eine Person eine Reihe von Dokumenten verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="b87ef-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="b87ef-108">Sie möchten sehen, welche Ideen in den Sets vorhanden sind und welche Dokumente über diese Ideen sprechen.</span><span class="sxs-lookup"><span data-stu-id="b87ef-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="b87ef-109">Wenn Sie ein bestimmtes Dokument finden, das interessant ist, möchten Sie auch Dokumente sehen, in denen ähnliche Ideen erörtert werden.</span><span class="sxs-lookup"><span data-stu-id="b87ef-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="b87ef-110">Designs-Modul versucht zu imitieren, wie Menschen Grund zu Dokumenten, durch die Analyse der "Designs", die in einer Überprüfung festgelegt und Zuweisen von Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="b87ef-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a review set and assigning them to documents.</span></span> <span data-ttu-id="b87ef-111">Designs geht einen Schritt weiter und identifiziert pro Dokument das "dominante Design"; dh das Design, das am häufigsten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b87ef-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="b87ef-112">Wie funktioniert Designs?</span><span class="sxs-lookup"><span data-stu-id="b87ef-112">How does Themes work?</span></span>
<span data-ttu-id="b87ef-113">Designs analysiert Dokumente mit Text in einer Überprüfungsgruppe, um allgemeine Designs zu analysieren, die in den Dokumenten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b87ef-113">Themes analyzes documents with text in a review set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="b87ef-114">Anschließend werden diese Designs den Dokumenten zugewiesen, in denen Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b87ef-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="b87ef-115">Sie beschriftet außerdem jeweils Wörter, die in den Dokumenten verwendet werden, die für das Design repräsentativ sind.</span><span class="sxs-lookup"><span data-stu-id="b87ef-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="b87ef-116">Da es sich bei einem Dokument um mehr als einen Betreff handeln kann, sind dem Dokument in vielen Fällen mehr als ein Design zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b87ef-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="b87ef-117">Das Design, das in einem Dokument am deutlichsten erscheint, wird als dominierendes Design festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b87ef-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>