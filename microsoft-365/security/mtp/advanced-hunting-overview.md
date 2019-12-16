---
title: Übersicht über die erweiterte Suche in Microsoft Threat Protection
description: Erfahren Sie mehr über erweiterte Suchabfragen in Microsoft 365 und wie Sie diese verwenden, um Bedrohungen und Schwachstellen in Ihrem Netzwerk proaktiv zu ermitteln.
keywords: Erweiterte Suche, Bedrohungssuche, Cyber-Bedrohungssuche, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennung, Schema, Kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 03cd648a178d63b2b964e0136c105068f4d1c6ca
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911135"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="fb935-104">Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fb935-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="fb935-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fb935-105">**Applies to:**</span></span>
- <span data-ttu-id="fb935-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fb935-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="fb935-107">Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können.</span><span class="sxs-lookup"><span data-stu-id="fb935-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="fb935-108">Sie können Ereignisse in Ihrem Netzwerk proaktiv prüfen, um interessante Indikatoren und Entitäten zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="fb935-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="fb935-109">Der flexible Zugriff auf Daten ermöglicht eine uneingeschränkte Suche nach bekannten und potenziellen Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="fb935-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="fb935-110">Im Microsoft 365 Security Center unterstützt die erweiterte Suche Abfragen für Daten aus Microsoft Defender ATP und deckt sowohl Daten von eingebundenen Geräten als auch aus Office 365 ATP ab und stellt Daten aus E-Mails bereit.</span><span class="sxs-lookup"><span data-stu-id="fb935-110">in the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="fb935-111">Um die erweiterte Suche verwenden zu können, [aktivieren Sie Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="fb935-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="fb935-112">Erste Schritte mit der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="fb935-112">Get started with advanced hunting</span></span>

<span data-ttu-id="fb935-113">Es wird empfohlen, mehrere Schritte durchzugehen, um schnell mit der Verwendung der erweiterten Suche loszulegen.</span><span class="sxs-lookup"><span data-stu-id="fb935-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="fb935-114">Lernziel</span><span class="sxs-lookup"><span data-stu-id="fb935-114">Learning goal</span></span> | <span data-ttu-id="fb935-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb935-115">Description</span></span> | <span data-ttu-id="fb935-116">Ressource</span><span class="sxs-lookup"><span data-stu-id="fb935-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="fb935-117">**Gespür für die Sprache**</span><span class="sxs-lookup"><span data-stu-id="fb935-117">**Get a feel for the language**</span></span> | <span data-ttu-id="fb935-118">Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/), die dieselbe Syntax und dieselben Operatoren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb935-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="fb935-119">Beginnen Sie, die Abfragesprache zu erlernen, indem Sie die erste Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb935-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="fb935-120">Übersicht über die Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="fb935-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="fb935-121">**Grundlegendes zum Schema**</span><span class="sxs-lookup"><span data-stu-id="fb935-121">**Understand the schema**</span></span> | <span data-ttu-id="fb935-122">Verschaffen Sie sich einen allgemeinen Überblick über die Tabellen im Schema und die zugehörigen Spalten.</span><span class="sxs-lookup"><span data-stu-id="fb935-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="fb935-123">Auf diese Weise können Sie bestimmen, wo nach Daten gesucht wird und wie Sie Ihre Abfragen erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb935-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="fb935-124">Schemareferenz</span><span class="sxs-lookup"><span data-stu-id="fb935-124">Schema Reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="fb935-125">**Verwenden vordefinierter Abfragen**</span><span class="sxs-lookup"><span data-stu-id="fb935-125">**Use predefined queries**</span></span> | <span data-ttu-id="fb935-126">Erkunden Sie Sammlungen vordefinierten Abfragen, die unterschiedliche Bedrohungssuchszenarien umfassen.</span><span class="sxs-lookup"><span data-stu-id="fb935-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="fb935-127">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="fb935-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="fb935-128">**Optimieren von Abfragen**</span><span class="sxs-lookup"><span data-stu-id="fb935-128">**Optimize queries**</span></span> | <span data-ttu-id="fb935-129">Erfahren Sie, wie Sie effiziente Abfragen und Abfragen erstellen, die Daten aus E-Mails und Geräten kombinieren.</span><span class="sxs-lookup"><span data-stu-id="fb935-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="fb935-130">[Bewährte Methoden für Abfragen](advanced-hunting-shared-queries.md), [Suche auf Geräten und E-Mails](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="fb935-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="fb935-131">Hilfe beim Schreiben von Abfragen</span><span class="sxs-lookup"><span data-stu-id="fb935-131">Get help as you write queries</span></span>
<span data-ttu-id="fb935-132">Nutzen Sie die folgenden Funktionen, um Abfragen schneller zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="fb935-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="fb935-133">**Vorschlagssuche** – Beim Schreiben von Abfragen stellt die erweiterte Suche Vorschläge bereit.</span><span class="sxs-lookup"><span data-stu-id="fb935-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="fb935-134">**Schemareferenz** – Eine Schemareferenz, die die Liste der Tabellen und die zugehörigen Spalten enthält, wird neben dem Arbeitsbereich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fb935-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="fb935-135">Wenn Sie weitere Informationen erhalten möchten, zeigen Sie mit dem Mauszeiger auf ein Element.</span><span class="sxs-lookup"><span data-stu-id="fb935-135">For more information, hover over an item.</span></span> <span data-ttu-id="fb935-136">Doppelklicken Sie auf ein Element, um es im Abfrage-Editor einzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb935-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="fb935-137">Ausführen eines Drilldowns für Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="fb935-137">Drilldown from query results</span></span>
<span data-ttu-id="fb935-138">Wenn Sie weitere Informationen zu Entitäten, z. B. Computern, Dateien, Benutzern, IP-Adressen und URLs, anzeigen möchten, klicken Sie in den Abfrageergebnissen einfach auf den Entitätsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="fb935-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="fb935-139">Dadurch wird eine detaillierte Profilseite für die ausgewählte Entität im Microsoft Defender Security Center geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fb935-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="fb935-140">Optimieren von Abfragen aus den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="fb935-140">Tweak your queries from the results</span></span>
<span data-ttu-id="fb935-141">Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="fb935-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="fb935-142">Sie können die folgenden Optionen für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="fb935-142">You can use the options on this page to modify the server farm settings.</span></span>

- <span data-ttu-id="fb935-143">Explizites Suchen nach dem ausgewählten Wert (`==`)</span><span class="sxs-lookup"><span data-stu-id="fb935-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="fb935-144">Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)</span><span class="sxs-lookup"><span data-stu-id="fb935-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="fb935-145">Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with`</span><span class="sxs-lookup"><span data-stu-id="fb935-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Abbildung eines erweiterten Suchresultsets in Microsoft Defender ATP](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="fb935-147">Filtern der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="fb935-147">Filter the query results</span></span>
<span data-ttu-id="fb935-148">Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="fb935-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="fb935-149">Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="fb935-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="fb935-150">Verfeinern Sie Ihre Abfrage, indem Sie die Schaltflächen „+“ oder „-“ für die Werte verwenden, die Sie ein- bzw. ausschließen möchten, und dann **Abfrage ausführen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="fb935-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Abbildung eines erweiterten Suchfilters](../images/advanced-hunting-filter.png)

<span data-ttu-id="fb935-152">Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fb935-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fb935-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fb935-153">Related topics</span></span>
- [<span data-ttu-id="fb935-154">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="fb935-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fb935-155">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="fb935-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fb935-156">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="fb935-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fb935-157">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="fb935-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fb935-158">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="fb935-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)