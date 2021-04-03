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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500830"
---
# <a name="deviceinfo"></a><span data-ttu-id="f9071-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="f9071-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9071-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f9071-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9071-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f9071-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="f9071-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f9071-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f9071-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f9071-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="f9071-109">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Geräten in der Organisation, einschließlich der Betriebssystemversion, der aktiven Benutzer `DeviceInfo` und des [](advanced-hunting-overview.md) Computernamens.</span><span class="sxs-lookup"><span data-stu-id="f9071-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="f9071-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f9071-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f9071-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="f9071-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="f9071-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f9071-112">Column name</span></span> | <span data-ttu-id="f9071-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f9071-113">Data type</span></span> | <span data-ttu-id="f9071-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9071-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f9071-115">datetime</span><span class="sxs-lookup"><span data-stu-id="f9071-115">datetime</span></span> | <span data-ttu-id="f9071-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="f9071-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f9071-117">string</span><span class="sxs-lookup"><span data-stu-id="f9071-117">string</span></span> | <span data-ttu-id="f9071-118">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="f9071-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f9071-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-119">string</span></span> | <span data-ttu-id="f9071-120">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="f9071-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="f9071-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-121">string</span></span> | <span data-ttu-id="f9071-122">Version des Endpunkt-Agents oder -Sensors, der auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f9071-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="f9071-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-123">string</span></span> | <span data-ttu-id="f9071-124">Öffentliche IP-Adresse, die vom integrierten Gerät zum Herstellen einer Verbindung mit dem Defender for Endpoint-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9071-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="f9071-125">Dies kann die IP-Adresse des Geräts selbst, eines NAT-Geräts oder eines Proxys sein.</span><span class="sxs-lookup"><span data-stu-id="f9071-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="f9071-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-126">string</span></span> | <span data-ttu-id="f9071-127">Architektur des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f9071-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="f9071-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-128">string</span></span> | <span data-ttu-id="f9071-129">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9071-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f9071-130">Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7</span><span class="sxs-lookup"><span data-stu-id="f9071-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="f9071-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-131">string</span></span> | <span data-ttu-id="f9071-132">Buildversion des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f9071-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="f9071-133">boolean</span><span class="sxs-lookup"><span data-stu-id="f9071-133">boolean</span></span> | <span data-ttu-id="f9071-134">Boolescher Indikator, ob das Gerät mit Azure Active Directory verbunden ist</span><span class="sxs-lookup"><span data-stu-id="f9071-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="f9071-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-135">string</span></span> | <span data-ttu-id="f9071-136">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Gerät angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="f9071-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="f9071-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-137">string</span></span> | <span data-ttu-id="f9071-138">Gerätetag, das über die Registrierung hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="f9071-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="f9071-139">long</span><span class="sxs-lookup"><span data-stu-id="f9071-139">long</span></span> | <span data-ttu-id="f9071-140">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="f9071-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f9071-141">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9071-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="f9071-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-142">string</span></span> | <span data-ttu-id="f9071-143">Version des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f9071-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="f9071-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f9071-144">string</span></span> | <span data-ttu-id="f9071-145">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="f9071-145">Machine group of the machine.</span></span> <span data-ttu-id="f9071-146">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f9071-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f9071-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f9071-147">Related topics</span></span>
- [<span data-ttu-id="f9071-148">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f9071-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9071-149">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="f9071-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9071-150">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="f9071-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
