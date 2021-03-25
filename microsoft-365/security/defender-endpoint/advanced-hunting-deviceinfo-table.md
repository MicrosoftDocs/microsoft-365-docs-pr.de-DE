---
title: DeviceInfo-Tabelle im Schema für die erweiterte Suche
description: Weitere Informationen zu Betriebssystem, Computername und anderen Geräteinformationen finden Sie in der DeviceInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, deviceinfo, device, os, platform, users, DeviceInfo
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
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067064"
---
# <a name="deviceinfo"></a><span data-ttu-id="5cb2a-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="5cb2a-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5cb2a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5cb2a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5cb2a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5cb2a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="5cb2a-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5cb2a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5cb2a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="5cb2a-109">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Geräten in der Organisation, einschließlich der Betriebssystemversion, der aktiven Benutzer `DeviceInfo` und des [](advanced-hunting-overview.md) Computernamens.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="5cb2a-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5cb2a-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="5cb2a-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="5cb2a-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="5cb2a-112">Column name</span></span> | <span data-ttu-id="5cb2a-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5cb2a-113">Data type</span></span> | <span data-ttu-id="5cb2a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cb2a-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5cb2a-115">datetime</span><span class="sxs-lookup"><span data-stu-id="5cb2a-115">datetime</span></span> | <span data-ttu-id="5cb2a-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5cb2a-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5cb2a-117">string</span><span class="sxs-lookup"><span data-stu-id="5cb2a-117">string</span></span> | <span data-ttu-id="5cb2a-118">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="5cb2a-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5cb2a-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-119">string</span></span> | <span data-ttu-id="5cb2a-120">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="5cb2a-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="5cb2a-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-121">string</span></span> | <span data-ttu-id="5cb2a-122">Version des Endpunkt-Agents oder -Sensors, der auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="5cb2a-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="5cb2a-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-123">string</span></span> | <span data-ttu-id="5cb2a-124">Öffentliche IP-Adresse, die vom integrierten Gerät zum Herstellen einer Verbindung mit dem Defender for Endpoint-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="5cb2a-125">Dies kann die IP-Adresse des Geräts selbst, eines NAT-Geräts oder eines Proxys sein.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="5cb2a-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-126">string</span></span> | <span data-ttu-id="5cb2a-127">Architektur des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="5cb2a-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="5cb2a-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-128">string</span></span> | <span data-ttu-id="5cb2a-129">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5cb2a-130">Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7</span><span class="sxs-lookup"><span data-stu-id="5cb2a-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="5cb2a-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-131">string</span></span> | <span data-ttu-id="5cb2a-132">Buildversion des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="5cb2a-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="5cb2a-133">boolean</span><span class="sxs-lookup"><span data-stu-id="5cb2a-133">boolean</span></span> | <span data-ttu-id="5cb2a-134">Boolescher Indikator, ob das Gerät mit Azure Active Directory verbunden ist</span><span class="sxs-lookup"><span data-stu-id="5cb2a-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="5cb2a-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-135">string</span></span> | <span data-ttu-id="5cb2a-136">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Gerät angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="5cb2a-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="5cb2a-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-137">string</span></span> | <span data-ttu-id="5cb2a-138">Gerätetag, das über die Registrierung hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="5cb2a-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="5cb2a-139">long</span><span class="sxs-lookup"><span data-stu-id="5cb2a-139">long</span></span> | <span data-ttu-id="5cb2a-140">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5cb2a-141">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="5cb2a-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-142">string</span></span> | <span data-ttu-id="5cb2a-143">Version des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="5cb2a-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="5cb2a-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5cb2a-144">string</span></span> | <span data-ttu-id="5cb2a-145">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-145">Machine group of the machine.</span></span> <span data-ttu-id="5cb2a-146">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="5cb2a-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5cb2a-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5cb2a-147">Related topics</span></span>
- [<span data-ttu-id="5cb2a-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="5cb2a-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5cb2a-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="5cb2a-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5cb2a-150">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="5cb2a-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
