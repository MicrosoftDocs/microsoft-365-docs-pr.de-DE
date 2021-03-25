---
title: Verwenden von freigegebenen Abfragen bei der erweiterten Suche
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Github-Repository, meine Abfragen, freigegebene Abfragen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067431"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="207da-105">Verwenden von freigegebenen Abfragen bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="207da-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="207da-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="207da-106">**Applies to:**</span></span>
- [<span data-ttu-id="207da-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="207da-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="207da-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="207da-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="207da-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="207da-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="207da-110">[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="207da-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="207da-111">Sie können öffentlich freigegebene Abfragen auch auf GitHub finden.</span><span class="sxs-lookup"><span data-stu-id="207da-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="207da-112">Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="207da-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Abbildung freigegebener Abfragen](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="207da-114">Speichern, Ändern und Freigeben einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="207da-114">Save, modify, and share a query</span></span>
<span data-ttu-id="207da-115">Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="207da-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="207da-116">Geben Sie eine neue Abfrage ein, oder laden Sie eine vorhandene abfrage unter **Freigegebene Abfragen** oder **Meine Abfragen**.</span><span class="sxs-lookup"><span data-stu-id="207da-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="207da-117">Wählen **Sie Speichern** oder Speichern **unter** aus den Speicheroptionen aus.</span><span class="sxs-lookup"><span data-stu-id="207da-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="207da-118">Um das Überschreiben einer vorhandenen Abfrage zu vermeiden, wählen Sie **Speichern unter aus.**</span><span class="sxs-lookup"><span data-stu-id="207da-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="207da-119">Geben Sie einen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="207da-119">Enter a name for the query.</span></span>

   ![Abbildung des Speicherns einer Abfrage](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="207da-121">Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="207da-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="207da-122">**Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="207da-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="207da-123">**Meine Abfragen** – nur für Sie zugänglich</span><span class="sxs-lookup"><span data-stu-id="207da-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="207da-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="207da-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="207da-125">Löschen oder Umbenennen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="207da-125">Delete or rename a query</span></span>
1. <span data-ttu-id="207da-126">Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="207da-126">Right-click on a query you want to rename or delete.</span></span>

    ![Abbildung des Löschens einer Abfrage](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="207da-128">Wählen Sie **Löschen** aus, und bestätigen Sie Löschung.</span><span class="sxs-lookup"><span data-stu-id="207da-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="207da-129">Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="207da-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="207da-130">Erstellen eines direkten Links zu einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="207da-130">Create a direct link to a query</span></span>
<span data-ttu-id="207da-131">Um einen Link zu generieren, der Ihre Abfrage direkt im Editor für erweiterte Suchabfragen öffnet, müssen Sie Ihre Abfrage abschließend ausführen und link **freigeben auswählen.**</span><span class="sxs-lookup"><span data-stu-id="207da-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="207da-132">Access-Abfragen im GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="207da-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="207da-133">Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span><span class="sxs-lookup"><span data-stu-id="207da-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="207da-134">Dieses Repository ist für Beiträge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="207da-134">This repository is open to contributions.</span></span> <span data-ttu-id="207da-135">Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="207da-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="207da-136">Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="207da-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="207da-137">Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](threat-analytics.md)-Berichte im Microsoft Defender Security Center bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="207da-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="207da-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="207da-138">Related topics</span></span>
- [<span data-ttu-id="207da-139">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="207da-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="207da-140">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="207da-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="207da-141">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="207da-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="207da-142">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="207da-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="207da-143">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="207da-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="207da-144">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="207da-144">Custom detections overview</span></span>](overview-custom-detections.md)
