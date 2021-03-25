---
title: DeviceNetworkInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicenetworkinfo, device, device, mac, ip, adapter, dns, dhcp, gateway, tunnel, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067055"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="f4a01-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="f4a01-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4a01-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f4a01-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4a01-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f4a01-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f4a01-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f4a01-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f4a01-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f4a01-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="f4a01-109">Die Tabelle im Schema der erweiterten Suche enthält Informationen zur Netzwerkkonfiguration von Geräten, einschließlich Netzwerkadaptern, IP- und MAC-Adressen sowie verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f4a01-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="f4a01-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f4a01-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f4a01-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="f4a01-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="f4a01-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f4a01-112">Column name</span></span> | <span data-ttu-id="f4a01-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f4a01-113">Data type</span></span> | <span data-ttu-id="f4a01-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4a01-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f4a01-115">datetime</span><span class="sxs-lookup"><span data-stu-id="f4a01-115">datetime</span></span> | <span data-ttu-id="f4a01-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="f4a01-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f4a01-117">string</span><span class="sxs-lookup"><span data-stu-id="f4a01-117">string</span></span> | <span data-ttu-id="f4a01-118">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="f4a01-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f4a01-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-119">string</span></span> | <span data-ttu-id="f4a01-120">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="f4a01-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="f4a01-121">long</span><span class="sxs-lookup"><span data-stu-id="f4a01-121">long</span></span> | <span data-ttu-id="f4a01-122">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="f4a01-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f4a01-123">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden.</span><span class="sxs-lookup"><span data-stu-id="f4a01-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="f4a01-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-124">string</span></span> | <span data-ttu-id="f4a01-125">Name des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="f4a01-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="f4a01-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-126">string</span></span> | <span data-ttu-id="f4a01-127">MAC-Adresse des Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="f4a01-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f4a01-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-128">string</span></span> | <span data-ttu-id="f4a01-129">Netzwerkadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="f4a01-129">Network adapter type.</span></span> <span data-ttu-id="f4a01-130">Mögliche Werte finden Sie in [dieser Enumeration.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="f4a01-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="f4a01-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-131">string</span></span> | <span data-ttu-id="f4a01-132">Betriebsstatus des Netzwerkadapters.</span><span class="sxs-lookup"><span data-stu-id="f4a01-132">Operational status of the network adapter.</span></span> <span data-ttu-id="f4a01-133">Mögliche Werte finden Sie in [dieser Enumeration.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="f4a01-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="f4a01-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-134">string</span></span> | <span data-ttu-id="f4a01-135">Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH</span><span class="sxs-lookup"><span data-stu-id="f4a01-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f4a01-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-136">string</span></span> | <span data-ttu-id="f4a01-137">Netzwerke, mit der der Adapter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f4a01-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="f4a01-138">Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f4a01-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="f4a01-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-139">string</span></span> | <span data-ttu-id="f4a01-140">DNS-Serveradressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="f4a01-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="f4a01-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-141">string</span></span> | <span data-ttu-id="f4a01-142">IPv4-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="f4a01-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="f4a01-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-143">string</span></span> | <span data-ttu-id="f4a01-144">IPv6-Adresse des DHCP-Servers</span><span class="sxs-lookup"><span data-stu-id="f4a01-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="f4a01-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-145">string</span></span> | <span data-ttu-id="f4a01-146">Standardgatewayadressen im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="f4a01-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="f4a01-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4a01-147">string</span></span> | <span data-ttu-id="f4a01-148">JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link-lokal</span><span class="sxs-lookup"><span data-stu-id="f4a01-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f4a01-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f4a01-149">Related topics</span></span>
- [<span data-ttu-id="f4a01-150">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f4a01-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f4a01-151">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="f4a01-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f4a01-152">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="f4a01-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
