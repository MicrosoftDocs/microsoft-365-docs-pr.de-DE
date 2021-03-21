---
title: CJK/Double Byte-Unterstützung für Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Advanced eDiscovery in Microsoft 365 Sprachen wie Chinesisch, Japanisch und Koreanisch (CJK) unterstützt, die einen Doppel-Byte-Zeichensatz verwenden.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926601"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="fa60f-103">CJK-Sprachunterstützung für Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fa60f-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="fa60f-104">Advanced eDiscovery unterstützt Doppel-Byte-Zeichensatzsprachen (dazu gehören vereinfachtes Chinesisch, traditionelles Chinesisch, Japanisch und Koreanisch, die gemeinsam als *CJK-Sprachen* bekannt sind) für die folgenden erweiterten Szenarien in einem Überprüfungssatz:</span><span class="sxs-lookup"><span data-stu-id="fa60f-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="fa60f-105">Wenn Sie [die Daten in einem Überprüfungssatz abfragen.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="fa60f-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="fa60f-106">Wenn Sie [Dokumente in einem Überprüfungssatz kennzeichnen.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="fa60f-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="fa60f-107">Wenn Sie [Falldaten in einem Überprüfungssatz](analyzing-data-in-review-set.md) mithilfe der Fast-Duplikaterkennung, des E-Mail-Threadings und der Designsanalyse analysieren.</span><span class="sxs-lookup"><span data-stu-id="fa60f-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="fa60f-108">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="fa60f-108">Frequently asked questions</span></span>

<span data-ttu-id="fa60f-109">**Wie erstelle ich eine Suche zum Sammeln von Elementen, die #A0 enthalten?**</span><span class="sxs-lookup"><span data-stu-id="fa60f-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="fa60f-110">Sie können #A0 [für](building-search-queries.md#keyword-searches)Stichwortsuchen, Stichwortabfragen und [Suchbedingungen](keyword-queries-and-search-conditions.md) verwenden, wenn Sie in Advanced eDiscovery nach Inhalten suchen.</span><span class="sxs-lookup"><span data-stu-id="fa60f-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="fa60f-111">Die Suche nach #A0 wird auch bei der Suche nach Inhalten in Core eDiscovery und Content Search unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa60f-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="fa60f-112">Wir bieten CJK-Unterstützung für [](keyword-queries-and-search-conditions.md#search-conditions)alle [Suchoperatoren](keyword-queries-and-search-conditions.md#search-operators) und Suchbedingungen, einschließlich der booleschen Operatoren **AND**, **OR**, **NOT** und **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="fa60f-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="fa60f-113">Wenn Sie sicher sind, dass Inhaltsstandorte oder -elemente #A0 enthalten, Suchabfragen jedoch keine Ergebnisse zurückgeben, klicken Sie auf das Symbol Abfragesprache-Land/Region</span><span class="sxs-lookup"><span data-stu-id="fa60f-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Abfragesprache-Land/Region-Symbol in der Inhaltssuche](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="fa60f-115">und wählen Sie den entsprechenden Sprach-Länder-Kulturcodewert für die Suche aus.</span><span class="sxs-lookup"><span data-stu-id="fa60f-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="fa60f-116">Die standardmäßige Sprache/Region ist neutral.</span><span class="sxs-lookup"><span data-stu-id="fa60f-116">The default language/region is neutral.</span></span>

<span data-ttu-id="fa60f-117">**Kann ich nach mehreren Sprachen gleichzeitig suchen?**</span><span class="sxs-lookup"><span data-stu-id="fa60f-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="fa60f-118">Dies hängt von Ihrem Suchszenario ab.</span><span class="sxs-lookup"><span data-stu-id="fa60f-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="fa60f-119">Wenn Sie [Daten in einem Überprüfungssatz](review-set-search.md) in Advanced eDiscovery abfragen, können Sie nach mehreren Sprachen suchen.</span><span class="sxs-lookup"><span data-stu-id="fa60f-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="fa60f-120">Wenn Sie [eine Suche zum Sammeln von Daten erstellen,](create-search-to-collect-data.md)erstellen Sie eine separate Suche für jede Zielsprache.</span><span class="sxs-lookup"><span data-stu-id="fa60f-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="fa60f-121">Wenn Sie z. B. nach einem Dokument suchen, das Chinesisch und Koreanisch enthält, wählen Sie chinesisch für die erste Abfrage aus, und wählen Sie koreanisch für die zweite Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="fa60f-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="fa60f-122">**Das Symbol "Sprache/Land/Region der Abfrage" wird nicht angezeigt, um eine Sprache für Abfragen in einem Überprüfungssatz auszuwählen. Wie kann ich eine Abfragesprache in einer Überprüfungssatzsuche angeben?**</span><span class="sxs-lookup"><span data-stu-id="fa60f-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="fa60f-123">Für Überprüfungssatzabfragen müssen Sie keine Dokumentsprache angeben.</span><span class="sxs-lookup"><span data-stu-id="fa60f-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="fa60f-124">Advanced eDiscovery erkennt automatisch Dokumentsprachen, wenn Sie einem Überprüfungssatz Inhalte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa60f-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="fa60f-125">Auf diese Weise können Sie Ihre Abfrageergebnisse in einem Überprüfungssatz optimieren.</span><span class="sxs-lookup"><span data-stu-id="fa60f-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="fa60f-126">**Kann ich erkannte Sprachen in [Dateimetadaten sehen?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="fa60f-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="fa60f-127">Nein, in Dateimetadaten werden keine erkannten Sprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa60f-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="fa60f-128">**Kann ich in einem Überprüfungssatz nach Dokumentsprachen filtern?**</span><span class="sxs-lookup"><span data-stu-id="fa60f-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="fa60f-129">Nein, Sie können in einem Überprüfungssatz nicht nach Dokumentsprachen filtern, sortieren oder suchen.</span><span class="sxs-lookup"><span data-stu-id="fa60f-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="fa60f-130">**Wirkt sich diese #A0 für Überprüfungssatzszenarien auf meine vorhandenen Such- und Überprüfungssätze aus?**</span><span class="sxs-lookup"><span data-stu-id="fa60f-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="fa60f-131">Nein, keine der vorhandenen Such- und Überprüfungssätze ändert sich.</span><span class="sxs-lookup"><span data-stu-id="fa60f-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="fa60f-132">Vorhandene Daten müssen nicht neu indiziert werden, und die Suchergebnisse für englischen Text sind identisch.</span><span class="sxs-lookup"><span data-stu-id="fa60f-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="fa60f-133">**Wie kann ich meine Anzeigesprache in Chinesisch, Japanisch oder Koreanisch ändern?**</span><span class="sxs-lookup"><span data-stu-id="fa60f-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="fa60f-134">Informationen zum Ändern von Anzeigesprache und Zeitzone finden Sie unter Festlegen von Sprach- und [Regioneneinstellungen für Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="fa60f-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="fa60f-135">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="fa60f-135">Known issues</span></span>

- <span data-ttu-id="fa60f-136">OCR unterstützt keine #A0 aus Bilddateien</span><span class="sxs-lookup"><span data-stu-id="fa60f-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="fa60f-137">E-Mail-Dateien (z. B. \*.eml und \*.msg) [in](view-documents-in-review-set.md#annotate-view) der Anmerkungsansicht werden für #A0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa60f-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="fa60f-138">Die Hervorhebung von Suchtreffer in der [Textansicht](view-documents-in-review-set.md#text-view) wird für CJK-Sprachen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa60f-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="fa60f-139">Das [Relevanzmodul,](using-relevance.md) das zum Analysieren von Daten verwendet wird, unterstützt keine CJK-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="fa60f-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="fa60f-140">[Abfragebasierte Halte halte](managing-holds.md#manage-non-custodial-holds) werden für CJK-Sprachen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa60f-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>