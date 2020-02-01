---
title: DeviceNetworkInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über die Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, machinenetworkinfo, DeviceNetworkInfo, Gerät, Computer, Mac, IP, Adapter, DNS, DHCP, Gateway, Tunnel
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
ms.openlocfilehash: 25349328cd128113de7846cba5c7c9ad74631092
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600412"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="8e521-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="8e521-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="8e521-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8e521-105">**Applies to:**</span></span>
- <span data-ttu-id="8e521-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8e521-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8e521-107">Die `DeviceNetworkInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP-und Mac-Adressen und verbundenen Netzwerken oder Domänen.</span><span class="sxs-lookup"><span data-stu-id="8e521-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="8e521-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8e521-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8e521-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8e521-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8e521-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8e521-110">Column name</span></span> | <span data-ttu-id="8e521-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8e521-111">Data type</span></span> | <span data-ttu-id="8e521-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e521-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8e521-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8e521-113">datetime</span></span> | <span data-ttu-id="8e521-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="8e521-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8e521-115">string</span><span class="sxs-lookup"><span data-stu-id="8e521-115">string</span></span> | <span data-ttu-id="8e521-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="8e521-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8e521-117">string</span><span class="sxs-lookup"><span data-stu-id="8e521-117">string</span></span> | <span data-ttu-id="8e521-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="8e521-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="8e521-119">long</span><span class="sxs-lookup"><span data-stu-id="8e521-119">long</span></span> | <span data-ttu-id="8e521-120">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="8e521-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8e521-121">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e521-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="8e521-122">string</span><span class="sxs-lookup"><span data-stu-id="8e521-122">string</span></span> | <span data-ttu-id="8e521-123">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="8e521-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="8e521-124">string</span><span class="sxs-lookup"><span data-stu-id="8e521-124">string</span></span> | <span data-ttu-id="8e521-125">Mac-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="8e521-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="8e521-126">string</span><span class="sxs-lookup"><span data-stu-id="8e521-126">string</span></span> | <span data-ttu-id="8e521-127">Typ des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="8e521-127">Network adapter type.</span></span> <span data-ttu-id="8e521-128">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="8e521-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="8e521-129">string</span><span class="sxs-lookup"><span data-stu-id="8e521-129">string</span></span> | <span data-ttu-id="8e521-130">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="8e521-130">Operational status of the network adapter.</span></span> <span data-ttu-id="8e521-131">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="8e521-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="8e521-132">string</span><span class="sxs-lookup"><span data-stu-id="8e521-132">string</span></span> | <span data-ttu-id="8e521-133">Tunneling-Protokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, beispielsweise 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="8e521-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="8e521-134">string</span><span class="sxs-lookup"><span data-stu-id="8e521-134">string</span></span> | <span data-ttu-id="8e521-135">Netzwerke, mit denen der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="8e521-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="8e521-136">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="8e521-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="8e521-137">string</span><span class="sxs-lookup"><span data-stu-id="8e521-137">string</span></span> | <span data-ttu-id="8e521-138">DNS-Serveradressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="8e521-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="8e521-139">string</span><span class="sxs-lookup"><span data-stu-id="8e521-139">string</span></span> | <span data-ttu-id="8e521-140">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="8e521-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="8e521-141">string</span><span class="sxs-lookup"><span data-stu-id="8e521-141">string</span></span> | <span data-ttu-id="8e521-142">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="8e521-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="8e521-143">string</span><span class="sxs-lookup"><span data-stu-id="8e521-143">string</span></span> | <span data-ttu-id="8e521-144">Standardgateway-Adressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="8e521-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="8e521-145">string</span><span class="sxs-lookup"><span data-stu-id="8e521-145">string</span></span> | <span data-ttu-id="8e521-146">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen zusammen mit dem jeweiligen Subnetz-Präfix und dem IP-Adressraum enthält, beispielsweise Public, private oder Link-Local</span><span class="sxs-lookup"><span data-stu-id="8e521-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8e521-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8e521-147">Related topics</span></span>
- [<span data-ttu-id="8e521-148">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="8e521-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8e521-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="8e521-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8e521-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="8e521-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8e521-151">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="8e521-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8e521-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="8e521-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8e521-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="8e521-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
