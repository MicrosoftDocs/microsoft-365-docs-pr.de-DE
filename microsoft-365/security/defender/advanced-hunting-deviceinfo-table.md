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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689109"
---
# <a name="deviceinfo"></a><span data-ttu-id="e80ff-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="e80ff-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e80ff-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e80ff-105">**Applies to:**</span></span>
- <span data-ttu-id="e80ff-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e80ff-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="e80ff-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e80ff-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="e80ff-108">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Geräten in der Organisation, einschließlich Betriebssystemversion, aktiven Benutzern `DeviceInfo` und Computernamen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e80ff-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="e80ff-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e80ff-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e80ff-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e80ff-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e80ff-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="e80ff-111">Column name</span></span> | <span data-ttu-id="e80ff-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e80ff-112">Data type</span></span> | <span data-ttu-id="e80ff-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e80ff-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e80ff-114">datetime</span><span class="sxs-lookup"><span data-stu-id="e80ff-114">datetime</span></span> | <span data-ttu-id="e80ff-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e80ff-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e80ff-116">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-116">string</span></span> | <span data-ttu-id="e80ff-117">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="e80ff-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e80ff-118">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-118">string</span></span> | <span data-ttu-id="e80ff-119">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="e80ff-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="e80ff-120">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-120">string</span></span> | <span data-ttu-id="e80ff-121">Version des Endpunkt-Agents oder -Sensors, der auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="e80ff-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="e80ff-122">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-122">string</span></span> | <span data-ttu-id="e80ff-123">Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender for Endpoint-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e80ff-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="e80ff-124">Dies kann die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys sein.</span><span class="sxs-lookup"><span data-stu-id="e80ff-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="e80ff-125">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-125">string</span></span> | <span data-ttu-id="e80ff-126">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e80ff-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="e80ff-127">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-127">string</span></span> | <span data-ttu-id="e80ff-128">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e80ff-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="e80ff-129">Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7</span><span class="sxs-lookup"><span data-stu-id="e80ff-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="e80ff-130">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-130">string</span></span> | <span data-ttu-id="e80ff-131">Erstellen der Version des Betriebssystems, das auf dem Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="e80ff-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="e80ff-132">boolean</span><span class="sxs-lookup"><span data-stu-id="e80ff-132">boolean</span></span> | <span data-ttu-id="e80ff-133">Boolescher Indikator, ob der Computer mit der Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e80ff-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="e80ff-134">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-134">string</span></span> | <span data-ttu-id="e80ff-135">Eindeutige ID für das Gerät in Azure AD</span><span class="sxs-lookup"><span data-stu-id="e80ff-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="e80ff-136">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-136">string</span></span> | <span data-ttu-id="e80ff-137">Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Computer angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="e80ff-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="e80ff-138">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-138">string</span></span> | <span data-ttu-id="e80ff-139">Computertag, das über die Registrierung hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="e80ff-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="e80ff-140">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-140">string</span></span> | <span data-ttu-id="e80ff-141">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e80ff-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="e80ff-142">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-142">string</span></span> | <span data-ttu-id="e80ff-143">Computergruppe des Computers.</span><span class="sxs-lookup"><span data-stu-id="e80ff-143">Machine group of the machine.</span></span> <span data-ttu-id="e80ff-144">Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e80ff-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="e80ff-145">long</span><span class="sxs-lookup"><span data-stu-id="e80ff-145">long</span></span> | <span data-ttu-id="e80ff-146">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="e80ff-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e80ff-147">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e80ff-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="e80ff-148">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-148">string</span></span> | <span data-ttu-id="e80ff-149">Gibt an, ob das Gerät derzeit in Microsoft Defender For Endpoint onboarded ist oder ob das Gerät nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e80ff-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="e80ff-150">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-150">string</span></span> | <span data-ttu-id="e80ff-151">Zusätzliche Informationen zum Ereignis im JSON-Arrayformat</span><span class="sxs-lookup"><span data-stu-id="e80ff-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="e80ff-152">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-152">string</span></span> | <span data-ttu-id="e80ff-153">Umfassendere Klassifizierung, die bestimmte Gerätetypen in den folgenden Kategorien einteilt: Endpunkt, Netzwerkgerät, IoT, Unbekannt</span><span class="sxs-lookup"><span data-stu-id="e80ff-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="e80ff-154">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-154">string</span></span> | <span data-ttu-id="e80ff-155">Gerätetyp basierend auf Zweck und Funktionalität, z. B. Netzwerkgerät, Arbeitsstation, Server, Mobil, Spielekonsole oder Drucker</span><span class="sxs-lookup"><span data-stu-id="e80ff-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="e80ff-156">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-156">string</span></span> | <span data-ttu-id="e80ff-157">Zusätzlicher Modifizierer für bestimmte Gerätetypen, z. B. ein mobiles Gerät kann ein Tablet oder ein Smartphone sein</span><span class="sxs-lookup"><span data-stu-id="e80ff-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="e80ff-158">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-158">string</span></span> | <span data-ttu-id="e80ff-159">Modellname oder Nummer des Produkts des Herstellers oder Herstellers</span><span class="sxs-lookup"><span data-stu-id="e80ff-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="e80ff-160">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-160">string</span></span> | <span data-ttu-id="e80ff-161">Name des Produktanbieters oder Herstellers</span><span class="sxs-lookup"><span data-stu-id="e80ff-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="e80ff-162">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-162">string</span></span> | <span data-ttu-id="e80ff-163">Verteilung der Betriebssystemplattform, z. B. Ubuntu oder RedHat für Linux-Plattformen</span><span class="sxs-lookup"><span data-stu-id="e80ff-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="e80ff-164">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-164">string</span></span> | <span data-ttu-id="e80ff-165">Zusätzliche Informationen zur Betriebssystemversion, z. B. der beliebte Name, der Codename oder die Versionsnummer</span><span class="sxs-lookup"><span data-stu-id="e80ff-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="e80ff-166">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-166">string</span></span> | <span data-ttu-id="e80ff-167">Frühere Geräte-IDs, die demselben Gerät zugewiesen wurden</span><span class="sxs-lookup"><span data-stu-id="e80ff-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="e80ff-168">string</span><span class="sxs-lookup"><span data-stu-id="e80ff-168">string</span></span> | <span data-ttu-id="e80ff-169">Die neueste Geräte-ID, die einem Gerät zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="e80ff-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="e80ff-170">Die Tabelle enthält Geräteinformationen basierend auf Takten, bei denen es sich um periodische Berichte oder `DeviceInfo` Signale eines Geräts handelt.</span><span class="sxs-lookup"><span data-stu-id="e80ff-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="e80ff-171">Alle 15 Minuten sendet das Gerät einen teilweisen Takt, der häufig geänderte Attribute wie `LoggedOnUsers` enthält.</span><span class="sxs-lookup"><span data-stu-id="e80ff-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="e80ff-172">Einmal am Tag wird ein vollständiger Takt mit den Attributen des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="e80ff-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="e80ff-173">Sie können die folgende Beispielabfrage verwenden, um den neuesten Status eines Geräts zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="e80ff-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="e80ff-174">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e80ff-174">Related topics</span></span>
- [<span data-ttu-id="e80ff-175">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="e80ff-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e80ff-176">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="e80ff-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e80ff-177">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="e80ff-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e80ff-178">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="e80ff-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e80ff-179">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="e80ff-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e80ff-180">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="e80ff-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
