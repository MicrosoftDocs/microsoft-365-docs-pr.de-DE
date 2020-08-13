---
title: 'Verwenden von freigegebenen Abfragen in Microsoft Bedrohungsschutz: Erweiterte Suche'
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, GitHub Repo, meine Abfragen, freigegebene Abfragen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d9dcd07a4fc63130d015bf31270d1de9212f9a53
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649187"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="4d82e-105">Verwenden von freigegebenen Abfragen bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="4d82e-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="4d82e-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4d82e-106">**Applies to:**</span></span>
- <span data-ttu-id="4d82e-107">Microsoft-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="4d82e-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="4d82e-108">[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4d82e-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="4d82e-109">Sie können öffentlich freigegebene Abfragen auch auf GitHub finden.</span><span class="sxs-lookup"><span data-stu-id="4d82e-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="4d82e-110">Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="4d82e-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Abbildung freigegebener Abfragen](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="4d82e-112">Speichern, Ändern und Freigeben einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="4d82e-112">Save, modify, and share a query</span></span>
<span data-ttu-id="4d82e-113">Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4d82e-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="4d82e-114">Erstellen oder Ändern einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="4d82e-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="4d82e-115">Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter**aus.</span><span class="sxs-lookup"><span data-stu-id="4d82e-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="4d82e-116">Geben Sie einen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="4d82e-116">Enter a name for the query.</span></span> 

   ![Abbildung des Speicherns einer Abfrage](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="4d82e-118">Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="4d82e-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="4d82e-119">**Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="4d82e-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="4d82e-120">**Meine Abfragen** – nur für Sie zugänglich</span><span class="sxs-lookup"><span data-stu-id="4d82e-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="4d82e-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4d82e-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="4d82e-122">Löschen oder Umbenennen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="4d82e-122">Delete or rename a query</span></span>
1. <span data-ttu-id="4d82e-123">Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="4d82e-123">Right-click on a query you want to rename or delete.</span></span>

    ![Abbildung des Löschens einer Abfrage](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="4d82e-125">Wählen Sie **Löschen** aus, und bestätigen Sie Löschung.</span><span class="sxs-lookup"><span data-stu-id="4d82e-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="4d82e-126">Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="4d82e-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="4d82e-127">Erstellen eines direkten Links zu einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="4d82e-127">Create a direct link to a query</span></span>
<span data-ttu-id="4d82e-128">Um einen Link zu generieren, der Ihre Abfrage direkt im erweiterten Suchabfrage-Editor öffnet, schließen Sie Ihre Abfrage ab und wählen Sie **Link freigeben**aus.</span><span class="sxs-lookup"><span data-stu-id="4d82e-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="4d82e-129">Access-Abfragen im GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="4d82e-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="4d82e-130">Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="4d82e-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="4d82e-131">Dieses Repository ist für Beiträge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4d82e-131">This repository is open to contributions.</span></span> <span data-ttu-id="4d82e-132">Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="4d82e-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="4d82e-133">Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="4d82e-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="4d82e-134">Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4d82e-134">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d82e-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4d82e-135">Related topics</span></span>
- [<span data-ttu-id="4d82e-136">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="4d82e-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4d82e-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="4d82e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4d82e-138">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="4d82e-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4d82e-139">Jagd auf Geräte, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="4d82e-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4d82e-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="4d82e-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4d82e-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="4d82e-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
