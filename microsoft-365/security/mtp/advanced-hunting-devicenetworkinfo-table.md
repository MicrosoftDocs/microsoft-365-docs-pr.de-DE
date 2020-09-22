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
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197073"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="be13d-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="be13d-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be13d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="be13d-105">**Applies to:**</span></span>
- <span data-ttu-id="be13d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="be13d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="be13d-107">Die `DeviceNetworkInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP-und Mac-Adressen und verbundenen Netzwerken oder Domänen.</span><span class="sxs-lookup"><span data-stu-id="be13d-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="be13d-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="be13d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="be13d-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="be13d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="be13d-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="be13d-110">Column name</span></span> | <span data-ttu-id="be13d-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="be13d-111">Data type</span></span> | <span data-ttu-id="be13d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be13d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="be13d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="be13d-113">datetime</span></span> | <span data-ttu-id="be13d-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="be13d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="be13d-115">string</span><span class="sxs-lookup"><span data-stu-id="be13d-115">string</span></span> | <span data-ttu-id="be13d-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="be13d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="be13d-117">string</span><span class="sxs-lookup"><span data-stu-id="be13d-117">string</span></span> | <span data-ttu-id="be13d-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="be13d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="be13d-119">long</span><span class="sxs-lookup"><span data-stu-id="be13d-119">long</span></span> | <span data-ttu-id="be13d-120">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="be13d-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="be13d-121">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be13d-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="be13d-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-122">string</span></span> | <span data-ttu-id="be13d-123">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="be13d-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="be13d-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-124">string</span></span> | <span data-ttu-id="be13d-125">Mac-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="be13d-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="be13d-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-126">string</span></span> | <span data-ttu-id="be13d-127">Typ des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="be13d-127">Network adapter type.</span></span> <span data-ttu-id="be13d-128">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="be13d-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="be13d-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-129">string</span></span> | <span data-ttu-id="be13d-130">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="be13d-130">Operational status of the network adapter.</span></span> <span data-ttu-id="be13d-131">Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="be13d-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="be13d-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-132">string</span></span> | <span data-ttu-id="be13d-133">Tunneling-Protokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, beispielsweise 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="be13d-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="be13d-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-134">string</span></span> | <span data-ttu-id="be13d-135">Netzwerke, mit denen der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="be13d-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="be13d-136">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="be13d-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="be13d-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-137">string</span></span> | <span data-ttu-id="be13d-138">DNS-Serveradressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="be13d-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="be13d-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-139">string</span></span> | <span data-ttu-id="be13d-140">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="be13d-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="be13d-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-141">string</span></span> | <span data-ttu-id="be13d-142">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="be13d-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="be13d-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-143">string</span></span> | <span data-ttu-id="be13d-144">Standardgateway-Adressen im JSON-Array Format</span><span class="sxs-lookup"><span data-stu-id="be13d-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="be13d-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="be13d-145">string</span></span> | <span data-ttu-id="be13d-146">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen zusammen mit dem jeweiligen Subnetz-Präfix und dem IP-Adressraum enthält, beispielsweise Public, private oder Link-Local</span><span class="sxs-lookup"><span data-stu-id="be13d-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be13d-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="be13d-147">Related topics</span></span>
- [<span data-ttu-id="be13d-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="be13d-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be13d-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="be13d-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be13d-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="be13d-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be13d-151">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="be13d-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be13d-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="be13d-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be13d-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="be13d-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
