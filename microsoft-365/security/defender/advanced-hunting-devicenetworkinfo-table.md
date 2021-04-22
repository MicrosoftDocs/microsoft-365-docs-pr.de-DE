---
title: DeviceNetworkInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: e6bfb781b3454025c5ce0f43899180c91761a56d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932559"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="0a8e4-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="0a8e4-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0a8e4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0a8e4-105">**Applies to:**</span></span>
- <span data-ttu-id="0a8e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a8e4-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="0a8e4-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP- und MAC-Adressen sowie verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0a8e4-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="0a8e4-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0a8e4-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0a8e4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0a8e4-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0a8e4-110">Column name</span></span> | <span data-ttu-id="0a8e4-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0a8e4-111">Data type</span></span> | <span data-ttu-id="0a8e4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a8e4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0a8e4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0a8e4-113">datetime</span></span> | <span data-ttu-id="0a8e4-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="0a8e4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0a8e4-115">string</span><span class="sxs-lookup"><span data-stu-id="0a8e4-115">string</span></span> | <span data-ttu-id="0a8e4-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="0a8e4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0a8e4-117">string</span><span class="sxs-lookup"><span data-stu-id="0a8e4-117">string</span></span> | <span data-ttu-id="0a8e4-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="0a8e4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="0a8e4-119">string</span><span class="sxs-lookup"><span data-stu-id="0a8e4-119">string</span></span> | <span data-ttu-id="0a8e4-120">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="0a8e4-120">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="0a8e4-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-121">string</span></span> | <span data-ttu-id="0a8e4-122">MAC-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="0a8e4-122">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="0a8e4-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-123">string</span></span> | <span data-ttu-id="0a8e4-124">Netzwerkadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-124">Network adapter type.</span></span> <span data-ttu-id="0a8e4-125">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="0a8e4-125">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="0a8e4-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-126">string</span></span> | <span data-ttu-id="0a8e4-127">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-127">Operational status of the network adapter.</span></span> <span data-ttu-id="0a8e4-128">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="0a8e4-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="0a8e4-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-129">string</span></span> | <span data-ttu-id="0a8e4-130">Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="0a8e4-130">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="0a8e4-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-131">string</span></span> | <span data-ttu-id="0a8e4-132">Netzwerke, mit der der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-132">Networks that the adapter is connected to.</span></span> <span data-ttu-id="0a8e4-133">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-133">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="0a8e4-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-134">string</span></span> | <span data-ttu-id="0a8e4-135">DNS-Serveradressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="0a8e4-135">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="0a8e4-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-136">string</span></span> | <span data-ttu-id="0a8e4-137">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="0a8e4-137">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="0a8e4-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-138">string</span></span> | <span data-ttu-id="0a8e4-139">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="0a8e4-139">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="0a8e4-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-140">string</span></span> | <span data-ttu-id="0a8e4-141">Standardgatewayadressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="0a8e4-141">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="0a8e4-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a8e4-142">string</span></span> | <span data-ttu-id="0a8e4-143">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link-lokal</span><span class="sxs-lookup"><span data-stu-id="0a8e4-143">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="0a8e4-144">long</span><span class="sxs-lookup"><span data-stu-id="0a8e4-144">long</span></span> | <span data-ttu-id="0a8e4-145">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0a8e4-146">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a8e4-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0a8e4-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0a8e4-147">Related topics</span></span>
- [<span data-ttu-id="0a8e4-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="0a8e4-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0a8e4-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="0a8e4-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0a8e4-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="0a8e4-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0a8e4-151">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="0a8e4-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0a8e4-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="0a8e4-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0a8e4-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="0a8e4-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)