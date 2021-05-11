---
title: Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicherortfehlers
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Während einer Untersuchung können Sie die Schaltfläche Wiederholen verwenden, um Inhaltssuchen mit Fehlern beim Speicherort von Inhalten zu beheben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311820"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="d405d-103">Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicherortfehlers</span><span class="sxs-lookup"><span data-stu-id="d405d-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="d405d-104">Wenn Sie die Inhaltssuche im Security and Compliance Center zum Durchsuchen einer großen Anzahl von Postfächern verwenden, werden möglicherweise Suchfehler angezeigt, die dem Fehler ähneln:</span><span class="sxs-lookup"><span data-stu-id="d405d-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="d405d-105">Diese Fehler (mit Fehlercodes von CS001-002, CS003-002, CS008-009, CS012-002 und anderen Fehlern des Formulars CS0XX-0XX) deuten darauf hin, dass die Inhaltssuche bestimmte Inhaltsorte nicht durchsucht hat. In diesem Beispiel wurden zwei Postfächer nicht durchsucht.</span><span class="sxs-lookup"><span data-stu-id="d405d-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="d405d-106">Diese Fehler werden auf der Flyoutseite für Statusdetails der Inhaltssuche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d405d-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="d405d-107">Ursache von Fehlern beim Speicherort von Inhalten</span><span class="sxs-lookup"><span data-stu-id="d405d-107">Cause of content location errors</span></span>

<span data-ttu-id="d405d-108">Beim Durchsuchen einer großen Anzahl von Postfächern wird die Suche auf Tausende von Servern in einem Microsoft-Rechenzentrum verteilt.</span><span class="sxs-lookup"><span data-stu-id="d405d-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="d405d-109">Zu einem beliebigen Zeitpunkt könnten sich bestimmte Server im Neustartzustand befinden oder einen Fehler bei redundanten Kopien durchführen.</span><span class="sxs-lookup"><span data-stu-id="d405d-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="d405d-110">In einem dieser Fälle ist die Anforderung der Inhaltssuche zum Abrufen von Daten zu einem Zeitergebnis. Im vorherigen Beispiel waren die Fehler für die fehlgeschlagenen Postfächer das Ergebnis des Timeouts der Suche.</span><span class="sxs-lookup"><span data-stu-id="d405d-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="d405d-111">Beheben von Fehlern beim Speicherort von Inhalten</span><span class="sxs-lookup"><span data-stu-id="d405d-111">Resolving content location errors</span></span>

<span data-ttu-id="d405d-112">Ein Neustart der Suche führt häufig zu ähnlichen Fehlern auf verschiedenen Servern.</span><span class="sxs-lookup"><span data-stu-id="d405d-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="d405d-113">Klicken Sie anstatt die Suche neu zu starten, klicken Sie auf die Schaltfläche **Wiederholen,** die oben auf der Suchergebnissetseite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d405d-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Klicken Sie auf die Schaltfläche Wiederholen, um Fehler beim Speicherort von Inhalten zu beheben.](../media/retrycontentsearch3.png)

<span data-ttu-id="d405d-115">Dies führt dazu, dass die Suche nur nach den fehlgeschlagenen Postfächern erneutversucht wird.</span><span class="sxs-lookup"><span data-stu-id="d405d-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="d405d-116">Wenn Sie die Suche wiederholen, werden die anderen Ergebnisse, die erfolgreich zurückgegeben wurden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d405d-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="d405d-117">Tipps, um Fehler beim Speicherort von Inhalten zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="d405d-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="d405d-118">Im Folgenden finden Sie einige zusätzliche Ursachen für Fehler beim Speicherort von Inhalten und einige Tipps, die Sie beim Durchsuchen einer großen Anzahl von Postfächern vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="d405d-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="d405d-119">Das durchsuchte Postfach ist möglicherweise aufgrund von Benutzeraktivitäten ausgelastet.</span><span class="sxs-lookup"><span data-stu-id="d405d-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="d405d-120">In diesem Fall kann der Suchdienst sich selbst drosseln, um zu verhindern, dass das Postfach nicht verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="d405d-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="d405d-121">Um dies zu vermeiden, versuchen Sie, Suchbegriffe außerhalb der Geschäftszeiten zu führen.</span><span class="sxs-lookup"><span data-stu-id="d405d-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="d405d-122">Die Suchabfrage ruft möglicherweise zu viel Inhalt aus dem Postfach ab.</span><span class="sxs-lookup"><span data-stu-id="d405d-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="d405d-123">Versuchen Sie nach Möglichkeit, den Suchbereich mithilfe von Schlüsselwörtern, Datumsbereichen und Suchbedingungen zu einenten.</span><span class="sxs-lookup"><span data-stu-id="d405d-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="d405d-124">Zu viele Schlüsselwörter oder Stichwortausdrücke, wenn Sie eine Suchabfrage mithilfe der [Stichwörterliste erstellen.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)</span><span class="sxs-lookup"><span data-stu-id="d405d-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span> <span data-ttu-id="d405d-125">Wenn Sie eine Suchabfrage ausführen, die die Stichwörterliste verwendet, führt der Dienst im Wesentlichen eine separate Suche für jede Zeile in der Stichwortliste aus, sodass Statistiken generiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d405d-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="d405d-126">Wenn Sie die Stichwörterliste in Suchabfragen verwenden, minimieren Sie die Anzahl der Zeilen in der Stichwortliste, oder teilen Sie die Stichwörter in kleinere Listen auf, und erstellen Sie eine andere Suche für jede Stichwortliste.</span><span class="sxs-lookup"><span data-stu-id="d405d-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d405d-127">Um Probleme zu reduzieren, die durch große Stichwortlisten verursacht werden, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d405d-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="d405d-128">Es werden zu viele Suchdurchsuchungen für dasselbe Postfach gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d405d-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="d405d-129">Versuchen Sie nach Möglichkeit, eine Suche für jedes Postfach gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="d405d-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="d405d-130">Zu viele Postfächer in einer einzigen Suche durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="d405d-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="d405d-131">Die Wahrscheinlichkeit von Fehlern beim Speicherort von Inhalten steigt beim Durchsuchen einer großen Anzahl von Postfächern.</span><span class="sxs-lookup"><span data-stu-id="d405d-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="d405d-132">Versuchen Sie nach Möglichkeit, mehrere Suchen ausführen, sodass jede Suche eine Teilmenge von Postfächern in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="d405d-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="d405d-133">Die erforderliche Wartung wird für das Postfach ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d405d-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="d405d-134">Obwohl diese Ursache wahrscheinlich selten auftritt, warten Sie ein wenig, nachdem Sie den Fehler zum Speicherort des Inhalts erhalten haben, und wiederholen Sie dann die Suche.</span><span class="sxs-lookup"><span data-stu-id="d405d-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
