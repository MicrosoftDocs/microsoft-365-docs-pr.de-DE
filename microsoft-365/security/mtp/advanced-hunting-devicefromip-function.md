---
title: DeviceFromIP()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie die DeviceFromIP()-Funktion verwenden, um die Geräte zu erhalten, denen eine bestimmte IP-Adresse zugewiesen wurde.
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Gerät, DevicefromIP, Funktion, Anreicherung
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931302"
---
# <a name="devicefromip"></a><span data-ttu-id="42375-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="42375-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="42375-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="42375-105">**Applies to:**</span></span>
- <span data-ttu-id="42375-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42375-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="42375-107">Verwenden Sie die Funktion in Ihren Abfragen für die erweiterte Suche, um schnell die Liste der Geräte zu erhalten, die zu einem bestimmten Zeitpunkt einer bestimmten `DeviceFromIP()` IP-Adresse [](advanced-hunting-overview.md) zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="42375-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="42375-108">Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="42375-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="42375-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="42375-109">Column</span></span> | <span data-ttu-id="42375-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="42375-110">Data type</span></span> | <span data-ttu-id="42375-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42375-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="42375-112">string</span><span class="sxs-lookup"><span data-stu-id="42375-112">string</span></span> | <span data-ttu-id="42375-113">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="42375-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="42375-114">string</span><span class="sxs-lookup"><span data-stu-id="42375-114">string</span></span> | <span data-ttu-id="42375-115">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="42375-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="42375-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="42375-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="42375-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="42375-117">Arguments</span></span>

<span data-ttu-id="42375-118">Diese Funktion wird als Teil einer Abfrage aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="42375-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="42375-119">**x**– Der erste Parameter ist in der Regel bereits eine Spalte in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="42375-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="42375-120">In diesem Fall handelt es sich um die Spalte namens "IP-Adresse", für die eine Liste der Geräte angezeigt werden soll, die ihr `IP` zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="42375-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="42375-121">Es sollte eine lokale IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="42375-121">It should be a local IP address.</span></span> <span data-ttu-id="42375-122">Externe IP-Adressen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42375-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="42375-123">**y**– Ein zweiter optionaler Parameter ist der , der die Funktion anweisen soll, die neuesten zugewiesenen Geräte aus einem `Timestamp` bestimmten Zeitpunkt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="42375-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="42375-124">Wenn nicht angegeben, gibt die Funktion die neuesten verfügbaren Datensätze zurück.</span><span class="sxs-lookup"><span data-stu-id="42375-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="42375-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42375-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="42375-126">Holen Sie sich die neuesten Geräte, denen bestimmte IP-Adressen zugewiesen wurden</span><span class="sxs-lookup"><span data-stu-id="42375-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="42375-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="42375-127">Related topics</span></span>
- [<span data-ttu-id="42375-128">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="42375-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42375-129">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="42375-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="42375-130">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="42375-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
