---
title: Abfragen der Daten in einem Prüfdateisatz
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
description: ''
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082574"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="6c130-102">Abfragen der Daten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="6c130-102">Query the data in a review set</span></span>

<span data-ttu-id="6c130-103">In den meisten Fällen wird es hilfreich sein, tiefer in die Inhalte einer Überprüfungsgruppe eingreifen und diese für eine effizientere Überprüfung organisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="6c130-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="6c130-104">Abfragen in einem Überprüfungs Satz ermöglichen es Ihnen, sich auf eine Teilmenge von Dokumenten zu konzentrieren, die die von Ihnen auf einmal definierten Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6c130-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="6c130-105">Erstellen und Durchführen einer Abfrage innerhalb eines Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="6c130-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="6c130-106">Wenn Sie eine Abfrage innerhalb Ihres Überprüfungs Satzes erstellen und ausführen möchten, klicken Sie in der Überprüfungsgruppe auf "neue Abfrage".</span><span class="sxs-lookup"><span data-stu-id="6c130-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="6c130-107">Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, klicken Sie auf "Speichern", um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c130-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="6c130-108">Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, klicken Sie einfach auf die gespeicherte Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6c130-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="6c130-109">Eine Liste der Metadaten, nach denen Sie suchen können, finden Sie unter [Document Metadata fields](document-metadata-fields.md) .</span><span class="sxs-lookup"><span data-stu-id="6c130-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="6c130-110">Erstellen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="6c130-110">Building your query</span></span>

<span data-ttu-id="6c130-111">Sie können Ihre Abfrage mit einer Kombination aus Konditions Karten und Abfragesprache in der Bedingungs Karte Stichwörter erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c130-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="6c130-112">Sie können Konditions Karten zusammen als Block gruppieren, um eine komplexere Abfrage zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="6c130-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="6c130-113">Konditions Karte</span><span class="sxs-lookup"><span data-stu-id="6c130-113">Condition card</span></span>

<span data-ttu-id="6c130-114">Jedes durchsuchbare Feld in einem Überprüfungs-Datensatz verfügt über eine entsprechende Bedingungs Karte, die Sie zum Erstellen Ihrer Abfrage verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6c130-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="6c130-115">Es gibt mehrere Arten von Konditions Karten:</span><span class="sxs-lookup"><span data-stu-id="6c130-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="6c130-116">FREETEXT: FREETEXT-Bedingungs Karte wird für Textfelder wie Betreff verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c130-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="6c130-117">Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="6c130-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="6c130-118">Datum: Datum Konditions Karte wird für Datumsfelder wie Datum der letzten Änderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c130-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="6c130-119">Suchoptionen: auf der Bedingungs Karte für Suchoptionen wird eine Liste der möglichen Werte für das jeweilige Feld in der Überprüfungsgruppe bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6c130-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="6c130-120">Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6c130-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="6c130-121">Stichwort: Bedingungs Karte für Schlüsselwörter ist eine bestimmte Instanz der FREETEXT-Bedingungs Karte, die Sie verwenden können, um nach Begriffen zu suchen, oder verwenden Sie die KQL-ähnliche Abfragesprache in.</span><span class="sxs-lookup"><span data-stu-id="6c130-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="6c130-122">Weitere Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="6c130-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="6c130-123">Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="6c130-123">Query language</span></span>

<span data-ttu-id="6c130-124">Zusätzlich zu den Konditions Karten können Sie eine KQL-ähnliche Abfragesprache in der Stichwörter Karte verwenden, um Ihre Abfrage zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="6c130-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="6c130-125">Die Abfragesprache unterstützt die standardmäßige KQL-Syntax wie and, or, Not und Near (n).</span><span class="sxs-lookup"><span data-stu-id="6c130-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="6c130-126">Es unterstützt auch Einzelplatz Platzhalter (?) und mehrstellige Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="6c130-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="6c130-127">Filter</span><span class="sxs-lookup"><span data-stu-id="6c130-127">Filter</span></span>

<span data-ttu-id="6c130-128">Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtern zusätzliche Bedingungen in der Fliege mit Ihren Abfrageergebnissen überlagern.</span><span class="sxs-lookup"><span data-stu-id="6c130-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="6c130-129">Filter unterscheiden sich in einigen wichtigen Punkten von Abfragen:</span><span class="sxs-lookup"><span data-stu-id="6c130-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="6c130-130">Filter sind vorübergehend (d. h., Sie werden nicht in verschiedenen Sitzungen gespeichert), während Abfragen in der Überprüfungsgruppe gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6c130-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="6c130-131">Filter sind immer Additiv; Filter werden oben auf die Abfrage angewendet, die Sie zurzeit anwenden, während durch das Anwenden einer Abfrage die Abfrage wirksam ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6c130-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>