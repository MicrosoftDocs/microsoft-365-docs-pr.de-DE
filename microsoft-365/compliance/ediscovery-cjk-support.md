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
description: Erfahren Sie, wie Advanced eDiscovery in Microsoft 365 die Sprachen Chinesisch, Japanisch und Koreanisch (CJK) unterstützt, die einen Doppelbyte-Zeichensatz verwenden.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626935"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="8b606-103">Unterstützung für CJK-Sprachen für erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8b606-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="8b606-104">Advanced eDiscovery unterstützt Doppelbyte-Zeichensatz Sprachen (darunter vereinfachtes Chinesisch, traditionelles Chinesisch, Japanisch und Koreanisch, die als *cjk* -Sprachen bezeichnet werden) für die folgenden erweiterten Szenarien in einem Überprüfungs Satz:</span><span class="sxs-lookup"><span data-stu-id="8b606-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="8b606-105">Wenn Sie [die Daten in einem Überprüfungs Satzes Abfragen](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="8b606-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="8b606-106">Wenn Sie [Dokumente in einem Überprüfungs Satzes markieren](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="8b606-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="8b606-107">Wenn Sie [Falldaten in einer Überprüfungsgruppe](analyzing-data-in-review-set.md) mithilfe von nahezu doppelter Erkennung, e-Mail-Threading und Design Analyse analysieren.</span><span class="sxs-lookup"><span data-stu-id="8b606-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8b606-108">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="8b606-108">Frequently asked questions</span></span>

<span data-ttu-id="8b606-109">**Wie erstelle ich eine Suche zum Sammeln von Elementen, die CJK-Zeichen enthalten?**</span><span class="sxs-lookup"><span data-stu-id="8b606-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="8b606-110">Bei der Suche nach Inhalten in Advanced eDiscovery können Sie CJK-Zeichen für [Stichwortsuche](building-search-queries.md#keyword-searches), [Stichwortabfragen und Suchbedingungen](keyword-queries-and-search-conditions.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b606-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="8b606-111">Die Suche nach CJK-Zeichen wird auch bei der Suche nach Inhalten in der zentralen eDiscovery-und Inhaltssuche unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b606-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="8b606-112">Wir bieten CJK-Unterstützung für alle [Suchoperatoren](keyword-queries-and-search-conditions.md#search-operators) und [Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions), einschließlich der booleschen Operatoren **and**, **or**, **Not**und **near**.</span><span class="sxs-lookup"><span data-stu-id="8b606-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="8b606-113">Wenn Sie sicher sind, dass Inhaltsspeicher oder-Elemente CJK-Zeichen enthalten, die Suche jedoch keine Ergebnisse zurückgibt, klicken Sie auf das Symbol Abfragesprache – Land/Region</span><span class="sxs-lookup"><span data-stu-id="8b606-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Abfragesprache – Land/Region-Symbol in der Inhaltssuche](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="8b606-115">aus, und wählen Sie den entsprechenden Kultur Codewert für Sprache/Land für die Suche aus.</span><span class="sxs-lookup"><span data-stu-id="8b606-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="8b606-116">Die standardmäßige Sprache/Region ist neutral.</span><span class="sxs-lookup"><span data-stu-id="8b606-116">The default language/region is neutral.</span></span>

<span data-ttu-id="8b606-117">**Kann ich gleichzeitig nach mehreren Sprachen suchen?**</span><span class="sxs-lookup"><span data-stu-id="8b606-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="8b606-118">Dies hängt von Ihrem Such Szenario ab.</span><span class="sxs-lookup"><span data-stu-id="8b606-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="8b606-119">Wenn Sie [Daten in einer Überprüfungsgruppe](review-set-search.md) in Advanced eDiscovery Abfragen, können Sie nach mehreren Sprachen suchen.</span><span class="sxs-lookup"><span data-stu-id="8b606-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="8b606-120">Wenn Sie [eine Suche zum Erfassen von Daten erstellen](create-search-to-collect-data.md), erstellen Sie eine separate Suche für jede Sprache, für die Sie sich interessieren.</span><span class="sxs-lookup"><span data-stu-id="8b606-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="8b606-121">Wenn Sie beispielsweise nach einem Dokument suchen, das sowohl Chinesisch als auch Koreanisch enthält, wählen Sie Chinesisch für Ihre erste Abfrage aus, und wählen Sie Koreanisch für die zweite Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="8b606-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="8b606-122">**Das Symbol Abfragesprache-Land/Region wird nicht angezeigt, um eine Sprache für Abfragen in einem Überprüfungs Satzes auszuwählen. Wie kann ich eine Abfragesprache in einer Überprüfungs Sätze-Suche angeben?**</span><span class="sxs-lookup"><span data-stu-id="8b606-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="8b606-123">Zum Überprüfen von Abfrage Sätzen müssen Sie keine Dokumentsprache angeben.</span><span class="sxs-lookup"><span data-stu-id="8b606-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="8b606-124">Erweiterte eDiscovery erkennt Dokumentsprachen automatisch, wenn Sie einem Überprüfungs Satzes Inhalte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b606-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="8b606-125">Auf diese Weise können Sie Ihre Abfrageergebnisse in einem Überprüfungspaket optimieren.</span><span class="sxs-lookup"><span data-stu-id="8b606-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="8b606-126">**Kann ich erkannte Sprachen in [Datei Metadaten](view-documents-in-review-set.md#file-metadata)anzeigen?**</span><span class="sxs-lookup"><span data-stu-id="8b606-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="8b606-127">Nein, erkannte Sprachen werden in Datei Metadaten nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b606-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="8b606-128">**Kann ich nach Dokumentsprachen in einem Überprüfungs Satzes Filtern**?</span><span class="sxs-lookup"><span data-stu-id="8b606-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="8b606-129">Nein, Sie können nicht nach Dokumentsprachen in einem Überprüfungs Satzes filtern, Sortieren oder durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="8b606-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="8b606-130">**Betrifft diese cjk-Version für die Überprüfung Szenarien Festlegen einer meiner vorhandenen suchen und Überprüfungs Sätze?**</span><span class="sxs-lookup"><span data-stu-id="8b606-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="8b606-131">Nein, keines der vorhandenen Such-und Überprüfungs Sätze wird geändert.</span><span class="sxs-lookup"><span data-stu-id="8b606-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="8b606-132">Sie müssen keine vorhandenen Daten neu indizieren, und die Suchergebnisse für den englischen Text sind identisch.</span><span class="sxs-lookup"><span data-stu-id="8b606-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="8b606-133">**Wie ändere ich meine Anzeigesprache in Chinesisch, Japanisch oder Koreanisch?**</span><span class="sxs-lookup"><span data-stu-id="8b606-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="8b606-134">Informationen zum Ändern der Anzeigesprache und der Zeitzone finden Sie unter [Vorgehensweise Festlegen von Sprach-und Regionseinstellungen für Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="8b606-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="8b606-135">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="8b606-135">Known issues</span></span>

- <span data-ttu-id="8b606-136">OCR unterstützt keine CJK-Zeichen aus Bilddateien</span><span class="sxs-lookup"><span data-stu-id="8b606-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="8b606-137">E-Mail-Dateien (wie \*. eml und \*. msg) in [anmerkungsansicht](view-documents-in-review-set.md#annotate-view) werden für CJK-Sprachen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b606-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="8b606-138">Die Hervorhebung von Suchtreffern in der [Text Ansicht](view-documents-in-review-set.md#text-view) wird für CJK-Sprachen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b606-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="8b606-139">Das zum Analysieren von Daten verwendete [Relevanz-Modul](using-relevance.md) unterstützt keine CJK-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="8b606-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="8b606-140">[Abfragebasierte Aufbewahrungen](managing-holds.md#manage-non-custodial-holds) werden für CJK-Sprachen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b606-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
