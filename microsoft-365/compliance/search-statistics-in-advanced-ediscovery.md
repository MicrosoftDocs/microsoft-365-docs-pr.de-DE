---
title: Suchstatistik im Voraus eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Überprüfen Sie Ihre Suchergebnisse, indem Sie die Statistiken anzeigen, die generiert werden, nachdem Sie eine Sammlungs Suche in Advanced eDiscovery ausgeführt haben.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750776"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="de09a-103">Suchstatistik in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="de09a-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="de09a-104">Eine Möglichkeit, Ihre Suchergebnisse zu validieren, besteht darin, die Statistiken rund um Ihre Ergebnisse zu prüfen, um sicherzustellen, dass Sie Ihren Erwartungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="de09a-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="de09a-105">Wenn eine Suche abgeschlossen ist, werden allgemeine Statistiken im Flyout "Suchdetails" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="de09a-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="de09a-106">Anzahl und Umfang der von der Suche abgerufenen Elemente</span><span class="sxs-lookup"><span data-stu-id="de09a-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="de09a-107">Anzahl und Volumen der teilweise indizierten oder nicht indizierten Elemente, die in den Suchspeicherorten gefunden wurden</span><span class="sxs-lookup"><span data-stu-id="de09a-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="de09a-108">Anzahl der durchsuchten Postfächer und Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="de09a-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="de09a-109">Um detailliertere Statistiken anzuzeigen, klicken Sie im Flyout "Suchdetails" auf "Statistik".</span><span class="sxs-lookup"><span data-stu-id="de09a-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="de09a-110">Zusammenfassungsansicht</span><span class="sxs-lookup"><span data-stu-id="de09a-110">Summary view</span></span>

<span data-ttu-id="de09a-111">In der Zusammenfassungsansicht werden die Suchergebnisse nach Speicherorttyp (beispielsweise Exchange) aufgeschlüsselt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de09a-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="de09a-112">Für jeden Standorttyp können Sie Folgendes sehen:</span><span class="sxs-lookup"><span data-stu-id="de09a-112">For each location type, you can see:</span></span>

- <span data-ttu-id="de09a-113">Anzahl von Speicherorten mit Elementen, die mit den Suchbedingungen übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="de09a-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="de09a-114">Anzahl der Elemente aus diesen Speicherorten, die den Suchbedingungen entsprechen</span><span class="sxs-lookup"><span data-stu-id="de09a-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="de09a-115">Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="de09a-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="de09a-116">Ansicht "obere Standorte"</span><span class="sxs-lookup"><span data-stu-id="de09a-116">Top locations view</span></span>

<span data-ttu-id="de09a-117">In der Ansicht "Top Locations" werden die einzelnen Standorte mit den meisten Übereinstimmungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de09a-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="de09a-118">Für jeden Standort wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="de09a-118">For each location, you will see:</span></span>

- <span data-ttu-id="de09a-119">Speicherort Name (beispielsweise SharePoint-URL)</span><span class="sxs-lookup"><span data-stu-id="de09a-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="de09a-120">Speicherorttyp</span><span class="sxs-lookup"><span data-stu-id="de09a-120">Location type</span></span>

- <span data-ttu-id="de09a-121">Anzahl der Elemente, die mit den Suchbedingungen übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="de09a-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="de09a-122">Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="de09a-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="de09a-123">Ansicht "Abfragen"</span><span class="sxs-lookup"><span data-stu-id="de09a-123">Queries view</span></span>

<span data-ttu-id="de09a-124">Wenn Sie (c:s) Schlüsselwort-oder Stichwort Zeilen in Ihrer Abfrage verwendet haben, können Sie den aufschlüsseln der Abfrage in der Ansicht Abfragen pro Standorttyp sehen.</span><span class="sxs-lookup"><span data-stu-id="de09a-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="de09a-125">Für jeden Standorttyp werden die folgenden Aufgaben angezeigt:</span><span class="sxs-lookup"><span data-stu-id="de09a-125">For each location type, you will see:</span></span>

- <span data-ttu-id="de09a-126">Part: in dieser Spalte wird entweder das Wort "Primary" oder "Keyword" angegeben.</span><span class="sxs-lookup"><span data-stu-id="de09a-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="de09a-127">"Primary" bedeutet, dass die Zeile Statistiken für die gesamte Abfrage enthält, wobei "Stichwort" eine der Abfragekomponenten ist.</span><span class="sxs-lookup"><span data-stu-id="de09a-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="de09a-128">Query: die tatsächliche Abfragekomponente, auf die sich die Zeile bezieht.</span><span class="sxs-lookup"><span data-stu-id="de09a-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="de09a-129">Wenn Part "Primary" ist, handelt es sich um die gesamte Abfrage; Wenn Teil "Stichwort" war, wird eine der Abfragekomponenten hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de09a-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="de09a-130">Wenn Sie alle Inhalts-Postfächer durchsuchen (indem Sie keine Stichwörter angeben), lautet die tatsächliche Abfrage (Size >= 0), sodass alle Elemente zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="de09a-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="de09a-131">Wenn Sie SharePoint Online-und OneDrive für Unternehmen-Websites Durchsuchen, werden die beiden folgenden Komponenten hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="de09a-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="de09a-132">Not IsExternalContent: 1 – schließt alle Inhalte einer lokalen SharePoint-Organisation aus</span><span class="sxs-lookup"><span data-stu-id="de09a-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="de09a-133">Not isOneNotePage: 1 – schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate eines Dokuments handeln würde, das mit der Suchabfrage übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="de09a-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="de09a-134">Die Anzahl der Speicherorte, an denen Elemente mit den Suchbedingungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="de09a-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="de09a-135">Die Anzahl der Elemente aus diesen Speicherorten, die den Suchbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="de09a-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="de09a-136">Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="de09a-136">Total volume of items that matched the search conditions.</span></span>
