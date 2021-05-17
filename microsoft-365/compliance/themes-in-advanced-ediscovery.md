---
title: Designs - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie Designs in Advanced eDiscovery, um Überprüfungssätze zu organisieren, indem Sie das dominante Design in jedem Dokument finden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285531"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="a4f37-103">Designs in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a4f37-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="a4f37-104">Wie schreibt eine Person ein Dokument?</span><span class="sxs-lookup"><span data-stu-id="a4f37-104">How does a person write a document?</span></span> <span data-ttu-id="a4f37-105">Sie beginnen in der Regel mit einem oder mehreren Ideen, die sie im Dokument vermitteln möchten, und verfassen mithilfe von Wörtern, die an den Ideen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="a4f37-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="a4f37-106">Um so verbreiteter eine Idee ist, werden die Wörter, die mit dieser Idee in Zusammenhang stehen, in der Regel häufiger verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4f37-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="a4f37-107">Dies informiert darüber, wie Auch Personen Dokumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4f37-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="a4f37-108">Wichtig beim Lesen eines Dokuments sind die Ideen, die das Dokument vermitteln soll, welche Ideen wo angezeigt werden und was die Beziehungen zwischen den Ideen sind.</span><span class="sxs-lookup"><span data-stu-id="a4f37-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="a4f37-109">Dies kann auf die Art und Weise erweitert werden, wie eine Person eine Reihe von Dokumenten nutzen möchte.</span><span class="sxs-lookup"><span data-stu-id="a4f37-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="a4f37-110">Sie möchten sehen, welche Ideen in den Sätzen vorhanden sind und welche Dokumente über diese Ideen sprechen.</span><span class="sxs-lookup"><span data-stu-id="a4f37-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="a4f37-111">Wenn sie ein bestimmtes Dokument von Interesse finden, möchten sie auch Dokumente sehen können, in denen ähnliche Ideen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a4f37-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="a4f37-112">Die Themes-Funktionalität in Advanced eDiscovery versucht nachzuahmen, wie Menschen  über Dokumente nachdenklich sind, indem sie die Designs analysiert, die in einem Überprüfungssatz behandelt werden, und Dokumente im Überprüfungssatz ein Design zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a4f37-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="a4f37-113">Im Advanced eDiscovery Designs einen Schritt weiter und identifiziert das *dominante Design* in jedem Dokument.</span><span class="sxs-lookup"><span data-stu-id="a4f37-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="a4f37-114">Das dominante Design ist das Design, das am häufigsten in einem Dokument angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a4f37-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="a4f37-115">Wie funktioniert Designs?</span><span class="sxs-lookup"><span data-stu-id="a4f37-115">How does Themes work?</span></span>

<span data-ttu-id="a4f37-116">Die Funktion „Designs“ untersucht Dokumente mit Text in einem Prüfdateisatz auf gemeinsame Designs, die in allen Dokumenten des Prüfdateisatzes enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a4f37-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="a4f37-117">Advanced eDiscovery weist diese Designs den Dokumenten zu, in denen Sie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a4f37-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="a4f37-118">Außerdem wird jedes Design mit den in den Dokumenten verwendeten Wörtern gekennzeichnet, die für das Design repräsentativ sind.</span><span class="sxs-lookup"><span data-stu-id="a4f37-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="a4f37-119">Da ein Dokument verschiedene Typen von Designs enthalten kann, weist Advanced eDiscovery Dokumenten häufig mehrere Designs zu.</span><span class="sxs-lookup"><span data-stu-id="a4f37-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="a4f37-120">Das Design, das in einem Dokument am stärksten vertreten ist, wird als dominantes Design festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4f37-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
