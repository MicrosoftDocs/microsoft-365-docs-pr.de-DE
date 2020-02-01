---
title: Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicher Fehlers
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie die Schaltfläche Wiederholen zum Auflösen von Inhalts suchen mit fehlerhaften Inhaltsverzeichnissen.
ms.openlocfilehash: ce88749a887fea57e977e210de1eda40268cb832
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601622"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="0c1ec-103">Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicher Fehlers</span><span class="sxs-lookup"><span data-stu-id="0c1ec-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="0c1ec-104">Wenn Sie die Inhaltssuche im Security and Compliance Center verwenden, um eine große Anzahl von Postfächern zu durchsuchen, erhalten Sie möglicherweise ähnliche Suchfehler wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the following:</span></span>

```text
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="0c1ec-105">Diese Fehler (mit Fehlercodes von CS001-002, CS003-002, CS008-009, CS012-002 und anderen Fehlern im Format CS0XX-0xx) deuten darauf hin, dass die Inhaltssuche keine bestimmten inhaltsspeicherorte durchsucht; in diesem Beispiel wurden zwei Postfächer nicht durchsucht.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="0c1ec-106">Diese Fehler werden auf der Dropdown Seite Statusdetails der Inhaltssuche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="0c1ec-107">Ursache für Fehler bei Inhaltsverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="0c1ec-107">Cause of content location errors</span></span>

<span data-ttu-id="0c1ec-108">Beim Durchsuchen einer großen Anzahl von Postfächern wird die Suche auf Tausende von Servern in einem Microsoft-Rechenzentrum verteilt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="0c1ec-109">Zu einem bestimmten Zeitpunkt können bestimmte Server im Neustart Zustand sein oder bei einem Failover auf redundante Kopien.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="0c1ec-110">In beiden Fällen wird die Anforderung der Inhaltssuche zum Abrufen von Daten Timeout.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-110">In either of these cases, the Content Search's request to retrieve data will timeout.</span></span> <span data-ttu-id="0c1ec-111">Im vorherigen Beispiel waren die Fehler für die Postfächer, bei denen ein Fehler aufgetreten ist, das Ergebnis der Such Zeitüberschreitung.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-111">In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="0c1ec-112">Beheben von Inhaltsspeicherort Fehlern</span><span class="sxs-lookup"><span data-stu-id="0c1ec-112">Resolving content location errors</span></span>

<span data-ttu-id="0c1ec-113">Das Neustarten der Suche führt häufig zu ähnlichen Fehlern auf unterschiedlichen Servern.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-113">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="0c1ec-114">Anstatt die Suche neu zu starten, klicken Sie auf die Schaltfläche wieder **holen** , die oben auf der Suchergebnisseite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-114">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Klicken Sie auf die Schaltfläche wiederholen, um Fehler des Inhaltsspeichers zu beheben](media/retrycontentsearch3.png)

<span data-ttu-id="0c1ec-116">Dies führt dazu, dass die Suche nur für die nicht erfolgreichen Postfächer erneut versucht wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-116">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="0c1ec-117">Wenn Sie die Suche wiederholen, werden die anderen Ergebnisse, die erfolgreich zurückgegeben wurden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-117">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="0c1ec-118">Tipps zum Vermeiden von Inhaltsspeicherort Fehlern</span><span class="sxs-lookup"><span data-stu-id="0c1ec-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="0c1ec-119">Im folgenden finden Sie einige Ursachen für Fehler bei der Inhalts Lokalisierung und einige Tipps, die Ihnen beim Durchsuchen einer großen Anzahl von Postfächern helfen sollen, dies zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="0c1ec-120">Das durchsuchte Postfach ist aufgrund von Benutzeraktivitäten möglicherweise ausgelastet.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-120">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="0c1ec-121">In diesem Fall kann sich der Suchdienst selbst Drosseln, um zu verhindern, dass das Postfach nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-121">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="0c1ec-122">Um dies zu vermeiden, versuchen Sie, Suchvorgänge außerhalb der Geschäftszeiten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-122">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="0c1ec-123">Die Suchabfrage Ruft möglicherweise zu viel Inhalt aus dem Postfach ab.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-123">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="0c1ec-124">Versuchen Sie nach Möglichkeit, den Suchbereich mithilfe von Schlüsselwörtern, Datumsbereichen und Suchbedingungen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-124">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="0c1ec-125">Zu viele Stichwörter oder Keyword-Phrasen beim Erstellen einer Suchabfrage mithilfe der [Liste Stichwörter](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span><span class="sxs-lookup"><span data-stu-id="0c1ec-125">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="0c1ec-126">Wenn Sie eine Suchabfrage ausführen, die die Liste Stichwörter verwendet, führt der Dienst im Wesentlichen eine separate Suche für jede Zeile in der Stichwortliste aus, sodass Statistiken generiert werden können.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-126">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="0c1ec-127">Wenn Sie die Liste Stichwörter in Suchabfragen verwenden, minimieren Sie die Anzahl der Zeilen in der Stichwortliste, oder Teilen Sie die Zahlen Schlüsselwörter in kleinere Listen auf, und erstellen Sie eine andere Suche für jede Stichwortliste.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-127">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0c1ec-128">Um Probleme aufgrund großer Stichwortlisten zu verringern, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="0c1ec-129">Zu viele Suchvorgänge werden gleichzeitig für dasselbe Postfach ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-129">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="0c1ec-130">Versuchen Sie nach Möglichkeit, eine Suche auf einem Postfach gleichzeitig auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-130">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="0c1ec-131">Durchsuchen zu vieler Postfächer in einer einzigen Suche.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-131">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="0c1ec-132">Die Wahrscheinlichkeit von Inhaltsspeicherort Fehlern steigt beim Durchsuchen einer sehr großen Anzahl von Postfächern.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-132">The probability of content location errors increases when searching a very large number of mailboxes.</span></span> <span data-ttu-id="0c1ec-133">Versuchen Sie nach Möglichkeit, mehrere Suchvorgänge auszuführen, damit jede Suche eine Teilmenge von Postfächern in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-133">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="0c1ec-134">Die erforderliche Wartung wird für das Postfach ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-134">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="0c1ec-135">Obwohl diese Ursache wahrscheinlich selten auftritt, warten Sie eine Weile, nachdem Sie den Inhaltsspeicherort Fehler erhalten haben, und wiederholen Sie die Suche.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-135">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
