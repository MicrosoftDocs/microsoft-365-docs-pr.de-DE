---
title: Abfragen der Daten in einem Prüfdateisatz
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
description: In diesem Artikel erfahren Sie, wie Sie eine Abfrage in einem Überprüfungspaket erstellen und ausführen, um Daten für eine effizientere Überprüfung in einem erweiterten eDiscovery-Fall zu organisieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 871630af4b8b19e5fad1a062129782e36b9706f5
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527435"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="ca7cb-103">Abfragen der Daten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="ca7cb-103">Query the data in a review set</span></span>

<span data-ttu-id="ca7cb-104">In den meisten Fällen ist es hilfreich, die Daten in einer Überprüfungsgruppe tiefer zu analysieren und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="ca7cb-105">Mithilfe von Abfragen in einem Überprüfungs Satz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die die Kriterien ihrer Überprüfung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="ca7cb-106">Erstellen und Durchführen einer Abfrage in einem Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="ca7cb-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="ca7cb-107">Klicken Sie zum Erstellen und Ausführen einer Abfrage für die Dokumente in einem Prüfdateisatz auf **Neue Abfrage** im Prüfdateisatz.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-107">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="ca7cb-108">Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, klicken Sie auf **Speichern** , um die Abfrage zu speichern und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-108">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="ca7cb-109">Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, klicken Sie auf eine gespeicherte Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-109">To run a query that has been previously saved, click a saved query.</span></span>

![Überprüfen von Mengen Abfragen](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="ca7cb-111">Erstellen einer Überprüfungs Sätze-Abfrage</span><span class="sxs-lookup"><span data-stu-id="ca7cb-111">Building a review set query</span></span>

<span data-ttu-id="ca7cb-112">Sie können eine Abfrage erstellen, indem Sie eine Kombination aus Konditions Karten und Abfragesprache in der Konditions Karte Stichwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-112">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="ca7cb-113">Sie können auch Bedingungs Karten zusammen als Block (eine *Bedingungsgruppe*) gruppieren, um eine komplexere Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-113">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="ca7cb-114">Eine Liste und Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Dokumentmetadatenfeldern in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ca7cb-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="ca7cb-115">Konditions Karten</span><span class="sxs-lookup"><span data-stu-id="ca7cb-115">Condition cards</span></span>

<span data-ttu-id="ca7cb-116">Jedes durchsuchbare Feld in einem Überprüfungs-Datensatz verfügt über eine entsprechende Bedingungs Karte, die Sie zum Erstellen Ihrer Abfrage verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-116">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="ca7cb-117">Es gibt mehrere Arten von Konditions Karten:</span><span class="sxs-lookup"><span data-stu-id="ca7cb-117">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="ca7cb-118">FREETEXT: eine FREETEXT-Bedingungs Karte wird für Textfelder wie Betreff verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-118">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="ca7cb-119">Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="ca7cb-120">Datum: eine Datums-Konditions Karte wird für Datumsfelder wie Datum der letzten Änderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-120">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="ca7cb-121">Suchoptionen: eine Bedingungs Karte für Suchoptionen enthält eine Liste der möglichen Werte für das jeweilige Feld im Überprüfungs.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-121">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="ca7cb-122">Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="ca7cb-123">Stichwort: eine Keyword-Bedingungs Karte ist eine bestimmte Instanz der FREETEXT-Konditions Karte, mit der Sie nach Begriffen suchen oder KQL-ähnliche Abfragesprache in verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-123">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="ca7cb-124">Weitere Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="ca7cb-125">Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="ca7cb-125">Query language</span></span>

<span data-ttu-id="ca7cb-126">Zusätzlich zu den Konditions Karten können Sie eine KQL-ähnliche Abfragesprache in der Stichwörter Karte verwenden, um Ihre Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-126">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="ca7cb-127">Die Abfragesprache für Review-Mengen Abfragen unterstützt Standard boolesche Operatoren wie **and**, **or**, **Not**und **near**.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="ca7cb-128">Außerdem wird ein Platzhalter mit einem einzelnen Zeichen (?) und ein mehr stelliger Platzhalter (\*) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="ca7cb-129">Verwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="ca7cb-129">Using filters</span></span>

<span data-ttu-id="ca7cb-130">Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtersätzen für eine Überprüfungs Satz Abfrage schnell zusätzliche Bedingungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="ca7cb-131">Auf diese Weise können Sie die durch eine Prüfdateisatz-Abfrage angezeigten Ergebnisse weiter verfeinern.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-131">This helps you further refine the results displayed by a review set query.</span></span>

![Überprüfen von Filtersätzen](../media/AeDReviewSetFilters.png)

<span data-ttu-id="ca7cb-133">Filter unterscheiden sich in zwei wichtigen Punkten von Abfragen:</span><span class="sxs-lookup"><span data-stu-id="ca7cb-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="ca7cb-134">Filter sind vorübergehend.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-134">Filters are transient.</span></span> <span data-ttu-id="ca7cb-135">Sie bleiben außerhalb der vorhandenen Sitzung bestehen.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="ca7cb-136">Mit anderen Worten: Sie können einen Filter nicht speichern.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="ca7cb-137">Abfragen werden in der Überprüfungsgruppe gespeichert und greifen beim Öffnen des Überprüfungs Satzes auf diese zu.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="ca7cb-138">Filter sind immer additiv.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-138">Filters are always additive.</span></span> <span data-ttu-id="ca7cb-139">Filter werden zusätzlich zur aktuellen Prüfdateisatz-Abfrage angewendet.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="ca7cb-140">Durch das Anwenden einer anderen Abfrage werden die von der aktuellen Abfrage zurückgegebenen Ergebnisse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ca7cb-140">Applying a different query will replace the results returned by the current query.</span></span>
