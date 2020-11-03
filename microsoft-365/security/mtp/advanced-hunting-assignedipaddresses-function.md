---
title: AssignedIPAddresses ()-Funktion in Advanced Hunting for Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: cb9dffca148c95f284a6a7e920f3a08a839b748d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847644"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="ac924-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="ac924-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ac924-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ac924-105">**Applies to:**</span></span>
- <span data-ttu-id="ac924-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac924-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ac924-107">Verwenden Sie die `AssignedIPAddresses()` -Funktion in Ihren [erweiterten](advanced-hunting-overview.md) Suchabfragen, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="ac924-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="ac924-108">Wenn Sie ein Timestamp-Argument angeben, ruft diese Funktion die neuesten IP-Adressen zur angegebenen Zeit ab.</span><span class="sxs-lookup"><span data-stu-id="ac924-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="ac924-109">Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="ac924-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="ac924-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="ac924-110">Column</span></span> | <span data-ttu-id="ac924-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ac924-111">Data type</span></span> | <span data-ttu-id="ac924-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac924-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="ac924-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ac924-113">datetime</span></span> | <span data-ttu-id="ac924-114">Spätester Zeitpunkt, zu dem das Gerät mit der IP-Adresse beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="ac924-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="ac924-115">string</span><span class="sxs-lookup"><span data-stu-id="ac924-115">string</span></span> | <span data-ttu-id="ac924-116">Vom Gerät verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ac924-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="ac924-117">string</span><span class="sxs-lookup"><span data-stu-id="ac924-117">string</span></span> | <span data-ttu-id="ac924-118">Gibt an, ob es sich bei der IP-Adresse um eine öffentliche oder private Adresse handelt.</span><span class="sxs-lookup"><span data-stu-id="ac924-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="ac924-119">int</span><span class="sxs-lookup"><span data-stu-id="ac924-119">int</span></span> | <span data-ttu-id="ac924-120">Netzwerkadaptertyp, der von dem Gerät verwendet wird, dem die IP-Adresse zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ac924-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="ac924-121">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="ac924-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="ac924-122">int</span><span class="sxs-lookup"><span data-stu-id="ac924-122">int</span></span> | <span data-ttu-id="ac924-123">Netzwerke, mit denen der Adapter mit der zugewiesenen IP-Adresse verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="ac924-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="ac924-124">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="ac924-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="ac924-125">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac924-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="ac924-126">Argumente</span><span class="sxs-lookup"><span data-stu-id="ac924-126">Arguments</span></span>

- <span data-ttu-id="ac924-127">**x** – `DeviceId` oder `DeviceName` Wert, der das Gerät identifiziert</span><span class="sxs-lookup"><span data-stu-id="ac924-127">**x** —`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="ac924-128">**y** – `Timestamp` (DateTime)-Wert, in dem die Funktion angewiesen wird, die aktuellsten zugewiesenen IP-Adressen von einem bestimmten Zeitpunkt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ac924-128">**y** —`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="ac924-129">Wenn nicht angegeben, gibt die Funktion die neuesten IP-Adressen zurück.</span><span class="sxs-lookup"><span data-stu-id="ac924-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="ac924-130">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ac924-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="ac924-131">Abrufen der Liste der IP-Adressen, die von einem Gerät verwendet werden vor 24 Stunden</span><span class="sxs-lookup"><span data-stu-id="ac924-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="ac924-132">Abrufen von von einem Gerät verwendeten IP-Adressen und Auffinden von Geräten, die mit dieser kommunizieren</span><span class="sxs-lookup"><span data-stu-id="ac924-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="ac924-133">Diese Abfrage verwendet die `AssignedIPAddresses()` -Funktion, um zugewiesene IP-Adressen für das Gerät ( `example-device-name` ) an oder vor einem bestimmten Datum ( `example-date` ) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ac924-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="ac924-134">Anschließend werden die IP-Adressen verwendet, um Verbindungen mit dem Gerät zu finden, das von anderen Geräten initiiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ac924-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="ac924-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ac924-135">Related topics</span></span>
- [<span data-ttu-id="ac924-136">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ac924-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ac924-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="ac924-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ac924-138">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="ac924-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
