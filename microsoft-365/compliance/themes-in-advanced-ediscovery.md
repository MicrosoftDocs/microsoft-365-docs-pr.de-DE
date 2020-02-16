---
title: Designs
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
description: ''
ms.openlocfilehash: 5de5a67c320a64d627baf204fe4b2ad051c9f452
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069542"
---
# <a name="themes"></a><span data-ttu-id="87518-102">Designs</span><span class="sxs-lookup"><span data-stu-id="87518-102">Themes</span></span>

<span data-ttu-id="87518-103">Wie schreibt eine Person ein Dokument?</span><span class="sxs-lookup"><span data-stu-id="87518-103">How does a person write a document?</span></span> <span data-ttu-id="87518-104">Sie beginnen im Allgemeinen mit einem oder mehreren Ideen, die Sie im Dokument vermitteln möchten, und verfassen sich mit Wörtern, die mit den Ideen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="87518-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="87518-105">Je häufiger eine Idee ist, desto häufiger sind die Wörter, die mit dieser Idee verwandt sind, eher.</span><span class="sxs-lookup"><span data-stu-id="87518-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="87518-106">Dies informiert darüber, wie auch Benutzer Dokumente konsumieren.</span><span class="sxs-lookup"><span data-stu-id="87518-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="87518-107">Das wichtigste beim Lesen eines Dokuments ist die Idee, die das Dokument zu vermitteln versucht, welche Ideen angezeigt werden und wie die Beziehungen zwischen den Ideen aussehen.</span><span class="sxs-lookup"><span data-stu-id="87518-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="87518-108">Dies kann erweitert werden, um zu erfahren, wie eine Person eine Reihe von Dokumenten verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="87518-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="87518-109">Sie möchten sehen, welche Ideen in den Sets vorhanden sind und welche Dokumente über diese Ideen sprechen.</span><span class="sxs-lookup"><span data-stu-id="87518-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="87518-110">Wenn Sie ein bestimmtes Dokument finden, das interessant ist, möchten Sie auch Dokumente sehen, in denen ähnliche Ideen erörtert werden.</span><span class="sxs-lookup"><span data-stu-id="87518-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="87518-111">Die Designs-Funktionalität in Advanced eDiscovery versucht zu imitieren, wie Menschen Grund zu Dokumenten sind, indem Sie die in einer Überprüfungsgruppe besprochenen *Designs* analysieren und einem Dokument in der Überprüfungsgruppe ein Design zuweisen.</span><span class="sxs-lookup"><span data-stu-id="87518-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="87518-112">In Advanced eDiscovery geht Designs einen Schritt weiter und identifiziert das *dominante Design* in jedem Dokument.</span><span class="sxs-lookup"><span data-stu-id="87518-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="87518-113">Das dominante Design ist diejenige, die am häufigsten in einem Dokument angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87518-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="87518-114">Wie funktioniert Designs?</span><span class="sxs-lookup"><span data-stu-id="87518-114">How does Themes work?</span></span>

<span data-ttu-id="87518-115">Die Designs-Funktion analysiert Dokumente mit Text in einem Überprüfungs Satzes, um allgemeine Designs zu analysieren, die in allen Dokumenten in der Überprüfungsgruppe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="87518-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="87518-116">Advanced eDiscovery ordnet diese Designs den Dokumenten zu, in denen Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="87518-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="87518-117">Außerdem werden die einzelnen Designs mit den in den Dokumenten verwendeten Wörtern versehen, die für das Design repräsentativ sind.</span><span class="sxs-lookup"><span data-stu-id="87518-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="87518-118">Da ein Dokument verschiedene Arten von Gegenstand enthalten kann, weist Advanced eDiscovery häufig mehreren Designs zu Dokumenten zu.</span><span class="sxs-lookup"><span data-stu-id="87518-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="87518-119">Das Design, das in einem Dokument am deutlichsten erscheint, wird als dominierendes Design festgelegt.</span><span class="sxs-lookup"><span data-stu-id="87518-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
