---
title: DeviceFromIP ()-Funktion in Advanced Hunting for Microsoft 365 Defender
description: Erfahren Sie, wie Sie die DeviceFromIP ()-Funktion verwenden, um die Geräte abzurufen, denen eine bestimmte IP-Adresse zugewiesen wurde.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Gerät, devicefromIP, Funktion, Anreicherung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741108"
---
# <a name="devicefromip"></a><span data-ttu-id="0238b-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="0238b-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0238b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0238b-105">**Applies to:**</span></span>
- <span data-ttu-id="0238b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0238b-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="0238b-107">Verwenden Sie die `DeviceFromIP()` -Funktion in Ihren [erweiterten Jagd](advanced-hunting-overview.md) Abfragen, um schnell eine Liste der Geräte zu erhalten, die zu einem bestimmten Zeitpunkt einer bestimmten IP-Adresse zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="0238b-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="0238b-108">Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="0238b-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="0238b-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="0238b-109">Column</span></span> | <span data-ttu-id="0238b-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0238b-110">Data type</span></span> | <span data-ttu-id="0238b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0238b-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="0238b-112">string</span><span class="sxs-lookup"><span data-stu-id="0238b-112">string</span></span> | <span data-ttu-id="0238b-113">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0238b-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="0238b-114">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0238b-114">string</span></span> | <span data-ttu-id="0238b-115">Eindeutiger Bezeichner für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="0238b-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="0238b-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="0238b-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="0238b-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="0238b-117">Arguments</span></span>

<span data-ttu-id="0238b-118">Diese Funktion wird als Teil einer Abfrage aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0238b-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="0238b-119">**x**– der erste Parameter ist normalerweise bereits eine Spalte in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="0238b-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="0238b-120">In diesem Fall ist dies die Spalte mit dem Namen `IP` , die IP-Adresse, für die Sie eine Liste der Geräte anzeigen möchten, die ihr zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="0238b-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="0238b-121">Es sollte sich um eine lokale IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="0238b-121">It should be a local IP address.</span></span> <span data-ttu-id="0238b-122">Externe IP-Adressen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0238b-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="0238b-123">**y**– ein zweiter optionaler Parameter ist der `Timestamp` , der die Funktion anweist, die zuletzt zugewiesenen Geräte aus einem bestimmten Zeitpunkt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0238b-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="0238b-124">Wenn nicht angegeben, gibt die Funktion die neuesten verfügbaren Datensätze zurück.</span><span class="sxs-lookup"><span data-stu-id="0238b-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="0238b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0238b-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="0238b-126">Abrufen der neuesten Geräte, denen bestimmte IP-Adressen zugewiesen wurden</span><span class="sxs-lookup"><span data-stu-id="0238b-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="0238b-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0238b-127">Related topics</span></span>
- [<span data-ttu-id="0238b-128">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="0238b-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0238b-129">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="0238b-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0238b-130">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="0238b-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
