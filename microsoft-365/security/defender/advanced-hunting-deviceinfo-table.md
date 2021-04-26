---
title: DeviceInfo-Tabelle im Schema für die erweiterte Suche
description: Weitere Informationen zu Betriebssystem, Computername und anderen Computerinformationen finden Sie in der DeviceInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, os, platform, users
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023129"
---
# <a name="deviceinfo"></a><span data-ttu-id="c95ad-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c95ad-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c95ad-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c95ad-105">**Applies to:**</span></span>
- <span data-ttu-id="c95ad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c95ad-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="c95ad-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c95ad-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="c95ad-108">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Geräten in der Organisation, einschließlich Betriebssystemversion, aktiven Benutzern `DeviceInfo` und Computernamen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c95ad-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="c95ad-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c95ad-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c95ad-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c95ad-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c95ad-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c95ad-111">Column name</span></span> | <span data-ttu-id="c95ad-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c95ad-112">Data type</span></span> | <span data-ttu-id="c95ad-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c95ad-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c95ad-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c95ad-114">datetime</span></span> | <span data-ttu-id="c95ad-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c95ad-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c95ad-116">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-116">string</span></span> | <span data-ttu-id="c95ad-117">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="c95ad-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c95ad-118">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-118">string</span></span> | <span data-ttu-id="c95ad-119">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="c95ad-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="c95ad-120">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-120">string</span></span> | <span data-ttu-id="c95ad-121">Version des Endpunkt-Agents oder -Sensors, der auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c95ad-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="c95ad-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c95ad-122">string</span></span> | <span data-ttu-id="c95ad-123">Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender for Endpoint-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c95ad-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="c95ad-124">Dies kann die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys sein.</span><span class="sxs-lookup"><span data-stu-id="c95ad-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="c95ad-125">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-125">string</span></span> | <span data-ttu-id="c95ad-126">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c95ad-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c95ad-127">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-127">string</span></span> | <span data-ttu-id="c95ad-128">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c95ad-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c95ad-129">Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7</span><span class="sxs-lookup"><span data-stu-id="c95ad-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="c95ad-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c95ad-130">string</span></span> | <span data-ttu-id="c95ad-131">Erstellen der Version des Betriebssystems, das auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c95ad-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="c95ad-132">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="c95ad-132">boolean</span></span> | <span data-ttu-id="c95ad-133">Boolescher Indikator, ob der Computer mit Azure Active Directory verbunden ist</span><span class="sxs-lookup"><span data-stu-id="c95ad-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="c95ad-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c95ad-134">string</span></span> | <span data-ttu-id="c95ad-135">Eindeutige ID für das Gerät in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c95ad-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="c95ad-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c95ad-136">string</span></span> | <span data-ttu-id="c95ad-137">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Computer angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="c95ad-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="c95ad-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c95ad-138">string</span></span> | <span data-ttu-id="c95ad-139">Computertag, das über die Registrierung hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="c95ad-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="c95ad-140">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-140">string</span></span> | <span data-ttu-id="c95ad-141">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c95ad-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="c95ad-142">string</span><span class="sxs-lookup"><span data-stu-id="c95ad-142">string</span></span> | <span data-ttu-id="c95ad-143">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="c95ad-143">Machine group of the machine.</span></span> <span data-ttu-id="c95ad-144">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c95ad-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="c95ad-145">long</span><span class="sxs-lookup"><span data-stu-id="c95ad-145">long</span></span> | <span data-ttu-id="c95ad-146">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="c95ad-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c95ad-147">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c95ad-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="c95ad-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c95ad-148">string</span></span> | <span data-ttu-id="c95ad-149">Zusätzliche Informationen zum Ereignis im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="c95ad-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="c95ad-150">Die Tabelle enthält Geräteinformationen basierend auf Takten, bei denen es sich um periodische Berichte oder `DeviceInfo` Signale eines Geräts handelt.</span><span class="sxs-lookup"><span data-stu-id="c95ad-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="c95ad-151">Alle 15 Minuten sendet das Gerät einen teilweisen Takt, der häufig geänderte Attribute wie `LoggedOnUsers` enthält.</span><span class="sxs-lookup"><span data-stu-id="c95ad-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="c95ad-152">Einmal am Tag wird ein vollständiger Takt mit den Attributen des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="c95ad-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="c95ad-153">Sie können die folgende Beispielabfrage verwenden, um den neuesten Status eines Geräts zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="c95ad-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="c95ad-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c95ad-154">Related topics</span></span>
- [<span data-ttu-id="c95ad-155">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c95ad-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c95ad-156">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c95ad-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c95ad-157">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c95ad-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c95ad-158">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="c95ad-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c95ad-159">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c95ad-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c95ad-160">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c95ad-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
