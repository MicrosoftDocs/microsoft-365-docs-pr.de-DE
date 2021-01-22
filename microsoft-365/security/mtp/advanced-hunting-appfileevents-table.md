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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932874"
---
# <a name="appfileevents"></a><span data-ttu-id="7fb94-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="7fb94-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7fb94-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7fb94-105">**Applies to:**</span></span>
- <span data-ttu-id="7fb94-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fb94-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7fb94-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu dateibezogenen Aktivitäten in Cloud-Apps und Diensten, die von `AppFileEvents` Microsoft Cloud App Security überwacht werden. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7fb94-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7fb94-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7fb94-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="7fb94-109">Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="7fb94-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="7fb94-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7fb94-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7fb94-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7fb94-111">Column name</span></span> | <span data-ttu-id="7fb94-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7fb94-112">Data type</span></span> | <span data-ttu-id="7fb94-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fb94-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7fb94-114">datetime</span><span class="sxs-lookup"><span data-stu-id="7fb94-114">datetime</span></span> | <span data-ttu-id="7fb94-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7fb94-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7fb94-116">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-116">string</span></span> | <span data-ttu-id="7fb94-117">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="7fb94-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="7fb94-118">Weitere Informationen [finden Sie in der In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="7fb94-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="7fb94-119">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-119">string</span></span> | <span data-ttu-id="7fb94-120">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="7fb94-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="7fb94-121">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-121">string</span></span> | <span data-ttu-id="7fb94-122">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="7fb94-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="7fb94-123">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-123">string</span></span> | <span data-ttu-id="7fb94-124">Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="7fb94-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="7fb94-125">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-125">string</span></span> | <span data-ttu-id="7fb94-126">Ursprünglicher Name der Datei, die als Ergebnis der Aktion umbenannt wurde</span><span class="sxs-lookup"><span data-stu-id="7fb94-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="7fb94-127">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-127">string</span></span> | <span data-ttu-id="7fb94-128">Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="7fb94-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="7fb94-129">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-129">string</span></span> | <span data-ttu-id="7fb94-130">Verwendetes Netzwerkprotokoll</span><span class="sxs-lookup"><span data-stu-id="7fb94-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="7fb94-131">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-131">string</span></span> | <span data-ttu-id="7fb94-132">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="7fb94-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7fb94-133">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-133">string</span></span> | <span data-ttu-id="7fb94-134">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="7fb94-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7fb94-135">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-135">string</span></span> | <span data-ttu-id="7fb94-136">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="7fb94-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7fb94-137">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-137">string</span></span> | <span data-ttu-id="7fb94-138">Eindeutiger Bezeichner für das Konto in Azure AD</span><span class="sxs-lookup"><span data-stu-id="7fb94-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7fb94-139">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-139">string</span></span> | <span data-ttu-id="7fb94-140">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7fb94-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7fb94-141">In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="7fb94-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7fb94-142">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-142">string</span></span> | <span data-ttu-id="7fb94-143">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="7fb94-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="7fb94-144">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-144">string</span></span> | <span data-ttu-id="7fb94-145">Gerätetyp</span><span class="sxs-lookup"><span data-stu-id="7fb94-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="7fb94-146">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-146">string</span></span> | <span data-ttu-id="7fb94-147">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7fb94-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7fb94-148">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7fb94-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="7fb94-149">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-149">string</span></span> | <span data-ttu-id="7fb94-150">Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="7fb94-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="7fb94-151">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-151">string</span></span> | <span data-ttu-id="7fb94-152">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="7fb94-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7fb94-153">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-153">string</span></span> | <span data-ttu-id="7fb94-154">Die IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="7fb94-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="7fb94-155">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-155">string</span></span> | <span data-ttu-id="7fb94-156">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="7fb94-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="7fb94-157">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-157">string</span></span> | <span data-ttu-id="7fb94-158">Internetdienstanbieter (Internet Service Provider, ISP), der der Endpunkt-IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="7fb94-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="7fb94-159">long</span><span class="sxs-lookup"><span data-stu-id="7fb94-159">long</span></span> | <span data-ttu-id="7fb94-160">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="7fb94-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7fb94-161">string</span><span class="sxs-lookup"><span data-stu-id="7fb94-161">string</span></span> | <span data-ttu-id="7fb94-162">Zusätzliche Informationen über die Entität oder das Ereignis</span><span class="sxs-lookup"><span data-stu-id="7fb94-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7fb94-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7fb94-163">Related topics</span></span>
- [<span data-ttu-id="7fb94-164">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="7fb94-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fb94-165">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7fb94-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7fb94-166">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="7fb94-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7fb94-167">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="7fb94-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7fb94-168">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7fb94-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7fb94-169">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7fb94-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
