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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023189"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="d9d65-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="d9d65-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d9d65-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d9d65-105">**Applies to:**</span></span>
- <span data-ttu-id="d9d65-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9d65-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d9d65-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d9d65-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="d9d65-108">Die Tabelle im Schema der erweiterten Suche enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP- und MAC-Adressen sowie verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d9d65-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="d9d65-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d9d65-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="d9d65-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d9d65-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d9d65-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d9d65-111">Column name</span></span> | <span data-ttu-id="d9d65-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d9d65-112">Data type</span></span> | <span data-ttu-id="d9d65-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9d65-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d9d65-114">datetime</span><span class="sxs-lookup"><span data-stu-id="d9d65-114">datetime</span></span> | <span data-ttu-id="d9d65-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="d9d65-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d9d65-116">string</span><span class="sxs-lookup"><span data-stu-id="d9d65-116">string</span></span> | <span data-ttu-id="d9d65-117">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="d9d65-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d9d65-118">string</span><span class="sxs-lookup"><span data-stu-id="d9d65-118">string</span></span> | <span data-ttu-id="d9d65-119">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="d9d65-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="d9d65-120">string</span><span class="sxs-lookup"><span data-stu-id="d9d65-120">string</span></span> | <span data-ttu-id="d9d65-121">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="d9d65-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="d9d65-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-122">string</span></span> | <span data-ttu-id="d9d65-123">MAC-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="d9d65-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="d9d65-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-124">string</span></span> | <span data-ttu-id="d9d65-125">Netzwerkadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="d9d65-125">Network adapter type.</span></span> <span data-ttu-id="d9d65-126">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="d9d65-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="d9d65-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-127">string</span></span> | <span data-ttu-id="d9d65-128">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="d9d65-128">Operational status of the network adapter.</span></span> <span data-ttu-id="d9d65-129">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="d9d65-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="d9d65-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-130">string</span></span> | <span data-ttu-id="d9d65-131">Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="d9d65-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="d9d65-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-132">string</span></span> | <span data-ttu-id="d9d65-133">Netzwerke, mit der der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d9d65-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="d9d65-134">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d9d65-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="d9d65-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-135">string</span></span> | <span data-ttu-id="d9d65-136">DNS-Serveradressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="d9d65-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="d9d65-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-137">string</span></span> | <span data-ttu-id="d9d65-138">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="d9d65-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="d9d65-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-139">string</span></span> | <span data-ttu-id="d9d65-140">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="d9d65-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="d9d65-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-141">string</span></span> | <span data-ttu-id="d9d65-142">Standardgatewayadressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="d9d65-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="d9d65-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d9d65-143">string</span></span> | <span data-ttu-id="d9d65-144">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link-lokal</span><span class="sxs-lookup"><span data-stu-id="d9d65-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="d9d65-145">long</span><span class="sxs-lookup"><span data-stu-id="d9d65-145">long</span></span> | <span data-ttu-id="d9d65-146">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="d9d65-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d9d65-147">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9d65-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d9d65-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d9d65-148">Related topics</span></span>
- [<span data-ttu-id="d9d65-149">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="d9d65-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d9d65-150">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d9d65-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d9d65-151">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="d9d65-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d9d65-152">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="d9d65-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d9d65-153">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d9d65-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d9d65-154">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d9d65-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)