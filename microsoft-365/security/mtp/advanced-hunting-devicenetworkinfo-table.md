---
title: DeviceNetworkInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über die Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Jagd, Bedrohungs Jagd, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, machinenetworkinfo, DeviceNetworkInfo, Gerät, Computer, Mac, IP, Adapter, DNS, DHCP, Gateway, Tunnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e0d183dd762aba7f11ee46acc81a89b453dc70cb
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809305"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="652a1-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="652a1-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="652a1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="652a1-105">**Applies to:**</span></span>
- <span data-ttu-id="652a1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="652a1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="652a1-107">Die `DeviceNetworkInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP-und Mac-Adressen und verbundenen Netzwerken oder Domänen.</span><span class="sxs-lookup"><span data-stu-id="652a1-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="652a1-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="652a1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="652a1-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="652a1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="652a1-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="652a1-110">Column name</span></span> | <span data-ttu-id="652a1-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="652a1-111">Data type</span></span> | <span data-ttu-id="652a1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="652a1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="652a1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="652a1-113">datetime</span></span> | <span data-ttu-id="652a1-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="652a1-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="652a1-115">string</span><span class="sxs-lookup"><span data-stu-id="652a1-115">string</span></span> | <span data-ttu-id="652a1-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="652a1-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="652a1-117">string</span><span class="sxs-lookup"><span data-stu-id="652a1-117">string</span></span> | <span data-ttu-id="652a1-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="652a1-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="652a1-119">long</span><span class="sxs-lookup"><span data-stu-id="652a1-119">long</span></span> | <span data-ttu-id="652a1-120">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="652a1-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="652a1-121">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="652a1-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="652a1-122">string</span><span class="sxs-lookup"><span data-stu-id="652a1-122">string</span></span> | <span data-ttu-id="652a1-123">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="652a1-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="652a1-124">string</span><span class="sxs-lookup"><span data-stu-id="652a1-124">string</span></span> | <span data-ttu-id="652a1-125">Mac-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="652a1-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="652a1-126">string</span><span class="sxs-lookup"><span data-stu-id="652a1-126">string</span></span> | <span data-ttu-id="652a1-127">Typ des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="652a1-127">Network adapter type.</span></span> <span data-ttu-id="652a1-128">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="652a1-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="652a1-129">string</span><span class="sxs-lookup"><span data-stu-id="652a1-129">string</span></span> | <span data-ttu-id="652a1-130">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="652a1-130">Operational status of the network adapter.</span></span> <span data-ttu-id="652a1-131">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="652a1-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="652a1-132">string</span><span class="sxs-lookup"><span data-stu-id="652a1-132">string</span></span> | <span data-ttu-id="652a1-133">Tunneling-Protokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, beispielsweise 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="652a1-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="652a1-134">string</span><span class="sxs-lookup"><span data-stu-id="652a1-134">string</span></span> | <span data-ttu-id="652a1-135">Netzwerke, mit denen der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="652a1-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="652a1-136">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="652a1-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="652a1-137">string</span><span class="sxs-lookup"><span data-stu-id="652a1-137">string</span></span> | <span data-ttu-id="652a1-138">DNS-Serveradressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="652a1-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="652a1-139">string</span><span class="sxs-lookup"><span data-stu-id="652a1-139">string</span></span> | <span data-ttu-id="652a1-140">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="652a1-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="652a1-141">string</span><span class="sxs-lookup"><span data-stu-id="652a1-141">string</span></span> | <span data-ttu-id="652a1-142">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="652a1-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="652a1-143">string</span><span class="sxs-lookup"><span data-stu-id="652a1-143">string</span></span> | <span data-ttu-id="652a1-144">Standardgateway-Adressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="652a1-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="652a1-145">string</span><span class="sxs-lookup"><span data-stu-id="652a1-145">string</span></span> | <span data-ttu-id="652a1-146">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen zusammen mit dem jeweiligen Subnetz-Präfix und dem IP-Adressraum enthält, beispielsweise Public, private oder Link-Local</span><span class="sxs-lookup"><span data-stu-id="652a1-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="652a1-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="652a1-147">Related topics</span></span>
- [<span data-ttu-id="652a1-148">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="652a1-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="652a1-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="652a1-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="652a1-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="652a1-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="652a1-151">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="652a1-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="652a1-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="652a1-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="652a1-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="652a1-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
