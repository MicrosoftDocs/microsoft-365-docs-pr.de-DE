---
title: Tabelle "AppFileEvents" im Schema "Erweiterte Suche"
description: Informationen zu dateibezogenen Ereignissen im Zusammenhang mit Cloud-Apps und -Diensten in der Tabelle "AppFileEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145487"
---
# <a name="appfileevents"></a><span data-ttu-id="0ef50-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0ef50-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0ef50-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0ef50-105">**Applies to:**</span></span>
- <span data-ttu-id="0ef50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ef50-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0ef50-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu dateibezogenen Aktivitäten in Cloud-Apps und Diensten, die von `AppFileEvents` Microsoft Cloud App Security überwacht werden. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0ef50-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0ef50-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0ef50-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0ef50-109">Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="0ef50-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0ef50-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0ef50-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0ef50-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0ef50-111">Column name</span></span> | <span data-ttu-id="0ef50-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0ef50-112">Data type</span></span> | <span data-ttu-id="0ef50-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ef50-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0ef50-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0ef50-114">datetime</span></span> | <span data-ttu-id="0ef50-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="0ef50-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0ef50-116">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-116">string</span></span> | <span data-ttu-id="0ef50-117">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="0ef50-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="0ef50-118">Details finden Sie in der [In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="0ef50-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="0ef50-119">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-119">string</span></span> | <span data-ttu-id="0ef50-120">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="0ef50-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="0ef50-121">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-121">string</span></span> | <span data-ttu-id="0ef50-122">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="0ef50-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0ef50-123">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-123">string</span></span> | <span data-ttu-id="0ef50-124">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="0ef50-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="0ef50-125">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-125">string</span></span> | <span data-ttu-id="0ef50-126">Der ursprüngliche Name der Datei, die als Ergebnis der Aktion umbenannt wurde</span><span class="sxs-lookup"><span data-stu-id="0ef50-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="0ef50-127">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-127">string</span></span> | <span data-ttu-id="0ef50-128">Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="0ef50-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="0ef50-129">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-129">string</span></span> | <span data-ttu-id="0ef50-130">Verwendetes Netzwerkprotokoll</span><span class="sxs-lookup"><span data-stu-id="0ef50-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="0ef50-131">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-131">string</span></span> | <span data-ttu-id="0ef50-132">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="0ef50-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0ef50-133">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-133">string</span></span> | <span data-ttu-id="0ef50-134">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="0ef50-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0ef50-135">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-135">string</span></span> | <span data-ttu-id="0ef50-136">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="0ef50-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0ef50-137">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-137">string</span></span> | <span data-ttu-id="0ef50-138">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="0ef50-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0ef50-139">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-139">string</span></span> | <span data-ttu-id="0ef50-140">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="0ef50-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0ef50-141">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-141">string</span></span> | <span data-ttu-id="0ef50-142">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0ef50-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0ef50-143">In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="0ef50-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0ef50-144">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-144">string</span></span> | <span data-ttu-id="0ef50-145">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="0ef50-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="0ef50-146">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-146">string</span></span> | <span data-ttu-id="0ef50-147">Gerätetyp</span><span class="sxs-lookup"><span data-stu-id="0ef50-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="0ef50-148">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-148">string</span></span> | <span data-ttu-id="0ef50-149">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0ef50-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0ef50-150">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0ef50-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0ef50-151">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-151">string</span></span> | <span data-ttu-id="0ef50-152">Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0ef50-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="0ef50-153">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-153">string</span></span> | <span data-ttu-id="0ef50-154">Während der Kommunikation verwendeter TCP-Port</span><span class="sxs-lookup"><span data-stu-id="0ef50-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="0ef50-155">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-155">string</span></span> | <span data-ttu-id="0ef50-156">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="0ef50-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0ef50-157">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-157">string</span></span> | <span data-ttu-id="0ef50-158">Die IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="0ef50-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="0ef50-159">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-159">string</span></span> | <span data-ttu-id="0ef50-160">Zielport der zugehörigen Netzwerkkommunikation</span><span class="sxs-lookup"><span data-stu-id="0ef50-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="0ef50-161">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-161">string</span></span> | <span data-ttu-id="0ef50-162">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="0ef50-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="0ef50-163">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-163">string</span></span> | <span data-ttu-id="0ef50-164">Internetdienstanbieter (Internet Service Provider, ISP), der der Endpunkt-IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="0ef50-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="0ef50-165">long</span><span class="sxs-lookup"><span data-stu-id="0ef50-165">long</span></span> | <span data-ttu-id="0ef50-166">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="0ef50-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0ef50-167">string</span><span class="sxs-lookup"><span data-stu-id="0ef50-167">string</span></span> | <span data-ttu-id="0ef50-168">Zusätzliche Informationen über die Entität oder das Ereignis</span><span class="sxs-lookup"><span data-stu-id="0ef50-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0ef50-169">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0ef50-169">Related topics</span></span>
- [<span data-ttu-id="0ef50-170">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="0ef50-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0ef50-171">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="0ef50-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0ef50-172">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="0ef50-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0ef50-173">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="0ef50-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0ef50-174">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="0ef50-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0ef50-175">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="0ef50-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
