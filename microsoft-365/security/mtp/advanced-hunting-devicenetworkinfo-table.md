---
title: Tabelle "DeviceNetworkInfo" im Schema "Erweiterte Suche"
description: Informationen zu Netzwerkkonfigurationsinformationen in der Tabelle "DeviceNetworkInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, machinenetworkinfo, DeviceNetworkInfo, Gerät, Computer, Mac, IP, Adapter, DNS, DHCP, Gateway, Tunnel
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931206"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="30c6a-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="30c6a-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="30c6a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="30c6a-105">**Applies to:**</span></span>
- <span data-ttu-id="30c6a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30c6a-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="30c6a-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP- und MAC-Adressen und verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="30c6a-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="30c6a-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="30c6a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="30c6a-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="30c6a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="30c6a-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="30c6a-110">Column name</span></span> | <span data-ttu-id="30c6a-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="30c6a-111">Data type</span></span> | <span data-ttu-id="30c6a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30c6a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="30c6a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="30c6a-113">datetime</span></span> | <span data-ttu-id="30c6a-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="30c6a-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="30c6a-115">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-115">string</span></span> | <span data-ttu-id="30c6a-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="30c6a-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="30c6a-117">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-117">string</span></span> | <span data-ttu-id="30c6a-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="30c6a-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="30c6a-119">long</span><span class="sxs-lookup"><span data-stu-id="30c6a-119">long</span></span> | <span data-ttu-id="30c6a-120">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="30c6a-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="30c6a-121">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30c6a-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="30c6a-122">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-122">string</span></span> | <span data-ttu-id="30c6a-123">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="30c6a-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="30c6a-124">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-124">string</span></span> | <span data-ttu-id="30c6a-125">DIE MAC-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="30c6a-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="30c6a-126">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-126">string</span></span> | <span data-ttu-id="30c6a-127">Netzwerkadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="30c6a-127">Network adapter type.</span></span> <span data-ttu-id="30c6a-128">Die möglichen Werte finden Sie in [dieser Enumeration.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="30c6a-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="30c6a-129">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-129">string</span></span> | <span data-ttu-id="30c6a-130">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="30c6a-130">Operational status of the network adapter.</span></span> <span data-ttu-id="30c6a-131">Die möglichen Werte finden Sie in [dieser Enumeration.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="30c6a-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="30c6a-132">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-132">string</span></span> | <span data-ttu-id="30c6a-133">Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="30c6a-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="30c6a-134">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-134">string</span></span> | <span data-ttu-id="30c6a-135">Netzwerke, mit der der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="30c6a-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="30c6a-136">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="30c6a-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="30c6a-137">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-137">string</span></span> | <span data-ttu-id="30c6a-138">DNS-Serveradressen im JSON-Array-Format</span><span class="sxs-lookup"><span data-stu-id="30c6a-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="30c6a-139">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-139">string</span></span> | <span data-ttu-id="30c6a-140">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="30c6a-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="30c6a-141">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-141">string</span></span> | <span data-ttu-id="30c6a-142">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="30c6a-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="30c6a-143">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-143">string</span></span> | <span data-ttu-id="30c6a-144">Standardgatewayadressen im JSON-Array-Format</span><span class="sxs-lookup"><span data-stu-id="30c6a-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="30c6a-145">string</span><span class="sxs-lookup"><span data-stu-id="30c6a-145">string</span></span> | <span data-ttu-id="30c6a-146">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link lokal</span><span class="sxs-lookup"><span data-stu-id="30c6a-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="30c6a-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30c6a-147">Related topics</span></span>
- [<span data-ttu-id="30c6a-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="30c6a-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="30c6a-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="30c6a-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="30c6a-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="30c6a-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="30c6a-151">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="30c6a-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="30c6a-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="30c6a-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="30c6a-153">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="30c6a-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
