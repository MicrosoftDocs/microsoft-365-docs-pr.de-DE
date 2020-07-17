---
title: AlertInfo-Tabelle im Advanced Hunting-Schema
description: Informationen zu Warnungs Generierungs Ereignissen in der alertinfo-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, alertinfo, Warnung, Schweregrad, Kategorie, Gehrungs, ATT&ck, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS und Azure ATP
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
ms.openlocfilehash: a1290ee415073a9cb3948bc4b0cc6bb3ae13285b
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899017"
---
# <a name="alertinfo"></a><span data-ttu-id="8f827-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="8f827-104">AlertInfo</span></span>

<span data-ttu-id="8f827-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8f827-105">**Applies to:**</span></span>
- <span data-ttu-id="8f827-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f827-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="8f827-107">Die `AlertInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="8f827-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="8f827-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8f827-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8f827-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8f827-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8f827-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8f827-110">Column name</span></span> | <span data-ttu-id="8f827-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8f827-111">Data type</span></span> | <span data-ttu-id="8f827-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f827-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8f827-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8f827-113">datetime</span></span> | <span data-ttu-id="8f827-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="8f827-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="8f827-115">string</span><span class="sxs-lookup"><span data-stu-id="8f827-115">string</span></span> | <span data-ttu-id="8f827-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="8f827-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="8f827-117">string</span><span class="sxs-lookup"><span data-stu-id="8f827-117">string</span></span> | <span data-ttu-id="8f827-118">Titel der Warnung</span><span class="sxs-lookup"><span data-stu-id="8f827-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="8f827-119">string</span><span class="sxs-lookup"><span data-stu-id="8f827-119">string</span></span> | <span data-ttu-id="8f827-120">Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität</span><span class="sxs-lookup"><span data-stu-id="8f827-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="8f827-121">string</span><span class="sxs-lookup"><span data-stu-id="8f827-121">string</span></span> | <span data-ttu-id="8f827-122">Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an</span><span class="sxs-lookup"><span data-stu-id="8f827-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="8f827-123">string</span><span class="sxs-lookup"><span data-stu-id="8f827-123">string</span></span> | <span data-ttu-id="8f827-124">Produkt oder Dienst, der die Warnungsinformationen bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="8f827-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="8f827-125">string</span><span class="sxs-lookup"><span data-stu-id="8f827-125">string</span></span> | <span data-ttu-id="8f827-126">Erkennungstechnologie oder Sensor, der die wichtige Komponente oder Aktivität identifiziert hat</span><span class="sxs-lookup"><span data-stu-id="8f827-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="8f827-127">string</span><span class="sxs-lookup"><span data-stu-id="8f827-127">string</span></span> | <span data-ttu-id="8f827-128">Gehrungs ATT&ck Techniques, die mit der Aktivität verbunden sind, die die Warnung ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="8f827-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8f827-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8f827-129">Related topics</span></span>
- [<span data-ttu-id="8f827-130">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="8f827-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8f827-131">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="8f827-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8f827-132">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="8f827-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8f827-133">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="8f827-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8f827-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="8f827-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8f827-135">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="8f827-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
