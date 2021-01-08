---
title: Benennungsänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Namensänderungen in Tabellen und Spalten im Schema für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Benennungsänderungen, Umbenennen, Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780811"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="755a5-104">Schema "Erweiterte Suche" – Namensänderungen</span><span class="sxs-lookup"><span data-stu-id="755a5-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="755a5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="755a5-105">**Applies to:**</span></span>
- <span data-ttu-id="755a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="755a5-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="755a5-107">Das [Schema für die erweiterte Suche](advanced-hunting-schema-tables.md) wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="755a5-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="755a5-108">In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="755a5-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="755a5-109">In diesem Artikel finden Sie Informationen zu Namensänderungen, die sich auf Ihre Abfragen auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="755a5-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="755a5-110">Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="755a5-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="755a5-111">Sie müssen diese Abfragen nicht manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="755a5-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="755a5-112">Sie müssen jedoch die folgenden Abfragen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="755a5-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="755a5-113">Abfragen, die mit der API ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="755a5-113">Queries that are run using the API</span></span>
- <span data-ttu-id="755a5-114">Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="755a5-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="755a5-115">Dezember 2020</span><span class="sxs-lookup"><span data-stu-id="755a5-115">December 2020</span></span>

| <span data-ttu-id="755a5-116">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="755a5-116">Table name</span></span> | <span data-ttu-id="755a5-117">Ursprünglicher Spaltenname</span><span class="sxs-lookup"><span data-stu-id="755a5-117">Original column name</span></span> | <span data-ttu-id="755a5-118">Neuer Spaltenname</span><span class="sxs-lookup"><span data-stu-id="755a5-118">New column name</span></span> | <span data-ttu-id="755a5-119">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="755a5-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="755a5-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="755a5-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="755a5-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="755a5-121">FinalEmailAction</span></span> | <span data-ttu-id="755a5-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="755a5-122">EmailAction</span></span> | <span data-ttu-id="755a5-123">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="755a5-123">Customer feedback</span></span> |
| [<span data-ttu-id="755a5-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="755a5-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="755a5-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="755a5-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="755a5-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="755a5-126">EmailActionPolicy</span></span> | <span data-ttu-id="755a5-127">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="755a5-127">Customer feedback</span></span> |
| [<span data-ttu-id="755a5-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="755a5-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="755a5-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="755a5-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="755a5-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="755a5-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="755a5-131">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="755a5-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="755a5-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="755a5-132">Related topics</span></span>
- [<span data-ttu-id="755a5-133">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="755a5-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="755a5-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="755a5-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)