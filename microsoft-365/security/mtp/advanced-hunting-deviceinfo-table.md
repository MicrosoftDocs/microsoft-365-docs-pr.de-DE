---
title: DeviceInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Betriebssystem, Computername und andere Computer Informationen in der deviceInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, machineinfo, deviceInfo, Gerät, Computer, OS, Plattform, Benutzer
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
ms.openlocfilehash: 342e5747f2c59022ffef76f30e4845f26550c88a
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649085"
---
# <a name="deviceinfo"></a><span data-ttu-id="33e7f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="33e7f-104">DeviceInfo</span></span>

<span data-ttu-id="33e7f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="33e7f-105">**Applies to:**</span></span>
- <span data-ttu-id="33e7f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="33e7f-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="33e7f-107">Die `DeviceInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Computern in der Organisation, einschließlich Betriebssystemversion, aktive Benutzer und Computername.</span><span class="sxs-lookup"><span data-stu-id="33e7f-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="33e7f-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="33e7f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="33e7f-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="33e7f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="33e7f-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="33e7f-110">Column name</span></span> | <span data-ttu-id="33e7f-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="33e7f-111">Data type</span></span> | <span data-ttu-id="33e7f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e7f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="33e7f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="33e7f-113">datetime</span></span> | <span data-ttu-id="33e7f-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="33e7f-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="33e7f-115">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-115">string</span></span> | <span data-ttu-id="33e7f-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="33e7f-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="33e7f-117">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-117">string</span></span> | <span data-ttu-id="33e7f-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="33e7f-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="33e7f-119">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-119">string</span></span> | <span data-ttu-id="33e7f-120">Version des Endpunkt-Agents oder-Sensors, der auf dem Computer läuft</span><span class="sxs-lookup"><span data-stu-id="33e7f-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="33e7f-121">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-121">string</span></span> | <span data-ttu-id="33e7f-122">Öffentliche IP-Adresse, die vom Onboarding-Computer zum Herstellen einer Verbindung mit dem Microsoft Defender ATP-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="33e7f-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="33e7f-123">Hierbei kann es sich um die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys handeln.</span><span class="sxs-lookup"><span data-stu-id="33e7f-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="33e7f-124">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-124">string</span></span> | <span data-ttu-id="33e7f-125">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33e7f-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="33e7f-126">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-126">string</span></span> | <span data-ttu-id="33e7f-127">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33e7f-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="33e7f-128">Dies weist auf bestimmte Betriebssysteme hin, einschließlich Variationen innerhalb der gleichen Familie wie Windows 10 und Windows 7</span><span class="sxs-lookup"><span data-stu-id="33e7f-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="33e7f-129">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-129">string</span></span> | <span data-ttu-id="33e7f-130">Buildversion des Betriebssystems, das auf dem Computer läuft</span><span class="sxs-lookup"><span data-stu-id="33e7f-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="33e7f-131">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="33e7f-131">boolean</span></span> | <span data-ttu-id="33e7f-132">Boolescher Indikator dafür, ob der Computer mit dem Azure-Active Directory verbunden ist</span><span class="sxs-lookup"><span data-stu-id="33e7f-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="33e7f-133">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-133">string</span></span> | <span data-ttu-id="33e7f-134">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Array Format auf dem Computer angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="33e7f-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="33e7f-135">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-135">string</span></span> | <span data-ttu-id="33e7f-136">Durch die Registrierung hinzugefügtes Machine-Tag</span><span class="sxs-lookup"><span data-stu-id="33e7f-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="33e7f-137">long</span><span class="sxs-lookup"><span data-stu-id="33e7f-137">long</span></span> | <span data-ttu-id="33e7f-138">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="33e7f-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="33e7f-139">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33e7f-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="33e7f-140">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-140">string</span></span> | <span data-ttu-id="33e7f-141">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33e7f-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="33e7f-142">string</span><span class="sxs-lookup"><span data-stu-id="33e7f-142">string</span></span> | <span data-ttu-id="33e7f-143">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="33e7f-143">Machine group of the machine.</span></span> <span data-ttu-id="33e7f-144">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="33e7f-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="33e7f-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="33e7f-145">Related topics</span></span>
- [<span data-ttu-id="33e7f-146">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="33e7f-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="33e7f-147">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="33e7f-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="33e7f-148">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="33e7f-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="33e7f-149">Jagd auf Geräte, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="33e7f-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="33e7f-150">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="33e7f-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="33e7f-151">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="33e7f-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
