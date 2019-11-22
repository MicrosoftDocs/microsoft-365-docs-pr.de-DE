---
title: Abfragen der Daten in einem Prüfdateisatz
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
ms.openlocfilehash: 8eadfbeb1a78edd12129c97dc3144a45c5c409cf
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191270"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="71e74-102">Abfragen der Daten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="71e74-102">Query the data in a review set</span></span>

<span data-ttu-id="71e74-103">In den meisten Fällen ist es hilfreich, die Daten in einer Überprüfungsgruppe tiefer zu analysieren und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="71e74-103">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="71e74-104">Mithilfe von Abfragen in einem Überprüfungs Satz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die die Kriterien ihrer Überprüfung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="71e74-104">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="71e74-105">Erstellen und Durchführen einer Abfrage in einem Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="71e74-105">Creating and running a query in a review set</span></span>

<span data-ttu-id="71e74-106">Wenn Sie eine Abfrage für die Dokumente in einem Überprüfungs Satzes erstellen und ausführen möchten, klicken Sie in der Überprüfungsgruppe auf **neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="71e74-106">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="71e74-107">Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, klicken Sie auf **Speichern** , um die Abfrage zu speichern und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71e74-107">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="71e74-108">Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, klicken Sie auf eine gespeicherte Abfrage.</span><span class="sxs-lookup"><span data-stu-id="71e74-108">To run a query that has been previously saved, click a saved query.</span></span> 

![Überprüfen von Mengen Abfragen](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="71e74-110">Erstellen einer Überprüfungs Sätze-Abfrage</span><span class="sxs-lookup"><span data-stu-id="71e74-110">Building a review set query</span></span>

<span data-ttu-id="71e74-111">Sie können eine Abfrage erstellen, indem Sie eine Kombination aus Konditions Karten und Abfragesprache in der Konditions Karte Stichwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="71e74-111">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="71e74-112">Sie können auch Bedingungs Karten zusammen als Block (eine *Bedingungsgruppe*) gruppieren, um eine komplexere Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71e74-112">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="71e74-113">Eine Liste und eine Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="71e74-113">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="71e74-114">Konditions Karten</span><span class="sxs-lookup"><span data-stu-id="71e74-114">Condition cards</span></span>

<span data-ttu-id="71e74-115">Jedes durchsuchbare Feld in einem Überprüfungs-Datensatz verfügt über eine entsprechende Bedingungs Karte, die Sie zum Erstellen Ihrer Abfrage verwenden können.</span><span class="sxs-lookup"><span data-stu-id="71e74-115">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="71e74-116">Es gibt mehrere Arten von Konditions Karten:</span><span class="sxs-lookup"><span data-stu-id="71e74-116">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="71e74-117">FREETEXT: eine FREETEXT-Bedingungs Karte wird für Textfelder wie Betreff verwendet.</span><span class="sxs-lookup"><span data-stu-id="71e74-117">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="71e74-118">Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="71e74-118">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="71e74-119">Datum: eine Datums-Konditions Karte wird für Datumsfelder wie Datum der letzten Änderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="71e74-119">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="71e74-120">Suchoptionen: eine Bedingungs Karte für Suchoptionen enthält eine Liste der möglichen Werte für das jeweilige Feld im Überprüfungs.</span><span class="sxs-lookup"><span data-stu-id="71e74-120">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="71e74-121">Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="71e74-121">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="71e74-122">Stichwort: eine Keyword-Bedingungs Karte ist eine bestimmte Instanz der FREETEXT-Konditions Karte, mit der Sie nach Begriffen suchen oder KQL-ähnliche Abfragesprache in verwenden können.</span><span class="sxs-lookup"><span data-stu-id="71e74-122">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="71e74-123">Weitere Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="71e74-123">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="71e74-124">Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="71e74-124">Query language</span></span>

<span data-ttu-id="71e74-125">Zusätzlich zu den Konditions Karten können Sie eine KQL-ähnliche Abfragesprache in der Stichwörter Karte verwenden, um Ihre Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71e74-125">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="71e74-126">Die Abfragesprache für Review-Mengen Abfragen unterstützt Standard boolesche Operatoren wie and, or, Not und Near (n).</span><span class="sxs-lookup"><span data-stu-id="71e74-126">The query language for review set queries supports standard Boolean operators, such as AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="71e74-127">Außerdem wird ein Platzhalter mit einem einzelnen Zeichen (?) und ein mehr stelliger Platzhalter (\*) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="71e74-127">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="71e74-128">Verwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="71e74-128">Using filters</span></span>

<span data-ttu-id="71e74-129">Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtersätzen für eine Überprüfungs Satz Abfrage schnell zusätzliche Bedingungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="71e74-129">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="71e74-130">Auf diese Weise können Sie die Ergebnisse, die von einer Abfrage mit Überprüfungs Sätzen angezeigt werden, weiter verfeinern.</span><span class="sxs-lookup"><span data-stu-id="71e74-130">This helps you further refine the results displayed by a review set query.</span></span> 

![Überprüfen von Filtersätzen](media/AeDReviewSetFilters.png)

<span data-ttu-id="71e74-132">Filter unterscheiden sich in zwei wichtigen Punkten von Abfragen:</span><span class="sxs-lookup"><span data-stu-id="71e74-132">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="71e74-133">Filter sind vorübergehend.</span><span class="sxs-lookup"><span data-stu-id="71e74-133">Filters are transient.</span></span> <span data-ttu-id="71e74-134">Sie bleiben außerhalb der vorhandenen Sitzung bestehen.</span><span class="sxs-lookup"><span data-stu-id="71e74-134">They don't persist beyond the existing session.</span></span> <span data-ttu-id="71e74-135">Mit anderen Worten: Sie können einen Filter nicht speichern.</span><span class="sxs-lookup"><span data-stu-id="71e74-135">In other words, you can't save a filter.</span></span> <span data-ttu-id="71e74-136">Abfragen werden in der Überprüfungsgruppe gespeichert und greifen beim Öffnen des Überprüfungs Satzes auf diese zu.</span><span class="sxs-lookup"><span data-stu-id="71e74-136">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="71e74-137">Filter sind immer additiv.</span><span class="sxs-lookup"><span data-stu-id="71e74-137">Filters are always additive.</span></span> <span data-ttu-id="71e74-138">Filter werden zusätzlich zur aktuellen Überprüfungs Satz Abfrage angewendet.</span><span class="sxs-lookup"><span data-stu-id="71e74-138">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="71e74-139">Durch das Anwenden einer anderen Abfrage werden die Ergebnisse ersetzt, die von der aktuellen Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="71e74-139">Applying a different query will replace the results returned by the current query.</span></span>
