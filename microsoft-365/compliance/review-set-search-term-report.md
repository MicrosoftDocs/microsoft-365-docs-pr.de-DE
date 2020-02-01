---
title: Generieren eines Suchausdrucks Berichts für eine Überprüfungsgruppe
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: f3421c62f0c7ac519ad44fc05174cd76872551d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601612"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="62c6e-102">Generieren eines Suchausdrucks Berichts für eine Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="62c6e-102">Generate search term report for a review set</span></span>

<span data-ttu-id="62c6e-103">In eDiscovery ist eine der am häufigsten verwendeten Bedingungen für das Abfragen von Dokumenten die Verwendung von Stichwort Suchbegriffen.</span><span class="sxs-lookup"><span data-stu-id="62c6e-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="62c6e-104">Durch die Identifizierung von Dokumenten, die die spezifischen Stichwörter (auch *Begriffe*genannt) enthalten, die für einen Fall wichtig sind, können Bearbeiter damit beginnen, eine allgemeine Vorstellung davon zu erhalten, was Ihnen zusteht.</span><span class="sxs-lookup"><span data-stu-id="62c6e-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="62c6e-105">In Advanced eDiscovery in Microsoft 365 können Sie genau dies tun, indem Sie Suchbegriffs Berichte zu gespeicherten Abfragen innerhalb eines Überprüfungs Satzes generieren.</span><span class="sxs-lookup"><span data-stu-id="62c6e-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="62c6e-106">Schritt 1: Erstellen einer gespeicherten Abfrage in der Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="62c6e-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="62c6e-107">Erstellen Sie zum Generieren eines aussagekräftigen Suchausdrucks Berichts eine gespeicherte Abfrage, die die Gruppe von Dokumenten in der Überprüfungsgruppe definiert, für die Sie einen Suchausdrucks Bericht generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="62c6e-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="62c6e-108">Sie können beispielsweise einen Datumsbereich oder die tatsächlichen Suchbegriffe (mithilfe der Bedingungsliste für Stichwörter) verwenden, um die Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62c6e-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="62c6e-109">Weitere Informationen zum Überprüfen von Mengen Abfragen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="62c6e-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="62c6e-110">Schritt 2: Generieren eines Suchausdrucks Berichts</span><span class="sxs-lookup"><span data-stu-id="62c6e-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="62c6e-111">Es gibt zwei verschiedene Methoden zum Generieren eines Suchausdrucks Berichts: über das Kontextmenü der gespeicherten Abfrage, die Sie in Schritt 1 erstellt haben, oder über die Suchbegriffs Berichts-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="62c6e-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="62c6e-112">Um das Kontextmenü zu verwenden, öffnen Sie das Kontextmenü der gespeicherten Abfrage, die Sie in Schritt 1 erstellt haben, und klicken Sie auf **Suchausdrucks Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="62c6e-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="62c6e-113">Um die Verwaltungskonsole zu verwenden, wechseln Sie zu **Manage Review Sets #a0 anzeigen von Suchbegriffs Berichten**, klicken Sie auf **neu**, und wählen Sie dann die gespeicherte Abfrage aus, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="62c6e-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="62c6e-114">Geben Sie dann die Begriffe ein, über die Sie berichten möchten, getrennt durch NewLine; Wenn die gespeicherte Abfrage, die Sie in Schritt 1 verwendeter Stichwort-Konditions Karte erstellt haben, wird die Flyout-Seite vorab mit den Begriffen aus der ersten Keyword-Bedingungs Karte aufgefüllt, die in der gespeicherten Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62c6e-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="62c6e-115">Wählen Sie dann bis zu drei Pivots für die Berichterstellung aus, und klicken Sie auf **generieren**, um den Auftrag zum Generieren von Suchbegriffs Berichten zu starten.</span><span class="sxs-lookup"><span data-stu-id="62c6e-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="62c6e-116">Was ist ein Pivot?</span><span class="sxs-lookup"><span data-stu-id="62c6e-116">What is a pivot?</span></span>

