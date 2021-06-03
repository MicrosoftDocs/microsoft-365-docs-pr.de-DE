---
title: Abfragen des Inhalts in einem Prüfdateisatz
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
description: Erfahren Sie, wie Sie eine Abfrage in einem Prüfdateisatz erstellen und ausführen, um Inhalte für eine effizientere Überprüfung in einem Advanced eDiscovery Fall zu organisieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736422"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="155fc-103">Abfragen und Filtern von Inhalten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="155fc-103">Query and filter content in a review set</span></span>

<span data-ttu-id="155fc-104">In den meisten Fällen ist es hilfreich, sich eingehender mit den Inhalten in einem Prüfdateisatz zu befassen und sie zu organisieren, um eine effizientere Überprüfung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="155fc-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="155fc-105">Mithilfe von Filtern und Abfragen in einem Prüfdateisatz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die den Kriterien Ihrer Rezension entsprechen.</span><span class="sxs-lookup"><span data-stu-id="155fc-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="155fc-106">Standardfilter</span><span class="sxs-lookup"><span data-stu-id="155fc-106">Default filters</span></span>

<span data-ttu-id="155fc-107">In einem Prüfdateisatz gibt es fünf Standardfilter, die im Prüfdateisatz vorinstalliert sind:</span><span class="sxs-lookup"><span data-stu-id="155fc-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="155fc-108">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="155fc-108">Keywords</span></span>
- <span data-ttu-id="155fc-109">Datum</span><span class="sxs-lookup"><span data-stu-id="155fc-109">Date</span></span>
- <span data-ttu-id="155fc-110">Absender/Autor</span><span class="sxs-lookup"><span data-stu-id="155fc-110">Sender/Author</span></span>
- <span data-ttu-id="155fc-111">Betreff/Titel</span><span class="sxs-lookup"><span data-stu-id="155fc-111">Subject/Title</span></span>
- <span data-ttu-id="155fc-112">Tags</span><span class="sxs-lookup"><span data-stu-id="155fc-112">Tags</span></span>

![Standardfiltertypen](../media/DefaultFilterTypes.png)

<span data-ttu-id="155fc-114">Klicken Sie auf jeden Filter, um ihn zu erweitern und einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="155fc-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="155fc-115">Klicken Sie außerhalb des Filters, um den Filter automatisch auf den Prüfdateisatz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="155fc-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="155fc-116">Der folgende Screenshot zeigt den Datumsfilter, der so konfiguriert ist, dass Dokumente innerhalb eines Datumsbereichs angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="155fc-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Erweiterter Standardfilter](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="155fc-118">Hinzufügen oder Entfernen von Filtern</span><span class="sxs-lookup"><span data-stu-id="155fc-118">Add or remove filters</span></span>

<span data-ttu-id="155fc-119">Um Filter hinzuzufügen oder zu entfernen, die für den Prüfdateisatz angezeigt werden, wählen Sie **Filter** aus, um den Filterbereich zu öffnen, der auf einer Flyoutseite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="155fc-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Filterbereich](../media/FilterPanel.png)

<span data-ttu-id="155fc-121">Die verfügbaren Filter sind in vier Abschnitten unterteilt:</span><span class="sxs-lookup"><span data-stu-id="155fc-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="155fc-122">**Suche:** Filter, die unterschiedliche Suchfunktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="155fc-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="155fc-123">**Analyse & vorhersagebasierte Codierung:** Filter für Eigenschaften, die generiert und zu Dokumenten hinzugefügt werden, wenn Sie das **Dokument & E-Mail-Analyseauftrag** ausführen oder Modelle für die Vorhersagecodierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="155fc-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="155fc-124">**IDs:** Filtert nach allen ID-Eigenschaften von Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="155fc-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="155fc-125">**Elementeigenschaften:** Filter für Dokumenteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="155fc-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="155fc-126">Erweitern Sie jeden Abschnitt, und wählen Oder deaktivieren Sie Filter, um sie im Filtersatz hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="155fc-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="155fc-127">Wenn Sie einen Filter hinzufügen, wird er im Filtersatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="155fc-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Liste der Filterabschnitte und Eigenschaften im Filterbereich](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="155fc-129">Wenn Sie einen Abschnitt im Filterbereich erweitern, werden Sie feststellen, dass die Standardfiltertypen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="155fc-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="155fc-130">Sie können diese ausgewählt lassen oder die Auswahl aufheben und sie aus dem Filtersatz entfernen.</span><span class="sxs-lookup"><span data-stu-id="155fc-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="155fc-131">Filtertypen</span><span class="sxs-lookup"><span data-stu-id="155fc-131">Filter types</span></span>

