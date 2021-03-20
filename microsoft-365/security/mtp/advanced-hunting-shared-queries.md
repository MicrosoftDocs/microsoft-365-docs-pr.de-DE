---
title: Verwenden freigegebener Abfragen in der erweiterten Suche in Microsoft 365 Defender
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Github-Repository, meine Abfragen, freigegebene Abfragen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ccf2b52c744e2ae8e7ccfc631268d79a375c91d4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904042"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="d0d0f-105">Verwenden von freigegebenen Abfragen bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="d0d0f-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d0d0f-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d0d0f-106">**Applies to:**</span></span>
- <span data-ttu-id="d0d0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0d0f-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="d0d0f-108">[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="d0d0f-109">Sie können öffentlich freigegebene Abfragen auch auf GitHub finden.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="d0d0f-110">Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Abbildung freigegebener Abfragen](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="d0d0f-112">Speichern, Ändern und Freigeben einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="d0d0f-112">Save, modify, and share a query</span></span>
<span data-ttu-id="d0d0f-113">Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="d0d0f-114">Erstellen oder Ändern einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="d0d0f-115">Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="d0d0f-116">Geben Sie einen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-116">Enter a name for the query.</span></span> 

   ![Abbildung des Speicherns einer Abfrage](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="d0d0f-118">Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="d0d0f-119">**Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="d0d0f-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="d0d0f-120">**Meine Abfragen** – nur für Sie zugänglich</span><span class="sxs-lookup"><span data-stu-id="d0d0f-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="d0d0f-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="d0d0f-122">Löschen oder Umbenennen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="d0d0f-122">Delete or rename a query</span></span>
1. <span data-ttu-id="d0d0f-123">Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-123">Right-click on a query you want to rename or delete.</span></span>

    ![Abbildung des Löschens einer Abfrage](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="d0d0f-125">Wählen Sie **Löschen** aus, und bestätigen Sie Löschung.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="d0d0f-126">Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="d0d0f-127">Erstellen eines direkten Links zu einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="d0d0f-127">Create a direct link to a query</span></span>
<span data-ttu-id="d0d0f-128">Um einen Link zu generieren, der Ihre Abfrage direkt im Editor für erweiterte Suchabfragen öffnet, müssen Sie Ihre Abfrage abschließend ausführen und link **freigeben auswählen.**</span><span class="sxs-lookup"><span data-stu-id="d0d0f-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="d0d0f-129">Access-Abfragen im GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="d0d0f-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="d0d0f-130">Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="d0d0f-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="d0d0f-131">Dieses Repository ist für Beiträge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-131">This repository is open to contributions.</span></span> <span data-ttu-id="d0d0f-132">Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="d0d0f-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="d0d0f-133">Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="d0d0f-134">Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d0d0f-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0d0f-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d0d0f-135">Related topics</span></span>
- [<span data-ttu-id="d0d0f-136">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="d0d0f-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0d0f-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d0d0f-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0d0f-138">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="d0d0f-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d0d0f-139">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="d0d0f-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d0d0f-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d0d0f-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d0d0f-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d0d0f-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)