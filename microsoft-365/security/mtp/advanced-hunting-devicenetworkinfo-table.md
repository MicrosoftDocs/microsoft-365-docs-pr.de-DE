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
ms.openlocfilehash: 141d2589c5e3c5d8746ba58de01dd63ef0f0c576
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649367"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="888f4-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="888f4-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="888f4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="888f4-105">**Applies to:**</span></span>
- <span data-ttu-id="888f4-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="888f4-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="888f4-107">Die `DeviceNetworkInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP-und Mac-Adressen und verbundenen Netzwerken oder Domänen.</span><span class="sxs-lookup"><span data-stu-id="888f4-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="888f4-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="888f4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="888f4-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="888f4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="888f4-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="888f4-110">Column name</span></span> | <span data-ttu-id="888f4-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="888f4-111">Data type</span></span> | <span data-ttu-id="888f4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="888f4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="888f4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="888f4-113">datetime</span></span> | <span data-ttu-id="888f4-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="888f4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="888f4-115">string</span><span class="sxs-lookup"><span data-stu-id="888f4-115">string</span></span> | <span data-ttu-id="888f4-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="888f4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="888f4-117">string</span><span class="sxs-lookup"><span data-stu-id="888f4-117">string</span></span> | <span data-ttu-id="888f4-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="888f4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="888f4-119">long</span><span class="sxs-lookup"><span data-stu-id="888f4-119">long</span></span> | <span data-ttu-id="888f4-120">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="888f4-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="888f4-121">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="888f4-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="888f4-122">string</span><span class="sxs-lookup"><span data-stu-id="888f4-122">string</span></span> | <span data-ttu-id="888f4-123">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="888f4-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="888f4-124">string</span><span class="sxs-lookup"><span data-stu-id="888f4-124">string</span></span> | <span data-ttu-id="888f4-125">Mac-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="888f4-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="888f4-126">string</span><span class="sxs-lookup"><span data-stu-id="888f4-126">string</span></span> | <span data-ttu-id="888f4-127">Typ des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="888f4-127">Network adapter type.</span></span> <span data-ttu-id="888f4-128">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="888f4-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="888f4-129">string</span><span class="sxs-lookup"><span data-stu-id="888f4-129">string</span></span> | <span data-ttu-id="888f4-130">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="888f4-130">Operational status of the network adapter.</span></span> <span data-ttu-id="888f4-131">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="888f4-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="888f4-132">string</span><span class="sxs-lookup"><span data-stu-id="888f4-132">string</span></span> | <span data-ttu-id="888f4-133">Tunneling-Protokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, beispielsweise 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="888f4-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="888f4-134">string</span><span class="sxs-lookup"><span data-stu-id="888f4-134">string</span></span> | <span data-ttu-id="888f4-135">Netzwerke, mit denen der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="888f4-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="888f4-136">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="888f4-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="888f4-137">string</span><span class="sxs-lookup"><span data-stu-id="888f4-137">string</span></span> | <span data-ttu-id="888f4-138">DNS-Serveradressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="888f4-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="888f4-139">string</span><span class="sxs-lookup"><span data-stu-id="888f4-139">string</span></span> | <span data-ttu-id="888f4-140">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="888f4-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="888f4-141">string</span><span class="sxs-lookup"><span data-stu-id="888f4-141">string</span></span> | <span data-ttu-id="888f4-142">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="888f4-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="888f4-143">string</span><span class="sxs-lookup"><span data-stu-id="888f4-143">string</span></span> | <span data-ttu-id="888f4-144">Standardgateway-Adressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="888f4-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="888f4-145">string</span><span class="sxs-lookup"><span data-stu-id="888f4-145">string</span></span> | <span data-ttu-id="888f4-146">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen zusammen mit dem jeweiligen Subnetz-Präfix und dem IP-Adressraum enthält, beispielsweise Public, private oder Link-Local</span><span class="sxs-lookup"><span data-stu-id="888f4-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="888f4-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="888f4-147">Related topics</span></span>
- [<span data-ttu-id="888f4-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="888f4-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="888f4-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="888f4-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="888f4-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="888f4-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="888f4-151">Jagd auf Geräte, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="888f4-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="888f4-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="888f4-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="888f4-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="888f4-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
