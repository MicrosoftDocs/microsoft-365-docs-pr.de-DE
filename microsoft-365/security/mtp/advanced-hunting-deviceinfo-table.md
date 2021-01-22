---
title: Tabelle "DeviceInfo" im Schema "Erweiterte Suche"
description: Informationen zu Betriebssystem, Computername und anderen Computerinformationen in der Tabelle "DeviceInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, MachineInfo, DeviceInfo, Gerät, Computer, BETRIEBSSYSTEM, Plattform, Benutzer
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
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931278"
---
# <a name="deviceinfo"></a><span data-ttu-id="079f4-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="079f4-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="079f4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="079f4-105">**Applies to:**</span></span>
- <span data-ttu-id="079f4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="079f4-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="079f4-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Computern in der Organisation, einschließlich Betriebssystemversion, aktiver Benutzer `DeviceInfo` und Computername. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="079f4-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="079f4-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="079f4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="079f4-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="079f4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="079f4-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="079f4-110">Column name</span></span> | <span data-ttu-id="079f4-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="079f4-111">Data type</span></span> | <span data-ttu-id="079f4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="079f4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="079f4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="079f4-113">datetime</span></span> | <span data-ttu-id="079f4-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="079f4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="079f4-115">string</span><span class="sxs-lookup"><span data-stu-id="079f4-115">string</span></span> | <span data-ttu-id="079f4-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="079f4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="079f4-117">string</span><span class="sxs-lookup"><span data-stu-id="079f4-117">string</span></span> | <span data-ttu-id="079f4-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="079f4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="079f4-119">string</span><span class="sxs-lookup"><span data-stu-id="079f4-119">string</span></span> | <span data-ttu-id="079f4-120">Version des Endpunkt-Agents oder Sensors, der auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="079f4-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="079f4-121">string</span><span class="sxs-lookup"><span data-stu-id="079f4-121">string</span></span> | <span data-ttu-id="079f4-122">Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender für Endpunktdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="079f4-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="079f4-123">Dies kann die IP-Adresse des Computers selbst, ein NAT-Gerät oder ein Proxy sein.</span><span class="sxs-lookup"><span data-stu-id="079f4-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="079f4-124">string</span><span class="sxs-lookup"><span data-stu-id="079f4-124">string</span></span> | <span data-ttu-id="079f4-125">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="079f4-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="079f4-126">string</span><span class="sxs-lookup"><span data-stu-id="079f4-126">string</span></span> | <span data-ttu-id="079f4-127">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="079f4-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="079f4-128">Dies weist auf bestimmte Betriebssysteme hin, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="079f4-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="079f4-129">string</span><span class="sxs-lookup"><span data-stu-id="079f4-129">string</span></span> | <span data-ttu-id="079f4-130">Buildversion des Betriebssystems, das auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="079f4-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="079f4-131">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="079f4-131">boolean</span></span> | <span data-ttu-id="079f4-132">Boolescher Indikator dafür, ob der Computer mit Azure Active Directory verbunden ist</span><span class="sxs-lookup"><span data-stu-id="079f4-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="079f4-133">string</span><span class="sxs-lookup"><span data-stu-id="079f4-133">string</span></span> | <span data-ttu-id="079f4-134">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Array-Format auf dem Computer angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="079f4-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="079f4-135">string</span><span class="sxs-lookup"><span data-stu-id="079f4-135">string</span></span> | <span data-ttu-id="079f4-136">Computertag, das über die Registrierung hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="079f4-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="079f4-137">long</span><span class="sxs-lookup"><span data-stu-id="079f4-137">long</span></span> | <span data-ttu-id="079f4-138">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="079f4-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="079f4-139">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="079f4-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="079f4-140">string</span><span class="sxs-lookup"><span data-stu-id="079f4-140">string</span></span> | <span data-ttu-id="079f4-141">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="079f4-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="079f4-142">string</span><span class="sxs-lookup"><span data-stu-id="079f4-142">string</span></span> | <span data-ttu-id="079f4-143">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="079f4-143">Machine group of the machine.</span></span> <span data-ttu-id="079f4-144">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="079f4-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="079f4-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="079f4-145">Related topics</span></span>
- [<span data-ttu-id="079f4-146">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="079f4-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="079f4-147">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="079f4-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="079f4-148">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="079f4-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="079f4-149">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="079f4-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="079f4-150">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="079f4-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="079f4-151">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="079f4-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
