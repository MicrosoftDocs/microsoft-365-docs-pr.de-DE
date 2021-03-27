---
title: DeviceInfo-Tabelle im Schema für die erweiterte Suche
description: Weitere Informationen zu Betriebssystem, Computername und anderen Computerinformationen finden Sie in der DeviceInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, os, platform, users
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d56710f4933a8971230c78d7b3570f14b9bda335
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382625"
---
# <a name="deviceinfo"></a><span data-ttu-id="089eb-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="089eb-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="089eb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="089eb-105">**Applies to:**</span></span>
- <span data-ttu-id="089eb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="089eb-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="089eb-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Geräten in der Organisation, einschließlich Betriebssystemversion, aktiven Benutzern `DeviceInfo` und Computernamen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="089eb-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="089eb-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="089eb-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="089eb-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="089eb-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="089eb-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="089eb-110">Column name</span></span> | <span data-ttu-id="089eb-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="089eb-111">Data type</span></span> | <span data-ttu-id="089eb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="089eb-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="089eb-113">datetime</span><span class="sxs-lookup"><span data-stu-id="089eb-113">datetime</span></span> | <span data-ttu-id="089eb-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="089eb-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="089eb-115">string</span><span class="sxs-lookup"><span data-stu-id="089eb-115">string</span></span> | <span data-ttu-id="089eb-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="089eb-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="089eb-117">string</span><span class="sxs-lookup"><span data-stu-id="089eb-117">string</span></span> | <span data-ttu-id="089eb-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="089eb-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="089eb-119">string</span><span class="sxs-lookup"><span data-stu-id="089eb-119">string</span></span> | <span data-ttu-id="089eb-120">Version des Endpunkt-Agents oder -Sensors, der auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="089eb-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="089eb-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="089eb-121">string</span></span> | <span data-ttu-id="089eb-122">Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender for Endpoint-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="089eb-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="089eb-123">Dies kann die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys sein.</span><span class="sxs-lookup"><span data-stu-id="089eb-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="089eb-124">string</span><span class="sxs-lookup"><span data-stu-id="089eb-124">string</span></span> | <span data-ttu-id="089eb-125">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="089eb-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="089eb-126">string</span><span class="sxs-lookup"><span data-stu-id="089eb-126">string</span></span> | <span data-ttu-id="089eb-127">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="089eb-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="089eb-128">Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7</span><span class="sxs-lookup"><span data-stu-id="089eb-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="089eb-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="089eb-129">string</span></span> | <span data-ttu-id="089eb-130">Erstellen der Version des Betriebssystems, das auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="089eb-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="089eb-131">boolean</span><span class="sxs-lookup"><span data-stu-id="089eb-131">boolean</span></span> | <span data-ttu-id="089eb-132">Boolescher Indikator, ob der Computer mit Azure Active Directory verbunden ist</span><span class="sxs-lookup"><span data-stu-id="089eb-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="089eb-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="089eb-133">string</span></span> | <span data-ttu-id="089eb-134">Eindeutige ID für das Gerät in Azure AD</span><span class="sxs-lookup"><span data-stu-id="089eb-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="089eb-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="089eb-135">string</span></span> | <span data-ttu-id="089eb-136">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Computer angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="089eb-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="089eb-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="089eb-137">string</span></span> | <span data-ttu-id="089eb-138">Computertag, das über die Registrierung hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="089eb-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="089eb-139">string</span><span class="sxs-lookup"><span data-stu-id="089eb-139">string</span></span> | <span data-ttu-id="089eb-140">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="089eb-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="089eb-141">string</span><span class="sxs-lookup"><span data-stu-id="089eb-141">string</span></span> | <span data-ttu-id="089eb-142">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="089eb-142">Machine group of the machine.</span></span> <span data-ttu-id="089eb-143">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="089eb-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="089eb-144">long</span><span class="sxs-lookup"><span data-stu-id="089eb-144">long</span></span> | <span data-ttu-id="089eb-145">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="089eb-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="089eb-146">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="089eb-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="089eb-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="089eb-147">string</span></span> | <span data-ttu-id="089eb-148">Zusätzliche Informationen zum Ereignis im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="089eb-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="089eb-149">Die Tabelle enthält Geräteinformationen basierend auf Takten, bei denen es sich um periodische Berichte oder `DeviceInfo` Signale eines Geräts handelt.</span><span class="sxs-lookup"><span data-stu-id="089eb-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="089eb-150">Alle 15 Minuten sendet das Gerät einen teilweisen Takt, der häufig geänderte Attribute wie `LoggedOnUsers` enthält.</span><span class="sxs-lookup"><span data-stu-id="089eb-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="089eb-151">Einmal am Tag wird ein vollständiger Takt mit den Attributen des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="089eb-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="089eb-152">Sie können die folgende Beispielabfrage verwenden, um den neuesten Status eines Geräts zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="089eb-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="089eb-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="089eb-153">Related topics</span></span>
- [<span data-ttu-id="089eb-154">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="089eb-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="089eb-155">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="089eb-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="089eb-156">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="089eb-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="089eb-157">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="089eb-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="089eb-158">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="089eb-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="089eb-159">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="089eb-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
