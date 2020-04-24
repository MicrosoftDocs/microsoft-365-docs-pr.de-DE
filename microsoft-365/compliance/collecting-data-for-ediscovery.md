---
title: Sammeln von Daten für einen Fall in Advanced eDiscovery
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 462c58f8531265026b34fe3d8484736aefa4c5fa
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799938"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="ba89c-102">Sammeln von Daten für einen Fall in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ba89c-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="ba89c-103">Nachdem Sie Verwalter und Datenquellen identifiziert haben, die für Ihren Fall von Interesse sind, müssen Sie die Dokumente identifizieren, in die Sie eintauchen möchten.</span><span class="sxs-lookup"><span data-stu-id="ba89c-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="ba89c-104">Sie können das Such Tool in Advanced eDiscovery verwenden, um relevante Dokumente aus Freiheits-und nicht-Freiheits Speicherorten in Microsoft 365 zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ba89c-104">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="ba89c-105">Nachdem Sie eine Suche ausgeführt haben, können Sie Statistiken zu den abgerufenen Elementen anzeigen, beispielsweise die Speicherorte mit den meisten Elementen, die mit der Suchabfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ba89c-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="ba89c-106">Sie können auch eine Vorschau einer Teilmenge der Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ba89c-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="ba89c-107">Wenn Sie die Gruppe von Dokumenten identifiziert haben, die Sie weiter untersuchen möchten, können Sie die Suchergebnisse zu einem Überprüfungs Sätze hinzufügen, um Sie zu sammeln und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ba89c-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="ba89c-108">Erstellen einer Suche</span><span class="sxs-lookup"><span data-stu-id="ba89c-108">Create a search</span></span>

<span data-ttu-id="ba89c-109">Wenn Sie auf der Registerkarte **Suchen** die Option **neue Suche** auswählen, wird ein Assistent gestartet, der Sie durch das Erstellen einer Suche führt.</span><span class="sxs-lookup"><span data-stu-id="ba89c-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="ba89c-110">Ausführliche Informationen zum Erstellen einer Suche finden Sie unter [Erstellen einer Suche zum Erfassen von Daten](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="ba89c-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="ba89c-111">Nachdem eine Suche erstellt wurde, wird eine Flyout-Seite mit Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba89c-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="ba89c-112">Die Schaltflächen **Statistik** und **Vorschau** sind anfänglich nicht verfügbar, da die Suche noch nicht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba89c-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="ba89c-113">Sie können den Fortschritt der Suche auf der Registerkarte **Suchen** verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ba89c-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="ba89c-114">Anzeigen von Suchergebnissen und Statistiken</span><span class="sxs-lookup"><span data-stu-id="ba89c-114">View search results and statistics</span></span>

<span data-ttu-id="ba89c-115">Es gibt zwei Komponenten einer Inhaltssuche: Statistik (Schätzungen) und Vorschau.</span><span class="sxs-lookup"><span data-stu-id="ba89c-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="ba89c-116">Nachdem jede dieser Komponenten abgeschlossen ist, wird der Status angezeigt, der in den entsprechenden Spalten auf der Registerkarte **Suchvorgänge** von über **mittelte** in **in Bearbeitung** geändert in **abgeschlossen**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ba89c-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="ba89c-117">Wenn die Such Schätzung abgeschlossen ist, wählen Sie die Suche aus, um die Flyout-Seite anzuzeigen, in der einige allgemeine Statistiken zu den Ergebnissen der Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba89c-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="ba89c-118">Zu diesem Zeitpunkt ist die Schaltfläche **Statistik** aktiv.</span><span class="sxs-lookup"><span data-stu-id="ba89c-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="ba89c-119">Sie können ihn auswählen, um Suchstatistiken anzuzeigen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="ba89c-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="ba89c-120">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="ba89c-120">Summary</span></span>
- <span data-ttu-id="ba89c-121">Top-Standorte</span><span class="sxs-lookup"><span data-stu-id="ba89c-121">Top locations</span></span>
- <span data-ttu-id="ba89c-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="ba89c-122">Queries</span></span>

<span data-ttu-id="ba89c-123">Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistiken](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="ba89c-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="ba89c-124">Sobald die Vorschau abgeschlossen ist, wird die Schaltfläche **Vorschau** aktiv.</span><span class="sxs-lookup"><span data-stu-id="ba89c-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="ba89c-125">Wählen Sie diese Option aus, um eine ausgewählte Teilmenge der Ergebnisse in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ba89c-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="ba89c-126">Hinzufügen von Suchergebnissen zu einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="ba89c-126">Add search results to a review set</span></span>

<span data-ttu-id="ba89c-127">Wenn Sie bereit sind, die gesamten Ergebnisse einer Suche zu sammeln und zu verarbeiten, können Sie dies tun, indem Sie es zu einem Überprüfungs Satzes hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba89c-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="ba89c-128">Ausführliche Informationen finden Sie unter [Hinzufügen von Daten zu einem Überprüfungs Sätze](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="ba89c-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="ba89c-129">Hinzufügen von nicht-Microsoft 365-Daten zu einem Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="ba89c-129">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="ba89c-130">Im Rahmen des Sammlungsprozesses für einen Fall können Sie auch nicht Office 365 Daten zu einer Überprüfungsgruppe hinzufügen und überprüfen und zusammen mit den Office 365 Daten analysieren, die Sie mithilfe des Such Tools gesammelt haben.</span><span class="sxs-lookup"><span data-stu-id="ba89c-130">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="ba89c-131">Wenn Sie nicht-Office 365 hinzufügen, müssen Sie ihn einer bestimmten Depotbank in dem Fall zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ba89c-131">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="ba89c-132">Weitere Informationen finden Sie unter [Laden von nicht-Microsoft 365-Daten in einen Überprüfungs Satzes](load-non-Office-365-data-into-a-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="ba89c-132">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
