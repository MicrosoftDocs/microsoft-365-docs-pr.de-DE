---
title: AlertInfo-Tabelle im Schema der erweiterten Suche
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der AlertInfo-Tabelle des schemas für erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, severity, category, MITRE, ATT&CK, Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, MCAS und Microsoft Defender for Identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933697"
---
# <a name="alertinfo"></a><span data-ttu-id="9e3c3-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="9e3c3-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e3c3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9e3c3-105">**Applies to:**</span></span>
- <span data-ttu-id="9e3c3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e3c3-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9e3c3-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Warnungen von `AlertInfo` Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9e3c3-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="9e3c3-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9e3c3-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c3-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e3c3-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="9e3c3-110">Column name</span></span> | <span data-ttu-id="9e3c3-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9e3c3-111">Data type</span></span> | <span data-ttu-id="9e3c3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e3c3-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9e3c3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="9e3c3-113">datetime</span></span> | <span data-ttu-id="9e3c3-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9e3c3-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="9e3c3-115">string</span><span class="sxs-lookup"><span data-stu-id="9e3c3-115">string</span></span> | <span data-ttu-id="9e3c3-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="9e3c3-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="9e3c3-117">string</span><span class="sxs-lookup"><span data-stu-id="9e3c3-117">string</span></span> | <span data-ttu-id="9e3c3-118">Titel der Warnung</span><span class="sxs-lookup"><span data-stu-id="9e3c3-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="9e3c3-119">string</span><span class="sxs-lookup"><span data-stu-id="9e3c3-119">string</span></span> | <span data-ttu-id="9e3c3-120">Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität</span><span class="sxs-lookup"><span data-stu-id="9e3c3-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="9e3c3-121">string</span><span class="sxs-lookup"><span data-stu-id="9e3c3-121">string</span></span> | <span data-ttu-id="9e3c3-122">Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an</span><span class="sxs-lookup"><span data-stu-id="9e3c3-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="9e3c3-123">string</span><span class="sxs-lookup"><span data-stu-id="9e3c3-123">string</span></span> | <span data-ttu-id="9e3c3-124">Produkt oder Dienst, das die Warnungsinformationen bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="9e3c3-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="9e3c3-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9e3c3-125">string</span></span> | <span data-ttu-id="9e3c3-126">Erkennungstechnologie oder Sensor, die die wichtige Komponente oder Aktivität identifiziert hat</span><span class="sxs-lookup"><span data-stu-id="9e3c3-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="9e3c3-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9e3c3-127">string</span></span> | <span data-ttu-id="9e3c3-128">MITRE ATT&CK-Techniken, die der Aktivität zugeordnet sind, die die Warnung ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="9e3c3-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9e3c3-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9e3c3-129">Related topics</span></span>
- [<span data-ttu-id="9e3c3-130">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9e3c3-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e3c3-131">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="9e3c3-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e3c3-132">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="9e3c3-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e3c3-133">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="9e3c3-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e3c3-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="9e3c3-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e3c3-135">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="9e3c3-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
