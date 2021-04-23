---
title: Verwenden freigegebener Abfragen in der erweiterten Suche in Microsoft 365 Defender
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft 365 Defender, microsoft 365, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Github-Repository, meine Abfragen, freigegebene Abfragen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952584"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="30294-105">Verwenden von freigegebenen Abfragen bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="30294-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="30294-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="30294-106">**Applies to:**</span></span>
- <span data-ttu-id="30294-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30294-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="30294-108">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="30294-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="30294-109">[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="30294-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="30294-110">Sie können öffentlich freigegebene Abfragen auch auf GitHub finden.</span><span class="sxs-lookup"><span data-stu-id="30294-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="30294-111">Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="30294-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Abbildung freigegebener Abfragen](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="30294-113">Speichern, Ändern und Freigeben einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="30294-113">Save, modify, and share a query</span></span>
<span data-ttu-id="30294-114">Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="30294-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="30294-115">Erstellen oder Ändern einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="30294-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="30294-116">Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="30294-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="30294-117">Geben Sie einen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="30294-117">Enter a name for the query.</span></span> 

   ![Abbildung des Speicherns einer Abfrage](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="30294-119">Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="30294-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="30294-120">**Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="30294-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="30294-121">**Meine Abfragen** – nur für Sie zugänglich</span><span class="sxs-lookup"><span data-stu-id="30294-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="30294-122">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="30294-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="30294-123">Löschen oder Umbenennen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="30294-123">Delete or rename a query</span></span>
1. <span data-ttu-id="30294-124">Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="30294-124">Right-click on a query you want to rename or delete.</span></span>

    ![Abbildung des Löschens einer Abfrage](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="30294-126">Wählen Sie **Löschen** aus, und bestätigen Sie Löschung.</span><span class="sxs-lookup"><span data-stu-id="30294-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="30294-127">Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="30294-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="30294-128">Erstellen eines direkten Links zu einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="30294-128">Create a direct link to a query</span></span>
<span data-ttu-id="30294-129">Um einen Link zu generieren, der Ihre Abfrage direkt im Editor für erweiterte Suchabfragen öffnet, müssen Sie Ihre Abfrage abschließend ausführen und link **freigeben auswählen.**</span><span class="sxs-lookup"><span data-stu-id="30294-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="30294-130">Access-Abfragen im GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="30294-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="30294-131">Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="30294-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="30294-132">Dieses Repository ist für Beiträge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="30294-132">This repository is open to contributions.</span></span> <span data-ttu-id="30294-133">Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="30294-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="30294-134">Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="30294-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="30294-135">Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="30294-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="30294-136">Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender for Endpoint verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30294-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="30294-137">[Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um bedrohungen mithilfe von weiteren Datenquellen nach Bedrohungen zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="30294-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="30294-138">Sie können Ihre erweiterten Suchworkflows von Microsoft Defender for Endpoint zu Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrate advanced hunting queries from Microsoft Defender for Endpoint ausführen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="30294-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="30294-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30294-139">Related topics</span></span>
- [<span data-ttu-id="30294-140">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="30294-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="30294-141">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="30294-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="30294-142">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="30294-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="30294-143">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="30294-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="30294-144">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="30294-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="30294-145">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="30294-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)