<span data-ttu-id="62c6e-117">Pivots ist die Art und Weise, wie der Bericht organisiert wird.</span><span class="sxs-lookup"><span data-stu-id="62c6e-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="62c6e-118">Sehen Sie sich das folgende Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="62c6e-118">Consider the following example.</span></span>

- <span data-ttu-id="62c6e-119">Die gespeicherte Abfrage ruft 10 Dokumente ab: DOC1 bis doc10.</span><span class="sxs-lookup"><span data-stu-id="62c6e-119">The saved query retrieves 10 documents: doc1 through doc10.</span></span>

- <span data-ttu-id="62c6e-120">DOC1, Dokument2, doc3, doc4, doc5, doc6 und DOC7 enthalten den Begriff "eDiscovery".</span><span class="sxs-lookup"><span data-stu-id="62c6e-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="62c6e-121">doc6, DOC7, doc8, doc9 und doc10 enthalten den Begriff "Untersuchung".</span><span class="sxs-lookup"><span data-stu-id="62c6e-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="62c6e-122">DOC1, doc3, doc5, DOC7, doc9 sind aus Depotbank A.</span><span class="sxs-lookup"><span data-stu-id="62c6e-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="62c6e-123">Dokument2, doc4, doc6, doc8, doc10 sind aus Depotbank B.</span><span class="sxs-lookup"><span data-stu-id="62c6e-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="62c6e-124">Wenn Sie in diesem Fall einen Suchausdrucks Bericht zu den Begriffen "eDiscovery" und "Untersuchung" generieren und auf Depotbanken pivotieren, wäre der Suchbegriff Bericht wie folgt organisiert:</span><span class="sxs-lookup"><span data-stu-id="62c6e-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="62c6e-125">"eDiscovery"-Depot A: 4 Dokumente</span><span class="sxs-lookup"><span data-stu-id="62c6e-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="62c6e-126">"eDiscovery"-Verwalter B: 3 Dokumente</span><span class="sxs-lookup"><span data-stu-id="62c6e-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="62c6e-127">"Untersuchung"-Depot A: 2 Dokumente</span><span class="sxs-lookup"><span data-stu-id="62c6e-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="62c6e-128">"Untersuchung"-Verwalter B: 3 Dokumente</span><span class="sxs-lookup"><span data-stu-id="62c6e-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="62c6e-129">Schritt 3: Herunterladen des Berichts</span><span class="sxs-lookup"><span data-stu-id="62c6e-129">Step 3: Download report</span></span>

<span data-ttu-id="62c6e-130">In der Suchbegriffs-Verwaltungskonsole können Sie den Status eines zuvor erstellten Berichtsauftrags für den Suchbegriff nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="62c6e-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="62c6e-131">Sobald der Auftrag abgeschlossen ist, können Sie auf die Zeile für den Suchbegriff Bericht klicken und auf "herunterladen" klicken, um den Suchbegriff Bericht in einem CSV-Format herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="62c6e-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="62c6e-132">Es wird eine Zeile pro (Suchbegriff, Pivots) Tupel geben, und jede Zeile enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="62c6e-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="62c6e-133">Wie viele Dokumente wurden abgerufen?</span><span class="sxs-lookup"><span data-stu-id="62c6e-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="62c6e-134">Wie oft wurde der Suchbegriff in den Dokumenten gefunden?</span><span class="sxs-lookup"><span data-stu-id="62c6e-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="62c6e-135">Was ist das Gesamtvolumen der abgerufenen Dokumente?</span><span class="sxs-lookup"><span data-stu-id="62c6e-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="62c6e-136">Wie viele Familien wurden abgerufen?</span><span class="sxs-lookup"><span data-stu-id="62c6e-136">How many families were retrieved?</span></span>

- <span data-ttu-id="62c6e-137">Was ist die Gesamtanzahl von Dokumenten dieser Familien, einschließlich der Dokumente, die nicht den Suchbegriff hatten?</span><span class="sxs-lookup"><span data-stu-id="62c6e-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="62c6e-138">Was ist das Gesamtvolumen der oben genannten?</span><span class="sxs-lookup"><span data-stu-id="62c6e-138">What is the total volume of the above?</span></span>