---
title: Benennungsänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Namensänderungen in Tabellen und Spalten im Schema für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Namensänderungen, Umbenennen, Microsoft Threat Protection
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932202"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="4bdc2-104">Schema der erweiterten Suche – Namensänderungen</span><span class="sxs-lookup"><span data-stu-id="4bdc2-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4bdc2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4bdc2-105">**Applies to:**</span></span>
- <span data-ttu-id="4bdc2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bdc2-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4bdc2-107">Das [Schema für die erweiterte Suche](advanced-hunting-schema-tables.md) wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4bdc2-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="4bdc2-108">In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4bdc2-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="4bdc2-109">In diesem Artikel finden Sie Informationen zu Namensänderungen, die sich auf Ihre Abfragen auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="4bdc2-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="4bdc2-110">Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bdc2-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="4bdc2-111">Sie müssen diese Abfragen nicht manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4bdc2-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="4bdc2-112">Sie müssen jedoch die folgenden Abfragen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="4bdc2-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="4bdc2-113">Abfragen, die mit der API ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="4bdc2-113">Queries that are run using the API</span></span>
- <span data-ttu-id="4bdc2-114">Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="4bdc2-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="4bdc2-115">Dezember 2020</span><span class="sxs-lookup"><span data-stu-id="4bdc2-115">December 2020</span></span>

| <span data-ttu-id="4bdc2-116">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="4bdc2-116">Table name</span></span> | <span data-ttu-id="4bdc2-117">Ursprünglicher Spaltenname</span><span class="sxs-lookup"><span data-stu-id="4bdc2-117">Original column name</span></span> | <span data-ttu-id="4bdc2-118">Neuer Spaltenname</span><span class="sxs-lookup"><span data-stu-id="4bdc2-118">New column name</span></span> | <span data-ttu-id="4bdc2-119">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="4bdc2-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="4bdc2-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4bdc2-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="4bdc2-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="4bdc2-121">FinalEmailAction</span></span> | <span data-ttu-id="4bdc2-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="4bdc2-122">EmailAction</span></span> | <span data-ttu-id="4bdc2-123">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="4bdc2-123">Customer feedback</span></span> |
| [<span data-ttu-id="4bdc2-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4bdc2-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="4bdc2-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="4bdc2-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="4bdc2-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="4bdc2-126">EmailActionPolicy</span></span> | <span data-ttu-id="4bdc2-127">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="4bdc2-127">Customer feedback</span></span> |
| [<span data-ttu-id="4bdc2-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4bdc2-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="4bdc2-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="4bdc2-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="4bdc2-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="4bdc2-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="4bdc2-131">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="4bdc2-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4bdc2-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4bdc2-132">Related topics</span></span>
- [<span data-ttu-id="4bdc2-133">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="4bdc2-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4bdc2-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="4bdc2-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)