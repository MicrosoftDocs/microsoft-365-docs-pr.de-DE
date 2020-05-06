---
title: Erstellen von Suchabfragen-Daten Untersuchungen
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
ms.custom: seo-marvel-mar2020
description: Verwenden Sie Stichwörter und Bedingungen, um den Suchbereich bei der Suche nach Daten mithilfe von Daten Untersuchung in Microsoft 365 einzuschränken.
ms.openlocfilehash: 95466d0e7c7109001fef001cc0d5bca5b6d658ed
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034113"
---
# <a name="build-search-queries"></a><span data-ttu-id="93407-103">Erstellen von Suchabfragen</span><span class="sxs-lookup"><span data-stu-id="93407-103">Build search queries</span></span>

<span data-ttu-id="93407-104">Beim Erstellen von Suchabfragen können Sie Schlüsselwörter verwenden, um bestimmte Inhalte und Bedingungen zu finden, um den Umfang der Suche einzuschränken, um Elemente zurückzugeben, die für Ihre Untersuchung am relevantesten sind.</span><span class="sxs-lookup"><span data-stu-id="93407-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![Verwenden von Stichwörtern und Bedingungen zum Einschränken der Ergebnisse einer Suche](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="93407-106">Stichwortsuche</span><span class="sxs-lookup"><span data-stu-id="93407-106">Keyword searches</span></span>

<span data-ttu-id="93407-107">Geben Sie eine Stichwortabfrage in das Feld **Schlüsselwörter** in der Suchabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="93407-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="93407-108">Sie können Schlüsselwörter, Eigenschaften von e-Mail-Nachrichten wie gesendete und empfangene Datumsangaben oder Dokumenteigenschaften angeben, beispielsweise Dateinamen oder das Datum, an dem ein Dokument zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="93407-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="93407-109">Sie können auch komplexere Abfragen mit booleschen Operatoren wie **AND**, **OR**, **NOT** und **NEAR** verwenden.</span><span class="sxs-lookup"><span data-stu-id="93407-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="93407-110">Sie können auch nach vertraulichen Informationen wie Sozialversicherungsnummern in Dokumenten in SharePoint und OneDrive (nicht in e-Mail-Nachrichten) suchen oder nach Dokumenten suchen, die extern freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="93407-110">You can also search for sensitive information, such as social security numbers, in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="93407-111">Wenn Sie das Feld **Schlüsselwörter** leer lassen, sind alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, in den Suchergebnissen enthalten.</span><span class="sxs-lookup"><span data-stu-id="93407-111">If you leave the **Keywords** box empty, all content located in the specified content locations is included in the search results.</span></span>
    
<span data-ttu-id="93407-112">Alternativ können Sie das Kontrollkästchen **Schlüsselwort Liste anzeigen** aktivieren und dann in jede Zeile ein Stichwort oder einen Stichwort Satz eingeben.</span><span class="sxs-lookup"><span data-stu-id="93407-112">Alternatively, you can select the **Show keyword list** check box and then type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="93407-113">Wenn Sie dies tun, werden die Schlüsselwörter in jeder Zeile durch einen logischen Operator (dargestellt als *c:s*) verbunden, der in der Funktionalität des **or** -Operators in der erstellten Suchabfrage ähnelt.</span><span class="sxs-lookup"><span data-stu-id="93407-113">If you do this, the keywords in each row are connected by a logical operator (represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="93407-114">Dies bedeutet, dass Elemente, die ein beliebiges Schlüsselwort in einer beliebigen Zeile enthalten, in den Suchergebnissen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="93407-114">This means that items that contain any keyword in any row are included in the search results.</span></span>

![Verwenden der Stichwortliste zum Abrufen von Statistiken zu jedem Stichwort in der Abfrage](../media/KeywordListSearch.png)

<span data-ttu-id="93407-116">Gründe für die Verwendung der Schlüsselwortliste</span><span class="sxs-lookup"><span data-stu-id="93407-116">Why use the keyword list?</span></span> <span data-ttu-id="93407-117">Sie können Statistiken abrufen, die zeigen, wie viele Elemente in der Stichwortliste mit jedem Stichwort übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="93407-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="93407-118">Dies kann Ihnen helfen, schnell die Schlüsselwörter zu identifizieren, die am häufigsten (und am wenigsten) effektiv sind.</span><span class="sxs-lookup"><span data-stu-id="93407-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="93407-119">Sie können auch eine Stichwort Phrase (umgeben von Klammern) in einer Zeile in der Liste Stichwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="93407-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="93407-120">Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistiken](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="93407-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="93407-121">Um Probleme aufgrund großer Stichwortlisten zu verringern, sind Sie auf maximal 20 Zeilen in der Stichwortliste limitiert.</span><span class="sxs-lookup"><span data-stu-id="93407-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="93407-122">Bedingungen</span><span class="sxs-lookup"><span data-stu-id="93407-122">Conditions</span></span>
    
<span data-ttu-id="93407-123">Sie können Suchbedingungen hinzufügen, um den Umfang einer Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="93407-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="93407-124">Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="93407-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="93407-125">Eine Bedingung ist logisch mit der Stichwortabfrage (im Feld Schlüsselwort angegeben) durch einen logischen Operator (der als *c:c*dargestellt wird) verbunden, der in der Funktionalität des **and-** Operators ähnelt.</span><span class="sxs-lookup"><span data-stu-id="93407-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="93407-126">Dies bedeutet, dass Elemente sowohl die Stichwortabfrage als auch eine oder mehrere Bedingungen erfüllen müssen, die in den Suchergebnissen enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="93407-126">This means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="93407-127">Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="93407-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="93407-128">Eine Liste und eine Beschreibung der Bedingungen, die Sie in einer Suchabfrage verwenden können, finden Sie im Abschnitt "Suchbedingungen" unter [Stichwortabfragen und Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="93407-128">For a list and description of conditions you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
