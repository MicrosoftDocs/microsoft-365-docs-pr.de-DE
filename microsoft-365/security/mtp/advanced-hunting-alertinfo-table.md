---
title: Tabelle "AlertInfo" im Schema "Erweiterte Suche"
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der Tabelle "AlertInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Schweregrad, Kategorie, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS und Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929970"
---
# <a name="alertinfo"></a><span data-ttu-id="3731c-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="3731c-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3731c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3731c-105">**Applies to:**</span></span>
- <span data-ttu-id="3731c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3731c-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="3731c-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Warnungen von `AlertInfo` Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3731c-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="3731c-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3731c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="3731c-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3731c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3731c-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="3731c-110">Column name</span></span> | <span data-ttu-id="3731c-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3731c-111">Data type</span></span> | <span data-ttu-id="3731c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3731c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3731c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3731c-113">datetime</span></span> | <span data-ttu-id="3731c-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="3731c-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="3731c-115">string</span><span class="sxs-lookup"><span data-stu-id="3731c-115">string</span></span> | <span data-ttu-id="3731c-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="3731c-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="3731c-117">string</span><span class="sxs-lookup"><span data-stu-id="3731c-117">string</span></span> | <span data-ttu-id="3731c-118">Titel der Warnung</span><span class="sxs-lookup"><span data-stu-id="3731c-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="3731c-119">string</span><span class="sxs-lookup"><span data-stu-id="3731c-119">string</span></span> | <span data-ttu-id="3731c-120">Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität</span><span class="sxs-lookup"><span data-stu-id="3731c-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="3731c-121">string</span><span class="sxs-lookup"><span data-stu-id="3731c-121">string</span></span> | <span data-ttu-id="3731c-122">Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an</span><span class="sxs-lookup"><span data-stu-id="3731c-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="3731c-123">string</span><span class="sxs-lookup"><span data-stu-id="3731c-123">string</span></span> | <span data-ttu-id="3731c-124">Produkt oder Dienst, das die Warnungsinformationen bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="3731c-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="3731c-125">string</span><span class="sxs-lookup"><span data-stu-id="3731c-125">string</span></span> | <span data-ttu-id="3731c-126">Erkennungstechnologie oder Sensor, die die wichtige Komponente oder Aktivität identifiziert hat</span><span class="sxs-lookup"><span data-stu-id="3731c-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="3731c-127">string</span><span class="sxs-lookup"><span data-stu-id="3731c-127">string</span></span> | <span data-ttu-id="3731c-128">MITRE ATT&CK-Techniken, die der Aktivität zugeordnet sind, die die Warnung ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="3731c-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3731c-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3731c-129">Related topics</span></span>
- [<span data-ttu-id="3731c-130">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3731c-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3731c-131">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="3731c-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3731c-132">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="3731c-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3731c-133">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="3731c-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3731c-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="3731c-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3731c-135">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="3731c-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
