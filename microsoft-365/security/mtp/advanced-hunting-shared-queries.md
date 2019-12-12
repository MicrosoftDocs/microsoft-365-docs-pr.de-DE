---
title: 'Verwenden von freigegebenen Abfragen in Microsoft Bedrohungsschutz: Erweiterte Suche'
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungssuche, Cyber-Bedrohungssuche, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennung, Schema, Kusto, Github-Repo, meine Abfragen, freigegebene Abfragen
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
ms.openlocfilehash: bd92bde39f56180a79490a24b78ee3824cc262e7
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911104"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="bc6c4-105">Verwenden von freigegebenen Abfragen bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="bc6c4-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="bc6c4-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bc6c4-106">**Applies to:**</span></span>
- <span data-ttu-id="bc6c4-107">Microsoft-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="bc6c4-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="bc6c4-108">[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="bc6c4-109">Sie können öffentlich freigegebene Abfragen auch auf GitHub finden.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="bc6c4-110">Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Abbildung freigegebener Abfragen](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="bc6c4-112">Speichern, Ändern und Freigeben einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="bc6c4-112">Save, modify, and share a query</span></span>
<span data-ttu-id="bc6c4-113">Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="bc6c4-114">Erstellen oder Ändern einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-114">Create or modify a lookup table</span></span> 

2. <span data-ttu-id="bc6c4-115">Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter**aus.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="bc6c4-116">Geben Sie einen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-116">Enter a descriptive name for the connection.</span></span> 

   ![Abbildung des Speicherns einer Abfrage](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="bc6c4-118">Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="bc6c4-119">**Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="bc6c4-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="bc6c4-120">**Meine Abfragen** – nur für Sie zugänglich</span><span class="sxs-lookup"><span data-stu-id="bc6c4-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="bc6c4-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="bc6c4-122">Löschen oder Umbenennen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="bc6c4-122">Delete or rename a query</span></span>
1. <span data-ttu-id="bc6c4-123">Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-123">Right-click on a query you want to rename or delete.</span></span>

    ![Abbildung des Löschens einer Abfrage](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="bc6c4-125">Wählen Sie **Löschen** aus, und bestätigen Sie Löschung.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="bc6c4-126">Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="bc6c4-127">Access-Abfragen im GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="bc6c4-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="bc6c4-128">Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="bc6c4-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="bc6c4-129">Dieses Repository ist für Beiträge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-129">This repository is open to contributions.</span></span> <span data-ttu-id="bc6c4-130">Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="bc6c4-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="bc6c4-131">Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="bc6c4-132">Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bc6c4-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc6c4-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bc6c4-133">Related topics</span></span>
- [<span data-ttu-id="bc6c4-134">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="bc6c4-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bc6c4-135">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="bc6c4-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bc6c4-136">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="bc6c4-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bc6c4-137">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="bc6c4-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bc6c4-138">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="bc6c4-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)