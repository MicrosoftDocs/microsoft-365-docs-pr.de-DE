---
title: DeviceFromIP()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie die DeviceFromIP()-Funktion verwenden, um die Geräte zu erhalten, denen eine bestimmte IP-Adresse zugewiesen wurde.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933181"
---
# <a name="devicefromip"></a><span data-ttu-id="80e62-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="80e62-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="80e62-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80e62-105">**Applies to:**</span></span>
- <span data-ttu-id="80e62-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80e62-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="80e62-107">Verwenden Sie `DeviceFromIP()` die Funktion in Ihren [erweiterten](advanced-hunting-overview.md) Suchabfragen, um schnell die Liste der Geräte zu erhalten, die zu einem bestimmten Zeitpunkt einer bestimmten IP-Adresse zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="80e62-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="80e62-108">Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="80e62-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="80e62-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="80e62-109">Column</span></span> | <span data-ttu-id="80e62-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="80e62-110">Data type</span></span> | <span data-ttu-id="80e62-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80e62-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="80e62-112">string</span><span class="sxs-lookup"><span data-stu-id="80e62-112">string</span></span> | <span data-ttu-id="80e62-113">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="80e62-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="80e62-114">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="80e62-114">string</span></span> | <span data-ttu-id="80e62-115">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="80e62-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="80e62-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="80e62-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="80e62-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="80e62-117">Arguments</span></span>

<span data-ttu-id="80e62-118">Diese Funktion wird als Teil einer Abfrage aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="80e62-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="80e62-119">**x**– Der erste Parameter ist in der Regel bereits eine Spalte in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="80e62-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="80e62-120">In diesem Fall ist es die Spalte namens , die IP-Adresse, für die Eine Liste der Geräte angezeigt werden soll, die `IP` ihr zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="80e62-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="80e62-121">Es sollte eine lokale IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="80e62-121">It should be a local IP address.</span></span> <span data-ttu-id="80e62-122">Externe IP-Adressen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80e62-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="80e62-123">**y**– Ein zweiter optionaler Parameter ist der , mit dem die Funktion angewiesen wird, die neuesten zugewiesenen Geräte aus einer `Timestamp` bestimmten Zeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="80e62-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="80e62-124">Wenn nicht angegeben, gibt die Funktion die neuesten verfügbaren Datensätze zurück.</span><span class="sxs-lookup"><span data-stu-id="80e62-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="80e62-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80e62-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="80e62-126">Holen Sie sich die neuesten Geräte, denen bestimmte IP-Adressen zugewiesen wurden</span><span class="sxs-lookup"><span data-stu-id="80e62-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="80e62-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80e62-127">Related topics</span></span>
- [<span data-ttu-id="80e62-128">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="80e62-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="80e62-129">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="80e62-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="80e62-130">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="80e62-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
