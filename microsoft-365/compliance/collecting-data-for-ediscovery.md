---
title: Sammeln von Daten für einen Fall in Advanced eDiscovery
ms.author: esclee
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
ms.openlocfilehash: 4e0bc71071ecfe20a2141e72b1146e9688618faf
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633604"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="183b7-102">Sammeln von Daten für einen Fall in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="183b7-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="183b7-103">Nachdem Sie Verwalter und Datenquellen identifiziert haben, die für Ihren Fall von Interesse sind, müssen Sie die Dokumente identifizieren, in die Sie eintauchen möchten.</span><span class="sxs-lookup"><span data-stu-id="183b7-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="183b7-104">Sie können das Such Tool in Advanced eDiscovery verwenden, um diese von Freiheits-und nicht-Freiheits belassenen Speicherorten in Office 365 zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="183b7-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="183b7-105">Nachdem Sie eine Suche ausgeführt haben, können Sie Statistiken zu den abgerufenen Elementen anzeigen, beispielsweise die Speicherorte mit den meisten Elementen, die mit der Suchabfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="183b7-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="183b7-106">Sie können auch eine Vorschau einer Teilmenge der Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="183b7-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="183b7-107">Wenn Sie die Gruppe von Dokumenten identifiziert haben, die Sie weiter untersuchen möchten, können Sie die Suchergebnisse zu einem Überprüfungs Sätze hinzufügen, um Sie zu sammeln und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="183b7-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="183b7-108">Erstellen einer Suche</span><span class="sxs-lookup"><span data-stu-id="183b7-108">Create a search</span></span>

<span data-ttu-id="183b7-109">Wenn Sie auf der Registerkarte **Suchen** die Option **neue Suche** auswählen, wird ein Assistent gestartet, der Sie durch das Erstellen einer Suche führt.</span><span class="sxs-lookup"><span data-stu-id="183b7-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="183b7-110">Ausführliche Informationen zum Erstellen einer Suche finden Sie unter [Erstellen einer Suche zum Erfassen von Daten](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="183b7-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="183b7-111">Nachdem eine Suche erstellt wurde, wird eine Flyout-Seite mit Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="183b7-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="183b7-112">Die Schaltflächen **Statistik** und **Vorschau** sind anfänglich nicht verfügbar, da die Suche noch nicht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="183b7-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="183b7-113">Sie können den Fortschritt der Suche auf der Registerkarte **Suchen** verfolgen.</span><span class="sxs-lookup"><span data-stu-id="183b7-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="183b7-114">Anzeigen von Suchergebnissen und Statistiken</span><span class="sxs-lookup"><span data-stu-id="183b7-114">View search results and statistics</span></span>

<span data-ttu-id="183b7-115">Es gibt zwei Komponenten einer Inhaltssuche: Statistik (Schätzungen) und Vorschau.</span><span class="sxs-lookup"><span data-stu-id="183b7-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="183b7-116">Nachdem jede dieser Komponenten abgeschlossen ist, wird der Status angezeigt, der in den entsprechenden Spalten auf der Registerkarte **Suchvorgänge** von über **mittelte** in **in Bearbeitung** geändert in **abgeschlossen**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="183b7-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="183b7-117">Wenn die Such Schätzung abgeschlossen ist, wählen Sie die Suche aus, um die Flyout-Seite anzuzeigen, in der einige allgemeine Statistiken zu den Ergebnissen der Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="183b7-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="183b7-118">Zu diesem Zeitpunkt ist die Schaltfläche **Statistik** aktiv.</span><span class="sxs-lookup"><span data-stu-id="183b7-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="183b7-119">Sie können ihn auswählen, um Suchstatistiken anzuzeigen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="183b7-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="183b7-120">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="183b7-120">Summary</span></span>
- <span data-ttu-id="183b7-121">Top-Standorte</span><span class="sxs-lookup"><span data-stu-id="183b7-121">Top locations</span></span>
- <span data-ttu-id="183b7-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="183b7-122">Queries</span></span>

<span data-ttu-id="183b7-123">Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistiken](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="183b7-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="183b7-124">Sobald die Vorschau abgeschlossen ist, wird die Schaltfläche **Vorschau** aktiv.</span><span class="sxs-lookup"><span data-stu-id="183b7-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="183b7-125">Wählen Sie diese Option aus, um eine ausgewählte Teilmenge der Ergebnisse in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="183b7-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="183b7-126">Hinzufügen von Suchergebnissen zu einer Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="183b7-126">Adding search results to a review set</span></span>

<span data-ttu-id="183b7-127">Wenn Sie bereit sind, die gesamten Ergebnisse einer Suche zu sammeln und zu verarbeiten, können Sie dies tun, indem Sie es zu einem Überprüfungs Satzes hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="183b7-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="183b7-128">Ausführliche Informationen finden Sie unter [Hinzufügen von Daten zu einem Überprüfungs Sätze](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="183b7-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>
