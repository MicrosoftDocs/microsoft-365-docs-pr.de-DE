---
title: DeviceNetworkInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1c8a3f3ab91add9e057c4661677997e658f42386
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063511"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="7fd7e-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="7fd7e-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7fd7e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7fd7e-105">**Applies to:**</span></span>
- <span data-ttu-id="7fd7e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fd7e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7fd7e-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP- und MAC-Adressen sowie verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7fd7e-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="7fd7e-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7fd7e-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7fd7e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7fd7e-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7fd7e-110">Column name</span></span> | <span data-ttu-id="7fd7e-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7fd7e-111">Data type</span></span> | <span data-ttu-id="7fd7e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fd7e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7fd7e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7fd7e-113">datetime</span></span> | <span data-ttu-id="7fd7e-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7fd7e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7fd7e-115">string</span><span class="sxs-lookup"><span data-stu-id="7fd7e-115">string</span></span> | <span data-ttu-id="7fd7e-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="7fd7e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7fd7e-117">string</span><span class="sxs-lookup"><span data-stu-id="7fd7e-117">string</span></span> | <span data-ttu-id="7fd7e-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="7fd7e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="7fd7e-119">long</span><span class="sxs-lookup"><span data-stu-id="7fd7e-119">long</span></span> | <span data-ttu-id="7fd7e-120">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7fd7e-121">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="7fd7e-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-122">string</span></span> | <span data-ttu-id="7fd7e-123">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="7fd7e-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="7fd7e-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-124">string</span></span> | <span data-ttu-id="7fd7e-125">MAC-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="7fd7e-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="7fd7e-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-126">string</span></span> | <span data-ttu-id="7fd7e-127">Netzwerkadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-127">Network adapter type.</span></span> <span data-ttu-id="7fd7e-128">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="7fd7e-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="7fd7e-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-129">string</span></span> | <span data-ttu-id="7fd7e-130">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-130">Operational status of the network adapter.</span></span> <span data-ttu-id="7fd7e-131">Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="7fd7e-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="7fd7e-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-132">string</span></span> | <span data-ttu-id="7fd7e-133">Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="7fd7e-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="7fd7e-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-134">string</span></span> | <span data-ttu-id="7fd7e-135">Netzwerke, mit der der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="7fd7e-136">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7fd7e-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="7fd7e-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-137">string</span></span> | <span data-ttu-id="7fd7e-138">DNS-Serveradressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="7fd7e-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="7fd7e-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-139">string</span></span> | <span data-ttu-id="7fd7e-140">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="7fd7e-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="7fd7e-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-141">string</span></span> | <span data-ttu-id="7fd7e-142">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="7fd7e-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="7fd7e-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-143">string</span></span> | <span data-ttu-id="7fd7e-144">Standardgatewayadressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="7fd7e-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="7fd7e-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7fd7e-145">string</span></span> | <span data-ttu-id="7fd7e-146">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link-lokal</span><span class="sxs-lookup"><span data-stu-id="7fd7e-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7fd7e-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7fd7e-147">Related topics</span></span>
- [<span data-ttu-id="7fd7e-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="7fd7e-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fd7e-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7fd7e-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7fd7e-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="7fd7e-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7fd7e-151">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="7fd7e-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7fd7e-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7fd7e-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7fd7e-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7fd7e-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)