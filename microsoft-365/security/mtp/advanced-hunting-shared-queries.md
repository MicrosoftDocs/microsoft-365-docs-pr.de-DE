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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 64c9b07dad0f109698222d3f3f079a4f3318273a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210310"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="7b685-105">Verwenden von freigegebenen Abfragen bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="7b685-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="7b685-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7b685-106">**Applies to:**</span></span>
- <span data-ttu-id="7b685-107">Microsoft-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="7b685-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7b685-108">[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="7b685-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="7b685-109">Sie können öffentlich freigegebene Abfragen auch auf GitHub finden.</span><span class="sxs-lookup"><span data-stu-id="7b685-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="7b685-110">Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="7b685-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Abbildung freigegebener Abfragen](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="7b685-112">Speichern, Ändern und Freigeben einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="7b685-112">Save, modify, and share a query</span></span>
<span data-ttu-id="7b685-113">Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7b685-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="7b685-114">Erstellen oder Ändern einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="7b685-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="7b685-115">Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter**aus.</span><span class="sxs-lookup"><span data-stu-id="7b685-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="7b685-116">Geben Sie einen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="7b685-116">Enter a name for the query.</span></span> 

   ![Abbildung des Speicherns einer Abfrage](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="7b685-118">Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="7b685-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="7b685-119">**Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="7b685-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="7b685-120">**Meine Abfragen** – nur für Sie zugänglich</span><span class="sxs-lookup"><span data-stu-id="7b685-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="7b685-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7b685-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="7b685-122">Löschen oder Umbenennen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="7b685-122">Delete or rename a query</span></span>
1. <span data-ttu-id="7b685-123">Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="7b685-123">Right-click on a query you want to rename or delete.</span></span>

    ![Abbildung des Löschens einer Abfrage](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="7b685-125">Wählen Sie **Löschen** aus, und bestätigen Sie Löschung.</span><span class="sxs-lookup"><span data-stu-id="7b685-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="7b685-126">Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="7b685-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="7b685-127">Access-Abfragen im GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="7b685-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="7b685-128">Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="7b685-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="7b685-129">Dieses Repository ist für Beiträge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7b685-129">This repository is open to contributions.</span></span> <span data-ttu-id="7b685-130">Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="7b685-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="7b685-131">Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7b685-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="7b685-132">Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7b685-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b685-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7b685-133">Related topics</span></span>
- [<span data-ttu-id="7b685-134">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="7b685-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b685-135">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7b685-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7b685-136">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="7b685-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7b685-137">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7b685-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7b685-138">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7b685-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)