---
title: AssignedIPAddresses ()-Funktion im Advanced Hunting for Microsoft Threat Protection
description: Erfahren Sie, wie Sie die AssignedIPAddresses ()-Funktion verwenden, um die neuesten IP-Adressen abzurufen, die einem Gerät zugewiesen sind.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Datei Profil, Datei Profil, Funktion, Bereicherung
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
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794231"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="0a0f5-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="0a0f5-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="0a0f5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0a0f5-105">**Applies to:**</span></span>
- <span data-ttu-id="0a0f5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0a0f5-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0a0f5-107">Verwenden Sie die- `AssignedIPAddresses()` Funktion, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät oder den neuesten IP-Adressen von einem bestimmten Zeitpunkt zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="0a0f5-108">Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="0a0f5-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="0a0f5-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="0a0f5-109">Column</span></span> | <span data-ttu-id="0a0f5-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0a0f5-110">Data type</span></span> | <span data-ttu-id="0a0f5-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a0f5-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="0a0f5-112">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="0a0f5-112">Timestamp</span></span> | <span data-ttu-id="0a0f5-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="0a0f5-113">datetime</span></span> | <span data-ttu-id="0a0f5-114">Spätester Zeitpunkt, zu dem das Gerät mit der IP-Adresse beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="0a0f5-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="0a0f5-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="0a0f5-115">IPAddress</span></span> | <span data-ttu-id="0a0f5-116">string</span><span class="sxs-lookup"><span data-stu-id="0a0f5-116">string</span></span> | <span data-ttu-id="0a0f5-117">Vom Gerät verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0a0f5-117">IP address used by the device</span></span> |
| <span data-ttu-id="0a0f5-118">IPType</span><span class="sxs-lookup"><span data-stu-id="0a0f5-118">IPType</span></span> | <span data-ttu-id="0a0f5-119">string</span><span class="sxs-lookup"><span data-stu-id="0a0f5-119">string</span></span> | <span data-ttu-id="0a0f5-120">Gibt an, ob es sich bei der IP-Adresse um eine öffentliche oder private Adresse handelt.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="0a0f5-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="0a0f5-121">NetworkAdapterType</span></span> | <span data-ttu-id="0a0f5-122">int</span><span class="sxs-lookup"><span data-stu-id="0a0f5-122">int</span></span> | <span data-ttu-id="0a0f5-123">Netzwerkadaptertyp, der von dem Gerät verwendet wird, dem die IP-Adresse zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="0a0f5-124">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="0a0f5-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="0a0f5-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="0a0f5-125">ConnectedNetworks</span></span> | <span data-ttu-id="0a0f5-126">int</span><span class="sxs-lookup"><span data-stu-id="0a0f5-126">int</span></span> | <span data-ttu-id="0a0f5-127">Netzwerke, mit denen der Adapter mit der zugewiesenen IP-Adresse verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="0a0f5-128">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="0a0f5-129">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a0f5-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="0a0f5-130">Argumente</span><span class="sxs-lookup"><span data-stu-id="0a0f5-130">Arguments</span></span>

- <span data-ttu-id="0a0f5-131">**x** – `DeviceId` oder `DeviceName` Wert, der das Gerät identifiziert</span><span class="sxs-lookup"><span data-stu-id="0a0f5-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="0a0f5-132">**y** – `Timestamp` (DateTime)-Wert, der den bestimmten Zeitpunkt angibt, an dem die neuesten IP-Adressen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="0a0f5-133">Wenn nicht angegeben, gibt die Funktion die neuesten IP-Adressen zurück.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="0a0f5-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0a0f5-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="0a0f5-135">Abrufen der Liste der IP-Adressen, die von einem Gerät seit 24 Stunden verwendet werden</span><span class="sxs-lookup"><span data-stu-id="0a0f5-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="0a0f5-136">Abrufen von von einem Gerät verwendeten IP-Adressen und Auffinden von Geräten, die mit dieser kommunizieren</span><span class="sxs-lookup"><span data-stu-id="0a0f5-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="0a0f5-137">Diese Abfrage verwendet die `AssignedIPAddresses()` -Funktion, um zugewiesene IP-Adressen für das Gerät ( `example-device-name` ) an oder vor einem bestimmten Datum ( `example-date` ) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="0a0f5-138">Anschließend werden die IP-Adressen verwendet, um Verbindungen mit dem Gerät zu finden, das von anderen Geräten initiiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0a0f5-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="0a0f5-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0a0f5-139">Related topics</span></span>
- [<span data-ttu-id="0a0f5-140">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="0a0f5-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0a0f5-141">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="0a0f5-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0a0f5-142">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="0a0f5-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)