<span data-ttu-id="155fc-132">Jedes durchsuchbare Feld in einem Prüfdateisatz verfügt über einen entsprechenden Filter, den Sie für Filterelemente verwenden können, die auf einem bestimmten Feld basieren.</span><span class="sxs-lookup"><span data-stu-id="155fc-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="155fc-133">Es gibt mehrere Filtertypen:</span><span class="sxs-lookup"><span data-stu-id="155fc-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="155fc-134">**Freetext:** Auf Textfelder wie "Subject" wird ein Freitextfilter angewendet.</span><span class="sxs-lookup"><span data-stu-id="155fc-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="155fc-135">Sie können mehrere Suchbegriffe auflisten, indem Sie sie durch ein Komma trennen.</span><span class="sxs-lookup"><span data-stu-id="155fc-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="155fc-136">**Datum:** Ein Datumsfilter wird für Datumsfelder wie "Datum der letzten Änderung" verwendet.</span><span class="sxs-lookup"><span data-stu-id="155fc-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="155fc-137">**Suchoptionen:** Ein Suchoptionenfilter stellt eine Liste möglicher Werte (jeder Wert wird mit einem Kontrollkästchen angezeigt, das Sie auswählen können) für bestimmte Felder in der Rezension bereit.</span><span class="sxs-lookup"><span data-stu-id="155fc-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="155fc-138">Dieser Filter wird für Felder wie "Sender" verwendet, in denen eine begrenzte Anzahl möglicher Werte im Prüfdateisatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="155fc-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="155fc-139">**Schlüsselwort:** Eine Schlüsselwortbedingung ist eine bestimmte Instanz der Freitextbedingung, die Sie verwenden können, um nach Begriffen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="155fc-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="155fc-140">Sie können auch KQL-ähnliche Abfragesprache in diesem Filtertyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="155fc-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="155fc-141">Weitere Informationen finden Sie in den Abschnitten "Abfragesprache" und "Erweiterter Abfrage-Generator" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="155fc-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="155fc-142">Einschließen und Ausschließen von Filterbeziehungen</span><span class="sxs-lookup"><span data-stu-id="155fc-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="155fc-143">Sie haben die Möglichkeit, die Ein- und Ausschließen-Beziehung für einen bestimmten Filter zu ändern.</span><span class="sxs-lookup"><span data-stu-id="155fc-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="155fc-144">Im Tag-Filter können Sie beispielsweise Elemente ausschließen, die mit einem bestimmten Tag markiert sind, indem Sie im Dropdownfilter **"Gleich"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="155fc-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Tagfilter ausschließen](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="155fc-146">Speichern von Filtern als Abfragen</span><span class="sxs-lookup"><span data-stu-id="155fc-146">Save filters as queries</span></span>

<span data-ttu-id="155fc-147">Nachdem Sie mit Ihren Filtern zufrieden sind, können Sie die Filterkombination als Filterabfrage speichern.</span><span class="sxs-lookup"><span data-stu-id="155fc-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="155fc-148">Auf diese Weise können Sie den Filter in zukünftigen Überprüfungssitzungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="155fc-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="155fc-149">Wählen Sie zum Speichern eines Filters **die Option "Abfrage speichern"** aus, und nennen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="155fc-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="155fc-150">Sie oder andere Prüfer können zuvor gespeicherte Filterabfragen ausführen, indem Sie die Dropdownliste **"Gespeicherte Filterabfragen"** und eine Filterabfrage auswählen, die auf Prüfdateisatzdokumente angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="155fc-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Speichern einer Filterabfrage](../media/SaveFilterQuery.png)

<span data-ttu-id="155fc-152">Um eine Filterabfrage zu löschen, öffnen Sie den Filterbereich, und wählen Sie neben der Abfrage das Papierkorbsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="155fc-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Löschen einer Filterabfrage](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="155fc-154">Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="155fc-154">Query language</span></span>

<span data-ttu-id="155fc-155">Zusätzlich zur Verwendung von Filtern können Sie auch eine KQL-ähnliche Abfragesprache im Filter "Schlüsselwörter" verwenden, um die Suchabfrage für den Prüfdateisatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="155fc-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="155fc-156">Die Abfragesprache für Überprüfungssatzabfragen unterstützt standardmäßige boolesche Operatoren wie **AND**, **OR**, **NOT** und **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="155fc-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="155fc-157">Es unterstützt auch einen einstelligen Platzhalter (?) und einen mehrstelligen Platzhalter (\*).</span><span class="sxs-lookup"><span data-stu-id="155fc-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="155fc-158">Erweiterter Abfrage-Generator</span><span class="sxs-lookup"><span data-stu-id="155fc-158">Advanced query builder</span></span>

<span data-ttu-id="155fc-159">Sie können auch erweiterte Abfragen erstellen, um nach Dokumenten in einem Prüfdateisatz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="155fc-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="155fc-160">Öffnen Sie den Filterbereich, wählen Sie **Filter** aus, und erweitern Sie den **Suchabschnitt.**</span><span class="sxs-lookup"><span data-stu-id="155fc-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Hinzufügen eines KQL-Filters](../media/AddKQLFilter.png)

2. <span data-ttu-id="155fc-162">Wählen Sie den **KQL-Filter** aus, und klicken Sie auf **"Abfrage-Generator öffnen".**</span><span class="sxs-lookup"><span data-stu-id="155fc-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="155fc-163">In diesem Bereich können Sie komplexe KQL-Abfragen mithilfe des Abfrage-Generators erstellen.</span><span class="sxs-lookup"><span data-stu-id="155fc-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="155fc-164">Sie können Bedingungen hinzufügen oder Bedingungsgruppen hinzufügen, die aus mehreren Bedingungen bestehen, die logisch durch **AND-** oder **OR-Beziehungen** verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="155fc-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Verwenden des Abfrage-Generators zum Konfigurieren komplexer Filterabfragen](../media/ComplexQuery.png)
