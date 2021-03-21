---
title: AssignedIPAddresses()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie die AssignedIPAddresses()-Funktion verwenden, um die neuesten einem Gerät zugewiesenen IP-Adressen zu erhalten.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, FileProfile, Dateiprofil, Funktion, Bereicherung
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
ms.openlocfilehash: c52f7b8bf5a93a75b3330a3377f3fab34b8e7837
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922920"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="7f788-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="7f788-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7f788-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7f788-105">**Applies to:**</span></span>
- <span data-ttu-id="7f788-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f788-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7f788-107">Verwenden Sie `AssignedIPAddresses()` die Funktion in Ihren [erweiterten](advanced-hunting-overview.md) Suchabfragen, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="7f788-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="7f788-108">Wenn Sie ein Zeitstempelargument angeben, ruft diese Funktion die neuesten IP-Adressen zum angegebenen Zeitpunkt ab.</span><span class="sxs-lookup"><span data-stu-id="7f788-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="7f788-109">Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="7f788-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="7f788-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="7f788-110">Column</span></span> | <span data-ttu-id="7f788-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7f788-111">Data type</span></span> | <span data-ttu-id="7f788-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f788-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="7f788-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7f788-113">datetime</span></span> | <span data-ttu-id="7f788-114">Die letzte Zeit, zu der das Gerät mithilfe der IP-Adresse beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="7f788-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="7f788-115">string</span><span class="sxs-lookup"><span data-stu-id="7f788-115">string</span></span> | <span data-ttu-id="7f788-116">Vom Gerät verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="7f788-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="7f788-117">string</span><span class="sxs-lookup"><span data-stu-id="7f788-117">string</span></span> | <span data-ttu-id="7f788-118">Gibt an, ob es sich bei der IP-Adresse um eine öffentliche oder eine private Adresse handelt.</span><span class="sxs-lookup"><span data-stu-id="7f788-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="7f788-119">int</span><span class="sxs-lookup"><span data-stu-id="7f788-119">int</span></span> | <span data-ttu-id="7f788-120">Netzwerkadaptertyp, der vom Gerät verwendet wird, dem die IP-Adresse zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="7f788-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="7f788-121">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="7f788-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="7f788-122">int</span><span class="sxs-lookup"><span data-stu-id="7f788-122">int</span></span> | <span data-ttu-id="7f788-123">Netzwerke, mit denen der Adapter mit der zugewiesenen IP-Adresse verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7f788-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="7f788-124">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7f788-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="7f788-125">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f788-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="7f788-126">Argumente</span><span class="sxs-lookup"><span data-stu-id="7f788-126">Arguments</span></span>

- <span data-ttu-id="7f788-127">**x**– `DeviceId` oder `DeviceName` Wert, der das Gerät identifiziert</span><span class="sxs-lookup"><span data-stu-id="7f788-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="7f788-128">**y**– (datetime)-Wert, der die Funktion anweisen soll, die neuesten zugewiesenen IP-Adressen aus `Timestamp` einem bestimmten Zeitpunkt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7f788-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="7f788-129">Wenn nicht angegeben, gibt die Funktion die neuesten IP-Adressen zurück.</span><span class="sxs-lookup"><span data-stu-id="7f788-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="7f788-130">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7f788-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="7f788-131">Liste der vor 24 Stunden von einem Gerät verwendeten IP-Adressen erhalten</span><span class="sxs-lookup"><span data-stu-id="7f788-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="7f788-132">Get IP addresses used by a device and find devices communicating with it</span><span class="sxs-lookup"><span data-stu-id="7f788-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="7f788-133">Diese Abfrage verwendet die Funktion, um zugewiesene IP-Adressen für das Gerät ( ) an oder vor einem bestimmten Datum `AssignedIPAddresses()` `example-device-name` ( ) zu `example-date` erhalten.</span><span class="sxs-lookup"><span data-stu-id="7f788-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="7f788-134">Anschließend werden die IP-Adressen verwendet, um Verbindungen mit dem Gerät zu finden, die von anderen Geräten initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7f788-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="7f788-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7f788-135">Related topics</span></span>
- [<span data-ttu-id="7f788-136">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="7f788-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7f788-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7f788-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7f788-138">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7f788-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)