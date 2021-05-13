---
title: Abfragen der Daten in einem Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, wie Sie eine Abfrage in einem Überprüfungssatz erstellen und ausführen, um Daten für eine effizientere Überprüfung in einem Advanced eDiscovery organisieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345800"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="56328-103">Abfragen der Daten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="56328-103">Query the data in a review set</span></span>

<span data-ttu-id="56328-104">In den meisten Fällen ist es hilfreich, sich tiefer in die Daten in einem Überprüfungssatz zu vertiefen und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="56328-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="56328-105">Die Verwendung von Abfragen in einem Überprüfungssatz hilft Ihnen, sich auf eine Teilmenge von Dokumenten zu konzentrieren, die die Kriterien Ihrer Überprüfung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="56328-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="56328-106">Erstellen und Ausführen einer Abfrage in einem Überprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="56328-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="56328-107">Wenn Sie eine Abfrage für die Dokumente in einem Überprüfungssatz erstellen und ausführen möchten, wählen Sie im Überprüfungssatz **Neue** Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="56328-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="56328-108">Nachdem Sie die Abfrage benennen und die Bedingungen definiert haben, wählen Sie **Speichern** aus, um die Abfrage zu speichern und ausführen.</span><span class="sxs-lookup"><span data-stu-id="56328-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="56328-109">Wählen Sie zum Ausführen einer zuvor gespeicherten Abfrage eine gespeicherte Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="56328-109">To run a query that has been previously saved, select a saved query.</span></span>

![Überprüfen von Satzabfragen](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="56328-111">Erstellen einer Überprüfungssatzabfrage</span><span class="sxs-lookup"><span data-stu-id="56328-111">Building a review set query</span></span>

<span data-ttu-id="56328-112">Sie können eine Abfrage mithilfe einer Kombination aus Schlüsselwörtern, Eigenschaften und Bedingungen in der Keywords-Bedingung erstellen.</span><span class="sxs-lookup"><span data-stu-id="56328-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="56328-113">Sie können Bedingungen auch als Block gruppieren (als *Bedingungsgruppe* bezeichnet), um eine komplexere Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56328-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="56328-114">Eine Liste und Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Dokumentmetadatenfeldern in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="56328-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="56328-115">Bedingungen</span><span class="sxs-lookup"><span data-stu-id="56328-115">Conditions</span></span>

<span data-ttu-id="56328-116">Jedes durchsuchbare Feld in einem Überprüfungssatz hat eine entsprechende Bedingung, die Sie zum Erstellen ihrer Abfrage verwenden können.</span><span class="sxs-lookup"><span data-stu-id="56328-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="56328-117">Es gibt mehrere Arten von Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="56328-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="56328-118">Freetext: Eine Freetextbedingung wird für Textfelder wie betreff verwendet.</span><span class="sxs-lookup"><span data-stu-id="56328-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="56328-119">Sie können mehrere Suchbegriffe auflisten, indem Sie sie durch ein Komma trennen.</span><span class="sxs-lookup"><span data-stu-id="56328-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="56328-120">Date: Eine Datumsbedingung wird für Datumsfelder wie das Datum der letzten Änderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="56328-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="56328-121">Suchoptionen: Eine Suchoptionenbedingung enthält eine Liste der möglichen Werte für das bestimmte Feld in Ihrem Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="56328-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="56328-122">Dies wird für Felder verwendet, z. B. Absender, bei denen eine begrenzte Anzahl möglicher Werte in Ihrem Überprüfungssatz enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="56328-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="56328-123">Schlüsselwort: Eine Schlüsselwortbedingung ist eine bestimmte Instanz von Freetextbedingung, die Sie zum Suchen nach Begriffen oder verwenden KQL- like query language in verwenden können.</span><span class="sxs-lookup"><span data-stu-id="56328-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="56328-124">Weitere Informationen finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="56328-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="56328-125">Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="56328-125">Query language</span></span>

<span data-ttu-id="56328-126">Zusätzlich zu den Bedingungen können Sie eine KQL- like query language in der Keywords-Bedingung verwenden, um Ihre Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56328-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="56328-127">Die Abfragesprache für Überprüfungssatzabfragen unterstützt standardmäßige boolesche Operatoren, z. B. **AND**, **OR**, **NOT** und **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="56328-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="56328-128">Es unterstützt auch einen einstelligen Platzhalter (?) und einen mehrstelligen Platzhalter (\*).</span><span class="sxs-lookup"><span data-stu-id="56328-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="56328-129">Filter</span><span class="sxs-lookup"><span data-stu-id="56328-129">Filters</span></span>

<span data-ttu-id="56328-130">Zusätzlich zu den Abfragen, die Sie speichern können, können Sie Mithilfe von Überprüfungssatzfiltern schnell zusätzliche Bedingungen auf eine Überprüfungssatzabfrage anwenden.</span><span class="sxs-lookup"><span data-stu-id="56328-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="56328-131">Mithilfe von Filtern können Sie die Ergebnisse, die von einer Überprüfungssatzabfrage angezeigt werden, weiter verfeinern.</span><span class="sxs-lookup"><span data-stu-id="56328-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Überprüfen von Satzfiltern](../media/AeDReviewSetFilters.png)

<span data-ttu-id="56328-133">Filter unterscheiden sich auf zwei wesentliche Weise von Abfragen:</span><span class="sxs-lookup"><span data-stu-id="56328-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="56328-134">Filter sind vorübergehend.</span><span class="sxs-lookup"><span data-stu-id="56328-134">Filters are transient.</span></span> <span data-ttu-id="56328-135">Sie bleiben nicht über die vorhandene Sitzung hinaus erhalten.</span><span class="sxs-lookup"><span data-stu-id="56328-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="56328-136">Anders ausgedrückt: Sie können keinen Filter speichern.</span><span class="sxs-lookup"><span data-stu-id="56328-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="56328-137">Abfragen werden im Überprüfungssatz gespeichert und greifen auf sie zu, wenn Sie den Überprüfungssatz öffnen.</span><span class="sxs-lookup"><span data-stu-id="56328-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="56328-138">Filter sind immer additiv.</span><span class="sxs-lookup"><span data-stu-id="56328-138">Filters are always additive.</span></span> <span data-ttu-id="56328-139">Filter werden zusätzlich zur aktuellen Prüfdateisatz-Abfrage angewendet.</span><span class="sxs-lookup"><span data-stu-id="56328-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="56328-140">Durch das Anwenden einer anderen Abfrage werden die von der aktuellen Abfrage zurückgegebenen Ergebnisse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56328-140">Applying a different query will replace the results returned by the current query.</span></span>
